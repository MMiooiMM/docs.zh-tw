---
title: let 子句 - C# 參考
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- let_CSharpKeyword
- let
helpviewer_keywords:
- let keyword [C#]
- let clause [C#]
ms.assetid: 13c9c1a4-ce57-48ef-8e1b-4c2a59b99fb4
ms.openlocfilehash: df3df279d2dbdb59a0a94d9afad37d1a7ddf7b57
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/01/2019
ms.locfileid: "73422704"
---
# <a name="let-clause-c-reference"></a>let 子句 (C# 參考)

在查詢運算式中，有時它十分適合儲存子運算式的結果，以將它用於後續子句。 您可以使用 `let` 關鍵字執行這項作業，而此關鍵字會建立新的範圍變數，並使用您提供的運算式結果將它初始化。 使用值初始化之後，就不能使用範圍變數來儲存另一個值。 不過，如果範圍變數保留可查詢類型，則可以進行查詢。

## <a name="example"></a>範例

在下列範例中，以兩種方式使用 `let`：

1. 建立本身可進行查詢的可列舉類型。

2. 讓查詢只對範圍變數 `word` 呼叫一次 `ToLower`。 如果不使用 `let`，則您需要在 `where` 子句的每個述詞中呼叫 `ToLower`。

[!code-csharp[cscsrefQueryKeywords#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Let.cs#28)]

## <a name="see-also"></a>請參閱

- [C# 參考](../../language-reference/index.md)
- [查詢關鍵字 (LINQ)](query-keywords.md)
- [Language-Integrated Query (LINQ)](../../linq/index.md)
- [開始使用 C# 中的 LINQ](/dotnet/csharp/programming-guide/concepts/linq/)
- [處理查詢運算式中的例外狀況](../../linq/handle-exceptions-in-query-expressions.md)
