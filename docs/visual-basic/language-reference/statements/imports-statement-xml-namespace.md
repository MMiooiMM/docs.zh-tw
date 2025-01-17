---
title: Imports 語句-XML 命名空間（Visual Basic）
ms.date: 07/20/2015
f1_keywords:
- vb.ImportsXmlns
helpviewer_keywords:
- XML namespace [Visual Basic], importing
- imports [Visual Basic]
- Imports statement [Visual Basic]
- namespaces [Visual Basic], importing
ms.assetid: 1f4d50a6-08c7-4c2e-8206-ccae35fcd1b4
ms.openlocfilehash: 0fca0caecfd69580510a539317856209108e5a32
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581760"
---
# <a name="imports-statement-xml-namespace"></a>Imports 陳述式 (XML 命名空間)

匯入 XML 常值和 XML 軸屬性中所使用的 XML 命名空間前置詞。

## <a name="syntax"></a>語法

```vb
Imports <xmlns:xmlNamespacePrefix = "xmlNamespaceName">
```

## <a name="parts"></a>組件

`xmlNamespacePrefix`  
選擇項。 XML 元素和屬性可以參考 `xmlNamespaceName` 的字串。 如果未提供任何 `xmlNamespacePrefix`，則匯入的 XML 命名空間是預設的 XML 命名空間。 必須是有效的 XML 識別碼。 如需詳細資訊，請參閱宣告[的 XML 元素和屬性的名稱](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)。

`xmlNamespaceName`  
必要項。 識別正在匯入之 XML 命名空間的字串。

## <a name="remarks"></a>備註

您可以使用 `Imports` 語句來定義可用於 XML 常值和 XML 軸屬性的全域 XML 命名空間，或做為傳遞給 `GetXmlNamespace` 運算子的參數。 （如需有關使用 `Imports` 語句匯入可在程式碼中使用類型名稱之別名的詳細資訊，請參閱[Imports 語句（.Net 命名空間和類型）](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)。使用 `Imports` 語句來宣告 XML 命名空間的語法，與 XML 中使用的語法相同。 因此，您可以從 XML 檔案複製命名空間宣告，並在 `Imports` 語句中使用它。

當您想要重複建立來自相同命名空間的 XML 元素時，XML 命名空間前置詞非常有用。 以 `Imports` 語句宣告的 XML 命名空間前置詞，在檔案中的所有程式碼都可供使用時，是全域的。 當您建立 XML 專案常值時，以及當您存取 XML 軸屬性時，可以使用它。 如需詳細資訊，請參閱[Xml 元素常](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)值和[xml 軸屬性](../../../visual-basic/language-reference/xml-axis/index.md)。

如果您定義不含命名空間前置詞的全域 XML 命名空間（例如 `Imports <xmlns="http://SomeNameSpace>"`），該命名空間會被視為預設的 XML 命名空間。 預設的 XML 命名空間會用於未明確指定命名空間的任何 XML 專案常值或 XML 屬性軸屬性。 如果指定的命名空間是空的命名空間（也就是 `xmlns=""`），也會使用預設的命名空間。 預設的 XML 命名空間不適用於 XML 常值中的 XML 屬性，或是沒有命名空間的 XML 屬性軸屬性。

Xml 常值中定義的 XML 命名空間（稱為*本機 XML 命名空間*）優先于 `Imports` 語句定義為全域的 xml 命名空間。 @No__t_0 語句所定義的 XML 命名空間會優先于針對 Visual Basic 專案匯入的 XML 命名空間。 如果 XML 常值定義 XML 命名空間，該本機命名空間就不會套用至內嵌運算式。

全域 XML 命名空間會遵循與 .NET Framework 命名空間相同的範圍和定義規則。 因此，您可以在任何可匯入 .NET Framework 命名空間的位置加入 `Imports` 語句，以定義全域 XML 命名空間。 這包括程式碼檔案和專案層級的匯入命名空間。 如需專案層級匯入之命名空間的詳細資訊，請參閱[專案設計工具、參考頁（Visual Basic）](/visualstudio/ide/reference/references-page-project-designer-visual-basic)。

每個來源檔案都可以包含任意數目的 `Imports` 語句。 這些必須遵循 option 宣告（例如 `Option Strict` 語句），而且必須在程式設計專案宣告之前，例如 `Module` 或 `Class` 語句。

## <a name="example"></a>範例

下列範例會匯入預設的 XML 命名空間和以前置詞 `ns` 識別的 XML 命名空間。 然後，它會建立同時使用這兩個命名空間的 XML 常值。

[!code-vb[VbXMLSamples#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/Module1.vb#45)]

此程式碼顯示下列文字：

```xml
<ns:outer xmlns="http://DefaultNamespace"
          xmlns:ns="http://NewNamespace">
  <ns:innerElement></ns:innerElement>
  <siblingElement></siblingElement>
  <innerElement />
</ns:outer>
```

## <a name="example"></a>範例

下列範例會將 XML 命名空間前置詞彙入 `ns`。 然後，它會建立使用命名空間前置詞的 XML 常值，並顯示專案的最終格式。

[!code-vb[VbXMLSamples#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples10.vb#22)]

此程式碼顯示下列文字：

```xml
<ns:outer xmlns:ns="http://SomeNamespace">
  <ns:middle xmlns:ns="http://NewNamespace">
    <ns:inner1 />
    <inner2 xmlns="http://SomeNamespace" />
  </ns:middle>
</ns:outer>
```

請注意，編譯器會將 XML 命名空間前置詞從全域前置詞轉換成本機前置詞定義。

## <a name="example"></a>範例

下列範例會將 XML 命名空間前置詞彙入 `ns`。 然後它會使用命名空間的前置詞來建立 XML 常值，以及存取完整名稱為 `ns:name` 的第一個子節點。

[!code-vb[VbXMLSamples#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples8.vb#19)]

此程式碼顯示下列文字：

`Patrick Hines`

## <a name="see-also"></a>請參閱

- [XML 項目常值](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [XML 軸屬性](../../../visual-basic/language-reference/xml-axis/index.md)
- [宣告的 XML 項目和屬性的名稱](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
- [GetXmlNamespace 運算子](../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md)
