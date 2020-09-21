---
ms.openlocfilehash: 62a5f56bb7fffc453623a2c3202f288a19110158
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90539514"
---
### <a name="localization-pubternal-apis-removed"></a><span data-ttu-id="abdcb-101">Localización: API "Pubternal" quitadas</span><span class="sxs-lookup"><span data-stu-id="abdcb-101">Localization: "Pubternal" APIs removed</span></span>

<span data-ttu-id="abdcb-102">Para mantener mejor la superficie de la API pública de ASP.NET Core, se han quitado algunas API de localización de :::no-loc text="\"pubternal\"":::.</span><span class="sxs-lookup"><span data-stu-id="abdcb-102">To better maintain the public API surface of ASP.NET Core, some :::no-loc text="\"pubternal\""::: localization APIs were removed.</span></span> <span data-ttu-id="abdcb-103">Una API de :::no-loc text="\"pubternal\""::: tiene un modificador de acceso `public` y se define en un espacio de nombres que implica una intención [interna](../../../../docs/csharp/language-reference/keywords/internal.md).</span><span class="sxs-lookup"><span data-stu-id="abdcb-103">A :::no-loc text="\"pubternal\""::: API has a `public` access modifier and is defined in a namespace that implies an [internal](../../../../docs/csharp/language-reference/keywords/internal.md) intent.</span></span>

<span data-ttu-id="abdcb-104">Para obtener información, vea [dotnet/aspnetcore#22291](https://github.com/dotnet/aspnetcore/issues/22291).</span><span class="sxs-lookup"><span data-stu-id="abdcb-104">For discussion, see [dotnet/aspnetcore#22291](https://github.com/dotnet/aspnetcore/issues/22291).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="abdcb-105">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="abdcb-105">Version introduced</span></span>

<span data-ttu-id="abdcb-106">5.0 (versión preliminar 6)</span><span class="sxs-lookup"><span data-stu-id="abdcb-106">5.0 Preview 6</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="abdcb-107">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="abdcb-107">Old behavior</span></span>

<span data-ttu-id="abdcb-108">Las siguientes API eran `public`:</span><span class="sxs-lookup"><span data-stu-id="abdcb-108">The following APIs were `public`:</span></span>

- `Microsoft.Extensions.Localization.Internal.AssemblyWrapper`
- `Microsoft.Extensions.Localization.Internal.IResourceStringProvider`
- <span data-ttu-id="abdcb-109">El constructor `Microsoft.Extensions.Localization.ResourceManagerStringLocalizer` se sobrecarga al aceptar cualquiera de los tipos de parámetro siguientes:</span><span class="sxs-lookup"><span data-stu-id="abdcb-109">`Microsoft.Extensions.Localization.ResourceManagerStringLocalizer` constructor overloads accepting either of the following parameter types:</span></span>
  - `AssemblyWrapper`
  - `IResourceStringProvider`

#### <a name="new-behavior"></a><span data-ttu-id="abdcb-110">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="abdcb-110">New behavior</span></span>

<span data-ttu-id="abdcb-111">En la lista siguiente se describen los cambios:</span><span class="sxs-lookup"><span data-stu-id="abdcb-111">The following list outlines the changes:</span></span>

- <span data-ttu-id="abdcb-112">`Microsoft.Extensions.Localization.Internal.AssemblyWrapper` se ha convertido en `Microsoft.Extensions.Localization.AssemblyWrapper` y ahora es `internal`.</span><span class="sxs-lookup"><span data-stu-id="abdcb-112">`Microsoft.Extensions.Localization.Internal.AssemblyWrapper` became `Microsoft.Extensions.Localization.AssemblyWrapper` and is now `internal`.</span></span>
- <span data-ttu-id="abdcb-113">`Microsoft.Extensions.Localization.Internal.IResourceStringProvider` se ha convertido en `Microsoft.Extensions.Localization.Internal.IResourceStringProvider` y ahora es `internal`.</span><span class="sxs-lookup"><span data-stu-id="abdcb-113">`Microsoft.Extensions.Localization.Internal.IResourceStringProvider` became `Microsoft.Extensions.Localization.Internal.IResourceStringProvider` and is now `internal`.</span></span>
- <span data-ttu-id="abdcb-114">Las sobrecargas del constructor `Microsoft.Extensions.Localization.ResourceManagerStringLocalizer` al aceptar cualquiera de los tipos de parámetro siguientes ahora son `internal`:</span><span class="sxs-lookup"><span data-stu-id="abdcb-114">`Microsoft.Extensions.Localization.ResourceManagerStringLocalizer` constructor overloads accepting either of the following parameter types are now `internal`:</span></span>
  - `AssemblyWrapper`
  - `IResourceStringProvider`

#### <a name="reason-for-change"></a><span data-ttu-id="abdcb-115">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="abdcb-115">Reason for change</span></span>

<span data-ttu-id="abdcb-116">Se explica de forma más detallada en [aspnet/Announcements#377](https://github.com/aspnet/Announcements/issues/377#issue-473651882). Los tipos :::no-loc text="\"pubternal\""::: se han quitado de la superficie de la API de `public`.</span><span class="sxs-lookup"><span data-stu-id="abdcb-116">Explained more thoroughly at [aspnet/Announcements#377](https://github.com/aspnet/Announcements/issues/377#issue-473651882), :::no-loc text="\"pubternal\""::: types were removed from the `public` API surface.</span></span> <span data-ttu-id="abdcb-117">Estos cambios adaptan más clases a la decisión de diseño mencionada.</span><span class="sxs-lookup"><span data-stu-id="abdcb-117">These changes adapt more classes to that design decision.</span></span> <span data-ttu-id="abdcb-118">Las clases en cuestión estaban pensadas como puntos de extensión para las pruebas internas del equipo.</span><span class="sxs-lookup"><span data-stu-id="abdcb-118">The classes in question were intended as extension points for the team's internal testing.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="abdcb-119">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="abdcb-119">Recommended action</span></span>

<span data-ttu-id="abdcb-120">Aunque es improbable, algunas aplicaciones pueden depender intencional o accidentalmente de los tipos de :::no-loc text="\"pubternal\"":::.</span><span class="sxs-lookup"><span data-stu-id="abdcb-120">Although it's unlikely, some apps may intentionally or accidentally depend upon the :::no-loc text="\"pubternal\""::: types.</span></span> <span data-ttu-id="abdcb-121">Consulte las secciones de [Nuevo comportamiento](#new-behavior) para determinar cómo realizar la migración para dejar de usar estos tipos.</span><span class="sxs-lookup"><span data-stu-id="abdcb-121">See the [New behavior](#new-behavior) sections to determine how to migrate away from the types.</span></span>

<span data-ttu-id="abdcb-122">Si ha identificado un escenario en el que la API pública permitía esto antes del cambio mencionado, pero no lo hace ahora, registre una incidencia en [dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/issues).</span><span class="sxs-lookup"><span data-stu-id="abdcb-122">If you've identified a scenario which the public API allowed before this change but doesn't now, file an issue at [dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/issues).</span></span>

#### <a name="category"></a><span data-ttu-id="abdcb-123">Categoría</span><span class="sxs-lookup"><span data-stu-id="abdcb-123">Category</span></span>

<span data-ttu-id="abdcb-124">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="abdcb-124">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="abdcb-125">API afectadas</span><span class="sxs-lookup"><span data-stu-id="abdcb-125">Affected APIs</span></span>

- `Microsoft.Extensions.Localization.Internal.AssemblyWrapper`
- `Microsoft.Extensions.Localization.Internal.IResourceStringProvider`
- <xref:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.%23ctor%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:Microsoft.Extensions.Localization.Internal.AssemblyWrapper`
- `T:Microsoft.Extensions.Localization.Internal.IResourceStringProvider`
- `Overload:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.#ctor`

-->
