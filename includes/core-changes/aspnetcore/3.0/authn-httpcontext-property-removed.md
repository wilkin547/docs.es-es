---
ms.openlocfilehash: 60ebcd9fc9ca18c33d31b82ba5020426d22a7d5a
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032730"
---
### <a name="authentication-httpcontextauthentication-property-removed"></a><span data-ttu-id="6088b-101">Autenticación: se ha quitado la propiedad HttpContext.Authentication</span><span class="sxs-lookup"><span data-stu-id="6088b-101">Authentication: HttpContext.Authentication property removed</span></span>

<span data-ttu-id="6088b-102">La propiedad `Authentication` en desuso se ha quitado en `HttpContext`.</span><span class="sxs-lookup"><span data-stu-id="6088b-102">The deprecated `Authentication` property on `HttpContext` has been removed.</span></span>

#### <a name="change-description"></a><span data-ttu-id="6088b-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="6088b-103">Change description</span></span>

<span data-ttu-id="6088b-104">Como parte de [dotnet/aspnetcore#6504](https://github.com/dotnet/aspnetcore/pull/6504), la propiedad `Authentication` en desuso se ha quitado en `HttpContext`.</span><span class="sxs-lookup"><span data-stu-id="6088b-104">As part of [dotnet/aspnetcore#6504](https://github.com/dotnet/aspnetcore/pull/6504), the deprecated `Authentication` property on `HttpContext` has been removed.</span></span> <span data-ttu-id="6088b-105">La propiedad `Authentication` se ha dejado en desuso desde la versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="6088b-105">The `Authentication` property has been deprecated since 2.0.</span></span> <span data-ttu-id="6088b-106">Se ha publicado una [guía de migración](/aspnet/core/migration/1x-to-2x/identity-2x?view=aspnetcore-2.2#use-httpcontext-authentication-extensions) para migrar código con esta propiedad en desuso a las nuevas API de reemplazo.</span><span class="sxs-lookup"><span data-stu-id="6088b-106">A [migration guide](/aspnet/core/migration/1x-to-2x/identity-2x?view=aspnetcore-2.2#use-httpcontext-authentication-extensions) was published to migrate code using this deprecated property to the new replacement APIs.</span></span> <span data-ttu-id="6088b-107">Las clases o API restantes no utilizadas relacionadas con la pila de autenticación antigua ASP.NET Core 1.x se han quitado en la confirmación [dotnet/aspnetcore@d7a7c65](https://github.com/dotnet/aspnetcore/commit/d7a7c65).</span><span class="sxs-lookup"><span data-stu-id="6088b-107">The remaining unused classes / APIs related to the old ASP.NET Core 1.x authentication stack were removed in commit [dotnet/aspnetcore@d7a7c65](https://github.com/dotnet/aspnetcore/commit/d7a7c65).</span></span>

<span data-ttu-id="6088b-108">Para obtener información, vea [dotnet/aspnetcore#6533](https://github.com/dotnet/aspnetcore/issues/6533).</span><span class="sxs-lookup"><span data-stu-id="6088b-108">For discussion, see [dotnet/aspnetcore#6533](https://github.com/dotnet/aspnetcore/issues/6533).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="6088b-109">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="6088b-109">Version introduced</span></span>

<span data-ttu-id="6088b-110">3.0</span><span class="sxs-lookup"><span data-stu-id="6088b-110">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="6088b-111">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="6088b-111">Reason for change</span></span>

<span data-ttu-id="6088b-112">Las API de ASP.NET Core 1.0 se han reemplazado por métodos de extensión en <xref:Microsoft.AspNetCore.Authentication.AuthenticationHttpContextExtensions?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="6088b-112">ASP.NET Core 1.0 APIs have been replaced by extension methods in <xref:Microsoft.AspNetCore.Authentication.AuthenticationHttpContextExtensions?displayProperty=fullName>.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="6088b-113">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="6088b-113">Recommended action</span></span>

<span data-ttu-id="6088b-114">Consulte la [guía de migración](/aspnet/core/migration/1x-to-2x/identity-2x?view=aspnetcore-2.2#use-httpcontext-authentication-extensions).</span><span class="sxs-lookup"><span data-stu-id="6088b-114">See the [migration guide](/aspnet/core/migration/1x-to-2x/identity-2x?view=aspnetcore-2.2#use-httpcontext-authentication-extensions).</span></span>

#### <a name="category"></a><span data-ttu-id="6088b-115">Categoría</span><span class="sxs-lookup"><span data-stu-id="6088b-115">Category</span></span>

<span data-ttu-id="6088b-116">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="6088b-116">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="6088b-117">API afectadas</span><span class="sxs-lookup"><span data-stu-id="6088b-117">Affected APIs</span></span>

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
