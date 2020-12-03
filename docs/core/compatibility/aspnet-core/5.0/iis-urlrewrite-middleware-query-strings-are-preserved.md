---
title: 'Cambio importante: IIS: Mantenimiento de las cadenas de consulta de middleware de UrlRewrite'
description: 'Obtenga información sobre el cambio importante en ASP.NET Core 5.0 titulado IIS: Mantenimiento de las cadenas de consulta de middleware de UrlRewrite'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: e4d1ecba62f9e43e7377aba1138968f15f8895d5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760098"
---
# <a name="iis-urlrewrite-middleware-query-strings-are-preserved"></a><span data-ttu-id="4192f-103">IIS: Mantenimiento de las cadenas de consulta de middleware de UrlRewrite</span><span class="sxs-lookup"><span data-stu-id="4192f-103">IIS: UrlRewrite middleware query strings are preserved</span></span>

<span data-ttu-id="4192f-104">Un defecto del middleware de UrlRewrite de IIS impedía que la cadena de consulta se conservase en reglas de reescritura.</span><span class="sxs-lookup"><span data-stu-id="4192f-104">An IIS UrlRewrite middleware defect prevented the query string from being preserved in rewrite rules.</span></span> <span data-ttu-id="4192f-105">Ese defecto se ha corregido para mantener la coherencia con el comportamiento del módulo UrlRewrite de IIS.</span><span class="sxs-lookup"><span data-stu-id="4192f-105">That defect has been fixed to maintain consistency with the IIS UrlRewrite Module's behavior.</span></span>

<span data-ttu-id="4192f-106">Para obtener información, vea el tema [dotnet/aspnetcore#22972](https://github.com/dotnet/aspnetcore/issues/22972).</span><span class="sxs-lookup"><span data-stu-id="4192f-106">For discussion, see issue [dotnet/aspnetcore#22972](https://github.com/dotnet/aspnetcore/issues/22972).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="4192f-107">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="4192f-107">Version introduced</span></span>

<span data-ttu-id="4192f-108">ASP.NET Core 5.0 Preview 7</span><span class="sxs-lookup"><span data-stu-id="4192f-108">ASP.NET Core 5.0 Preview 7</span></span>

## <a name="old-behavior"></a><span data-ttu-id="4192f-109">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="4192f-109">Old behavior</span></span>

<span data-ttu-id="4192f-110">Observe la siguiente regla de reescritura:</span><span class="sxs-lookup"><span data-stu-id="4192f-110">Consider the following rewrite rule:</span></span>

```xml
<rule name="MyRule" stopProcessing="true">
  <match url="^about" />
  <action type="Redirect" url="/contact" redirectType="Temporary" appendQueryString="true" />
</rule>
```

<span data-ttu-id="4192f-111">La regla anterior no anexa la cadena de consulta.</span><span class="sxs-lookup"><span data-stu-id="4192f-111">The preceding rule doesn't append the query string.</span></span> <span data-ttu-id="4192f-112">Un URI como `/about?id=1` redirige a `/contact` en lugar de a `/contact?id=1`.</span><span class="sxs-lookup"><span data-stu-id="4192f-112">A URI like `/about?id=1` redirects to `/contact` instead of `/contact?id=1`.</span></span> <span data-ttu-id="4192f-113">El valor predeterminado del atributo `appendQueryString` también es `true`.</span><span class="sxs-lookup"><span data-stu-id="4192f-113">The `appendQueryString` attribute defaults to `true` as well.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="4192f-114">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="4192f-114">New behavior</span></span>

<span data-ttu-id="4192f-115">La cadena de consulta se mantiene.</span><span class="sxs-lookup"><span data-stu-id="4192f-115">The query string is preserved.</span></span> <span data-ttu-id="4192f-116">El URI del ejemplo de [Comportamiento anterior](#old-behavior) sería `/contact?id=1`.</span><span class="sxs-lookup"><span data-stu-id="4192f-116">The URI from the example in [Old behavior](#old-behavior) would be `/contact?id=1`.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="4192f-117">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="4192f-117">Reason for change</span></span>

<span data-ttu-id="4192f-118">El comportamiento anterior no coincidía con el comportamiento del módulo UrlRewrite de IIS.</span><span class="sxs-lookup"><span data-stu-id="4192f-118">The old behavior didn't match the IIS UrlRewrite Module's behavior.</span></span> <span data-ttu-id="4192f-119">Para admitir la migración entre el middleware y el módulo, el objetivo es mantener comportamientos coherentes.</span><span class="sxs-lookup"><span data-stu-id="4192f-119">To support porting between the middleware and module, the goal is to maintain consistent behaviors.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="4192f-120">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="4192f-120">Recommended action</span></span>

<span data-ttu-id="4192f-121">Si se prefiere el comportamiento de eliminación de la cadena de consulta, el elemento `action` debe establecerse en `appendQueryString="false"`.</span><span class="sxs-lookup"><span data-stu-id="4192f-121">If the behavior of removing the query string is preferred, set the `action` element to `appendQueryString="false"`.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="4192f-122">API afectadas</span><span class="sxs-lookup"><span data-stu-id="4192f-122">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Rewrite.IISUrlRewriteOptionsExtensions.AddIISUrlRewrite%2A?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

`Overload:Microsoft.AspNetCore.Rewrite.IISUrlRewriteOptionsExtensions.AddIISUrlRewrite`

-->
