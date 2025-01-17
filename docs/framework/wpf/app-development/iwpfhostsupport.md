---
title: IWpfHostSupport
ms.date: 03/30/2017
helpviewer_keywords:
- IWpfHostSupport interface [WPF]
ms.assetid: cc5a0281-de81-4cc1-87e4-0e46b1a811e9
ms.openlocfilehash: 91a29233d12a842a64b7d3dd497312f6dc6742ca
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423642"
---
# <a name="iwpfhostsupport"></a>IWpfHostSupport
透過 Presentationhost.exe 裝載 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 內容的應用程式會執行此介面，以提供主機和 Presentationhost.exe 之間的整合點。  
  
## <a name="remarks"></a>備註  
 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] 的應用程式（例如網頁瀏覽器）可以裝載 WPF 內容，包括 XAML 瀏覽器應用程式（Xbap）和鬆散的 XAML。 若要裝載 WPF 內容，[!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] 應用程式會建立[WebBrowser 控制項](https://go.microsoft.com/fwlink/?LinkId=97911)的實例。 WPF 會建立 Presentationhost.exe 的實例，它會將裝載的 WPF 內容提供給主控制項，以便在[WebBrowser 控制項](https://go.microsoft.com/fwlink/?LinkId=97911)中顯示。  
  
 `IWpfHostSupport` 啟用的整合允許 Presentationhost.exe：  
  
- 探索並向主機應用程式感興趣的原始輸入裝置（人類介面裝置）進行註冊。  
  
- 從已註冊的原始輸入裝置接收輸入訊息，並將適當的訊息轉送至主應用程式。  
  
- 查詢主應用程式中的自訂進度和錯誤使用者介面。  
  
> [!NOTE]
> 僅限在本機用戶端電腦上使用及支援此 API  
  
## <a name="members"></a>Members  
  
|成員|描述|  
|------------|-----------------|  
|[GetRawInputDevices](getrawinputdevices.md)|可讓 PresentationHost.exe 探索主應用程式有興趣的未經處理輸入裝置 (人性化介面裝置)。|  
|[FilterInputMessage](filterinputmessage.md)|除非傳回 E_NOTIMPL，否則每當收到訊息時，都會由 PresentationHost.exe 呼叫。|  
|[GetCustomUI](getcustomui.md)|根據預設，Presentationhost.exe 會提供自己的部署進度和部署錯誤使用者介面，在部署 WPF 內容時顯示。|
