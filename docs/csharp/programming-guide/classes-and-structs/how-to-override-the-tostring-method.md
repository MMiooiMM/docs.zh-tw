---
title: 如何：覆寫 ToString 方法-程式C#設計指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- ToString method, overriding in C#
- inheritance [C#], overriding OnPaint and ToString
ms.assetid: 8016db69-1f19-420c-8e17-98e8bebb7749
ms.openlocfilehash: 9dd567e537768ceb8b9f61ce58dccd443db38ec7
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/01/2019
ms.locfileid: "73419346"
---
# <a name="how-to-override-the-tostring-method-c-programming-guide"></a>如何：覆寫 ToString 方法 (C# 程式設計手冊)

C# 中的每個類別或結構都會隱含地繼承 <xref:System.Object> 類別。 因此，C# 中的每個物件都會取得 <xref:System.Object.ToString%2A> 方法，以傳回該物件的字串表示。 例如，所有 `int` 類型的變數都有 `ToString` 方法，並讓它們以字串傳回其內容︰  
  
 [!code-csharp[csProgGuideInheritance#37](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#37)]  
  
 當您建立自訂類別或結構時，應該覆寫 <xref:System.Object.ToString%2A> 方法，以將您的類型資訊提供給用戶端程式碼。  
  
 如需如何使用 `ToString` 方法以使用格式字串和其他類型之自訂格式的資訊，請參閱[格式化類型](../../../standard/base-types/formatting-types.md)。  
  
> [!IMPORTANT]
> 當您決定要透過這種方法提供的資訊時，請考慮不受信任的程式碼是否要使用類別或結構。 請務必確定您未提供任何可能會遭惡意程式碼利用的資訊。  
  
在類別或結構中覆寫 `ToString` 方法：
  
1. 宣告具有下列修飾詞和傳回型別的 `ToString` 方法︰  
  
    ```csharp  
    public override string ToString(){}  
    ```  
  
2. 實作方法，讓它傳回字串。  
  
     下列範例除了會傳回類別的名稱，也會傳回此類別之特定執行個體 (Instance) 所特有的資料。  
  
     [!code-csharp[csProgGuideInheritance#36](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#36)]  
  
     您可以測試 `ToString` 方法，如下列程式碼範例所示：  
  
     [!code-csharp[csProgGuideInheritance#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#38)]  
  
## <a name="see-also"></a>請參閱

- <xref:System.IFormattable>
- [C# 程式設計指南](../index.md)
- [類別和結構](./index.md)
- [字串](../strings/index.md)
- [string](../../language-reference/builtin-types/reference-types.md)
- [override](../../language-reference/keywords/override.md)
- [virtual](../../language-reference/keywords/virtual.md)
- [格式化類型](../../../standard/base-types/formatting-types.md)
