---
title: 路由服務的 Hello World
ms.date: 03/30/2017
ms.assetid: 0f4b0d5b-6522-4ad5-9f3a-baa78316d7d1
ms.openlocfilehash: 1ab3da97bc94f864bbd28ca072f4df8f7d854ea1
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2019
ms.locfileid: "70044930"
---
# <a name="hello-world-with-the-routing-service"></a>路由服務的 Hello World
這個範例會示範 Windows Communication Foundation (WCF) 路由服務。 路由服務是一個 WCF 元件, 可讓您輕鬆地在應用程式中包含以內容為基礎的路由器。 這個範例會調整標準 WCF 計算機範例, 以便使用路由服務進行通訊。 在此範例中，計算機用戶端設定為傳送訊息到路由器所公開的端點。 路由服務會設定為接受傳送給它的所有訊息，並將其轉送到對應於計算機服務的端點。 因此，傳送自用戶端的訊息會由路由器接收，然後再重新路由至實際的計算機服務。 來自計算機服務的訊息會傳送回路由器，接著再將其傳遞回計算機用戶端。

### <a name="to-use-this-sample"></a>若要使用這個範例

1. 使用 Visual Studio 2012, 開啟 HelloRoutingService。

2. 按下 F5 或 CTRL+SHIFT+B。

    > [!NOTE]
    > 如果按下 F5，計算機用戶端會自動啟動。 如果您按下 CTRL+SHIFT+B (建置)，則必須自行啟動下列應用程式。
    >
    > 1. 計算機用戶端 (./CalculatorClient/bin/client.exe)
    > 2. 計算機服務 (./CalculatorService/bin/service.exe)
    > 3. 路由服務 (./RoutingService/bin/RoutingService.exe)

3. 按 ENTER 鍵以啟動用戶端。

     您應該會看到下列輸出：

    ```console
     Add(100,15.99) = 115.99

     Subtract(145,76.54) = 68.46

     Multiply(9,81.25) = 731.25

     Divide(22,7) = 3.14285714285714
    ```

## <a name="configurable-via-code-or-appconfig"></a>可透過程式碼或 App.Config 設定
 此範例預設為使用 App.config 檔案定義路由器的行為。 您也可以將 App.config 檔案的名稱變更為其他任何名稱，讓其無法辨識，而且可以取消註解對 ConfigureRouterViaCode() 的方法呼叫。 任一種方法都會在路由器中導致相同的行為。

### <a name="scenario"></a>狀況
 此範例示範當做基本訊息幫浦的路由器。 路由服務會當做傳輸 Proxy 節點，而此節點設定為將訊息直接傳遞到一組預先設定的目的地端點。

### <a name="real-world-scenario"></a>真實情節
 Contoso 希望增加它在命名、定址、設定及其服務安全性上所擁有的彈性。 若要這樣做，請將基本訊息幫浦放在其服務前方，以當做公開面對的端點。 這可讓它們在實際服務的前方增加額外的安全性，並使其在日後更容易實作向外延展的方案或服務版本控制。

> [!IMPORTANT]
> 這些範例可能已安裝在您的電腦上。 請先檢查下列 (預設) 目錄，然後再繼續。  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> 如果此目錄不存在, 請移至[.NET Framework 4 的 Windows Communication Foundation (wcf) 和 Windows Workflow Foundation (WF) 範例](https://go.microsoft.com/fwlink/?LinkId=150780), 以下載所有 Windows Communication Foundation (wcf) [!INCLUDE[wf1](../../../../includes/wf1-md.md)]和範例。 此範例位於下列目錄。  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\RoutingServices\HelloRoutingService`  
  
## <a name="see-also"></a>另請參閱

- [AppFabric 裝載和持續性範例](https://go.microsoft.com/fwlink/?LinkId=193961)
