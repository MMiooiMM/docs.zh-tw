---
title: 內建類型資料表 - C# 參考
ms.custom: seodec18
description: 內建 C# 類型的關鍵字
ms.date: 08/17/2018
helpviewer_keywords:
- types [C#], built-in
- built-in C# types
ms.assetid: 54f901f2-bf2f-472c-ae8d-73e8ecfc57fe
ms.openlocfilehash: 22bdfa197e3ce9c119203c74eeb0eb8217022a68
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/01/2019
ms.locfileid: "73422912"
---
# <a name="built-in-types-table-c-reference"></a>內建類型資料表 (C# 參考)

下表顯示內C#建類型的關鍵字，這些是 <xref:System> 命名空間中預先定義類型的別名：

|C# 類型|.NET 型別|  
|--------------|-------------------------|  
|[bool](bool.md)|<xref:System.Boolean?displayProperty=nameWithType>|  
|[byte](../builtin-types/integral-numeric-types.md)|<xref:System.Byte?displayProperty=nameWithType>|  
|[sbyte](../builtin-types/integral-numeric-types.md)|<xref:System.SByte?displayProperty=nameWithType>|  
|[char](char.md)|<xref:System.Char?displayProperty=nameWithType>|  
|[decimal](../builtin-types/floating-point-numeric-types.md)|<xref:System.Decimal?displayProperty=nameWithType>|  
|[double](../builtin-types/floating-point-numeric-types.md)|<xref:System.Double?displayProperty=nameWithType>|  
|[float](../builtin-types/floating-point-numeric-types.md)|<xref:System.Single?displayProperty=nameWithType>|  
|[int](../builtin-types/integral-numeric-types.md)|<xref:System.Int32?displayProperty=nameWithType>|  
|[uint](../builtin-types/integral-numeric-types.md)|<xref:System.UInt32?displayProperty=nameWithType>|  
|[long](../builtin-types/integral-numeric-types.md)|<xref:System.Int64?displayProperty=nameWithType>|  
|[ulong](../builtin-types/integral-numeric-types.md)|<xref:System.UInt64?displayProperty=nameWithType>|  
|[object](../builtin-types/reference-types.md)|<xref:System.Object?displayProperty=nameWithType>|  
|[short](../builtin-types/integral-numeric-types.md)|<xref:System.Int16?displayProperty=nameWithType>|  
|[ushort](../builtin-types/integral-numeric-types.md)|<xref:System.UInt16?displayProperty=nameWithType>|  
|[string](../builtin-types/reference-types.md)|<xref:System.String?displayProperty=nameWithType>|  
  
## <a name="remarks"></a>備註

表中除了 `object` 和 `string` 以外的所有型別，都視為簡單型別。

.NET 型別與其 C# 型別關鍵字別名是可互換的。 例如，您可以使用下列任一個宣告來宣告整數變數：

```csharp
int x = 123;
System.Int32 y = 123;
```

使用 [typeof](../operators/type-testing-and-cast.md#typeof-operator) 運算子，取得表示指定類型的 <xref:System.Type?displayProperty=nameWithType> 執行個體：

```csharp
Type stringType = typeof(string);
Console.WriteLine(stringType.FullName);

Type doubleType = typeof(System.Double);
Console.WriteLine(doubleType.FullName);

// Output:
// System.String
// System.Double
```

## <a name="see-also"></a>請參閱

- [C# 參考](../index.md)
- [C# 程式設計指南](../../programming-guide/index.md)
- [C# 關鍵字](index.md)
- [實值型別](value-types.md)
- [參考型別](reference-types.md)
- [預設值表](default-values-table.md)
- [dynamic](../builtin-types/reference-types.md)
