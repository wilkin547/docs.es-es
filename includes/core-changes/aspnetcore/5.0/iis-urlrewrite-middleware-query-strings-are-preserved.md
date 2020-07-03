---
ms.openlocfilehash: 29908ed916690e67db3cc5d72ebe1b1c6aea45c6
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325218"
---
### <a name="iis-urlrewrite-middleware-query-strings-are-preserved"></a><span data-ttu-id="0d4e9-101">IIS: Mantenimiento de las cadenas de consulta de middleware de UrlRewrite</span><span class="sxs-lookup"><span data-stu-id="0d4e9-101">IIS: UrlRewrite middleware query strings are preserved</span></span>

<span data-ttu-id="0d4e9-102">Un defecto del middleware de UrlRewrite de IIS impedía que la cadena de consulta se conservase en reglas de reescritura.</span><span class="sxs-lookup"><span data-stu-id="0d4e9-102">An IIS UrlRewrite middleware defect prevented the query string from being preserved in rewrite rules.</span></span> <span data-ttu-id="0d4e9-103">Ese defecto se ha corregido para mantener la coherencia con el comportamiento del módulo UrlRewrite de IIS.</span><span class="sxs-lookup"><span data-stu-id="0d4e9-103">That defect has been fixed to maintain consistency with the IIS UrlRewrite Module's behavior.</span></span>

<span data-ttu-id="0d4e9-104">Para obtener información, vea el tema [dotnet/aspnetcore#22972](https://github.com/dotnet/aspnetcore/issues/22972).</span><span class="sxs-lookup"><span data-stu-id="0d4e9-104">For discussion, see issue [dotnet/aspnetcore#22972](https://github.com/dotnet/aspnetcore/issues/22972).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="0d4e9-105">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="0d4e9-105">Version introduced</span></span>

<span data-ttu-id="0d4e9-106">ASP.NET Core 5.0 Preview 7</span><span class="sxs-lookup"><span data-stu-id="0d4e9-106">ASP.NET Core 5.0 Preview 7</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="0d4e9-107">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="0d4e9-107">Old behavior</span></span>

<span data-ttu-id="0d4e9-108">Observe la siguiente regla de reescritura:</span><span class="sxs-lookup"><span data-stu-id="0d4e9-108">Consider the following rewrite rule:</span></span>

```xml
<rule name="MyRule" stopProcessing="true">
  <match url="^about" />
  <action type="Redirect" url="/contact" redirectType="Temporary" appendQueryString="true" />
</rule>
```

<span data-ttu-id="0d4e9-109">La regla anterior no anexa la cadena de consulta.</span><span class="sxs-lookup"><span data-stu-id="0d4e9-109">The preceding rule doesn't append the query string.</span></span> <span data-ttu-id="0d4e9-110">Un URI como `/about?id=1` redirige a `/contact` en lugar de a `/contact?id=1`.</span><span class="sxs-lookup"><span data-stu-id="0d4e9-110">A URI like `/about?id=1` redirects to `/contact` instead of `/contact?id=1`.</span></span> <span data-ttu-id="0d4e9-111">El valor predeterminado del atributo `appendQueryString` también es `true`.</span><span class="sxs-lookup"><span data-stu-id="0d4e9-111">The `appendQueryString` attribute defaults to `true` as well.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="0d4e9-112">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="0d4e9-112">New behavior</span></span>

<span data-ttu-id="0d4e9-113">La cadena de consulta se mantiene.</span><span class="sxs-lookup"><span data-stu-id="0d4e9-113">The query string is preserved.</span></span> <span data-ttu-id="0d4e9-114">El URI del ejemplo de [Comportamiento anterior](#old-behavior) sería `/contact?id=1`.</span><span class="sxs-lookup"><span data-stu-id="0d4e9-114">The URI from the example in [Old behavior](#old-behavior) would be `/contact?id=1`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="0d4e9-115">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="0d4e9-115">Reason for change</span></span>

<span data-ttu-id="0d4e9-116">El comportamiento anterior no coincidía con el comportamiento del módulo UrlRewrite de IIS.</span><span class="sxs-lookup"><span data-stu-id="0d4e9-116">The old behavior didn't match the IIS UrlRewrite Module's behavior.</span></span> <span data-ttu-id="0d4e9-117">Para admitir la migración entre el middleware y el módulo, el objetivo es mantener comportamientos coherentes.</span><span class="sxs-lookup"><span data-stu-id="0d4e9-117">To support porting between the middleware and module, the goal is to maintain consistent behaviors.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="0d4e9-118">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="0d4e9-118">Recommended action</span></span>

<span data-ttu-id="0d4e9-119">Si se prefiere el comportamiento de eliminación de la cadena de consulta, el elemento `action` debe establecerse en `appendQueryString="false"`.</span><span class="sxs-lookup"><span data-stu-id="0d4e9-119">If the behavior of removing the query string is preferred, set the `action` element to `appendQueryString="false"`.</span></span>

#### <a name="category"></a><span data-ttu-id="0d4e9-120">Categoría</span><span class="sxs-lookup"><span data-stu-id="0d4e9-120">Category</span></span>

<span data-ttu-id="0d4e9-121">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="0d4e9-121">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="0d4e9-122">API afectadas</span><span class="sxs-lookup"><span data-stu-id="0d4e9-122">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Rewrite.IISUrlRewriteOptionsExtensions.AddIISUrlRewrite%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

`Overload:Microsoft.AspNetCore.Rewrite.IISUrlRewriteOptionsExtensions.AddIISUrlRewrite`

-->
