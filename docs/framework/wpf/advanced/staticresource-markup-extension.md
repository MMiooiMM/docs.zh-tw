---
title: StaticResource 標記延伸
ms.date: 03/30/2017
f1_keywords:
- StaticResource
- StaticResourceExtension
helpviewer_keywords:
- XAML [WPF], StaticResource markup extension
- StaticResource markup extensions [WPF]
ms.assetid: 97af044c-71f1-4617-9a94-9064b68185d2
ms.openlocfilehash: b15e2c0bac5610c6f1b10a640254236987c0bcf5
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458731"
---
# <a name="staticresource-markup-extension"></a>StaticResource 標記延伸
藉由查閱已定義資源的參考，為任何 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 屬性屬性提供值。 該資源的查閱行為類似于載入時間查閱，它會尋找先前從目前 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 頁面的標記載入的資源，以及其他應用程式來源，並將該資源值產生為屬性執行時間物件中的值。  
  
## <a name="xaml-attribute-usage"></a>XAML Attribute Usage  
  
```xml  
<object property="{StaticResource key}" .../>  
```  
  
## <a name="xaml-object-element-usage"></a>XAML 物件項目用法  
  
```xml  
<object>  
  <object.property>  
<StaticResource ResourceKey="key" .../>  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a>XAML 值  
  
|||  
|-|-|  
|`key`|要求資源的金鑰。 如果資源是在標記中建立，則此索引鍵一開始是由[x：Key](../../xaml-services/x-key-directive.md)指示詞所指派，或在呼叫 <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> （如果資源是在程式碼中建立）時，以 `key` 參數的形式提供。|  
  
## <a name="remarks"></a>備註  
  
> [!IMPORTANT]
> `StaticResource` 不能嘗試對 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 檔案中進一步定義的資源進行向前參考。 不支援嘗試這麼做，而且即使這類參考不會失敗，當搜尋代表 <xref:System.Windows.ResourceDictionary> 的內部雜湊表時，嘗試向前參考也會造成載入時間效能的負面影響。 為了獲得最佳結果，請調整資源字典的組合，讓向前參考可以避免。 如果您無法避免正向參考，請改用[DynamicResource 標記延伸](dynamicresource-markup-extension.md)。  
  
 指定的 <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> 應對應至現有的資源，並在頁面、應用程式、可用的控制項主題和外部資源或系統資源的某個層級以[x：Key](../../xaml-services/x-key-directive.md)指示詞識別。 資源查閱會依照該順序發生。 如需靜態和動態資源的資源查閱行為詳細資訊，請參閱[XAML 資源](../../../desktop-wpf/fundamentals/xaml-resources-define.md)。  
  
 資源索引鍵可以是[XamlName 文法](../../xaml-services/xamlname-grammar.md)中定義的任何字串。 資源金鑰也可以是其他物件類型，例如 <xref:System.Type>。 <xref:System.Type> 鍵是如何透過隱含樣式索引鍵，以主題為控制項樣式的基礎。 如需詳細資訊，請參閱[控制項撰寫概觀](../controls/control-authoring-overview.md)。  
  
 參考資源的替代宣告式方法是[DynamicResource 標記延伸](dynamicresource-markup-extension.md)。  
  
 屬性 (Attribute) 語法是最常搭配這個標記延伸來使用的語法。 `StaticResource` 識別項字串後所提供的字串語彙基元，是指派做為基礎 <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> 延伸類別的 <xref:System.Windows.StaticResourceExtension> 值。  
  
 `StaticResource` 可以在物件專案語法中使用。 在此情況下，必須指定 <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> 屬性的值。  
  
 `StaticResource` 也可以用於會指定 <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> 屬性 (Property) 做為 property=value 配對組的詳細屬性 (Attribute) 使用方式中。  
  
```xml  
<object property="{StaticResource ResourceKey=key}" .../>  
```  
  
 詳細使用方式通常是適用於具有一個以上可設定屬性或有些屬性為選擇性屬性的標記延伸。 因為 `StaticResource` 只有一個必要的可設定屬性，所以這種詳細使用方式並不常見。  
  
 在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 處理器執行中，此標記延伸模組的處理是由 <xref:System.Windows.StaticResourceExtension> 類別所定義。  
  
 `StaticResource` 是一種標記延伸。 如果必須將屬性 (Attribute) 值加上逸出符號，以免成為常值或處理常式名稱，而且這個動作必須更全面地實施 (而不是只對特定類型或屬性 (Property) 設定類型轉換子 (Type Converter))，則通常會實作標記延伸。 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 中的所有標記延伸都會在其屬性語法中使用 { 與 } 字元，這個慣例讓 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 處理器知道某個標記延伸必須處理這個屬性。 如需詳細資訊，請參閱[標記延伸和 WPF XAML](markup-extensions-and-wpf-xaml.md)。  
  
## <a name="see-also"></a>請參閱

- [設定樣式和範本](../controls/styling-and-templating.md)
- [XAML 概觀 (WPF)](xaml-overview-wpf.md)
- [標記延伸和 WPF XAML](markup-extensions-and-wpf-xaml.md)
- [XAML 資源](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [資源和程式碼](resources-and-code.md)
