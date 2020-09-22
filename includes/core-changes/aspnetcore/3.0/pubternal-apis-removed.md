---
ms.openlocfilehash: 224cd3c7897c64ef05baba7d3d31dbe5ac0dd610
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606569"
---
### <a name="pubternal-apis-removed"></a><span data-ttu-id="91ca9-101">API "Pubternal" quitadas</span><span class="sxs-lookup"><span data-stu-id="91ca9-101">"Pubternal" APIs removed</span></span>

<span data-ttu-id="91ca9-102">Para mantener mejor la superficie de la API pública de ASP.NET Core, la mayoría de los tipos de los espacios de nombres `*.Internal` (conocidos como API :::no-loc text="\"pubternal\"":::) se han vuelto realmente internos.</span><span class="sxs-lookup"><span data-stu-id="91ca9-102">To better maintain the public API surface of ASP.NET Core, most of the types in `*.Internal` namespaces (referred to as :::no-loc text="\"pubternal\""::: APIs) have become truly internal.</span></span> <span data-ttu-id="91ca9-103">Los miembros de estos espacios de nombres nunca debían admitirse como API de acceso público.</span><span class="sxs-lookup"><span data-stu-id="91ca9-103">Members in these namespaces were never meant to be supported as public-facing APIs.</span></span> <span data-ttu-id="91ca9-104">Las API podían dividirse en versiones secundarias y con frecuencia lo hacían.</span><span class="sxs-lookup"><span data-stu-id="91ca9-104">The APIs could break in minor releases and often did.</span></span> <span data-ttu-id="91ca9-105">El código que depende de estas API se divide cuando se actualiza a ASP.NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="91ca9-105">Code that depends on these APIs breaks when updating to ASP.NET Core 3.0.</span></span>

<span data-ttu-id="91ca9-106">Para más información, consulte [dotnet/aspnetcore#4932](https://github.com/dotnet/aspnetcore/issues/4932) y [dotnet/aspnetcore#11312](https://github.com/dotnet/aspnetcore/issues/11312).</span><span class="sxs-lookup"><span data-stu-id="91ca9-106">For more information, see [dotnet/aspnetcore#4932](https://github.com/dotnet/aspnetcore/issues/4932) and [dotnet/aspnetcore#11312](https://github.com/dotnet/aspnetcore/issues/11312).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="91ca9-107">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="91ca9-107">Version introduced</span></span>

<span data-ttu-id="91ca9-108">3.0</span><span class="sxs-lookup"><span data-stu-id="91ca9-108">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="91ca9-109">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="91ca9-109">Old behavior</span></span>

<span data-ttu-id="91ca9-110">Las API afectadas se marcan con el modificador de acceso `public` y existen en los espacios de nombres `*.Internal`.</span><span class="sxs-lookup"><span data-stu-id="91ca9-110">The affected APIs are marked with the `public` access modifier and exist in `*.Internal` namespaces.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="91ca9-111">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="91ca9-111">New behavior</span></span>

<span data-ttu-id="91ca9-112">Las API afectadas se marcan con el modificador de acceso [internal](../../../../docs/csharp/language-reference/keywords/internal.md) y ya no se pueden usar en el código fuera de ese ensamblado.</span><span class="sxs-lookup"><span data-stu-id="91ca9-112">The affected APIs are marked with the [internal](../../../../docs/csharp/language-reference/keywords/internal.md) access modifier and can no longer be used by code outside that assembly.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="91ca9-113">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="91ca9-113">Reason for change</span></span>

<span data-ttu-id="91ca9-114">Las instrucciones para estas API de :::no-loc text="\"pubternal\""::: eran las siguientes:</span><span class="sxs-lookup"><span data-stu-id="91ca9-114">The guidance for these :::no-loc text="\"pubternal\""::: APIs was that they:</span></span>

* <span data-ttu-id="91ca9-115">Podían cambiar sin previo aviso.</span><span class="sxs-lookup"><span data-stu-id="91ca9-115">Could change without notice.</span></span>
* <span data-ttu-id="91ca9-116">No estaban sujetas a las directivas de .NET para evitar cambios importantes.</span><span class="sxs-lookup"><span data-stu-id="91ca9-116">Weren't subject to .NET policies to prevent breaking changes.</span></span>

<span data-ttu-id="91ca9-117">La salida de las API `public` (incluso en los espacios de nombres de `*.Internal`) era confusa para los clientes.</span><span class="sxs-lookup"><span data-stu-id="91ca9-117">Leaving the APIs `public` (even in the `*.Internal` namespaces) was confusing to customers.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="91ca9-118">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="91ca9-118">Recommended action</span></span>

<span data-ttu-id="91ca9-119">Deje de usar estas API :::no-loc text="\"pubternal\"":::.</span><span class="sxs-lookup"><span data-stu-id="91ca9-119">Stop using these :::no-loc text="\"pubternal\""::: APIs.</span></span> <span data-ttu-id="91ca9-120">Si tiene alguna pregunta sobre API alternativas, abra una incidencia en el repositorio [dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/issues).</span><span class="sxs-lookup"><span data-stu-id="91ca9-120">If you have questions about alternate APIs, open an issue in the [dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/issues) repository.</span></span>

<span data-ttu-id="91ca9-121">Por ejemplo, considere el siguiente código de almacenamiento en búfer de solicitudes HTTP en un proyecto ASP.NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="91ca9-121">For example, consider the following HTTP request buffering code in an ASP.NET Core 2.2 project.</span></span> <span data-ttu-id="91ca9-122">El método de extensión `EnableRewind` existe en el espacio de nombres `Microsoft.AspNetCore.Http.Internal`.</span><span class="sxs-lookup"><span data-stu-id="91ca9-122">The `EnableRewind` extension method exists in the `Microsoft.AspNetCore.Http.Internal` namespace.</span></span>

```csharp
HttpContext.Request.EnableRewind();
```

<span data-ttu-id="91ca9-123">En un proyecto ASP.NET Core 3.0, reemplace la llamada `EnableRewind` por una llamada al método de extensión `EnableBuffering`.</span><span class="sxs-lookup"><span data-stu-id="91ca9-123">In an ASP.NET Core 3.0 project, replace the `EnableRewind` call with a call to the `EnableBuffering` extension method.</span></span> <span data-ttu-id="91ca9-124">La característica de almacenamiento en búfer de solicitudes funciona igual que lo hacía antes.</span><span class="sxs-lookup"><span data-stu-id="91ca9-124">The request buffering feature works as it did in the past.</span></span> <span data-ttu-id="91ca9-125">`EnableBuffering` llama a la API `internal` ahora.</span><span class="sxs-lookup"><span data-stu-id="91ca9-125">`EnableBuffering` calls the now `internal` API.</span></span>

```csharp
HttpContext.Request.EnableBuffering();
```

#### <a name="category"></a><span data-ttu-id="91ca9-126">Categoría</span><span class="sxs-lookup"><span data-stu-id="91ca9-126">Category</span></span>

<span data-ttu-id="91ca9-127">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="91ca9-127">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="91ca9-128">API afectadas</span><span class="sxs-lookup"><span data-stu-id="91ca9-128">Affected APIs</span></span>

<span data-ttu-id="91ca9-129">Todas las API de los espacios de nombres `Microsoft.AspNetCore.*` y `Microsoft.Extensions.*` que tienen un segmento `Internal` en el nombre del espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="91ca9-129">All APIs in the `Microsoft.AspNetCore.*` and `Microsoft.Extensions.*` namespaces that have an `Internal` segment in the namespace name.</span></span> <span data-ttu-id="91ca9-130">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="91ca9-130">For example:</span></span>

- `Microsoft.AspNetCore.Authentication.Internal`
- `Microsoft.AspNetCore.Builder.Internal`
- `Microsoft.AspNetCore.DataProtection.Cng.Internal`
- `Microsoft.AspNetCore.DataProtection.Internal`
- `Microsoft.AspNetCore.Hosting.Internal`
- `Microsoft.AspNetCore.Http.Internal`
- `Microsoft.AspNetCore.Mvc.Core.Infrastructure`
- `Microsoft.AspNetCore.Mvc.Core.Internal`
- `Microsoft.AspNetCore.Mvc.Cors.Internal`
- `Microsoft.AspNetCore.Mvc.DataAnnotations.Internal`
- `Microsoft.AspNetCore.Mvc.Formatters.Internal`
- `Microsoft.AspNetCore.Mvc.Formatters.Json.Internal`
- `Microsoft.AspNetCore.Mvc.Formatters.Xml.Internal`
- `Microsoft.AspNetCore.Mvc.Internal`
- `Microsoft.AspNetCore.Mvc.ModelBinding.Internal`
- `Microsoft.AspNetCore.Mvc.Razor.Internal`
- `Microsoft.AspNetCore.Mvc.RazorPages.Internal`
- `Microsoft.AspNetCore.Mvc.TagHelpers.Internal`
- `Microsoft.AspNetCore.Mvc.ViewFeatures.Internal`
- `Microsoft.AspNetCore.Rewrite.Internal`
- `Microsoft.AspNetCore.Routing.Internal`
- `Microsoft.AspNetCore.Server.Kestrel.Core.Adapter.Internal`
- `Microsoft.AspNetCore.Server.Kestrel.Core.Internal.Http`
- `Microsoft.AspNetCore.Server.Kestrel.Core.Internal.Infrastructure`
- `Microsoft.AspNetCore.Server.Kestrel.Https.Internal`

<!--

#### Affected APIs

- `N:Microsoft.AspNetCore.Authentication.Internal`
- `N:Microsoft.AspNetCore.Builder.Internal`
- `N:Microsoft.AspNetCore.DataProtection.Cng.Internal`
- `N:Microsoft.AspNetCore.DataProtection.Internal`
- `N:Microsoft.AspNetCore.Hosting.Internal`
- `N:Microsoft.AspNetCore.Http.Internal`
- `N:Microsoft.AspNetCore.Mvc.Core.Infrastructure`
- `N:Microsoft.AspNetCore.Mvc.Core.Internal`
- `N:Microsoft.AspNetCore.Mvc.Cors.Internal`
- `N:Microsoft.AspNetCore.Mvc.DataAnnotations.Internal`
- `N:Microsoft.AspNetCore.Mvc.Formatters.Internal`
- `N:Microsoft.AspNetCore.Mvc.Formatters.Json.Internal`
- `N:Microsoft.AspNetCore.Mvc.Formatters.Xml.Internal`
- `N:Microsoft.AspNetCore.Mvc.Internal`
- `N:Microsoft.AspNetCore.Mvc.ModelBinding.Internal`
- `N:Microsoft.AspNetCore.Mvc.Razor.Internal`
- `N:Microsoft.AspNetCore.Mvc.RazorPages.Internal`
- `N:Microsoft.AspNetCore.Mvc.TagHelpers.Internal`
- `N:Microsoft.AspNetCore.Mvc.ViewFeatures.Internal`
- `N:Microsoft.AspNetCore.Rewrite.Internal`
- `N:Microsoft.AspNetCore.Routing.Internal`
- `N:Microsoft.AspNetCore.Server.Kestrel.Core.Adapter.Internal`
- `N:Microsoft.AspNetCore.Server.Kestrel.Core.Internal.Http`
- `N:Microsoft.AspNetCore.Server.Kestrel.Core.Internal.Infrastructure`
- `N:Microsoft.AspNetCore.Server.Kestrel.Https.Internal`

-->
