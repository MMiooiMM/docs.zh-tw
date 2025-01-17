---
ms.openlocfilehash: ad451329d7b9ec15bc8b3c49159346d79944d692
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394255"
---
### <a name="authentication-newtonsoftjson-types-replaced"></a>驗證： Newtonsoft 已取代的 Json 類型

在 ASP.NET Core 3.0 中，驗證 Api 中使用的 `Newtonsoft.Json` 類型已由 `System.Text.Json` 類型所取代。 除了下列情況以外，驗證套件的基本使用方式不會受到影響：

* 衍生自 OAuth 提供者的類別，例如來自[aspnet 的 contrib](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers)。
* Advanced 宣告操作的實施。

如需詳細資訊，請參閱[aspnet/AspNetCore # 7105 in](https://github.com/aspnet/AspNetCore/pull/7105)。 如需討論，請參閱[aspnet/AspNetCore # 7289](https://github.com/aspnet/AspNetCore/issues/7289)。

#### <a name="version-introduced"></a>引進的版本

3.0

#### <a name="recommended-action"></a>建議的動作

針對衍生的 OAuth 執行，最常見的變更是在 `CreateTicketAsync` 覆寫中以 `JsonDocument.Parse` 取代 `JObject.Parse`，[如下所示。](https://github.com/aspnet/AspNetCore/pull/7105/files?utf8=%E2%9C%93&diff=unified&w=1#diff-e1c9f9740a6fe8021020a6f249c589b0L40) `JsonDocument` 會實作 `IDisposable`。

下列清單列出已知的變更：

- <xref:Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimAction.Run(Newtonsoft.Json.Linq.JObject,System.Security.Claims.ClaimsIdentity,System.String)?displayProperty=nameWithType> 會變成 `ClaimAction.Run(JsonElement userData, ClaimsIdentity identity, string issuer)`。 @No__t-0 的所有衍生的實作為同樣的影響。
- <xref:Microsoft.AspNetCore.Authentication.ClaimActionCollectionMapExtensions.MapCustomJson(Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimActionCollection,System.String,System.Func{Newtonsoft.Json.Linq.JObject,System.String})?displayProperty=nameWithType> 會變成 `MapCustomJson(this ClaimActionCollection collection, string claimType, Func<JsonElement, string> resolver)`
- <xref:Microsoft.AspNetCore.Authentication.ClaimActionCollectionMapExtensions.MapCustomJson(Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimActionCollection,System.String,System.String,System.Func{Newtonsoft.Json.Linq.JObject,System.String})?displayProperty=nameWithType> 會變成 `MapCustomJson(this ClaimActionCollection collection, string claimType, string valueType, Func<JsonElement, string> resolver)`
- <xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthCreatingTicketContext> 已移除一個舊的函式，而另一個已使用 `JsonElement` 取代 `JObject`。 @No__t-0 屬性和 @no__t 1 方法已更新為符合。
- <xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthTokenResponse.Success(Newtonsoft.Json.Linq.JObject)> 現在接受類型為 `JsonDocument` 的參數，而不是 `JObject`。 已更新 `Response` 屬性以符合。 `OAuthTokenResponse` 現在可處置，並會由 `OAuthHandler` 處置。 覆寫 `ExchangeCodeAsync` 的衍生 OAuth 部署不需要處置 `JsonDocument` 或 `OAuthTokenResponse`。
- <xref:Microsoft.AspNetCore.Authentication.OpenIdConnect.UserInformationReceivedContext.User?displayProperty=nameWithType> 已從 `JObject` 變更為 `JsonDocument`。
- <xref:Microsoft.AspNetCore.Authentication.Twitter.TwitterCreatingTicketContext.User?displayProperty=nameWithType> 已從 `JObject` 變更為 `JsonElement`。
- <xref:Microsoft.AspNetCore.Authentication.Twitter.TwitterHandler.CreateTicketAsync(System.Security.Claims.ClaimsIdentity,Microsoft.AspNetCore.Authentication.AuthenticationProperties,Microsoft.AspNetCore.Authentication.Twitter.AccessToken,Newtonsoft.Json.Linq.JObject)?displayProperty=nameWithType> 已從接受 `JObject` 變更為 `JsonElement`。

#### <a name="category"></a>分類

ASP.NET Core

#### <a name="affected-apis"></a>受影響的 API

- <xref:Microsoft.AspNetCore.Authentication.Facebook?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Authentication.Google?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Authentication.MicrosoftAccount?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Authentication.OAuth?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Authentication.OpenIdConnect?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Authentication.Twitter?displayProperty=nameWithType>

<!--

#### Affected APIs

- `N:Microsoft.AspNetCore.Authentication.Facebook`
- `N:Microsoft.AspNetCore.Authentication.Google`
- `N:Microsoft.AspNetCore.Authentication.MicrosoftAccount`
- `N:Microsoft.AspNetCore.Authentication.OAuth`
- `N:Microsoft.AspNetCore.Authentication.OpenIdConnect`
- `N:Microsoft.AspNetCore.Authentication.Twitter`

-->
