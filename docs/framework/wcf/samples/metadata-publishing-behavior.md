---
title: 中繼資料發行行為
ms.date: 03/30/2017
helpviewer_keywords:
- service behaviors, metadata publishing sample
- Metadata Publishing Behaviors Sample [Windows Communication Foundation]
ms.assetid: 78c13633-d026-4814-910e-1c801cffdac7
ms.openlocfilehash: 4b3bc0490f791776793e91de0bb8608264663af5
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/27/2019
ms.locfileid: "70044838"
---
# <a name="metadata-publishing-behavior"></a>中繼資料發行行為
中繼資料發行行為範例會示範如何控制服務的中繼資料發行功能。 為避免不慎洩漏可能的敏感性服務中繼資料, Windows Communication Foundation (WCF) 服務的預設設定會停用中繼資料發行。 這個行為依預設為安全行為，但也表示您無法使用中繼資料匯入工具 (例如 Svcutil.exe) 來產生呼叫服務所需的用戶端程式碼，除非組態中已明確啟用服務的中繼發行行為。  
  
> [!IMPORTANT]
> 為了清楚說明，這個範例示範如何建立不安全的中繼資料發行端點。 未經驗證的匿名使用者可能可以使用這類端點，所以部署前必須小心謹慎，才能確保公開服務中繼資料是否適切。 如需保護中繼資料端點的範例, 請參閱[自訂安全中繼資料端點](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md)範例。  
  
 此範例是以`ICalculator`執行服務合約的[消費者入門](../../../../docs/framework/wcf/samples/getting-started-sample.md)為基礎。 在這個範例中，用戶端是主控台應用程式 (.exe)，而服務則是由網際網路資訊服務 (IIS) 所裝載。  
  
> [!NOTE]
> 此範例的安裝程序與建置指示位於本主題的結尾。  
  
 為了讓服務公開中繼資料，服務上必須設定 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>。 當這個行為存在時，您便可以發行中繼資料，方法是將端點設定成將 <xref:System.ServiceModel.Description.IMetadataExchange> 合約當做 WS-MetadataExchange (MEX) 通訊協定的實作來進行公開。 為了方便起見，這個合約已經被指定成縮寫組態名稱，"IMetadataExchange"。 這個範例會使用 `mexHttpBinding`，這個快捷標準繫結等同於安全性模式設為 `wsHttpBinding` 的 `None`。 "Mex"的相對位址用於端點中，當解析服務基底位址的端點位址 `http://localhost/servicemodelsamples/service.svc/mex` 。 此行為組態列出如下：  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      <!-- The serviceMetadata behavior publishes metadata through   
           the IMetadataExchange contract. When this behavior is   
           present, you can expose this contract through an endpoint   
           as shown below. Setting httpGetEnabled to true publishes   
           the service's WSDL at the <baseaddress>?wsdl, for example,  
           http://localhost/servicemodelsamples/service.svc?wsdl -->  
      <serviceMetadata httpGetEnabled="True"/>  
      <serviceDebug includeExceptionDetailInFaults="False" />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 此 MEX 端點列出如下。  
  
```xml  
<!-- the MEX endpoint is exposed at   
     http://localhost/servicemodelsamples/service.svc/mex   
     To expose the IMetadataExchange contract, you   
     must enable the serviceMetadata behavior as demonstrated                           
     previously. -->  
<endpoint address="mex"  
          binding="mexHttpBinding"  
          contract="IMetadataExchange" />  
```  
  
 這個範例會將 <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> 屬性設定為 `true`，也會使用 HTTP GET 公開服務的中繼資料。 若要啟用 HTTP GET 中繼資料端點，服務必須有 HTTP 基底位址。 查詢字串 `?wsdl` 會用於服務的基底位址上，以便存取中繼資料。 例如, 若要在網頁瀏覽器中查看服務的 WSDL, 您會使用位址`http://localhost/servicemodelsamples/service.svc?wsdl`。 此外，您可以將 <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> 設定為 `true`，以便使用這個行為來透過 HTTPS 公開中繼資料。 這個作業需要 HTTPS 基底位址。  
  
 若要存取服務的 MEX 端點, 請使用[System.servicemodel 中繼資料公用程式工具 (Svcutil .exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)。  
  
 `svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /out:generatedClient.cs`  
  
 這樣便會產生以該服務中繼資料為基礎的用戶端。  
  
 若要使用 HTTP GET 來存取服務的中繼資料, 請將`http://localhost/servicemodelsamples/service.svc?wsdl`瀏覽器指向。  
  
 如果您移除這項行為並嘗試開啟服務，這時會發生例外狀況。 這個錯誤的發生原因是如果不使用這項行為，透過 `IMetadataExchange` 合約設定的端點就不會有任何實作。  
  
 如果將 `HttpGetEnabled` 設定為 `false`，您就會看到 CalculatorService 說明網頁而不是服務的中繼資料。  
  
### <a name="to-set-up-build-and-run-the-sample"></a>若要安裝、建置及執行範例  
  
1. 請確定您已[針對 Windows Communication Foundation 範例執行一次安裝程式](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。  
  
2. 若要建置方案的 C# 或 Visual Basic .NET 版本，請遵循 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)中的指示。  
  
3. 若要在單一或跨電腦設定中執行範例, 請遵循執行[Windows Communication Foundation 範例](../../../../docs/framework/wcf/samples/running-the-samples.md)中的指示。  
  
> [!IMPORTANT]
> 這些範例可能已安裝在您的電腦上。 請先檢查下列 (預設) 目錄，然後再繼續。  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> 如果此目錄不存在, 請移至[.NET Framework 4 的 Windows Communication Foundation (wcf) 和 Windows Workflow Foundation (WF) 範例](https://go.microsoft.com/fwlink/?LinkId=150780), 以下載所有 Windows Communication Foundation (wcf) [!INCLUDE[wf1](../../../../includes/wf1-md.md)]和範例。 此範例位於下列目錄。  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\Metadata`  
