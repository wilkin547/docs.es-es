---
ms.openlocfilehash: 8479168b64153d3c729f8814a2649df8d46f2135
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394192"
---
### <a name="razor-runtime-compilation-moved-to-a-package"></a><span data-ttu-id="c51fc-101">Razor: la compilación en entorno de ejecución se ha movido a un paquete</span><span class="sxs-lookup"><span data-stu-id="c51fc-101">Razor: Runtime compilation moved to a package</span></span>

<span data-ttu-id="c51fc-102">La compatibilidad con la compilación en entorno de ejecución de las vistas de Razor y Razor Pages se ha movido a un paquete independiente.</span><span class="sxs-lookup"><span data-stu-id="c51fc-102">Support for runtime compilation of Razor views and Razor Pages has moved to a separate package.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="c51fc-103">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="c51fc-103">Version introduced</span></span>

<span data-ttu-id="c51fc-104">3.0</span><span class="sxs-lookup"><span data-stu-id="c51fc-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="c51fc-105">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="c51fc-105">Old behavior</span></span>

<span data-ttu-id="c51fc-106">La compilación en entorno de ejecución está disponible sin necesidad de paquetes adicionales.</span><span class="sxs-lookup"><span data-stu-id="c51fc-106">Runtime compilation is available without needing additional packages.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="c51fc-107">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="c51fc-107">New behavior</span></span>

<span data-ttu-id="c51fc-108">La funcionalidad se ha movido al paquete `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation`.</span><span class="sxs-lookup"><span data-stu-id="c51fc-108">The functionality has been moved to the `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` package.</span></span>

<span data-ttu-id="c51fc-109">Las siguientes API estaban disponibles anteriormente en `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions` para admitir la compilación en entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="c51fc-109">The following APIs were previously available in `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions` to support runtime compilation.</span></span> <span data-ttu-id="c51fc-110">Las API ahora están disponibles mediante `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation.MvcRazorRuntimeCompilationOptions`.</span><span class="sxs-lookup"><span data-stu-id="c51fc-110">The APIs are now available via `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation.MvcRazorRuntimeCompilationOptions`.</span></span>

- `RazorViewEngineOptions.FileProviders` -> `MvcRazorRuntimeCompilationOptions.FileProviders`
- `RazorViewEngineOptions.AdditionalCompilationReferences` -> `MvcRazorRuntimeCompilationOptions.AdditionalReferencePaths`

<span data-ttu-id="c51fc-111">Además, se ha quitado `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions.AllowRecompilingViewsOnFileChange`.</span><span class="sxs-lookup"><span data-stu-id="c51fc-111">In addition, `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions.AllowRecompilingViewsOnFileChange` has been removed.</span></span> <span data-ttu-id="c51fc-112">La recompilación en los cambios de archivo está habilitada de forma predeterminada al hacer referencia al paquete `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation`.</span><span class="sxs-lookup"><span data-stu-id="c51fc-112">Recompilation on file changes is enabled by default by referencing the `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` package.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="c51fc-113">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="c51fc-113">Reason for change</span></span>

<span data-ttu-id="c51fc-114">Este cambio era necesario para quitar la dependencia de marco compartido de ASP.NET Core en Roslyn.</span><span class="sxs-lookup"><span data-stu-id="c51fc-114">This change was necessary to remove the ASP.NET Core shared framework dependency on Roslyn.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="c51fc-115">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="c51fc-115">Recommended action</span></span>

<span data-ttu-id="c51fc-116">Las aplicaciones que requieren la compilación o recompilación en entorno de ejecución de archivos Razor deben realizar los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="c51fc-116">Apps that require runtime compilation or recompilation of Razor files should take the following steps:</span></span>

1. <span data-ttu-id="c51fc-117">Agregar una referencia al paquete `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation`.</span><span class="sxs-lookup"><span data-stu-id="c51fc-117">Add a reference to the `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation` package.</span></span>
1. <span data-ttu-id="c51fc-118">Actualizar el método `Startup.ConfigureServices` del proyecto para incluir una llamada a `AddMvcRazorRuntimeCompilation`.</span><span class="sxs-lookup"><span data-stu-id="c51fc-118">Update the project's `Startup.ConfigureServices` method to include a call to `AddMvcRazorRuntimeCompilation`.</span></span> <span data-ttu-id="c51fc-119">Por ejemplo, en `Startup.ConfigureServices`:</span><span class="sxs-lookup"><span data-stu-id="c51fc-119">For example, in `Startup.ConfigureServices`:</span></span>

    ```csharp
    services.AddMvc()
        .AddMvcRazorRuntimeCompilation();
    ```

#### <a name="category"></a><span data-ttu-id="c51fc-120">Categoría</span><span class="sxs-lookup"><span data-stu-id="c51fc-120">Category</span></span>

<span data-ttu-id="c51fc-121">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c51fc-121">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="c51fc-122">API afectadas</span><span class="sxs-lookup"><span data-stu-id="c51fc-122">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions?displayProperty=fullName>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions`

-->
