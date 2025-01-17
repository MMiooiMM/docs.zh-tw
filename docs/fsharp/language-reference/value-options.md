---
title: 值的選項
description: 瞭解F#值選項類型，這是選項類型的結構版本。
ms.date: 02/06/2019
ms.openlocfilehash: 4dc3f7217943345b7aaf1165fd648ab2e01bd727
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424011"
---
# <a name="value-options"></a>值的選項

當下列兩種情況F#成立時，會使用值選項輸入：

1. 案例適用于[ F#選項](options.md)。
2. 使用結構可在您的案例中提供效能優勢。

並非所有的效能相關案例都是使用結構來「解決」。 使用時，您必須考慮複製的額外成本，而不是參考型別。 不過，大型F#程式通常會具現化許多可流經最忙碌路徑的選擇性類型，在這種情況下，結構通常可以在程式的存留期內產生較佳的整體效能。

## <a name="definition"></a>定義

Value 選項會定義為[結構的區分](discriminated-unions.md#struct-discriminated-unions)等位，與參考選項類型類似。 其定義可以透過這種方式來考慮：

```fsharp
[<StructuralEquality; StructuralComparison>]
[<Struct>]
type ValueOption<'T> =
    | ValueNone
    | ValueSome of 'T
```

Value 選項符合結構相等和比較。 主要差異在於編譯的名稱、型別名稱和大小寫名稱全都表示它是實值型別。

## <a name="using-value-options"></a>使用值選項

值選項的使用方式就像[選項](options.md)一樣。 `ValueSome` 可用來表示值存在，而且當值不存在時，會使用 `ValueNone`：

```fsharp
let tryParseDateTime (s: string) =
    match System.DateTime.TryParse(s) with
    | (true, dt) -> ValueSome dt
    | (false, _) -> ValueNone

let possibleDateString1 = "1990-12-25"
let possibleDateString2 = "This is not a date"

let result1 = tryParseDateTime possibleDateString1
let result2 = tryParseDateTime possibleDateString2

match (result1, result2) with
| ValueSome d1, ValueSome d2 -> printfn "Both are dates!"
| ValueSome d1, ValueNone -> printfn "Only the first is a date!"
| ValueNone, ValueSome d2 -> printfn "Only the second is a date!"
| ValueNone, ValueNone -> printfn "None of them are dates!"
```

如同[選項](options.md)，傳回 `ValueOption` 之函式的命名慣例是在其前面加上 `try`。

## <a name="value-option-properties-and-methods"></a>值選項屬性和方法

目前有一個屬性用於值選項： `Value`。 叫用此屬性時，如果沒有任何值存在，就會引發 <xref:System.InvalidOperationException>。

## <a name="value-option-functions"></a>值選項函數

目前有一個模組系結函數適用于值選項，`defaultValueArg`：

```fsharp
val defaultValueArg : arg:'T voption -> defaultValue:'T -> 'T
```

如同 `defaultArg` 函式，`defaultValueArg` 會傳回指定值選項的基礎值（如果有的話）。否則，它會傳回指定的預設值。

目前沒有適用于值選項的其他模組系結函數。

## <a name="see-also"></a>請參閱

- [選項](options.md)
