---
ms.openlocfilehash: cd13e7560ee98e0c862c5e2293521c6aaa273455
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75344304"
---
### <a name="razor-runtime-compilation-moved-to-a-package"></a>Razor: la compilación en entorno de ejecución se ha movido a un paquete

La compatibilidad con la compilación en entorno de ejecución de las vistas de Razor y Razor Pages se ha movido a un paquete independiente.

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="old-behavior"></a>Comportamiento anterior

La compilación en entorno de ejecución está disponible sin necesidad de paquetes adicionales.

#### <a name="new-behavior"></a>Comportamiento nuevo

La funcionalidad se ha pasado al paquete [Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation](https://www.nuget.org/packages/Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation/).

Las siguientes API estaban disponibles anteriormente en `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions` para admitir la compilación en entorno de ejecución. Las API ahora están disponibles mediante `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation.MvcRazorRuntimeCompilationOptions`.

- `RazorViewEngineOptions.FileProviders` es ahora `MvcRazorRuntimeCompilationOptions.FileProviders`
- `RazorViewEngineOptions.AdditionalCompilationReferences` es ahora `MvcRazorRuntimeCompilationOptions.AdditionalReferencePaths`

Además, se ha quitado `Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions.AllowRecompilingViewsOnFileChange`. La recompilación en los cambios de archivo está habilitada de forma predeterminada al hacer referencia al paquete `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation`.

#### <a name="reason-for-change"></a>Motivo del cambio

Este cambio era necesario para quitar la dependencia de marco compartido de ASP.NET Core en Roslyn.

#### <a name="recommended-action"></a>Acción recomendada

Las aplicaciones que requieren la compilación o recompilación en entorno de ejecución de archivos Razor deben realizar los pasos siguientes:

1. Agregar una referencia al paquete `Microsoft.AspNetCore.Mvc.Razor.RuntimeCompilation`.
1. Actualizar el método `Startup.ConfigureServices` del proyecto para incluir una llamada a `AddRazorRuntimeCompilation`. Por ejemplo:

    ```csharp
    services.AddMvc()
        .AddRazorRuntimeCompilation();
    ```

#### <a name="category"></a>Categoría

ASP.NET Core

#### <a name="affected-apis"></a>API afectadas

<xref:Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions?displayProperty=fullName>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.Mvc.Razor.RazorViewEngineOptions`

-->
