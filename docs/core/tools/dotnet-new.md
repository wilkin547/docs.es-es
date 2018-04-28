---
title: 'Comando dotnet new: CLI de .NET Core'
description: El comando dotnet new crea proyectos de .NET Core basados en la plantilla especificada.
author: mairaw
ms.author: mairaw
ms.date: 03/26/2018
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: ab8d6f779a428aab7bd2739105dcf08b51d14ab9
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="dotnet-new"></a><span data-ttu-id="0913f-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="0913f-103">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="0913f-104">nombre</span><span class="sxs-lookup"><span data-stu-id="0913f-104">Name</span></span>

<span data-ttu-id="0913f-105">`dotnet new`: crea un nuevo proyecto, archivo de configuración o solución según la plantilla especificada.</span><span class="sxs-lookup"><span data-stu-id="0913f-105">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="0913f-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="0913f-106">Synopsis</span></span>

# <a name="net-core-20tabnetcore2x"></a>[<span data-ttu-id="0913f-107">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="0913f-107">.NET Core 2.0</span></span>](#tab/netcore2x)
```
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="0913f-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="0913f-108">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="0913f-109">Description</span><span class="sxs-lookup"><span data-stu-id="0913f-109">Description</span></span>

<span data-ttu-id="0913f-110">El comando `dotnet new` proporciona una manera cómoda de inicializar un proyecto .NET Core válido.</span><span class="sxs-lookup"><span data-stu-id="0913f-110">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span>

<span data-ttu-id="0913f-111">El comando llama al [motor de plantillas](https://github.com/dotnet/templating) para crear los artefactos en el disco basándose en las opciones y la plantilla especificadas.</span><span class="sxs-lookup"><span data-stu-id="0913f-111">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="0913f-112">Argumentos</span><span class="sxs-lookup"><span data-stu-id="0913f-112">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="0913f-113">La plantilla de la que se va a crear una instancia cuando se invoca el comando.</span><span class="sxs-lookup"><span data-stu-id="0913f-113">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="0913f-114">Cada plantilla puede tener opciones específicas que puede pasar.</span><span class="sxs-lookup"><span data-stu-id="0913f-114">Each template might have specific options you can pass.</span></span> <span data-ttu-id="0913f-115">Para obtener más información, vea [Opciones de plantilla](#template-options).</span><span class="sxs-lookup"><span data-stu-id="0913f-115">For more information, see [Template options](#template-options).</span></span>

# <a name="net-core-20tabnetcore2x"></a>[<span data-ttu-id="0913f-116">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="0913f-116">.NET Core 2.0</span></span>](#tab/netcore2x)

<span data-ttu-id="0913f-117">El comando contiene una lista predeterminada de plantillas.</span><span class="sxs-lookup"><span data-stu-id="0913f-117">The command contains a default list of templates.</span></span> <span data-ttu-id="0913f-118">Use `dotnet new -l` para obtener una lista de las plantillas disponibles.</span><span class="sxs-lookup"><span data-stu-id="0913f-118">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="0913f-119">En la siguiente tabla se muestran las plantillas que vienen preinstaladas con el SDK de .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="0913f-119">The following table shows the templates that come pre-installed with the .NET Core 2.0 SDK.</span></span> <span data-ttu-id="0913f-120">El lenguaje predeterminado de la plantilla se muestra entre corchetes.</span><span class="sxs-lookup"><span data-stu-id="0913f-120">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="0913f-121">Descripción de plantilla</span><span class="sxs-lookup"><span data-stu-id="0913f-121">Template description</span></span>                          | <span data-ttu-id="0913f-122">Nombre de plantilla</span><span class="sxs-lookup"><span data-stu-id="0913f-122">Template name</span></span> | <span data-ttu-id="0913f-123">Lenguajes</span><span class="sxs-lookup"><span data-stu-id="0913f-123">Languages</span></span>     |
|----------------------------------------------|---------------|---------------|
| <span data-ttu-id="0913f-124">Aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="0913f-124">Console application</span></span>                          | `console`     | <span data-ttu-id="0913f-125">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="0913f-125">[C#], F#, VB</span></span>  |
| <span data-ttu-id="0913f-126">Biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="0913f-126">Class library</span></span>                                | `classlib`    | <span data-ttu-id="0913f-127">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="0913f-127">[C#], F#, VB</span></span>  |
| <span data-ttu-id="0913f-128">Proyecto de prueba unitaria</span><span class="sxs-lookup"><span data-stu-id="0913f-128">Unit test project</span></span>                            | `mstest`      | <span data-ttu-id="0913f-129">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="0913f-129">[C#], F#, VB</span></span>  |
| <span data-ttu-id="0913f-130">Proyecto de prueba xUnit</span><span class="sxs-lookup"><span data-stu-id="0913f-130">xUnit test project</span></span>                           | `xunit`       | <span data-ttu-id="0913f-131">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="0913f-131">[C#], F#, VB</span></span>  |
| <span data-ttu-id="0913f-132">Vacío de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="0913f-132">ASP.NET Core empty</span></span>                           | `web`         | <span data-ttu-id="0913f-133">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="0913f-133">[C#], F#</span></span>      |
| <span data-ttu-id="0913f-134">Aplicación web de ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="0913f-134">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="0913f-135">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="0913f-135">[C#], F#</span></span>      |
| <span data-ttu-id="0913f-136">Aplicación web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="0913f-136">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="0913f-137">[C#]</span><span class="sxs-lookup"><span data-stu-id="0913f-137">[C#]</span></span>          |
| <span data-ttu-id="0913f-138">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="0913f-138">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="0913f-139">[C#]</span><span class="sxs-lookup"><span data-stu-id="0913f-139">[C#]</span></span>          |
| <span data-ttu-id="0913f-140">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="0913f-140">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="0913f-141">[C#]</span><span class="sxs-lookup"><span data-stu-id="0913f-141">[C#]</span></span>          |
| <span data-ttu-id="0913f-142">ASP.NET Core con React.js y Redux</span><span class="sxs-lookup"><span data-stu-id="0913f-142">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="0913f-143">[C#]</span><span class="sxs-lookup"><span data-stu-id="0913f-143">[C#]</span></span>          |
| <span data-ttu-id="0913f-144">API web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="0913f-144">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="0913f-145">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="0913f-145">[C#], F#</span></span>      |
| <span data-ttu-id="0913f-146">archivo global.json</span><span class="sxs-lookup"><span data-stu-id="0913f-146">global.json file</span></span>                             | `globaljson`  |               |
| <span data-ttu-id="0913f-147">Configuración de NuGet</span><span class="sxs-lookup"><span data-stu-id="0913f-147">Nuget config</span></span>                                 | `nugetconfig` |               |
| <span data-ttu-id="0913f-148">Configuración de la Web</span><span class="sxs-lookup"><span data-stu-id="0913f-148">Web config</span></span>                                   | `webconfig`   |               |
| <span data-ttu-id="0913f-149">Archivo de solución</span><span class="sxs-lookup"><span data-stu-id="0913f-149">Solution file</span></span>                                | `sln`         |               |
| <span data-ttu-id="0913f-150">Página de Razor</span><span class="sxs-lookup"><span data-stu-id="0913f-150">Razor page</span></span>                                   | `page`        |               |
| <span data-ttu-id="0913f-151">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="0913f-151">MVC ViewImports</span></span>                              | `viewimports` |               |
| <span data-ttu-id="0913f-152">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="0913f-152">MVC ViewStart</span></span>                                | `viewstart`   |               |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="0913f-153">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="0913f-153">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="0913f-154">El comando contiene una lista predeterminada de plantillas.</span><span class="sxs-lookup"><span data-stu-id="0913f-154">The command contains a default list of templates.</span></span> <span data-ttu-id="0913f-155">Use `dotnet new -all` para obtener una lista de las plantillas disponibles.</span><span class="sxs-lookup"><span data-stu-id="0913f-155">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="0913f-156">En la siguiente tabla se muestran las plantillas que vienen preinstaladas con el SDK de .NET Core 1.x.</span><span class="sxs-lookup"><span data-stu-id="0913f-156">The following table shows the templates that come pre-installed with the .NET Core 1.x SDK.</span></span> <span data-ttu-id="0913f-157">El lenguaje predeterminado de la plantilla se muestra entre corchetes.</span><span class="sxs-lookup"><span data-stu-id="0913f-157">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="0913f-158">Descripción de plantilla</span><span class="sxs-lookup"><span data-stu-id="0913f-158">Template description</span></span>  | <span data-ttu-id="0913f-159">Nombre de plantilla</span><span class="sxs-lookup"><span data-stu-id="0913f-159">Template name</span></span> | <span data-ttu-id="0913f-160">Lenguajes</span><span class="sxs-lookup"><span data-stu-id="0913f-160">Languages</span></span> |
|----------------------|---------------|-----------|
| <span data-ttu-id="0913f-161">Aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="0913f-161">Console application</span></span>  | `console`     | <span data-ttu-id="0913f-162">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="0913f-162">[C#], F#</span></span>  |
| <span data-ttu-id="0913f-163">Biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="0913f-163">Class library</span></span>        | `classlib`    | <span data-ttu-id="0913f-164">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="0913f-164">[C#], F#</span></span>  |
| <span data-ttu-id="0913f-165">Proyecto de prueba unitaria</span><span class="sxs-lookup"><span data-stu-id="0913f-165">Unit test project</span></span>    | `mstest`      | <span data-ttu-id="0913f-166">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="0913f-166">[C#], F#</span></span>  |
| <span data-ttu-id="0913f-167">Proyecto de prueba xUnit</span><span class="sxs-lookup"><span data-stu-id="0913f-167">xUnit test project</span></span>   | `xunit`       | <span data-ttu-id="0913f-168">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="0913f-168">[C#], F#</span></span>  |
| <span data-ttu-id="0913f-169">Vacío de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="0913f-169">ASP.NET Core empty</span></span>   | `web`         | <span data-ttu-id="0913f-170">[C#]</span><span class="sxs-lookup"><span data-stu-id="0913f-170">[C#]</span></span>      |
| <span data-ttu-id="0913f-171">Aplicación web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="0913f-171">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="0913f-172">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="0913f-172">[C#], F#</span></span>  |
| <span data-ttu-id="0913f-173">API web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="0913f-173">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="0913f-174">[C#]</span><span class="sxs-lookup"><span data-stu-id="0913f-174">[C#]</span></span>      |
| <span data-ttu-id="0913f-175">Configuración de NuGet</span><span class="sxs-lookup"><span data-stu-id="0913f-175">Nuget config</span></span>         | `nugetconfig` |           |
| <span data-ttu-id="0913f-176">Configuración de la Web</span><span class="sxs-lookup"><span data-stu-id="0913f-176">Web config</span></span>           | `webconfig`   |           |
| <span data-ttu-id="0913f-177">Archivo de solución</span><span class="sxs-lookup"><span data-stu-id="0913f-177">Solution file</span></span>        | `sln`         |           |

---

## <a name="options"></a><span data-ttu-id="0913f-178">Opciones</span><span class="sxs-lookup"><span data-stu-id="0913f-178">Options</span></span>

# <a name="net-core-20tabnetcore2x"></a>[<span data-ttu-id="0913f-179">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="0913f-179">.NET Core 2.0</span></span>](#tab/netcore2x)

`--force`

<span data-ttu-id="0913f-180">Fuerza la generación de contenido incluso aunque se vayan a cambiar los archivos existentes.</span><span class="sxs-lookup"><span data-stu-id="0913f-180">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="0913f-181">Esto es necesario cuando el directorio de salida ya contiene un proyecto.</span><span class="sxs-lookup"><span data-stu-id="0913f-181">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="0913f-182">Imprime la ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="0913f-182">Prints out help for the command.</span></span> <span data-ttu-id="0913f-183">Puede invocarse para el propio comando `dotnet new` o para cualquier plantilla, como `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="0913f-183">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="0913f-184">Instala un paquete de plantillas u origen desde los parámetros `PATH` o `NUGET_ID` proporcionados.</span><span class="sxs-lookup"><span data-stu-id="0913f-184">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="0913f-185">Si quiere instalar una versión preliminar de un paquete de plantilla, tendrá que especificar la versión en el formato de `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="0913f-185">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="0913f-186">De manera predeterminada, `dotnet new` pasa \* para la versión, que representa la última versión estable del paquete.</span><span class="sxs-lookup"><span data-stu-id="0913f-186">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="0913f-187">Vea un ejemplo en la sección [Ejemplos](#examples).</span><span class="sxs-lookup"><span data-stu-id="0913f-187">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="0913f-188">Para obtener información sobre cómo crear plantillas personalizadas, consulte [Custom templates for dotnet new](custom-templates.md) (Plantillas personalizadas para dotnet new).</span><span class="sxs-lookup"><span data-stu-id="0913f-188">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="0913f-189">Muestra las plantillas que contienen el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="0913f-189">Lists templates containing the specified name.</span></span> <span data-ttu-id="0913f-190">Si se invoca para el comando `dotnet new`, muestra las plantillas posibles disponibles para un directorio determinado.</span><span class="sxs-lookup"><span data-stu-id="0913f-190">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="0913f-191">Por ejemplo, si el directorio ya contiene un proyecto, no mostrará todas las plantillas del proyecto.</span><span class="sxs-lookup"><span data-stu-id="0913f-191">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="0913f-192">El lenguaje de la plantilla que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="0913f-192">The language of the template to create.</span></span> <span data-ttu-id="0913f-193">El lenguaje aceptado cambia según la plantilla (vea los valores predeterminados en la sección [argumentos](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="0913f-193">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="0913f-194">No es válido para algunas plantillas.</span><span class="sxs-lookup"><span data-stu-id="0913f-194">Not valid for some templates.</span></span>

    > [!NOTE]
    > Some shells interpret `#` as a special character. In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="0913f-195">El nombre de la salida creada.</span><span class="sxs-lookup"><span data-stu-id="0913f-195">The name for the created output.</span></span> <span data-ttu-id="0913f-196">Si no se especifica ningún nombre, se usa el nombre del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="0913f-196">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="0913f-197">La ubicación para colocar la salida generada.</span><span class="sxs-lookup"><span data-stu-id="0913f-197">Location to place the generated output.</span></span> <span data-ttu-id="0913f-198">El valor predeterminado es el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="0913f-198">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="0913f-199">Filtra plantillas en función de los tipos disponibles.</span><span class="sxs-lookup"><span data-stu-id="0913f-199">Filters templates based on available types.</span></span> <span data-ttu-id="0913f-200">Los valores predefinidos son “project”, “item” y “other”.</span><span class="sxs-lookup"><span data-stu-id="0913f-200">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="0913f-201">Desinstala un paquete de plantillas u origen en los parámetros `PATH` o `NUGET_ID` proporcionados.</span><span class="sxs-lookup"><span data-stu-id="0913f-201">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="0913f-202">Para desinstalar una plantilla mediante `PATH`, debe usar el nombre completo de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="0913f-202">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="0913f-203">Por ejemplo, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* funcionará, pero *./GarciaSoftware.ConsoleTemplate.CSharp* desde la carpeta contenedora no lo hará.</span><span class="sxs-lookup"><span data-stu-id="0913f-203">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="0913f-204">Además, no debe incluir una barra diagonal para finalizar el directorio en la ruta de acceso a la plantilla.</span><span class="sxs-lookup"><span data-stu-id="0913f-204">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="0913f-205">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="0913f-205">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="0913f-206">Muestra todas las plantillas de un tipo de proyecto específico cuando se ejecuta en el contexto del comando `dotnet new` por sí solo.</span><span class="sxs-lookup"><span data-stu-id="0913f-206">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="0913f-207">Cuando se ejecuta en el contexto de una plantilla específica, como `dotnet new web -all`, `-all` se interpreta como una marca para forzar la creación.</span><span class="sxs-lookup"><span data-stu-id="0913f-207">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="0913f-208">Esto es necesario cuando el directorio de salida ya contiene un proyecto.</span><span class="sxs-lookup"><span data-stu-id="0913f-208">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="0913f-209">Imprime la ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="0913f-209">Prints out help for the command.</span></span> <span data-ttu-id="0913f-210">Puede invocarse para el propio comando `dotnet new` o para cualquier plantilla, como `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="0913f-210">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="0913f-211">Muestra las plantillas que contienen el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="0913f-211">Lists templates containing the specified name.</span></span> <span data-ttu-id="0913f-212">Si se invoca para el comando `dotnet new`, muestra las plantillas posibles disponibles para un directorio determinado.</span><span class="sxs-lookup"><span data-stu-id="0913f-212">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="0913f-213">Por ejemplo, si el directorio ya contiene un proyecto, no mostrará todas las plantillas del proyecto.</span><span class="sxs-lookup"><span data-stu-id="0913f-213">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="0913f-214">El lenguaje de la plantilla que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="0913f-214">The language of the template to create.</span></span> <span data-ttu-id="0913f-215">El lenguaje aceptado cambia según la plantilla (vea los valores predeterminados en la sección [argumentos](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="0913f-215">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="0913f-216">No es válido para algunas plantillas.</span><span class="sxs-lookup"><span data-stu-id="0913f-216">Not valid for some templates.</span></span>

    > [!NOTE]
    > Some shells interpret `#` as a special character. In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="0913f-217">El nombre de la salida creada.</span><span class="sxs-lookup"><span data-stu-id="0913f-217">The name for the created output.</span></span> <span data-ttu-id="0913f-218">Si no se especifica ningún nombre, se usa el nombre del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="0913f-218">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="0913f-219">La ubicación para colocar la salida generada.</span><span class="sxs-lookup"><span data-stu-id="0913f-219">Location to place the generated output.</span></span> <span data-ttu-id="0913f-220">El valor predeterminado es el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="0913f-220">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="0913f-221">Opciones de plantilla</span><span class="sxs-lookup"><span data-stu-id="0913f-221">Template options</span></span>

<span data-ttu-id="0913f-222">Cada plantilla de proyecto puede tener opciones adicionales disponibles.</span><span class="sxs-lookup"><span data-stu-id="0913f-222">Each project template may have additional options available.</span></span> <span data-ttu-id="0913f-223">Las plantillas principales tienen las siguientes opciones adicionales:</span><span class="sxs-lookup"><span data-stu-id="0913f-223">The core templates have the following additional options:</span></span>

# <a name="net-core-20tabnetcore2x"></a>[<span data-ttu-id="0913f-224">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="0913f-224">.NET Core 2.0</span></span>](#tab/netcore2x)

<span data-ttu-id="0913f-225">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="0913f-225">**console, angular, react, reactredux**</span></span>

  <span data-ttu-id="0913f-226">`--no-restore`: no se realiza una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="0913f-226">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="0913f-227">**classlib**</span><span class="sxs-lookup"><span data-stu-id="0913f-227">**classlib**</span></span>

<span data-ttu-id="0913f-228">`-f|--framework <FRAMEWORK>`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="0913f-228">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="0913f-229">Valores: `netcoreapp2.0` para crear una biblioteca de clases de .NET Core o `netstandard2.0` para crear una biblioteca de clases de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="0913f-229">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="0913f-230">El valor predeterminado es `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="0913f-230">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="0913f-231">`--no-restore`: no se realiza una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="0913f-231">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="0913f-232">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="0913f-232">**mstest, xunit**</span></span>

<span data-ttu-id="0913f-233">`-p|--enable-pack`: habilita el empaquetado para el proyecto mediante [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="0913f-233">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="0913f-234">`--no-restore`: no se realiza una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="0913f-234">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="0913f-235">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="0913f-235">**globaljson**</span></span>

<span data-ttu-id="0913f-236">`--sdk-version <VERSION_NUMBER>`: especifica la versión del SDK de .NET Core que se usará con el archivo *global.json*.</span><span class="sxs-lookup"><span data-stu-id="0913f-236">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="0913f-237">**web**</span><span class="sxs-lookup"><span data-stu-id="0913f-237">**web**</span></span>

<span data-ttu-id="0913f-238">`--use-launch-settings`: incluye *launchSettings.json* en la salida de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="0913f-238">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="0913f-239">`--no-restore`: no se realiza una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="0913f-239">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="0913f-240">**webapi**</span><span class="sxs-lookup"><span data-stu-id="0913f-240">**webapi**</span></span>

<span data-ttu-id="0913f-241">`-au|--auth <AUTHENTICATION_TYPE>`: el tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="0913f-241">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="0913f-242">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="0913f-242">The possible values are:</span></span>

- <span data-ttu-id="0913f-243">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="0913f-243">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="0913f-244">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="0913f-244">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="0913f-245">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="0913f-245">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="0913f-246">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="0913f-246">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="0913f-247">`--aad-b2c-instance <INSTANCE>`: la instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="0913f-247">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="0913f-248">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="0913f-248">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="0913f-249">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="0913f-249">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="0913f-250">`-ssp|--susi-policy-id <ID>`: el id. de inicio de sesión y de directiva de registro de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="0913f-250">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="0913f-251">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="0913f-251">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="0913f-252">`--aad-instance <INSTANCE>`: la instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="0913f-252">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="0913f-253">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="0913f-253">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="0913f-254">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="0913f-254">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="0913f-255">`--client-id <ID>`: el id. de cliente para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="0913f-255">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="0913f-256">Úsela con las autenticaciones `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="0913f-256">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="0913f-257">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="0913f-257">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="0913f-258">`--domain <DOMAIN>`: el dominio para el inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="0913f-258">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="0913f-259">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="0913f-259">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="0913f-260">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="0913f-260">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="0913f-261">`--tenant-id <ID>`: el id. de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="0913f-261">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="0913f-262">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="0913f-262">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="0913f-263">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="0913f-263">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="0913f-264">`-r|--org-read-access`: concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="0913f-264">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="0913f-265">Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="0913f-265">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="0913f-266">`--use-launch-settings`: incluye *launchSettings.json* en la salida de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="0913f-266">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="0913f-267">`-uld|--use-local-db`: especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="0913f-267">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="0913f-268">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="0913f-268">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="0913f-269">`--no-restore`: no se realiza una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="0913f-269">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="0913f-270">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="0913f-270">**mvc, razor**</span></span>

<span data-ttu-id="0913f-271">`-au|--auth <AUTHENTICATION_TYPE>`: el tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="0913f-271">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="0913f-272">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="0913f-272">The possible values are:</span></span>

- <span data-ttu-id="0913f-273">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="0913f-273">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="0913f-274">`Individual`: autenticación individual.</span><span class="sxs-lookup"><span data-stu-id="0913f-274">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="0913f-275">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="0913f-275">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="0913f-276">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="0913f-276">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="0913f-277">`MultiOrg`: autenticación organizativa para varios inquilinos.</span><span class="sxs-lookup"><span data-stu-id="0913f-277">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="0913f-278">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="0913f-278">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="0913f-279">`--aad-b2c-instance <INSTANCE>`: la instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="0913f-279">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="0913f-280">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="0913f-280">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="0913f-281">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="0913f-281">The default value is `https://login.microsoftonline.com/tfp/` .</span></span>

<span data-ttu-id="0913f-282">`-ssp|--susi-policy-id <ID>`: el id. de inicio de sesión y de directiva de registro de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="0913f-282">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="0913f-283">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="0913f-283">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="0913f-284">`-rp|--reset-password-policy-id <ID>`: el id. de la directiva de restablecimiento de contraseñas para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="0913f-284">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="0913f-285">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="0913f-285">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="0913f-286">`-ep|--edit-profile-policy-id <ID>`: el id. de directiva de edición de perfiles para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="0913f-286">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="0913f-287">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="0913f-287">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="0913f-288">`--aad-instance <INSTANCE>`: la instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="0913f-288">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="0913f-289">Úsela con las autenticaciones `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="0913f-289">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="0913f-290">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="0913f-290">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="0913f-291">`--client-id <ID>`: el id. de cliente para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="0913f-291">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="0913f-292">Úsela con las autenticaciones `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="0913f-292">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="0913f-293">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="0913f-293">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="0913f-294">`--domain <DOMAIN>`: el dominio para el inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="0913f-294">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="0913f-295">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="0913f-295">Use with `SingleOrg` or `IndividualB2C` authentication..</span></span> <span data-ttu-id="0913f-296">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="0913f-296">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="0913f-297">`--tenant-id <ID>`: el id. de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="0913f-297">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="0913f-298">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="0913f-298">Use with `SingleOrg` authentication..</span></span> <span data-ttu-id="0913f-299">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="0913f-299">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="0913f-300">`--callback-path <PATH>`: la ruta de acceso de solicitud de la ruta de acceso de la base de la aplicación del URI de redirección.</span><span class="sxs-lookup"><span data-stu-id="0913f-300">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="0913f-301">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="0913f-301">Use with `SingleOrg` or `IndividualB2C` authentication..</span></span> <span data-ttu-id="0913f-302">El valor predeterminado es `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="0913f-302">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="0913f-303">`-r|--org-read-access`: concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="0913f-303">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="0913f-304">Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="0913f-304">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="0913f-305">`--use-launch-settings`: incluye *launchSettings.json* en la salida de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="0913f-305">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="0913f-306">`--use-browserlink`: incluye BrowserLink en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="0913f-306">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="0913f-307">`-uld|--use-local-db`: especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="0913f-307">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="0913f-308">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="0913f-308">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="0913f-309">`--no-restore`: no se realiza una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="0913f-309">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="0913f-310">**page**</span><span class="sxs-lookup"><span data-stu-id="0913f-310">**page**</span></span>

<span data-ttu-id="0913f-311">`-na|--namespace <NAMESPACE_NAME>`: espacio de nombres para el código generado.</span><span class="sxs-lookup"><span data-stu-id="0913f-311">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="0913f-312">El valor predeterminado es `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="0913f-312">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="0913f-313">`-np|--no-pagemodel`: crea la página sin PageModel.</span><span class="sxs-lookup"><span data-stu-id="0913f-313">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="0913f-314">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="0913f-314">**viewimports**</span></span>

<span data-ttu-id="0913f-315">`-na|--namespace <NAMESPACE_NAME>`: espacio de nombres para el código generado.</span><span class="sxs-lookup"><span data-stu-id="0913f-315">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="0913f-316">El valor predeterminado es `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="0913f-316">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="0913f-317">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="0913f-317">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="0913f-318">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="0913f-318">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="0913f-319">`-f|--framework`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="0913f-319">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="0913f-320">Valores: `netcoreapp1.0` o `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="0913f-320">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="0913f-321">El valor predeterminado es `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="0913f-321">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="0913f-322">**classlib**</span><span class="sxs-lookup"><span data-stu-id="0913f-322">**classlib**</span></span>

<span data-ttu-id="0913f-323">`-f|--framework`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="0913f-323">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="0913f-324">Valores: `netcoreapp1.0`, `netcoreapp1.1` o de `netstandard1.0` a `netstandard1.6`.</span><span class="sxs-lookup"><span data-stu-id="0913f-324">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="0913f-325">El valor predeterminado es `netstandard1.4`.</span><span class="sxs-lookup"><span data-stu-id="0913f-325">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="0913f-326">**mvc**</span><span class="sxs-lookup"><span data-stu-id="0913f-326">**mvc**</span></span>

<span data-ttu-id="0913f-327">`-f|--framework`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="0913f-327">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="0913f-328">Valores: `netcoreapp1.0` o `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="0913f-328">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="0913f-329">El valor predeterminado es `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="0913f-329">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="0913f-330">`-au|--auth`: el tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="0913f-330">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="0913f-331">Valores: `None` o `Individual`.</span><span class="sxs-lookup"><span data-stu-id="0913f-331">Values: `None` or `Individual`.</span></span> <span data-ttu-id="0913f-332">El valor predeterminado es `None`.</span><span class="sxs-lookup"><span data-stu-id="0913f-332">The default value is `None`.</span></span>

<span data-ttu-id="0913f-333">`-uld|--use-local-db`: especifica si se va a usar o no LocalDB en lugar de SQLite.</span><span class="sxs-lookup"><span data-stu-id="0913f-333">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="0913f-334">Valores: `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="0913f-334">Values: `true` or `false`.</span></span> <span data-ttu-id="0913f-335">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="0913f-335">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="0913f-336">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="0913f-336">Examples</span></span>

<span data-ttu-id="0913f-337">Creación de un proyecto de aplicación de consola con F# en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="0913f-337">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang F#`

<span data-ttu-id="0913f-338">Creación de un proyecto de biblioteca de clases de .NET Standard en el directorio especificado (disponible solo con el SDK de .NET Core 2.0 o versiones posteriores):</span><span class="sxs-lookup"><span data-stu-id="0913f-338">Create a .NET Standard class library project in the specified directory (available only with .NET Core 2.0 SDK or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="0913f-339">Creación de un proyecto de aplicación MVC de ASP.NET Core C# en el directorio actual sin autenticación destinado a .NET Core 2.0:</span><span class="sxs-lookup"><span data-stu-id="0913f-339">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication targeting .NET Core 2.0:</span></span>

`dotnet new mvc -au None -f netcoreapp2.0`

<span data-ttu-id="0913f-340">Creación de una aplicación de xUnit que tenga como destino .NET Core 2.0:</span><span class="sxs-lookup"><span data-stu-id="0913f-340">Create a new xUnit application targeting .NET Core 2.0:</span></span>

`dotnet new xunit --framework netcoreapp2.0`

<span data-ttu-id="0913f-341">Enumere todas las plantillas disponibles para MVC:</span><span class="sxs-lookup"><span data-stu-id="0913f-341">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

<span data-ttu-id="0913f-342">Instalación de la versión 2.0 de las plantillas Aplicación de página única para ASP.NET Core (opción de comando solo disponible para .NET Core SDK 1.1 y versiones posteriores):</span><span class="sxs-lookup"><span data-stu-id="0913f-342">Install version 2.0 of the Single Page Application templates for ASP.NET Core (command option available for .NET Core SDK 1.1 and later versions only):</span></span>

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

## <a name="see-also"></a><span data-ttu-id="0913f-343">Vea también</span><span class="sxs-lookup"><span data-stu-id="0913f-343">See also</span></span>

<span data-ttu-id="0913f-344">[Custom templates for dotnet new](custom-templates.md) (Plantillas personalizadas para dotnet new)</span><span class="sxs-lookup"><span data-stu-id="0913f-344">[Custom templates for dotnet new](custom-templates.md)</span></span>  
[<span data-ttu-id="0913f-345">Creación de una plantilla personalizada para dotnet new</span><span class="sxs-lookup"><span data-stu-id="0913f-345">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)  
[<span data-ttu-id="0913f-346">Repositorio de GitHub dotnet/dotnet-template-samples</span><span class="sxs-lookup"><span data-stu-id="0913f-346">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)  
<span data-ttu-id="0913f-347">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new) (Plantillas disponibles para dotnet new)</span><span class="sxs-lookup"><span data-stu-id="0913f-347">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)</span></span>
