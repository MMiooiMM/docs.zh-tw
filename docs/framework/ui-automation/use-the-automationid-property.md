---
title: 使用 AutomationID 屬性
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- AutomationId property
- UI Automation, AutomationId property
- properties, AutomationId
ms.assetid: a24e807b-d7c3-4e93-ac48-80094c4e1c90
ms.openlocfilehash: 7a172db8bcb626d78a24b546147b4e32f20f5d83
ms.sourcegitcommit: 9c3a4f2d3babca8919a1e490a159c1500ba7a844
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/12/2019
ms.locfileid: "72291353"
---
# <a name="use-the-automationid-property"></a>使用 AutomationID 屬性
> [!NOTE]
> 這份文件適用於想要使用 <xref:System.Windows.Automation> 命名空間中定義之 Managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 類別的 .NET Framework 開發人員。 如需 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 的最新資訊，請參閱 @no__t 1Windows Automation API：UI Automation @ no__t-0。  
  
 本主題包含的案例和範例程式碼，說明如何及何時可以使用 <xref:System.Windows.Automation.AutomationElement.AutomationIdProperty> 找出 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 樹狀結構內的項目。  
  
 <xref:System.Windows.Automation.AutomationElement.AutomationIdProperty> 可唯一識別來自其同層級的使用者介面自動化項目。 如需與控制項識別相關之屬性識別項的詳細資訊，請參閱 [UI Automation Properties Overview](ui-automation-properties-overview.md)。  
  
> [!NOTE]
> <xref:System.Windows.Automation.AutomationElement.AutomationIdProperty> 不保證整個樹狀結構的唯一身分識別；它通常需要搭配容器和範圍資訊才更加實用。 例如，應用程式可能會包含具有多個最上層功能表項目的功能表控制項，而這些項目也有多個子功能表項目。 這些次要功能表項目可由 Item1、Item2 (依此類推) 之類的一般配置識別，因此最上層功能表項目的子系可以有重複識別項。  
  
## <a name="scenarios"></a>案例  
 已識別三個主要的使用者介面自動化用戶端應用程式案例，其在搜尋項目時需要使用 <xref:System.Windows.Automation.AutomationElement.AutomationIdProperty> 才能達到正確且一致的結果。  
  
> [!NOTE]
> 所有控制項檢視中的使用者介面自動化項目都支援<xref:System.Windows.Automation.AutomationElement.AutomationIdProperty> ，除了最上層的應用程式視窗、衍生自不具識別碼或 x:Uid 之 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 控制項的使用者介面自動化項目，以及和使用者介面自動化項目衍生自不具控制項識別碼之 [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)] 控制項的使用者介面自動化項目以外。  
  
#### <a name="use-a-unique-and-discoverable-automationid-to-locate-a-specific-element-in-the-ui-automation-tree"></a>使用唯一且可探索的 AutomationID，在使用者介面自動化樹狀結構中找出特定項目  
  
- 使用 UI Spy 之類的工具，來報告感的 [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] 元素的 <xref:System.Windows.Automation.AutomationElement.AutomationIdProperty>。 您即可將這個值以測試指令碼形式複製及貼入用戶端應用程式，以進行後續的自動化測試。 這種方法可減少並簡化要在執行階段中識別及尋找項目的必要程式碼。  
  
> [!CAUTION]
> 一般而言，您應該試著取得 <xref:System.Windows.Automation.AutomationElement.RootElement%2A>的直接子系。 如果搜尋子代可能會逐一查看數百或甚至數千個項目，就很有可能會造成堆疊溢位。 如果您嘗試取得較低層級的特定項目，您應該從應用程式視窗或較低層級的容器開始搜尋。  
  
 [!code-csharp[UIAAutomationID_snip#100](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAAutomationID_snip/CSharp/FindByAutomationID.xaml.cs#100)]
 [!code-vb[UIAAutomationID_snip#100](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAAutomationID_snip/VisualBasic/FindByAutomationID.xaml.vb#100)]  
  
#### <a name="use-a-persistent-path-to-return-to-a-previously-identified-automationelement"></a>使用持續性路徑，返回先前識別的 AutomationElement  
  
- 用戶端應用程式 (從簡單的測試指令碼到完整的錄製和播放公用程式) 可能需要存取目前未具現化因此並不存在於使用者介面自動化樹狀結構中的項目，例如檔案開啟對話方塊或功能表項目。 這些元素只能透過重現或「播放」來具現化，方法是使用 UI 自動化屬性（例如 AutomationID、控制項模式和事件接聽程式）的特定 UI 動作序列。
  
 [!code-csharp[UIAAutomationID_snip#UIAWorkerThread](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAAutomationID_snip/CSharp/FindByAutomationID.xaml.cs#uiaworkerthread)]
 [!code-vb[UIAAutomationID_snip#UIAWorkerThread](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAAutomationID_snip/VisualBasic/FindByAutomationID.xaml.vb#uiaworkerthread)]  
[!code-csharp[UIAAutomationID_snip#Playback](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAAutomationID_snip/CSharp/FindByAutomationID.xaml.cs#playback)]
[!code-vb[UIAAutomationID_snip#Playback](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAAutomationID_snip/VisualBasic/FindByAutomationID.xaml.vb#playback)]  
  
#### <a name="use-a-relative-path-to-return-to-a-previously-identified-automationelement"></a>使用相對路徑，返回先前識別的 AutomationElement  
  
- 在某些情況下，由於 AutomationID 只保證在同層級是唯一的，因此在使用者介面自動化樹狀結構中的多個項目可能有相同的 AutomationID 屬性值。 在這些情況下，項目只能依據父代、祖系 (若有需要) 來唯一識別。 例如，開發人員可能會提供包含多個功能表項目的功能表列，且每個功能表項目具有多個子功能表項目，並以循序 AutomationID 如「項目 1」、「項目 2」等等來識別子系。 這樣一來，每個功能表項目即可由本身的 AutomationID 搭配其父代及其祖系 (若有需要) 的 AutomationID 來唯一識別。  
  
## <a name="see-also"></a>另請參閱

- <xref:System.Windows.Automation.AutomationElement.AutomationIdProperty>
- [UI 自動化樹狀目錄概觀](ui-automation-tree-overview.md)
- [根據屬性條件尋找 UI 自動化項目](find-a-ui-automation-element-based-on-a-property-condition.md)
