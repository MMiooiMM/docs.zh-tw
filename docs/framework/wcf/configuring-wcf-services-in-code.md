---
title: 在程式碼中設定 WCF 服務
ms.date: 03/30/2017
ms.assetid: 193c725d-134f-4d31-a8f8-4e575233bff6
ms.openlocfilehash: c6bcf08511470d28e1087108d95e477683b0338b
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320636"
---
# <a name="configuring-wcf-services-in-code"></a>在程式碼中設定 WCF 服務
Windows Communication Foundation （WCF）可讓開發人員使用設定檔或程式碼來設定服務。  當服務需要在部署後進行設定時，組態檔非常有用。 使用組態檔時，IT 專業人員只需更新組態檔，不必重新編譯。 但是組態檔可能會很複雜而難以維護。 由於不支援組態檔偵錯，而且組態項目是以名稱來參考，這使得製作組態檔容易出錯且難度增加。 WCF 也可以讓您在程式碼中設定服務。 在舊版的 WCF （4.0 和更早版本）中，您可以輕鬆地在自我裝載的案例中設定程式碼中的服務，<xref:System.ServiceModel.ServiceHost> 類別可讓您在呼叫 ServiceHost 之前設定端點和行為。開啟。 但是在 Web 裝載案例中，您就無法直接存取 <xref:System.ServiceModel.ServiceHost> 類別。 為了設定 Web 裝載服務，您需要建立會建立 `System.ServiceModel.ServiceHostFactory` 的 <xref:System.ServiceModel.Activation.ServiceHostFactory>，並執行任何所需的設定。 從 .NET 4.5 開始，WCF 提供更簡單的方式，在程式碼中設定自我裝載和 web 裝載的服務。  
  
## <a name="the-configure-method"></a>Configure 方法  
 只需定義名為 `Configure` 的公用靜態方法，並在您的服務實作類別中包含下列簽章：  
  
```csharp  
public static void Configure(ServiceConfiguration config)  
```  
  
 Configure 方法接受可讓開發人員加入端點和行為的 <xref:System.ServiceModel.ServiceConfiguration> 執行個體。 在開啟服務主機之前，WCF 會呼叫這個方法。 一旦定義之後，將會忽略 app.config 或 web.config 檔案中指定的任何服務組態設定。  
  
 下列程式碼片段說明如何定義 `Configure` 方法，以及加入服務端點、端點行為和服務行為：  
  
```csharp  
public class Service1 : IService1  
    {  
        public static void Configure(ServiceConfiguration config)  
        {  
            ServiceEndpoint se = new ServiceEndpoint(new ContractDescription("IService1"), new BasicHttpBinding(), new EndpointAddress("basic"));  
            se.Behaviors.Add(new MyEndpointBehavior());  
            config.AddServiceEndpoint(se);  
  
            config.Description.Behaviors.Add(new ServiceMetadataBehavior { HttpGetEnabled = true });  
            config.Description.Behaviors.Add(new ServiceDebugBehavior { IncludeExceptionDetailInFaults = true });  
        }  
  
        public string GetData(int value)  
        {  
            return $"You entered: {value}";
        }  
  
        public CompositeType GetDataUsingDataContract(CompositeType composite)  
        {  
            if (composite == null)  
            {  
                throw new ArgumentNullException("composite");  
            }  
            if (composite.BoolValue)  
            {  
                composite.StringValue += "Suffix";  
            }  
            return composite;  
        }  
    }  
```  
  
 若要為服務啟用通訊協定 (例如 https)，您可以明確加入使用該通訊協定的端點，或是呼叫 ServiceConfiguration.EnableProtocol(Binding) 以自動加入端點，也就是自動為每個與通訊協定相容的基底位址 (Base Address) 及所定義的每份服務合約加入端點。 下列程式碼示範如何使用 ServiceConfiguration.EnableProtocol 方法：  
  
```csharp  
public class Service1 : IService1   
{   
    public string GetData(int value);   
    public static void Configure(ServiceConfiguration config)   
    {   
        // Enable "Add Service Reference" support   
       config.Description.Behaviors.Add( new ServiceMetadataBehavior { HttpGetEnabled = true });   
       // set up support for http, https, net.tcp, net.pipe   
       config.EnableProtocol(new BasicHttpBinding());   
       config.EnableProtocol(new BasicHttpBinding());   
       config.EnableProtocol(new NetTcpBinding());   
       config.EnableProtocol(new NetNamedPipeBinding());   
       // add an extra BasicHttpBinding endpoint at http:///basic   
       config.AddServiceEndpoint(typeof(IService1), new BasicHttpBinding(),"basic");   
    }   
}   
```  
  
 < @No__t_0 > 區段中的設定僅適用于未以程式設計方式將應用程式端點新增至 <xref:System.ServiceModel.ServiceConfiguration> 時。您可以選擇性地從預設應用程式佈建檔載入服務設定，方法是呼叫 <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A>，然後變更設定。 <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration> 類別也允許您從集中式組態載入組態。 下列程式碼說明如何實作此作業：  
  
```csharp
public class Service1 : IService1   
{   
    public void DoWork();   
    public static void Configure(ServiceConfiguration config)   
    {   
          config.LoadFromConfiguration(ConfigurationManager.OpenMappedExeConfiguration(new ExeConfigurationFileMap { ExeConfigFilename = @"c:\sharedConfig\MyConfig.config" }, ConfigurationUserLevel.None));   
    }   
}  
```  
  
> [!IMPORTANT]
> 請注意，<xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A> 會忽略 < `service` > < 標記內的 < `host` > 設定。 在概念上，< `host` > 是關於主機設定，而不是服務設定，它會在 Configure 方法執行之前載入。  
  
## <a name="see-also"></a>請參閱

- [使用設定檔設定服務](configuring-services-using-configuration-files.md)
- [設定用戶端行為](configuring-client-behaviors.md)
- [簡化設定](simplified-configuration.md)
- [組態](./samples/configuration-sample.md)
- [IIS 和 WAS 中以組態為基礎的啟用](./feature-details/configuration-based-activation-in-iis-and-was.md)
- [組態與中繼資料支援](./extending/configuration-and-metadata-support.md)
- [組態](./diagnostics/exceptions-reference/configuration.md)
- [如何：在設定中指定服務繫結](how-to-specify-a-service-binding-in-configuration.md)
- [如何：在組態中建立服務端點](./feature-details/how-to-create-a-service-endpoint-in-configuration.md)
- [如何：使用組態檔發行服務的中繼資料](./feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [如何：在設定中指定用戶端繫結](how-to-specify-a-client-binding-in-configuration.md)
