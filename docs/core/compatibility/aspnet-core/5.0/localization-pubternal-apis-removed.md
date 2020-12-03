---
title: 'Cambio importante: API Pubternal quitadas'
description: Obtenga información sobre el cambio importante en ASP.NET Core 5.0 donde se han quitado algunas API Pubternal de localización
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: ae647d66b716175536edb3c978b027ebb7d3ddac
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760127"
---
# <a name="localization-pubternal-apis-removed"></a><span data-ttu-id="b22ee-103">Localización: API "Pubternal" quitadas</span><span class="sxs-lookup"><span data-stu-id="b22ee-103">Localization: "Pubternal" APIs removed</span></span>

<span data-ttu-id="b22ee-104">Para mantener mejor la superficie de la API pública de ASP.NET Core, se han quitado algunas API de localización de :::no-loc text="\"pubternal\"":::.</span><span class="sxs-lookup"><span data-stu-id="b22ee-104">To better maintain the public API surface of ASP.NET Core, some :::no-loc text="\"pubternal\""::: localization APIs were removed.</span></span> <span data-ttu-id="b22ee-105">Una API de :::no-loc text="\"pubternal\""::: tiene un modificador de acceso `public` y se define en un espacio de nombres que implica una intención [interna](../../../../csharp/language-reference/keywords/internal.md).</span><span class="sxs-lookup"><span data-stu-id="b22ee-105">A :::no-loc text="\"pubternal\""::: API has a `public` access modifier and is defined in a namespace that implies an [internal](../../../../csharp/language-reference/keywords/internal.md) intent.</span></span>

<span data-ttu-id="b22ee-106">Para obtener información, vea [dotnet/aspnetcore#22291](https://github.com/dotnet/aspnetcore/issues/22291).</span><span class="sxs-lookup"><span data-stu-id="b22ee-106">For discussion, see [dotnet/aspnetcore#22291](https://github.com/dotnet/aspnetcore/issues/22291).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="b22ee-107">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="b22ee-107">Version introduced</span></span>

<span data-ttu-id="b22ee-108">5.0 (versión preliminar 6)</span><span class="sxs-lookup"><span data-stu-id="b22ee-108">5.0 Preview 6</span></span>

## <a name="old-behavior"></a><span data-ttu-id="b22ee-109">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="b22ee-109">Old behavior</span></span>

<span data-ttu-id="b22ee-110">Las siguientes API eran `public`:</span><span class="sxs-lookup"><span data-stu-id="b22ee-110">The following APIs were `public`:</span></span>

- `Microsoft.Extensions.Localization.Internal.AssemblyWrapper`
- `Microsoft.Extensions.Localization.Internal.IResourceStringProvider`
- <span data-ttu-id="b22ee-111">El constructor `Microsoft.Extensions.Localization.ResourceManagerStringLocalizer` se sobrecarga al aceptar cualquiera de los tipos de parámetro siguientes:</span><span class="sxs-lookup"><span data-stu-id="b22ee-111">`Microsoft.Extensions.Localization.ResourceManagerStringLocalizer` constructor overloads accepting either of the following parameter types:</span></span>
  - `AssemblyWrapper`
  - `IResourceStringProvider`

## <a name="new-behavior"></a><span data-ttu-id="b22ee-112">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="b22ee-112">New behavior</span></span>

<span data-ttu-id="b22ee-113">En la lista siguiente se describen los cambios:</span><span class="sxs-lookup"><span data-stu-id="b22ee-113">The following list outlines the changes:</span></span>

- <span data-ttu-id="b22ee-114">`Microsoft.Extensions.Localization.Internal.AssemblyWrapper` se ha convertido en `Microsoft.Extensions.Localization.AssemblyWrapper` y ahora es `internal`.</span><span class="sxs-lookup"><span data-stu-id="b22ee-114">`Microsoft.Extensions.Localization.Internal.AssemblyWrapper` became `Microsoft.Extensions.Localization.AssemblyWrapper` and is now `internal`.</span></span>
- <span data-ttu-id="b22ee-115">`Microsoft.Extensions.Localization.Internal.IResourceStringProvider` se ha convertido en `Microsoft.Extensions.Localization.Internal.IResourceStringProvider` y ahora es `internal`.</span><span class="sxs-lookup"><span data-stu-id="b22ee-115">`Microsoft.Extensions.Localization.Internal.IResourceStringProvider` became `Microsoft.Extensions.Localization.Internal.IResourceStringProvider` and is now `internal`.</span></span>
- <span data-ttu-id="b22ee-116">Las sobrecargas del constructor `Microsoft.Extensions.Localization.ResourceManagerStringLocalizer` al aceptar cualquiera de los tipos de parámetro siguientes ahora son `internal`:</span><span class="sxs-lookup"><span data-stu-id="b22ee-116">`Microsoft.Extensions.Localization.ResourceManagerStringLocalizer` constructor overloads accepting either of the following parameter types are now `internal`:</span></span>
  - `AssemblyWrapper`
  - `IResourceStringProvider`

## <a name="reason-for-change"></a><span data-ttu-id="b22ee-117">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="b22ee-117">Reason for change</span></span>

<span data-ttu-id="b22ee-118">Se explica de forma más detallada en [aspnet/Announcements#377](https://github.com/aspnet/Announcements/issues/377#issue-473651882). Los tipos :::no-loc text="\"pubternal\""::: se han quitado de la superficie de la API de `public`.</span><span class="sxs-lookup"><span data-stu-id="b22ee-118">Explained more thoroughly at [aspnet/Announcements#377](https://github.com/aspnet/Announcements/issues/377#issue-473651882), :::no-loc text="\"pubternal\""::: types were removed from the `public` API surface.</span></span> <span data-ttu-id="b22ee-119">Estos cambios adaptan más clases a la decisión de diseño mencionada.</span><span class="sxs-lookup"><span data-stu-id="b22ee-119">These changes adapt more classes to that design decision.</span></span> <span data-ttu-id="b22ee-120">Las clases en cuestión estaban pensadas como puntos de extensión para las pruebas internas del equipo.</span><span class="sxs-lookup"><span data-stu-id="b22ee-120">The classes in question were intended as extension points for the team's internal testing.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="b22ee-121">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="b22ee-121">Recommended action</span></span>

<span data-ttu-id="b22ee-122">Aunque es improbable, algunas aplicaciones pueden depender intencional o accidentalmente de los tipos de :::no-loc text="\"pubternal\"":::.</span><span class="sxs-lookup"><span data-stu-id="b22ee-122">Although it's unlikely, some apps may intentionally or accidentally depend upon the :::no-loc text="\"pubternal\""::: types.</span></span> <span data-ttu-id="b22ee-123">Consulte las secciones de [Nuevo comportamiento](#new-behavior) para determinar cómo realizar la migración para dejar de usar estos tipos.</span><span class="sxs-lookup"><span data-stu-id="b22ee-123">See the [New behavior](#new-behavior) sections to determine how to migrate away from the types.</span></span>

<span data-ttu-id="b22ee-124">Si ha identificado un escenario en el que la API pública permitía esto antes del cambio mencionado, pero no lo hace ahora, registre una incidencia en [dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/issues).</span><span class="sxs-lookup"><span data-stu-id="b22ee-124">If you've identified a scenario which the public API allowed before this change but doesn't now, file an issue at [dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/issues).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="b22ee-125">API afectadas</span><span class="sxs-lookup"><span data-stu-id="b22ee-125">Affected APIs</span></span>

- `Microsoft.Extensions.Localization.Internal.AssemblyWrapper`
- `Microsoft.Extensions.Localization.Internal.IResourceStringProvider`
- <xref:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.%23ctor%2A?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

- `T:Microsoft.Extensions.Localization.Internal.AssemblyWrapper`
- `T:Microsoft.Extensions.Localization.Internal.IResourceStringProvider`
- `Overload:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.#ctor`

-->
