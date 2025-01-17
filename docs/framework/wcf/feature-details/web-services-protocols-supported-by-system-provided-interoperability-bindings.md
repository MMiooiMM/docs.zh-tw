---
title: 系統提供的互通性繫結所支援的 Web 服務通訊協定
ms.date: 03/30/2017
helpviewer_keywords:
- WS-protocols
- Web services protocols
- Windows Communication Foundation, Web service protocols
ms.assetid: 1f7fc4ff-30fe-4e46-adda-91caad3b06c6
ms.openlocfilehash: 963325604f66ddd4f8470933584b7880c86403bc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2019
ms.locfileid: "69951565"
---
# <a name="web-services-protocols-supported-by-system-provided-interoperability-bindings"></a>系統提供的互通性繫結所支援的 Web 服務通訊協定
Windows Communication Foundation (WCF) 是為了與支援一組稱為 Web 服務規格之規格的 Web 服務交互操作所建立。 為了簡化互通性最佳作法的服務設定, WCF 引進三個互通的系統<xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType>提供<xref:System.ServiceModel.WSHttpBinding?displayProperty=nameWithType>系結<xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType>:、和。 為了與組織互通以進行結構化資訊標準 (OASIS) 標準, WCF 包含一個可互通的系統提供系結<xref:System.ServiceModel.WS2007HttpBinding?displayProperty=nameWithType>:。 針對中繼資料發行, WCF 包含兩種互通的系統提供系結: [ \<mexHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpbinding.md)和[ \<mexHttpsBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpsbinding.md)。 本主題列出系統提供之繫結支援的規格。  
  
## <a name="web-services-protocols-supported-by-basichttpbinding-wshttpbinding-ws2007httpbinding-and-wsdualhttpbinding-bindings"></a>basicHttpBinding、wsHttpBinding、ws2007HttpBinding 和 wsDualHttpBinding 繫結支援的 Web 服務通訊協定  
  
### <a name="all-bindings"></a>所有繫結  
 BasicHttpBinding > [、 wsHttpBinding>\<](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)和[ws2007HttpBinding >系結支援下列通訊協定。\< ](../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) [ \< ](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)  
  
> [!NOTE]
> 如需用於發行中繼資料之繫結的詳細資訊，請參閱本主題中稍後的「系統提供之中繼資料繫結」一節。  
  
|Category|Protocol|規格和用法|  
|--------------|--------------|-----------------------------|  
|Transport|HTTP 1.1|[HTTP 1.1](https://go.microsoft.com/fwlink/?LinkId=84048)<br /><br /> `BasicHttpBinding`、`WSHttpBinding` 和 `WS2007HttpBinding` 使用 HTTP 和 HTTPS 傳輸。|  
|訊息|MTOM|[MTOM](https://go.microsoft.com/fwlink/?LinkId=95326)<br /><br /> `basicHttpBinding`、`wsHttpBinding` 和 `ws2007HttpBinding` 支援訊息傳輸最佳化機制 (MTOM)。 預設不使用。 若要使用 MTOM，請將 `messageEncoding` 屬性設為 `"Mtom"`。<br /><br /> 範例：<br /><br /> `<wsHttpBinding> <binding messageEncoding="Mtom"/> </wsHttpBinding>`|  
|中繼資料|WSDL 1.1|[WSDL 1.1](https://go.microsoft.com/fwlink/?LinkId=94859)<br /><br /> WCF 使用 Web 服務描述語言 (WSDL) 來描述服務。|  
|中繼資料|WS-Policy|[WS-Policy](https://go.microsoft.com/fwlink/?LinkId=94864)<br /><br /> WCF 會使用 WS-Policy 規格搭配定義域特定的判斷提示, 來描述服務需求和功能。|  
|中繼資料|WS-Policy 1.5|[WS-原則1。5](https://go.microsoft.com/fwlink/?LinkId=95327)<br /><br /> WCF 會使用 WS-Policy 規格搭配定義域特定的判斷提示, 來描述服務需求和功能。|  
|中繼資料|WS-PolicyAttachment|[WS-PolicyAttachment](https://go.microsoft.com/fwlink/?LinkId=95328)<br /><br /> WCF 會執行 Ws-policyattachment, 在 Web 服務描述語言 (WSDL) 的各種範圍中附加原則運算式。|  
|中繼資料|WS-MetadataExchange|[WS-MetadataExchange](https://go.microsoft.com/fwlink/?LinkId=94868)<br /><br /> WCF 會執行透過 ws-metadataexchange, 以取得 XML 架構、WSDL 和 WS 原則。|  
  
### <a name="basichttpbinding"></a>basicHttpBinding  
  
|Category|Protocol|規格和用法|  
|--------------|--------------|-----------------------------|  
|訊息|SOAP 1.1|[SOAP 1.1](https://go.microsoft.com/fwlink/?LinkId=90520)<br /><br /> 為了與 Basic Profile 1.1 保持一致，`basicHttpBinding` 項目實作 SOAP 1.1 訊息通訊協定。|  
|安全性|WSS SOAP 訊息安全性 1.0|[WSS SOAP 訊息安全性1。0](https://go.microsoft.com/fwlink/?LinkId=94684)<br /><br /> 為了與 Basic Security Profile 保持一致，`basicHttpBinding` 項目實作 Web 服務安全性 (WSS) SOAP 訊息安全性 1.0 規格，以用於使用者名稱/密碼和 X.509 型的安全性。<br /><br /> `<basicHttpBinding> <binding name="Binding1"> <security mode="TransportWithMessageCredential &#124;                     "Message" .../> </binding> </basicHttpBinding>`|  
|安全性|WSS SOAP 訊息安全性 UsernameToken 設定檔 1.0|[WSS SOAP 訊息安全性 UsernameToken 設定檔1。0](https://go.microsoft.com/fwlink/?LinkId=95334)<br /><br /> `<basicHttpBinding> <binding name="Binding1"> <security mode="TransportWithMessageCredential"> <transport clientCredentialType="Basic"/> </security> </basicHttpBinding>`|  
|安全性|WSS SOAP Message Security x.509 憑證權杖設定檔1。0|[WSS SOAP Message Security x.509 憑證權杖設定檔1。0](https://go.microsoft.com/fwlink/?LinkId=95335)<br /><br /> `<basicHttpBinding>   <security mode="Message"> <message clientCredentialType="Certificate"/> </security> </basicHttpBinding>`|  
  
### <a name="wshttpbinding-ws2007httpbinding-and-wsdualhttpbinding"></a>wsHttpBinding、ws2007HttpBinding 和 wsDualHttpBinding  
  
|Category|Protocol|規格和用法|  
|--------------|--------------|-----------------------------|  
|訊息|SOAP 1.2|[初步](https://go.microsoft.com/fwlink/?LinkId=48282)<br /><br /> [訊息架構](https://go.microsoft.com/fwlink/?LinkId=94664)<br /><br /> [附加 (包括 HTTP 系結)](https://go.microsoft.com/fwlink/?LinkId=95329)|  
|訊息|WS-ADDRESSING 2005/08|[Web 服務定址 1.0-核心](https://go.microsoft.com/fwlink/?LinkId=90574)<br /><br /> [Web 服務定址 1.0-SOAP](https://go.microsoft.com/fwlink/?LinkId=95330)<br /><br /> `wsHttpBinding`、`ws2007HttpBinding` 和 `wsDualHttpBinding` 會實作全球資訊網協會 (W3C) WS-Addressing 建議，以啟用非同步訊息、訊息相互關聯和傳輸中性的定址機制。<br /><br /> 雖然 WS-* 規格允許 WS-Addressing 標頭加密，但是 WCF 並不提供這項支援。|  
|訊息|WS-Addressing 1.0 - 中繼資料|[Ws-addressing 1.0 中繼資料](https://www.w3.org/2007/05/addressing/metadata)若要啟用此通訊協定的支援, 可以藉由設定 ServiceMetadata 行為中的原則版本-將 policyversion 設為 1.2 (預設值), wsdl 描述與 WS-ADDRESSING wsdl 相容, 其中 policyversion 設定為 1.5, wsdl 描述為與 ws-addressing 中繼資料相容。<br /><br /> 雖然 WS-* 規格允許 WS-Addressing 標頭加密，但是 WCF 並不提供這項支援。|  
|安全性|WSS SOAP 訊息安全性 1.0|[WSS SOAP 訊息安全性1。0](https://go.microsoft.com/fwlink/?LinkId=94684)<br /><br /> `securityMode` 屬性設為 "wsSecurityOverHttp" (預設值) 且使用 `wsSecurity` 子項目設定參數時使用。<br /><br /> `<wsHttpBinding>   <binding name="myBinding">      <security mode="Message" .../>   </binding> </wsHttpBinding>`|  
|安全性|WSS SOAP 訊息安全性 UsernameToken 設定檔1。1|[WSS SOAP 訊息安全性 UsernameToken 設定檔1。0](https://go.microsoft.com/fwlink/?LinkId=95331)<br /><br /> `wsSecurity` 項目的 `authenticationMode` 屬性設為 "Username" 時使用。<br /><br /> `<wsHttpBinding>   <binding name="MyBinding">     <security mode="Message>       <message           clientCredentialType="UserName        negotiateServiceCredential="false"        establishSecurityContext="false"/>     </security> </binding> </wsHttpBinding>`|  
|安全性|WSS SOAP 訊息安全性 X.509 憑證權杖設定檔 1.1|[WSS SOAP Message Security x.509 憑證權杖設定檔1。1](https://go.microsoft.com/fwlink/?LinkId=95332)<br /><br /> 用於在 `wsSecurity` 項目的 `authenticationMode` 屬性設為 "Username"、"Certificate" 或 "None" 時保護訊息。 此外，當 `wsSecurity` 項目的 `authenticationMode` 屬性設為 "Certificate" 時，請使用此規格進行用戶端驗證。<br /><br /> `<wsHttpBinding>   <binding name="MyBinding">     <security mode="Message>       <message           clientCredentialType="Certificate"        negotiateServiceCredential="false"        establishSecurityContext="false"/>     </security>   </binding> </wsHttpBinding>`|  
|安全性|WSS SOAP 訊息安全性 Kerberos 權杖設定檔 1.1|[WSS SOAP 訊息安全性 Kerberos 權杖設定檔1。1](https://go.microsoft.com/fwlink/?LinkId=95333)<br /><br /> 用於在 `wsSecurity` 項目的 `authenticationMode` 屬性設為 "Windows" 時進行驗證和保護訊息。<br /><br /> `<wsHttpBinding>   <binding name="MyBinding">     <security mode="Message>       <message           clientCredentialType="Windows"        negotiateServiceCredential="false"        establishSecurityContext="false"/>     </security>   </binding> </wsHttpBinding>`|  
|安全性|WS-SecureConversation|[WS-SecureConversation](https://go.microsoft.com/fwlink/?LinkId=95317)<br /><br /> 用於當 `security/@mode` 屬性設為 "Message"，且 `message/@establishSecurityContext` 屬性設為 "true" (預設值) 時提供安全的工作階段。|  
|安全性|WS-Trust|[WS-Trust](https://go.microsoft.com/fwlink/?LinkId=95318)<br /><br /> WS-SecureConversation (請參閱前述) 所使用。|  
|可信賴傳訊|WS-ReliableMessaging|[WS-ReliableMessaging](https://go.microsoft.com/fwlink/?LinkId=95322)<br /><br /> 當繫結設定為使用 `reliableSession` 時使用。<br /><br /> `<wsHttpBinding>  <binding name="myBinding">    <reliableSession/>   </binding> </wsHttpBinding>`|  
|異動|WS-AtomicTransaction|[WS-AtomicTransaction](https://go.microsoft.com/fwlink/?LinkId=95323)<br /><br /> 用於交易管理員之間的通訊。 WCF 用戶端和服務一律使用本機交易管理員。|  
|異動|WS-Coordination|[WS-Coordination](https://go.microsoft.com/fwlink/?LinkId=95324)<br /><br /> 用於當 `flowTransactions` 屬性設為 "Allowed" 或 "Required" 時流動異動內容。<br /><br /> `<wsHttpBinding>   <binding transactionFlow="true"/> </wsHttpBinding>`|  
  
## <a name="wsfederationhttpbinding-and-ws2007federationhttpbinding"></a>wsFederationHttpBinding 和 ws2007FederationHttpBinding  
 引進了[ \<wsFederationHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)和[ \<ws2007FederationHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md)元素, 以提供同盟案例的支援, 其中協力廠商發出用來驗證用戶端的權杖。 除了 `wsHttpBinding` 使用的通訊協定外，`wsFederationHttpBinding` 還使用：  
  
- `WS-Trust`，進行權杖發行。  
  
- WSS 安全性判斷提示標記語言 (SAML) 權杖設定檔 1.0 和 1.1，適用於最常見的發行權杖格式。  
  
 範例：  
  
```xml  
<wsFederationHttpBinding>  
  <binding name="myBinding">  
     <security mode="Message">  
       <message issuedKeyType="Symmetric"   
                issuedTokenType="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1">  
         <issuerMetadata address =   
         'http://localhost/FederationSample/HomeRealmSTS/STS.svc/mex'>  
       </message>  
     </security>  
  </binding>  
</wsFederationHttpBinding>  
```  
  
 如需詳細資訊, 請參閱[同盟](../../../../docs/framework/wcf/feature-details/federation.md)。  
  
## <a name="system-provided-metadata-bindings"></a>系統提供之中繼資料繫結  
 下表說明系統提供之互通中繼資料繫結所支援的通訊協定，該繫結由 <xref:System.ServiceModel.Description.MetadataExchangeBindings?displayProperty=nameWithType> 類別公開。  
  
### <a name="mexhttpbinding"></a>mexHttpBinding  
 MexHttpBinding > 系結支援下列通訊協定。 [ \< ](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpbinding.md) 如需使用此系結的詳細資訊, 請參閱[發行中繼資料](../../../../docs/framework/wcf/feature-details/publishing-metadata.md)。  
  
|Category|Protocol|規格和用法|  
|--------------|--------------|-----------------------------|  
|Transport|HTTP 1.1|[HTTP 1.1](https://go.microsoft.com/fwlink/?LinkId=84048)|  
|訊息|SOAP 1.2|[初步](https://go.microsoft.com/fwlink/?LinkId=48282)<br /><br /> [訊息架構](https://go.microsoft.com/fwlink/?LinkId=94664)<br /><br /> [附加 (包括 HTTP 系結)](https://go.microsoft.com/fwlink/?LinkId=95329)|  
|訊息|WS-ADDRESSING 2005/08|[Web 服務定址 1.0-核心](https://go.microsoft.com/fwlink/?LinkId=90574)<br /><br /> [Web 服務定址 1.0-SOAP](https://go.microsoft.com/fwlink/?LinkId=95330)|  
|中繼資料|WS-MetadataExchange|[WS-MetadataExchange](https://go.microsoft.com/fwlink/?LinkId=94868)<br /><br /> WCF 會執行透過 ws-metadataexchange, 以取得 XML 架構、WSDL 和 WS 原則。|  
  
### <a name="mexhttpsbinding"></a>mexHttpsBinding  
 mexHttpsBinding > 支援下列通訊協定。 [ \< ](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpsbinding.md) 如需使用此系結的詳細資訊, 請參閱[發行中繼資料](../../../../docs/framework/wcf/feature-details/publishing-metadata.md)。  
  
|Category|Protocol|規格和用法|  
|--------------|--------------|-----------------------------|  
|Transport|HTTP 1.1|[HTTP 1.1](https://go.microsoft.com/fwlink/?LinkId=84048)<br /><br /> 已啟用傳輸安全性。|  
|訊息|SOAP 1.2|[初步](https://go.microsoft.com/fwlink/?LinkId=48282)<br /><br /> [訊息架構](https://go.microsoft.com/fwlink/?LinkId=94664)<br /><br /> [附加 (包括 HTTP 系結)](https://go.microsoft.com/fwlink/?LinkId=95329)|  
|訊息|WS-ADDRESSING 2005/08|[Web 服務定址 1.0-核心](https://go.microsoft.com/fwlink/?LinkId=90574)<br /><br /> [Web 服務定址 1.0-SOAP](https://go.microsoft.com/fwlink/?LinkId=95330)|  
|中繼資料|WS-MetadataExchange|[WS-MetadataExchange](https://go.microsoft.com/fwlink/?LinkId=94868)<br /><br /> WCF 會執行透過 ws-metadataexchange, 以取得 XML 架構、WSDL 和 WS 原則。|  
  
## <a name="see-also"></a>另請參閱

- [系統提供的繫結](../../../../docs/framework/wcf/system-provided-bindings.md)
- [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)
- [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)
- [\<wsDualHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)
- [\<mexHttpsBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpsbinding.md)
- [\<mexHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpbinding.md)
