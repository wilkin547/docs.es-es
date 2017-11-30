---
title: 'Comando dotnet new: CLI de .NET Core'
description: El comando dotnet new crea proyectos de .NET Core basados en la plantilla especificada.
keywords: dotnet-new, CLI, comando de CLI, .NET Core
author: mairaw
ms.author: mairaw
ms.date: 08/13/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: fcc3ed2e-9265-4d50-b59e-dc2e5c190b34
ms.openlocfilehash: d64881380febee08414f57a36ed92079e8d69ed6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="dotnet-new"></a><span data-ttu-id="9b919-104">dotnet new</span><span class="sxs-lookup"><span data-stu-id="9b919-104">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="9b919-105">Name</span><span class="sxs-lookup"><span data-stu-id="9b919-105">Name</span></span>

<span data-ttu-id="9b919-106">`dotnet new`: crea un nuevo proyecto, archivo de configuración o solución según la plantilla especificada.</span><span class="sxs-lookup"><span data-stu-id="9b919-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="9b919-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="9b919-107">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="9b919-108">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="9b919-108">.NET Core 2.x</span></span>](#tab/netcore2x)
```
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="9b919-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="9b919-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="9b919-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="9b919-110">Description</span></span>

<span data-ttu-id="9b919-111">El comando `dotnet new` proporciona una manera cómoda de inicializar un proyecto .NET Core válido.</span><span class="sxs-lookup"><span data-stu-id="9b919-111">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span> 

<span data-ttu-id="9b919-112">El comando llama al [motor de plantillas](https://github.com/dotnet/templating) para crear los artefactos en el disco basándose en las opciones y la plantilla especificadas.</span><span class="sxs-lookup"><span data-stu-id="9b919-112">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="9b919-113">Argumentos</span><span class="sxs-lookup"><span data-stu-id="9b919-113">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="9b919-114">La plantilla de la que se va a crear una instancia cuando se invoca el comando.</span><span class="sxs-lookup"><span data-stu-id="9b919-114">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="9b919-115">Cada plantilla puede tener opciones específicas que puede pasar.</span><span class="sxs-lookup"><span data-stu-id="9b919-115">Each template might have specific options you can pass.</span></span> <span data-ttu-id="9b919-116">Para obtener más información, vea [Opciones de plantilla](#template-options).</span><span class="sxs-lookup"><span data-stu-id="9b919-116">For more information, see [Template options](#template-options).</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="9b919-117">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="9b919-117">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="9b919-118">El comando contiene una lista predeterminada de plantillas.</span><span class="sxs-lookup"><span data-stu-id="9b919-118">The command contains a default list of templates.</span></span> <span data-ttu-id="9b919-119">Use `dotnet new -l` para obtener una lista de las plantillas disponibles.</span><span class="sxs-lookup"><span data-stu-id="9b919-119">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="9b919-120">En la siguiente tabla se muestran las plantillas que vienen preinstaladas con el SDK de .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="9b919-120">The following table shows the templates that come pre-installed with the .NET Core 2.0 SDK.</span></span> <span data-ttu-id="9b919-121">El lenguaje predeterminado de la plantilla se muestra entre corchetes.</span><span class="sxs-lookup"><span data-stu-id="9b919-121">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="9b919-122">Descripción de plantilla</span><span class="sxs-lookup"><span data-stu-id="9b919-122">Template description</span></span>                          | <span data-ttu-id="9b919-123">Nombre de plantilla</span><span class="sxs-lookup"><span data-stu-id="9b919-123">Template name</span></span>  | <span data-ttu-id="9b919-124">Lenguajes</span><span class="sxs-lookup"><span data-stu-id="9b919-124">Languages</span></span>     |
|----------------------------------------------|----------------|---------------|
| <span data-ttu-id="9b919-125">Aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="9b919-125">Console application</span></span>                          | <span data-ttu-id="9b919-126">consola</span><span class="sxs-lookup"><span data-stu-id="9b919-126">console</span></span>        | <span data-ttu-id="9b919-127">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="9b919-127">[C#], F#, VB</span></span>  |
| <span data-ttu-id="9b919-128">Biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="9b919-128">Class library</span></span>                                | <span data-ttu-id="9b919-129">classlib</span><span class="sxs-lookup"><span data-stu-id="9b919-129">classlib</span></span>       | <span data-ttu-id="9b919-130">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="9b919-130">[C#], F#, VB</span></span>  |
| <span data-ttu-id="9b919-131">Proyecto de prueba unitaria</span><span class="sxs-lookup"><span data-stu-id="9b919-131">Unit test project</span></span>                            | <span data-ttu-id="9b919-132">mstest</span><span class="sxs-lookup"><span data-stu-id="9b919-132">mstest</span></span>         | <span data-ttu-id="9b919-133">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="9b919-133">[C#], F#, VB</span></span>  |
| <span data-ttu-id="9b919-134">Proyecto de prueba xUnit</span><span class="sxs-lookup"><span data-stu-id="9b919-134">xUnit test project</span></span>                           | <span data-ttu-id="9b919-135">xunit</span><span class="sxs-lookup"><span data-stu-id="9b919-135">xunit</span></span>          | <span data-ttu-id="9b919-136">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="9b919-136">[C#], F#, VB</span></span>  |
| <span data-ttu-id="9b919-137">Vacío de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="9b919-137">ASP.NET Core empty</span></span>                           | <span data-ttu-id="9b919-138">web</span><span class="sxs-lookup"><span data-stu-id="9b919-138">web</span></span>            | <span data-ttu-id="9b919-139">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="9b919-139">[C#], F#</span></span>      |
| <span data-ttu-id="9b919-140">Aplicación web de ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="9b919-140">ASP.NET Core Web App (Model-View-Controller)</span></span> | <span data-ttu-id="9b919-141">mvc</span><span class="sxs-lookup"><span data-stu-id="9b919-141">mvc</span></span>            | <span data-ttu-id="9b919-142">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="9b919-142">[C#], F#</span></span>      |
| <span data-ttu-id="9b919-143">Aplicación web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="9b919-143">ASP.NET Core Web App</span></span>                         | <span data-ttu-id="9b919-144">razor</span><span class="sxs-lookup"><span data-stu-id="9b919-144">razor</span></span>          | <span data-ttu-id="9b919-145">[C#]</span><span class="sxs-lookup"><span data-stu-id="9b919-145">[C#]</span></span>          |
| <span data-ttu-id="9b919-146">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="9b919-146">ASP.NET Core with Angular</span></span>                    | <span data-ttu-id="9b919-147">angular</span><span class="sxs-lookup"><span data-stu-id="9b919-147">angular</span></span>        | <span data-ttu-id="9b919-148">[C#]</span><span class="sxs-lookup"><span data-stu-id="9b919-148">[C#]</span></span>          |
| <span data-ttu-id="9b919-149">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="9b919-149">ASP.NET Core with React.js</span></span>                   | <span data-ttu-id="9b919-150">react</span><span class="sxs-lookup"><span data-stu-id="9b919-150">react</span></span>          | <span data-ttu-id="9b919-151">[C#]</span><span class="sxs-lookup"><span data-stu-id="9b919-151">[C#]</span></span>          |
| <span data-ttu-id="9b919-152">ASP.NET Core con React.js y Redux</span><span class="sxs-lookup"><span data-stu-id="9b919-152">ASP.NET Core with React.js and Redux</span></span>         | <span data-ttu-id="9b919-153">reactredux</span><span class="sxs-lookup"><span data-stu-id="9b919-153">reactredux</span></span>     | <span data-ttu-id="9b919-154">[C#]</span><span class="sxs-lookup"><span data-stu-id="9b919-154">[C#]</span></span>          |
| <span data-ttu-id="9b919-155">API web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="9b919-155">ASP.NET Core Web API</span></span>                         | <span data-ttu-id="9b919-156">webapi</span><span class="sxs-lookup"><span data-stu-id="9b919-156">webapi</span></span>         | <span data-ttu-id="9b919-157">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="9b919-157">[C#], F#</span></span>      |
| <span data-ttu-id="9b919-158">archivo global.json</span><span class="sxs-lookup"><span data-stu-id="9b919-158">global.json file</span></span>                             | <span data-ttu-id="9b919-159">globaljson</span><span class="sxs-lookup"><span data-stu-id="9b919-159">globaljson</span></span>     |               |
| <span data-ttu-id="9b919-160">Configuración de NuGet</span><span class="sxs-lookup"><span data-stu-id="9b919-160">Nuget config</span></span>                                 | <span data-ttu-id="9b919-161">nugetconfig</span><span class="sxs-lookup"><span data-stu-id="9b919-161">nugetconfig</span></span>    |               |
| <span data-ttu-id="9b919-162">Configuración de la Web</span><span class="sxs-lookup"><span data-stu-id="9b919-162">Web config</span></span>                                   | <span data-ttu-id="9b919-163">webconfig</span><span class="sxs-lookup"><span data-stu-id="9b919-163">webconfig</span></span>      |               |
| <span data-ttu-id="9b919-164">Archivo de solución</span><span class="sxs-lookup"><span data-stu-id="9b919-164">Solution file</span></span>                                | <span data-ttu-id="9b919-165">sln</span><span class="sxs-lookup"><span data-stu-id="9b919-165">sln</span></span>            |               |
| <span data-ttu-id="9b919-166">Página de Razor</span><span class="sxs-lookup"><span data-stu-id="9b919-166">Razor page</span></span>                                   | <span data-ttu-id="9b919-167">página</span><span class="sxs-lookup"><span data-stu-id="9b919-167">page</span></span>           |               |
| <span data-ttu-id="9b919-168">MVC/ViewImports</span><span class="sxs-lookup"><span data-stu-id="9b919-168">MVC/ViewImports</span></span>                              | <span data-ttu-id="9b919-169">viewimports</span><span class="sxs-lookup"><span data-stu-id="9b919-169">viewimports</span></span>    |               |
| <span data-ttu-id="9b919-170">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="9b919-170">MVC ViewStart</span></span>                                | <span data-ttu-id="9b919-171">viewstart</span><span class="sxs-lookup"><span data-stu-id="9b919-171">viewstart</span></span>      |               |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="9b919-172">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="9b919-172">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="9b919-173">El comando contiene una lista predeterminada de plantillas.</span><span class="sxs-lookup"><span data-stu-id="9b919-173">The command contains a default list of templates.</span></span> <span data-ttu-id="9b919-174">Use `dotnet new -all` para obtener una lista de las plantillas disponibles.</span><span class="sxs-lookup"><span data-stu-id="9b919-174">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="9b919-175">En la siguiente tabla se muestran las plantillas que vienen preinstaladas con el SDK de .NET Core 1.x.</span><span class="sxs-lookup"><span data-stu-id="9b919-175">The following table shows the templates that come pre-installed with the .NET Core 1.x SDK.</span></span> <span data-ttu-id="9b919-176">El lenguaje predeterminado de la plantilla se muestra entre corchetes.</span><span class="sxs-lookup"><span data-stu-id="9b919-176">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="9b919-177">Descripción de plantilla</span><span class="sxs-lookup"><span data-stu-id="9b919-177">Template description</span></span>  | <span data-ttu-id="9b919-178">Nombre de plantilla</span><span class="sxs-lookup"><span data-stu-id="9b919-178">Template name</span></span>  | <span data-ttu-id="9b919-179">Lenguajes</span><span class="sxs-lookup"><span data-stu-id="9b919-179">Languages</span></span> |
|----------------------|----------------|-----------|
| <span data-ttu-id="9b919-180">Aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="9b919-180">Console application</span></span>  | <span data-ttu-id="9b919-181">consola</span><span class="sxs-lookup"><span data-stu-id="9b919-181">console</span></span>        | <span data-ttu-id="9b919-182">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="9b919-182">[C#], F#</span></span>  |
| <span data-ttu-id="9b919-183">Biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="9b919-183">Class library</span></span>        | <span data-ttu-id="9b919-184">classlib</span><span class="sxs-lookup"><span data-stu-id="9b919-184">classlib</span></span>       | <span data-ttu-id="9b919-185">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="9b919-185">[C#], F#</span></span>  |
| <span data-ttu-id="9b919-186">Proyecto de prueba unitaria</span><span class="sxs-lookup"><span data-stu-id="9b919-186">Unit test project</span></span>    | <span data-ttu-id="9b919-187">mstest</span><span class="sxs-lookup"><span data-stu-id="9b919-187">mstest</span></span>         | <span data-ttu-id="9b919-188">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="9b919-188">[C#], F#</span></span>  |
| <span data-ttu-id="9b919-189">Proyecto de prueba xUnit</span><span class="sxs-lookup"><span data-stu-id="9b919-189">xUnit test project</span></span>   | <span data-ttu-id="9b919-190">xunit</span><span class="sxs-lookup"><span data-stu-id="9b919-190">xunit</span></span>          | <span data-ttu-id="9b919-191">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="9b919-191">[C#], F#</span></span>  |
| <span data-ttu-id="9b919-192">Vacío de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="9b919-192">ASP.NET Core empty</span></span>   | <span data-ttu-id="9b919-193">web</span><span class="sxs-lookup"><span data-stu-id="9b919-193">web</span></span>            | <span data-ttu-id="9b919-194">[C#]</span><span class="sxs-lookup"><span data-stu-id="9b919-194">[C#]</span></span>      |
| <span data-ttu-id="9b919-195">Aplicación web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="9b919-195">ASP.NET Core Web App</span></span> | <span data-ttu-id="9b919-196">mvc</span><span class="sxs-lookup"><span data-stu-id="9b919-196">mvc</span></span>            | <span data-ttu-id="9b919-197">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="9b919-197">[C#], F#</span></span>  |
| <span data-ttu-id="9b919-198">API web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="9b919-198">ASP.NET Core Web API</span></span> | <span data-ttu-id="9b919-199">webapi</span><span class="sxs-lookup"><span data-stu-id="9b919-199">webapi</span></span>         | <span data-ttu-id="9b919-200">[C#]</span><span class="sxs-lookup"><span data-stu-id="9b919-200">[C#]</span></span>      |
| <span data-ttu-id="9b919-201">Configuración de NuGet</span><span class="sxs-lookup"><span data-stu-id="9b919-201">Nuget config</span></span>         | <span data-ttu-id="9b919-202">nugetconfig</span><span class="sxs-lookup"><span data-stu-id="9b919-202">nugetconfig</span></span>    |           |
| <span data-ttu-id="9b919-203">Configuración de la Web</span><span class="sxs-lookup"><span data-stu-id="9b919-203">Web config</span></span>           | <span data-ttu-id="9b919-204">webconfig</span><span class="sxs-lookup"><span data-stu-id="9b919-204">webconfig</span></span>      |           |
| <span data-ttu-id="9b919-205">Archivo de solución</span><span class="sxs-lookup"><span data-stu-id="9b919-205">Solution file</span></span>        | <span data-ttu-id="9b919-206">sln</span><span class="sxs-lookup"><span data-stu-id="9b919-206">sln</span></span>            |           |

---

## <a name="options"></a><span data-ttu-id="9b919-207">Opciones</span><span class="sxs-lookup"><span data-stu-id="9b919-207">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="9b919-208">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="9b919-208">.NET Core 2.x</span></span>](#tab/netcore2x)

`--force`

<span data-ttu-id="9b919-209">Fuerza la generación de contenido incluso aunque se vayan a cambiar los archivos existentes.</span><span class="sxs-lookup"><span data-stu-id="9b919-209">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="9b919-210">Esto es necesario cuando el directorio de salida ya contiene un proyecto.</span><span class="sxs-lookup"><span data-stu-id="9b919-210">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="9b919-211">Imprime la ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="9b919-211">Prints out help for the command.</span></span> <span data-ttu-id="9b919-212">Puede invocarse para el propio comando `dotnet new` o para cualquier plantilla, como `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="9b919-212">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="9b919-213">Instala un paquete de plantillas u origen desde los parámetros `PATH` o `NUGET_ID` proporcionados.</span><span class="sxs-lookup"><span data-stu-id="9b919-213">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="9b919-214">Para obtener información sobre cómo crear plantillas personalizadas, consulte [Custom templates for dotnet new](custom-templates.md) (Plantillas personalizadas para dotnet new).</span><span class="sxs-lookup"><span data-stu-id="9b919-214">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="9b919-215">Muestra las plantillas que contienen el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="9b919-215">Lists templates containing the specified name.</span></span> <span data-ttu-id="9b919-216">Si se invoca para el comando `dotnet new`, muestra las plantillas posibles disponibles para un directorio determinado.</span><span class="sxs-lookup"><span data-stu-id="9b919-216">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="9b919-217">Por ejemplo, si el directorio ya contiene un proyecto, no mostrará todas las plantillas del proyecto.</span><span class="sxs-lookup"><span data-stu-id="9b919-217">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="9b919-218">El lenguaje de la plantilla que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="9b919-218">The language of the template to create.</span></span> <span data-ttu-id="9b919-219">El lenguaje aceptado cambia según la plantilla (vea los valores predeterminados en la sección [argumentos](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="9b919-219">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="9b919-220">No es válido para algunas plantillas.</span><span class="sxs-lookup"><span data-stu-id="9b919-220">Not valid for some templates.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="9b919-221">El nombre de la salida creada.</span><span class="sxs-lookup"><span data-stu-id="9b919-221">The name for the created output.</span></span> <span data-ttu-id="9b919-222">Si no se especifica ningún nombre, se usa el nombre del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="9b919-222">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="9b919-223">La ubicación para colocar la salida generada.</span><span class="sxs-lookup"><span data-stu-id="9b919-223">Location to place the generated output.</span></span> <span data-ttu-id="9b919-224">El valor predeterminado es el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="9b919-224">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="9b919-225">Filtra plantillas en función de los tipos disponibles.</span><span class="sxs-lookup"><span data-stu-id="9b919-225">Filters templates based on available types.</span></span> <span data-ttu-id="9b919-226">Los valores predefinidos son “project”, “item” y “other”.</span><span class="sxs-lookup"><span data-stu-id="9b919-226">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="9b919-227">Desinstala un paquete de plantillas u origen en los parámetros `PATH` o `NUGET_ID` proporcionados.</span><span class="sxs-lookup"><span data-stu-id="9b919-227">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="9b919-228">Para desinstalar una plantilla mediante `PATH`, debe usar el nombre completo de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="9b919-228">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="9b919-229">Por ejemplo, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* funcionará, pero *./GarciaSoftware.ConsoleTemplate.CSharp* desde la carpeta contenedora no lo hará.</span><span class="sxs-lookup"><span data-stu-id="9b919-229">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="9b919-230">Además, no debe incluir una barra diagonal para finalizar el directorio en la ruta de acceso a la plantilla.</span><span class="sxs-lookup"><span data-stu-id="9b919-230">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="9b919-231">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="9b919-231">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="9b919-232">Muestra todas las plantillas de un tipo de proyecto específico cuando se ejecuta en el contexto del comando `dotnet new` por sí solo.</span><span class="sxs-lookup"><span data-stu-id="9b919-232">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="9b919-233">Cuando se ejecuta en el contexto de una plantilla específica, como `dotnet new web -all`, `-all` se interpreta como una marca para forzar la creación.</span><span class="sxs-lookup"><span data-stu-id="9b919-233">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="9b919-234">Esto es necesario cuando el directorio de salida ya contiene un proyecto.</span><span class="sxs-lookup"><span data-stu-id="9b919-234">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="9b919-235">Imprime la ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="9b919-235">Prints out help for the command.</span></span> <span data-ttu-id="9b919-236">Puede invocarse para el propio comando `dotnet new` o para cualquier plantilla, como `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="9b919-236">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="9b919-237">Muestra las plantillas que contienen el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="9b919-237">Lists templates containing the specified name.</span></span> <span data-ttu-id="9b919-238">Si se invoca para el comando `dotnet new`, muestra las plantillas posibles disponibles para un directorio determinado.</span><span class="sxs-lookup"><span data-stu-id="9b919-238">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="9b919-239">Por ejemplo, si el directorio ya contiene un proyecto, no mostrará todas las plantillas del proyecto.</span><span class="sxs-lookup"><span data-stu-id="9b919-239">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="9b919-240">El lenguaje de la plantilla que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="9b919-240">The language of the template to create.</span></span> <span data-ttu-id="9b919-241">El lenguaje aceptado cambia según la plantilla (vea los valores predeterminados en la sección [argumentos](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="9b919-241">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="9b919-242">No es válido para algunas plantillas.</span><span class="sxs-lookup"><span data-stu-id="9b919-242">Not valid for some templates.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="9b919-243">El nombre de la salida creada.</span><span class="sxs-lookup"><span data-stu-id="9b919-243">The name for the created output.</span></span> <span data-ttu-id="9b919-244">Si no se especifica ningún nombre, se usa el nombre del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="9b919-244">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="9b919-245">La ubicación para colocar la salida generada.</span><span class="sxs-lookup"><span data-stu-id="9b919-245">Location to place the generated output.</span></span> <span data-ttu-id="9b919-246">El valor predeterminado es el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="9b919-246">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="9b919-247">Opciones de plantilla</span><span class="sxs-lookup"><span data-stu-id="9b919-247">Template options</span></span>

<span data-ttu-id="9b919-248">Cada plantilla de proyecto puede tener opciones adicionales disponibles.</span><span class="sxs-lookup"><span data-stu-id="9b919-248">Each project template may have additional options available.</span></span> <span data-ttu-id="9b919-249">Las plantillas principales tienen las siguientes opciones adicionales:</span><span class="sxs-lookup"><span data-stu-id="9b919-249">The core templates have the following additional options:</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="9b919-250">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="9b919-250">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="9b919-251">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="9b919-251">**console, angular, react, reactredux**</span></span>

<span data-ttu-id="9b919-252">`--no-restore`: no se realiza una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="9b919-252">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="9b919-253">**classlib**</span><span class="sxs-lookup"><span data-stu-id="9b919-253">**classlib**</span></span>

<span data-ttu-id="9b919-254">`-f|--framework <FRAMEWORK>`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="9b919-254">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="9b919-255">Valores: `netcoreapp2.0` para crear una biblioteca de clases de .NET Core o `netstandard2.0` para crear una biblioteca de clases de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="9b919-255">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="9b919-256">El valor predeterminado es `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="9b919-256">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="9b919-257">`--no-restore`: no se realiza una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="9b919-257">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="9b919-258">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="9b919-258">**mstest, xunit**</span></span>

<span data-ttu-id="9b919-259">`-p|--enable-pack`: habilita el empaquetado para el proyecto mediante [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="9b919-259">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="9b919-260">`--no-restore`: no se realiza una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="9b919-260">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="9b919-261">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="9b919-261">**globaljson**</span></span>

<span data-ttu-id="9b919-262">`--sdk-version <VERSION_NUMBER>`: especifica la versión del SDK de .NET Core que se usará con el archivo *global.json*.</span><span class="sxs-lookup"><span data-stu-id="9b919-262">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="9b919-263">**web**</span><span class="sxs-lookup"><span data-stu-id="9b919-263">**web**</span></span>

<span data-ttu-id="9b919-264">`--use-launch-settings`: incluye *launchSettings.json* en la salida de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="9b919-264">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="9b919-265">`--no-restore`: no se realiza una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="9b919-265">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="9b919-266">**webapi**</span><span class="sxs-lookup"><span data-stu-id="9b919-266">**webapi**</span></span>

<span data-ttu-id="9b919-267">`-au|--auth <AUTHENTICATION_TYPE>`: el tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="9b919-267">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="9b919-268">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="9b919-268">The possible values are:</span></span>

- <span data-ttu-id="9b919-269">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="9b919-269">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="9b919-270">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="9b919-270">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="9b919-271">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="9b919-271">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="9b919-272">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="9b919-272">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="9b919-273">`--aad-b2c-instance <INSTANCE>`: la instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="9b919-273">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="9b919-274">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="9b919-274">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="9b919-275">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="9b919-275">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="9b919-276">`-ssp|--susi-policy-id <ID>`: el id. de inicio de sesión y de directiva de registro de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="9b919-276">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="9b919-277">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="9b919-277">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="9b919-278">`--aad-instance <INSTANCE>`: la instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="9b919-278">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="9b919-279">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="9b919-279">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="9b919-280">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="9b919-280">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="9b919-281">`--client-id <ID>`: el id. de cliente para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="9b919-281">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="9b919-282">Úsela con las autenticaciones `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="9b919-282">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="9b919-283">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="9b919-283">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="9b919-284">`--domain <DOMAIN>`: el dominio para el inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="9b919-284">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="9b919-285">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="9b919-285">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="9b919-286">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="9b919-286">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="9b919-287">`--tenant-id <ID>`: el id. de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="9b919-287">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="9b919-288">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="9b919-288">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="9b919-289">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="9b919-289">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="9b919-290">`-r|--org-read-access`: concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="9b919-290">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="9b919-291">Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="9b919-291">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="9b919-292">`--use-launch-settings`: incluye *launchSettings.json* en la salida de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="9b919-292">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="9b919-293">`-uld|--use-local-db`: especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="9b919-293">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="9b919-294">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="9b919-294">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="9b919-295">`--no-restore`: no se realiza una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="9b919-295">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="9b919-296">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="9b919-296">**mvc, razor**</span></span>

<span data-ttu-id="9b919-297">`-au|--auth <AUTHENTICATION_TYPE>`: el tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="9b919-297">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="9b919-298">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="9b919-298">The possible values are:</span></span>

- <span data-ttu-id="9b919-299">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="9b919-299">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="9b919-300">`Individual`: autenticación individual.</span><span class="sxs-lookup"><span data-stu-id="9b919-300">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="9b919-301">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="9b919-301">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="9b919-302">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="9b919-302">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="9b919-303">`MultiOrg`: autenticación organizativa para varios inquilinos.</span><span class="sxs-lookup"><span data-stu-id="9b919-303">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="9b919-304">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="9b919-304">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="9b919-305">`--aad-b2c-instance <INSTANCE>`: la instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="9b919-305">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="9b919-306">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="9b919-306">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="9b919-307">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="9b919-307">The default value is `https://login.microsoftonline.com/tfp/` .</span></span>

<span data-ttu-id="9b919-308">`-ssp|--susi-policy-id <ID>`: el id. de inicio de sesión y de directiva de registro de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="9b919-308">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="9b919-309">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="9b919-309">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="9b919-310">`-rp|--reset-password-policy-id <ID>`: el id. de la directiva de restablecimiento de contraseñas para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="9b919-310">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="9b919-311">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="9b919-311">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="9b919-312">`-ep|--edit-profile-policy-id <ID>`: el id. de directiva de edición de perfiles para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="9b919-312">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="9b919-313">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="9b919-313">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="9b919-314">`--aad-instance <INSTANCE>`: la instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="9b919-314">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="9b919-315">Úsela con las autenticaciones `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="9b919-315">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="9b919-316">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="9b919-316">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="9b919-317">`--client-id <ID>`: el id. de cliente para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="9b919-317">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="9b919-318">Úsela con las autenticaciones `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="9b919-318">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="9b919-319">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="9b919-319">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="9b919-320">`--domain <DOMAIN>`: el dominio para el inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="9b919-320">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="9b919-321">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="9b919-321">Use with `SingleOrg` or `IndividualB2C` authentication..</span></span> <span data-ttu-id="9b919-322">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="9b919-322">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="9b919-323">`--tenant-id <ID>`: el id. de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="9b919-323">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="9b919-324">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="9b919-324">Use with `SingleOrg` authentication..</span></span> <span data-ttu-id="9b919-325">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="9b919-325">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="9b919-326">`--callback-path <PATH>`: la ruta de acceso de solicitud de la ruta de acceso de la base de la aplicación del URI de redirección.</span><span class="sxs-lookup"><span data-stu-id="9b919-326">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="9b919-327">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="9b919-327">Use with `SingleOrg` or `IndividualB2C` authentication..</span></span> <span data-ttu-id="9b919-328">El valor predeterminado es `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="9b919-328">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="9b919-329">`-r|--org-read-access`: concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="9b919-329">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="9b919-330">Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="9b919-330">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="9b919-331">`--use-launch-settings`: incluye *launchSettings.json* en la salida de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="9b919-331">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="9b919-332">`--use-browserlink`: incluye BrowserLink en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="9b919-332">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="9b919-333">`-uld|--use-local-db`: especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="9b919-333">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="9b919-334">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="9b919-334">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="9b919-335">`--no-restore`: no se realiza una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="9b919-335">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="9b919-336">**page**</span><span class="sxs-lookup"><span data-stu-id="9b919-336">**page**</span></span>

<span data-ttu-id="9b919-337">`-na|--namespace <NAMESPACE_NAME>`: espacio de nombres para el código generado.</span><span class="sxs-lookup"><span data-stu-id="9b919-337">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="9b919-338">El valor predeterminado es `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="9b919-338">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="9b919-339">`-np|--no-pagemodel`: crea la página sin PageModel.</span><span class="sxs-lookup"><span data-stu-id="9b919-339">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="9b919-340">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="9b919-340">**viewimports**</span></span>

<span data-ttu-id="9b919-341">`-na|--namespace <NAMESPACE_NAME>`: espacio de nombres para el código generado.</span><span class="sxs-lookup"><span data-stu-id="9b919-341">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="9b919-342">El valor predeterminado es `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="9b919-342">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="9b919-343">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="9b919-343">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="9b919-344">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="9b919-344">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="9b919-345">`-f|--framework`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="9b919-345">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="9b919-346">Valores: `netcoreapp1.0` o `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="9b919-346">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="9b919-347">El valor predeterminado es `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="9b919-347">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="9b919-348">**classlib**</span><span class="sxs-lookup"><span data-stu-id="9b919-348">**classlib**</span></span>

<span data-ttu-id="9b919-349">`-f|--framework`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="9b919-349">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="9b919-350">Valores: `netcoreapp1.0`, `netcoreapp1.1` o de `netstandard1.0` a `netstandard1.6`.</span><span class="sxs-lookup"><span data-stu-id="9b919-350">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="9b919-351">El valor predeterminado es `netstandard1.4`.</span><span class="sxs-lookup"><span data-stu-id="9b919-351">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="9b919-352">**mvc**</span><span class="sxs-lookup"><span data-stu-id="9b919-352">**mvc**</span></span>

<span data-ttu-id="9b919-353">`-f|--framework`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="9b919-353">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="9b919-354">Valores: `netcoreapp1.0` o `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="9b919-354">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="9b919-355">El valor predeterminado es `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="9b919-355">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="9b919-356">`-au|--auth`: el tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="9b919-356">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="9b919-357">Valores: `None` o `Individual`.</span><span class="sxs-lookup"><span data-stu-id="9b919-357">Values: `None` or `Individual`.</span></span> <span data-ttu-id="9b919-358">El valor predeterminado es `None`.</span><span class="sxs-lookup"><span data-stu-id="9b919-358">The default value is `None`.</span></span>

<span data-ttu-id="9b919-359">`-uld|--use-local-db`: especifica si se va a usar o no LocalDB en lugar de SQLite.</span><span class="sxs-lookup"><span data-stu-id="9b919-359">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="9b919-360">Valores: `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="9b919-360">Values: `true` or `false`.</span></span> <span data-ttu-id="9b919-361">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="9b919-361">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="9b919-362">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="9b919-362">Examples</span></span>

<span data-ttu-id="9b919-363">Creación de un proyecto de aplicación de consola con F# en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="9b919-363">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang f#`

<span data-ttu-id="9b919-364">Creación de un proyecto de biblioteca de clases de .NET Standard en el directorio especificado (disponible solo con el SDK de .NET Core 2.0 o versiones posteriores):</span><span class="sxs-lookup"><span data-stu-id="9b919-364">Create a .NET Standard class library project in the specified directory (available only with .NET Core 2.0 SDK or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="9b919-365">Creación de un proyecto de aplicación MVC de ASP.NET Core C# en el directorio actual sin autenticación destinado a .NET Core 2.0:</span><span class="sxs-lookup"><span data-stu-id="9b919-365">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication targeting .NET Core 2.0:</span></span>

`dotnet new mvc -au None -f netcoreapp2.0`

<span data-ttu-id="9b919-366">Creación de una aplicación de xUnit que tenga como destino .NET Core 2.0:</span><span class="sxs-lookup"><span data-stu-id="9b919-366">Create a new xUnit application targeting .NET Core 2.0:</span></span>

`dotnet new xunit --framework netcoreapp2.0`

<span data-ttu-id="9b919-367">Enumere todas las plantillas disponibles para MVC:</span><span class="sxs-lookup"><span data-stu-id="9b919-367">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

## <a name="see-also"></a><span data-ttu-id="9b919-368">Vea también</span><span class="sxs-lookup"><span data-stu-id="9b919-368">See also</span></span>

<span data-ttu-id="9b919-369">[Custom templates for dotnet new](custom-templates.md) (Plantillas personalizadas para dotnet new)</span><span class="sxs-lookup"><span data-stu-id="9b919-369">[Custom templates for dotnet new](custom-templates.md)</span></span>  
[<span data-ttu-id="9b919-370">Creación de una plantilla personalizada para dotnet new</span><span class="sxs-lookup"><span data-stu-id="9b919-370">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)  
[<span data-ttu-id="9b919-371">Repositorio de GitHub dotnet/dotnet-template-samples</span><span class="sxs-lookup"><span data-stu-id="9b919-371">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)  
<span data-ttu-id="9b919-372">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new) (Plantillas disponibles para dotnet new)</span><span class="sxs-lookup"><span data-stu-id="9b919-372">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)</span></span>
