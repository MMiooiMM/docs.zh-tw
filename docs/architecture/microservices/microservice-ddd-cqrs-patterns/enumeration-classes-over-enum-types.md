---
title: 使用列舉類別，而非列舉類型
description: 容器化 .NET 應用程式的 .NET 微服務架構 | 了解如何使用列舉類別 (而非列舉) 來解決後者的一些限制。
ms.date: 10/08/2018
ms.openlocfilehash: 255bccab0e1fe71e00c0d0b47c8af05f80cb760b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/30/2019
ms.locfileid: "73093870"
---
# <a name="use-enumeration-classes-instead-of-enum-types"></a>使用列舉類別，而非列舉類型

[列舉](../../../csharp/language-reference/keywords/enum.md) (簡稱「列舉類型」) 是整數型別的精簡語言包裝函式。 您可能會想要將其用途限制在儲存一組封閉值中的一個值時。 依大小 (小、中、大) 分類是不錯的範例。 使用列舉來控制流程或更強固的抽象概念可能會導致[程式碼異味](https://deviq.com/code-smells/) (Code Smell)。 這種使用方式會導致程式碼因為有許多查看列舉值的控制流程陳述式而變得很脆弱。

相反地，您可以建立列舉類別，以便利用物件導向語言的所有豐富功能。

不過，這個主題並不重要，而且在許多情況下，為了方便作業，您仍然可以使用標準[列舉類型](../../../csharp/language-reference/keywords/enum.md) (如果偏好這樣做)。 無論如何，使用列舉類別與商務相關概念比較有關。

## <a name="implement-an-enumeration-base-class"></a>實作列舉基底類別

eShopOnContainers 中的訂購微服務提供範例列舉基底類別實作，如下列範例所示：

```csharp
public abstract class Enumeration : IComparable
{
    public string Name { get; private set; }

    public int Id { get; private set; }

    protected Enumeration(int id, string name)
    {
        Id = id;
        Name = name;
    }

    public override string ToString() => Name;

    public static IEnumerable<T> GetAll<T>() where T : Enumeration
    {
        var fields = typeof(T).GetFields(BindingFlags.Public |
                                         BindingFlags.Static |
                                         BindingFlags.DeclaredOnly);

        return fields.Select(f => f.GetValue(null)).Cast<T>();
    }

    public override bool Equals(object obj)
    {
        var otherValue = obj as Enumeration;

        if (otherValue == null)
            return false;

        var typeMatches = GetType().Equals(obj.GetType());
        var valueMatches = Id.Equals(otherValue.Id);

        return typeMatches && valueMatches;
    }

    public int CompareTo(object other) => Id.CompareTo(((Enumeration)other).Id);

    // Other utility methods ...
}
```

您可以使用此類別作為任何實體或值物件中的類型，如下列 `CardType` : `Enumeration` 類別所示：

```csharp
public class CardType : Enumeration
{
    public static CardType Amex = new CardType(1, "Amex");
    public static CardType Visa = new CardType(2, "Visa");
    public static CardType MasterCard = new CardType(3, "MasterCard");

    public CardType(int id, string name)
        : base(id, name)
    {
    }
}
```

## <a name="additional-resources"></a>其他資源

- **Enum’s are evil—update (列舉很邪惡—更新)**  \
  <https://www.planetgeek.ch/2009/07/01/enums-are-evil/>

- **Daniel hardman:。列舉如何散佈疾病，以及如何解決此**情況 \
  <https://codecraft.co/2012/10/29/how-enums-spread-disease-and-how-to-cure-it/>

- **Jimmy Bogard。列舉類別** \
  <https://lostechies.com/jimmybogard/2008/08/12/enumeration-classes/>

- **Steve Smith。 \ 中的C#列舉替代**專案
  <https://ardalis.com/enum-alternatives-in-c>

- **Enumeration.cs：** eShopOnContainers 中的基底列舉類別 \
  <https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.Domain/SeedWork/Enumeration.cs>

- **CardType.cs**： eShopOnContainers 中的範例列舉類別 \
  <https://github.com/dotnet-architecture/eShopOnContainers/blob/dev/src/Services/Ordering/Ordering.Domain/AggregatesModel/BuyerAggregate/CardType.cs>

- **SmartEnum**： Ardalis - 可協助在 .NET 中產生強型別且更聰明的列舉。 \
  <https://www.nuget.org/packages/Ardalis.SmartEnum/>

>[!div class="step-by-step"]
>[上一頁](implement-value-objects.md)
>[下一頁](domain-model-layer-validations.md)
