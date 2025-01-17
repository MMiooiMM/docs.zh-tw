---
title: 裝載服務
ms.date: 03/30/2017
helpviewer_keywords:
- hosting services [WCF]
ms.assetid: 192be927-6be2-4fda-98f0-e513c4881acc
ms.openlocfilehash: 634e34eceeb3d3b8828a6d5ed85b6194bcf8586c
ms.sourcegitcommit: 9b2ef64c4fc10a4a10f28a223d60d17d7d249ee8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/26/2019
ms.locfileid: "72961157"
---
# <a name="hosting-services"></a>裝載服務

如果要成為作用中的服務，必須將服務裝載在建立及控制其內容和存留時間的執行階段環境中。 Windows Communication Foundation （WCF）服務的設計目的是要在支援 managed 程式碼的任何 Windows 進程中執行。

WCF 提供統一的程式設計模型，用來建立服務導向的應用程式。 這個程式設計模型會維持一致並與部署服務的執行階段環境互相獨立。 實務上，這意味著不管裝載選項為何，服務的程式碼看起來都差不多。

這些裝載選項的範圍從在主控台應用程式中執行到伺服器環境 (例如，在由網際網路資訊服務 (IIS) 或 Windows Process Activation Service (WAS) 管理的背景工作處理序中執行的 Windows 服務) 不一而足。 開發人員可選擇滿足服務部署需求的裝載環境。 這些需求可能源自部署了應用程式的平台、應用程式必須賴以傳送與接收訊息的傳輸，或是用來確保足夠可用性所需的處理序回收類型與其他處理序管理，或是其他一些管理或可靠性需求。 下節將提供有關裝載選項的資訊與指引。

## <a name="hosting-options"></a>裝載選項

### <a name="self-host-in-a-managed-application"></a>受控應用程式中的自我裝載
 WCF 服務可以裝載于任何 managed 應用程式中。 這是最彈性的選項，因為它只需要最少的基礎結構就可部署。 您可以將服務的程式碼嵌入 Managed 應用程式程式碼中，然後建立並開啟 <xref:System.ServiceModel.ServiceHost> 的執行個體以便提供服務。 如需詳細資訊，請參閱[如何：在 Managed 應用程式中裝載 WCF 服務](how-to-host-a-wcf-service-in-a-managed-application.md)。

 此選項可啟用兩個常見的案例：在主控台應用程式中執行的 WCF 服務和豐富型用戶端應用程式（例如以 Windows Presentation Foundation （WPF）或 Windows Forms （WinForms）為基礎的）。 在應用程式的開發階段，將 WCF 服務裝載于主控台應用程式中通常很有用。 這樣一來，您可以很容易地進行偵錯、取得追蹤資訊以便了解應用程式裡面所發生的事，以及藉由將它們複製到新的位置輕易地加以移動。 此裝載選項也可讓豐富型用戶端應用程式（例如 WPF 和 WinForms 應用程式）輕鬆地與外界進行通訊。 例如，對等共同作業用戶端會使用 WPF 做為其使用者介面，同時裝載 WCF 服務，以允許其他用戶端與其連線並共用資訊。

### <a name="managed-windows-services"></a>Managed Windows 服務
 這個裝載選項包含將 WCF 服務裝載為 managed Windows 服務（之前稱為 NT 服務）的應用程式域（AppDomain），以便服務的進程存留期是由的服務控制管理員（SCM）控制Windows 服務。 就像自我裝載選項一樣，此類型的裝載環境要求將某些裝載程式碼撰寫成應用程式的一部分。 服務會同時實作為 Windows 服務和 WCF 服務，方法是讓它繼承自 <xref:System.ServiceProcess.ServiceBase> 類別以及 WCF 服務合約介面。 <xref:System.ServiceModel.ServiceHost> 接著會透過覆寫的 <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> 方法來建立並開啟，並透過覆寫的 <xref:System.ServiceProcess.ServiceBase.OnStop> 方法加以關閉。 繼承自 <xref:System.Configuration.Install.Installer> 的安裝程式類別必須同時實作，以允許藉由 Installutil.exe 工具將程式安裝為 Windows 服務。 如需詳細資訊，請參閱[如何：在 Managed Windows 服務中裝載 WCF 服務](./feature-details/how-to-host-a-wcf-service-in-a-managed-windows-service.md)。 Managed Windows 服務裝載選項所啟用的案例，就是在非訊息啟動的安全環境中，由 IIS 外部主控的長時間執行 WCF 服務。 服務的存留期會改由作業系統來控制。 所有 Windows 版本都提供這個裝載選項。

### <a name="internet-information-services-iis"></a>Internet Information Services (IIS)
 IIS 裝載選項會與 ASP.NET 整合，並使用這些技術所提供的功能，例如進程回收、閒置關機、進程健康狀態監控，以及訊息型啟用。 在 [!INCLUDE[wxp](../../../includes/wxp-md.md)] 和 [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] 作業系統中，建議您採用這個解決方案來裝載必須具備高度可用性與高度擴充性的 Web 服務應用程式。 IIS 同時提供整合式管理功能，而這也是客戶希望從企業級伺服器產品中所得到的功能。 這個裝載選項要求必須正確設定 IIS，但不要求您將任何裝載程式碼撰寫為應用程式的一部分。 如需如何設定 WCF 服務之 IIS 裝載的詳細資訊，請參閱[如何：在 iis 中裝載 Wcf 服務](./feature-details/how-to-host-a-wcf-service-in-iis.md)。

 請注意，IIS 裝載的服務只能使用 HTTP 傳輸。 它在 IIS 5.1 版的實作方式已經為 [!INCLUDE[wxp](../../../includes/wxp-md.md)]帶來一些限制。 IIS 5.1 針對 WCF 服務所提供的訊息型啟用 [!INCLUDE[wxp](../../../includes/wxp-md.md)] 會封鎖同一部電腦上任何其他自我裝載的 WCF 服務，使其無法使用埠80進行通訊。 當 IIS 6.0 在 [!INCLUDE[ws2003](../../../includes/ws2003-md.md)]上主控時，WCF 服務可以在與其他應用程式相同的 AppDomain/應用程式集區/背景工作進程中執行。 但因為 WCF 和 IIS 6.0 都使用核心模式 HTTP 堆疊（HTTP.SYS），所以 IIS 6.0 可以與在同一部電腦上執行的其他自我裝載 WCF 服務共用埠80，而不像 IIS 5.1。

### <a name="windows-process-activation-service-was"></a>Windows Process Activation Service (WAS)
 Windows Process Activation Service (WAS) 是 [!INCLUDE[lserver](../../../includes/lserver-md.md)] 上全新的處理序啟動機制 ( [!INCLUDE[wv](../../../includes/wv-md.md)]也提供此機制)。 它會保留熟悉的 IIS 6.0 進程模型（應用程式集區和訊息型進程啟用）和裝載功能（例如快速失敗保護、健康情況監視及回收），但它會從啟用中移除對 HTTP 的相依性。結構. IIS 7.0 使用 WAS，透過 HTTP 完成以訊息為基礎的啟用。 其他 WCF 元件也會插入 WAS，以透過 WCF 支援的其他通訊協定（例如 TCP、MSMQ 和具名管道）來提供以訊息為基礎的啟用。 如此便可讓使用通訊協定的應用程式使用 IIS 功能，例如處理序回收、快速故障防護，以及只提供給以 HTTP 為基礎的應用程式使用的常見組態系統等。

 這個裝載選項要求必須正確設定 WAS，但不要求您將任何裝載程式碼撰寫為應用程式的一部分。 如需如何設定 WAS 裝載的詳細資訊，請參閱[如何：在 was 中裝載 WCF 服務](./feature-details/how-to-host-a-wcf-service-in-was.md)。

## <a name="choose-a-hosting-environment"></a>選擇裝載環境
 下表將摘要說明一些與各個裝載選項相關的主要優點與案例。

|裝載環境|常見案例|主要優點與限制|
|-------------------------|----------------------|----------------------------------|
|Managed 應用程式 (「自我裝載」)|-在開發期間使用的主控台應用程式。<br />-豐富的 WinForm 和 WPF 用戶端應用程式存取服務。|彈性.<br />-易於部署。<br />-不是服務的企業解決方案。|
|Windows 服務 (之前稱為 NT 服務)|-裝載于 IIS 外部的長時間執行 WCF 服務。|-作業系統所控制的服務進程存留期，而不是訊息啟動。<br />-所有版本的 Windows 都支援。<br />-安全環境。|
|IIS 5.1、IIS 6。0|-使用 HTTP 通訊協定，並存執行 WCF 服務與網際網路上的 ASP.NET 內容。|-進程回收。<br />-閒置關機。<br />-進程健全狀況監視。<br />-以訊息為基礎的啟用。<br />-僅限 HTTP。|
|Windows Process Activation Service (WAS)|-執行 WCF 服務，而不使用各種傳輸通訊協定在網際網路上安裝 IIS。|-不需要 IIS。<br />-進程回收。<br />-閒置關機。<br />-進程健全狀況監視。<br />-以訊息為基礎的啟用。<br />-適用于 HTTP、TCP、具名管道和 MSMQ。|
|IIS 7.0|-執行具有 ASP.NET 內容的 WCF 服務。<br />-使用各種傳輸通訊協定在網際網路上執行 WCF 服務。|-是優點。<br />-與 ASP.NET 和 IIS 內容整合。|

 裝載環境的選擇取決於用來部署該環境的 Windows 版本、用來傳送訊息所需的傳輸，以及所需的處理序類型和應用程式定義域回收。 下表摘要說明與這些需求相關的資料。

|裝載環境|平台可用性|支援的傳輸|處理序和 AppDomain 回收|
|-------------------------|---------------------------|--------------------------|-------------------------------------|
|Managed 應用程式 (「自我裝載」)|[!INCLUDE[wxp](../../../includes/wxp-md.md)], [!INCLUDE[ws2003](../../../includes/ws2003-md.md)], [!INCLUDE[wv](../../../includes/wv-md.md)],<br /><br /> [!INCLUDE[lserver](../../../includes/lserver-md.md)]|HTTP、<br /><br /> net.tcp、<br /><br /> net.pipe、<br /><br /> net.msmq|否|
|Windows 服務 (之前稱為 NT 服務)|[!INCLUDE[wxp](../../../includes/wxp-md.md)], [!INCLUDE[ws2003](../../../includes/ws2003-md.md)], [!INCLUDE[wv](../../../includes/wv-md.md)],<br /><br /> [!INCLUDE[lserver](../../../includes/lserver-md.md)]|HTTP、<br /><br /> net.tcp、<br /><br /> net.pipe、<br /><br /> net.msmq|否|
|IIS 5.1|[!INCLUDE[wxp](../../../includes/wxp-md.md)]|HTTP|[是]|
|IIS 6.0|[!INCLUDE[ws2003](../../../includes/ws2003-md.md)]|HTTP|[是]|
|Windows Process Activation Service (WAS)|[!INCLUDE[wv](../../../includes/wv-md.md)]、 [!INCLUDE[lserver](../../../includes/lserver-md.md)]|HTTP、<br /><br /> net.tcp、<br /><br /> net.pipe、<br /><br /> net.msmq|[是]|

 從未受信任的主機執行服務或任何延伸項目都會破壞安全性，這點請您務必注意。 同時，請注意當您開啟模擬下的 <xref:System.ServiceModel.ServiceHost> 時，應用程式必須確定使用者尚未登出，例如，藉由快取使用者的 <xref:System.Security.Principal.WindowsIdentity> 來判斷。

## <a name="see-also"></a>請參閱

- [基本程式設計週期](basic-programming-lifecycle.md)
- [履行服務合約](implementing-service-contracts.md)
- [如何：在 IIS 中裝載 WCF 服務](./feature-details/how-to-host-a-wcf-service-in-iis.md)
- [如何：在 WAS 中裝載 WCF 服務](./feature-details/how-to-host-a-wcf-service-in-was.md)
- [如何：在 Managed Windows 服務中裝載 WCF 服務](./feature-details/how-to-host-a-wcf-service-in-a-managed-windows-service.md)
- [如何：於受管理的應用程式中裝載 WCF 服務](how-to-host-a-wcf-service-in-a-managed-application.md)
