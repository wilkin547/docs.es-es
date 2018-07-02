---
title: 'Comando dotnet new: CLI de .NET Core'
description: El comando dotnet new crea proyectos de .NET Core basados en la plantilla especificada.
author: mairaw
ms.author: mairaw
ms.date: 06/12/2018
ms.openlocfilehash: f0ef91361dfbc2c2ba5532fbd607786289e98c69
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36207814"
---
# <a name="dotnet-new"></a><span data-ttu-id="f249f-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="f249f-103">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="f249f-104">nombre</span><span class="sxs-lookup"><span data-stu-id="f249f-104">Name</span></span>

<span data-ttu-id="f249f-105">`dotnet new`: crea un nuevo proyecto, archivo de configuración o solución según la plantilla especificada.</span><span class="sxs-lookup"><span data-stu-id="f249f-105">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="f249f-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="f249f-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="f249f-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="f249f-107">.NET Core 2.1</span></span>](#tab/netcore21)
```
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output]
    [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```
# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="f249f-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="f249f-108">.NET Core 2.0</span></span>](#tab/netcore20)
```
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="f249f-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="f249f-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="f249f-110">Description</span><span class="sxs-lookup"><span data-stu-id="f249f-110">Description</span></span>

<span data-ttu-id="f249f-111">El comando `dotnet new` proporciona una manera cómoda de inicializar un proyecto .NET Core válido.</span><span class="sxs-lookup"><span data-stu-id="f249f-111">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span>

<span data-ttu-id="f249f-112">El comando llama al [motor de plantillas](https://github.com/dotnet/templating) para crear los artefactos en el disco basándose en las opciones y la plantilla especificadas.</span><span class="sxs-lookup"><span data-stu-id="f249f-112">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="f249f-113">Argumentos</span><span class="sxs-lookup"><span data-stu-id="f249f-113">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="f249f-114">La plantilla de la que se va a crear una instancia cuando se invoca el comando.</span><span class="sxs-lookup"><span data-stu-id="f249f-114">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="f249f-115">Cada plantilla puede tener opciones específicas que puede pasar.</span><span class="sxs-lookup"><span data-stu-id="f249f-115">Each template might have specific options you can pass.</span></span> <span data-ttu-id="f249f-116">Para obtener más información, vea [Opciones de plantilla](#template-options).</span><span class="sxs-lookup"><span data-stu-id="f249f-116">For more information, see [Template options](#template-options).</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="f249f-117">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="f249f-117">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="f249f-118">El comando contiene una lista predeterminada de plantillas.</span><span class="sxs-lookup"><span data-stu-id="f249f-118">The command contains a default list of templates.</span></span> <span data-ttu-id="f249f-119">Use `dotnet new -l` para obtener una lista de las plantillas disponibles.</span><span class="sxs-lookup"><span data-stu-id="f249f-119">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="f249f-120">En la tabla siguiente se muestran las plantillas que vienen preinstaladas con el SDK de .NET Core 2.1.300.</span><span class="sxs-lookup"><span data-stu-id="f249f-120">The following table shows the templates that come pre-installed with the .NET Core SDK 2.1.300.</span></span> <span data-ttu-id="f249f-121">El lenguaje predeterminado de la plantilla se muestra entre corchetes.</span><span class="sxs-lookup"><span data-stu-id="f249f-121">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="f249f-122">Descripción de plantilla</span><span class="sxs-lookup"><span data-stu-id="f249f-122">Template description</span></span>                          | <span data-ttu-id="f249f-123">Nombre de plantilla</span><span class="sxs-lookup"><span data-stu-id="f249f-123">Template name</span></span>   | <span data-ttu-id="f249f-124">Lenguajes</span><span class="sxs-lookup"><span data-stu-id="f249f-124">Languages</span></span>     |
|----------------------------------------------|-----------------|---------------|
| <span data-ttu-id="f249f-125">Aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="f249f-125">Console application</span></span>                          | `console`       | <span data-ttu-id="f249f-126">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="f249f-126">[C#], F#, VB</span></span>  |
| <span data-ttu-id="f249f-127">Biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="f249f-127">Class library</span></span>                                | `classlib`      | <span data-ttu-id="f249f-128">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="f249f-128">[C#], F#, VB</span></span>  |
| <span data-ttu-id="f249f-129">Proyecto de prueba unitaria</span><span class="sxs-lookup"><span data-stu-id="f249f-129">Unit test project</span></span>                            | `mstest`        | <span data-ttu-id="f249f-130">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="f249f-130">[C#], F#, VB</span></span>  |
| <span data-ttu-id="f249f-131">Proyecto de prueba xUnit</span><span class="sxs-lookup"><span data-stu-id="f249f-131">xUnit test project</span></span>                           | `xunit`         | <span data-ttu-id="f249f-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="f249f-132">[C#], F#, VB</span></span>  |
| <span data-ttu-id="f249f-133">Página de Razor</span><span class="sxs-lookup"><span data-stu-id="f249f-133">Razor page</span></span>                                   | `page`          | <span data-ttu-id="f249f-134">[C#]</span><span class="sxs-lookup"><span data-stu-id="f249f-134">[C#]</span></span>          |
| <span data-ttu-id="f249f-135">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="f249f-135">MVC ViewImports</span></span>                              | `viewimports`   | <span data-ttu-id="f249f-136">[C#]</span><span class="sxs-lookup"><span data-stu-id="f249f-136">[C#]</span></span>          |
| <span data-ttu-id="f249f-137">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="f249f-137">MVC ViewStart</span></span>                                | `viewstart`     | <span data-ttu-id="f249f-138">[C#]</span><span class="sxs-lookup"><span data-stu-id="f249f-138">[C#]</span></span>          |
| <span data-ttu-id="f249f-139">Vacío de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="f249f-139">ASP.NET Core empty</span></span>                           | `web`           | <span data-ttu-id="f249f-140">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="f249f-140">[C#], F#</span></span>      |
| <span data-ttu-id="f249f-141">Aplicación web de ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="f249f-141">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`           | <span data-ttu-id="f249f-142">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="f249f-142">[C#], F#</span></span>      |
| <span data-ttu-id="f249f-143">Aplicación web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="f249f-143">ASP.NET Core Web App</span></span>                         | `razor`         | <span data-ttu-id="f249f-144">[C#]</span><span class="sxs-lookup"><span data-stu-id="f249f-144">[C#]</span></span>          |
| <span data-ttu-id="f249f-145">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="f249f-145">ASP.NET Core with Angular</span></span>                    | `angular`       | <span data-ttu-id="f249f-146">[C#]</span><span class="sxs-lookup"><span data-stu-id="f249f-146">[C#]</span></span>          |
| <span data-ttu-id="f249f-147">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="f249f-147">ASP.NET Core with React.js</span></span>                   | `react`         | <span data-ttu-id="f249f-148">[C#]</span><span class="sxs-lookup"><span data-stu-id="f249f-148">[C#]</span></span>          |
| <span data-ttu-id="f249f-149">ASP.NET Core con React.js y Redux</span><span class="sxs-lookup"><span data-stu-id="f249f-149">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`    | <span data-ttu-id="f249f-150">[C#]</span><span class="sxs-lookup"><span data-stu-id="f249f-150">[C#]</span></span>          |
| <span data-ttu-id="f249f-151">API web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="f249f-151">ASP.NET Core Web API</span></span>                         | `webapi`        | <span data-ttu-id="f249f-152">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="f249f-152">[C#], F#</span></span>      |
| <span data-ttu-id="f249f-153">Biblioteca de clases de Razor</span><span class="sxs-lookup"><span data-stu-id="f249f-153">Razor class library</span></span>                          | `razorclasslib` | <span data-ttu-id="f249f-154">[C#]</span><span class="sxs-lookup"><span data-stu-id="f249f-154">[C#]</span></span>          |
| <span data-ttu-id="f249f-155">archivo global.json</span><span class="sxs-lookup"><span data-stu-id="f249f-155">global.json file</span></span>                             | `globaljson`    |               |
| <span data-ttu-id="f249f-156">Configuración de NuGet</span><span class="sxs-lookup"><span data-stu-id="f249f-156">NuGet config</span></span>                                 | `nugetconfig`   |               |
| <span data-ttu-id="f249f-157">Configuración de la Web</span><span class="sxs-lookup"><span data-stu-id="f249f-157">Web config</span></span>                                   | `webconfig`     |               |
| <span data-ttu-id="f249f-158">Archivo de solución</span><span class="sxs-lookup"><span data-stu-id="f249f-158">Solution file</span></span>                                | `sln`           |               |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="f249f-159">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="f249f-159">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="f249f-160">El comando contiene una lista predeterminada de plantillas.</span><span class="sxs-lookup"><span data-stu-id="f249f-160">The command contains a default list of templates.</span></span> <span data-ttu-id="f249f-161">Use `dotnet new -l` para obtener una lista de las plantillas disponibles.</span><span class="sxs-lookup"><span data-stu-id="f249f-161">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="f249f-162">En la tabla siguiente se muestran las plantillas que vienen preinstaladas con el SDK de .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="f249f-162">The following table shows the templates that come pre-installed with the .NET Core SDK 2.0.</span></span> <span data-ttu-id="f249f-163">El lenguaje predeterminado de la plantilla se muestra entre corchetes.</span><span class="sxs-lookup"><span data-stu-id="f249f-163">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="f249f-164">Descripción de plantilla</span><span class="sxs-lookup"><span data-stu-id="f249f-164">Template description</span></span>                          | <span data-ttu-id="f249f-165">Nombre de plantilla</span><span class="sxs-lookup"><span data-stu-id="f249f-165">Template name</span></span> | <span data-ttu-id="f249f-166">Lenguajes</span><span class="sxs-lookup"><span data-stu-id="f249f-166">Languages</span></span>     |
|----------------------------------------------|---------------|---------------|
| <span data-ttu-id="f249f-167">Aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="f249f-167">Console application</span></span>                          | `console`     | <span data-ttu-id="f249f-168">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="f249f-168">[C#], F#, VB</span></span>  |
| <span data-ttu-id="f249f-169">Biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="f249f-169">Class library</span></span>                                | `classlib`    | <span data-ttu-id="f249f-170">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="f249f-170">[C#], F#, VB</span></span>  |
| <span data-ttu-id="f249f-171">Proyecto de prueba unitaria</span><span class="sxs-lookup"><span data-stu-id="f249f-171">Unit test project</span></span>                            | `mstest`      | <span data-ttu-id="f249f-172">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="f249f-172">[C#], F#, VB</span></span>  |
| <span data-ttu-id="f249f-173">Proyecto de prueba xUnit</span><span class="sxs-lookup"><span data-stu-id="f249f-173">xUnit test project</span></span>                           | `xunit`       | <span data-ttu-id="f249f-174">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="f249f-174">[C#], F#, VB</span></span>  |
| <span data-ttu-id="f249f-175">Vacío de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="f249f-175">ASP.NET Core empty</span></span>                           | `web`         | <span data-ttu-id="f249f-176">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="f249f-176">[C#], F#</span></span>      |
| <span data-ttu-id="f249f-177">Aplicación web de ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="f249f-177">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="f249f-178">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="f249f-178">[C#], F#</span></span>      |
| <span data-ttu-id="f249f-179">Aplicación web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="f249f-179">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="f249f-180">[C#]</span><span class="sxs-lookup"><span data-stu-id="f249f-180">[C#]</span></span>          |
| <span data-ttu-id="f249f-181">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="f249f-181">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="f249f-182">[C#]</span><span class="sxs-lookup"><span data-stu-id="f249f-182">[C#]</span></span>          |
| <span data-ttu-id="f249f-183">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="f249f-183">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="f249f-184">[C#]</span><span class="sxs-lookup"><span data-stu-id="f249f-184">[C#]</span></span>          |
| <span data-ttu-id="f249f-185">ASP.NET Core con React.js y Redux</span><span class="sxs-lookup"><span data-stu-id="f249f-185">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="f249f-186">[C#]</span><span class="sxs-lookup"><span data-stu-id="f249f-186">[C#]</span></span>          |
| <span data-ttu-id="f249f-187">API web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="f249f-187">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="f249f-188">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="f249f-188">[C#], F#</span></span>      |
| <span data-ttu-id="f249f-189">archivo global.json</span><span class="sxs-lookup"><span data-stu-id="f249f-189">global.json file</span></span>                             | `globaljson`  |               |
| <span data-ttu-id="f249f-190">Configuración de NuGet</span><span class="sxs-lookup"><span data-stu-id="f249f-190">NuGet config</span></span>                                 | `nugetconfig` |               |
| <span data-ttu-id="f249f-191">Configuración de la Web</span><span class="sxs-lookup"><span data-stu-id="f249f-191">Web config</span></span>                                   | `webconfig`   |               |
| <span data-ttu-id="f249f-192">Archivo de solución</span><span class="sxs-lookup"><span data-stu-id="f249f-192">Solution file</span></span>                                | `sln`         |               |
| <span data-ttu-id="f249f-193">Página de Razor</span><span class="sxs-lookup"><span data-stu-id="f249f-193">Razor page</span></span>                                   | `page`        |               |
| <span data-ttu-id="f249f-194">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="f249f-194">MVC ViewImports</span></span>                              | `viewimports` |               |
| <span data-ttu-id="f249f-195">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="f249f-195">MVC ViewStart</span></span>                                | `viewstart`   |               |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="f249f-196">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="f249f-196">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="f249f-197">El comando contiene una lista predeterminada de plantillas.</span><span class="sxs-lookup"><span data-stu-id="f249f-197">The command contains a default list of templates.</span></span> <span data-ttu-id="f249f-198">Use `dotnet new -all` para obtener una lista de las plantillas disponibles.</span><span class="sxs-lookup"><span data-stu-id="f249f-198">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="f249f-199">En la tabla siguiente se muestran las plantillas que vienen preinstaladas con el SDK de .NET 1.x.</span><span class="sxs-lookup"><span data-stu-id="f249f-199">The following table shows the templates that come pre-installed with the .NET Core SDK 1.x.</span></span> <span data-ttu-id="f249f-200">El lenguaje predeterminado de la plantilla se muestra entre corchetes.</span><span class="sxs-lookup"><span data-stu-id="f249f-200">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="f249f-201">Descripción de plantilla</span><span class="sxs-lookup"><span data-stu-id="f249f-201">Template description</span></span>  | <span data-ttu-id="f249f-202">Nombre de plantilla</span><span class="sxs-lookup"><span data-stu-id="f249f-202">Template name</span></span> | <span data-ttu-id="f249f-203">Lenguajes</span><span class="sxs-lookup"><span data-stu-id="f249f-203">Languages</span></span> |
|----------------------|---------------|-----------|
| <span data-ttu-id="f249f-204">Aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="f249f-204">Console application</span></span>  | `console`     | <span data-ttu-id="f249f-205">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="f249f-205">[C#], F#</span></span>  |
| <span data-ttu-id="f249f-206">Biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="f249f-206">Class library</span></span>        | `classlib`    | <span data-ttu-id="f249f-207">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="f249f-207">[C#], F#</span></span>  |
| <span data-ttu-id="f249f-208">Proyecto de prueba unitaria</span><span class="sxs-lookup"><span data-stu-id="f249f-208">Unit test project</span></span>    | `mstest`      | <span data-ttu-id="f249f-209">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="f249f-209">[C#], F#</span></span>  |
| <span data-ttu-id="f249f-210">Proyecto de prueba xUnit</span><span class="sxs-lookup"><span data-stu-id="f249f-210">xUnit test project</span></span>   | `xunit`       | <span data-ttu-id="f249f-211">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="f249f-211">[C#], F#</span></span>  |
| <span data-ttu-id="f249f-212">Vacío de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="f249f-212">ASP.NET Core empty</span></span>   | `web`         | <span data-ttu-id="f249f-213">[C#]</span><span class="sxs-lookup"><span data-stu-id="f249f-213">[C#]</span></span>      |
| <span data-ttu-id="f249f-214">Aplicación web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="f249f-214">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="f249f-215">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="f249f-215">[C#], F#</span></span>  |
| <span data-ttu-id="f249f-216">API web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="f249f-216">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="f249f-217">[C#]</span><span class="sxs-lookup"><span data-stu-id="f249f-217">[C#]</span></span>      |
| <span data-ttu-id="f249f-218">Configuración de NuGet</span><span class="sxs-lookup"><span data-stu-id="f249f-218">NuGet config</span></span>         | `nugetconfig` |           |
| <span data-ttu-id="f249f-219">Configuración de la Web</span><span class="sxs-lookup"><span data-stu-id="f249f-219">Web config</span></span>           | `webconfig`   |           |
| <span data-ttu-id="f249f-220">Archivo de solución</span><span class="sxs-lookup"><span data-stu-id="f249f-220">Solution file</span></span>        | `sln`         |           |

---

## <a name="options"></a><span data-ttu-id="f249f-221">Opciones</span><span class="sxs-lookup"><span data-stu-id="f249f-221">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="f249f-222">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="f249f-222">.NET Core 2.1</span></span>](#tab/netcore21)

`--force`

<span data-ttu-id="f249f-223">Fuerza la generación de contenido incluso aunque se vayan a cambiar los archivos existentes.</span><span class="sxs-lookup"><span data-stu-id="f249f-223">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="f249f-224">Esto es necesario cuando el directorio de salida ya contiene un proyecto.</span><span class="sxs-lookup"><span data-stu-id="f249f-224">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="f249f-225">Imprime la ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="f249f-225">Prints out help for the command.</span></span> <span data-ttu-id="f249f-226">Puede invocarse para el propio comando `dotnet new` o para cualquier plantilla, como `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="f249f-226">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="f249f-227">Instala un paquete de plantillas u origen desde los parámetros `PATH` o `NUGET_ID` proporcionados.</span><span class="sxs-lookup"><span data-stu-id="f249f-227">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="f249f-228">Si quiere instalar una versión preliminar de un paquete de plantilla, tendrá que especificar la versión en el formato de `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="f249f-228">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="f249f-229">De manera predeterminada, `dotnet new` pasa \* para la versión, que representa la última versión estable del paquete.</span><span class="sxs-lookup"><span data-stu-id="f249f-229">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="f249f-230">Vea un ejemplo en la sección [Ejemplos](#examples).</span><span class="sxs-lookup"><span data-stu-id="f249f-230">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="f249f-231">Para obtener información sobre cómo crear plantillas personalizadas, consulte [Custom templates for dotnet new](custom-templates.md) (Plantillas personalizadas para dotnet new).</span><span class="sxs-lookup"><span data-stu-id="f249f-231">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="f249f-232">Muestra las plantillas que contienen el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="f249f-232">Lists templates containing the specified name.</span></span> <span data-ttu-id="f249f-233">Si se invoca para el comando `dotnet new`, muestra las plantillas posibles disponibles para un directorio determinado.</span><span class="sxs-lookup"><span data-stu-id="f249f-233">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="f249f-234">Por ejemplo, si el directorio ya contiene un proyecto, no mostrará todas las plantillas del proyecto.</span><span class="sxs-lookup"><span data-stu-id="f249f-234">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="f249f-235">El lenguaje de la plantilla que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="f249f-235">The language of the template to create.</span></span> <span data-ttu-id="f249f-236">El lenguaje aceptado cambia según la plantilla (vea los valores predeterminados en la sección [argumentos](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="f249f-236">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="f249f-237">No es válido para algunas plantillas.</span><span class="sxs-lookup"><span data-stu-id="f249f-237">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="f249f-238">Algunos shells interpretan `#` como un carácter especial.</span><span class="sxs-lookup"><span data-stu-id="f249f-238">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="f249f-239">En esos casos, debe incluir el valor del parámetro de lenguaje, como `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="f249f-239">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="f249f-240">El nombre de la salida creada.</span><span class="sxs-lookup"><span data-stu-id="f249f-240">The name for the created output.</span></span> <span data-ttu-id="f249f-241">Si no se especifica ningún nombre, se usa el nombre del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="f249f-241">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="f249f-242">Especifica un origen de NuGet para usarlo durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="f249f-242">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="f249f-243">La ubicación para colocar la salida generada.</span><span class="sxs-lookup"><span data-stu-id="f249f-243">Location to place the generated output.</span></span> <span data-ttu-id="f249f-244">El valor predeterminado es el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="f249f-244">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="f249f-245">Filtra plantillas en función de los tipos disponibles.</span><span class="sxs-lookup"><span data-stu-id="f249f-245">Filters templates based on available types.</span></span> <span data-ttu-id="f249f-246">Los valores predefinidos son “project”, “item” y “other”.</span><span class="sxs-lookup"><span data-stu-id="f249f-246">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="f249f-247">Desinstala un paquete de plantillas u origen en los parámetros `PATH` o `NUGET_ID` proporcionados.</span><span class="sxs-lookup"><span data-stu-id="f249f-247">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="f249f-248">Para desinstalar una plantilla mediante `PATH`, debe usar el nombre completo de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="f249f-248">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="f249f-249">Por ejemplo, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* funcionará, pero *./GarciaSoftware.ConsoleTemplate.CSharp* desde la carpeta contenedora no lo hará.</span><span class="sxs-lookup"><span data-stu-id="f249f-249">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="f249f-250">Además, no debe incluir una barra diagonal para finalizar el directorio en la ruta de acceso a la plantilla.</span><span class="sxs-lookup"><span data-stu-id="f249f-250">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="f249f-251">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="f249f-251">.NET Core 2.0</span></span>](#tab/netcore20)

`--force`

<span data-ttu-id="f249f-252">Fuerza la generación de contenido incluso aunque se vayan a cambiar los archivos existentes.</span><span class="sxs-lookup"><span data-stu-id="f249f-252">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="f249f-253">Esto es necesario cuando el directorio de salida ya contiene un proyecto.</span><span class="sxs-lookup"><span data-stu-id="f249f-253">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="f249f-254">Imprime la ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="f249f-254">Prints out help for the command.</span></span> <span data-ttu-id="f249f-255">Puede invocarse para el propio comando `dotnet new` o para cualquier plantilla, como `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="f249f-255">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="f249f-256">Instala un paquete de plantillas u origen desde los parámetros `PATH` o `NUGET_ID` proporcionados.</span><span class="sxs-lookup"><span data-stu-id="f249f-256">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="f249f-257">Si quiere instalar una versión preliminar de un paquete de plantilla, tendrá que especificar la versión en el formato de `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="f249f-257">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="f249f-258">De manera predeterminada, `dotnet new` pasa \* para la versión, que representa la última versión estable del paquete.</span><span class="sxs-lookup"><span data-stu-id="f249f-258">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="f249f-259">Vea un ejemplo en la sección [Ejemplos](#examples).</span><span class="sxs-lookup"><span data-stu-id="f249f-259">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="f249f-260">Para obtener información sobre cómo crear plantillas personalizadas, consulte [Custom templates for dotnet new](custom-templates.md) (Plantillas personalizadas para dotnet new).</span><span class="sxs-lookup"><span data-stu-id="f249f-260">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="f249f-261">Muestra las plantillas que contienen el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="f249f-261">Lists templates containing the specified name.</span></span> <span data-ttu-id="f249f-262">Si se invoca para el comando `dotnet new`, muestra las plantillas posibles disponibles para un directorio determinado.</span><span class="sxs-lookup"><span data-stu-id="f249f-262">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="f249f-263">Por ejemplo, si el directorio ya contiene un proyecto, no mostrará todas las plantillas del proyecto.</span><span class="sxs-lookup"><span data-stu-id="f249f-263">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="f249f-264">El lenguaje de la plantilla que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="f249f-264">The language of the template to create.</span></span> <span data-ttu-id="f249f-265">El lenguaje aceptado cambia según la plantilla (vea los valores predeterminados en la sección [argumentos](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="f249f-265">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="f249f-266">No es válido para algunas plantillas.</span><span class="sxs-lookup"><span data-stu-id="f249f-266">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="f249f-267">Algunos shells interpretan `#` como un carácter especial.</span><span class="sxs-lookup"><span data-stu-id="f249f-267">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="f249f-268">En esos casos, debe incluir el valor del parámetro de lenguaje, como `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="f249f-268">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="f249f-269">El nombre de la salida creada.</span><span class="sxs-lookup"><span data-stu-id="f249f-269">The name for the created output.</span></span> <span data-ttu-id="f249f-270">Si no se especifica ningún nombre, se usa el nombre del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="f249f-270">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="f249f-271">La ubicación para colocar la salida generada.</span><span class="sxs-lookup"><span data-stu-id="f249f-271">Location to place the generated output.</span></span> <span data-ttu-id="f249f-272">El valor predeterminado es el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="f249f-272">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="f249f-273">Filtra plantillas en función de los tipos disponibles.</span><span class="sxs-lookup"><span data-stu-id="f249f-273">Filters templates based on available types.</span></span> <span data-ttu-id="f249f-274">Los valores predefinidos son “project”, “item” y “other”.</span><span class="sxs-lookup"><span data-stu-id="f249f-274">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="f249f-275">Desinstala un paquete de plantillas u origen en los parámetros `PATH` o `NUGET_ID` proporcionados.</span><span class="sxs-lookup"><span data-stu-id="f249f-275">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="f249f-276">Para desinstalar una plantilla mediante `PATH`, debe usar el nombre completo de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="f249f-276">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="f249f-277">Por ejemplo, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* funcionará, pero *./GarciaSoftware.ConsoleTemplate.CSharp* desde la carpeta contenedora no lo hará.</span><span class="sxs-lookup"><span data-stu-id="f249f-277">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="f249f-278">Además, no debe incluir una barra diagonal para finalizar el directorio en la ruta de acceso a la plantilla.</span><span class="sxs-lookup"><span data-stu-id="f249f-278">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="f249f-279">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="f249f-279">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="f249f-280">Muestra todas las plantillas de un tipo de proyecto específico cuando se ejecuta en el contexto del comando `dotnet new` por sí solo.</span><span class="sxs-lookup"><span data-stu-id="f249f-280">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="f249f-281">Cuando se ejecuta en el contexto de una plantilla específica, como `dotnet new web -all`, `-all` se interpreta como una marca para forzar la creación.</span><span class="sxs-lookup"><span data-stu-id="f249f-281">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="f249f-282">Esto es necesario cuando el directorio de salida ya contiene un proyecto.</span><span class="sxs-lookup"><span data-stu-id="f249f-282">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="f249f-283">Imprime la ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="f249f-283">Prints out help for the command.</span></span> <span data-ttu-id="f249f-284">Puede invocarse para el propio comando `dotnet new` o para cualquier plantilla, como `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="f249f-284">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="f249f-285">Muestra las plantillas que contienen el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="f249f-285">Lists templates containing the specified name.</span></span> <span data-ttu-id="f249f-286">Si se invoca para el comando `dotnet new`, muestra las plantillas posibles disponibles para un directorio determinado.</span><span class="sxs-lookup"><span data-stu-id="f249f-286">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="f249f-287">Por ejemplo, si el directorio ya contiene un proyecto, no mostrará todas las plantillas del proyecto.</span><span class="sxs-lookup"><span data-stu-id="f249f-287">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="f249f-288">El lenguaje de la plantilla que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="f249f-288">The language of the template to create.</span></span> <span data-ttu-id="f249f-289">El lenguaje aceptado cambia según la plantilla (vea los valores predeterminados en la sección [argumentos](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="f249f-289">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="f249f-290">No es válido para algunas plantillas.</span><span class="sxs-lookup"><span data-stu-id="f249f-290">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="f249f-291">Algunos shells interpretan `#` como un carácter especial.</span><span class="sxs-lookup"><span data-stu-id="f249f-291">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="f249f-292">En esos casos, debe incluir el valor del parámetro de lenguaje, como `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="f249f-292">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="f249f-293">El nombre de la salida creada.</span><span class="sxs-lookup"><span data-stu-id="f249f-293">The name for the created output.</span></span> <span data-ttu-id="f249f-294">Si no se especifica ningún nombre, se usa el nombre del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="f249f-294">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="f249f-295">La ubicación para colocar la salida generada.</span><span class="sxs-lookup"><span data-stu-id="f249f-295">Location to place the generated output.</span></span> <span data-ttu-id="f249f-296">El valor predeterminado es el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="f249f-296">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="f249f-297">Opciones de plantilla</span><span class="sxs-lookup"><span data-stu-id="f249f-297">Template options</span></span>

<span data-ttu-id="f249f-298">Cada plantilla de proyecto puede tener opciones adicionales disponibles.</span><span class="sxs-lookup"><span data-stu-id="f249f-298">Each project template may have additional options available.</span></span> <span data-ttu-id="f249f-299">Las plantillas principales tienen las siguientes opciones adicionales:</span><span class="sxs-lookup"><span data-stu-id="f249f-299">The core templates have the following additional options:</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="f249f-300">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="f249f-300">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="f249f-301">**console, angular, react, reactredux, razorclasslib**</span><span class="sxs-lookup"><span data-stu-id="f249f-301">**console, angular, react, reactredux, razorclasslib**</span></span>

  <span data-ttu-id="f249f-302">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="f249f-302">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="f249f-303">**classlib**</span><span class="sxs-lookup"><span data-stu-id="f249f-303">**classlib**</span></span>

<span data-ttu-id="f249f-304">`-f|--framework <FRAMEWORK>`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="f249f-304">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="f249f-305">Valores: `netcoreapp2.0` para crear una biblioteca de clases de .NET Core o `netstandard2.0` para crear una biblioteca de clases de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="f249f-305">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="f249f-306">El valor predeterminado es `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="f249f-306">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="f249f-307">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="f249f-307">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="f249f-308">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="f249f-308">**mstest, xunit**</span></span>

<span data-ttu-id="f249f-309">`-p|--enable-pack`: habilita el empaquetado para el proyecto mediante [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="f249f-309">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="f249f-310">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="f249f-310">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="f249f-311">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="f249f-311">**globaljson**</span></span>

<span data-ttu-id="f249f-312">`--sdk-version <VERSION_NUMBER>`: especifica la versión del SDK de .NET Core que se usará con el archivo *global.json*.</span><span class="sxs-lookup"><span data-stu-id="f249f-312">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="f249f-313">**web**</span><span class="sxs-lookup"><span data-stu-id="f249f-313">**web**</span></span>

<span data-ttu-id="f249f-314">`--use-launch-settings`: incluye *launchSettings.json* en la salida de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="f249f-314">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="f249f-315">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="f249f-315">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="f249f-316">**webapi**</span><span class="sxs-lookup"><span data-stu-id="f249f-316">**webapi**</span></span>

<span data-ttu-id="f249f-317">`-au|--auth <AUTHENTICATION_TYPE>`: el tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="f249f-317">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="f249f-318">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="f249f-318">The possible values are:</span></span>

- <span data-ttu-id="f249f-319">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="f249f-319">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="f249f-320">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="f249f-320">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="f249f-321">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="f249f-321">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="f249f-322">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="f249f-322">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="f249f-323">`--aad-b2c-instance <INSTANCE>`: la instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="f249f-323">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="f249f-324">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="f249f-324">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="f249f-325">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="f249f-325">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="f249f-326">`-ssp|--susi-policy-id <ID>`: el id. de inicio de sesión y de directiva de registro de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="f249f-326">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="f249f-327">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="f249f-327">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="f249f-328">`--aad-instance <INSTANCE>`: la instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="f249f-328">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="f249f-329">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="f249f-329">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="f249f-330">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="f249f-330">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="f249f-331">`--client-id <ID>`: el id. de cliente para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="f249f-331">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="f249f-332">Úsela con las autenticaciones `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="f249f-332">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="f249f-333">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="f249f-333">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="f249f-334">`--domain <DOMAIN>`: el dominio para el inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="f249f-334">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="f249f-335">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="f249f-335">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="f249f-336">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="f249f-336">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="f249f-337">`--tenant-id <ID>`: el id. de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="f249f-337">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="f249f-338">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="f249f-338">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="f249f-339">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="f249f-339">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="f249f-340">`-r|--org-read-access`: concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="f249f-340">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="f249f-341">Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="f249f-341">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="f249f-342">`--use-launch-settings`: incluye *launchSettings.json* en la salida de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="f249f-342">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="f249f-343">`-uld|--use-local-db`: especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="f249f-343">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="f249f-344">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="f249f-344">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="f249f-345">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="f249f-345">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="f249f-346">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="f249f-346">**mvc, razor**</span></span>

<span data-ttu-id="f249f-347">`-au|--auth <AUTHENTICATION_TYPE>`: el tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="f249f-347">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="f249f-348">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="f249f-348">The possible values are:</span></span>

- <span data-ttu-id="f249f-349">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="f249f-349">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="f249f-350">`Individual`: autenticación individual.</span><span class="sxs-lookup"><span data-stu-id="f249f-350">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="f249f-351">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="f249f-351">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="f249f-352">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="f249f-352">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="f249f-353">`MultiOrg`: autenticación organizativa para varios inquilinos.</span><span class="sxs-lookup"><span data-stu-id="f249f-353">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="f249f-354">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="f249f-354">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="f249f-355">`--aad-b2c-instance <INSTANCE>`: la instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="f249f-355">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="f249f-356">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="f249f-356">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="f249f-357">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="f249f-357">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="f249f-358">`-ssp|--susi-policy-id <ID>`: el id. de inicio de sesión y de directiva de registro de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="f249f-358">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="f249f-359">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="f249f-359">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="f249f-360">`-rp|--reset-password-policy-id <ID>`: el id. de la directiva de restablecimiento de contraseñas para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="f249f-360">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="f249f-361">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="f249f-361">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="f249f-362">`-ep|--edit-profile-policy-id <ID>`: el id. de directiva de edición de perfiles para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="f249f-362">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="f249f-363">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="f249f-363">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="f249f-364">`--aad-instance <INSTANCE>`: la instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="f249f-364">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="f249f-365">Úsela con las autenticaciones `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="f249f-365">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="f249f-366">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="f249f-366">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="f249f-367">`--client-id <ID>`: el id. de cliente para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="f249f-367">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="f249f-368">Úsela con las autenticaciones `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="f249f-368">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="f249f-369">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="f249f-369">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="f249f-370">`--domain <DOMAIN>`: el dominio para el inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="f249f-370">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="f249f-371">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="f249f-371">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="f249f-372">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="f249f-372">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="f249f-373">`--tenant-id <ID>`: el id. de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="f249f-373">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="f249f-374">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="f249f-374">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="f249f-375">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="f249f-375">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="f249f-376">`--callback-path <PATH>`: la ruta de acceso de solicitud de la ruta de acceso de la base de la aplicación del URI de redirección.</span><span class="sxs-lookup"><span data-stu-id="f249f-376">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="f249f-377">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="f249f-377">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="f249f-378">El valor predeterminado es `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="f249f-378">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="f249f-379">`-r|--org-read-access`: concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="f249f-379">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="f249f-380">Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="f249f-380">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="f249f-381">`--use-launch-settings`: incluye *launchSettings.json* en la salida de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="f249f-381">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="f249f-382">`--use-browserlink`: incluye BrowserLink en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="f249f-382">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="f249f-383">`-uld|--use-local-db`: especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="f249f-383">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="f249f-384">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="f249f-384">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="f249f-385">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="f249f-385">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="f249f-386">**page**</span><span class="sxs-lookup"><span data-stu-id="f249f-386">**page**</span></span>

<span data-ttu-id="f249f-387">`-na|--namespace <NAMESPACE_NAME>`: espacio de nombres para el código generado.</span><span class="sxs-lookup"><span data-stu-id="f249f-387">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="f249f-388">El valor predeterminado es `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="f249f-388">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="f249f-389">`-np|--no-pagemodel`: crea la página sin PageModel.</span><span class="sxs-lookup"><span data-stu-id="f249f-389">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="f249f-390">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="f249f-390">**viewimports**</span></span>

<span data-ttu-id="f249f-391">`-na|--namespace <NAMESPACE_NAME>`: espacio de nombres para el código generado.</span><span class="sxs-lookup"><span data-stu-id="f249f-391">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="f249f-392">El valor predeterminado es `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="f249f-392">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="f249f-393">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="f249f-393">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="f249f-394">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="f249f-394">**console, angular, react, reactredux**</span></span>

  <span data-ttu-id="f249f-395">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="f249f-395">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="f249f-396">**classlib**</span><span class="sxs-lookup"><span data-stu-id="f249f-396">**classlib**</span></span>

<span data-ttu-id="f249f-397">`-f|--framework <FRAMEWORK>`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="f249f-397">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="f249f-398">Valores: `netcoreapp2.0` para crear una biblioteca de clases de .NET Core o `netstandard2.0` para crear una biblioteca de clases de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="f249f-398">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="f249f-399">El valor predeterminado es `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="f249f-399">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="f249f-400">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="f249f-400">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="f249f-401">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="f249f-401">**mstest, xunit**</span></span>

<span data-ttu-id="f249f-402">`-p|--enable-pack`: habilita el empaquetado para el proyecto mediante [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="f249f-402">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="f249f-403">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="f249f-403">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="f249f-404">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="f249f-404">**globaljson**</span></span>

<span data-ttu-id="f249f-405">`--sdk-version <VERSION_NUMBER>`: especifica la versión del SDK de .NET Core que se usará con el archivo *global.json*.</span><span class="sxs-lookup"><span data-stu-id="f249f-405">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="f249f-406">**web**</span><span class="sxs-lookup"><span data-stu-id="f249f-406">**web**</span></span>

<span data-ttu-id="f249f-407">`--use-launch-settings`: incluye *launchSettings.json* en la salida de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="f249f-407">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="f249f-408">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="f249f-408">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="f249f-409">**webapi**</span><span class="sxs-lookup"><span data-stu-id="f249f-409">**webapi**</span></span>

<span data-ttu-id="f249f-410">`-au|--auth <AUTHENTICATION_TYPE>`: el tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="f249f-410">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="f249f-411">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="f249f-411">The possible values are:</span></span>

- <span data-ttu-id="f249f-412">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="f249f-412">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="f249f-413">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="f249f-413">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="f249f-414">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="f249f-414">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="f249f-415">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="f249f-415">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="f249f-416">`--aad-b2c-instance <INSTANCE>`: la instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="f249f-416">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="f249f-417">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="f249f-417">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="f249f-418">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="f249f-418">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="f249f-419">`-ssp|--susi-policy-id <ID>`: el id. de inicio de sesión y de directiva de registro de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="f249f-419">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="f249f-420">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="f249f-420">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="f249f-421">`--aad-instance <INSTANCE>`: la instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="f249f-421">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="f249f-422">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="f249f-422">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="f249f-423">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="f249f-423">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="f249f-424">`--client-id <ID>`: el id. de cliente para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="f249f-424">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="f249f-425">Úsela con las autenticaciones `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="f249f-425">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="f249f-426">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="f249f-426">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="f249f-427">`--domain <DOMAIN>`: el dominio para el inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="f249f-427">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="f249f-428">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="f249f-428">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="f249f-429">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="f249f-429">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="f249f-430">`--tenant-id <ID>`: el id. de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="f249f-430">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="f249f-431">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="f249f-431">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="f249f-432">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="f249f-432">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="f249f-433">`-r|--org-read-access`: concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="f249f-433">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="f249f-434">Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="f249f-434">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="f249f-435">`--use-launch-settings`: incluye *launchSettings.json* en la salida de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="f249f-435">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="f249f-436">`-uld|--use-local-db`: especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="f249f-436">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="f249f-437">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="f249f-437">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="f249f-438">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="f249f-438">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="f249f-439">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="f249f-439">**mvc, razor**</span></span>

<span data-ttu-id="f249f-440">`-au|--auth <AUTHENTICATION_TYPE>`: el tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="f249f-440">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="f249f-441">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="f249f-441">The possible values are:</span></span>

- <span data-ttu-id="f249f-442">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="f249f-442">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="f249f-443">`Individual`: autenticación individual.</span><span class="sxs-lookup"><span data-stu-id="f249f-443">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="f249f-444">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="f249f-444">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="f249f-445">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="f249f-445">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="f249f-446">`MultiOrg`: autenticación organizativa para varios inquilinos.</span><span class="sxs-lookup"><span data-stu-id="f249f-446">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="f249f-447">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="f249f-447">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="f249f-448">`--aad-b2c-instance <INSTANCE>`: la instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="f249f-448">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="f249f-449">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="f249f-449">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="f249f-450">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="f249f-450">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="f249f-451">`-ssp|--susi-policy-id <ID>`: el id. de inicio de sesión y de directiva de registro de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="f249f-451">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="f249f-452">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="f249f-452">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="f249f-453">`-rp|--reset-password-policy-id <ID>`: el id. de la directiva de restablecimiento de contraseñas para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="f249f-453">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="f249f-454">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="f249f-454">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="f249f-455">`-ep|--edit-profile-policy-id <ID>`: el id. de directiva de edición de perfiles para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="f249f-455">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="f249f-456">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="f249f-456">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="f249f-457">`--aad-instance <INSTANCE>`: la instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="f249f-457">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="f249f-458">Úsela con las autenticaciones `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="f249f-458">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="f249f-459">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="f249f-459">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="f249f-460">`--client-id <ID>`: el id. de cliente para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="f249f-460">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="f249f-461">Úsela con las autenticaciones `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="f249f-461">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="f249f-462">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="f249f-462">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="f249f-463">`--domain <DOMAIN>`: el dominio para el inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="f249f-463">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="f249f-464">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="f249f-464">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="f249f-465">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="f249f-465">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="f249f-466">`--tenant-id <ID>`: el id. de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="f249f-466">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="f249f-467">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="f249f-467">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="f249f-468">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="f249f-468">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="f249f-469">`--callback-path <PATH>`: la ruta de acceso de solicitud de la ruta de acceso de la base de la aplicación del URI de redirección.</span><span class="sxs-lookup"><span data-stu-id="f249f-469">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="f249f-470">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="f249f-470">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="f249f-471">El valor predeterminado es `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="f249f-471">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="f249f-472">`-r|--org-read-access`: concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="f249f-472">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="f249f-473">Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="f249f-473">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="f249f-474">`--use-launch-settings`: incluye *launchSettings.json* en la salida de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="f249f-474">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="f249f-475">`--use-browserlink`: incluye BrowserLink en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="f249f-475">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="f249f-476">`-uld|--use-local-db`: especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="f249f-476">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="f249f-477">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="f249f-477">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="f249f-478">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="f249f-478">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="f249f-479">**page**</span><span class="sxs-lookup"><span data-stu-id="f249f-479">**page**</span></span>

<span data-ttu-id="f249f-480">`-na|--namespace <NAMESPACE_NAME>`: espacio de nombres para el código generado.</span><span class="sxs-lookup"><span data-stu-id="f249f-480">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="f249f-481">El valor predeterminado es `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="f249f-481">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="f249f-482">`-np|--no-pagemodel`: crea la página sin PageModel.</span><span class="sxs-lookup"><span data-stu-id="f249f-482">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="f249f-483">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="f249f-483">**viewimports**</span></span>

<span data-ttu-id="f249f-484">`-na|--namespace <NAMESPACE_NAME>`: espacio de nombres para el código generado.</span><span class="sxs-lookup"><span data-stu-id="f249f-484">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="f249f-485">El valor predeterminado es `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="f249f-485">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="f249f-486">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="f249f-486">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="f249f-487">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="f249f-487">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="f249f-488">`-f|--framework`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="f249f-488">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="f249f-489">Valores: `netcoreapp1.0` o `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="f249f-489">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="f249f-490">El valor predeterminado es `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="f249f-490">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="f249f-491">**classlib**</span><span class="sxs-lookup"><span data-stu-id="f249f-491">**classlib**</span></span>

<span data-ttu-id="f249f-492">`-f|--framework`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="f249f-492">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="f249f-493">Valores: `netcoreapp1.0`, `netcoreapp1.1` o de `netstandard1.0` a `netstandard1.6`.</span><span class="sxs-lookup"><span data-stu-id="f249f-493">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="f249f-494">El valor predeterminado es `netstandard1.4`.</span><span class="sxs-lookup"><span data-stu-id="f249f-494">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="f249f-495">**mvc**</span><span class="sxs-lookup"><span data-stu-id="f249f-495">**mvc**</span></span>

<span data-ttu-id="f249f-496">`-f|--framework`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="f249f-496">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="f249f-497">Valores: `netcoreapp1.0` o `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="f249f-497">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="f249f-498">El valor predeterminado es `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="f249f-498">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="f249f-499">`-au|--auth`: el tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="f249f-499">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="f249f-500">Valores: `None` o `Individual`.</span><span class="sxs-lookup"><span data-stu-id="f249f-500">Values: `None` or `Individual`.</span></span> <span data-ttu-id="f249f-501">El valor predeterminado es `None`.</span><span class="sxs-lookup"><span data-stu-id="f249f-501">The default value is `None`.</span></span>

<span data-ttu-id="f249f-502">`-uld|--use-local-db`: especifica si se va a usar o no LocalDB en lugar de SQLite.</span><span class="sxs-lookup"><span data-stu-id="f249f-502">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="f249f-503">Valores: `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="f249f-503">Values: `true` or `false`.</span></span> <span data-ttu-id="f249f-504">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="f249f-504">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="f249f-505">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="f249f-505">Examples</span></span>

<span data-ttu-id="f249f-506">Creación de un proyecto de aplicación de consola con F# en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="f249f-506">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang F#`

<span data-ttu-id="f249f-507">Creación de un proyecto de biblioteca de clases de .NET Standard en el directorio especificado (disponible solo con el SDK de .NET Core 2.0 o versiones posteriores):</span><span class="sxs-lookup"><span data-stu-id="f249f-507">Create a .NET Standard class library project in the specified directory (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="f249f-508">Creación de un proyecto de aplicación MVC de ASP.NET Core C# en el directorio actual sin autenticación:</span><span class="sxs-lookup"><span data-stu-id="f249f-508">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication:</span></span>

`dotnet new mvc -au None`

<span data-ttu-id="f249f-509">Cree una aplicación de xUnit.</span><span class="sxs-lookup"><span data-stu-id="f249f-509">Create a new xUnit application:</span></span>

`dotnet new xunit`

<span data-ttu-id="f249f-510">Enumere todas las plantillas disponibles para MVC:</span><span class="sxs-lookup"><span data-stu-id="f249f-510">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

<span data-ttu-id="f249f-511">Instalación de la versión 2.0 de las plantillas Aplicación de página única para ASP.NET Core (opción de comando solo disponible para .NET Core SDK 1.1 y versiones posteriores):</span><span class="sxs-lookup"><span data-stu-id="f249f-511">Install version 2.0 of the Single Page Application templates for ASP.NET Core (command option available for .NET Core SDK 1.1 and later versions only):</span></span>

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

<span data-ttu-id="f249f-512">Creación de un archivo *global.json* en el directorio actual que establezca la versión del SDK en 2.0.0 (solo disponible en el SDK de .NET Core 2.0 o versiones posteriores):</span><span class="sxs-lookup"><span data-stu-id="f249f-512">Create a *global.json* in the current directory setting the SDK version to 2.0.0 (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new globaljson --sdk-version 2.0.0`

## <a name="see-also"></a><span data-ttu-id="f249f-513">Vea también</span><span class="sxs-lookup"><span data-stu-id="f249f-513">See also</span></span>

<span data-ttu-id="f249f-514">[Custom templates for dotnet new](custom-templates.md) (Plantillas personalizadas para dotnet new)</span><span class="sxs-lookup"><span data-stu-id="f249f-514">[Custom templates for dotnet new](custom-templates.md)</span></span>  
[<span data-ttu-id="f249f-515">Creación de una plantilla personalizada para dotnet new</span><span class="sxs-lookup"><span data-stu-id="f249f-515">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)  
[<span data-ttu-id="f249f-516">Repositorio de GitHub dotnet/dotnet-template-samples</span><span class="sxs-lookup"><span data-stu-id="f249f-516">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)  
<span data-ttu-id="f249f-517">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new) (Plantillas disponibles para dotnet new)</span><span class="sxs-lookup"><span data-stu-id="f249f-517">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)</span></span>
