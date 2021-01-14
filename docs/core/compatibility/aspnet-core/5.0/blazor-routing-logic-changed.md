---
title: 'Cambio importante: Blazor: Cambios en la lógica de enrutamiento en aplicaciones Blazor'
description: 'Obtenga información sobre el cambio importante en ASP.NET Core 5.0 titulado Blazor: Cambios en la lógica de enrutamiento en aplicaciones Blazor'
author: scottaddie
ms.author: scaddie
ms.date: 12/14/2020
ms.openlocfilehash: 4ab8289565c88b17eb204a11724bb12a09b033c2
ms.sourcegitcommit: d0990c1c1ab2f81908360f47eafa8db9aa165137
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2020
ms.locfileid: "97513512"
---
# <a name="blazor-route-precedence-logic-changed-in-blazor-apps"></a><span data-ttu-id="6709f-103">Blazor: Lógica de precedencia de ruta cambiada en aplicaciones Blazor</span><span class="sxs-lookup"><span data-stu-id="6709f-103">Blazor: Route precedence logic changed in Blazor apps</span></span>

<span data-ttu-id="6709f-104">Un error en la implementación de enrutamiento de Blazor afectaba al modo en que se determinaba la prioridad de las rutas.</span><span class="sxs-lookup"><span data-stu-id="6709f-104">A bug in the Blazor routing implementation affected how the precedence of routes was determined.</span></span> <span data-ttu-id="6709f-105">Este error afectaba a las rutas de captura general o a las rutas con parámetros opcionales dentro de la aplicación Blazor.</span><span class="sxs-lookup"><span data-stu-id="6709f-105">This bug affects catch-all routes or routes with optional parameters within your Blazor app.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="6709f-106">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="6709f-106">Version introduced</span></span>

<span data-ttu-id="6709f-107">5.0.1</span><span class="sxs-lookup"><span data-stu-id="6709f-107">5.0.1</span></span>

## <a name="old-behavior"></a><span data-ttu-id="6709f-108">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="6709f-108">Old behavior</span></span>

<span data-ttu-id="6709f-109">Con el comportamiento erróneo, se tenían en cuenta primero las rutas con menor prioridad y se hacían coincidir antes que las rutas con mayor prioridad.</span><span class="sxs-lookup"><span data-stu-id="6709f-109">With the erroneous behavior, routes with lower precedence are considered and matched over routes with higher precedence.</span></span> <span data-ttu-id="6709f-110">Por ejemplo, la ruta `{*slug}` se hacía coincidir antes que la ruta `/customer/{id}`.</span><span class="sxs-lookup"><span data-stu-id="6709f-110">For example, the `{*slug}` route is matched before `/customer/{id}`.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="6709f-111">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="6709f-111">New behavior</span></span>

<span data-ttu-id="6709f-112">El comportamiento actual coincide más estrechamente con el comportamiento de enrutamiento definido en las aplicaciones de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="6709f-112">The current behavior more closely matches the routing behavior defined in ASP.NET Core apps.</span></span> <span data-ttu-id="6709f-113">El marco determina primero la prioridad de la ruta para cada segmento.</span><span class="sxs-lookup"><span data-stu-id="6709f-113">The framework determines the route precedence for each segment first.</span></span> <span data-ttu-id="6709f-114">La longitud de la ruta solo se usa como segundo criterio para priorizar en caso de igualdad.</span><span class="sxs-lookup"><span data-stu-id="6709f-114">The route's length is used only as a second criteria to break ties.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="6709f-115">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="6709f-115">Reason for change</span></span>

<span data-ttu-id="6709f-116">El comportamiento original se considera un error en la implementación.</span><span class="sxs-lookup"><span data-stu-id="6709f-116">The original behavior is considered a bug in the implementation.</span></span> <span data-ttu-id="6709f-117">Como objetivo, el sistema de enrutamiento de las aplicaciones Blazor debe comportarse del mismo modo que el sistema de enrutamiento del resto de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="6709f-117">As a goal, the routing system in Blazor apps should behave the same way as the routing system in the rest of ASP.NET Core.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="6709f-118">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="6709f-118">Recommended action</span></span>

<span data-ttu-id="6709f-119">Si actualiza desde versiones anteriores de Blazor a 5.x, use el atributo `PreferExactMatches` en el componente `Router`.</span><span class="sxs-lookup"><span data-stu-id="6709f-119">If upgrading from previous versions of Blazor to 5.x, use the `PreferExactMatches` attribute on the `Router` component.</span></span> <span data-ttu-id="6709f-120">Este atributo se puede usar para escoger el comportamiento correcto.</span><span class="sxs-lookup"><span data-stu-id="6709f-120">This attribute can be used to opt into the correct behavior.</span></span> <span data-ttu-id="6709f-121">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6709f-121">For example:</span></span>

```razor
<Router AppAssembly="@typeof(Program).Assembly" PreferExactMatches="true">
```

<span data-ttu-id="6709f-122">Cuando `PreferExactMatches` se establece en `true`, la coincidencia de rutas prefiere las coincidencias exactas a los caracteres comodín.</span><span class="sxs-lookup"><span data-stu-id="6709f-122">When `PreferExactMatches` is set to `true`, route matching prefers exact matches over wildcards.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="6709f-123">API afectadas</span><span class="sxs-lookup"><span data-stu-id="6709f-123">Affected APIs</span></span>

<span data-ttu-id="6709f-124">None</span><span class="sxs-lookup"><span data-stu-id="6709f-124">None</span></span>

<!--

## Category

ASP.NET Core

## Affected APIs

Not detectable via API analysis

-->
