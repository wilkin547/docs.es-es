---
ms.openlocfilehash: ad451329d7b9ec15bc8b3c49159346d79944d692
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2019
ms.locfileid: "72393981"
---
### <a name="authentication-newtonsoftjson-types-replaced"></a><span data-ttu-id="a4cb5-101">Autenticación: se han reemplazado los tipos Newtonsoft.Json</span><span class="sxs-lookup"><span data-stu-id="a4cb5-101">Authentication: Newtonsoft.Json types replaced</span></span>

<span data-ttu-id="a4cb5-102">En ASP.NET Core 3.0, los tipos de `Newtonsoft.Json` utilizados en las API de autenticación se han reemplazado por tipos de `System.Text.Json`.</span><span class="sxs-lookup"><span data-stu-id="a4cb5-102">In ASP.NET Core 3.0, `Newtonsoft.Json` types used in Authentication APIs have been replaced with `System.Text.Json` types.</span></span> <span data-ttu-id="a4cb5-103">Excepto en los casos siguientes, el uso básico de los paquetes de autenticación no se ve afectado:</span><span class="sxs-lookup"><span data-stu-id="a4cb5-103">Except for the following cases, basic usage of the Authentication packages remains unaffected:</span></span>

* <span data-ttu-id="a4cb5-104">Clases que se derivan de los proveedores de OAuth, como las de [aspnet-contrib](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers).</span><span class="sxs-lookup"><span data-stu-id="a4cb5-104">Classes derived from the OAuth providers, such as those from [aspnet-contrib](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers).</span></span>
* <span data-ttu-id="a4cb5-105">Implementaciones avanzadas de manipulación de notificaciones.</span><span class="sxs-lookup"><span data-stu-id="a4cb5-105">Advanced claim manipulation implementations.</span></span>

<span data-ttu-id="a4cb5-106">Para obtener más información, consulte [aspnet/AspNetCore#7105](https://github.com/aspnet/AspNetCore/pull/7105).</span><span class="sxs-lookup"><span data-stu-id="a4cb5-106">For more information, see [aspnet/AspNetCore#7105](https://github.com/aspnet/AspNetCore/pull/7105).</span></span> <span data-ttu-id="a4cb5-107">También puede consultar [aspnet/AspNetCore#7289](https://github.com/aspnet/AspNetCore/issues/7289).</span><span class="sxs-lookup"><span data-stu-id="a4cb5-107">For discussion, see [aspnet/AspNetCore#7289](https://github.com/aspnet/AspNetCore/issues/7289).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="a4cb5-108">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="a4cb5-108">Version introduced</span></span>

<span data-ttu-id="a4cb5-109">3.0</span><span class="sxs-lookup"><span data-stu-id="a4cb5-109">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a4cb5-110">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="a4cb5-110">Recommended action</span></span>

<span data-ttu-id="a4cb5-111">En el caso de las implementaciones de OAuth derivadas, el cambio más común es reemplazar `JObject.Parse` por `JsonDocument.Parse` en la invalidación `CreateTicketAsync`, tal como se muestra [aquí](https://github.com/aspnet/AspNetCore/pull/7105/files?utf8=%E2%9C%93&diff=unified&w=1#diff-e1c9f9740a6fe8021020a6f249c589b0L40).</span><span class="sxs-lookup"><span data-stu-id="a4cb5-111">For derived OAuth implementations, the most common change is to replace `JObject.Parse` with `JsonDocument.Parse` in the `CreateTicketAsync` override as shown [here](https://github.com/aspnet/AspNetCore/pull/7105/files?utf8=%E2%9C%93&diff=unified&w=1#diff-e1c9f9740a6fe8021020a6f249c589b0L40).</span></span> <span data-ttu-id="a4cb5-112">`JsonDocument` implementa `IDisposable`.</span><span class="sxs-lookup"><span data-stu-id="a4cb5-112">`JsonDocument` implements `IDisposable`.</span></span>

<span data-ttu-id="a4cb5-113">En la lista siguiente se describen los cambios conocidos:</span><span class="sxs-lookup"><span data-stu-id="a4cb5-113">The following list outlines known changes:</span></span>

- <span data-ttu-id="a4cb5-114"><xref:Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimAction.Run(Newtonsoft.Json.Linq.JObject,System.Security.Claims.ClaimsIdentity,System.String)?displayProperty=nameWithType> se convierte en `ClaimAction.Run(JsonElement userData, ClaimsIdentity identity, string issuer)`.</span><span class="sxs-lookup"><span data-stu-id="a4cb5-114"><xref:Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimAction.Run(Newtonsoft.Json.Linq.JObject,System.Security.Claims.ClaimsIdentity,System.String)?displayProperty=nameWithType> becomes `ClaimAction.Run(JsonElement userData, ClaimsIdentity identity, string issuer)`.</span></span> <span data-ttu-id="a4cb5-115">Todas las implementaciones derivadas de `ClaimAction` se ven afectadas de manera similar.</span><span class="sxs-lookup"><span data-stu-id="a4cb5-115">All derived implementations of `ClaimAction` are similarly affected.</span></span>
- <span data-ttu-id="a4cb5-116"><xref:Microsoft.AspNetCore.Authentication.ClaimActionCollectionMapExtensions.MapCustomJson(Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimActionCollection,System.String,System.Func{Newtonsoft.Json.Linq.JObject,System.String})?displayProperty=nameWithType> se convierte en `MapCustomJson(this ClaimActionCollection collection, string claimType, Func<JsonElement, string> resolver)`</span><span class="sxs-lookup"><span data-stu-id="a4cb5-116"><xref:Microsoft.AspNetCore.Authentication.ClaimActionCollectionMapExtensions.MapCustomJson(Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimActionCollection,System.String,System.Func{Newtonsoft.Json.Linq.JObject,System.String})?displayProperty=nameWithType> becomes `MapCustomJson(this ClaimActionCollection collection, string claimType, Func<JsonElement, string> resolver)`</span></span>
- <span data-ttu-id="a4cb5-117"><xref:Microsoft.AspNetCore.Authentication.ClaimActionCollectionMapExtensions.MapCustomJson(Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimActionCollection,System.String,System.String,System.Func{Newtonsoft.Json.Linq.JObject,System.String})?displayProperty=nameWithType> se convierte en `MapCustomJson(this ClaimActionCollection collection, string claimType, string valueType, Func<JsonElement, string> resolver)`</span><span class="sxs-lookup"><span data-stu-id="a4cb5-117"><xref:Microsoft.AspNetCore.Authentication.ClaimActionCollectionMapExtensions.MapCustomJson(Microsoft.AspNetCore.Authentication.OAuth.Claims.ClaimActionCollection,System.String,System.String,System.Func{Newtonsoft.Json.Linq.JObject,System.String})?displayProperty=nameWithType> becomes `MapCustomJson(this ClaimActionCollection collection, string claimType, string valueType, Func<JsonElement, string> resolver)`</span></span>
- <span data-ttu-id="a4cb5-118">Ha habido un constructor anterior de <xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthCreatingTicketContext> que se ha quitado y otro que ha reemplazado `JObject` por `JsonElement`.</span><span class="sxs-lookup"><span data-stu-id="a4cb5-118"><xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthCreatingTicketContext> has had one old constructor removed and the other replaced `JObject` with `JsonElement`.</span></span> <span data-ttu-id="a4cb5-119">La propiedad `User` y el método `RunClaimActions` se han actualizado para que coincidan.</span><span class="sxs-lookup"><span data-stu-id="a4cb5-119">The `User` property and `RunClaimActions` method have been updated to match.</span></span>
- <span data-ttu-id="a4cb5-120"><xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthTokenResponse.Success(Newtonsoft.Json.Linq.JObject)> ahora acepta un parámetro de tipo `JsonDocument` en lugar de `JObject`.</span><span class="sxs-lookup"><span data-stu-id="a4cb5-120"><xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthTokenResponse.Success(Newtonsoft.Json.Linq.JObject)> now accepts a parameter of type `JsonDocument` instead of `JObject`.</span></span> <span data-ttu-id="a4cb5-121">La propiedad `Response` se ha actualizado para que coincida.</span><span class="sxs-lookup"><span data-stu-id="a4cb5-121">The `Response` property has been updated to match.</span></span> <span data-ttu-id="a4cb5-122">`OAuthTokenResponse` ahora es descartable y se eliminará mediante `OAuthHandler`.</span><span class="sxs-lookup"><span data-stu-id="a4cb5-122">`OAuthTokenResponse` is now disposable and will be disposed by `OAuthHandler`.</span></span> <span data-ttu-id="a4cb5-123">Las implementaciones de OAuth derivadas que invalidan `ExchangeCodeAsync` no necesitan desechar `JsonDocument` o `OAuthTokenResponse`.</span><span class="sxs-lookup"><span data-stu-id="a4cb5-123">Derived OAuth implementations overriding `ExchangeCodeAsync` don't need to dispose the `JsonDocument` or `OAuthTokenResponse`.</span></span>
- <span data-ttu-id="a4cb5-124"><xref:Microsoft.AspNetCore.Authentication.OpenIdConnect.UserInformationReceivedContext.User?displayProperty=nameWithType> ha cambiado de `JObject` a `JsonDocument`.</span><span class="sxs-lookup"><span data-stu-id="a4cb5-124"><xref:Microsoft.AspNetCore.Authentication.OpenIdConnect.UserInformationReceivedContext.User?displayProperty=nameWithType> changed from `JObject` to `JsonDocument`.</span></span>
- <span data-ttu-id="a4cb5-125"><xref:Microsoft.AspNetCore.Authentication.Twitter.TwitterCreatingTicketContext.User?displayProperty=nameWithType> ha cambiado de `JObject` a `JsonElement`.</span><span class="sxs-lookup"><span data-stu-id="a4cb5-125"><xref:Microsoft.AspNetCore.Authentication.Twitter.TwitterCreatingTicketContext.User?displayProperty=nameWithType> changed from `JObject` to `JsonElement`.</span></span>
- <span data-ttu-id="a4cb5-126"><xref:Microsoft.AspNetCore.Authentication.Twitter.TwitterHandler.CreateTicketAsync(System.Security.Claims.ClaimsIdentity,Microsoft.AspNetCore.Authentication.AuthenticationProperties,Microsoft.AspNetCore.Authentication.Twitter.AccessToken,Newtonsoft.Json.Linq.JObject)?displayProperty=nameWithType> ha cambiado de aceptar `JObject` a `JsonElement`.</span><span class="sxs-lookup"><span data-stu-id="a4cb5-126"><xref:Microsoft.AspNetCore.Authentication.Twitter.TwitterHandler.CreateTicketAsync(System.Security.Claims.ClaimsIdentity,Microsoft.AspNetCore.Authentication.AuthenticationProperties,Microsoft.AspNetCore.Authentication.Twitter.AccessToken,Newtonsoft.Json.Linq.JObject)?displayProperty=nameWithType> changed from accepting `JObject` to `JsonElement`.</span></span>

#### <a name="category"></a><span data-ttu-id="a4cb5-127">Categoría</span><span class="sxs-lookup"><span data-stu-id="a4cb5-127">Category</span></span>

<span data-ttu-id="a4cb5-128">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="a4cb5-128">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a4cb5-129">API afectadas</span><span class="sxs-lookup"><span data-stu-id="a4cb5-129">Affected APIs</span></span>

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
