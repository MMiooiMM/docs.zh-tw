---
title: <serviceAuthorization> 項目
ms.date: 03/30/2017
ms.assetid: 18cddad5-ddcb-4839-a0ac-1d6f6ab783ca
ms.openlocfilehash: f476f754a340f52859be2986e42754cba0ef3771
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/03/2019
ms.locfileid: "71834015"
---
# <a name="serviceauthorization-element"></a>@no__t 0serviceAuthorization > 元素

指定設定，這些設定會將存取權授權給服務作業。

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)\
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<behaviors >** ](behaviors.md)\
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[ **\<serviceBehaviors >** ](servicebehaviors.md)\
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7[ **&nbsp;0behavior >** ](behavior-of-servicebehaviors.md)1
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7 @ no__t-8 @ no__t-9 **&nbsp;1serviceAuthorization >**  

## <a name="syntax"></a>語法

```xml
<serviceAuthorization impersonateCallerForAllOperations="Boolean"
                      principalPermissionMode="None/UseWindowsGroups/UseAspNetRoles/Custom"
                      roleProviderName="String"
                      serviceAuthorizationManagerType="String">
  <authorizationPolicies>
    <add policyType="String" />
  </authorizationPolicies>
</serviceAuthorization>
```

## <a name="attributes-and-elements"></a>屬性和元素

下列各節說明屬性、子項目和父元素：

### <a name="attributes"></a>屬性

|屬性|描述|  
|---------------|-----------------|  
|impersonateCallerForAllOperations|布林值，指定服務中所有作業是否都模擬呼叫端。 預設為 `false`。<br /><br /> 當特定服務作業模擬呼叫端時，執行緒內容會在執行指定的服務之前切換為呼叫端內容。|  
|principalPermissionMode|設定用於在伺服器上執行作業的原則。 包括下列值：<br /><br /> -無<br />-UseWindowsGroups<br />-   UseAspNetRoles<br />-Custom<br /><br /> 預設值為 UseWindowsGroups。 此值的型別為 <xref:System.ServiceModel.Description.PrincipalPermissionMode>。 如需使用此屬性的詳細資訊，請參閱 [How to：使用 PrincipalPermissionAttribute 類別 @ no__t-0 來限制存取。|  
|roleProviderName|字串，指定角色提供者的名稱，它會提供 Windows Communication Foundation (WCF) 應用程式的角色資訊。 預設值是空字串。|  
|ServiceAuthorizationManagerType|字串，其中包含服務授權管理員的型別。 如需詳細資訊，請參閱<xref:System.ServiceModel.ServiceAuthorizationManager>。|  

### <a name="child-elements"></a>子元素

|元素|描述|  
|-------------|-----------------|  
|authorizationPolicies|包含授權原則型別的集合，使用 `add` 關鍵字可加入這些型別。 每個授權原則包含一個必要的 `policyType` 屬性字串。 該屬性會指定授權原則，可讓一組輸入宣告轉換成另一組宣告。 它可以做為授與或拒絕存取控制 (Access Control) 的基礎。 如需詳細資訊，請參閱<xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>。|  

### <a name="parent-elements"></a>父元素

|元素|描述|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|包含服務行為之設定的集合。|  

## <a name="remarks"></a>備註

本章節包含會影響授權的項目、自訂的角色提供者，以及模擬。  
  
`principalPermissionMode` 屬性會指定要在授權使用保護的方法時使用的使用者群組。 預設值為 `UseWindowsGroups`，其指定了在 Windows 群組 (例如 "Administrators" 或 "Users") 中搜尋嘗試存取資源的身分識別。 您也可以指定 `UseAspNetRoles`，以使用在 \<system. web > 元素下設定的自訂角色提供者，如下列程式碼所示：

```xml
<system.web>
  <membership defaultProvider="SqlProvider"
              userIsOnlineTimeWindow="15">
    <providers>
      <clear />
      <add name="SqlProvider"
           type="System.Web.Security.SqlMembershipProvider"
           connectionStringName="SqlConn"
           applicationName="MembershipProvider"
           enablePasswordRetrieval="false"
           enablePasswordReset="false"
           requiresQuestionAndAnswer="false"
           requiresUniqueEmail="true"
           passwordFormat="Hashed" />
    </providers>
  </membership>
  <!-- Other configuration code not shown. -->
</system.web>
```
  
下列程式碼顯示搭配 `principalPermissionMode` 屬性使用的 `roleProviderName`：
  
```xml
<behaviors>
  <behavior name="ServiceBehaviour">
    <serviceAuthorization principalPermissionMode ="UseAspNetRoles"
                          roleProviderName ="SqlProvider" />
  </behavior>
  <!-- Other configuration code not shown. -->
</behaviors>
```

如需使用此 configuration 元素的詳細範例，請參閱[授權存取服務作業](../../../wcf/samples/authorizing-access-to-service-operations.md)和[授權原則](../../../wcf/samples/authorization-policy.md)。
  
## <a name="see-also"></a>另請參閱

- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- [安全性行為](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [授權存取服務作業](../../../wcf/samples/authorizing-access-to-service-operations.md)
- [如何：為服務建立自訂授權管理員 @ no__t-0
- [如何：使用 PrincipalPermissionAttribute 類別來限制存取 @ no__t-0
- [授權原則](../../../wcf/samples/authorization-policy.md)
