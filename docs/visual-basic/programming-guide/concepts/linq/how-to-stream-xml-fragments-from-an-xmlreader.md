---
title: HOW TO：從 XmlReader 串流 XML 片段（Visual Basic）
ms.date: 07/20/2015
ms.assetid: f67ce598-4a12-4dcb-9a07-24deca02a111
ms.openlocfilehash: 3edb9cbbe9b649a5b4d232a3937e6f322b4a6b7d
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/03/2019
ms.locfileid: "71835151"
---
# <a name="how-to-stream-xml-fragments-from-an-xmlreader-visual-basic"></a>HOW TO：從 XmlReader 串流 XML 片段（Visual Basic）
當您必須處理大型 XML 檔案時，可能無法將整個 XML 樹狀載入記憶體中。 這個主題顯示如何使用 <xref:System.Xml.XmlReader> 串流片段。  
  
 使用 <xref:System.Xml.XmlReader> 讀取 <xref:System.Xml.Linq.XElement> 物件的其中一個最有效方式為，撰寫您自己自訂的座標軸方法。 座標軸方法通常會傳回集合，例如，<xref:System.Collections.Generic.IEnumerable%601> 的 <xref:System.Xml.Linq.XElement>，如本主題的範例中所示。 在自訂座標軸方法中，呼叫 <xref:System.Xml.Linq.XNode.ReadFrom%2A> 方法來建立 XML 片段後，使用 `yield return` 傳回集合。 這會將延後執行語意 (Semantics) 提供給您自訂的座標軸方法。  
  
 當您從 <xref:System.Xml.XmlReader> 物件建立 XML 樹狀結構時，<xref:System.Xml.XmlReader> 必須定位在項目上。 <xref:System.Xml.Linq.XNode.ReadFrom%2A> 方法在讀取項目的關閉標記前不會傳回。  
  
 如果您要建立部分樹狀結構，您可以具現化 <xref:System.Xml.XmlReader>、將讀取器定位在您要轉換為 <xref:System.Xml.Linq.XElement> 樹狀結構的節點上，然後建立 <xref:System.Xml.Linq.XElement> 物件。  
  
 [如何：具有標頭資訊（Visual Basic）存取權的資料流程 XML 片段 ](../../../../visual-basic/programming-guide/concepts/linq/how-to-stream-xml-fragments-with-access-to-header-information.md) 包含如何串流更複雜檔的資訊和範例。  
  
 [如何：執行大型 XML 檔的串流轉換（Visual Basic） ](../../../../visual-basic/programming-guide/concepts/linq/how-to-perform-streaming-transform-of-large-xml-documents.md) 包含使用 LINQ to XML 轉換非常大的 XML 檔，同時維持小型記憶體使用量的範例。  
  
## <a name="example"></a>範例  
 這個範例會建立自訂座標軸方法。 您可以使用 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 查詢進行查詢。 自訂座標軸方法  `StreamRootChildDoc` 是一種方法，特別針對讀取具有重複 `Child` 項目的文件而設計。  
  
```vb  
Module Module1  
    Sub Main()  
        Dim markup = "<Root>" &  
                     "  <Child Key=""01"">" &  
                     "    <GrandChild>aaa</GrandChild>" &  
                     "  </Child>" &  
                     "  <Child Key=""02"">" &  
                     "    <GrandChild>bbb</GrandChild>" &  
                     "  </Child>" &  
                     "  <Child Key=""03"">" &  
                     "    <GrandChild>ccc</GrandChild>" &  
                     "  </Child>" &  
                     "</Root>"  
  
        Dim grandChildData =  
             From el In New StreamRootChildDoc(New IO.StringReader(markup))  
             Where CInt(el.@Key) > 1  
             Select el.<GrandChild>.Value  
  
        For Each s In grandChildData  
            Console.WriteLine(s)  
        Next  
    End Sub  
End Module  
  
Public Class StreamRootChildDoc  
    Implements IEnumerable(Of XElement)  
  
    Private _stringReader As IO.StringReader  
  
    Public Sub New(ByVal stringReader As IO.StringReader)  
        _stringReader = stringReader  
    End Sub  
  
    Public Function GetEnumerator() As IEnumerator(Of XElement) Implements IEnumerable(Of XElement).GetEnumerator  
        Return New StreamChildEnumerator(_stringReader)  
    End Function  
  
    Public Function GetEnumerator1() As IEnumerator Implements IEnumerable.GetEnumerator  
        Return Me.GetEnumerator()  
    End Function  
End Class  
  
Public Class StreamChildEnumerator  
    Implements IEnumerator(Of XElement)  
  
    Private _current As XElement  
    Private _reader As Xml.XmlReader  
    Private _stringReader As IO.StringReader  
  
    Public Sub New(ByVal stringReader As IO.StringReader)  
        _stringReader = stringReader  
        _reader = Xml.XmlReader.Create(_stringReader)  
        _reader.MoveToContent()  
    End Sub  
  
    Public ReadOnly Property Current As XElement Implements IEnumerator(Of XElement).Current  
        Get  
            Return _current  
        End Get  
    End Property  
  
    Public ReadOnly Property Current1 As Object Implements IEnumerator.Current  
        Get  
            Return Me.Current  
        End Get  
    End Property  
  
    Public Function MoveNext() As Boolean Implements IEnumerator.MoveNext  
        While _reader.Read()  
            Select Case _reader.NodeType  
                Case Xml.XmlNodeType.Element  
                    Dim el = TryCast(XElement.ReadFrom(_reader), XElement)  
                    If el IsNot Nothing Then  
                        _current = el  
                        Return True  
                    End If  
            End Select  
        End While  
  
        Return False  
    End Function  
  
    Public Sub Reset() Implements IEnumerator.Reset  
        _reader = Xml.XmlReader.Create(_stringReader)  
        _reader.MoveToContent()  
    End Sub  
  
#Region "IDisposable Support"  
    Private disposedValue As Boolean ' To detect redundant calls  
  
    ' IDisposable  
    Protected Overridable Sub Dispose(ByVal disposing As Boolean)  
        If Not Me.disposedValue Then  
            If disposing Then  
                _reader.Close()  
            End If  
        End If  
        Me.disposedValue = True  
    End Sub  
  
    Public Sub Dispose() Implements IDisposable.Dispose  
        Dispose(True)  
        GC.SuppressFinalize(Me)  
    End Sub  
#End Region  
  
End Class  
```  
  
 這個範例會產生下列輸出：  
  
```console  
bbb  
ccc  
```  
  
 在此範例中，來源文件很小。 但是，即使有數百萬的 `Child` 元素，此範例的記憶體使用量還是很小。  
  
## <a name="see-also"></a>另請參閱

- [逐步解說：在 Visual Basic @ no__t-0 中執行 IEnumerable （of T）
- [剖析 XML （Visual Basic）](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
