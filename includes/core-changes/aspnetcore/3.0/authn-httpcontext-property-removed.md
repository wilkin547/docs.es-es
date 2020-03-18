---
ms.openlocfilehash: 60ebcd9fc9ca18c33d31b82ba5020426d22a7d5a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901615"
---
### <a name="authentication-httpcontextauthentication-property-removed"></a><span data-ttu-id="548cf-101">Autenticación: se ha quitado la propiedad HttpContext.Authentication</span><span class="sxs-lookup"><span data-stu-id="548cf-101">Authentication: HttpContext.Authentication property removed</span></span>

<span data-ttu-id="548cf-102">La propiedad `Authentication` en desuso se ha quitado en `HttpContext`.</span><span class="sxs-lookup"><span data-stu-id="548cf-102">The deprecated `Authentication` property on `HttpContext` has been removed.</span></span>

#### <a name="change-description"></a><span data-ttu-id="548cf-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="548cf-103">Change description</span></span>

<span data-ttu-id="548cf-104">Como parte de [dotnet/aspnetcore#6504](https://github.com/dotnet/aspnetcore/pull/6504), la propiedad `Authentication` en desuso se ha quitado en `HttpContext`.</span><span class="sxs-lookup"><span data-stu-id="548cf-104">As part of [dotnet/aspnetcore#6504](https://github.com/dotnet/aspnetcore/pull/6504), the deprecated `Authentication` property on `HttpContext` has been removed.</span></span> <span data-ttu-id="548cf-105">La propiedad `Authentication` se ha dejado en desuso desde la versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="548cf-105">The `Authentication` property has been deprecated since 2.0.</span></span> <span data-ttu-id="548cf-106">Se ha publicado una [guía de migración](/aspnet/core/migration/1x-to-2x/identity-2x?view=aspnetcore-2.2#use-httpcontext-authentication-extensions) para migrar código con esta propiedad en desuso a las nuevas API de reemplazo.</span><span class="sxs-lookup"><span data-stu-id="548cf-106">A [migration guide](/aspnet/core/migration/1x-to-2x/identity-2x?view=aspnetcore-2.2#use-httpcontext-authentication-extensions) was published to migrate code using this deprecated property to the new replacement APIs.</span></span> <span data-ttu-id="548cf-107">Las clases o API restantes no utilizadas relacionadas con la pila de autenticación antigua ASP.NET Core 1.x se han quitado en la confirmación [dotnet/aspnetcore@d7a7c65](https://github.com/dotnet/aspnetcore/commit/d7a7c65).</span><span class="sxs-lookup"><span data-stu-id="548cf-107">The remaining unused classes / APIs related to the old ASP.NET Core 1.x authentication stack were removed in commit [dotnet/aspnetcore@d7a7c65](https://github.com/dotnet/aspnetcore/commit/d7a7c65).</span></span>

<span data-ttu-id="548cf-108">Para obtener información, vea [dotnet/aspnetcore#6533](https://github.com/dotnet/aspnetcore/issues/6533).</span><span class="sxs-lookup"><span data-stu-id="548cf-108">For discussion, see [dotnet/aspnetcore#6533](https://github.com/dotnet/aspnetcore/issues/6533).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="548cf-109">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="548cf-109">Version introduced</span></span>

<span data-ttu-id="548cf-110">3.0</span><span class="sxs-lookup"><span data-stu-id="548cf-110">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="548cf-111">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="548cf-111">Reason for change</span></span>

<span data-ttu-id="548cf-112">Las API de ASP.NET Core 1.0 se han reemplazado por métodos de extensión en <xref:Microsoft.AspNetCore.Authentication.AuthenticationHttpContextExtensions?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="548cf-112">ASP.NET Core 1.0 APIs have been replaced by extension methods in <xref:Microsoft.AspNetCore.Authentication.AuthenticationHttpContextExtensions?displayProperty=fullName>.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="548cf-113">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="548cf-113">Recommended action</span></span>

<span data-ttu-id="548cf-114">Consulte la [guía de migración](/aspnet/core/migration/1x-to-2x/identity-2x?view=aspnetcore-2.2#use-httpcontext-authentication-extensions).</span><span class="sxs-lookup"><span data-stu-id="548cf-114">See the [migration guide](/aspnet/core/migration/1x-to-2x/identity-2x?view=aspnetcore-2.2#use-httpcontext-authentication-extensions).</span></span>

#### <a name="category"></a><span data-ttu-id="548cf-115">Categoría</span><span class="sxs-lookup"><span data-stu-id="548cf-115">Category</span></span>

<span data-ttu-id="548cf-116">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="548cf-116">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="548cf-117">API afectadas</span><span class="sxs-lookup"><span data-stu-id="548cf-117">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Http.Authentication.AuthenticateInfo?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Authentication.AuthenticationManager?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Authentication.AuthenticationProperties?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.AuthenticateContext?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.ChallengeBehavior?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.ChallengeContext?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.DescribeSchemesContext?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.IAuthenticationHandler?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.IHttpAuthenticationFeature.Handler?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.SignInContext?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.SignOutContext?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.HttpContext.Authentication?displayProperty=fullName>

<!-- 

#### Affected APIs

- `T:Microsoft.AspNetCore.Http.Authentication.AuthenticateInfo`
- `T:Microsoft.AspNetCore.Http.Authentication.AuthenticationManager`
- `T:Microsoft.AspNetCore.Http.Authentication.AuthenticationProperties`
- `T:Microsoft.AspNetCore.Http.Features.Authentication.AuthenticateContext`
- `T:Microsoft.AspNetCore.Http.Features.Authentication.ChallengeBehavior`
- `T:Microsoft.AspNetCore.Http.Features.Authentication.ChallengeContext`
- `T:Microsoft.AspNetCore.Http.Features.Authentication.DescribeSchemesContext`
- `T:Microsoft.AspNetCore.Http.Features.Authentication.IAuthenticationHandler`
- `P:Microsoft.AspNetCore.Http.Features.Authentication.IHttpAuthenticationFeature.Handler`
- `T:Microsoft.AspNetCore.Http.Features.Authentication.SignInContext`
- `T:Microsoft.AspNetCore.Http.Features.Authentication.SignOutContext`
- `P:Microsoft.AspNetCore.Http.HttpContext.Authentication`

-->
