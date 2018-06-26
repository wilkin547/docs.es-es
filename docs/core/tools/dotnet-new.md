---
title: 'Comando dotnet new: CLI de .NET Core'
description: El comando dotnet new crea proyectos de .NET Core basados en la plantilla especificada.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: ae24c4145cc67ca863c07e4d22af8a1c2c2dd732
ms.sourcegitcommit: 3540f614fc94f77ca4ab58df66db2d0f4d52dfee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/01/2018
ms.locfileid: "34570468"
---
# <a name="dotnet-new"></a><span data-ttu-id="7165b-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="7165b-103">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="7165b-104">nombre</span><span class="sxs-lookup"><span data-stu-id="7165b-104">Name</span></span>

<span data-ttu-id="7165b-105">`dotnet new`: crea un nuevo proyecto, archivo de configuración o solución según la plantilla especificada.</span><span class="sxs-lookup"><span data-stu-id="7165b-105">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="7165b-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="7165b-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="7165b-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="7165b-107">.NET Core 2.1</span></span>](#tab/netcore21)
```
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output]
    [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```
# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="7165b-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="7165b-108">.NET Core 2.0</span></span>](#tab/netcore20)
```
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="7165b-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="7165b-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="7165b-110">Description</span><span class="sxs-lookup"><span data-stu-id="7165b-110">Description</span></span>

<span data-ttu-id="7165b-111">El comando `dotnet new` proporciona una manera cómoda de inicializar un proyecto .NET Core válido.</span><span class="sxs-lookup"><span data-stu-id="7165b-111">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span>

<span data-ttu-id="7165b-112">El comando llama al [motor de plantillas](https://github.com/dotnet/templating) para crear los artefactos en el disco basándose en las opciones y la plantilla especificadas.</span><span class="sxs-lookup"><span data-stu-id="7165b-112">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="7165b-113">Argumentos</span><span class="sxs-lookup"><span data-stu-id="7165b-113">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="7165b-114">La plantilla de la que se va a crear una instancia cuando se invoca el comando.</span><span class="sxs-lookup"><span data-stu-id="7165b-114">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="7165b-115">Cada plantilla puede tener opciones específicas que puede pasar.</span><span class="sxs-lookup"><span data-stu-id="7165b-115">Each template might have specific options you can pass.</span></span> <span data-ttu-id="7165b-116">Para obtener más información, vea [Opciones de plantilla](#template-options).</span><span class="sxs-lookup"><span data-stu-id="7165b-116">For more information, see [Template options](#template-options).</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="7165b-117">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="7165b-117">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="7165b-118">El comando contiene una lista predeterminada de plantillas.</span><span class="sxs-lookup"><span data-stu-id="7165b-118">The command contains a default list of templates.</span></span> <span data-ttu-id="7165b-119">Use `dotnet new -l` para obtener una lista de las plantillas disponibles.</span><span class="sxs-lookup"><span data-stu-id="7165b-119">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="7165b-120">En la tabla siguiente se muestran las plantillas que vienen preinstaladas con el SDK de .NET Core 2.1.300.</span><span class="sxs-lookup"><span data-stu-id="7165b-120">The following table shows the templates that come pre-installed with the .NET Core SDK 2.1.300.</span></span> <span data-ttu-id="7165b-121">El lenguaje predeterminado de la plantilla se muestra entre corchetes.</span><span class="sxs-lookup"><span data-stu-id="7165b-121">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="7165b-122">Descripción de plantilla</span><span class="sxs-lookup"><span data-stu-id="7165b-122">Template description</span></span>                          | <span data-ttu-id="7165b-123">Nombre de plantilla</span><span class="sxs-lookup"><span data-stu-id="7165b-123">Template name</span></span>   | <span data-ttu-id="7165b-124">Lenguajes</span><span class="sxs-lookup"><span data-stu-id="7165b-124">Languages</span></span>     |
|----------------------------------------------|-----------------|---------------|
| <span data-ttu-id="7165b-125">Aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="7165b-125">Console application</span></span>                          | `console`       | <span data-ttu-id="7165b-126">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="7165b-126">[C#], F#, VB</span></span>  |
| <span data-ttu-id="7165b-127">Biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="7165b-127">Class library</span></span>                                | `classlib`      | <span data-ttu-id="7165b-128">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="7165b-128">[C#], F#, VB</span></span>  |
| <span data-ttu-id="7165b-129">Proyecto de prueba unitaria</span><span class="sxs-lookup"><span data-stu-id="7165b-129">Unit test project</span></span>                            | `mstest`        | <span data-ttu-id="7165b-130">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="7165b-130">[C#], F#, VB</span></span>  |
| <span data-ttu-id="7165b-131">Proyecto de prueba xUnit</span><span class="sxs-lookup"><span data-stu-id="7165b-131">xUnit test project</span></span>                           | `xunit`         | <span data-ttu-id="7165b-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="7165b-132">[C#], F#, VB</span></span>  |
| <span data-ttu-id="7165b-133">Página de Razor</span><span class="sxs-lookup"><span data-stu-id="7165b-133">Razor page</span></span>                                   | `page`          | <span data-ttu-id="7165b-134">[C#]</span><span class="sxs-lookup"><span data-stu-id="7165b-134">[C#]</span></span>          |
| <span data-ttu-id="7165b-135">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="7165b-135">MVC ViewImports</span></span>                              | `viewimports`   | <span data-ttu-id="7165b-136">[C#]</span><span class="sxs-lookup"><span data-stu-id="7165b-136">[C#]</span></span>          |
| <span data-ttu-id="7165b-137">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="7165b-137">MVC ViewStart</span></span>                                | `viewstart`     | <span data-ttu-id="7165b-138">[C#]</span><span class="sxs-lookup"><span data-stu-id="7165b-138">[C#]</span></span>          |
| <span data-ttu-id="7165b-139">Vacío de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="7165b-139">ASP.NET Core empty</span></span>                           | `web`           | <span data-ttu-id="7165b-140">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="7165b-140">[C#], F#</span></span>      |
| <span data-ttu-id="7165b-141">Aplicación web de ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="7165b-141">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`           | <span data-ttu-id="7165b-142">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="7165b-142">[C#], F#</span></span>      |
| <span data-ttu-id="7165b-143">Aplicación web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="7165b-143">ASP.NET Core Web App</span></span>                         | `razor`         | <span data-ttu-id="7165b-144">[C#]</span><span class="sxs-lookup"><span data-stu-id="7165b-144">[C#]</span></span>          |
| <span data-ttu-id="7165b-145">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="7165b-145">ASP.NET Core with Angular</span></span>                    | `angular`       | <span data-ttu-id="7165b-146">[C#]</span><span class="sxs-lookup"><span data-stu-id="7165b-146">[C#]</span></span>          |
| <span data-ttu-id="7165b-147">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="7165b-147">ASP.NET Core with React.js</span></span>                   | `react`         | <span data-ttu-id="7165b-148">[C#]</span><span class="sxs-lookup"><span data-stu-id="7165b-148">[C#]</span></span>          |
| <span data-ttu-id="7165b-149">ASP.NET Core con React.js y Redux</span><span class="sxs-lookup"><span data-stu-id="7165b-149">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`    | <span data-ttu-id="7165b-150">[C#]</span><span class="sxs-lookup"><span data-stu-id="7165b-150">[C#]</span></span>          |
| <span data-ttu-id="7165b-151">API web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="7165b-151">ASP.NET Core Web API</span></span>                         | `webapi`        | <span data-ttu-id="7165b-152">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="7165b-152">[C#], F#</span></span>      |
| <span data-ttu-id="7165b-153">Biblioteca de clases de Razor</span><span class="sxs-lookup"><span data-stu-id="7165b-153">Razor class library</span></span>                          | `razorclasslib` | <span data-ttu-id="7165b-154">[C#]</span><span class="sxs-lookup"><span data-stu-id="7165b-154">[C#]</span></span>          |
| <span data-ttu-id="7165b-155">archivo global.json</span><span class="sxs-lookup"><span data-stu-id="7165b-155">global.json file</span></span>                             | `globaljson`    |               |
| <span data-ttu-id="7165b-156">Configuración de NuGet</span><span class="sxs-lookup"><span data-stu-id="7165b-156">NuGet config</span></span>                                 | `nugetconfig`   |               |
| <span data-ttu-id="7165b-157">Configuración de la Web</span><span class="sxs-lookup"><span data-stu-id="7165b-157">Web config</span></span>                                   | `webconfig`     |               |
| <span data-ttu-id="7165b-158">Archivo de solución</span><span class="sxs-lookup"><span data-stu-id="7165b-158">Solution file</span></span>                                | `sln`           |               |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="7165b-159">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="7165b-159">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="7165b-160">El comando contiene una lista predeterminada de plantillas.</span><span class="sxs-lookup"><span data-stu-id="7165b-160">The command contains a default list of templates.</span></span> <span data-ttu-id="7165b-161">Use `dotnet new -l` para obtener una lista de las plantillas disponibles.</span><span class="sxs-lookup"><span data-stu-id="7165b-161">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="7165b-162">En la tabla siguiente se muestran las plantillas que vienen preinstaladas con el SDK de .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="7165b-162">The following table shows the templates that come pre-installed with the .NET Core SDK 2.0.</span></span> <span data-ttu-id="7165b-163">El lenguaje predeterminado de la plantilla se muestra entre corchetes.</span><span class="sxs-lookup"><span data-stu-id="7165b-163">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="7165b-164">Descripción de plantilla</span><span class="sxs-lookup"><span data-stu-id="7165b-164">Template description</span></span>                          | <span data-ttu-id="7165b-165">Nombre de plantilla</span><span class="sxs-lookup"><span data-stu-id="7165b-165">Template name</span></span> | <span data-ttu-id="7165b-166">Lenguajes</span><span class="sxs-lookup"><span data-stu-id="7165b-166">Languages</span></span>     |
|----------------------------------------------|---------------|---------------|
| <span data-ttu-id="7165b-167">Aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="7165b-167">Console application</span></span>                          | `console`     | <span data-ttu-id="7165b-168">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="7165b-168">[C#], F#, VB</span></span>  |
| <span data-ttu-id="7165b-169">Biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="7165b-169">Class library</span></span>                                | `classlib`    | <span data-ttu-id="7165b-170">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="7165b-170">[C#], F#, VB</span></span>  |
| <span data-ttu-id="7165b-171">Proyecto de prueba unitaria</span><span class="sxs-lookup"><span data-stu-id="7165b-171">Unit test project</span></span>                            | `mstest`      | <span data-ttu-id="7165b-172">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="7165b-172">[C#], F#, VB</span></span>  |
| <span data-ttu-id="7165b-173">Proyecto de prueba xUnit</span><span class="sxs-lookup"><span data-stu-id="7165b-173">xUnit test project</span></span>                           | `xunit`       | <span data-ttu-id="7165b-174">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="7165b-174">[C#], F#, VB</span></span>  |
| <span data-ttu-id="7165b-175">Vacío de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="7165b-175">ASP.NET Core empty</span></span>                           | `web`         | <span data-ttu-id="7165b-176">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="7165b-176">[C#], F#</span></span>      |
| <span data-ttu-id="7165b-177">Aplicación web de ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="7165b-177">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="7165b-178">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="7165b-178">[C#], F#</span></span>      |
| <span data-ttu-id="7165b-179">Aplicación web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="7165b-179">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="7165b-180">[C#]</span><span class="sxs-lookup"><span data-stu-id="7165b-180">[C#]</span></span>          |
| <span data-ttu-id="7165b-181">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="7165b-181">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="7165b-182">[C#]</span><span class="sxs-lookup"><span data-stu-id="7165b-182">[C#]</span></span>          |
| <span data-ttu-id="7165b-183">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="7165b-183">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="7165b-184">[C#]</span><span class="sxs-lookup"><span data-stu-id="7165b-184">[C#]</span></span>          |
| <span data-ttu-id="7165b-185">ASP.NET Core con React.js y Redux</span><span class="sxs-lookup"><span data-stu-id="7165b-185">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="7165b-186">[C#]</span><span class="sxs-lookup"><span data-stu-id="7165b-186">[C#]</span></span>          |
| <span data-ttu-id="7165b-187">API web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="7165b-187">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="7165b-188">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="7165b-188">[C#], F#</span></span>      |
| <span data-ttu-id="7165b-189">archivo global.json</span><span class="sxs-lookup"><span data-stu-id="7165b-189">global.json file</span></span>                             | `globaljson`  |               |
| <span data-ttu-id="7165b-190">Configuración de NuGet</span><span class="sxs-lookup"><span data-stu-id="7165b-190">NuGet config</span></span>                                 | `nugetconfig` |               |
| <span data-ttu-id="7165b-191">Configuración de la Web</span><span class="sxs-lookup"><span data-stu-id="7165b-191">Web config</span></span>                                   | `webconfig`   |               |
| <span data-ttu-id="7165b-192">Archivo de solución</span><span class="sxs-lookup"><span data-stu-id="7165b-192">Solution file</span></span>                                | `sln`         |               |
| <span data-ttu-id="7165b-193">Página de Razor</span><span class="sxs-lookup"><span data-stu-id="7165b-193">Razor page</span></span>                                   | `page`        |               |
| <span data-ttu-id="7165b-194">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="7165b-194">MVC ViewImports</span></span>                              | `viewimports` |               |
| <span data-ttu-id="7165b-195">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="7165b-195">MVC ViewStart</span></span>                                | `viewstart`   |               |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="7165b-196">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="7165b-196">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="7165b-197">El comando contiene una lista predeterminada de plantillas.</span><span class="sxs-lookup"><span data-stu-id="7165b-197">The command contains a default list of templates.</span></span> <span data-ttu-id="7165b-198">Use `dotnet new -all` para obtener una lista de las plantillas disponibles.</span><span class="sxs-lookup"><span data-stu-id="7165b-198">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="7165b-199">En la tabla siguiente se muestran las plantillas que vienen preinstaladas con el SDK de .NET 1.x.</span><span class="sxs-lookup"><span data-stu-id="7165b-199">The following table shows the templates that come pre-installed with the .NET Core SDK 1.x.</span></span> <span data-ttu-id="7165b-200">El lenguaje predeterminado de la plantilla se muestra entre corchetes.</span><span class="sxs-lookup"><span data-stu-id="7165b-200">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="7165b-201">Descripción de plantilla</span><span class="sxs-lookup"><span data-stu-id="7165b-201">Template description</span></span>  | <span data-ttu-id="7165b-202">Nombre de plantilla</span><span class="sxs-lookup"><span data-stu-id="7165b-202">Template name</span></span> | <span data-ttu-id="7165b-203">Lenguajes</span><span class="sxs-lookup"><span data-stu-id="7165b-203">Languages</span></span> |
|----------------------|---------------|-----------|
| <span data-ttu-id="7165b-204">Aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="7165b-204">Console application</span></span>  | `console`     | <span data-ttu-id="7165b-205">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="7165b-205">[C#], F#</span></span>  |
| <span data-ttu-id="7165b-206">Biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="7165b-206">Class library</span></span>        | `classlib`    | <span data-ttu-id="7165b-207">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="7165b-207">[C#], F#</span></span>  |
| <span data-ttu-id="7165b-208">Proyecto de prueba unitaria</span><span class="sxs-lookup"><span data-stu-id="7165b-208">Unit test project</span></span>    | `mstest`      | <span data-ttu-id="7165b-209">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="7165b-209">[C#], F#</span></span>  |
| <span data-ttu-id="7165b-210">Proyecto de prueba xUnit</span><span class="sxs-lookup"><span data-stu-id="7165b-210">xUnit test project</span></span>   | `xunit`       | <span data-ttu-id="7165b-211">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="7165b-211">[C#], F#</span></span>  |
| <span data-ttu-id="7165b-212">Vacío de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="7165b-212">ASP.NET Core empty</span></span>   | `web`         | <span data-ttu-id="7165b-213">[C#]</span><span class="sxs-lookup"><span data-stu-id="7165b-213">[C#]</span></span>      |
| <span data-ttu-id="7165b-214">Aplicación web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="7165b-214">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="7165b-215">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="7165b-215">[C#], F#</span></span>  |
| <span data-ttu-id="7165b-216">API web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="7165b-216">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="7165b-217">[C#]</span><span class="sxs-lookup"><span data-stu-id="7165b-217">[C#]</span></span>      |
| <span data-ttu-id="7165b-218">Configuración de NuGet</span><span class="sxs-lookup"><span data-stu-id="7165b-218">NuGet config</span></span>         | `nugetconfig` |           |
| <span data-ttu-id="7165b-219">Configuración de la Web</span><span class="sxs-lookup"><span data-stu-id="7165b-219">Web config</span></span>           | `webconfig`   |           |
| <span data-ttu-id="7165b-220">Archivo de solución</span><span class="sxs-lookup"><span data-stu-id="7165b-220">Solution file</span></span>        | `sln`         |           |

---

## <a name="options"></a><span data-ttu-id="7165b-221">Opciones</span><span class="sxs-lookup"><span data-stu-id="7165b-221">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="7165b-222">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="7165b-222">.NET Core 2.1</span></span>](#tab/netcore21)

`--force`

<span data-ttu-id="7165b-223">Fuerza la generación de contenido incluso aunque se vayan a cambiar los archivos existentes.</span><span class="sxs-lookup"><span data-stu-id="7165b-223">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="7165b-224">Esto es necesario cuando el directorio de salida ya contiene un proyecto.</span><span class="sxs-lookup"><span data-stu-id="7165b-224">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="7165b-225">Imprime la ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="7165b-225">Prints out help for the command.</span></span> <span data-ttu-id="7165b-226">Puede invocarse para el propio comando `dotnet new` o para cualquier plantilla, como `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="7165b-226">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="7165b-227">Instala un paquete de plantillas u origen desde los parámetros `PATH` o `NUGET_ID` proporcionados.</span><span class="sxs-lookup"><span data-stu-id="7165b-227">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="7165b-228">Si quiere instalar una versión preliminar de un paquete de plantilla, tendrá que especificar la versión en el formato de `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="7165b-228">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="7165b-229">De manera predeterminada, `dotnet new` pasa \* para la versión, que representa la última versión estable del paquete.</span><span class="sxs-lookup"><span data-stu-id="7165b-229">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="7165b-230">Vea un ejemplo en la sección [Ejemplos](#examples).</span><span class="sxs-lookup"><span data-stu-id="7165b-230">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="7165b-231">Para obtener información sobre cómo crear plantillas personalizadas, consulte [Custom templates for dotnet new](custom-templates.md) (Plantillas personalizadas para dotnet new).</span><span class="sxs-lookup"><span data-stu-id="7165b-231">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="7165b-232">Muestra las plantillas que contienen el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="7165b-232">Lists templates containing the specified name.</span></span> <span data-ttu-id="7165b-233">Si se invoca para el comando `dotnet new`, muestra las plantillas posibles disponibles para un directorio determinado.</span><span class="sxs-lookup"><span data-stu-id="7165b-233">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="7165b-234">Por ejemplo, si el directorio ya contiene un proyecto, no mostrará todas las plantillas del proyecto.</span><span class="sxs-lookup"><span data-stu-id="7165b-234">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="7165b-235">El lenguaje de la plantilla que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="7165b-235">The language of the template to create.</span></span> <span data-ttu-id="7165b-236">El lenguaje aceptado cambia según la plantilla (vea los valores predeterminados en la sección [argumentos](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="7165b-236">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="7165b-237">No es válido para algunas plantillas.</span><span class="sxs-lookup"><span data-stu-id="7165b-237">Not valid for some templates.</span></span>

    > [!NOTE]
    > Some shells interpret `#` as a special character. In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="7165b-238">El nombre de la salida creada.</span><span class="sxs-lookup"><span data-stu-id="7165b-238">The name for the created output.</span></span> <span data-ttu-id="7165b-239">Si no se especifica ningún nombre, se usa el nombre del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="7165b-239">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="7165b-240">Especifica un origen de NuGet para usarlo durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="7165b-240">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="7165b-241">La ubicación para colocar la salida generada.</span><span class="sxs-lookup"><span data-stu-id="7165b-241">Location to place the generated output.</span></span> <span data-ttu-id="7165b-242">El valor predeterminado es el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="7165b-242">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="7165b-243">Filtra plantillas en función de los tipos disponibles.</span><span class="sxs-lookup"><span data-stu-id="7165b-243">Filters templates based on available types.</span></span> <span data-ttu-id="7165b-244">Los valores predefinidos son “project”, “item” y “other”.</span><span class="sxs-lookup"><span data-stu-id="7165b-244">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="7165b-245">Desinstala un paquete de plantillas u origen en los parámetros `PATH` o `NUGET_ID` proporcionados.</span><span class="sxs-lookup"><span data-stu-id="7165b-245">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="7165b-246">Para desinstalar una plantilla mediante `PATH`, debe usar el nombre completo de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="7165b-246">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="7165b-247">Por ejemplo, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* funcionará, pero *./GarciaSoftware.ConsoleTemplate.CSharp* desde la carpeta contenedora no lo hará.</span><span class="sxs-lookup"><span data-stu-id="7165b-247">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="7165b-248">Además, no debe incluir una barra diagonal para finalizar el directorio en la ruta de acceso a la plantilla.</span><span class="sxs-lookup"><span data-stu-id="7165b-248">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="7165b-249">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="7165b-249">.NET Core 2.0</span></span>](#tab/netcore20)

`--force`

<span data-ttu-id="7165b-250">Fuerza la generación de contenido incluso aunque se vayan a cambiar los archivos existentes.</span><span class="sxs-lookup"><span data-stu-id="7165b-250">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="7165b-251">Esto es necesario cuando el directorio de salida ya contiene un proyecto.</span><span class="sxs-lookup"><span data-stu-id="7165b-251">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="7165b-252">Imprime la ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="7165b-252">Prints out help for the command.</span></span> <span data-ttu-id="7165b-253">Puede invocarse para el propio comando `dotnet new` o para cualquier plantilla, como `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="7165b-253">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="7165b-254">Instala un paquete de plantillas u origen desde los parámetros `PATH` o `NUGET_ID` proporcionados.</span><span class="sxs-lookup"><span data-stu-id="7165b-254">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="7165b-255">Si quiere instalar una versión preliminar de un paquete de plantilla, tendrá que especificar la versión en el formato de `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="7165b-255">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="7165b-256">De manera predeterminada, `dotnet new` pasa \* para la versión, que representa la última versión estable del paquete.</span><span class="sxs-lookup"><span data-stu-id="7165b-256">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="7165b-257">Vea un ejemplo en la sección [Ejemplos](#examples).</span><span class="sxs-lookup"><span data-stu-id="7165b-257">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="7165b-258">Para obtener información sobre cómo crear plantillas personalizadas, consulte [Custom templates for dotnet new](custom-templates.md) (Plantillas personalizadas para dotnet new).</span><span class="sxs-lookup"><span data-stu-id="7165b-258">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="7165b-259">Muestra las plantillas que contienen el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="7165b-259">Lists templates containing the specified name.</span></span> <span data-ttu-id="7165b-260">Si se invoca para el comando `dotnet new`, muestra las plantillas posibles disponibles para un directorio determinado.</span><span class="sxs-lookup"><span data-stu-id="7165b-260">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="7165b-261">Por ejemplo, si el directorio ya contiene un proyecto, no mostrará todas las plantillas del proyecto.</span><span class="sxs-lookup"><span data-stu-id="7165b-261">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="7165b-262">El lenguaje de la plantilla que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="7165b-262">The language of the template to create.</span></span> <span data-ttu-id="7165b-263">El lenguaje aceptado cambia según la plantilla (vea los valores predeterminados en la sección [argumentos](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="7165b-263">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="7165b-264">No es válido para algunas plantillas.</span><span class="sxs-lookup"><span data-stu-id="7165b-264">Not valid for some templates.</span></span>

    > [!NOTE]
    > Some shells interpret `#` as a special character. In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="7165b-265">El nombre de la salida creada.</span><span class="sxs-lookup"><span data-stu-id="7165b-265">The name for the created output.</span></span> <span data-ttu-id="7165b-266">Si no se especifica ningún nombre, se usa el nombre del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="7165b-266">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="7165b-267">La ubicación para colocar la salida generada.</span><span class="sxs-lookup"><span data-stu-id="7165b-267">Location to place the generated output.</span></span> <span data-ttu-id="7165b-268">El valor predeterminado es el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="7165b-268">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="7165b-269">Filtra plantillas en función de los tipos disponibles.</span><span class="sxs-lookup"><span data-stu-id="7165b-269">Filters templates based on available types.</span></span> <span data-ttu-id="7165b-270">Los valores predefinidos son “project”, “item” y “other”.</span><span class="sxs-lookup"><span data-stu-id="7165b-270">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="7165b-271">Desinstala un paquete de plantillas u origen en los parámetros `PATH` o `NUGET_ID` proporcionados.</span><span class="sxs-lookup"><span data-stu-id="7165b-271">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="7165b-272">Para desinstalar una plantilla mediante `PATH`, debe usar el nombre completo de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="7165b-272">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="7165b-273">Por ejemplo, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* funcionará, pero *./GarciaSoftware.ConsoleTemplate.CSharp* desde la carpeta contenedora no lo hará.</span><span class="sxs-lookup"><span data-stu-id="7165b-273">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="7165b-274">Además, no debe incluir una barra diagonal para finalizar el directorio en la ruta de acceso a la plantilla.</span><span class="sxs-lookup"><span data-stu-id="7165b-274">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="7165b-275">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="7165b-275">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="7165b-276">Muestra todas las plantillas de un tipo de proyecto específico cuando se ejecuta en el contexto del comando `dotnet new` por sí solo.</span><span class="sxs-lookup"><span data-stu-id="7165b-276">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="7165b-277">Cuando se ejecuta en el contexto de una plantilla específica, como `dotnet new web -all`, `-all` se interpreta como una marca para forzar la creación.</span><span class="sxs-lookup"><span data-stu-id="7165b-277">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="7165b-278">Esto es necesario cuando el directorio de salida ya contiene un proyecto.</span><span class="sxs-lookup"><span data-stu-id="7165b-278">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="7165b-279">Imprime la ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="7165b-279">Prints out help for the command.</span></span> <span data-ttu-id="7165b-280">Puede invocarse para el propio comando `dotnet new` o para cualquier plantilla, como `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="7165b-280">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="7165b-281">Muestra las plantillas que contienen el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="7165b-281">Lists templates containing the specified name.</span></span> <span data-ttu-id="7165b-282">Si se invoca para el comando `dotnet new`, muestra las plantillas posibles disponibles para un directorio determinado.</span><span class="sxs-lookup"><span data-stu-id="7165b-282">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="7165b-283">Por ejemplo, si el directorio ya contiene un proyecto, no mostrará todas las plantillas del proyecto.</span><span class="sxs-lookup"><span data-stu-id="7165b-283">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="7165b-284">El lenguaje de la plantilla que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="7165b-284">The language of the template to create.</span></span> <span data-ttu-id="7165b-285">El lenguaje aceptado cambia según la plantilla (vea los valores predeterminados en la sección [argumentos](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="7165b-285">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="7165b-286">No es válido para algunas plantillas.</span><span class="sxs-lookup"><span data-stu-id="7165b-286">Not valid for some templates.</span></span>

    > [!NOTE]
    > Some shells interpret `#` as a special character. In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="7165b-287">El nombre de la salida creada.</span><span class="sxs-lookup"><span data-stu-id="7165b-287">The name for the created output.</span></span> <span data-ttu-id="7165b-288">Si no se especifica ningún nombre, se usa el nombre del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="7165b-288">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="7165b-289">La ubicación para colocar la salida generada.</span><span class="sxs-lookup"><span data-stu-id="7165b-289">Location to place the generated output.</span></span> <span data-ttu-id="7165b-290">El valor predeterminado es el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="7165b-290">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="7165b-291">Opciones de plantilla</span><span class="sxs-lookup"><span data-stu-id="7165b-291">Template options</span></span>

<span data-ttu-id="7165b-292">Cada plantilla de proyecto puede tener opciones adicionales disponibles.</span><span class="sxs-lookup"><span data-stu-id="7165b-292">Each project template may have additional options available.</span></span> <span data-ttu-id="7165b-293">Las plantillas principales tienen las siguientes opciones adicionales:</span><span class="sxs-lookup"><span data-stu-id="7165b-293">The core templates have the following additional options:</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="7165b-294">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="7165b-294">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="7165b-295">**console, angular, react, reactredux, razorclasslib**</span><span class="sxs-lookup"><span data-stu-id="7165b-295">**console, angular, react, reactredux, razorclasslib**</span></span>

  <span data-ttu-id="7165b-296">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="7165b-296">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="7165b-297">**classlib**</span><span class="sxs-lookup"><span data-stu-id="7165b-297">**classlib**</span></span>

<span data-ttu-id="7165b-298">`-f|--framework <FRAMEWORK>`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="7165b-298">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="7165b-299">Valores: `netcoreapp2.0` para crear una biblioteca de clases de .NET Core o `netstandard2.0` para crear una biblioteca de clases de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="7165b-299">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="7165b-300">El valor predeterminado es `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="7165b-300">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="7165b-301">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="7165b-301">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="7165b-302">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="7165b-302">**mstest, xunit**</span></span>

<span data-ttu-id="7165b-303">`-p|--enable-pack`: habilita el empaquetado para el proyecto mediante [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="7165b-303">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="7165b-304">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="7165b-304">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="7165b-305">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="7165b-305">**globaljson**</span></span>

<span data-ttu-id="7165b-306">`--sdk-version <VERSION_NUMBER>`: especifica la versión del SDK de .NET Core que se usará con el archivo *global.json*.</span><span class="sxs-lookup"><span data-stu-id="7165b-306">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="7165b-307">**web**</span><span class="sxs-lookup"><span data-stu-id="7165b-307">**web**</span></span>

<span data-ttu-id="7165b-308">`--use-launch-settings`: incluye *launchSettings.json* en la salida de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="7165b-308">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="7165b-309">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="7165b-309">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="7165b-310">**webapi**</span><span class="sxs-lookup"><span data-stu-id="7165b-310">**webapi**</span></span>

<span data-ttu-id="7165b-311">`-au|--auth <AUTHENTICATION_TYPE>`: el tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="7165b-311">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="7165b-312">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="7165b-312">The possible values are:</span></span>

- <span data-ttu-id="7165b-313">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="7165b-313">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="7165b-314">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="7165b-314">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="7165b-315">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="7165b-315">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="7165b-316">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="7165b-316">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="7165b-317">`--aad-b2c-instance <INSTANCE>`: la instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="7165b-317">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="7165b-318">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="7165b-318">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="7165b-319">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="7165b-319">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="7165b-320">`-ssp|--susi-policy-id <ID>`: el id. de inicio de sesión y de directiva de registro de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="7165b-320">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="7165b-321">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="7165b-321">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="7165b-322">`--aad-instance <INSTANCE>`: la instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="7165b-322">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="7165b-323">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="7165b-323">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="7165b-324">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="7165b-324">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="7165b-325">`--client-id <ID>`: el id. de cliente para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="7165b-325">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="7165b-326">Úsela con las autenticaciones `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="7165b-326">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="7165b-327">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="7165b-327">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="7165b-328">`--domain <DOMAIN>`: el dominio para el inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="7165b-328">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="7165b-329">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="7165b-329">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="7165b-330">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="7165b-330">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="7165b-331">`--tenant-id <ID>`: el id. de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="7165b-331">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="7165b-332">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="7165b-332">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="7165b-333">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="7165b-333">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="7165b-334">`-r|--org-read-access`: concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="7165b-334">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="7165b-335">Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="7165b-335">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="7165b-336">`--use-launch-settings`: incluye *launchSettings.json* en la salida de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="7165b-336">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="7165b-337">`-uld|--use-local-db`: especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="7165b-337">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="7165b-338">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="7165b-338">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="7165b-339">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="7165b-339">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="7165b-340">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="7165b-340">**mvc, razor**</span></span>

<span data-ttu-id="7165b-341">`-au|--auth <AUTHENTICATION_TYPE>`: el tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="7165b-341">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="7165b-342">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="7165b-342">The possible values are:</span></span>

- <span data-ttu-id="7165b-343">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="7165b-343">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="7165b-344">`Individual`: autenticación individual.</span><span class="sxs-lookup"><span data-stu-id="7165b-344">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="7165b-345">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="7165b-345">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="7165b-346">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="7165b-346">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="7165b-347">`MultiOrg`: autenticación organizativa para varios inquilinos.</span><span class="sxs-lookup"><span data-stu-id="7165b-347">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="7165b-348">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="7165b-348">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="7165b-349">`--aad-b2c-instance <INSTANCE>`: la instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="7165b-349">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="7165b-350">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="7165b-350">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="7165b-351">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="7165b-351">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="7165b-352">`-ssp|--susi-policy-id <ID>`: el id. de inicio de sesión y de directiva de registro de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="7165b-352">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="7165b-353">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="7165b-353">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="7165b-354">`-rp|--reset-password-policy-id <ID>`: el id. de la directiva de restablecimiento de contraseñas para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="7165b-354">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="7165b-355">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="7165b-355">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="7165b-356">`-ep|--edit-profile-policy-id <ID>`: el id. de directiva de edición de perfiles para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="7165b-356">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="7165b-357">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="7165b-357">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="7165b-358">`--aad-instance <INSTANCE>`: la instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="7165b-358">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="7165b-359">Úsela con las autenticaciones `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="7165b-359">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="7165b-360">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="7165b-360">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="7165b-361">`--client-id <ID>`: el id. de cliente para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="7165b-361">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="7165b-362">Úsela con las autenticaciones `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="7165b-362">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="7165b-363">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="7165b-363">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="7165b-364">`--domain <DOMAIN>`: el dominio para el inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="7165b-364">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="7165b-365">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="7165b-365">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="7165b-366">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="7165b-366">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="7165b-367">`--tenant-id <ID>`: el id. de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="7165b-367">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="7165b-368">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="7165b-368">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="7165b-369">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="7165b-369">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="7165b-370">`--callback-path <PATH>`: la ruta de acceso de solicitud de la ruta de acceso de la base de la aplicación del URI de redirección.</span><span class="sxs-lookup"><span data-stu-id="7165b-370">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="7165b-371">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="7165b-371">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="7165b-372">El valor predeterminado es `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="7165b-372">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="7165b-373">`-r|--org-read-access`: concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="7165b-373">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="7165b-374">Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="7165b-374">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="7165b-375">`--use-launch-settings`: incluye *launchSettings.json* en la salida de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="7165b-375">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="7165b-376">`--use-browserlink`: incluye BrowserLink en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="7165b-376">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="7165b-377">`-uld|--use-local-db`: especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="7165b-377">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="7165b-378">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="7165b-378">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="7165b-379">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="7165b-379">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="7165b-380">**page**</span><span class="sxs-lookup"><span data-stu-id="7165b-380">**page**</span></span>

<span data-ttu-id="7165b-381">`-na|--namespace <NAMESPACE_NAME>`: espacio de nombres para el código generado.</span><span class="sxs-lookup"><span data-stu-id="7165b-381">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="7165b-382">El valor predeterminado es `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="7165b-382">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="7165b-383">`-np|--no-pagemodel`: crea la página sin PageModel.</span><span class="sxs-lookup"><span data-stu-id="7165b-383">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="7165b-384">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="7165b-384">**viewimports**</span></span>

<span data-ttu-id="7165b-385">`-na|--namespace <NAMESPACE_NAME>`: espacio de nombres para el código generado.</span><span class="sxs-lookup"><span data-stu-id="7165b-385">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="7165b-386">El valor predeterminado es `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="7165b-386">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="7165b-387">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="7165b-387">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="7165b-388">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="7165b-388">**console, angular, react, reactredux**</span></span>

  <span data-ttu-id="7165b-389">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="7165b-389">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="7165b-390">**classlib**</span><span class="sxs-lookup"><span data-stu-id="7165b-390">**classlib**</span></span>

<span data-ttu-id="7165b-391">`-f|--framework <FRAMEWORK>`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="7165b-391">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="7165b-392">Valores: `netcoreapp2.0` para crear una biblioteca de clases de .NET Core o `netstandard2.0` para crear una biblioteca de clases de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="7165b-392">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="7165b-393">El valor predeterminado es `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="7165b-393">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="7165b-394">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="7165b-394">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="7165b-395">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="7165b-395">**mstest, xunit**</span></span>

<span data-ttu-id="7165b-396">`-p|--enable-pack`: habilita el empaquetado para el proyecto mediante [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="7165b-396">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="7165b-397">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="7165b-397">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="7165b-398">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="7165b-398">**globaljson**</span></span>

<span data-ttu-id="7165b-399">`--sdk-version <VERSION_NUMBER>`: especifica la versión del SDK de .NET Core que se usará con el archivo *global.json*.</span><span class="sxs-lookup"><span data-stu-id="7165b-399">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="7165b-400">**web**</span><span class="sxs-lookup"><span data-stu-id="7165b-400">**web**</span></span>

<span data-ttu-id="7165b-401">`--use-launch-settings`: incluye *launchSettings.json* en la salida de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="7165b-401">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="7165b-402">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="7165b-402">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="7165b-403">**webapi**</span><span class="sxs-lookup"><span data-stu-id="7165b-403">**webapi**</span></span>

<span data-ttu-id="7165b-404">`-au|--auth <AUTHENTICATION_TYPE>`: el tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="7165b-404">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="7165b-405">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="7165b-405">The possible values are:</span></span>

- <span data-ttu-id="7165b-406">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="7165b-406">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="7165b-407">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="7165b-407">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="7165b-408">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="7165b-408">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="7165b-409">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="7165b-409">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="7165b-410">`--aad-b2c-instance <INSTANCE>`: la instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="7165b-410">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="7165b-411">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="7165b-411">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="7165b-412">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="7165b-412">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="7165b-413">`-ssp|--susi-policy-id <ID>`: el id. de inicio de sesión y de directiva de registro de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="7165b-413">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="7165b-414">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="7165b-414">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="7165b-415">`--aad-instance <INSTANCE>`: la instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="7165b-415">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="7165b-416">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="7165b-416">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="7165b-417">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="7165b-417">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="7165b-418">`--client-id <ID>`: el id. de cliente para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="7165b-418">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="7165b-419">Úsela con las autenticaciones `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="7165b-419">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="7165b-420">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="7165b-420">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="7165b-421">`--domain <DOMAIN>`: el dominio para el inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="7165b-421">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="7165b-422">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="7165b-422">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="7165b-423">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="7165b-423">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="7165b-424">`--tenant-id <ID>`: el id. de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="7165b-424">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="7165b-425">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="7165b-425">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="7165b-426">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="7165b-426">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="7165b-427">`-r|--org-read-access`: concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="7165b-427">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="7165b-428">Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="7165b-428">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="7165b-429">`--use-launch-settings`: incluye *launchSettings.json* en la salida de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="7165b-429">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="7165b-430">`-uld|--use-local-db`: especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="7165b-430">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="7165b-431">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="7165b-431">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="7165b-432">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="7165b-432">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="7165b-433">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="7165b-433">**mvc, razor**</span></span>

<span data-ttu-id="7165b-434">`-au|--auth <AUTHENTICATION_TYPE>`: el tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="7165b-434">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="7165b-435">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="7165b-435">The possible values are:</span></span>

- <span data-ttu-id="7165b-436">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="7165b-436">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="7165b-437">`Individual`: autenticación individual.</span><span class="sxs-lookup"><span data-stu-id="7165b-437">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="7165b-438">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="7165b-438">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="7165b-439">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="7165b-439">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="7165b-440">`MultiOrg`: autenticación organizativa para varios inquilinos.</span><span class="sxs-lookup"><span data-stu-id="7165b-440">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="7165b-441">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="7165b-441">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="7165b-442">`--aad-b2c-instance <INSTANCE>`: la instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="7165b-442">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="7165b-443">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="7165b-443">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="7165b-444">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="7165b-444">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="7165b-445">`-ssp|--susi-policy-id <ID>`: el id. de inicio de sesión y de directiva de registro de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="7165b-445">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="7165b-446">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="7165b-446">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="7165b-447">`-rp|--reset-password-policy-id <ID>`: el id. de la directiva de restablecimiento de contraseñas para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="7165b-447">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="7165b-448">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="7165b-448">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="7165b-449">`-ep|--edit-profile-policy-id <ID>`: el id. de directiva de edición de perfiles para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="7165b-449">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="7165b-450">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="7165b-450">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="7165b-451">`--aad-instance <INSTANCE>`: la instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="7165b-451">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="7165b-452">Úsela con las autenticaciones `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="7165b-452">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="7165b-453">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="7165b-453">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="7165b-454">`--client-id <ID>`: el id. de cliente para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="7165b-454">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="7165b-455">Úsela con las autenticaciones `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="7165b-455">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="7165b-456">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="7165b-456">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="7165b-457">`--domain <DOMAIN>`: el dominio para el inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="7165b-457">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="7165b-458">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="7165b-458">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="7165b-459">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="7165b-459">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="7165b-460">`--tenant-id <ID>`: el id. de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="7165b-460">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="7165b-461">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="7165b-461">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="7165b-462">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="7165b-462">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="7165b-463">`--callback-path <PATH>`: la ruta de acceso de solicitud de la ruta de acceso de la base de la aplicación del URI de redirección.</span><span class="sxs-lookup"><span data-stu-id="7165b-463">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="7165b-464">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="7165b-464">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="7165b-465">El valor predeterminado es `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="7165b-465">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="7165b-466">`-r|--org-read-access`: concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="7165b-466">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="7165b-467">Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="7165b-467">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="7165b-468">`--use-launch-settings`: incluye *launchSettings.json* en la salida de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="7165b-468">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="7165b-469">`--use-browserlink`: incluye BrowserLink en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="7165b-469">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="7165b-470">`-uld|--use-local-db`: especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="7165b-470">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="7165b-471">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="7165b-471">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="7165b-472">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="7165b-472">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="7165b-473">**page**</span><span class="sxs-lookup"><span data-stu-id="7165b-473">**page**</span></span>

<span data-ttu-id="7165b-474">`-na|--namespace <NAMESPACE_NAME>`: espacio de nombres para el código generado.</span><span class="sxs-lookup"><span data-stu-id="7165b-474">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="7165b-475">El valor predeterminado es `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="7165b-475">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="7165b-476">`-np|--no-pagemodel`: crea la página sin PageModel.</span><span class="sxs-lookup"><span data-stu-id="7165b-476">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="7165b-477">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="7165b-477">**viewimports**</span></span>

<span data-ttu-id="7165b-478">`-na|--namespace <NAMESPACE_NAME>`: espacio de nombres para el código generado.</span><span class="sxs-lookup"><span data-stu-id="7165b-478">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="7165b-479">El valor predeterminado es `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="7165b-479">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="7165b-480">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="7165b-480">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="7165b-481">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="7165b-481">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="7165b-482">`-f|--framework`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="7165b-482">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="7165b-483">Valores: `netcoreapp1.0` o `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="7165b-483">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="7165b-484">El valor predeterminado es `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="7165b-484">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="7165b-485">**classlib**</span><span class="sxs-lookup"><span data-stu-id="7165b-485">**classlib**</span></span>

<span data-ttu-id="7165b-486">`-f|--framework`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="7165b-486">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="7165b-487">Valores: `netcoreapp1.0`, `netcoreapp1.1` o de `netstandard1.0` a `netstandard1.6`.</span><span class="sxs-lookup"><span data-stu-id="7165b-487">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="7165b-488">El valor predeterminado es `netstandard1.4`.</span><span class="sxs-lookup"><span data-stu-id="7165b-488">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="7165b-489">**mvc**</span><span class="sxs-lookup"><span data-stu-id="7165b-489">**mvc**</span></span>

<span data-ttu-id="7165b-490">`-f|--framework`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="7165b-490">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="7165b-491">Valores: `netcoreapp1.0` o `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="7165b-491">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="7165b-492">El valor predeterminado es `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="7165b-492">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="7165b-493">`-au|--auth`: el tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="7165b-493">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="7165b-494">Valores: `None` o `Individual`.</span><span class="sxs-lookup"><span data-stu-id="7165b-494">Values: `None` or `Individual`.</span></span> <span data-ttu-id="7165b-495">El valor predeterminado es `None`.</span><span class="sxs-lookup"><span data-stu-id="7165b-495">The default value is `None`.</span></span>

<span data-ttu-id="7165b-496">`-uld|--use-local-db`: especifica si se va a usar o no LocalDB en lugar de SQLite.</span><span class="sxs-lookup"><span data-stu-id="7165b-496">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="7165b-497">Valores: `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="7165b-497">Values: `true` or `false`.</span></span> <span data-ttu-id="7165b-498">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="7165b-498">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="7165b-499">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="7165b-499">Examples</span></span>

<span data-ttu-id="7165b-500">Creación de un proyecto de aplicación de consola con F# en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="7165b-500">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang F#`

<span data-ttu-id="7165b-501">Creación de un proyecto de biblioteca de clases de .NET Standard en el directorio especificado (disponible solo con el SDK de .NET Core 2.0 o versiones posteriores):</span><span class="sxs-lookup"><span data-stu-id="7165b-501">Create a .NET Standard class library project in the specified directory (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="7165b-502">Creación de un proyecto de aplicación MVC de ASP.NET Core C# en el directorio actual sin autenticación destinado a .NET Core 2.0:</span><span class="sxs-lookup"><span data-stu-id="7165b-502">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication targeting .NET Core 2.0:</span></span>

`dotnet new mvc -au None -f netcoreapp2.0`

<span data-ttu-id="7165b-503">Creación de una aplicación de xUnit que tenga como destino .NET Core 2.0:</span><span class="sxs-lookup"><span data-stu-id="7165b-503">Create a new xUnit application targeting .NET Core 2.0:</span></span>

`dotnet new xunit --framework netcoreapp2.0`

<span data-ttu-id="7165b-504">Enumere todas las plantillas disponibles para MVC:</span><span class="sxs-lookup"><span data-stu-id="7165b-504">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

<span data-ttu-id="7165b-505">Instalación de la versión 2.0 de las plantillas Aplicación de página única para ASP.NET Core (opción de comando solo disponible para .NET Core SDK 1.1 y versiones posteriores):</span><span class="sxs-lookup"><span data-stu-id="7165b-505">Install version 2.0 of the Single Page Application templates for ASP.NET Core (command option available for .NET Core SDK 1.1 and later versions only):</span></span>

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

<span data-ttu-id="7165b-506">Creación de un archivo *global.json* en el directorio actual que establezca la versión del SDK en 2.0.0 (solo disponible en el SDK de .NET Core 2.0 o versiones posteriores):</span><span class="sxs-lookup"><span data-stu-id="7165b-506">Create a *global.json* in the current directory setting the SDK version to 2.0.0 (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new globaljson --sdk-version 2.0.0`

## <a name="see-also"></a><span data-ttu-id="7165b-507">Vea también</span><span class="sxs-lookup"><span data-stu-id="7165b-507">See also</span></span>

<span data-ttu-id="7165b-508">[Custom templates for dotnet new](custom-templates.md) (Plantillas personalizadas para dotnet new)</span><span class="sxs-lookup"><span data-stu-id="7165b-508">[Custom templates for dotnet new](custom-templates.md)</span></span>  
[<span data-ttu-id="7165b-509">Creación de una plantilla personalizada para dotnet new</span><span class="sxs-lookup"><span data-stu-id="7165b-509">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)  
[<span data-ttu-id="7165b-510">Repositorio de GitHub dotnet/dotnet-template-samples</span><span class="sxs-lookup"><span data-stu-id="7165b-510">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)  
<span data-ttu-id="7165b-511">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new) (Plantillas disponibles para dotnet new)</span><span class="sxs-lookup"><span data-stu-id="7165b-511">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)</span></span>