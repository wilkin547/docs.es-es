---
ms.openlocfilehash: 15ba678431b97e7c961c119d83546569bdf9bad2
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032762"
---
### <a name="http-some-cookie-samesite-defaults-changed-to-none"></a><span data-ttu-id="49e29-101">HTTP: Cambio a Ninguno de algunos valores predeterminados de cookie de SameSite</span><span class="sxs-lookup"><span data-stu-id="49e29-101">HTTP: Some cookie SameSite defaults changed to None</span></span>

<span data-ttu-id="49e29-102">`SameSite` es una opción para cookies que puede ayudar a mitigar algunos ataques de falsificación de solicitud entre sitios (CSRF).</span><span class="sxs-lookup"><span data-stu-id="49e29-102">`SameSite` is an option for cookies that can help mitigate some Cross-Site Request Forgery (CSRF) attacks.</span></span> <span data-ttu-id="49e29-103">Cuando esta opción se presentó inicialmente, se usaron valores predeterminados incoherentes en varias API de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="49e29-103">When this option was initially introduced, inconsistent defaults were used across various ASP.NET Core APIs.</span></span> <span data-ttu-id="49e29-104">La incoherencia ha generado unos resultados confusos.</span><span class="sxs-lookup"><span data-stu-id="49e29-104">The inconsistency has led to confusing results.</span></span> <span data-ttu-id="49e29-105">A partir de ASP.NET Core 3.0, estos valores predeterminados están organizados de mejor forma.</span><span class="sxs-lookup"><span data-stu-id="49e29-105">As of ASP.NET Core 3.0, these defaults are better aligned.</span></span> <span data-ttu-id="49e29-106">Debe aceptar participar en esta característica individualmente para cada componente.</span><span class="sxs-lookup"><span data-stu-id="49e29-106">You must opt in to this feature on a per-component basis.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="49e29-107">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="49e29-107">Version introduced</span></span>

<span data-ttu-id="49e29-108">3.0</span><span class="sxs-lookup"><span data-stu-id="49e29-108">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="49e29-109">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="49e29-109">Old behavior</span></span>

<span data-ttu-id="49e29-110">Las API de ASP.NET Core similares usaban diferentes valores predeterminados de <xref:Microsoft.AspNetCore.Http.SameSiteMode>.</span><span class="sxs-lookup"><span data-stu-id="49e29-110">Similar ASP.NET Core APIs used different default <xref:Microsoft.AspNetCore.Http.SameSiteMode> values.</span></span> <span data-ttu-id="49e29-111">Un ejemplo de la incoherencia se percibe en `HttpResponse.Cookies.Append(String, String)` y `HttpResponse.Cookies.Append(String, String, CookieOptions)`, que tenían como valor predeterminado `SameSiteMode.None` y `SameSiteMode.Lax`, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="49e29-111">An example of the inconsistency is seen in `HttpResponse.Cookies.Append(String, String)` and `HttpResponse.Cookies.Append(String, String, CookieOptions)`, which defaulted to `SameSiteMode.None` and `SameSiteMode.Lax`, respectively.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="49e29-112">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="49e29-112">New behavior</span></span>

<span data-ttu-id="49e29-113">Todas las API afectadas tienen como valor predeterminado `SameSiteMode.None`.</span><span class="sxs-lookup"><span data-stu-id="49e29-113">All the affected APIs default to `SameSiteMode.None`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="49e29-114">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="49e29-114">Reason for change</span></span>

<span data-ttu-id="49e29-115">El valor predeterminado se ha cambiado para que `SameSite` fuera una característica de participación opcional.</span><span class="sxs-lookup"><span data-stu-id="49e29-115">The default value was changed to make `SameSite` an opt-in feature.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="49e29-116">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="49e29-116">Recommended action</span></span>

<span data-ttu-id="49e29-117">Cada componente que emite cookies debe decidir si `SameSite` es adecuado para sus escenarios.</span><span class="sxs-lookup"><span data-stu-id="49e29-117">Each component that emits cookies needs to decide if `SameSite` is appropriate for its scenarios.</span></span> <span data-ttu-id="49e29-118">Revise el uso de las API afectadas y vuelva a configurar `SameSite` según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="49e29-118">Review your usage of the affected APIs and reconfigure `SameSite` as needed.</span></span>

#### <a name="category"></a><span data-ttu-id="49e29-119">Categoría</span><span class="sxs-lookup"><span data-stu-id="49e29-119">Category</span></span>

<span data-ttu-id="49e29-120">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="49e29-120">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="49e29-121">API afectadas</span><span class="sxs-lookup"><span data-stu-id="49e29-121">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Http.IResponseCookies.Append(System.String,System.String,Microsoft.AspNetCore.Http.CookieOptions)?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Builder.CookiePolicyOptions.MinimumSameSitePolicy%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:Microsoft.AspNetCore.Http.IResponseCookies.Append(System.String,System.String,Microsoft.AspNetCore.Http.CookieOptions)`
- `Overload:Microsoft.AspNetCore.Builder.CookiePolicyOptions.MinimumSameSitePolicy`

-->
