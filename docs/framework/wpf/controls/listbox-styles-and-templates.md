---
title: ListBox 樣式和範本
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], ListBox
- templates [WPF], ListBox
- states [WPF], ListBox
- ControlTemplate [WPF], ListBox
- parts [WPF], ListBox
- ListBox [WPF], styles and templates
ms.assetid: fc5764cb-c27b-495b-88d4-d969a8213ccb
ms.openlocfilehash: 279683752e6767bbf3e5bc359ec1e72193602c00
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459288"
---
# <a name="listbox-styles-and-templates"></a>ListBox 樣式和範本
本主題描述 <xref:System.Windows.Controls.ListBox> 控制項的樣式和範本。 您可以修改預設 <xref:System.Windows.Controls.ControlTemplate>，為控制項提供獨特的外觀。 如需詳細資訊，請參閱[透過建立 ControlTemplate 自訂現有控制項的外觀](customizing-the-appearance-of-an-existing-control.md)。  
  
## <a name="listbox-parts"></a>ListBox 組件  
 <xref:System.Windows.Controls.ListBox> 控制項沒有任何已命名的元件。  
  
 當您建立 <xref:System.Windows.Controls.ListBox>的 <xref:System.Windows.Controls.ControlTemplate> 時，您的範本可能會在 <xref:System.Windows.Controls.ScrollViewer>中包含 <xref:System.Windows.Controls.ItemsPresenter>。 （<xref:System.Windows.Controls.ItemsPresenter> 會顯示 <xref:System.Windows.Controls.ListBox>中的每個專案，<xref:System.Windows.Controls.ScrollViewer> 可在控制項內進行滾動）。  如果 <xref:System.Windows.Controls.ItemsPresenter> 不是 <xref:System.Windows.Controls.ScrollViewer>的直接子系，您必須為 <xref:System.Windows.Controls.ItemsPresenter> 指定名稱，`ItemsPresenter`。  
  
## <a name="listbox-states"></a>ListBox 狀態  
 下表列出 <xref:System.Windows.Controls.ListBox> 控制項的視覺狀態。  
  
|VisualState 名稱|VisualStateGroup 名稱|描述|  
|-|-|-|  
|驗證|ValidationStates|控制項有效。|  
|InvalidFocused|ValidationStates|控制項無效且已取得焦點。|  
|InvalidUnfocused|ValidationStates|控制項無效且未取得焦點。|  
  
## <a name="listboxitem-parts"></a>ListBoxItem 組件  
 <xref:System.Windows.Controls.ListBoxItem> 控制項沒有任何已命名的元件。  
  
## <a name="listboxitem-states"></a>ListBoxItem 狀態  
 下表列出 <xref:System.Windows.Controls.ListBox> 控制項的視覺狀態。  
  
|VisualState 名稱|VisualStateGroup 名稱|描述|  
|-|-|-|  
|一般|CommonStates|預設狀態。|  
|MouseOver|CommonStates|滑鼠指標移到控制項上。|  
|Disabled|CommonStates|項目已停用。|  
|已取得焦點|FocusStates|項目已取得焦點。|  
|未取得焦點|FocusStates|項目未取得焦點。|  
|未選取|SelectionStates|項目未獲選取。|  
|已選取|SelectionStates|項目目前已獲選取。|  
|SelectedUnfocused|SelectionStates|項目已獲選取，但未取得焦點。|  
|驗證|ValidationStates|控制項使用 <xref:System.Windows.Controls.Validation> 類別，而 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加屬性則 `false`。|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加屬性是控制項具有焦點 `true`。|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 附加屬性是 `true` 控制項沒有焦點。|  
  
## <a name="listbox-controltemplate-example"></a>ListBox ControlTemplate 範例  
 下列範例顯示如何定義 <xref:System.Windows.Controls.ListBox> 和 <xref:System.Windows.Controls.ListBoxItem> 控制項的 <xref:System.Windows.Controls.ControlTemplate>。  
  
 [!code-xaml[ControlTemplateExamples#ListBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/listbox.xaml#listbox)]  
  
 上述範例使用下列一或多項資源。  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 如需完整的範例，請參閱[使用 ControlTemplate 設定樣式範例](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)。  
  
## <a name="see-also"></a>請參閱

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [控制項的樣式和範本](control-styles-and-templates.md)
- [控制項自訂](control-customization.md)
- [設定樣式和範本](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [透過建立 ControlTemplate 自訂現有控制項的外觀](customizing-the-appearance-of-an-existing-control.md)
