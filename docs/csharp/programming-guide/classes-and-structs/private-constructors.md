---
title: 私用建構函式 - C# 程式設計手冊
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, private constructors
- private constructors [C#]
ms.assetid: 29eeaa7d-8d81-453c-94b9-0e2800172621
ms.openlocfilehash: 918d39b8aed25395106942524baa3b51221933dc
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/01/2019
ms.locfileid: "73418879"
---
# <a name="private-constructors-c-programming-guide"></a>私用建構函式 (C# 程式設計手冊)
私用建構函式是一種特殊的執行個體建構函式。 它通常會用於只包含靜態成員的類別。 如果類別具有一或多個私用建構函式，而且沒有任何公用建構函式，則其他類別 (巢狀類別除外) 無法建立此類別的執行個體。 例如:  
  
 [!code-csharp[csProgGuideObjects#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#11)]  
  
 宣告空的建構函式可防止自動產生無參數建構函式。 請注意，如果您未搭配建構函式使用存取修飾詞，預設仍會是私用的。 不過，通常會明確使用 [private](../../language-reference/keywords/private.md) 修飾詞來指出無法具現化類別。  
  
 當類別沒有執行個體欄位或方法 (例如 <xref:System.Math> 類別)，或是您要呼叫方法以取得類別的執行個體時，可以使用私用建構函式來防止建立類別的執行個體。 如果類別中的所有方法都是靜態的，請考慮將整個類別變為靜態。 如需詳細資訊，請參閱[靜態類別和靜態類別成員](./static-classes-and-static-class-members.md)。  
  
## <a name="example"></a>範例  
 以下是使用私用建構函式的類別範例。  
  
 [!code-csharp[csProgGuideObjects#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#12)]  
  
 請注意，如果您將範例中的下列陳述式取消註解，這時將會產生錯誤，因為建構函式會因其保護層級而無法存取：  
  
 [!code-csharp[csProgGuideObjects#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#13)]  
  
## <a name="c-language-specification"></a>C# 語言規格  

如需詳細資訊，請參閱 [C# 語言規格](/dotnet/csharp/language-reference/language-specification/introduction)的[私用建構式](~/_csharplang/spec/classes.md#private-constructors)。 語言規格是 C# 語法及用法的限定來源。
  
## <a name="see-also"></a>請參閱

- [C# 程式設計指南](../index.md)
- [類別和結構](./index.md)
- [建構函式](./constructors.md)
- [完成項](./destructors.md)
- [private](../../language-reference/keywords/private.md)
- [public](../../language-reference/keywords/public.md)
