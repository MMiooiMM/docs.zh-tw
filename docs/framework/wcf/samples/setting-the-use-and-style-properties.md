---
title: 設定 Use 和 Style 屬性-WCF 範例
ms.date: 03/30/2017
ms.assetid: c09a0600-116f-41cf-900a-1b7e4ea4e300
ms.openlocfilehash: 946f8f6aab253eb881faaba7adfdc68dc54d7f0b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2019
ms.locfileid: "69958808"
---
# <a name="setting-the-use-and-style-properties"></a>設定 Use 與 Style 屬性

這個範例會示範如何在 <xref:System.ServiceModel.XmlSerializerFormatAttribute> 和 <xref:System.ServiceModel.DataContractFormatAttribute> 上使用 Use 和 Style 屬性。 這些屬性會影響訊息的格式化方式。 根據預設，會以設為 <xref:System.ServiceModel.OperationFormatStyle.Document> 的樣式來格式化訊息本文。 這些設定可以指定於服務合約層級或作業合約層級。

> [!NOTE]
> 此範例的安裝程序與建置指示位於本主題的結尾。

<xref:System.ServiceModel.DataContractFormatAttribute.Style%2A> 樣式屬性會判斷該服務之 WSDL 中繼資料格式化的方式。 可能的值為 <xref:System.ServiceModel.OperationFormatStyle.Document> 和 <xref:System.ServiceModel.OperationFormatStyle.Rpc>。 RPC 表示為某個作業交換之訊息的 WSDL 表示法，如同遠端程序呼叫一般含有參數。 下列為範例。

```xml
<wsdl:message name="IUseAndStyleCalculator_Add_InputMessage">
  <wsdl:part name="n1" type="xsd:double"/>
  <wsdl:part name="n2" type="xsd:double"/>
</wsdl:message>
```

將樣式設為 <xref:System.ServiceModel.OperationFormatStyle.Document> 代表 WSDL 表示法含有一個代表文件的項目，此文件會為某作業進行交換，如以下範例所示。

```xml
<wsdl:message name="IUseAndStyleCalculator_Add_InputMessage">
  <wsdl:part name="parameters" element="tns:Add"/>
</wsdl:message>
```

<xref:System.ServiceModel.XmlSerializerFormatAttribute.Use%2A> 屬性會決定訊息的格式。 可能的值為 <xref:System.ServiceModel.OperationFormatUse.Literal> 和 <xref:System.ServiceModel.OperationFormatUse.Encoded>；預設值為 <xref:System.ServiceModel.OperationFormatUse.Literal>。 Literal 表示訊息是 WSDL 中結構描述的常值 (Literal) 執行個體，如下列 Document/Literal 範例所示。

```xml
<Add xmlns="http://Microsoft.ServiceModel.Samples">
  <n1>100</n1>
  <n2>15.99</n2>
</Add>
```

Encoded 表示 WSDL 中的結構描述是根據 SOAP 1.1 第 5 節的規則編碼的抽象規格。 下列式 RPC/Encoded 的範例。

```xml
<q1:Add xmlns:q1="http://Microsoft.ServiceModel.Samples">
  <n1 xsi:type="xsd:double" xmlns="">100</n1>
  <n2 xsi:type="xsd:double" xmlns="">15.99</n2>
</q1:Add>
```

WS-I Basic Profile 1.0 禁止使用 <xref:System.ServiceModel.OperationFormatUse.Encoded>，只有在舊版服務需要時才使用這個項目。 此 `Encoded` 訊息格式只會在使用 XmlSerializer 時才會提供。

為了讓您查看傳送和接收的訊息, 此範例是以[追蹤和訊息記錄](tracing-and-message-logging.md)為基礎。 服務組態與原始程式碼已修改成啟用並利用追蹤以及訊息記錄。 此外，<xref:System.ServiceModel.WSHttpBinding> 已經設定成不使用安全性，因此已記錄的訊息可以用未加密的格式檢視。 您應該使用[服務追蹤檢視器工具 (svctraceviewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md)來查看產生的追蹤記錄檔 (system.servicemodel. E2e 和 Message .log)。 這些追蹤已設定為建立在 C:\LOGS 資料夾中。 先建立資料夾，再執行此範例。 若要在追蹤檢視器工具中查看訊息內容, 請選取工具左側和右側窗格中的 [**訊息**]。

下列程式碼會示範 <xref:System.ServiceModel.XmlSerializerFormatAttribute.Use%2A> 屬性已設為 <xref:System.ServiceModel.OperationFormatUse>，而訊息本文格式已從預設的 <xref:System.ServiceModel.OperationFormatStyle> 變更為 <xref:System.ServiceModel.OperationFormatStyle.Document> 的服務合約。

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples"),
XmlSerializerFormat(Style = OperationFormatStyle.Rpc, 
                                 Use = OperationFormatUse.Encoded)]
public interface IUseAndStyleCalculator
{
    [OperationContract]
    double Add(double n1, double n2);
    [OperationContract]
    double Subtract(double n1, double n2);
    [OperationContract]
    double Multiply(double n1, double n2);
    [OperationContract]
    double Divide(double n1, double n2);
}
```

若要檢視不同 <xref:System.ServiceModel.XmlSerializerFormatAttribute.Use%2A> 和 <xref:System.ServiceModel.XmlSerializerFormatAttribute.Style%2A> 設定之間的差異，請修改服務中的這些設定，接著重新產生用戶端、執行範例，然後使用服務追蹤檢視器工具檢查 c:\logs\message.logs 檔。 藉由檢視也會發現對中繼資料的影響 `http://localhost/ServiceModelSamples/service.svc?wsdl` 。 服務的中繼資料通常會分成好幾頁。 主要的 wsdl 頁面會包含 WSDL 繫結，但是檢視 `http://localhost/ServiceModelSamples/service.svc?wsdl=wsdl0` 来觀察訊息定義。

## <a name="to-set-up-build-and-run-the-sample"></a>若要安裝、建置及執行範例

1. 請確定您已[針對 Windows Communication Foundation 範例執行一次安裝程式](one-time-setup-procedure-for-the-wcf-samples.md)。

2. 建立用於記錄訊息的 C:\LOGS 目錄。 給予使用者這個目錄的網路服務寫入權限。

3. 若要建置方案的 C# 或 Visual Basic .NET 版本，請遵循 [Building the Windows Communication Foundation Samples](building-the-samples.md)中的指示。

4. 若要在單一或跨電腦設定中執行範例, 請遵循執行[Windows Communication Foundation 範例](running-the-samples.md)中的指示。

> [!IMPORTANT]
> 這些範例可能已安裝在您的電腦上。 請先檢查下列 (預設) 目錄，然後再繼續。
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> 如果此目錄不存在, 請移至[.NET Framework 4 的 Windows Communication Foundation (wcf) 和 Windows Workflow Foundation (WF) 範例](https://go.microsoft.com/fwlink/?LinkId=150780), 以下載所有 Windows Communication Foundation (wcf) [!INCLUDE[wf1](../../../../includes/wf1-md.md)]和範例。 此範例位於下列目錄。
> 
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Message\UseAndStyle`
