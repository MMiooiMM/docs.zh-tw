---
title: mc:Ignorable 屬性
ms.date: 03/30/2017
helpviewer_keywords:
- mc XML namespace prefix [WPF]
- mc:Ignorable attribute
- XML [WPF], mc namespace prefix
- XAML [WPF], mc:Ignorable attribute
- mc:ProcessContent attribute
- XAML [WPF], mc:ProcessContent attribute
ms.assetid: acd9a6ef-b7ca-4146-abb6-60f3b366e9ec
ms.openlocfilehash: d8fdeec8784c9a44c9b272a0a5a8b9c56ace5230
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458825"
---
# <a name="mcignorable-attribute"></a>mc:Ignorable 屬性
指定 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 處理器可以忽略標記檔案中發現的 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 命名空間前置詞。 `mc:Ignorable` 屬性支援自訂命名空間對應和 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 版本設定的標記相容性。  
  
## <a name="xaml-attribute-usage-single-prefix"></a>XAML 屬性使用方式（單一前置詞）  
  
```xaml  
<object  
  xmlns:ignorablePrefix="ignorableUri"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## <a name="xaml-attribute-usage-two-prefixes"></a>XAML 屬性使用方式（兩個首碼）  
  
```xaml  
<object  
  xmlns:ignorablePrefix1="ignorableUri"  
  xmlns:ignorablePrefix2="ignorableUri2"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix1 ignorablePrefix2"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## <a name="xaml-values"></a>XAML 值  
  
|||  
|-|-|  
|*ignorablePrefix、ignorablePrefix1 等等。*|任何有效的前置字串，依據 XML 1.0 規格。|  
|*ignorableUri*|根據 XML 1.0 規格，指定命名空間的任何有效 URI。|  
|*ThisElementCanBeIgnored*|如果無法解析基礎類型，則 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 處理器實作為可以忽略的元素。|  
  
## <a name="remarks"></a>備註  
 `mc` [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 命名空間前置詞是對應 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 相容性命名空間 `http://schemas.openxmlformats.org/markup-compatibility/2006`時所使用的建議前置詞慣例。  
  
 元素或屬性，其中專案名稱的前置詞部分會識別為 `mc:Ignorable` 在 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 處理器處理時不會引發錯誤。 如果該屬性無法解析成基礎類型或程式設計結構，則會忽略該元素。 不過，請注意，忽略的元素仍然可能針對該專案未處理的其他專案需求，產生額外的剖析錯誤。 例如，特定專案內容模型可能只需要一個子專案，但如果指定的子專案是在 `mc:Ignorable` 前置詞中，而指定的子專案無法解析成型別，則 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 的處理器可能會引發錯誤。  
  
 `mc:Ignorable` 只適用于命名空間對應至識別碼字串。 `mc:Ignorable` 不會套用至元件中的命名空間對應，這會指定 CLR 命名空間和元件（或預設為目前可執行檔做為元件）。  
  
 如果您要執行 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 處理器，則您的處理器執行不能針對識別為 `mc:Ignorable`的前置詞所限定的任何元素或屬性，在類型解析上引發剖析或處理錯誤。 但是，您的處理器執行仍然可以引發無法載入或處理之元素的次要結果的例外狀況，例如先前指定的一個子項目範例。  
  
 根據預設，[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 的處理器會忽略忽略專案中的內容。 不過，您可以指定其他屬性[mc： ProcessContent 屬性](mc-processcontent-attribute.md)，以要求在下一個可用的父元素中繼續處理忽略專案內的內容。  
  
 您可以在屬性中指定多個前置詞，使用一或多個空白字元做為分隔符號，例如： `mc:Ignorable="ignore1 ignore2"`。  

 `http://schemas.openxmlformats.org/markup-compatibility/2006` 命名空間會定義在 SDK 的這個區域中未記載的其他元素和屬性。 如需詳細資訊，請參閱[XML 標記相容性規格](/office/open-xml/introduction-to-markup-compatibility#markup-compatibility-in-the-open-xml-file-formats-specification)。  
  
## <a name="see-also"></a>請參閱

- <xref:System.Windows.Markup.XamlReader>
- [PresentationOptions:Freeze 屬性](presentationoptions-freeze-attribute.md)
- [XAML 概觀 (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [WPF 中的文件](documents-in-wpf.md)
