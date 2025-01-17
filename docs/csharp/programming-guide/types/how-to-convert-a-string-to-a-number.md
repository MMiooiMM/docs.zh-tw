---
title: 如何：將字串轉換為數字程式C#設計指南
ms.custom: seodec18
ms.date: 02/11/2019
helpviewer_keywords:
- conversions [C#]
- conversions [C#], string to int
- converting strings to int [C#]
- strings [C#], converting to int
ms.assetid: 467b9979-86ee-4afd-b734-30299cda91e3
ms.openlocfilehash: c39602afbece4faaf6599a5c76f5746defffe03a
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/01/2019
ms.locfileid: "73417638"
---
# <a name="how-to-convert-a-string-to-a-number-c-programming-guide"></a>如何：將字串轉換為數值 (C# 程式設計手冊)

您可以透過呼叫可在數個數值型別 (`int`、`long`、`double` 等) 上找到的 `Parse` 或 `TryParse` 方法，或透過使用 <xref:System.Convert?displayProperty=nameWithType> 類別中的方法，將 [string](../../language-reference/builtin-types/reference-types.md) 轉換為數字。  
  
 如果您有一個字串，呼叫 `TryParse` 方法 (例如，[`int.TryParse("11", out number)`](xref:System.Int32.TryParse%2A)) 或 `Parse` 方法 (例如，[`var number = int.Parse("11")`](xref:System.Int32.Parse%2A)) 相較之下將更有效率且直接。  使用 <xref:System.Convert> 方法比實作 <xref:System.IConvertible> 的一般物件更有用。  
  
 您可以在預期字串包含的數值類型上使用 `Parse` 或 `TryParse` 方法，例如 <xref:System.Int32?displayProperty=nameWithType> 類型。  <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType> 方法會在內部使用 <xref:System.Int32.Parse%2A>。  `Parse` 方法會傳回轉換的數字；`TryParse` 方法會傳回 <xref:System.Boolean> 值，此值指出轉換是否成功，而且會在 [`out` 參數](../../language-reference/keywords/out.md)中傳回轉換的數字。 如果字串的格式無效，`Parse` 會擲回例外狀況，而 `TryParse` 會傳回 [false](../../language-reference/keywords/false-literal.md)。 呼叫 `Parse` 方法時，您必須一律使用例外狀況處理在剖析作業失敗時捕捉 <xref:System.FormatException>。  
  
## <a name="calling-the-parse-and-tryparse-methods"></a>呼叫 Parse 與 TryParse 方法

`Parse` 與 `TryParse` 方法會忽略字串開頭和結尾的空格，但所有其他字元必須是來自適當數值型別 (`int`、`long`、`ulong`、`float`、`decimal` 等) 的字元。  若構成數字的字串內有任何空格，則會造成錯誤。  例如，您可以使用 `decimal.TryParse` 來剖析 "10"、"10.3" 或 "  10  "，但您無法使用此方法來從 "10X"、"1 0" (注意內嵌的空格)、"10 .3" (注意內嵌的空格)、"10e1" (`float.TryParse` 在這裡可以運作) 剖析 10 等。 此外，無法成功剖析值為 `null` 或 <xref:System.String.Empty?displayProperty=nameWithType> 的字串。 您可以透過呼叫 <xref:System.String.IsNullOrEmpty%2A?displayProperty=nameWithType> 方法，在嘗試剖析 Null 或空字串之前先進行檢查。 

下列範例示範對 `Parse` 與 `TryParse` 的成功呼叫與不成功的呼叫。  
  
[!code-csharp[Parse and TryParse](~/samples/snippets/csharp/programming-guide/string-to-number/parse-tryparse/program.cs)]  

下列範例示範的方法可剖析預期應該包含前置數字字元 (包括十六進位字元) 與結尾非數字字元的字串。 在呼叫 <xref:System.Int32.TryParse%2A> 方法之前，它會將字串開頭的有效字元指派到新字串。 因為要剖析的字串包含一些字元，範例會呼叫 <xref:System.String.Concat%2A?displayProperty=nameWithType> 方法以將有效字元指派到新字串。 針對較大的字串，可以改為使用 <xref:System.Text.StringBuilder> 類別。 
  
[!code-csharp[Removing invalid characters](~/samples/snippets/csharp/programming-guide/string-to-number/parse-tryparse2/program.cs)]  

## <a name="calling-the-convert-methods"></a>呼叫轉換方法

下表列出您可以用來將字串轉換為數字的一些方法 (來自 <xref:System.Convert> 類別)。  
  
|數字類型|方法|  
|------------------|------------|  
|`decimal`|<xref:System.Convert.ToDecimal%28System.String%29>|  
|`float`|<xref:System.Convert.ToSingle%28System.String%29>|  
|`double`|<xref:System.Convert.ToDouble%28System.String%29>|  
|`short`|<xref:System.Convert.ToInt16%28System.String%29>|  
|`int`|<xref:System.Convert.ToInt32%28System.String%29>|  
|`long`|<xref:System.Convert.ToInt64%28System.String%29>|  
|`ushort`|<xref:System.Convert.ToUInt16%28System.String%29>|  
|`uint`|<xref:System.Convert.ToUInt32%28System.String%29>|  
|`ulong`|<xref:System.Convert.ToUInt64%28System.String%29>|  
  
 下列範例會呼叫 <xref:System.Convert.ToInt32%28System.String%29?displayProperty=nameWithType> 方法，將輸入字串轉換為[int](../../language-reference/builtin-types/integral-numeric-types.md)。此範例會攔截可由這個方法擲回的兩個最常見的例外狀況，<xref:System.FormatException> 和 <xref:System.OverflowException>。 若產生的數字可在不超過 <xref:System.Int32.MaxValue?displayProperty=nameWithType> 的情況下遞增，範例會增加 1 到結果並顯示輸出。  
  
[!code-csharp[Parsing with Convert methods](~/samples/snippets/csharp/programming-guide/string-to-number/convert/program.cs)]  
  
## <a name="see-also"></a>請參閱

- [型別](./index.md)
- [如何：判斷字串是否表示數值](../strings/how-to-determine-whether-a-string-represents-a-numeric-value.md)
- [Sample: .NET Core WinForms Formatting Utility (C#)](https://docs.microsoft.com/samples/dotnet/samples/winforms-formatting-utility-cs) (範例：.NET Core WinForms 格式化公用程式 (C#))
