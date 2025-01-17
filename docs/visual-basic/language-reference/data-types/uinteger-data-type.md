---
title: UInteger 資料類型（Visual Basic）
ms.date: 01/31/2018
f1_keywords:
- vb.uinteger
helpviewer_keywords:
- numbers [Visual Basic], whole
- UInteger data type
- literal type characters [Visual Basic], UI
- whole numbers
- integral data types [Visual Basic]
- integer numbers
- numbers [Visual Basic], integer
- integers [Visual Basic], data types
- integers [Visual Basic], types
- UI literal type characters [Visual Basic]
- data types [Visual Basic], integral
ms.assetid: db7ddd34-4f23-46f5-84dd-8b0f83bb8729
ms.openlocfilehash: 1ae0cbd3a518bf863a3c57f50934837a486d2901
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583127"
---
# <a name="uinteger-data-type"></a>UInteger 資料類型

保留不帶正負號的32位（4位元組）整數，範圍是從0到4294967295的值。

## <a name="remarks"></a>備註

@No__t_0 資料類型會以最有效率的資料寬度提供最大不帶正負號的值。

`UInteger` 的預設值為 0。

## <a name="literal-assignments"></a>常值指派

您可以藉由指派十進位常值、十六進位常值、八進位常值，或二進位常值（從 Visual Basic 2017）來宣告和初始化 `UInteger` 變數。 如果整數常值超出 `UInteger` 的範圍 (亦即，如果小於 <xref:System.UInt32.MinValue?displayProperty=nameWithType> 或大於 <xref:System.UInt32.MaxValue?displayProperty=nameWithType>)，就會發生編譯錯誤。

在下列範例中，以十進位、十六進位和二進位常值表示的 3,000,000,000 整數，會指派給 `UInteger` 值。

[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UInt)]

> [!NOTE]
> 您可以使用前置詞 `&h` 或 `&H` 來表示十六進位常值、前置詞 `&b` 或 `&B` 來表示二進位常值，而前置詞 `&o` 或 `&O` 表示八進位常值。 十進位常值沒有前置詞。

從 Visual Basic 2017 開始，您也可以使用底線字元（`_`）做為數位分隔符號，以增強可讀性，如下列範例所示。

[!code-vb[UInteger](../../../../samples/snippets/visualbasic/language-reference/data-types/numeric-literals.vb#UIntS)]

從 Visual Basic 15.5 開始，您也可以使用底線字元（`_`）做為前置詞和十六進位、二進位或八進位數位之間的前置分隔符號。 例如:

```vb
Dim number As UInteger = &H_0F8C_0326
```

[!INCLUDE [supporting-underscores](../../../../includes/vb-separator-langversion.md)]

數值常值也可以包含 `UI` 或 `ui`[類型字元](../../programming-guide/language-features/data-types/type-characters.md)來表示 `UInteger` 資料類型，如下列範例所示。

```vb
Dim number = &H_0FAC_14D7ui
```

## <a name="programming-tips"></a>程式設計提示

@No__t_0 和 `Integer` 資料類型在32位處理器上提供最佳效能，因為較小的整數類型（`UShort`、`Short`、`Byte` 和 `SByte`），即使使用較少的位，也需要更多時間來載入、儲存和提取。

- **負數。** 因為 `UInteger` 是不帶正負號的類型，所以不能代表負數。 如果您在評估為類型 `UInteger` 的運算式上使用一元減號（`-`）運算子，Visual Basic 會先將運算式轉換成 `Long`。

- **CLS 合規性。** @No__t_0 資料類型不是[Common Language Specification](https://www.ecma-international.org/publications/standards/Ecma-335.htm) （CLS）的一部分，因此符合 cls 標準的程式碼無法使用它所使用的元件。

- **Interop 考慮。** 如果您要使用的元件不是針對 .NET Framework 所撰寫（例如 Automation 或 COM 物件），請記住，`uint` 之類的類型在其他環境中可能會有不同的資料寬度（16位）。 如果您要將16位引數傳遞至這類元件，請將它宣告為 `UShort`，而不是在您的 managed Visual Basic 程式碼中 `UInteger`。

- **加寬.** @No__t_0 資料類型會擴展到 `Long`、`ULong`、`Decimal`、`Single` 和 `Double`。 這表示您可以將 `UInteger` 轉換成這些類型的任何一種，而不會遇到 <xref:System.OverflowException?displayProperty=nameWithType> 錯誤。

- **輸入字元。** 將常數值型別字元附加到常值 `UI` 會強制其成為 `UInteger` 的資料類型。 `UInteger` 沒有識別項型別字元。

- **架構類型。** 在 .NET Framework 中對應的類型為 <xref:System.UInt32?displayProperty=nameWithType> 結構。

## <a name="see-also"></a>請參閱

- <xref:System.UInt32>
- [資料類型](../../../visual-basic/language-reference/data-types/index.md)
- [類型轉換函式](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [轉換摘要](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [操作說明：呼叫使用不帶正負號類型的 Windows 函式](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [有效率地使用資料類型](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
