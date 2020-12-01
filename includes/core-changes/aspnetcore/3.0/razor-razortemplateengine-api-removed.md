---
ms.openlocfilehash: 35dd8db243b03e1dfd6311195ec97673cf114877
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032845"
---
### <a name="razor-razortemplateengine-api-removed"></a>Razor: API RazorTemplateEngine eliminada

Se ha quitado la API [RazorTemplateEngine](/dotnet/api/microsoft.aspnetcore.razor.language.razortemplateengine?view=aspnetcore-2.2) y se ha reemplazado por <xref:Microsoft.AspNetCore.Razor.Language.RazorProjectEngine>.

Para obtener información, vea la incidencia de GitHub [dotnet/aspnetcore#25215](https://github.com/dotnet/aspnetcore/issues/25215).

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="old-behavior"></a>Comportamiento anterior

Un motor de plantillas se puede crear y usar para analizar y generar código para archivos de Razor.

#### <a name="new-behavior"></a>Comportamiento nuevo

Se puede crear `RazorProjectEngine` y se le puede proporcionar el mismo tipo de información que a `RazorTemplateEngine` para analizar y generar código para archivos de Razor. `RazorProjectEngine` también proporciona niveles de configuración adicionales.

#### <a name="reason-for-change"></a>Motivo del cambio

`RazorTemplateEngine` estaba demasiado acoplado a las implementaciones existentes. Este acoplamiento tan estrecho daba lugar a más preguntas al intentar configurar correctamente una canalización de análisis y generación de Razor.

#### <a name="recommended-action"></a>Acción recomendada

Use `RazorProjectEngine` en lugar de `RazorTemplateEngine`. Considere los ejemplos siguientes.

##### <a name="create-and-configure-the-razorprojectengine"></a>Creación y configuración de RazorProjectEngine

```csharp
RazorProjectEngine projectEngine =
    RazorProjectEngine.Create(RazorConfiguration.Default,
        RazorProjectFileSystem.Create(@"C:\source\repos\ConsoleApp4\ConsoleApp4"),
        builder =>
        {
            builder.ConfigureClass((document, classNode) =>
            {
                classNode.ClassName = "MyClassName";

                // Can also configure other aspects of the class here.
            });

            // More configuration can go here
        });
```

##### <a name="generate-code-for-a-razor-file"></a>Generación de código para un archivo de Razor

```csharp
RazorProjectItem item = projectEngine.FileSystem.GetItem(
    @"C:\source\repos\ConsoleApp4\ConsoleApp4\Example.cshtml",
    FileKinds.Legacy);
RazorCodeDocument output = projectEngine.Process(item);

// Things available
RazorSyntaxTree syntaxTree = output.GetSyntaxTree();
DocumentIntermediateNode intermediateDocument =
    output.GetDocumentIntermediateNode();
RazorCSharpDocument csharpDocument = output.GetCSharpDocument();
```

#### <a name="category"></a>Categoría

ASP.NET Core

#### <a name="affected-apis"></a>API afectadas

- [RazorTemplateEngine](/dotnet/api/microsoft.aspnetcore.razor.language.razortemplateengine?view=aspnetcore-2.2)
- [RazorTemplateEngineOptions](/dotnet/api/microsoft.aspnetcore.razor.language.razortemplateengineoptions?view=aspnetcore-2.2)

<!--

#### Affected APIs

- `T:Microsoft.AspNetCore.Razor.Language.RazorTemplateEngine`
- `T:Microsoft.AspNetCore.Razor.Language.RazorTemplateEngineOptions`

-->
