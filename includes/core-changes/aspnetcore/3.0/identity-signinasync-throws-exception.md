---
ms.openlocfilehash: 6679e38aefa7d61ce430dc5375ff3b35c641ea27
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032781"
---
### <a name="identity-signinasync-throws-exception-for-unauthenticated-identity"></a><span data-ttu-id="41cab-101">Identity: SignInAsync produce una excepción para la identidad no autenticada</span><span class="sxs-lookup"><span data-stu-id="41cab-101">Identity: SignInAsync throws exception for unauthenticated identity</span></span>

<span data-ttu-id="41cab-102">De forma predeterminada, `SignInAsync` produce una excepción para las entidades de seguridad o identidades en las que `IsAuthenticated` es `false`.</span><span class="sxs-lookup"><span data-stu-id="41cab-102">By default, `SignInAsync` throws an exception for principals / identities in which `IsAuthenticated` is `false`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="41cab-103">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="41cab-103">Version introduced</span></span>

<span data-ttu-id="41cab-104">3.0</span><span class="sxs-lookup"><span data-stu-id="41cab-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="41cab-105">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="41cab-105">Old behavior</span></span>

<span data-ttu-id="41cab-106">`SignInAsync` acepta entidades de seguridad e identidades, incluidas las identidades en las que `IsAuthenticated` es `false`.</span><span class="sxs-lookup"><span data-stu-id="41cab-106">`SignInAsync` accepts any principals / identities, including identities in which `IsAuthenticated` is `false`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="41cab-107">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="41cab-107">New behavior</span></span>

<span data-ttu-id="41cab-108">De forma predeterminada, `SignInAsync` produce una excepción para las entidades de seguridad o identidades en las que `IsAuthenticated` es `false`.</span><span class="sxs-lookup"><span data-stu-id="41cab-108">By default, `SignInAsync` throws an exception for principals / identities in which `IsAuthenticated` is `false`.</span></span> <span data-ttu-id="41cab-109">Hay una nueva marca para suprimir este comportamiento, pero el comportamiento predeterminado ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="41cab-109">There's a new flag to suppress this behavior, but the default behavior has changed.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="41cab-110">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="41cab-110">Reason for change</span></span>

<span data-ttu-id="41cab-111">El comportamiento anterior era problemático porque, de forma predeterminada, `[Authorize]` / `RequireAuthenticatedUser()` rechazó estas entidades de seguridad.</span><span class="sxs-lookup"><span data-stu-id="41cab-111">The old behavior was problematic because, by default, these principals were rejected by `[Authorize]` / `RequireAuthenticatedUser()`.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="41cab-112">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="41cab-112">Recommended action</span></span>

<span data-ttu-id="41cab-113">En ASP.NET Core 3.0, versión preliminar 6, hay una marca de `RequireAuthenticatedSignIn` en `AuthenticationOptions` que es `true` de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="41cab-113">In ASP.NET Core 3.0 Preview 6, there's a `RequireAuthenticatedSignIn` flag on `AuthenticationOptions` that is `true` by default.</span></span> <span data-ttu-id="41cab-114">Establezca esta marca en `false` para restaurar el comportamiento anterior.</span><span class="sxs-lookup"><span data-stu-id="41cab-114">Set this flag to `false` to restore the old behavior.</span></span>

#### <a name="category"></a><span data-ttu-id="41cab-115">Categoría</span><span class="sxs-lookup"><span data-stu-id="41cab-115">Category</span></span>

<span data-ttu-id="41cab-116">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="41cab-116">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="41cab-117">API afectadas</span><span class="sxs-lookup"><span data-stu-id="41cab-117">Affected APIs</span></span>

<span data-ttu-id="41cab-118">None</span><span class="sxs-lookup"><span data-stu-id="41cab-118">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
