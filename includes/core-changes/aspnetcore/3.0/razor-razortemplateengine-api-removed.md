---
ms.openlocfilehash: 35dd8db243b03e1dfd6311195ec97673cf114877
ms.sourcegitcommit: 60dc0a11ebdd77f969f41891d5cca06335cda6a7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2020
ms.locfileid: "88957696"
---
### <a name="razor-razortemplateengine-api-removed"></a><span data-ttu-id="c80c5-101">Razor: API RazorTemplateEngine eliminada</span><span class="sxs-lookup"><span data-stu-id="c80c5-101">Razor: RazorTemplateEngine API removed</span></span>

<span data-ttu-id="c80c5-102">Se ha quitado la API [RazorTemplateEngine](/dotnet/api/microsoft.aspnetcore.razor.language.razortemplateengine?view=aspnetcore-2.2) y se ha reemplazado por <xref:Microsoft.AspNetCore.Razor.Language.RazorProjectEngine>.</span><span class="sxs-lookup"><span data-stu-id="c80c5-102">The [RazorTemplateEngine](/dotnet/api/microsoft.aspnetcore.razor.language.razortemplateengine?view=aspnetcore-2.2) API was removed and replaced with <xref:Microsoft.AspNetCore.Razor.Language.RazorProjectEngine>.</span></span>

<span data-ttu-id="c80c5-103">Para obtener información, vea la incidencia de GitHub [dotnet/aspnetcore#25215](https://github.com/dotnet/aspnetcore/issues/25215).</span><span class="sxs-lookup"><span data-stu-id="c80c5-103">For discussion, see GitHub issue [dotnet/aspnetcore#25215](https://github.com/dotnet/aspnetcore/issues/25215).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="c80c5-104">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="c80c5-104">Version introduced</span></span>

<span data-ttu-id="c80c5-105">3.0</span><span class="sxs-lookup"><span data-stu-id="c80c5-105">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="c80c5-106">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="c80c5-106">Old behavior</span></span>

<span data-ttu-id="c80c5-107">Un motor de plantillas se puede crear y usar para analizar y generar código para archivos de Razor.</span><span class="sxs-lookup"><span data-stu-id="c80c5-107">A template engine can be created and used to parse and generate code for Razor files.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="c80c5-108">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="c80c5-108">New behavior</span></span>

<span data-ttu-id="c80c5-109">Se puede crear `RazorProjectEngine` y se le puede proporcionar el mismo tipo de información que a `RazorTemplateEngine` para analizar y generar código para archivos de Razor.</span><span class="sxs-lookup"><span data-stu-id="c80c5-109">`RazorProjectEngine` can be created and provided the same type of information as `RazorTemplateEngine` to parse and generate code for Razor files.</span></span> <span data-ttu-id="c80c5-110">`RazorProjectEngine` también proporciona niveles de configuración adicionales.</span><span class="sxs-lookup"><span data-stu-id="c80c5-110">`RazorProjectEngine` also provides extra levels of configuration.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="c80c5-111">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="c80c5-111">Reason for change</span></span>

<span data-ttu-id="c80c5-112">`RazorTemplateEngine` estaba demasiado acoplado a las implementaciones existentes.</span><span class="sxs-lookup"><span data-stu-id="c80c5-112">`RazorTemplateEngine` was too tightly coupled to the existing implementations.</span></span> <span data-ttu-id="c80c5-113">Este acoplamiento tan estrecho daba lugar a más preguntas al intentar configurar correctamente una canalización de análisis y generación de Razor.</span><span class="sxs-lookup"><span data-stu-id="c80c5-113">This tight coupling led to more questions when trying to properly configure a Razor parsing/generation pipeline.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="c80c5-114">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="c80c5-114">Recommended action</span></span>

<span data-ttu-id="c80c5-115">Use `RazorProjectEngine` en lugar de `RazorTemplateEngine`.</span><span class="sxs-lookup"><span data-stu-id="c80c5-115">Use `RazorProjectEngine` instead of `RazorTemplateEngine`.</span></span> <span data-ttu-id="c80c5-116">Considere los ejemplos siguientes.</span><span class="sxs-lookup"><span data-stu-id="c80c5-116">Consider the following examples.</span></span>

##### <a name="create-and-configure-the-razorprojectengine"></a><span data-ttu-id="c80c5-117">Creación y configuración de RazorProjectEngine</span><span class="sxs-lookup"><span data-stu-id="c80c5-117">Create and configure the RazorProjectEngine</span></span>

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

##### <a name="generate-code-for-a-razor-file"></a><span data-ttu-id="c80c5-118">Generación de código para un archivo de Razor</span><span class="sxs-lookup"><span data-stu-id="c80c5-118">Generate code for a Razor file</span></span>

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

#### <a name="category"></a><span data-ttu-id="c80c5-119">Categoría</span><span class="sxs-lookup"><span data-stu-id="c80c5-119">Category</span></span>

<span data-ttu-id="c80c5-120">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c80c5-120">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="c80c5-121">API afectadas</span><span class="sxs-lookup"><span data-stu-id="c80c5-121">Affected APIs</span></span>

- [<span data-ttu-id="c80c5-122">RazorTemplateEngine</span><span class="sxs-lookup"><span data-stu-id="c80c5-122">RazorTemplateEngine</span></span>](/dotnet/api/microsoft.aspnetcore.razor.language.razortemplateengine?view=aspnetcore-2.2)
- [<span data-ttu-id="c80c5-123">RazorTemplateEngineOptions</span><span class="sxs-lookup"><span data-stu-id="c80c5-123">RazorTemplateEngineOptions</span></span>](/dotnet/api/microsoft.aspnetcore.razor.language.razortemplateengineoptions?view=aspnetcore-2.2)

<!--

#### Affected APIs

- `T:Microsoft.AspNetCore.Razor.Language.RazorTemplateEngine`
- `T:Microsoft.AspNetCore.Razor.Language.RazorTemplateEngineOptions`

-->
