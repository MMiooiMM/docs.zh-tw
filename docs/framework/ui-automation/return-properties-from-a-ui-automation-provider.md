---
title: 從 UI 自動化提供者傳回屬性
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- providers, UI Automation, returning properties
- properties, returned by UI Automation providers
- UI Automation, providers returning properties
ms.assetid: 5eba950e-b9e1-48eb-ab8e-b69db76bf589
ms.openlocfilehash: 5d073af121eae04a973667739c68a90d6dae9f2d
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/17/2019
ms.locfileid: "71042739"
---
# <a name="return-properties-from-a-ui-automation-provider"></a>從 UI 自動化提供者傳回屬性
> [!NOTE]
> 這份文件適用於想要使用 <xref:System.Windows.Automation> 命名空間中定義之 Managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 類別的 .NET Framework 開發人員。 如需的最新[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]資訊, [請參閱 Windows Automation API:使用者介面](https://go.microsoft.com/fwlink/?LinkID=156746)自動化。  
  
 本主題包含範例程式碼，示範使用者介面自動化提供者如何將項目的屬性傳回給用戶端應用程式。  
  
 對於任何未明確支援的屬性而言，提供者必須傳回 `null` (Visual Basic 中的`Nothing` )。 如此可確保 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 會嘗試從另一個來源取得屬性，例如裝載視窗提供者。  
  
## <a name="example"></a>範例  
 [!code-csharp[UIAFragmentProvider_snip#117](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAFragmentProvider_snip/CSharp/ListFragment.cs#117)]
 [!code-vb[UIAFragmentProvider_snip#117](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAFragmentProvider_snip/VisualBasic/ListFragment.vb#117)]  
  
## <a name="see-also"></a>另請參閱

- [UI 自動化提供者概觀](ui-automation-providers-overview.md)
- [伺服器端 UI 自動化提供者實作](server-side-ui-automation-provider-implementation.md)
