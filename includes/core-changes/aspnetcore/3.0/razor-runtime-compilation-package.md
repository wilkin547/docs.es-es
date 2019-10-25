---
ms.openlocfilehash: 8479168b64153d3c729f8814a2649df8d46f2135
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394192"
---
### <a name="razor-runtime-compilation-moved-to-a-package"></a>Razor: la compilación en entorno de ejecución se ha movido a un paquete

La compatibilidad con la compilación en entorno de ejecución de las vistas de Razor y Razor Pages se ha movido a un paquete independiente.

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="old-behavior"></a>Comportamiento anterior

La compilación en entorno de ejecución está disponible sin necesidad de paquetes adicionales.

#### <a name="new-behavior"></a>Comportamiento nuevo

La funcionalidad se ha movido al paquete `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation`.

Las siguientes API estaban disponibles anteriormente en `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions` para admitir la compilación en entorno de ejecución. Las API ahora están disponibles mediante `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation.MvcRazorRuntimeCompilationOptions`.

- `RazorViewEngineOptions.FileProviders` -> `MvcRazorRuntimeCompilationOptions.FileProviders`
- `RazorViewEngineOptions.AdditionalCompilationReferences` -> `MvcRazorRuntimeCompilationOptions.AdditionalReferencePaths`

Además, se ha quitado `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions.AllowRecompilingViewsOnFileChange`. La recompilación en los cambios de archivo está habilitada de forma predeterminada al hacer referencia al paquete `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation`.

#### <a name="reason-for-change"></a>Motivo del cambio

Este cambio era necesario para quitar la dependencia de marco compartido de ASP.NET Core en Roslyn.

#### <a name="recommended-action"></a>Acción recomendada

Las aplicaciones que requieren la compilación o recompilación en entorno de ejecución de archivos Razor deben realizar los pasos siguientes:

1. Agregar una referencia al paquete `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation`.
1. Actualizar el método `Startup.ConfigureServices` del proyecto para incluir una llamada a `AddMvcRazorRuntimeCompilation`. Por ejemplo, en `Startup.ConfigureServices`:

    ```csharp
    services.AddMvc()
        .AddMvcRazorRuntimeCompilation();
    ```

#### <a name="category"></a>Categoría

ASP.NET Core

#### <a name="affected-apis"></a>API afectadas

<xref:Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions?displayProperty=fullName>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions`

-->
