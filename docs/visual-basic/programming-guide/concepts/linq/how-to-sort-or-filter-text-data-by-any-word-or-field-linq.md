---
title: 如何：依任何字或欄位排序或篩選文字資料 (LINQ) (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 9df137fe-335b-46e0-aecf-ea8a9eddd4e3
ms.openlocfilehash: fa9efc51f72a47acfa32d42fc9ff8e5aadf61721
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524122"
---
# <a name="how-to-sort-or-filter-text-data-by-any-word-or-field-linq-visual-basic"></a>如何：依任何字或欄位排序或篩選文字資料 (LINQ) (Visual Basic)

下列範例示範如何依行中的任一欄位，來排序多行結構化文字 (例如逗號分隔值)。 此欄位可能會在執行階段以動態方式指定。 假設 scores.csv 中的欄位各代表學生的學號和四個測驗分數。

### <a name="to-create-a-file-that-contains-data"></a>建立內含資料的檔案

從[如何：從不同的檔案聯結內容（LINQ）（Visual Basic）](../../../../visual-basic/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md)主題複製分數 .csv 資料，並將它儲存至您的方案資料夾。

## <a name="example"></a>範例

```vb
Class SortLines

    Shared Sub Main()
        Dim scores As String() = System.IO.File.ReadAllLines("../../../scores.csv")

        ' Change this to any value from 0 to 4
        Dim sortField As Integer = 1

        Console.WriteLine("Sorted highest to lowest by field " & sortField)

        ' Demonstrates how to return query from a method.
        ' The query is executed here.
        For Each str As String In SortQuery(scores, sortField)
            Console.WriteLine(str)
        Next

        ' Keep console window open in debug mode.
        Console.WriteLine("Press any key to exit.")
        Console.ReadKey()

    End Sub

    Shared Function SortQuery(
        ByVal source As IEnumerable(Of String),
        ByVal num As Integer) As IEnumerable(Of String)

        Dim scoreQuery = From line In source
                         Let fields = line.Split(New Char() {","})
                         Order By fields(num) Descending
                         Select line

        Return scoreQuery
    End Function
End Class
' Output:
' Sorted highest to lowest by field 1
' 116, 99, 86, 90, 94
' 120, 99, 82, 81, 79
' 111, 97, 92, 81, 60
' 114, 97, 89, 85, 82
' 121, 96, 85, 91, 60
' 122, 94, 92, 91, 91
' 117, 93, 92, 80, 87
' 118, 92, 90, 83, 78
' 113, 88, 94, 65, 91
' 112, 75, 84, 91, 39
' 119, 68, 79, 88, 92
' 115, 35, 72, 91, 70
```

這個範例也會示範如何從函式傳回查詢變數。

## <a name="compiling-the-code"></a>編譯程式碼

建立 VB.NET 主控台應用程式專案，其中包含 System. Linq 命名空間的 `Imports` 語句。

## <a name="see-also"></a>請參閱

- [LINQ 和字串（Visual Basic）](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)
