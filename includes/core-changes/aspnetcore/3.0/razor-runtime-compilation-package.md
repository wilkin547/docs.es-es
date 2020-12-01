---
ms.openlocfilehash: cd13e7560ee98e0c862c5e2293521c6aaa273455
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032853"
---
### <a name="razor-runtime-compilation-moved-to-a-package"></a><span data-ttu-id="a09d3-101">Razor: la compilación en entorno de ejecución se ha movido a un paquete</span><span class="sxs-lookup"><span data-stu-id="a09d3-101">Razor: Runtime compilation moved to a package</span></span>

<span data-ttu-id="a09d3-102">La compatibilidad con la compilación en entorno de ejecución de las vistas de Razor y Razor Pages se ha movido a un paquete independiente.</span><span class="sxs-lookup"><span data-stu-id="a09d3-102">Support for runtime compilation of Razor views and Razor Pages has moved to a separate package.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="a09d3-103">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="a09d3-103">Version introduced</span></span>

<span data-ttu-id="a09d3-104">3.0</span><span class="sxs-lookup"><span data-stu-id="a09d3-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="a09d3-105">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="a09d3-105">Old behavior</span></span>

<span data-ttu-id="a09d3-106">La compilación en entorno de ejecución está disponible sin necesidad de paquetes adicionales.</span><span class="sxs-lookup"><span data-stu-id="a09d3-106">Runtime compilation is available without needing additional packages.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="a09d3-107">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="a09d3-107">New behavior</span></span>

<span data-ttu-id="a09d3-108">La funcionalidad se ha pasado al paquete [Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation](https://www.nuget.org/packages/Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation/).</span><span class="sxs-lookup"><span data-stu-id="a09d3-108">The functionality has been moved to the [Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation](https://www.nuget.org/packages/Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation/) package.</span></span>

<span data-ttu-id="a09d3-109">Las siguientes API estaban disponibles anteriormente en `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions` para admitir la compilación en entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a09d3-109">The following APIs were previously available in `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions` to support runtime compilation.</span></span> <span data-ttu-id="a09d3-110">Las API ahora están disponibles mediante `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation.MvcRazorRuntimeCompilationOptions`.</span><span class="sxs-lookup"><span data-stu-id="a09d3-110">The APIs are now available via `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation.MvcRazorRuntimeCompilationOptions`.</span></span>

- <span data-ttu-id="a09d3-111">`RazorViewEngineOptions.FileProviders` es ahora `MvcRazorRuntimeCompilationOptions.FileProviders`</span><span class="sxs-lookup"><span data-stu-id="a09d3-111">`RazorViewEngineOptions.FileProviders` is now `MvcRazorRuntimeCompilationOptions.FileProviders`</span></span>
- <span data-ttu-id="a09d3-112">`RazorViewEngineOptions.AdditionalCompilationReferences` es ahora `MvcRazorRuntimeCompilationOptions.AdditionalReferencePaths`</span><span class="sxs-lookup"><span data-stu-id="a09d3-112">`RazorViewEngineOptions.AdditionalCompilationReferences` is now `MvcRazorRuntimeCompilationOptions.AdditionalReferencePaths`</span></span>

<span data-ttu-id="a09d3-113">Además, se ha quitado `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions.AllowRecompilingViewsOnFileChange`.</span><span class="sxs-lookup"><span data-stu-id="a09d3-113">In addition, `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions.AllowRecompilingViewsOnFileChange` has been removed.</span></span> <span data-ttu-id="a09d3-114">La recompilación en los cambios de archivo está habilitada de forma predeterminada al hacer referencia al paquete `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation`.</span><span class="sxs-lookup"><span data-stu-id="a09d3-114">Recompilation on file changes is enabled by default by referencing the `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` package.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="a09d3-115">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="a09d3-115">Reason for change</span></span>

<span data-ttu-id="a09d3-116">Este cambio era necesario para quitar la dependencia de marco compartido de ASP.NET Core en Roslyn.</span><span class="sxs-lookup"><span data-stu-id="a09d3-116">This change was necessary to remove the ASP.NET Core shared framework dependency on Roslyn.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a09d3-117">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="a09d3-117">Recommended action</span></span>

<span data-ttu-id="a09d3-118">Las aplicaciones que requieren la compilación o recompilación en entorno de ejecución de archivos Razor deben realizar los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="a09d3-118">Apps that require runtime compilation or recompilation of Razor files should take the following steps:</span></span>

1. <span data-ttu-id="a09d3-119">Agregar una referencia al paquete `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation`.</span><span class="sxs-lookup"><span data-stu-id="a09d3-119">Add a reference to the `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` package.</span></span>
1. <span data-ttu-id="a09d3-120">Actualizar el método `Startup.ConfigureServices` del proyecto para incluir una llamada a `AddRazorRuntimeCompilation`.</span><span class="sxs-lookup"><span data-stu-id="a09d3-120">Update the project's `Startup.ConfigureServices` method to include a call to `AddRazorRuntimeCompilation`.</span></span> <span data-ttu-id="a09d3-121">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a09d3-121">For example:</span></span>

    ```csharp
    services.AddMvc()
        .AddRazorRuntimeCompilation();
    ```

#### <a name="category"></a><span data-ttu-id="a09d3-122">Categoría</span><span class="sxs-lookup"><span data-stu-id="a09d3-122">Category</span></span>

<span data-ttu-id="a09d3-123">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="a09d3-123">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a09d3-124">API afectadas</span><span class="sxs-lookup"><span data-stu-id="a09d3-124">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions?displayProperty=fullName>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions`

-->
