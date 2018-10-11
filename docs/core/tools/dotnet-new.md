---
title: 'Comando dotnet new: CLI de .NET Core'
description: El comando dotnet new crea proyectos de .NET Core basados en la plantilla especificada.
author: mairaw
ms.author: mairaw
ms.date: 07/31/2018
ms.openlocfilehash: 396c4ddf09854fa4582226bdb1422f8c929e459b
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2018
ms.locfileid: "47208638"
---
# <a name="dotnet-new"></a><span data-ttu-id="c0e25-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="c0e25-103">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="c0e25-104">nombre</span><span class="sxs-lookup"><span data-stu-id="c0e25-104">Name</span></span>

<span data-ttu-id="c0e25-105">`dotnet new`: crea un nuevo proyecto, archivo de configuración o solución según la plantilla especificada.</span><span class="sxs-lookup"><span data-stu-id="c0e25-105">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="c0e25-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="c0e25-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="c0e25-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="c0e25-107">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output]
    [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="c0e25-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="c0e25-108">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c0e25-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c0e25-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="c0e25-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="c0e25-110">Description</span></span>

<span data-ttu-id="c0e25-111">El comando `dotnet new` proporciona una manera cómoda de inicializar un proyecto .NET Core válido.</span><span class="sxs-lookup"><span data-stu-id="c0e25-111">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span>

<span data-ttu-id="c0e25-112">El comando llama al [motor de plantillas](https://github.com/dotnet/templating) para crear los artefactos en el disco basándose en las opciones y la plantilla especificadas.</span><span class="sxs-lookup"><span data-stu-id="c0e25-112">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="c0e25-113">Argumentos</span><span class="sxs-lookup"><span data-stu-id="c0e25-113">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="c0e25-114">La plantilla de la que se va a crear una instancia cuando se invoca el comando.</span><span class="sxs-lookup"><span data-stu-id="c0e25-114">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="c0e25-115">Cada plantilla puede tener opciones específicas que puede pasar.</span><span class="sxs-lookup"><span data-stu-id="c0e25-115">Each template might have specific options you can pass.</span></span> <span data-ttu-id="c0e25-116">Para obtener más información, vea [Opciones de plantilla](#template-options).</span><span class="sxs-lookup"><span data-stu-id="c0e25-116">For more information, see [Template options](#template-options).</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="c0e25-117">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="c0e25-117">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="c0e25-118">El comando contiene una lista predeterminada de plantillas.</span><span class="sxs-lookup"><span data-stu-id="c0e25-118">The command contains a default list of templates.</span></span> <span data-ttu-id="c0e25-119">Use `dotnet new -l` para obtener una lista de las plantillas disponibles.</span><span class="sxs-lookup"><span data-stu-id="c0e25-119">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="c0e25-120">En la tabla siguiente se muestran las plantillas que vienen preinstaladas con el SDK de .NET Core 2.1.300.</span><span class="sxs-lookup"><span data-stu-id="c0e25-120">The following table shows the templates that come pre-installed with the .NET Core SDK 2.1.300.</span></span> <span data-ttu-id="c0e25-121">El lenguaje predeterminado de la plantilla se muestra entre corchetes.</span><span class="sxs-lookup"><span data-stu-id="c0e25-121">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="c0e25-122">Descripción de plantilla</span><span class="sxs-lookup"><span data-stu-id="c0e25-122">Template description</span></span>                          | <span data-ttu-id="c0e25-123">Nombre de plantilla</span><span class="sxs-lookup"><span data-stu-id="c0e25-123">Template name</span></span>   | <span data-ttu-id="c0e25-124">Lenguajes</span><span class="sxs-lookup"><span data-stu-id="c0e25-124">Languages</span></span>     |
|----------------------------------------------|-----------------|---------------|
| <span data-ttu-id="c0e25-125">Aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="c0e25-125">Console application</span></span>                          | `console`       | <span data-ttu-id="c0e25-126">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="c0e25-126">[C#], F#, VB</span></span>  |
| <span data-ttu-id="c0e25-127">Biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="c0e25-127">Class library</span></span>                                | `classlib`      | <span data-ttu-id="c0e25-128">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="c0e25-128">[C#], F#, VB</span></span>  |
| <span data-ttu-id="c0e25-129">Proyecto de prueba unitaria</span><span class="sxs-lookup"><span data-stu-id="c0e25-129">Unit test project</span></span>                            | `mstest`        | <span data-ttu-id="c0e25-130">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="c0e25-130">[C#], F#, VB</span></span>  |
| <span data-ttu-id="c0e25-131">Proyecto de prueba xUnit</span><span class="sxs-lookup"><span data-stu-id="c0e25-131">xUnit test project</span></span>                           | `xunit`         | <span data-ttu-id="c0e25-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="c0e25-132">[C#], F#, VB</span></span>  |
| <span data-ttu-id="c0e25-133">Página de Razor</span><span class="sxs-lookup"><span data-stu-id="c0e25-133">Razor page</span></span>                                   | `page`          | <span data-ttu-id="c0e25-134">[C#]</span><span class="sxs-lookup"><span data-stu-id="c0e25-134">[C#]</span></span>          |
| <span data-ttu-id="c0e25-135">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="c0e25-135">MVC ViewImports</span></span>                              | `viewimports`   | <span data-ttu-id="c0e25-136">[C#]</span><span class="sxs-lookup"><span data-stu-id="c0e25-136">[C#]</span></span>          |
| <span data-ttu-id="c0e25-137">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="c0e25-137">MVC ViewStart</span></span>                                | `viewstart`     | <span data-ttu-id="c0e25-138">[C#]</span><span class="sxs-lookup"><span data-stu-id="c0e25-138">[C#]</span></span>          |
| <span data-ttu-id="c0e25-139">Vacío de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c0e25-139">ASP.NET Core empty</span></span>                           | `web`           | <span data-ttu-id="c0e25-140">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="c0e25-140">[C#], F#</span></span>      |
| <span data-ttu-id="c0e25-141">Aplicación web de ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="c0e25-141">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`           | <span data-ttu-id="c0e25-142">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="c0e25-142">[C#], F#</span></span>      |
| <span data-ttu-id="c0e25-143">Aplicación web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c0e25-143">ASP.NET Core Web App</span></span>                         | `razor`         | <span data-ttu-id="c0e25-144">[C#]</span><span class="sxs-lookup"><span data-stu-id="c0e25-144">[C#]</span></span>          |
| <span data-ttu-id="c0e25-145">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="c0e25-145">ASP.NET Core with Angular</span></span>                    | `angular`       | <span data-ttu-id="c0e25-146">[C#]</span><span class="sxs-lookup"><span data-stu-id="c0e25-146">[C#]</span></span>          |
| <span data-ttu-id="c0e25-147">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="c0e25-147">ASP.NET Core with React.js</span></span>                   | `react`         | <span data-ttu-id="c0e25-148">[C#]</span><span class="sxs-lookup"><span data-stu-id="c0e25-148">[C#]</span></span>          |
| <span data-ttu-id="c0e25-149">ASP.NET Core con React.js y Redux</span><span class="sxs-lookup"><span data-stu-id="c0e25-149">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`    | <span data-ttu-id="c0e25-150">[C#]</span><span class="sxs-lookup"><span data-stu-id="c0e25-150">[C#]</span></span>          |
| <span data-ttu-id="c0e25-151">API web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c0e25-151">ASP.NET Core Web API</span></span>                         | `webapi`        | <span data-ttu-id="c0e25-152">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="c0e25-152">[C#], F#</span></span>      |
| <span data-ttu-id="c0e25-153">Biblioteca de clases de Razor</span><span class="sxs-lookup"><span data-stu-id="c0e25-153">Razor class library</span></span>                          | `razorclasslib` | <span data-ttu-id="c0e25-154">[C#]</span><span class="sxs-lookup"><span data-stu-id="c0e25-154">[C#]</span></span>          |
| <span data-ttu-id="c0e25-155">archivo global.json</span><span class="sxs-lookup"><span data-stu-id="c0e25-155">global.json file</span></span>                             | `globaljson`    |               |
| <span data-ttu-id="c0e25-156">Configuración de NuGet</span><span class="sxs-lookup"><span data-stu-id="c0e25-156">NuGet config</span></span>                                 | `nugetconfig`   |               |
| <span data-ttu-id="c0e25-157">Configuración de la Web</span><span class="sxs-lookup"><span data-stu-id="c0e25-157">Web config</span></span>                                   | `webconfig`     |               |
| <span data-ttu-id="c0e25-158">Archivo de solución</span><span class="sxs-lookup"><span data-stu-id="c0e25-158">Solution file</span></span>                                | `sln`           |               |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="c0e25-159">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="c0e25-159">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="c0e25-160">El comando contiene una lista predeterminada de plantillas.</span><span class="sxs-lookup"><span data-stu-id="c0e25-160">The command contains a default list of templates.</span></span> <span data-ttu-id="c0e25-161">Use `dotnet new -l` para obtener una lista de las plantillas disponibles.</span><span class="sxs-lookup"><span data-stu-id="c0e25-161">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="c0e25-162">En la tabla siguiente se muestran las plantillas que vienen preinstaladas con el SDK de .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="c0e25-162">The following table shows the templates that come pre-installed with the .NET Core SDK 2.0.</span></span> <span data-ttu-id="c0e25-163">El lenguaje predeterminado de la plantilla se muestra entre corchetes.</span><span class="sxs-lookup"><span data-stu-id="c0e25-163">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="c0e25-164">Descripción de plantilla</span><span class="sxs-lookup"><span data-stu-id="c0e25-164">Template description</span></span>                          | <span data-ttu-id="c0e25-165">Nombre de plantilla</span><span class="sxs-lookup"><span data-stu-id="c0e25-165">Template name</span></span> | <span data-ttu-id="c0e25-166">Lenguajes</span><span class="sxs-lookup"><span data-stu-id="c0e25-166">Languages</span></span>     |
|----------------------------------------------|---------------|---------------|
| <span data-ttu-id="c0e25-167">Aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="c0e25-167">Console application</span></span>                          | `console`     | <span data-ttu-id="c0e25-168">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="c0e25-168">[C#], F#, VB</span></span>  |
| <span data-ttu-id="c0e25-169">Biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="c0e25-169">Class library</span></span>                                | `classlib`    | <span data-ttu-id="c0e25-170">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="c0e25-170">[C#], F#, VB</span></span>  |
| <span data-ttu-id="c0e25-171">Proyecto de prueba unitaria</span><span class="sxs-lookup"><span data-stu-id="c0e25-171">Unit test project</span></span>                            | `mstest`      | <span data-ttu-id="c0e25-172">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="c0e25-172">[C#], F#, VB</span></span>  |
| <span data-ttu-id="c0e25-173">Proyecto de prueba xUnit</span><span class="sxs-lookup"><span data-stu-id="c0e25-173">xUnit test project</span></span>                           | `xunit`       | <span data-ttu-id="c0e25-174">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="c0e25-174">[C#], F#, VB</span></span>  |
| <span data-ttu-id="c0e25-175">Vacío de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c0e25-175">ASP.NET Core empty</span></span>                           | `web`         | <span data-ttu-id="c0e25-176">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="c0e25-176">[C#], F#</span></span>      |
| <span data-ttu-id="c0e25-177">Aplicación web de ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="c0e25-177">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="c0e25-178">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="c0e25-178">[C#], F#</span></span>      |
| <span data-ttu-id="c0e25-179">Aplicación web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c0e25-179">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="c0e25-180">[C#]</span><span class="sxs-lookup"><span data-stu-id="c0e25-180">[C#]</span></span>          |
| <span data-ttu-id="c0e25-181">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="c0e25-181">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="c0e25-182">[C#]</span><span class="sxs-lookup"><span data-stu-id="c0e25-182">[C#]</span></span>          |
| <span data-ttu-id="c0e25-183">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="c0e25-183">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="c0e25-184">[C#]</span><span class="sxs-lookup"><span data-stu-id="c0e25-184">[C#]</span></span>          |
| <span data-ttu-id="c0e25-185">ASP.NET Core con React.js y Redux</span><span class="sxs-lookup"><span data-stu-id="c0e25-185">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="c0e25-186">[C#]</span><span class="sxs-lookup"><span data-stu-id="c0e25-186">[C#]</span></span>          |
| <span data-ttu-id="c0e25-187">API web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c0e25-187">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="c0e25-188">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="c0e25-188">[C#], F#</span></span>      |
| <span data-ttu-id="c0e25-189">archivo global.json</span><span class="sxs-lookup"><span data-stu-id="c0e25-189">global.json file</span></span>                             | `globaljson`  |               |
| <span data-ttu-id="c0e25-190">Configuración de NuGet</span><span class="sxs-lookup"><span data-stu-id="c0e25-190">NuGet config</span></span>                                 | `nugetconfig` |               |
| <span data-ttu-id="c0e25-191">Configuración de la Web</span><span class="sxs-lookup"><span data-stu-id="c0e25-191">Web config</span></span>                                   | `webconfig`   |               |
| <span data-ttu-id="c0e25-192">Archivo de solución</span><span class="sxs-lookup"><span data-stu-id="c0e25-192">Solution file</span></span>                                | `sln`         |               |
| <span data-ttu-id="c0e25-193">Página de Razor</span><span class="sxs-lookup"><span data-stu-id="c0e25-193">Razor page</span></span>                                   | `page`        |               |
| <span data-ttu-id="c0e25-194">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="c0e25-194">MVC ViewImports</span></span>                              | `viewimports` |               |
| <span data-ttu-id="c0e25-195">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="c0e25-195">MVC ViewStart</span></span>                                | `viewstart`   |               |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c0e25-196">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c0e25-196">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="c0e25-197">El comando contiene una lista predeterminada de plantillas.</span><span class="sxs-lookup"><span data-stu-id="c0e25-197">The command contains a default list of templates.</span></span> <span data-ttu-id="c0e25-198">Use `dotnet new -all` para obtener una lista de las plantillas disponibles.</span><span class="sxs-lookup"><span data-stu-id="c0e25-198">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="c0e25-199">En la tabla siguiente se muestran las plantillas que vienen preinstaladas con el SDK de .NET 1.x.</span><span class="sxs-lookup"><span data-stu-id="c0e25-199">The following table shows the templates that come pre-installed with the .NET Core SDK 1.x.</span></span> <span data-ttu-id="c0e25-200">El lenguaje predeterminado de la plantilla se muestra entre corchetes.</span><span class="sxs-lookup"><span data-stu-id="c0e25-200">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="c0e25-201">Descripción de plantilla</span><span class="sxs-lookup"><span data-stu-id="c0e25-201">Template description</span></span>  | <span data-ttu-id="c0e25-202">Nombre de plantilla</span><span class="sxs-lookup"><span data-stu-id="c0e25-202">Template name</span></span> | <span data-ttu-id="c0e25-203">Lenguajes</span><span class="sxs-lookup"><span data-stu-id="c0e25-203">Languages</span></span> |
|----------------------|---------------|-----------|
| <span data-ttu-id="c0e25-204">Aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="c0e25-204">Console application</span></span>  | `console`     | <span data-ttu-id="c0e25-205">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="c0e25-205">[C#], F#</span></span>  |
| <span data-ttu-id="c0e25-206">Biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="c0e25-206">Class library</span></span>        | `classlib`    | <span data-ttu-id="c0e25-207">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="c0e25-207">[C#], F#</span></span>  |
| <span data-ttu-id="c0e25-208">Proyecto de prueba unitaria</span><span class="sxs-lookup"><span data-stu-id="c0e25-208">Unit test project</span></span>    | `mstest`      | <span data-ttu-id="c0e25-209">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="c0e25-209">[C#], F#</span></span>  |
| <span data-ttu-id="c0e25-210">Proyecto de prueba xUnit</span><span class="sxs-lookup"><span data-stu-id="c0e25-210">xUnit test project</span></span>   | `xunit`       | <span data-ttu-id="c0e25-211">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="c0e25-211">[C#], F#</span></span>  |
| <span data-ttu-id="c0e25-212">Vacío de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c0e25-212">ASP.NET Core empty</span></span>   | `web`         | <span data-ttu-id="c0e25-213">[C#]</span><span class="sxs-lookup"><span data-stu-id="c0e25-213">[C#]</span></span>      |
| <span data-ttu-id="c0e25-214">Aplicación web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c0e25-214">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="c0e25-215">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="c0e25-215">[C#], F#</span></span>  |
| <span data-ttu-id="c0e25-216">API web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c0e25-216">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="c0e25-217">[C#]</span><span class="sxs-lookup"><span data-stu-id="c0e25-217">[C#]</span></span>      |
| <span data-ttu-id="c0e25-218">Configuración de NuGet</span><span class="sxs-lookup"><span data-stu-id="c0e25-218">NuGet config</span></span>         | `nugetconfig` |           |
| <span data-ttu-id="c0e25-219">Configuración de la Web</span><span class="sxs-lookup"><span data-stu-id="c0e25-219">Web config</span></span>           | `webconfig`   |           |
| <span data-ttu-id="c0e25-220">Archivo de solución</span><span class="sxs-lookup"><span data-stu-id="c0e25-220">Solution file</span></span>        | `sln`         |           |

---

## <a name="options"></a><span data-ttu-id="c0e25-221">Opciones</span><span class="sxs-lookup"><span data-stu-id="c0e25-221">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="c0e25-222">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="c0e25-222">.NET Core 2.1</span></span>](#tab/netcore21)

`--force`

<span data-ttu-id="c0e25-223">Fuerza la generación de contenido incluso aunque se vayan a cambiar los archivos existentes.</span><span class="sxs-lookup"><span data-stu-id="c0e25-223">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="c0e25-224">Esto es necesario cuando el directorio de salida ya contiene un proyecto.</span><span class="sxs-lookup"><span data-stu-id="c0e25-224">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="c0e25-225">Imprime la ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="c0e25-225">Prints out help for the command.</span></span> <span data-ttu-id="c0e25-226">Puede invocarse para el propio comando `dotnet new` o para cualquier plantilla, como `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-226">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="c0e25-227">Instala un paquete de plantillas u origen desde los parámetros `PATH` o `NUGET_ID` proporcionados.</span><span class="sxs-lookup"><span data-stu-id="c0e25-227">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="c0e25-228">Si quiere instalar una versión preliminar de un paquete de plantilla, tendrá que especificar la versión en el formato de `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-228">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="c0e25-229">De manera predeterminada, `dotnet new` pasa \* para la versión, que representa la última versión estable del paquete.</span><span class="sxs-lookup"><span data-stu-id="c0e25-229">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="c0e25-230">Vea un ejemplo en la sección [Ejemplos](#examples).</span><span class="sxs-lookup"><span data-stu-id="c0e25-230">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="c0e25-231">Para obtener información sobre cómo crear plantillas personalizadas, consulte [Custom templates for dotnet new](custom-templates.md) (Plantillas personalizadas para dotnet new).</span><span class="sxs-lookup"><span data-stu-id="c0e25-231">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="c0e25-232">Muestra las plantillas que contienen el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="c0e25-232">Lists templates containing the specified name.</span></span> <span data-ttu-id="c0e25-233">Si se invoca para el comando `dotnet new`, muestra las plantillas posibles disponibles para un directorio determinado.</span><span class="sxs-lookup"><span data-stu-id="c0e25-233">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="c0e25-234">Por ejemplo, si el directorio ya contiene un proyecto, no mostrará todas las plantillas del proyecto.</span><span class="sxs-lookup"><span data-stu-id="c0e25-234">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="c0e25-235">El lenguaje de la plantilla que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="c0e25-235">The language of the template to create.</span></span> <span data-ttu-id="c0e25-236">El lenguaje aceptado cambia según la plantilla (vea los valores predeterminados en la sección [argumentos](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="c0e25-236">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="c0e25-237">No es válido para algunas plantillas.</span><span class="sxs-lookup"><span data-stu-id="c0e25-237">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="c0e25-238">Algunos shells interpretan `#` como un carácter especial.</span><span class="sxs-lookup"><span data-stu-id="c0e25-238">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="c0e25-239">En esos casos, debe incluir el valor del parámetro de lenguaje, como `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-239">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="c0e25-240">El nombre de la salida creada.</span><span class="sxs-lookup"><span data-stu-id="c0e25-240">The name for the created output.</span></span> <span data-ttu-id="c0e25-241">Si no se especifica ningún nombre, se usa el nombre del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="c0e25-241">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="c0e25-242">Especifica un origen de NuGet para usarlo durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="c0e25-242">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="c0e25-243">La ubicación para colocar la salida generada.</span><span class="sxs-lookup"><span data-stu-id="c0e25-243">Location to place the generated output.</span></span> <span data-ttu-id="c0e25-244">El valor predeterminado es el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="c0e25-244">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="c0e25-245">Filtra plantillas en función de los tipos disponibles.</span><span class="sxs-lookup"><span data-stu-id="c0e25-245">Filters templates based on available types.</span></span> <span data-ttu-id="c0e25-246">Los valores predefinidos son “project”, “item” y “other”.</span><span class="sxs-lookup"><span data-stu-id="c0e25-246">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="c0e25-247">Desinstala un paquete de plantillas u origen en los parámetros `PATH` o `NUGET_ID` proporcionados.</span><span class="sxs-lookup"><span data-stu-id="c0e25-247">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="c0e25-248">Para desinstalar una plantilla mediante `PATH`, debe usar el nombre completo de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="c0e25-248">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="c0e25-249">Por ejemplo, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* funcionará, pero *./GarciaSoftware.ConsoleTemplate.CSharp* desde la carpeta contenedora no lo hará.</span><span class="sxs-lookup"><span data-stu-id="c0e25-249">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="c0e25-250">Además, no debe incluir una barra diagonal para finalizar el directorio en la ruta de acceso a la plantilla.</span><span class="sxs-lookup"><span data-stu-id="c0e25-250">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="c0e25-251">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="c0e25-251">.NET Core 2.0</span></span>](#tab/netcore20)

`--force`

<span data-ttu-id="c0e25-252">Fuerza la generación de contenido incluso aunque se vayan a cambiar los archivos existentes.</span><span class="sxs-lookup"><span data-stu-id="c0e25-252">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="c0e25-253">Esto es necesario cuando el directorio de salida ya contiene un proyecto.</span><span class="sxs-lookup"><span data-stu-id="c0e25-253">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="c0e25-254">Imprime la ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="c0e25-254">Prints out help for the command.</span></span> <span data-ttu-id="c0e25-255">Puede invocarse para el propio comando `dotnet new` o para cualquier plantilla, como `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-255">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="c0e25-256">Instala un paquete de plantillas u origen desde los parámetros `PATH` o `NUGET_ID` proporcionados.</span><span class="sxs-lookup"><span data-stu-id="c0e25-256">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="c0e25-257">Si quiere instalar una versión preliminar de un paquete de plantilla, tendrá que especificar la versión en el formato de `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-257">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="c0e25-258">De manera predeterminada, `dotnet new` pasa \* para la versión, que representa la última versión estable del paquete.</span><span class="sxs-lookup"><span data-stu-id="c0e25-258">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="c0e25-259">Vea un ejemplo en la sección [Ejemplos](#examples).</span><span class="sxs-lookup"><span data-stu-id="c0e25-259">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="c0e25-260">Para obtener información sobre cómo crear plantillas personalizadas, consulte [Custom templates for dotnet new](custom-templates.md) (Plantillas personalizadas para dotnet new).</span><span class="sxs-lookup"><span data-stu-id="c0e25-260">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="c0e25-261">Muestra las plantillas que contienen el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="c0e25-261">Lists templates containing the specified name.</span></span> <span data-ttu-id="c0e25-262">Si se invoca para el comando `dotnet new`, muestra las plantillas posibles disponibles para un directorio determinado.</span><span class="sxs-lookup"><span data-stu-id="c0e25-262">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="c0e25-263">Por ejemplo, si el directorio ya contiene un proyecto, no mostrará todas las plantillas del proyecto.</span><span class="sxs-lookup"><span data-stu-id="c0e25-263">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="c0e25-264">El lenguaje de la plantilla que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="c0e25-264">The language of the template to create.</span></span> <span data-ttu-id="c0e25-265">El lenguaje aceptado cambia según la plantilla (vea los valores predeterminados en la sección [argumentos](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="c0e25-265">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="c0e25-266">No es válido para algunas plantillas.</span><span class="sxs-lookup"><span data-stu-id="c0e25-266">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="c0e25-267">Algunos shells interpretan `#` como un carácter especial.</span><span class="sxs-lookup"><span data-stu-id="c0e25-267">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="c0e25-268">En esos casos, debe incluir el valor del parámetro de lenguaje, como `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-268">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="c0e25-269">El nombre de la salida creada.</span><span class="sxs-lookup"><span data-stu-id="c0e25-269">The name for the created output.</span></span> <span data-ttu-id="c0e25-270">Si no se especifica ningún nombre, se usa el nombre del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="c0e25-270">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="c0e25-271">La ubicación para colocar la salida generada.</span><span class="sxs-lookup"><span data-stu-id="c0e25-271">Location to place the generated output.</span></span> <span data-ttu-id="c0e25-272">El valor predeterminado es el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="c0e25-272">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="c0e25-273">Filtra plantillas en función de los tipos disponibles.</span><span class="sxs-lookup"><span data-stu-id="c0e25-273">Filters templates based on available types.</span></span> <span data-ttu-id="c0e25-274">Los valores predefinidos son “project”, “item” y “other”.</span><span class="sxs-lookup"><span data-stu-id="c0e25-274">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="c0e25-275">Desinstala un paquete de plantillas u origen en los parámetros `PATH` o `NUGET_ID` proporcionados.</span><span class="sxs-lookup"><span data-stu-id="c0e25-275">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="c0e25-276">Para desinstalar una plantilla mediante un origen `PATH`, debe usar el nombre completo de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="c0e25-276">To uninstall a template using a source `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="c0e25-277">Por ejemplo, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* funcionará, pero *./GarciaSoftware.ConsoleTemplate.CSharp* desde la carpeta contenedora no lo hará.</span><span class="sxs-lookup"><span data-stu-id="c0e25-277">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span> <span data-ttu-id="c0e25-278">Además, no debe incluir una barra diagonal para finalizar el directorio en la ruta de acceso a la plantilla.</span><span class="sxs-lookup"><span data-stu-id="c0e25-278">Additionally, do not include a final terminating directory slash on your template path.</span></span>
> 
> <span data-ttu-id="c0e25-279">Si no puede determinar el argumento `PATH` o `NUGET_ID` necesario para desinstalar una plantilla, la ejecución de `dotnet new --uninstall` sin un argumento enumerará todas las plantillas instaladas y el argumento requerido para desinstalarlas.</span><span class="sxs-lookup"><span data-stu-id="c0e25-279">If you are unable to determine the `PATH` or `NUGET_ID` argument needed to uninstall a template, running `dotnet new --uninstall` without an argument will list all installed templates and the argument required to uninstall them.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c0e25-280">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c0e25-280">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="c0e25-281">Muestra todas las plantillas de un tipo de proyecto específico cuando se ejecuta en el contexto del comando `dotnet new` por sí solo.</span><span class="sxs-lookup"><span data-stu-id="c0e25-281">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="c0e25-282">Cuando se ejecuta en el contexto de una plantilla específica, como `dotnet new web -all`, `-all` se interpreta como una marca para forzar la creación.</span><span class="sxs-lookup"><span data-stu-id="c0e25-282">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="c0e25-283">Esto es necesario cuando el directorio de salida ya contiene un proyecto.</span><span class="sxs-lookup"><span data-stu-id="c0e25-283">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="c0e25-284">Imprime la ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="c0e25-284">Prints out help for the command.</span></span> <span data-ttu-id="c0e25-285">Puede invocarse para el propio comando `dotnet new` o para cualquier plantilla, como `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-285">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="c0e25-286">Muestra las plantillas que contienen el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="c0e25-286">Lists templates containing the specified name.</span></span> <span data-ttu-id="c0e25-287">Si se invoca para el comando `dotnet new`, muestra las plantillas posibles disponibles para un directorio determinado.</span><span class="sxs-lookup"><span data-stu-id="c0e25-287">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="c0e25-288">Por ejemplo, si el directorio ya contiene un proyecto, no mostrará todas las plantillas del proyecto.</span><span class="sxs-lookup"><span data-stu-id="c0e25-288">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="c0e25-289">El lenguaje de la plantilla que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="c0e25-289">The language of the template to create.</span></span> <span data-ttu-id="c0e25-290">El lenguaje aceptado cambia según la plantilla (vea los valores predeterminados en la sección [argumentos](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="c0e25-290">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="c0e25-291">No es válido para algunas plantillas.</span><span class="sxs-lookup"><span data-stu-id="c0e25-291">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="c0e25-292">Algunos shells interpretan `#` como un carácter especial.</span><span class="sxs-lookup"><span data-stu-id="c0e25-292">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="c0e25-293">En esos casos, debe incluir el valor del parámetro de lenguaje, como `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-293">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="c0e25-294">El nombre de la salida creada.</span><span class="sxs-lookup"><span data-stu-id="c0e25-294">The name for the created output.</span></span> <span data-ttu-id="c0e25-295">Si no se especifica ningún nombre, se usa el nombre del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="c0e25-295">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="c0e25-296">La ubicación para colocar la salida generada.</span><span class="sxs-lookup"><span data-stu-id="c0e25-296">Location to place the generated output.</span></span> <span data-ttu-id="c0e25-297">El valor predeterminado es el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="c0e25-297">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="c0e25-298">Opciones de plantilla</span><span class="sxs-lookup"><span data-stu-id="c0e25-298">Template options</span></span>

<span data-ttu-id="c0e25-299">Cada plantilla de proyecto puede tener opciones adicionales disponibles.</span><span class="sxs-lookup"><span data-stu-id="c0e25-299">Each project template may have additional options available.</span></span> <span data-ttu-id="c0e25-300">Las plantillas principales tienen las siguientes opciones adicionales:</span><span class="sxs-lookup"><span data-stu-id="c0e25-300">The core templates have the following additional options:</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="c0e25-301">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="c0e25-301">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="c0e25-302">**console, angular, react, reactredux, razorclasslib**</span><span class="sxs-lookup"><span data-stu-id="c0e25-302">**console, angular, react, reactredux, razorclasslib**</span></span>

  <span data-ttu-id="c0e25-303">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="c0e25-303">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c0e25-304">**classlib**</span><span class="sxs-lookup"><span data-stu-id="c0e25-304">**classlib**</span></span>

<span data-ttu-id="c0e25-305">`-f|--framework <FRAMEWORK>`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="c0e25-305">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c0e25-306">Valores: `netcoreapp2.0` para crear una biblioteca de clases de .NET Core o `netstandard2.0` para crear una biblioteca de clases de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="c0e25-306">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="c0e25-307">El valor predeterminado es `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-307">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="c0e25-308">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="c0e25-308">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c0e25-309">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="c0e25-309">**mstest, xunit**</span></span>

<span data-ttu-id="c0e25-310">`-p|--enable-pack`: habilita el empaquetado para el proyecto mediante [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="c0e25-310">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="c0e25-311">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="c0e25-311">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c0e25-312">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="c0e25-312">**globaljson**</span></span>

<span data-ttu-id="c0e25-313">`--sdk-version <VERSION_NUMBER>`: especifica la versión del SDK de .NET Core que se usará con el archivo *global.json*.</span><span class="sxs-lookup"><span data-stu-id="c0e25-313">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="c0e25-314">**web**</span><span class="sxs-lookup"><span data-stu-id="c0e25-314">**web**</span></span>

<span data-ttu-id="c0e25-315">`--exclude-launch-settings`: excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="c0e25-315">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="c0e25-316">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="c0e25-316">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c0e25-317">`--no-https`: el proyecto no requiere HTTPS.</span><span class="sxs-lookup"><span data-stu-id="c0e25-317">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="c0e25-318">Esta opción solo se aplica si no se usan `IndividualAuth` u `OrganizationalAuth`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-318">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="c0e25-319">**webapi**</span><span class="sxs-lookup"><span data-stu-id="c0e25-319">**webapi**</span></span>

<span data-ttu-id="c0e25-320">`-au|--auth <AUTHENTICATION_TYPE>`: el tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="c0e25-320">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="c0e25-321">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="c0e25-321">The possible values are:</span></span>

- <span data-ttu-id="c0e25-322">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="c0e25-322">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="c0e25-323">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="c0e25-323">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="c0e25-324">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="c0e25-324">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="c0e25-325">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="c0e25-325">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="c0e25-326">`--aad-b2c-instance <INSTANCE>`: la instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="c0e25-326">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="c0e25-327">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-327">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="c0e25-328">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-328">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="c0e25-329">`-ssp|--susi-policy-id <ID>`: el id. de inicio de sesión y de directiva de registro de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="c0e25-329">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="c0e25-330">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-330">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="c0e25-331">`--aad-instance <INSTANCE>`: la instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="c0e25-331">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="c0e25-332">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-332">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="c0e25-333">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-333">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="c0e25-334">`--client-id <ID>`: el id. de cliente para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="c0e25-334">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="c0e25-335">Úsela con las autenticaciones `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-335">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="c0e25-336">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-336">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="c0e25-337">`--domain <DOMAIN>`: el dominio para el inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="c0e25-337">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="c0e25-338">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-338">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="c0e25-339">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-339">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="c0e25-340">`--tenant-id <ID>`: el id. de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="c0e25-340">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="c0e25-341">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-341">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="c0e25-342">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-342">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="c0e25-343">`-r|--org-read-access`: concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="c0e25-343">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="c0e25-344">Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-344">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="c0e25-345">`--exclude-launch-settings`: excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="c0e25-345">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="c0e25-346">`-uld|--use-local-db`: especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="c0e25-346">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="c0e25-347">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-347">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="c0e25-348">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="c0e25-348">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c0e25-349">`--no-https`: el proyecto no requiere HTTPS.</span><span class="sxs-lookup"><span data-stu-id="c0e25-349">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="c0e25-350">`app.UseHsts` y `app.UseHttpsRedirection` no se agregan a `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-350">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="c0e25-351">Esta opción solo se aplica si no se usan `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-351">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="c0e25-352">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="c0e25-352">**mvc, razor**</span></span>

<span data-ttu-id="c0e25-353">`-au|--auth <AUTHENTICATION_TYPE>`: el tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="c0e25-353">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="c0e25-354">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="c0e25-354">The possible values are:</span></span>

- <span data-ttu-id="c0e25-355">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="c0e25-355">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="c0e25-356">`Individual`: autenticación individual.</span><span class="sxs-lookup"><span data-stu-id="c0e25-356">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="c0e25-357">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="c0e25-357">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="c0e25-358">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="c0e25-358">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="c0e25-359">`MultiOrg`: autenticación organizativa para varios inquilinos.</span><span class="sxs-lookup"><span data-stu-id="c0e25-359">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="c0e25-360">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="c0e25-360">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="c0e25-361">`--aad-b2c-instance <INSTANCE>`: la instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="c0e25-361">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="c0e25-362">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-362">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="c0e25-363">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-363">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="c0e25-364">`-ssp|--susi-policy-id <ID>`: el id. de inicio de sesión y de directiva de registro de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="c0e25-364">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="c0e25-365">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-365">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="c0e25-366">`-rp|--reset-password-policy-id <ID>`: el id. de la directiva de restablecimiento de contraseñas para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="c0e25-366">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="c0e25-367">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-367">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="c0e25-368">`-ep|--edit-profile-policy-id <ID>`: el id. de directiva de edición de perfiles para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="c0e25-368">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="c0e25-369">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-369">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="c0e25-370">`--aad-instance <INSTANCE>`: la instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="c0e25-370">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="c0e25-371">Úsela con las autenticaciones `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-371">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="c0e25-372">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-372">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="c0e25-373">`--client-id <ID>`: el id. de cliente para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="c0e25-373">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="c0e25-374">Úsela con las autenticaciones `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-374">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="c0e25-375">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-375">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="c0e25-376">`--domain <DOMAIN>`: el dominio para el inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="c0e25-376">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="c0e25-377">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-377">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="c0e25-378">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-378">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="c0e25-379">`--tenant-id <ID>`: el id. de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="c0e25-379">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="c0e25-380">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-380">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="c0e25-381">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-381">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="c0e25-382">`--callback-path <PATH>`: la ruta de acceso de solicitud de la ruta de acceso de la base de la aplicación del URI de redirección.</span><span class="sxs-lookup"><span data-stu-id="c0e25-382">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="c0e25-383">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-383">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="c0e25-384">El valor predeterminado es `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-384">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="c0e25-385">`-r|--org-read-access`: concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="c0e25-385">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="c0e25-386">Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-386">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="c0e25-387">`--exclude-launch-settings`: excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="c0e25-387">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="c0e25-388">`--use-browserlink`: incluye BrowserLink en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="c0e25-388">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="c0e25-389">`-uld|--use-local-db`: especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="c0e25-389">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="c0e25-390">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-390">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="c0e25-391">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="c0e25-391">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c0e25-392">`--no-https`: el proyecto no requiere HTTPS.</span><span class="sxs-lookup"><span data-stu-id="c0e25-392">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="c0e25-393">`app.UseHsts` y `app.UseHttpsRedirection` no se agregan a `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-393">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="c0e25-394">Esta opción solo se aplica si no se usan `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-394">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="c0e25-395">**page**</span><span class="sxs-lookup"><span data-stu-id="c0e25-395">**page**</span></span>

<span data-ttu-id="c0e25-396">`-na|--namespace <NAMESPACE_NAME>`: espacio de nombres para el código generado.</span><span class="sxs-lookup"><span data-stu-id="c0e25-396">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="c0e25-397">El valor predeterminado es `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-397">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="c0e25-398">`-np|--no-pagemodel`: crea la página sin PageModel.</span><span class="sxs-lookup"><span data-stu-id="c0e25-398">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="c0e25-399">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="c0e25-399">**viewimports**</span></span>

<span data-ttu-id="c0e25-400">`-na|--namespace <NAMESPACE_NAME>`: espacio de nombres para el código generado.</span><span class="sxs-lookup"><span data-stu-id="c0e25-400">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="c0e25-401">El valor predeterminado es `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-401">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="c0e25-402">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="c0e25-402">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="c0e25-403">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="c0e25-403">**console, angular, react, reactredux**</span></span>

  <span data-ttu-id="c0e25-404">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="c0e25-404">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c0e25-405">**classlib**</span><span class="sxs-lookup"><span data-stu-id="c0e25-405">**classlib**</span></span>

<span data-ttu-id="c0e25-406">`-f|--framework <FRAMEWORK>`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="c0e25-406">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c0e25-407">Valores: `netcoreapp2.0` para crear una biblioteca de clases de .NET Core o `netstandard2.0` para crear una biblioteca de clases de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="c0e25-407">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="c0e25-408">El valor predeterminado es `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-408">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="c0e25-409">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="c0e25-409">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c0e25-410">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="c0e25-410">**mstest, xunit**</span></span>

<span data-ttu-id="c0e25-411">`-p|--enable-pack`: habilita el empaquetado para el proyecto mediante [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="c0e25-411">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="c0e25-412">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="c0e25-412">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c0e25-413">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="c0e25-413">**globaljson**</span></span>

<span data-ttu-id="c0e25-414">`--sdk-version <VERSION_NUMBER>`: especifica la versión del SDK de .NET Core que se usará con el archivo *global.json*.</span><span class="sxs-lookup"><span data-stu-id="c0e25-414">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="c0e25-415">**web**</span><span class="sxs-lookup"><span data-stu-id="c0e25-415">**web**</span></span>

<span data-ttu-id="c0e25-416">`--use-launch-settings`: incluye *launchSettings.json* en la salida de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="c0e25-416">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="c0e25-417">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="c0e25-417">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c0e25-418">**webapi**</span><span class="sxs-lookup"><span data-stu-id="c0e25-418">**webapi**</span></span>

<span data-ttu-id="c0e25-419">`-au|--auth <AUTHENTICATION_TYPE>`: el tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="c0e25-419">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="c0e25-420">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="c0e25-420">The possible values are:</span></span>

- <span data-ttu-id="c0e25-421">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="c0e25-421">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="c0e25-422">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="c0e25-422">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="c0e25-423">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="c0e25-423">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="c0e25-424">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="c0e25-424">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="c0e25-425">`--aad-b2c-instance <INSTANCE>`: la instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="c0e25-425">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="c0e25-426">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-426">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="c0e25-427">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-427">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="c0e25-428">`-ssp|--susi-policy-id <ID>`: el id. de inicio de sesión y de directiva de registro de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="c0e25-428">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="c0e25-429">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-429">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="c0e25-430">`--aad-instance <INSTANCE>`: la instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="c0e25-430">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="c0e25-431">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-431">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="c0e25-432">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-432">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="c0e25-433">`--client-id <ID>`: el id. de cliente para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="c0e25-433">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="c0e25-434">Úsela con las autenticaciones `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-434">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="c0e25-435">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-435">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="c0e25-436">`--domain <DOMAIN>`: el dominio para el inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="c0e25-436">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="c0e25-437">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-437">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="c0e25-438">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-438">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="c0e25-439">`--tenant-id <ID>`: el id. de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="c0e25-439">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="c0e25-440">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-440">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="c0e25-441">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-441">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="c0e25-442">`-r|--org-read-access`: concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="c0e25-442">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="c0e25-443">Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-443">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="c0e25-444">`--use-launch-settings`: incluye *launchSettings.json* en la salida de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="c0e25-444">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="c0e25-445">`-uld|--use-local-db`: especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="c0e25-445">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="c0e25-446">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-446">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="c0e25-447">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="c0e25-447">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c0e25-448">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="c0e25-448">**mvc, razor**</span></span>

<span data-ttu-id="c0e25-449">`-au|--auth <AUTHENTICATION_TYPE>`: el tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="c0e25-449">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="c0e25-450">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="c0e25-450">The possible values are:</span></span>

- <span data-ttu-id="c0e25-451">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="c0e25-451">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="c0e25-452">`Individual`: autenticación individual.</span><span class="sxs-lookup"><span data-stu-id="c0e25-452">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="c0e25-453">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="c0e25-453">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="c0e25-454">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="c0e25-454">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="c0e25-455">`MultiOrg`: autenticación organizativa para varios inquilinos.</span><span class="sxs-lookup"><span data-stu-id="c0e25-455">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="c0e25-456">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="c0e25-456">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="c0e25-457">`--aad-b2c-instance <INSTANCE>`: la instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="c0e25-457">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="c0e25-458">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-458">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="c0e25-459">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-459">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="c0e25-460">`-ssp|--susi-policy-id <ID>`: el id. de inicio de sesión y de directiva de registro de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="c0e25-460">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="c0e25-461">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-461">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="c0e25-462">`-rp|--reset-password-policy-id <ID>`: el id. de la directiva de restablecimiento de contraseñas para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="c0e25-462">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="c0e25-463">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-463">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="c0e25-464">`-ep|--edit-profile-policy-id <ID>`: el id. de directiva de edición de perfiles para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="c0e25-464">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="c0e25-465">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-465">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="c0e25-466">`--aad-instance <INSTANCE>`: la instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="c0e25-466">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="c0e25-467">Úsela con las autenticaciones `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-467">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="c0e25-468">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-468">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="c0e25-469">`--client-id <ID>`: el id. de cliente para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="c0e25-469">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="c0e25-470">Úsela con las autenticaciones `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-470">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="c0e25-471">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-471">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="c0e25-472">`--domain <DOMAIN>`: el dominio para el inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="c0e25-472">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="c0e25-473">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-473">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="c0e25-474">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-474">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="c0e25-475">`--tenant-id <ID>`: el id. de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="c0e25-475">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="c0e25-476">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-476">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="c0e25-477">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-477">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="c0e25-478">`--callback-path <PATH>`: la ruta de acceso de solicitud de la ruta de acceso de la base de la aplicación del URI de redirección.</span><span class="sxs-lookup"><span data-stu-id="c0e25-478">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="c0e25-479">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-479">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="c0e25-480">El valor predeterminado es `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-480">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="c0e25-481">`-r|--org-read-access`: concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="c0e25-481">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="c0e25-482">Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-482">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="c0e25-483">`--use-launch-settings`: incluye *launchSettings.json* en la salida de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="c0e25-483">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="c0e25-484">`--use-browserlink`: incluye BrowserLink en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="c0e25-484">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="c0e25-485">`-uld|--use-local-db`: especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="c0e25-485">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="c0e25-486">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-486">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="c0e25-487">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="c0e25-487">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="c0e25-488">**page**</span><span class="sxs-lookup"><span data-stu-id="c0e25-488">**page**</span></span>

<span data-ttu-id="c0e25-489">`-na|--namespace <NAMESPACE_NAME>`: espacio de nombres para el código generado.</span><span class="sxs-lookup"><span data-stu-id="c0e25-489">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="c0e25-490">El valor predeterminado es `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-490">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="c0e25-491">`-np|--no-pagemodel`: crea la página sin PageModel.</span><span class="sxs-lookup"><span data-stu-id="c0e25-491">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="c0e25-492">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="c0e25-492">**viewimports**</span></span>

<span data-ttu-id="c0e25-493">`-na|--namespace <NAMESPACE_NAME>`: espacio de nombres para el código generado.</span><span class="sxs-lookup"><span data-stu-id="c0e25-493">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="c0e25-494">El valor predeterminado es `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-494">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="c0e25-495">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="c0e25-495">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="c0e25-496">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="c0e25-496">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="c0e25-497">`-f|--framework`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="c0e25-497">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c0e25-498">Valores: `netcoreapp1.0` o `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-498">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="c0e25-499">El valor predeterminado es `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-499">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="c0e25-500">**classlib**</span><span class="sxs-lookup"><span data-stu-id="c0e25-500">**classlib**</span></span>

<span data-ttu-id="c0e25-501">`-f|--framework`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="c0e25-501">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c0e25-502">Valores: `netcoreapp1.0`, `netcoreapp1.1` o de `netstandard1.0` a `netstandard1.6`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-502">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="c0e25-503">El valor predeterminado es `netstandard1.4`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-503">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="c0e25-504">**mvc**</span><span class="sxs-lookup"><span data-stu-id="c0e25-504">**mvc**</span></span>

<span data-ttu-id="c0e25-505">`-f|--framework`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="c0e25-505">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="c0e25-506">Valores: `netcoreapp1.0` o `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-506">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="c0e25-507">El valor predeterminado es `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-507">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="c0e25-508">`-au|--auth`: el tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="c0e25-508">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="c0e25-509">Valores: `None` o `Individual`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-509">Values: `None` or `Individual`.</span></span> <span data-ttu-id="c0e25-510">El valor predeterminado es `None`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-510">The default value is `None`.</span></span>

<span data-ttu-id="c0e25-511">`-uld|--use-local-db`: especifica si se va a usar o no LocalDB en lugar de SQLite.</span><span class="sxs-lookup"><span data-stu-id="c0e25-511">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="c0e25-512">Valores: `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-512">Values: `true` or `false`.</span></span> <span data-ttu-id="c0e25-513">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="c0e25-513">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="c0e25-514">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="c0e25-514">Examples</span></span>

<span data-ttu-id="c0e25-515">Creación de un proyecto de aplicación de consola con F# en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="c0e25-515">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang F#`

<span data-ttu-id="c0e25-516">Creación de un proyecto de biblioteca de clases de .NET Standard en el directorio especificado (disponible solo con el SDK de .NET Core 2.0 o versiones posteriores):</span><span class="sxs-lookup"><span data-stu-id="c0e25-516">Create a .NET Standard class library project in the specified directory (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="c0e25-517">Creación de un proyecto de aplicación MVC de ASP.NET Core C# en el directorio actual sin autenticación:</span><span class="sxs-lookup"><span data-stu-id="c0e25-517">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication:</span></span>

`dotnet new mvc -au None`

<span data-ttu-id="c0e25-518">Cree una aplicación de xUnit.</span><span class="sxs-lookup"><span data-stu-id="c0e25-518">Create a new xUnit application:</span></span>

`dotnet new xunit`

<span data-ttu-id="c0e25-519">Enumere todas las plantillas disponibles para MVC:</span><span class="sxs-lookup"><span data-stu-id="c0e25-519">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

<span data-ttu-id="c0e25-520">Instalación de la versión 2.0 de las plantillas Aplicación de página única para ASP.NET Core (opción de comando solo disponible para .NET Core SDK 1.1 y versiones posteriores):</span><span class="sxs-lookup"><span data-stu-id="c0e25-520">Install version 2.0 of the Single Page Application templates for ASP.NET Core (command option available for .NET Core SDK 1.1 and later versions only):</span></span>

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

<span data-ttu-id="c0e25-521">Creación de un archivo *global.json* en el directorio actual que establezca la versión del SDK en 2.0.0 (solo disponible en el SDK de .NET Core 2.0 o versiones posteriores):</span><span class="sxs-lookup"><span data-stu-id="c0e25-521">Create a *global.json* in the current directory setting the SDK version to 2.0.0 (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new globaljson --sdk-version 2.0.0`

## <a name="see-also"></a><span data-ttu-id="c0e25-522">Vea también</span><span class="sxs-lookup"><span data-stu-id="c0e25-522">See also</span></span>

* <span data-ttu-id="c0e25-523">[Custom templates for dotnet new](custom-templates.md) (Plantillas personalizadas para dotnet new)</span><span class="sxs-lookup"><span data-stu-id="c0e25-523">[Custom templates for dotnet new](custom-templates.md)</span></span>  
* [<span data-ttu-id="c0e25-524">Creación de una plantilla personalizada para dotnet new</span><span class="sxs-lookup"><span data-stu-id="c0e25-524">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)  
* [<span data-ttu-id="c0e25-525">Repositorio de GitHub dotnet/dotnet-template-samples</span><span class="sxs-lookup"><span data-stu-id="c0e25-525">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)  
* <span data-ttu-id="c0e25-526">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new) (Plantillas disponibles para dotnet new)</span><span class="sxs-lookup"><span data-stu-id="c0e25-526">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)</span></span>
