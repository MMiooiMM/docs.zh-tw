---
title: 應用程式開發
ms.date: 01/26/2018
helpviewer_keywords:
- WPF [WPF], about application development
- application development [WPF], about
ms.assetid: 2996ce5e-81e9-49ae-881b-952db3dd1b7e
ms.openlocfilehash: ce37eecf7edf2adcc4f56af27a5c658400f7abba
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/01/2019
ms.locfileid: "73420645"
---
# <a name="application-development"></a>應用程式開發
<a name="introduction"></a>Windows Presentation Foundation （WPF）是一種呈現架構，可用來開發下列類型的應用程式：  
  
- 獨立應用程式（傳統樣式的 Windows 應用程式，建作為可執行元件，並從用戶端電腦執行）。  
  
- XAML 瀏覽器應用程式（Xbap）（這些應用程式是由建立為可執行元件並由網頁瀏覽器（例如 Microsoft Internet Explorer 或 Mozilla Firefox）所主控的導覽頁面所組成）。  
  
- 自訂控制項程式庫 (非可執行組件，其中包含可重複使用的控制項)。  
  
- 類別庫 (非可執行組件，其中包含可重複使用的類別)。  
  
> [!NOTE]
> 強烈建議不要在 Windows 服務中使用 WPF 類型。 如果您嘗試在 Windows 服務中使用這些功能，它們可能無法如預期般運作。  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 會實作多項服務，以建置這組應用程式。 本主題提供這些服務的概觀，並說明何處可以找到更多資訊。  

<a name="Application_Management"></a>   
## <a name="application-management"></a>應用程式管理  
 可執行的 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 應用程式通常需要一組核心功能，其中包括：  
  
- 建立及管理通用應用程式基礎結構 (包括建立進入點方法和 Windows 訊息迴圈以接收系統和輸入訊息)。  
  
- 追蹤應用程式存留期並與其互動。  
  
- 擷取及處理命令列參數。  
  
- 共用應用程式範圍的屬性和 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]資源。  
  
- 偵測及處理未處理的例外狀況。  
  
- 傳回結束代碼。  
  
- 管理獨立應用程式中的視窗。  
  
- 追蹤 XAML 瀏覽器應用程式（Xbap）中的導覽，以及具有流覽視窗和框架的獨立應用程式。  
  
 這些功能是由 <xref:System.Windows.Application> 類別實作，您可以使用「應用程式定義」將此類別新增至應用程式。  
  
 如需詳細資訊，請參閱[應用程式管理概觀](application-management-overview.md)。  
  
<a name="WPF_Application_Resource__Content__and_Data_Files"></a>   
## <a name="wpf-application-resource-content-and-data-files"></a>WPF 應用程式資源、內容和資料檔案  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 為內嵌資源擴充 Microsoft .NET Framework 中的核心支援，並支援三種無法執行的資料檔案：資源、內容和資料。 如需詳細資訊，請參閱 [WPF 應用程式資源、內容和資料檔案](wpf-application-resource-content-and-data-files.md)。  
  
 WPF 無法執行的資料檔案支援的主要元件，是使用唯一的 URI 來識別和載入它們的能力。 如需詳細資訊，請參閱 [WPF 中的 Pack URI](pack-uris-in-wpf.md)。  
  
<a name="Windows_and_Dialog_Boxes"></a>   
## <a name="windows-and-dialog-boxes"></a>視窗和對話方塊  
 使用者是透過視窗與 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 獨立應用程式互動。 視窗的用途是裝載應用程式內容，以及公開通常可讓使用者與內容互動的應用程式功能。 在 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 中，視窗是由 <xref:System.Windows.Window> 類別封裝，該類別支援：  
  
- 建立及顯示視窗。  
  
- 建立主控視窗/附屬視窗的關聯性。  
  
- 設定視窗外觀 (例如大小、位置、圖示、標題列文字、框線)。  
  
- 追蹤視窗存留期並與其互動。  
  
 如需詳細資訊，請參閱 [WPF 視窗概觀](wpf-windows-overview.md)。  
  
 <xref:System.Windows.Window> 可建立一種特殊的視窗類型，稱為對話方塊。 您可以建立強制回應和非強制回應類型的對話方塊。  
  
 為了方便起見，以及跨應用程式的重複使用性和一致使用者體驗的優點，[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 會公開三個通用的 Windows 對話方塊： <xref:Microsoft.Win32.OpenFileDialog>、<xref:Microsoft.Win32.SaveFileDialog>和 <xref:System.Windows.Controls.PrintDialog>。  
  
 訊息方塊是一種特殊的對話方塊類型，可將重要的文字資訊顯示給使用者，以及詢問簡單的「是/否/確定/取消」問題。 您可以使用 <xref:System.Windows.MessageBox> 類別來建立及顯示訊息方塊。  
  
 如需詳細資訊，請參閱[對話方塊概觀](dialog-boxes-overview.md)。  
  
<a name="Navigation"></a>   
## <a name="navigation"></a>巡覽  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 支援使用頁面 (<xref:System.Windows.Controls.Page>) 和超連結 (<xref:System.Windows.Documents.Hyperlink>) 的 Web 式瀏覽。 您可以透過各種方式來實作瀏覽，包括：  
  
- 裝載於網頁瀏覽器的獨立頁面。  
  
- 編譯成 XBAP 的頁面，裝載在網頁瀏覽器中。  
  
- 編譯成獨立應用程式並由瀏覽視窗 (<xref:System.Windows.Navigation.NavigationWindow>) 裝載的頁面。  
  
- 由框架（<xref:System.Windows.Controls.Frame>）主控的頁面，可能裝載于獨立頁面，或編譯成 XBAP 或獨立應用程式的頁面。  
  
 為了加速瀏覽，[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 會實作下列項目：  
  
- <xref:System.Windows.Navigation.NavigationService>，這是用來處理導覽要求的共用導覽引擎，可由 <xref:System.Windows.Controls.Frame>、<xref:System.Windows.Navigation.NavigationWindow>和 Xbap 用來支援應用程式內導覽。  
  
- 要啟始瀏覽的瀏覽方法。  
  
- 要追蹤瀏覽存留期並與其互動的瀏覽事件。  
  
- 使用日誌記住向後和向前瀏覽，該日誌也可供檢查和操作。  
  
 如需相關資訊，請參閱[瀏覽概觀](navigation-overview.md)。  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 也支援一種特殊的瀏覽類型，稱為結構化瀏覽。 結構化瀏覽可用來呼叫一或多個頁面，這些頁面會以與呼叫函式一致的結構化且可預期方式傳回資料。 此功能相依於 <xref:System.Windows.Navigation.PageFunction%601> 類別，這在[結構化巡覽概觀](structured-navigation-overview.md)中將進一步說明。 <xref:System.Windows.Navigation.PageFunction%601> 也可用來簡化複雜瀏覽拓撲的建立，這在[巡覽拓撲概觀](navigation-topologies-overview.md)中將進行說明。  
  
<a name="Hosting"></a>   
## <a name="hosting"></a>架設  
 Xbap 可以裝載于 Microsoft Internet Explorer 或 Firefox 中。 每個裝載模型有各自的一組考量和條件約束，[裝載](hosting-wpf-applications.md)中將進行說明。  
  
<a name="Build_and_Deploy"></a>   
## <a name="build-and-deploy"></a>建置和部署  
 雖然可以使用命令列編譯器從命令提示字元建立簡單的 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 應用程式，[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 與 Visual Studio 整合，以提供簡化開發和建立程式的額外支援。 如需詳細資訊，請參閱[建置 WPF 應用程式](building-a-wpf-application-wpf.md)。  
  
 根據您建置的應用程式類型，有一或多個部署選項可供選擇。 如需詳細資訊，請參閱[部署 WPF 應用程式](deploying-a-wpf-application-wpf.md)。  
  
<a name="related_topics"></a>   
## <a name="related-topics"></a>相關主題  
  
|標題|描述|  
|-----------|-----------------|  
|[應用程式管理概觀](application-management-overview.md)|提供 <xref:System.Windows.Application> 類別的概觀，包括管理應用程式存留期、視窗、應用程式資源和瀏覽。|  
|[WPF 中的視窗](windows-in-wpf-applications.md)|提供在應用程式中管理視窗的詳細資料，包括如何使用 <xref:System.Windows.Window> 類別和對話方塊。|  
|[瀏覽概觀](navigation-overview.md)|提供有關管理在應用程式頁面之間瀏覽的概觀。|  
|[裝載](hosting-wpf-applications.md)|提供 XAML 瀏覽器應用程式（Xbap）的總覽。|  
|[建置和部署](building-and-deploying-wpf-applications.md)|描述如何建置及部署 WPF 應用程式。|  
|[Visual Studio 中的 WPF 簡介](../getting-started/introduction-to-wpf-in-vs.md)|描述 WPF 的主要功能。|  
|[逐步解說：我的第一個 WPF 傳統型應用程式](../getting-started/walkthrough-my-first-wpf-desktop-application.md)|示範如何建立使用頁面瀏覽、配置、控制項、影像、樣式和繫結之 WPF 應用程式的逐步解說。|
