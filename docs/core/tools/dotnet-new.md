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
ms.workload: dotnetcore
ms.openlocfilehash: cf65dc80f135badcb1580726a12a9ae9d94ae3d7
ms.sourcegitcommit: 8bde7a3432f30fc771079744955c75c58c4eb393
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/20/2018
---
# <a name="dotnet-new"></a><span data-ttu-id="76f7f-104">dotnet new</span><span class="sxs-lookup"><span data-stu-id="76f7f-104">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="76f7f-105">nombre</span><span class="sxs-lookup"><span data-stu-id="76f7f-105">Name</span></span>

<span data-ttu-id="76f7f-106">`dotnet new`: crea un nuevo proyecto, archivo de configuración o solución según la plantilla especificada.</span><span class="sxs-lookup"><span data-stu-id="76f7f-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="76f7f-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="76f7f-107">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="76f7f-108">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="76f7f-108">.NET Core 2.x</span></span>](#tab/netcore2x)
```
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="76f7f-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="76f7f-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="76f7f-110">Description</span><span class="sxs-lookup"><span data-stu-id="76f7f-110">Description</span></span>

<span data-ttu-id="76f7f-111">El comando `dotnet new` proporciona una manera cómoda de inicializar un proyecto .NET Core válido.</span><span class="sxs-lookup"><span data-stu-id="76f7f-111">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span> 

<span data-ttu-id="76f7f-112">El comando llama al [motor de plantillas](https://github.com/dotnet/templating) para crear los artefactos en el disco basándose en las opciones y la plantilla especificadas.</span><span class="sxs-lookup"><span data-stu-id="76f7f-112">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="76f7f-113">Argumentos</span><span class="sxs-lookup"><span data-stu-id="76f7f-113">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="76f7f-114">La plantilla de la que se va a crear una instancia cuando se invoca el comando.</span><span class="sxs-lookup"><span data-stu-id="76f7f-114">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="76f7f-115">Cada plantilla puede tener opciones específicas que puede pasar.</span><span class="sxs-lookup"><span data-stu-id="76f7f-115">Each template might have specific options you can pass.</span></span> <span data-ttu-id="76f7f-116">Para obtener más información, vea [Opciones de plantilla](#template-options).</span><span class="sxs-lookup"><span data-stu-id="76f7f-116">For more information, see [Template options](#template-options).</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="76f7f-117">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="76f7f-117">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="76f7f-118">El comando contiene una lista predeterminada de plantillas.</span><span class="sxs-lookup"><span data-stu-id="76f7f-118">The command contains a default list of templates.</span></span> <span data-ttu-id="76f7f-119">Use `dotnet new -l` para obtener una lista de las plantillas disponibles.</span><span class="sxs-lookup"><span data-stu-id="76f7f-119">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="76f7f-120">En la siguiente tabla se muestran las plantillas que vienen preinstaladas con el SDK de .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="76f7f-120">The following table shows the templates that come pre-installed with the .NET Core 2.0 SDK.</span></span> <span data-ttu-id="76f7f-121">El lenguaje predeterminado de la plantilla se muestra entre corchetes.</span><span class="sxs-lookup"><span data-stu-id="76f7f-121">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="76f7f-122">Descripción de plantilla</span><span class="sxs-lookup"><span data-stu-id="76f7f-122">Template description</span></span>                          | <span data-ttu-id="76f7f-123">Nombre de plantilla</span><span class="sxs-lookup"><span data-stu-id="76f7f-123">Template name</span></span> | <span data-ttu-id="76f7f-124">Lenguajes</span><span class="sxs-lookup"><span data-stu-id="76f7f-124">Languages</span></span>     |
|----------------------------------------------|---------------|---------------|
| <span data-ttu-id="76f7f-125">Aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="76f7f-125">Console application</span></span>                          | `console`     | <span data-ttu-id="76f7f-126">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="76f7f-126">[C#], F#, VB</span></span>  |
| <span data-ttu-id="76f7f-127">Biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="76f7f-127">Class library</span></span>                                | `classlib`    | <span data-ttu-id="76f7f-128">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="76f7f-128">[C#], F#, VB</span></span>  |
| <span data-ttu-id="76f7f-129">Proyecto de prueba unitaria</span><span class="sxs-lookup"><span data-stu-id="76f7f-129">Unit test project</span></span>                            | `mstest`      | <span data-ttu-id="76f7f-130">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="76f7f-130">[C#], F#, VB</span></span>  |
| <span data-ttu-id="76f7f-131">Proyecto de prueba xUnit</span><span class="sxs-lookup"><span data-stu-id="76f7f-131">xUnit test project</span></span>                           | `xunit`       | <span data-ttu-id="76f7f-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="76f7f-132">[C#], F#, VB</span></span>  |
| <span data-ttu-id="76f7f-133">Vacío de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="76f7f-133">ASP.NET Core empty</span></span>                           | `web`         | <span data-ttu-id="76f7f-134">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="76f7f-134">[C#], F#</span></span>      |
| <span data-ttu-id="76f7f-135">Aplicación web de ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="76f7f-135">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="76f7f-136">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="76f7f-136">[C#], F#</span></span>      |
| <span data-ttu-id="76f7f-137">Aplicación web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="76f7f-137">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="76f7f-138">[C#]</span><span class="sxs-lookup"><span data-stu-id="76f7f-138">[C#]</span></span>          |
| <span data-ttu-id="76f7f-139">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="76f7f-139">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="76f7f-140">[C#]</span><span class="sxs-lookup"><span data-stu-id="76f7f-140">[C#]</span></span>          |
| <span data-ttu-id="76f7f-141">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="76f7f-141">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="76f7f-142">[C#]</span><span class="sxs-lookup"><span data-stu-id="76f7f-142">[C#]</span></span>          |
| <span data-ttu-id="76f7f-143">ASP.NET Core con React.js y Redux</span><span class="sxs-lookup"><span data-stu-id="76f7f-143">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="76f7f-144">[C#]</span><span class="sxs-lookup"><span data-stu-id="76f7f-144">[C#]</span></span>          |
| <span data-ttu-id="76f7f-145">API web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="76f7f-145">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="76f7f-146">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="76f7f-146">[C#], F#</span></span>      |
| <span data-ttu-id="76f7f-147">archivo global.json</span><span class="sxs-lookup"><span data-stu-id="76f7f-147">global.json file</span></span>                             | `globaljson`  |               |
| <span data-ttu-id="76f7f-148">Configuración de NuGet</span><span class="sxs-lookup"><span data-stu-id="76f7f-148">Nuget config</span></span>                                 | `nugetconfig` |               |
| <span data-ttu-id="76f7f-149">Configuración de la Web</span><span class="sxs-lookup"><span data-stu-id="76f7f-149">Web config</span></span>                                   | `webconfig`   |               |
| <span data-ttu-id="76f7f-150">Archivo de solución</span><span class="sxs-lookup"><span data-stu-id="76f7f-150">Solution file</span></span>                                | `sln`         |               |
| <span data-ttu-id="76f7f-151">Página de Razor</span><span class="sxs-lookup"><span data-stu-id="76f7f-151">Razor page</span></span>                                   | `page`        |               |
| <span data-ttu-id="76f7f-152">MVC/ViewImports</span><span class="sxs-lookup"><span data-stu-id="76f7f-152">MVC/ViewImports</span></span>                              | `viewimports` |               |
| <span data-ttu-id="76f7f-153">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="76f7f-153">MVC ViewStart</span></span>                                | `viewstart`   |               |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="76f7f-154">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="76f7f-154">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="76f7f-155">El comando contiene una lista predeterminada de plantillas.</span><span class="sxs-lookup"><span data-stu-id="76f7f-155">The command contains a default list of templates.</span></span> <span data-ttu-id="76f7f-156">Use `dotnet new -all` para obtener una lista de las plantillas disponibles.</span><span class="sxs-lookup"><span data-stu-id="76f7f-156">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="76f7f-157">En la siguiente tabla se muestran las plantillas que vienen preinstaladas con el SDK de .NET Core 1.x.</span><span class="sxs-lookup"><span data-stu-id="76f7f-157">The following table shows the templates that come pre-installed with the .NET Core 1.x SDK.</span></span> <span data-ttu-id="76f7f-158">El lenguaje predeterminado de la plantilla se muestra entre corchetes.</span><span class="sxs-lookup"><span data-stu-id="76f7f-158">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="76f7f-159">Descripción de plantilla</span><span class="sxs-lookup"><span data-stu-id="76f7f-159">Template description</span></span>  | <span data-ttu-id="76f7f-160">Nombre de plantilla</span><span class="sxs-lookup"><span data-stu-id="76f7f-160">Template name</span></span> | <span data-ttu-id="76f7f-161">Lenguajes</span><span class="sxs-lookup"><span data-stu-id="76f7f-161">Languages</span></span> |
|----------------------|---------------|-----------|
| <span data-ttu-id="76f7f-162">Aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="76f7f-162">Console application</span></span>  | `console`     | <span data-ttu-id="76f7f-163">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="76f7f-163">[C#], F#</span></span>  |
| <span data-ttu-id="76f7f-164">Biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="76f7f-164">Class library</span></span>        | `classlib`    | <span data-ttu-id="76f7f-165">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="76f7f-165">[C#], F#</span></span>  |
| <span data-ttu-id="76f7f-166">Proyecto de prueba unitaria</span><span class="sxs-lookup"><span data-stu-id="76f7f-166">Unit test project</span></span>    | `mstest`      | <span data-ttu-id="76f7f-167">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="76f7f-167">[C#], F#</span></span>  |
| <span data-ttu-id="76f7f-168">Proyecto de prueba xUnit</span><span class="sxs-lookup"><span data-stu-id="76f7f-168">xUnit test project</span></span>   | `xunit`       | <span data-ttu-id="76f7f-169">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="76f7f-169">[C#], F#</span></span>  |
| <span data-ttu-id="76f7f-170">Vacío de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="76f7f-170">ASP.NET Core empty</span></span>   | `web`         | <span data-ttu-id="76f7f-171">[C#]</span><span class="sxs-lookup"><span data-stu-id="76f7f-171">[C#]</span></span>      |
| <span data-ttu-id="76f7f-172">Aplicación web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="76f7f-172">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="76f7f-173">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="76f7f-173">[C#], F#</span></span>  |
| <span data-ttu-id="76f7f-174">API web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="76f7f-174">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="76f7f-175">[C#]</span><span class="sxs-lookup"><span data-stu-id="76f7f-175">[C#]</span></span>      |
| <span data-ttu-id="76f7f-176">Configuración de NuGet</span><span class="sxs-lookup"><span data-stu-id="76f7f-176">Nuget config</span></span>         | `nugetconfig` |           |
| <span data-ttu-id="76f7f-177">Configuración de la Web</span><span class="sxs-lookup"><span data-stu-id="76f7f-177">Web config</span></span>           | `webconfig`   |           |
| <span data-ttu-id="76f7f-178">Archivo de solución</span><span class="sxs-lookup"><span data-stu-id="76f7f-178">Solution file</span></span>        | `sln`         |           |

---

## <a name="options"></a><span data-ttu-id="76f7f-179">Opciones</span><span class="sxs-lookup"><span data-stu-id="76f7f-179">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="76f7f-180">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="76f7f-180">.NET Core 2.x</span></span>](#tab/netcore2x)

`--force`

<span data-ttu-id="76f7f-181">Fuerza la generación de contenido incluso aunque se vayan a cambiar los archivos existentes.</span><span class="sxs-lookup"><span data-stu-id="76f7f-181">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="76f7f-182">Esto es necesario cuando el directorio de salida ya contiene un proyecto.</span><span class="sxs-lookup"><span data-stu-id="76f7f-182">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="76f7f-183">Imprime la ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="76f7f-183">Prints out help for the command.</span></span> <span data-ttu-id="76f7f-184">Puede invocarse para el propio comando `dotnet new` o para cualquier plantilla, como `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="76f7f-184">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="76f7f-185">Instala un paquete de plantillas u origen desde los parámetros `PATH` o `NUGET_ID` proporcionados.</span><span class="sxs-lookup"><span data-stu-id="76f7f-185">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="76f7f-186">Para obtener información sobre cómo crear plantillas personalizadas, consulte [Custom templates for dotnet new](custom-templates.md) (Plantillas personalizadas para dotnet new).</span><span class="sxs-lookup"><span data-stu-id="76f7f-186">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="76f7f-187">Muestra las plantillas que contienen el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="76f7f-187">Lists templates containing the specified name.</span></span> <span data-ttu-id="76f7f-188">Si se invoca para el comando `dotnet new`, muestra las plantillas posibles disponibles para un directorio determinado.</span><span class="sxs-lookup"><span data-stu-id="76f7f-188">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="76f7f-189">Por ejemplo, si el directorio ya contiene un proyecto, no mostrará todas las plantillas del proyecto.</span><span class="sxs-lookup"><span data-stu-id="76f7f-189">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="76f7f-190">El lenguaje de la plantilla que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="76f7f-190">The language of the template to create.</span></span> <span data-ttu-id="76f7f-191">El lenguaje aceptado cambia según la plantilla (vea los valores predeterminados en la sección [argumentos](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="76f7f-191">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="76f7f-192">No es válido para algunas plantillas.</span><span class="sxs-lookup"><span data-stu-id="76f7f-192">Not valid for some templates.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="76f7f-193">El nombre de la salida creada.</span><span class="sxs-lookup"><span data-stu-id="76f7f-193">The name for the created output.</span></span> <span data-ttu-id="76f7f-194">Si no se especifica ningún nombre, se usa el nombre del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="76f7f-194">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="76f7f-195">La ubicación para colocar la salida generada.</span><span class="sxs-lookup"><span data-stu-id="76f7f-195">Location to place the generated output.</span></span> <span data-ttu-id="76f7f-196">El valor predeterminado es el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="76f7f-196">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="76f7f-197">Filtra plantillas en función de los tipos disponibles.</span><span class="sxs-lookup"><span data-stu-id="76f7f-197">Filters templates based on available types.</span></span> <span data-ttu-id="76f7f-198">Los valores predefinidos son “project”, “item” y “other”.</span><span class="sxs-lookup"><span data-stu-id="76f7f-198">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="76f7f-199">Desinstala un paquete de plantillas u origen en los parámetros `PATH` o `NUGET_ID` proporcionados.</span><span class="sxs-lookup"><span data-stu-id="76f7f-199">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="76f7f-200">Para desinstalar una plantilla mediante `PATH`, debe usar el nombre completo de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="76f7f-200">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="76f7f-201">Por ejemplo, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* funcionará, pero *./GarciaSoftware.ConsoleTemplate.CSharp* desde la carpeta contenedora no lo hará.</span><span class="sxs-lookup"><span data-stu-id="76f7f-201">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="76f7f-202">Además, no debe incluir una barra diagonal para finalizar el directorio en la ruta de acceso a la plantilla.</span><span class="sxs-lookup"><span data-stu-id="76f7f-202">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="76f7f-203">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="76f7f-203">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="76f7f-204">Muestra todas las plantillas de un tipo de proyecto específico cuando se ejecuta en el contexto del comando `dotnet new` por sí solo.</span><span class="sxs-lookup"><span data-stu-id="76f7f-204">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="76f7f-205">Cuando se ejecuta en el contexto de una plantilla específica, como `dotnet new web -all`, `-all` se interpreta como una marca para forzar la creación.</span><span class="sxs-lookup"><span data-stu-id="76f7f-205">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="76f7f-206">Esto es necesario cuando el directorio de salida ya contiene un proyecto.</span><span class="sxs-lookup"><span data-stu-id="76f7f-206">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="76f7f-207">Imprime la ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="76f7f-207">Prints out help for the command.</span></span> <span data-ttu-id="76f7f-208">Puede invocarse para el propio comando `dotnet new` o para cualquier plantilla, como `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="76f7f-208">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="76f7f-209">Muestra las plantillas que contienen el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="76f7f-209">Lists templates containing the specified name.</span></span> <span data-ttu-id="76f7f-210">Si se invoca para el comando `dotnet new`, muestra las plantillas posibles disponibles para un directorio determinado.</span><span class="sxs-lookup"><span data-stu-id="76f7f-210">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="76f7f-211">Por ejemplo, si el directorio ya contiene un proyecto, no mostrará todas las plantillas del proyecto.</span><span class="sxs-lookup"><span data-stu-id="76f7f-211">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="76f7f-212">El lenguaje de la plantilla que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="76f7f-212">The language of the template to create.</span></span> <span data-ttu-id="76f7f-213">El lenguaje aceptado cambia según la plantilla (vea los valores predeterminados en la sección [argumentos](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="76f7f-213">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="76f7f-214">No es válido para algunas plantillas.</span><span class="sxs-lookup"><span data-stu-id="76f7f-214">Not valid for some templates.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="76f7f-215">El nombre de la salida creada.</span><span class="sxs-lookup"><span data-stu-id="76f7f-215">The name for the created output.</span></span> <span data-ttu-id="76f7f-216">Si no se especifica ningún nombre, se usa el nombre del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="76f7f-216">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="76f7f-217">La ubicación para colocar la salida generada.</span><span class="sxs-lookup"><span data-stu-id="76f7f-217">Location to place the generated output.</span></span> <span data-ttu-id="76f7f-218">El valor predeterminado es el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="76f7f-218">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="76f7f-219">Opciones de plantilla</span><span class="sxs-lookup"><span data-stu-id="76f7f-219">Template options</span></span>

<span data-ttu-id="76f7f-220">Cada plantilla de proyecto puede tener opciones adicionales disponibles.</span><span class="sxs-lookup"><span data-stu-id="76f7f-220">Each project template may have additional options available.</span></span> <span data-ttu-id="76f7f-221">Las plantillas principales tienen las siguientes opciones adicionales:</span><span class="sxs-lookup"><span data-stu-id="76f7f-221">The core templates have the following additional options:</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="76f7f-222">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="76f7f-222">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="76f7f-223">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="76f7f-223">**console, angular, react, reactredux**</span></span>

<span data-ttu-id="76f7f-224">`--no-restore`: no se realiza una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="76f7f-224">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="76f7f-225">**classlib**</span><span class="sxs-lookup"><span data-stu-id="76f7f-225">**classlib**</span></span>

<span data-ttu-id="76f7f-226">`-f|--framework <FRAMEWORK>`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="76f7f-226">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="76f7f-227">Valores: `netcoreapp2.0` para crear una biblioteca de clases de .NET Core o `netstandard2.0` para crear una biblioteca de clases de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="76f7f-227">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="76f7f-228">El valor predeterminado es `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="76f7f-228">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="76f7f-229">`--no-restore`: no se realiza una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="76f7f-229">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="76f7f-230">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="76f7f-230">**mstest, xunit**</span></span>

<span data-ttu-id="76f7f-231">`-p|--enable-pack`: habilita el empaquetado para el proyecto mediante [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="76f7f-231">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="76f7f-232">`--no-restore`: no se realiza una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="76f7f-232">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="76f7f-233">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="76f7f-233">**globaljson**</span></span>

<span data-ttu-id="76f7f-234">`--sdk-version <VERSION_NUMBER>`: especifica la versión del SDK de .NET Core que se usará con el archivo *global.json*.</span><span class="sxs-lookup"><span data-stu-id="76f7f-234">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="76f7f-235">**web**</span><span class="sxs-lookup"><span data-stu-id="76f7f-235">**web**</span></span>

<span data-ttu-id="76f7f-236">`--use-launch-settings`: incluye *launchSettings.json* en la salida de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="76f7f-236">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="76f7f-237">`--no-restore`: no se realiza una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="76f7f-237">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="76f7f-238">**webapi**</span><span class="sxs-lookup"><span data-stu-id="76f7f-238">**webapi**</span></span>

<span data-ttu-id="76f7f-239">`-au|--auth <AUTHENTICATION_TYPE>`: el tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="76f7f-239">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="76f7f-240">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="76f7f-240">The possible values are:</span></span>

- <span data-ttu-id="76f7f-241">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="76f7f-241">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="76f7f-242">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="76f7f-242">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="76f7f-243">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="76f7f-243">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="76f7f-244">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="76f7f-244">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="76f7f-245">`--aad-b2c-instance <INSTANCE>`: la instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="76f7f-245">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="76f7f-246">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="76f7f-246">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="76f7f-247">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="76f7f-247">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="76f7f-248">`-ssp|--susi-policy-id <ID>`: el id. de inicio de sesión y de directiva de registro de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="76f7f-248">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="76f7f-249">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="76f7f-249">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="76f7f-250">`--aad-instance <INSTANCE>`: la instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="76f7f-250">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="76f7f-251">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="76f7f-251">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="76f7f-252">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="76f7f-252">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="76f7f-253">`--client-id <ID>`: el id. de cliente para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="76f7f-253">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="76f7f-254">Úsela con las autenticaciones `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="76f7f-254">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="76f7f-255">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="76f7f-255">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="76f7f-256">`--domain <DOMAIN>`: el dominio para el inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="76f7f-256">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="76f7f-257">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="76f7f-257">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="76f7f-258">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="76f7f-258">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="76f7f-259">`--tenant-id <ID>`: el id. de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="76f7f-259">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="76f7f-260">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="76f7f-260">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="76f7f-261">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="76f7f-261">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="76f7f-262">`-r|--org-read-access`: concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="76f7f-262">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="76f7f-263">Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="76f7f-263">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="76f7f-264">`--use-launch-settings`: incluye *launchSettings.json* en la salida de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="76f7f-264">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="76f7f-265">`-uld|--use-local-db`: especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="76f7f-265">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="76f7f-266">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="76f7f-266">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="76f7f-267">`--no-restore`: no se realiza una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="76f7f-267">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="76f7f-268">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="76f7f-268">**mvc, razor**</span></span>

<span data-ttu-id="76f7f-269">`-au|--auth <AUTHENTICATION_TYPE>`: el tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="76f7f-269">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="76f7f-270">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="76f7f-270">The possible values are:</span></span>

- <span data-ttu-id="76f7f-271">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="76f7f-271">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="76f7f-272">`Individual`: autenticación individual.</span><span class="sxs-lookup"><span data-stu-id="76f7f-272">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="76f7f-273">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="76f7f-273">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="76f7f-274">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="76f7f-274">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="76f7f-275">`MultiOrg`: autenticación organizativa para varios inquilinos.</span><span class="sxs-lookup"><span data-stu-id="76f7f-275">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="76f7f-276">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="76f7f-276">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="76f7f-277">`--aad-b2c-instance <INSTANCE>`: la instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="76f7f-277">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="76f7f-278">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="76f7f-278">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="76f7f-279">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="76f7f-279">The default value is `https://login.microsoftonline.com/tfp/` .</span></span>

<span data-ttu-id="76f7f-280">`-ssp|--susi-policy-id <ID>`: el id. de inicio de sesión y de directiva de registro de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="76f7f-280">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="76f7f-281">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="76f7f-281">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="76f7f-282">`-rp|--reset-password-policy-id <ID>`: el id. de la directiva de restablecimiento de contraseñas para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="76f7f-282">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="76f7f-283">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="76f7f-283">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="76f7f-284">`-ep|--edit-profile-policy-id <ID>`: el id. de directiva de edición de perfiles para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="76f7f-284">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="76f7f-285">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="76f7f-285">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="76f7f-286">`--aad-instance <INSTANCE>`: la instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="76f7f-286">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="76f7f-287">Úsela con las autenticaciones `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="76f7f-287">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="76f7f-288">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="76f7f-288">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="76f7f-289">`--client-id <ID>`: el id. de cliente para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="76f7f-289">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="76f7f-290">Úsela con las autenticaciones `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="76f7f-290">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="76f7f-291">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="76f7f-291">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="76f7f-292">`--domain <DOMAIN>`: el dominio para el inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="76f7f-292">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="76f7f-293">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="76f7f-293">Use with `SingleOrg` or `IndividualB2C` authentication..</span></span> <span data-ttu-id="76f7f-294">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="76f7f-294">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="76f7f-295">`--tenant-id <ID>`: el id. de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="76f7f-295">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="76f7f-296">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="76f7f-296">Use with `SingleOrg` authentication..</span></span> <span data-ttu-id="76f7f-297">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="76f7f-297">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="76f7f-298">`--callback-path <PATH>`: la ruta de acceso de solicitud de la ruta de acceso de la base de la aplicación del URI de redirección.</span><span class="sxs-lookup"><span data-stu-id="76f7f-298">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="76f7f-299">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="76f7f-299">Use with `SingleOrg` or `IndividualB2C` authentication..</span></span> <span data-ttu-id="76f7f-300">El valor predeterminado es `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="76f7f-300">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="76f7f-301">`-r|--org-read-access`: concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="76f7f-301">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="76f7f-302">Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="76f7f-302">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="76f7f-303">`--use-launch-settings`: incluye *launchSettings.json* en la salida de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="76f7f-303">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="76f7f-304">`--use-browserlink`: incluye BrowserLink en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="76f7f-304">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="76f7f-305">`-uld|--use-local-db`: especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="76f7f-305">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="76f7f-306">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="76f7f-306">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="76f7f-307">`--no-restore`: no se realiza una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="76f7f-307">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="76f7f-308">**page**</span><span class="sxs-lookup"><span data-stu-id="76f7f-308">**page**</span></span>

<span data-ttu-id="76f7f-309">`-na|--namespace <NAMESPACE_NAME>`: espacio de nombres para el código generado.</span><span class="sxs-lookup"><span data-stu-id="76f7f-309">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="76f7f-310">El valor predeterminado es `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="76f7f-310">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="76f7f-311">`-np|--no-pagemodel`: crea la página sin PageModel.</span><span class="sxs-lookup"><span data-stu-id="76f7f-311">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="76f7f-312">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="76f7f-312">**viewimports**</span></span>

<span data-ttu-id="76f7f-313">`-na|--namespace <NAMESPACE_NAME>`: espacio de nombres para el código generado.</span><span class="sxs-lookup"><span data-stu-id="76f7f-313">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="76f7f-314">El valor predeterminado es `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="76f7f-314">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="76f7f-315">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="76f7f-315">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="76f7f-316">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="76f7f-316">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="76f7f-317">`-f|--framework`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="76f7f-317">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="76f7f-318">Valores: `netcoreapp1.0` o `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="76f7f-318">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="76f7f-319">El valor predeterminado es `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="76f7f-319">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="76f7f-320">**classlib**</span><span class="sxs-lookup"><span data-stu-id="76f7f-320">**classlib**</span></span>

<span data-ttu-id="76f7f-321">`-f|--framework`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="76f7f-321">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="76f7f-322">Valores: `netcoreapp1.0`, `netcoreapp1.1` o de `netstandard1.0` a `netstandard1.6`.</span><span class="sxs-lookup"><span data-stu-id="76f7f-322">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="76f7f-323">El valor predeterminado es `netstandard1.4`.</span><span class="sxs-lookup"><span data-stu-id="76f7f-323">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="76f7f-324">**mvc**</span><span class="sxs-lookup"><span data-stu-id="76f7f-324">**mvc**</span></span>

<span data-ttu-id="76f7f-325">`-f|--framework`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="76f7f-325">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="76f7f-326">Valores: `netcoreapp1.0` o `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="76f7f-326">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="76f7f-327">El valor predeterminado es `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="76f7f-327">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="76f7f-328">`-au|--auth`: el tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="76f7f-328">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="76f7f-329">Valores: `None` o `Individual`.</span><span class="sxs-lookup"><span data-stu-id="76f7f-329">Values: `None` or `Individual`.</span></span> <span data-ttu-id="76f7f-330">El valor predeterminado es `None`.</span><span class="sxs-lookup"><span data-stu-id="76f7f-330">The default value is `None`.</span></span>

<span data-ttu-id="76f7f-331">`-uld|--use-local-db`: especifica si se va a usar o no LocalDB en lugar de SQLite.</span><span class="sxs-lookup"><span data-stu-id="76f7f-331">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="76f7f-332">Valores: `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="76f7f-332">Values: `true` or `false`.</span></span> <span data-ttu-id="76f7f-333">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="76f7f-333">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="76f7f-334">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="76f7f-334">Examples</span></span>

<span data-ttu-id="76f7f-335">Creación de un proyecto de aplicación de consola con F# en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="76f7f-335">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang f#`

<span data-ttu-id="76f7f-336">Creación de un proyecto de biblioteca de clases de .NET Standard en el directorio especificado (disponible solo con el SDK de .NET Core 2.0 o versiones posteriores):</span><span class="sxs-lookup"><span data-stu-id="76f7f-336">Create a .NET Standard class library project in the specified directory (available only with .NET Core 2.0 SDK or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="76f7f-337">Creación de un proyecto de aplicación MVC de ASP.NET Core C# en el directorio actual sin autenticación destinado a .NET Core 2.0:</span><span class="sxs-lookup"><span data-stu-id="76f7f-337">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication targeting .NET Core 2.0:</span></span>

`dotnet new mvc -au None -f netcoreapp2.0`

<span data-ttu-id="76f7f-338">Creación de una aplicación de xUnit que tenga como destino .NET Core 2.0:</span><span class="sxs-lookup"><span data-stu-id="76f7f-338">Create a new xUnit application targeting .NET Core 2.0:</span></span>

`dotnet new xunit --framework netcoreapp2.0`

<span data-ttu-id="76f7f-339">Enumere todas las plantillas disponibles para MVC:</span><span class="sxs-lookup"><span data-stu-id="76f7f-339">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

## <a name="see-also"></a><span data-ttu-id="76f7f-340">Vea también</span><span class="sxs-lookup"><span data-stu-id="76f7f-340">See also</span></span>

<span data-ttu-id="76f7f-341">[Custom templates for dotnet new](custom-templates.md) (Plantillas personalizadas para dotnet new)</span><span class="sxs-lookup"><span data-stu-id="76f7f-341">[Custom templates for dotnet new](custom-templates.md)</span></span>  
[<span data-ttu-id="76f7f-342">Creación de una plantilla personalizada para dotnet new</span><span class="sxs-lookup"><span data-stu-id="76f7f-342">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)  
[<span data-ttu-id="76f7f-343">Repositorio de GitHub dotnet/dotnet-template-samples</span><span class="sxs-lookup"><span data-stu-id="76f7f-343">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)  
<span data-ttu-id="76f7f-344">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new) (Plantillas disponibles para dotnet new)</span><span class="sxs-lookup"><span data-stu-id="76f7f-344">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)</span></span>
