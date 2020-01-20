---
ms.openlocfilehash: 58dbb73902c0226fa81acf1a70de2160f406f6c6
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901819"
---
### <a name="authorization-iauthorizationpolicyprovider-implementations-require-new-method"></a><span data-ttu-id="7afb0-101">Autorización: las implementaciones de IAuthorizationPolicyProvider requieren un método nuevo</span><span class="sxs-lookup"><span data-stu-id="7afb0-101">Authorization: IAuthorizationPolicyProvider implementations require new method</span></span>

<span data-ttu-id="7afb0-102">En ASP.NET Core 3.0, se ha agregado un nuevo método `GetFallbackPolicyAsync` a `IAuthorizationPolicyProvider`.</span><span class="sxs-lookup"><span data-stu-id="7afb0-102">In ASP.NET Core 3.0, a new `GetFallbackPolicyAsync` method was added to `IAuthorizationPolicyProvider`.</span></span> <span data-ttu-id="7afb0-103">El middleware de autorización usa esta directiva de reserva cuando no se especifica ninguna directiva.</span><span class="sxs-lookup"><span data-stu-id="7afb0-103">This fallback policy is used by the authorization middleware when no policy is specified.</span></span>

<span data-ttu-id="7afb0-104">Para obtener más información, consulte [dotnet/aspnetcore#9759](https://github.com/dotnet/aspnetcore/pull/9759).</span><span class="sxs-lookup"><span data-stu-id="7afb0-104">For more information, see [dotnet/aspnetcore#9759](https://github.com/dotnet/aspnetcore/pull/9759).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="7afb0-105">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="7afb0-105">Version introduced</span></span>

<span data-ttu-id="7afb0-106">3.0</span><span class="sxs-lookup"><span data-stu-id="7afb0-106">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="7afb0-107">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="7afb0-107">Old behavior</span></span>

<span data-ttu-id="7afb0-108">Las implementaciones de `IAuthorizationPolicyProvider` no requerían un método `GetFallbackPolicyAsync`.</span><span class="sxs-lookup"><span data-stu-id="7afb0-108">Implementations of `IAuthorizationPolicyProvider` didn't require a `GetFallbackPolicyAsync` method.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="7afb0-109">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="7afb0-109">New behavior</span></span>

<span data-ttu-id="7afb0-110">Las implementaciones de `IAuthorizationPolicyProvider` requieren un método `GetFallbackPolicyAsync`.</span><span class="sxs-lookup"><span data-stu-id="7afb0-110">Implementations of `IAuthorizationPolicyProvider` require a `GetFallbackPolicyAsync` method.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="7afb0-111">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="7afb0-111">Reason for change</span></span>

<span data-ttu-id="7afb0-112">Se necesitaba un nuevo método para que el nuevo `AuthorizationMiddleware` lo usara cuando no se especificara ninguna directiva.</span><span class="sxs-lookup"><span data-stu-id="7afb0-112">A new method was needed for the new `AuthorizationMiddleware` to use when no policy is specified.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="7afb0-113">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="7afb0-113">Recommended action</span></span>

<span data-ttu-id="7afb0-114">Agregue el método `GetFallbackPolicyAsync` a las implementaciones de `IAuthorizationPolicyProvider`.</span><span class="sxs-lookup"><span data-stu-id="7afb0-114">Add the `GetFallbackPolicyAsync` method to your implementations of `IAuthorizationPolicyProvider`.</span></span>

#### <a name="category"></a><span data-ttu-id="7afb0-115">Categoría</span><span class="sxs-lookup"><span data-stu-id="7afb0-115">Category</span></span>

<span data-ttu-id="7afb0-116">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="7afb0-116">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="7afb0-117">API afectadas</span><span class="sxs-lookup"><span data-stu-id="7afb0-117">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Authorization.IAuthorizationPolicyProvider?displayProperty=fullName>

<!-- 

#### Affected APIs

`T:Microsoft.AspNetCore.Authorization.IAuthorizationPolicyProvider`

-->
