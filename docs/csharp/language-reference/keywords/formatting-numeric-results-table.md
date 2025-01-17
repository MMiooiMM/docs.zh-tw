---
title: 格式化數值結果表 - C# 參考
ms.custom: seodec18
description: 深入了解 C# 標準數值格式字串
ms.date: 09/20/2018
helpviewer_keywords:
- formatting [C#]
- numeric formatting [C#]
- String.Format method
ms.assetid: 120ba537-4448-4c62-8676-7a8fdd98f496
ms.openlocfilehash: 2cba5e704787ae6368b2543c985babf2fde3b4dd
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/01/2019
ms.locfileid: "73422747"
---
# <a name="formatting-numeric-results-table-c-reference"></a>格式化數值結果表 (C# 參考)

下表顯示用來格式化數值結果的支援格式規範。 最後一個資料行中的格式化結果會對應至 "en-US" <xref:System.Globalization.CultureInfo>。

|格式規範|描述|範例|結果|  
|----------------------|-----------------|--------------|------------|  
|C 或 c|貨幣|`string s = $"{2.5:C}";`<br /><br /> `string s = $"{-2.5:C}";`|$2.50<br /><br /> ($2.50)|  
|D 或 d|Decimal|`string s = $"{25:D5}";`|00025|  
|E 或 e|指數|`string s = $"{250000:E2}";`|2.50E+005|  
|F 或 f|固定點|`string s = $"{2.5:F2}";`<br /><br /> `string s = $"{2.5:F0}";`|2.50<br /><br /> 3|  
|G 或 g|一般|`string s = $"{2.5:G}";`|2.5|  
|N 或 n|數值|`string s = $"{2500000:N}";`|2,500,000.00|  
|P 或 p|百分比|`string s = $"{0.25:P}";`|25.00%|  
|R 或 r|來回|`string s = $"{2.5:R}";`|2.5|  
|X 或 x|十六進位|`string s = $"{250:X}";`<br /><br /> `string s = $"{0xffff:X}";`|FA<br /><br /> FFFF|  

## <a name="remarks"></a>備註

您可以使用格式規範來建立格式字串。 格式字串的格式如下：`Axx`，其中

- `A` 是格式規範，可控制套用到數值的格式化類型。
- `xx` 是有效位數規範，會影響格式化輸出中的位數。 有效位數規範的值範圍是從 0 到 99。

僅整數類型可支援十進位 ("D" 或 "d") 和十六進位 ("X" 或 "x") 格式規範。 僅 <xref:System.Single>、<xref:System.Double> 和 <xref:System.Numerics.BigInteger> 類型支援來回行程 ("R" 或 "r") 格式規範。

標準數值格式字串受到下列各項支援：

- 所有數值類型之 `ToString` 方法的一些多載。 例如，您可以將數值格式字串提供給 <xref:System.Int32.ToString%28System.String%29?displayProperty=nameWithType> 和 <xref:System.Int32.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> 方法。

- .NET [複合格式化功能](../../../standard/base-types/composite-formatting.md)，可受到 <xref:System.String.Format%2A?displayProperty=nameWithType> 之類的方法支援。

- [插入字串](../tokens/interpolated.md)。

如需詳細資訊，請參閱[標準數值格式字串](../../../standard/base-types/standard-numeric-format-strings.md)。

## <a name="see-also"></a>請參閱

- [C# 參考](../index.md)
- [C# 程式設計指南](../../programming-guide/index.md)
- [格式化類型](../../../standard/base-types/formatting-types.md)
- [複合格式](../../../standard/base-types/composite-formatting.md)
- [字串內插補點](../tokens/interpolated.md)
- [string](../builtin-types/reference-types.md)
