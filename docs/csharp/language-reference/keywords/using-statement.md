---
title: using 陳述式 - C# 參考
ms.custom: seodec18
ms.date: 10/15/2019
helpviewer_keywords:
- using statement [C#]
ms.assetid: afc355e6-f0b9-4240-94dd-0d93f17d9fc3
ms.openlocfilehash: f5ff78eaf9d565a9708c7a3a11754579389e79e8
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/01/2019
ms.locfileid: "73422250"
---
# <a name="using-statement-c-reference"></a>using 陳述式 (C# 參考)

提供方便的語法，以確保正確使用 <xref:System.IDisposable> 物件。

## <a name="example"></a>範例

下列範例顯示如何使用 `using` 陳述式。

[!code-csharp[csrefKeywordsNamespace#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#4)]

從C# 8.0 開始，您可以針對不需要大括弧的 `using` 語句使用下列替代語法：

[!code-csharp[csrefKeywordsNamespace#New](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#ModernUsing)]

## <a name="remarks"></a>備註

<xref:System.IO.File> 和 <xref:System.Drawing.Font> 是 Managed 類型的範例，這些類型會存取 Unmanaged 資源 (在本例中為檔案控制代碼和裝置內容)。 還有許多其他類型的 Unmanaged 資源，以及封裝這些資源的類別庫類型。 所有這些類型都會實作 <xref:System.IDisposable> 介面。

當 `IDisposable` 物件的存留期限制為單一方法時，您應該在 `using` 陳述式中宣告它並加以具現化。 `using` 陳述式會以正確的方式呼叫物件上的 <xref:System.IDisposable.Dispose%2A> 方法，而且 (當您如稍早所示使用它時) 它也會在一呼叫 <xref:System.IDisposable.Dispose%2A> 時讓物件本身超出範圍。 在 `using` 區塊內，物件是唯讀的，而且無法加以修改或重新指派。

`using` 陳述式可確保會呼叫 <xref:System.IDisposable.Dispose%2A>，即使在 `using` 區塊內發生例外狀況也一樣。 您可以將物件放在 `try` 區塊內，然後在 `finally` 區塊中呼叫 <xref:System.IDisposable.Dispose%2A>，來達到相同的結果；事實上，這就是編譯器轉譯 `using` 陳述式的方式。 稍早的程式碼範例會在編譯時期展開為下列程式碼 (注意額外的大括號是為了建立物件的有限範圍)：

[!code-csharp[csrefKeywordsNamespace#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#5)]

較新的 `using` 語句語法會轉譯成非常類似的程式碼。 `try` 區塊會在宣告變數的位置開啟。 `finally` 區塊會在封閉區塊的結尾處新增，通常是在方法的結尾處。

如需 `try`-`finally` 陳述式的詳細資訊，請參閱 [try-finally](try-finally.md) 主題。

您可以在 `using` 陳述式中宣告一種類型的多個執行個體，如下列範例所示：

[!code-csharp[csrefKeywordsNamespace#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#6)]

您也可以使用C# 8 引進的新語法，結合相同類型的多個宣告。 下列範例會顯示這一點：

[!code-csharp[csrefKeywordsNamespace#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#MultipleUsing)]

您可以具現化資源物件，然後將變數傳遞至 `using` 陳述式，但這不是最佳做法。 在此情況下，控制權離開 `using` 區塊之後，物件仍會留在範圍內，不過它可能無法再存取其非受控資源。 換句話說，它不再是完全初始化。 如果您嘗試在 `using` 區塊外部使用該物件，則會有導致擲回例外狀況的風險。 因此，通常最好在 `using` 陳述式中具現化物件，並將其範圍限制為 `using` 區塊。

[!code-csharp[csrefKeywordsNamespace#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#7)]

如需處置 `IDisposable` 物件的詳細資訊，請參閱[使用實作 IDisposable 的物件](../../../standard/garbage-collection/using-objects.md)。

## <a name="c-language-specification"></a>C# 語言規格

如需詳細資訊，請參閱 [C# 語言規格](/dotnet/csharp/language-reference/language-specification/introduction)中的 [using 陳述式](~/_csharplang/spec/statements.md#the-using-statement)。 語言規格是 C# 語法及用法的限定來源。

## <a name="see-also"></a>請參閱

- [C# 參考](../index.md)
- [C# 程式設計指南](../../programming-guide/index.md)
- [C# 關鍵字](index.md)
- [using 指示詞](using-directive.md)
- [記憶體回收](../../../standard/garbage-collection/index.md)
- [使用實作 IDisposable 的物件](../../../standard/garbage-collection/using-objects.md)
- [IDisposable 介面](xref:System.IDisposable)
- [使用8.0 中C#的語句](~/_csharplang/proposals/csharp-8.0/using.md)
