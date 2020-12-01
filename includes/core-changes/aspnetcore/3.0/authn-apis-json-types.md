---
ms.openlocfilehash: 9bdfcca2fd03e24a636be3340f5057dc3f39358e
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032733"
---
### <a name="authentication-newtonsoftjson-types-replaced"></a>Autenticación: se han reemplazado los tipos Newtonsoft.Json

En ASP.NET Core 3.0, los tipos de `Newtonsoft.Json` utilizados en las API de autenticación se han reemplazado por tipos de `System.Text.Json`. Excepto en los casos siguientes, el uso básico de los paquetes de autenticación no se ve afectado:

* Clases que se derivan de los proveedores de OAuth, como las de [aspnet-contrib](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers).
* Implementaciones avanzadas de manipulación de notificaciones.

Para obtener más información, consulte [dotnet/aspnetcore#7105](https://github.com/dotnet/aspnetcore/pull/7105). Para obtener información, vea [dotnet/aspnetcore#7289](https://github.com/dotnet/aspnetcore/issues/7289).

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="recommended-action"></a>Acción recomendada

En el caso de las implementaciones de OAuth derivadas, el cambio más común es reemplazar `JObject.Parse` por `JsonDocument.Parse` en la invalidación `CreateTicketAsync`, tal como se muestra [aquí](https://github.com/dotnet/aspnetcore/pull/7105/files?utf8=%E2%9C%93&diff=unified&w=1#diff-e1c9f9740a6fe8021020a6f249c589b0L40). `JsonDocument` implementa `IDisposable`.

En la lista siguiente se describen los cambios conocidos:

- <xref:Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimAction.Run(Newtonsoft.Json.Linq.JObject,System.Security.Claims.ClaimsIdentity,System.String)?displayProperty=nameWithType> se convierte en `ClaimAction.Run(JsonElement userData, ClaimsIdentity identity, string issuer)`. Todas las implementaciones derivadas de `ClaimAction` se ven afectadas de manera similar.
- <xref:Microsoft.AspNetCore.Authentication.ClaimActionCollectionMapExtensions.MapCustomJson(Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimActionCollection,System.String,System.Func{Newtonsoft.Json.Linq.JObject,System.String})?displayProperty=nameWithType> se convierte en `MapCustomJson(this ClaimActionCollection collection, string claimType, Func<JsonElement, string> resolver)`.
- <xref:Microsoft.AspNetCore.Authentication.ClaimActionCollectionMapExtensions.MapCustomJson(Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimActionCollection,System.String,System.String,System.Func{Newtonsoft.Json.Linq.JObject,System.String})?displayProperty=nameWithType> se convierte en `MapCustomJson(this ClaimActionCollection collection, string claimType, string valueType, Func<JsonElement, string> resolver)`.
- Ha habido un constructor anterior de <xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthCreatingTicketContext> que se ha quitado y otro que ha reemplazado `JObject` por `JsonElement`. La propiedad `User` y el método `RunClaimActions` se han actualizado para que coincidan.
- <xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthTokenResponse.Success(Newtonsoft.Json.Linq.JObject)> ahora acepta un parámetro de tipo `JsonDocument` en lugar de `JObject`. La propiedad `Response` se ha actualizado para que coincida. `OAuthTokenResponse` ahora es descartable y se eliminará mediante `OAuthHandler`. Las implementaciones de OAuth derivadas que invalidan `ExchangeCodeAsync` no necesitan desechar `JsonDocument` o `OAuthTokenResponse`.
- <xref:Microsoft.AspNetCore.Authentication.OpenIdConnect.UserInformationReceivedContext.User?displayProperty=nameWithType> ha cambiado de `JObject` a `JsonDocument`.
- <xref:Microsoft.AspNetCore.Authentication.Twitter.TwitterCreatingTicketContext.User?displayProperty=nameWithType> ha cambiado de `JObject` a `JsonElement`.
- El último parámetro de [TwitterHandler.CreateTicketAsync(ClaimsIdentity,AuthenticationProperties,AccessToken,JObject)](/dotnet/api/microsoft.aspnetcore.authentication.twitter.twitterhandler.createticketasync?view=aspnetcore-2.2#Microsoft_AspNetCore_Authentication_Twitter_TwitterHandler_CreateTicketAsync_System_Security_Claims_ClaimsIdentity_Microsoft_AspNetCore_Authentication_AuthenticationProperties_Microsoft_AspNetCore_Authentication_Twitter_AccessToken_Newtonsoft_Json_Linq_JObject_) se ha cambiado de `JObject` a `JsonElement`. El método de reemplazo es <xref:Microsoft.AspNetCore.Authentication.Twitter.TwitterHandler.CreateTicketAsync(System.Security.Claims.ClaimsIdentity,Microsoft.AspNetCore.Authentication.AuthenticationProperties,Microsoft.AspNetCore.Authentication.Twitter.AccessToken,System.Text.Json.JsonElement)?displayProperty=nameWithType>.

#### <a name="category"></a>Categoría

ASP.NET Core

#### <a name="affected-apis"></a>API afectadas

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
