---
title: 等號比較運算子 - C# 參考
description: 深入了解 C# 等號比較運算子與 C# 型別等號。
ms.date: 06/26/2019
author: pkulikov
f1_keywords:
- ==_CSharpKeyword
- '!=_CSharpKeyword'
helpviewer_keywords:
- comparison operators [C#]
- relational operators [C#]
- equality operator [C#]
- equals operator [C#]
- == operator [C#]
- inequality operator [C#]
- not equals operator [C#]
- '!= operator [C#]'
ms.openlocfilehash: 11d2161004af5199d9e501f8ab1e3c0382e6bfe7
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039028"
---
# <a name="equality-operators-c-reference"></a>等號比較運算子 (C# 參考)

[`==` (相等)](#equality-operator-) 和 [`!=` (不等)](#inequality-operator-) 運算子可檢查其運算元是否相等。

## <a name="equality-operator-"></a>等號比較運算子 ==

等號比較運算子 `==` 會在其運算元相等時傳回 `true`，否則傳回 `false`。

### <a name="value-types-equality"></a>實值型別相等

若他們的值相等時，[內建實值型別](../keywords/value-types-table.md)的運算元就會相等：

[!code-csharp-interactive[value types equality](~/samples/csharp/language-reference/operators/EqualityOperators.cs#ValueTypesEquality)]

> [!NOTE]
> 針對 `==`、[`<`、`>`、`<=` 和 `>=`](comparison-operators.md) 運算子，如果任何運算元不是數字 (<xref:System.Double.NaN?displayProperty=nameWithType> 或 <xref:System.Single.NaN?displayProperty=nameWithType>)，則作業的結果是 `false`。 這代表 `NaN` 的值皆不會大於、小於或等於任何其他 `double` (或 `float`) 的值，包括 `NaN`。 如需詳細資訊和範例，請參閱 <xref:System.Double.NaN?displayProperty=nameWithType> 或 <xref:System.Single.NaN?displayProperty=nameWithType> 參考文章。

若基礎整數型別的對應值相等時，相同[列舉](../keywords/enum.md)類型的兩個運算元就會相等。

使用者定義[結構](../keywords/struct.md)型別預設不支援 `==` 運算子。 若要支援 `==` 運算子，使用者定義結構必須[多載](operator-overloading.md)它。

從 C# 7.3 開始，`==` 及 `!=` 運算子是由 C# [tuples](../../tuples.md) 所支援。 如需詳細資訊，請參閱 [C# Tuple 類型](../../tuples.md)一文中的[相等與 Tuple](../../tuples.md#equality-and-tuples)一節。

### <a name="reference-types-equality"></a>參考型別相等

根據預設，當兩個參考型別的運算元參考相同物件時，兩者就相等：

[!code-csharp[reference type equality](~/samples/csharp/language-reference/operators/EqualityOperators.cs#ReferenceTypesEquality)]

如範例所示，使用者定義參考型別預設支援 `==` 運算子。 不過，參考型別可以多載 `==` 運算子。 若參考型別多載 `==` 運算子，請使用 <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> 方法檢查兩個該類型的參考是否參考相同的物件。

### <a name="string-equality"></a>字串相等

當兩個 [string](../builtin-types/reference-types.md#the-string-type) 運算元皆為 `null`，或兩個 string 執行個體的長度相同且在各字元位置擁有完全相同的字元，兩者就會相等：

[!code-csharp-interactive[string equality](~/samples/csharp/language-reference/operators/EqualityOperators.cs#StringEquality)]

這是區分大小寫的序數比較。 如需有關字串比較的詳細資訊，請參閱[如何在 C# 中比較字串](../../how-to/compare-strings.md)。

### <a name="delegate-equality"></a>委派等號

相同執行階段型別的兩個[委派](../../programming-guide/delegates/index.md)運算元都是 `null` 或其引動過程清單長度相同且每個位置都有相等的項目時，那兩個運算元相等：

[!code-csharp-interactive[delegate equality](~/samples/csharp/language-reference/operators/EqualityOperators.cs#DelegateEquality)]

如需詳細資訊，請參閱 [C# 語言規格](~/_csharplang/spec/introduction.md)的[委派相等運算子](~/_csharplang/spec/expressions.md#delegate-equality-operators)一節。

從語意相同之 [lambda 運算式](../../programming-guide/statements-expressions-operators/lambda-expressions.md)之評估產生的委派不相等，如下列範例所示：

[!code-csharp-interactive[from identical lambdas](~/samples/csharp/language-reference/operators/EqualityOperators.cs#IdenticalLambdas)]

## <a name="inequality-operator-"></a>不等比較運算子 !=

不等比較運算子 `!=` 會在其運算元不相等時傳回 `true`，否則傳回 `false`。 對於[內建類型](../keywords/built-in-types-table.md)的運算元，運算式 `x != y` 會產生與運算式 `!(x == y)` 相同的結果。 如需有關型別等號的詳細資訊，請參閱[等號比較運算子](#equality-operator-)一節。

下列範例示範 `!=` 運算子的用法：

[!code-csharp-interactive[non-equality examples](~/samples/csharp/language-reference/operators/EqualityOperators.cs#NonEquality)]

## <a name="operator-overloadability"></a>運算子是否可多載

使用者定義類型可以[多載](operator-overloading.md) `==` 和 `!=` 運算子。 如果某個型別多載這兩個運算子之一，它也必須多載另一個運算子。

## <a name="c-language-specification"></a>C# 語言規格

如需詳細資訊，請參閱 [C# 語言規格](~/_csharplang/spec/introduction.md)的[關係及類型測試運算子](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators)一節。

## <a name="see-also"></a>請參閱

- [C# 參考](../index.md)
- [C# 運算子](index.md)
- <xref:System.IEquatable%601?displayProperty=nameWithType>
- <xref:System.Object.Equals%2A?displayProperty=nameWithType>
- <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType>
- [相等比較](../../programming-guide/statements-expressions-operators/equality-comparisons.md)
- [比較運算子](comparison-operators.md)
