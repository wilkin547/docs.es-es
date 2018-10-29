---
title: 'Comando dotnet new: CLI de .NET Core'
description: El comando dotnet new crea proyectos de .NET Core basados en la plantilla especificada.
author: mairaw
ms.author: mairaw
ms.date: 10/24/2018
ms.openlocfilehash: 56d76f1dd54097f9cf20129d74057235290c273c
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50188212"
---
# <a name="dotnet-new"></a><span data-ttu-id="4857a-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="4857a-103">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="4857a-104">nombre</span><span class="sxs-lookup"><span data-stu-id="4857a-104">Name</span></span>

<span data-ttu-id="4857a-105">`dotnet new`: crea un nuevo proyecto, archivo de configuración o solución según la plantilla especificada.</span><span class="sxs-lookup"><span data-stu-id="4857a-105">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="4857a-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="4857a-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="4857a-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="4857a-107">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output]
    [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="4857a-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="4857a-108">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="4857a-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="4857a-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="4857a-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="4857a-110">Description</span></span>

<span data-ttu-id="4857a-111">El comando `dotnet new` proporciona una manera cómoda de inicializar un proyecto .NET Core válido.</span><span class="sxs-lookup"><span data-stu-id="4857a-111">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span>

<span data-ttu-id="4857a-112">El comando llama al [motor de plantillas](https://github.com/dotnet/templating) para crear los artefactos en el disco basándose en las opciones y la plantilla especificadas.</span><span class="sxs-lookup"><span data-stu-id="4857a-112">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="4857a-113">Argumentos</span><span class="sxs-lookup"><span data-stu-id="4857a-113">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="4857a-114">La plantilla de la que se va a crear una instancia cuando se invoca el comando.</span><span class="sxs-lookup"><span data-stu-id="4857a-114">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="4857a-115">Cada plantilla puede tener opciones específicas que puede pasar.</span><span class="sxs-lookup"><span data-stu-id="4857a-115">Each template might have specific options you can pass.</span></span> <span data-ttu-id="4857a-116">Para obtener más información, vea [Opciones de plantilla](#template-options).</span><span class="sxs-lookup"><span data-stu-id="4857a-116">For more information, see [Template options](#template-options).</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="4857a-117">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="4857a-117">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="4857a-118">El comando contiene una lista predeterminada de plantillas.</span><span class="sxs-lookup"><span data-stu-id="4857a-118">The command contains a default list of templates.</span></span> <span data-ttu-id="4857a-119">Use `dotnet new -l` para obtener una lista de las plantillas disponibles.</span><span class="sxs-lookup"><span data-stu-id="4857a-119">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="4857a-120">En la tabla siguiente se muestran las plantillas que vienen preinstaladas con el SDK de .NET Core 2.1.300.</span><span class="sxs-lookup"><span data-stu-id="4857a-120">The following table shows the templates that come pre-installed with the .NET Core SDK 2.1.300.</span></span> <span data-ttu-id="4857a-121">El lenguaje predeterminado de la plantilla se muestra entre corchetes.</span><span class="sxs-lookup"><span data-stu-id="4857a-121">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="4857a-122">Descripción de plantilla</span><span class="sxs-lookup"><span data-stu-id="4857a-122">Template description</span></span>                          | <span data-ttu-id="4857a-123">Nombre de plantilla</span><span class="sxs-lookup"><span data-stu-id="4857a-123">Template name</span></span>    | <span data-ttu-id="4857a-124">Lenguajes</span><span class="sxs-lookup"><span data-stu-id="4857a-124">Languages</span></span>     |
|----------------------------------------------|------------------|---------------|
| <span data-ttu-id="4857a-125">Aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="4857a-125">Console application</span></span>                          | `console`        | <span data-ttu-id="4857a-126">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="4857a-126">[C#], F#, VB</span></span>  |
| <span data-ttu-id="4857a-127">Biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="4857a-127">Class library</span></span>                                | `classlib`       | <span data-ttu-id="4857a-128">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="4857a-128">[C#], F#, VB</span></span>  |
| <span data-ttu-id="4857a-129">Proyecto de prueba unitaria</span><span class="sxs-lookup"><span data-stu-id="4857a-129">Unit test project</span></span>                            | `mstest`         | <span data-ttu-id="4857a-130">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="4857a-130">[C#], F#, VB</span></span>  |
| <span data-ttu-id="4857a-131">Proyecto de prueba xUnit</span><span class="sxs-lookup"><span data-stu-id="4857a-131">xUnit test project</span></span>                           | `xunit`          | <span data-ttu-id="4857a-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="4857a-132">[C#], F#, VB</span></span>  |
| <span data-ttu-id="4857a-133">Página de Razor</span><span class="sxs-lookup"><span data-stu-id="4857a-133">Razor page</span></span>                                   | `page`           | <span data-ttu-id="4857a-134">[C#]</span><span class="sxs-lookup"><span data-stu-id="4857a-134">[C#]</span></span>          |
| <span data-ttu-id="4857a-135">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="4857a-135">MVC ViewImports</span></span>                              | `viewimports`    | <span data-ttu-id="4857a-136">[C#]</span><span class="sxs-lookup"><span data-stu-id="4857a-136">[C#]</span></span>          |
| <span data-ttu-id="4857a-137">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="4857a-137">MVC ViewStart</span></span>                                | `viewstart`      | <span data-ttu-id="4857a-138">[C#]</span><span class="sxs-lookup"><span data-stu-id="4857a-138">[C#]</span></span>          |
| <span data-ttu-id="4857a-139">Vacío de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="4857a-139">ASP.NET Core empty</span></span>                           | `web`            | <span data-ttu-id="4857a-140">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="4857a-140">[C#], F#</span></span>      |
| <span data-ttu-id="4857a-141">Aplicación web de ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="4857a-141">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`            | <span data-ttu-id="4857a-142">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="4857a-142">[C#], F#</span></span>      |
| <span data-ttu-id="4857a-143">Aplicación web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="4857a-143">ASP.NET Core Web App</span></span>                         | <span data-ttu-id="4857a-144">`razor`, `webapp`</span><span class="sxs-lookup"><span data-stu-id="4857a-144">`razor`, `webapp`</span></span>| <span data-ttu-id="4857a-145">[C#]</span><span class="sxs-lookup"><span data-stu-id="4857a-145">[C#]</span></span>          |
| <span data-ttu-id="4857a-146">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="4857a-146">ASP.NET Core with Angular</span></span>                    | `angular`        | <span data-ttu-id="4857a-147">[C#]</span><span class="sxs-lookup"><span data-stu-id="4857a-147">[C#]</span></span>          |
| <span data-ttu-id="4857a-148">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="4857a-148">ASP.NET Core with React.js</span></span>                   | `react`          | <span data-ttu-id="4857a-149">[C#]</span><span class="sxs-lookup"><span data-stu-id="4857a-149">[C#]</span></span>          |
| <span data-ttu-id="4857a-150">ASP.NET Core con React.js y Redux</span><span class="sxs-lookup"><span data-stu-id="4857a-150">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`     | <span data-ttu-id="4857a-151">[C#]</span><span class="sxs-lookup"><span data-stu-id="4857a-151">[C#]</span></span>          |
| <span data-ttu-id="4857a-152">API web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="4857a-152">ASP.NET Core Web API</span></span>                         | `webapi`         | <span data-ttu-id="4857a-153">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="4857a-153">[C#], F#</span></span>      |
| <span data-ttu-id="4857a-154">Biblioteca de clases de Razor</span><span class="sxs-lookup"><span data-stu-id="4857a-154">Razor class library</span></span>                          | `razorclasslib`  | <span data-ttu-id="4857a-155">[C#]</span><span class="sxs-lookup"><span data-stu-id="4857a-155">[C#]</span></span>          |
| <span data-ttu-id="4857a-156">archivo global.json</span><span class="sxs-lookup"><span data-stu-id="4857a-156">global.json file</span></span>                             | `globaljson`     |               |
| <span data-ttu-id="4857a-157">Configuración de NuGet</span><span class="sxs-lookup"><span data-stu-id="4857a-157">NuGet config</span></span>                                 | `nugetconfig`    |               |
| <span data-ttu-id="4857a-158">Configuración de la Web</span><span class="sxs-lookup"><span data-stu-id="4857a-158">Web config</span></span>                                   | `webconfig`      |               |
| <span data-ttu-id="4857a-159">Archivo de solución</span><span class="sxs-lookup"><span data-stu-id="4857a-159">Solution file</span></span>                                | `sln`            |               |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="4857a-160">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="4857a-160">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="4857a-161">El comando contiene una lista predeterminada de plantillas.</span><span class="sxs-lookup"><span data-stu-id="4857a-161">The command contains a default list of templates.</span></span> <span data-ttu-id="4857a-162">Use `dotnet new -l` para obtener una lista de las plantillas disponibles.</span><span class="sxs-lookup"><span data-stu-id="4857a-162">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="4857a-163">En la tabla siguiente se muestran las plantillas que vienen preinstaladas con el SDK de .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="4857a-163">The following table shows the templates that come pre-installed with the .NET Core SDK 2.0.</span></span> <span data-ttu-id="4857a-164">El lenguaje predeterminado de la plantilla se muestra entre corchetes.</span><span class="sxs-lookup"><span data-stu-id="4857a-164">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="4857a-165">Descripción de plantilla</span><span class="sxs-lookup"><span data-stu-id="4857a-165">Template description</span></span>                          | <span data-ttu-id="4857a-166">Nombre de plantilla</span><span class="sxs-lookup"><span data-stu-id="4857a-166">Template name</span></span> | <span data-ttu-id="4857a-167">Lenguajes</span><span class="sxs-lookup"><span data-stu-id="4857a-167">Languages</span></span>     |
|----------------------------------------------|---------------|---------------|
| <span data-ttu-id="4857a-168">Aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="4857a-168">Console application</span></span>                          | `console`     | <span data-ttu-id="4857a-169">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="4857a-169">[C#], F#, VB</span></span>  |
| <span data-ttu-id="4857a-170">Biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="4857a-170">Class library</span></span>                                | `classlib`    | <span data-ttu-id="4857a-171">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="4857a-171">[C#], F#, VB</span></span>  |
| <span data-ttu-id="4857a-172">Proyecto de prueba unitaria</span><span class="sxs-lookup"><span data-stu-id="4857a-172">Unit test project</span></span>                            | `mstest`      | <span data-ttu-id="4857a-173">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="4857a-173">[C#], F#, VB</span></span>  |
| <span data-ttu-id="4857a-174">Proyecto de prueba xUnit</span><span class="sxs-lookup"><span data-stu-id="4857a-174">xUnit test project</span></span>                           | `xunit`       | <span data-ttu-id="4857a-175">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="4857a-175">[C#], F#, VB</span></span>  |
| <span data-ttu-id="4857a-176">Vacío de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="4857a-176">ASP.NET Core empty</span></span>                           | `web`         | <span data-ttu-id="4857a-177">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="4857a-177">[C#], F#</span></span>      |
| <span data-ttu-id="4857a-178">Aplicación web de ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="4857a-178">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="4857a-179">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="4857a-179">[C#], F#</span></span>      |
| <span data-ttu-id="4857a-180">Aplicación web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="4857a-180">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="4857a-181">[C#]</span><span class="sxs-lookup"><span data-stu-id="4857a-181">[C#]</span></span>          |
| <span data-ttu-id="4857a-182">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="4857a-182">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="4857a-183">[C#]</span><span class="sxs-lookup"><span data-stu-id="4857a-183">[C#]</span></span>          |
| <span data-ttu-id="4857a-184">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="4857a-184">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="4857a-185">[C#]</span><span class="sxs-lookup"><span data-stu-id="4857a-185">[C#]</span></span>          |
| <span data-ttu-id="4857a-186">ASP.NET Core con React.js y Redux</span><span class="sxs-lookup"><span data-stu-id="4857a-186">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="4857a-187">[C#]</span><span class="sxs-lookup"><span data-stu-id="4857a-187">[C#]</span></span>          |
| <span data-ttu-id="4857a-188">API web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="4857a-188">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="4857a-189">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="4857a-189">[C#], F#</span></span>      |
| <span data-ttu-id="4857a-190">archivo global.json</span><span class="sxs-lookup"><span data-stu-id="4857a-190">global.json file</span></span>                             | `globaljson`  |               |
| <span data-ttu-id="4857a-191">Configuración de NuGet</span><span class="sxs-lookup"><span data-stu-id="4857a-191">NuGet config</span></span>                                 | `nugetconfig` |               |
| <span data-ttu-id="4857a-192">Configuración de la Web</span><span class="sxs-lookup"><span data-stu-id="4857a-192">Web config</span></span>                                   | `webconfig`   |               |
| <span data-ttu-id="4857a-193">Archivo de solución</span><span class="sxs-lookup"><span data-stu-id="4857a-193">Solution file</span></span>                                | `sln`         |               |
| <span data-ttu-id="4857a-194">Página de Razor</span><span class="sxs-lookup"><span data-stu-id="4857a-194">Razor page</span></span>                                   | `page`        |               |
| <span data-ttu-id="4857a-195">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="4857a-195">MVC ViewImports</span></span>                              | `viewimports` |               |
| <span data-ttu-id="4857a-196">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="4857a-196">MVC ViewStart</span></span>                                | `viewstart`   |               |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="4857a-197">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="4857a-197">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="4857a-198">El comando contiene una lista predeterminada de plantillas.</span><span class="sxs-lookup"><span data-stu-id="4857a-198">The command contains a default list of templates.</span></span> <span data-ttu-id="4857a-199">Use `dotnet new -all` para obtener una lista de las plantillas disponibles.</span><span class="sxs-lookup"><span data-stu-id="4857a-199">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="4857a-200">En la tabla siguiente se muestran las plantillas que vienen preinstaladas con el SDK de .NET 1.x.</span><span class="sxs-lookup"><span data-stu-id="4857a-200">The following table shows the templates that come pre-installed with the .NET Core SDK 1.x.</span></span> <span data-ttu-id="4857a-201">El lenguaje predeterminado de la plantilla se muestra entre corchetes.</span><span class="sxs-lookup"><span data-stu-id="4857a-201">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="4857a-202">Descripción de plantilla</span><span class="sxs-lookup"><span data-stu-id="4857a-202">Template description</span></span>  | <span data-ttu-id="4857a-203">Nombre de plantilla</span><span class="sxs-lookup"><span data-stu-id="4857a-203">Template name</span></span> | <span data-ttu-id="4857a-204">Lenguajes</span><span class="sxs-lookup"><span data-stu-id="4857a-204">Languages</span></span> |
|----------------------|---------------|-----------|
| <span data-ttu-id="4857a-205">Aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="4857a-205">Console application</span></span>  | `console`     | <span data-ttu-id="4857a-206">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="4857a-206">[C#], F#</span></span>  |
| <span data-ttu-id="4857a-207">Biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="4857a-207">Class library</span></span>        | `classlib`    | <span data-ttu-id="4857a-208">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="4857a-208">[C#], F#</span></span>  |
| <span data-ttu-id="4857a-209">Proyecto de prueba unitaria</span><span class="sxs-lookup"><span data-stu-id="4857a-209">Unit test project</span></span>    | `mstest`      | <span data-ttu-id="4857a-210">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="4857a-210">[C#], F#</span></span>  |
| <span data-ttu-id="4857a-211">Proyecto de prueba xUnit</span><span class="sxs-lookup"><span data-stu-id="4857a-211">xUnit test project</span></span>   | `xunit`       | <span data-ttu-id="4857a-212">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="4857a-212">[C#], F#</span></span>  |
| <span data-ttu-id="4857a-213">Vacío de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="4857a-213">ASP.NET Core empty</span></span>   | `web`         | <span data-ttu-id="4857a-214">[C#]</span><span class="sxs-lookup"><span data-stu-id="4857a-214">[C#]</span></span>      |
| <span data-ttu-id="4857a-215">Aplicación web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="4857a-215">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="4857a-216">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="4857a-216">[C#], F#</span></span>  |
| <span data-ttu-id="4857a-217">API web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="4857a-217">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="4857a-218">[C#]</span><span class="sxs-lookup"><span data-stu-id="4857a-218">[C#]</span></span>      |
| <span data-ttu-id="4857a-219">Configuración de NuGet</span><span class="sxs-lookup"><span data-stu-id="4857a-219">NuGet config</span></span>         | `nugetconfig` |           |
| <span data-ttu-id="4857a-220">Configuración de la Web</span><span class="sxs-lookup"><span data-stu-id="4857a-220">Web config</span></span>           | `webconfig`   |           |
| <span data-ttu-id="4857a-221">Archivo de solución</span><span class="sxs-lookup"><span data-stu-id="4857a-221">Solution file</span></span>        | `sln`         |           |

---

## <a name="options"></a><span data-ttu-id="4857a-222">Opciones</span><span class="sxs-lookup"><span data-stu-id="4857a-222">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="4857a-223">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="4857a-223">.NET Core 2.1</span></span>](#tab/netcore21)

`--force`

<span data-ttu-id="4857a-224">Fuerza la generación de contenido incluso aunque se vayan a cambiar los archivos existentes.</span><span class="sxs-lookup"><span data-stu-id="4857a-224">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="4857a-225">Esto es necesario cuando el directorio de salida ya contiene un proyecto.</span><span class="sxs-lookup"><span data-stu-id="4857a-225">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="4857a-226">Imprime la ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="4857a-226">Prints out help for the command.</span></span> <span data-ttu-id="4857a-227">Puede invocarse para el propio comando `dotnet new` o para cualquier plantilla, como `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="4857a-227">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="4857a-228">Instala un paquete de plantillas u origen desde los parámetros `PATH` o `NUGET_ID` proporcionados.</span><span class="sxs-lookup"><span data-stu-id="4857a-228">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="4857a-229">Si quiere instalar una versión preliminar de un paquete de plantilla, tendrá que especificar la versión en el formato de `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="4857a-229">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="4857a-230">De manera predeterminada, `dotnet new` pasa \* para la versión, que representa la última versión estable del paquete.</span><span class="sxs-lookup"><span data-stu-id="4857a-230">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="4857a-231">Vea un ejemplo en la sección [Ejemplos](#examples).</span><span class="sxs-lookup"><span data-stu-id="4857a-231">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="4857a-232">Para obtener información sobre cómo crear plantillas personalizadas, consulte [Custom templates for dotnet new](custom-templates.md) (Plantillas personalizadas para dotnet new).</span><span class="sxs-lookup"><span data-stu-id="4857a-232">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="4857a-233">Muestra las plantillas que contienen el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="4857a-233">Lists templates containing the specified name.</span></span> <span data-ttu-id="4857a-234">Si se invoca para el comando `dotnet new`, muestra las plantillas posibles disponibles para un directorio determinado.</span><span class="sxs-lookup"><span data-stu-id="4857a-234">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="4857a-235">Por ejemplo, si el directorio ya contiene un proyecto, no mostrará todas las plantillas del proyecto.</span><span class="sxs-lookup"><span data-stu-id="4857a-235">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="4857a-236">El lenguaje de la plantilla que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="4857a-236">The language of the template to create.</span></span> <span data-ttu-id="4857a-237">El lenguaje aceptado cambia según la plantilla (vea los valores predeterminados en la sección [argumentos](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="4857a-237">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="4857a-238">No es válido para algunas plantillas.</span><span class="sxs-lookup"><span data-stu-id="4857a-238">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="4857a-239">Algunos shells interpretan `#` como un carácter especial.</span><span class="sxs-lookup"><span data-stu-id="4857a-239">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="4857a-240">En esos casos, debe incluir el valor del parámetro de lenguaje, como `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="4857a-240">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="4857a-241">El nombre de la salida creada.</span><span class="sxs-lookup"><span data-stu-id="4857a-241">The name for the created output.</span></span> <span data-ttu-id="4857a-242">Si no se especifica ningún nombre, se usa el nombre del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="4857a-242">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="4857a-243">Especifica un origen de NuGet para usarlo durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="4857a-243">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="4857a-244">La ubicación para colocar la salida generada.</span><span class="sxs-lookup"><span data-stu-id="4857a-244">Location to place the generated output.</span></span> <span data-ttu-id="4857a-245">El valor predeterminado es el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="4857a-245">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="4857a-246">Filtra plantillas en función de los tipos disponibles.</span><span class="sxs-lookup"><span data-stu-id="4857a-246">Filters templates based on available types.</span></span> <span data-ttu-id="4857a-247">Los valores predefinidos son “project”, “item” y “other”.</span><span class="sxs-lookup"><span data-stu-id="4857a-247">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="4857a-248">Desinstala un paquete de plantillas u origen en los parámetros `PATH` o `NUGET_ID` proporcionados.</span><span class="sxs-lookup"><span data-stu-id="4857a-248">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="4857a-249">Para desinstalar una plantilla mediante `PATH`, debe usar el nombre completo de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="4857a-249">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="4857a-250">Por ejemplo, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* funcionará, pero *./GarciaSoftware.ConsoleTemplate.CSharp* desde la carpeta contenedora no lo hará.</span><span class="sxs-lookup"><span data-stu-id="4857a-250">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="4857a-251">Además, no debe incluir una barra diagonal para finalizar el directorio en la ruta de acceso a la plantilla.</span><span class="sxs-lookup"><span data-stu-id="4857a-251">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="4857a-252">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="4857a-252">.NET Core 2.0</span></span>](#tab/netcore20)

`--force`

<span data-ttu-id="4857a-253">Fuerza la generación de contenido incluso aunque se vayan a cambiar los archivos existentes.</span><span class="sxs-lookup"><span data-stu-id="4857a-253">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="4857a-254">Esto es necesario cuando el directorio de salida ya contiene un proyecto.</span><span class="sxs-lookup"><span data-stu-id="4857a-254">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="4857a-255">Imprime la ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="4857a-255">Prints out help for the command.</span></span> <span data-ttu-id="4857a-256">Puede invocarse para el propio comando `dotnet new` o para cualquier plantilla, como `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="4857a-256">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="4857a-257">Instala un paquete de plantillas u origen desde los parámetros `PATH` o `NUGET_ID` proporcionados.</span><span class="sxs-lookup"><span data-stu-id="4857a-257">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="4857a-258">Si quiere instalar una versión preliminar de un paquete de plantilla, tendrá que especificar la versión en el formato de `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="4857a-258">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="4857a-259">De manera predeterminada, `dotnet new` pasa \* para la versión, que representa la última versión estable del paquete.</span><span class="sxs-lookup"><span data-stu-id="4857a-259">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="4857a-260">Vea un ejemplo en la sección [Ejemplos](#examples).</span><span class="sxs-lookup"><span data-stu-id="4857a-260">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="4857a-261">Para obtener información sobre cómo crear plantillas personalizadas, consulte [Custom templates for dotnet new](custom-templates.md) (Plantillas personalizadas para dotnet new).</span><span class="sxs-lookup"><span data-stu-id="4857a-261">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="4857a-262">Muestra las plantillas que contienen el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="4857a-262">Lists templates containing the specified name.</span></span> <span data-ttu-id="4857a-263">Si se invoca para el comando `dotnet new`, muestra las plantillas posibles disponibles para un directorio determinado.</span><span class="sxs-lookup"><span data-stu-id="4857a-263">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="4857a-264">Por ejemplo, si el directorio ya contiene un proyecto, no mostrará todas las plantillas del proyecto.</span><span class="sxs-lookup"><span data-stu-id="4857a-264">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="4857a-265">El lenguaje de la plantilla que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="4857a-265">The language of the template to create.</span></span> <span data-ttu-id="4857a-266">El lenguaje aceptado cambia según la plantilla (vea los valores predeterminados en la sección [argumentos](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="4857a-266">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="4857a-267">No es válido para algunas plantillas.</span><span class="sxs-lookup"><span data-stu-id="4857a-267">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="4857a-268">Algunos shells interpretan `#` como un carácter especial.</span><span class="sxs-lookup"><span data-stu-id="4857a-268">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="4857a-269">En esos casos, debe incluir el valor del parámetro de lenguaje, como `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="4857a-269">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="4857a-270">El nombre de la salida creada.</span><span class="sxs-lookup"><span data-stu-id="4857a-270">The name for the created output.</span></span> <span data-ttu-id="4857a-271">Si no se especifica ningún nombre, se usa el nombre del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="4857a-271">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="4857a-272">La ubicación para colocar la salida generada.</span><span class="sxs-lookup"><span data-stu-id="4857a-272">Location to place the generated output.</span></span> <span data-ttu-id="4857a-273">El valor predeterminado es el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="4857a-273">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="4857a-274">Filtra plantillas en función de los tipos disponibles.</span><span class="sxs-lookup"><span data-stu-id="4857a-274">Filters templates based on available types.</span></span> <span data-ttu-id="4857a-275">Los valores predefinidos son “project”, “item” y “other”.</span><span class="sxs-lookup"><span data-stu-id="4857a-275">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="4857a-276">Desinstala un paquete de plantillas u origen en los parámetros `PATH` o `NUGET_ID` proporcionados.</span><span class="sxs-lookup"><span data-stu-id="4857a-276">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="4857a-277">Para desinstalar una plantilla mediante un origen `PATH`, debe usar el nombre completo de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="4857a-277">To uninstall a template using a source `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="4857a-278">Por ejemplo, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* funcionará, pero *./GarciaSoftware.ConsoleTemplate.CSharp* desde la carpeta contenedora no lo hará.</span><span class="sxs-lookup"><span data-stu-id="4857a-278">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span> <span data-ttu-id="4857a-279">Además, no debe incluir una barra diagonal para finalizar el directorio en la ruta de acceso a la plantilla.</span><span class="sxs-lookup"><span data-stu-id="4857a-279">Additionally, do not include a final terminating directory slash on your template path.</span></span>
> 
> <span data-ttu-id="4857a-280">Si no puede determinar el argumento `PATH` o `NUGET_ID` necesario para desinstalar una plantilla, la ejecución de `dotnet new --uninstall` sin un argumento enumerará todas las plantillas instaladas y el argumento requerido para desinstalarlas.</span><span class="sxs-lookup"><span data-stu-id="4857a-280">If you are unable to determine the `PATH` or `NUGET_ID` argument needed to uninstall a template, running `dotnet new --uninstall` without an argument will list all installed templates and the argument required to uninstall them.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="4857a-281">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="4857a-281">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="4857a-282">Muestra todas las plantillas de un tipo de proyecto específico cuando se ejecuta en el contexto del comando `dotnet new` por sí solo.</span><span class="sxs-lookup"><span data-stu-id="4857a-282">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="4857a-283">Cuando se ejecuta en el contexto de una plantilla específica, como `dotnet new web -all`, `-all` se interpreta como una marca para forzar la creación.</span><span class="sxs-lookup"><span data-stu-id="4857a-283">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="4857a-284">Esto es necesario cuando el directorio de salida ya contiene un proyecto.</span><span class="sxs-lookup"><span data-stu-id="4857a-284">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="4857a-285">Imprime la ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="4857a-285">Prints out help for the command.</span></span> <span data-ttu-id="4857a-286">Puede invocarse para el propio comando `dotnet new` o para cualquier plantilla, como `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="4857a-286">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="4857a-287">Muestra las plantillas que contienen el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="4857a-287">Lists templates containing the specified name.</span></span> <span data-ttu-id="4857a-288">Si se invoca para el comando `dotnet new`, muestra las plantillas posibles disponibles para un directorio determinado.</span><span class="sxs-lookup"><span data-stu-id="4857a-288">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="4857a-289">Por ejemplo, si el directorio ya contiene un proyecto, no mostrará todas las plantillas del proyecto.</span><span class="sxs-lookup"><span data-stu-id="4857a-289">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="4857a-290">El lenguaje de la plantilla que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="4857a-290">The language of the template to create.</span></span> <span data-ttu-id="4857a-291">El lenguaje aceptado cambia según la plantilla (vea los valores predeterminados en la sección [argumentos](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="4857a-291">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="4857a-292">No es válido para algunas plantillas.</span><span class="sxs-lookup"><span data-stu-id="4857a-292">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="4857a-293">Algunos shells interpretan `#` como un carácter especial.</span><span class="sxs-lookup"><span data-stu-id="4857a-293">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="4857a-294">En esos casos, debe incluir el valor del parámetro de lenguaje, como `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="4857a-294">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="4857a-295">El nombre de la salida creada.</span><span class="sxs-lookup"><span data-stu-id="4857a-295">The name for the created output.</span></span> <span data-ttu-id="4857a-296">Si no se especifica ningún nombre, se usa el nombre del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="4857a-296">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="4857a-297">La ubicación para colocar la salida generada.</span><span class="sxs-lookup"><span data-stu-id="4857a-297">Location to place the generated output.</span></span> <span data-ttu-id="4857a-298">El valor predeterminado es el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="4857a-298">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="4857a-299">Opciones de plantilla</span><span class="sxs-lookup"><span data-stu-id="4857a-299">Template options</span></span>

<span data-ttu-id="4857a-300">Cada plantilla de proyecto puede tener opciones adicionales disponibles.</span><span class="sxs-lookup"><span data-stu-id="4857a-300">Each project template may have additional options available.</span></span> <span data-ttu-id="4857a-301">Las plantillas principales tienen las siguientes opciones adicionales:</span><span class="sxs-lookup"><span data-stu-id="4857a-301">The core templates have the following additional options:</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="4857a-302">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="4857a-302">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="4857a-303">**console, angular, react, reactredux, razorclasslib**</span><span class="sxs-lookup"><span data-stu-id="4857a-303">**console, angular, react, reactredux, razorclasslib**</span></span>

  <span data-ttu-id="4857a-304">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="4857a-304">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="4857a-305">**classlib**</span><span class="sxs-lookup"><span data-stu-id="4857a-305">**classlib**</span></span>

<span data-ttu-id="4857a-306">`-f|--framework <FRAMEWORK>`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="4857a-306">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="4857a-307">Valores: `netcoreapp2.0` para crear una biblioteca de clases de .NET Core o `netstandard2.0` para crear una biblioteca de clases de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="4857a-307">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="4857a-308">El valor predeterminado es `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="4857a-308">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="4857a-309">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="4857a-309">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="4857a-310">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="4857a-310">**mstest, xunit**</span></span>

<span data-ttu-id="4857a-311">`-p|--enable-pack`: habilita el empaquetado para el proyecto mediante [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="4857a-311">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="4857a-312">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="4857a-312">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="4857a-313">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="4857a-313">**globaljson**</span></span>

<span data-ttu-id="4857a-314">`--sdk-version <VERSION_NUMBER>`: especifica la versión del SDK de .NET Core que se usará con el archivo *global.json*.</span><span class="sxs-lookup"><span data-stu-id="4857a-314">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="4857a-315">**web**</span><span class="sxs-lookup"><span data-stu-id="4857a-315">**web**</span></span>

<span data-ttu-id="4857a-316">`--exclude-launch-settings`: excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="4857a-316">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="4857a-317">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="4857a-317">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="4857a-318">`--no-https`: el proyecto no requiere HTTPS.</span><span class="sxs-lookup"><span data-stu-id="4857a-318">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="4857a-319">Esta opción solo se aplica si no se usan `IndividualAuth` u `OrganizationalAuth`.</span><span class="sxs-lookup"><span data-stu-id="4857a-319">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="4857a-320">**webapi**</span><span class="sxs-lookup"><span data-stu-id="4857a-320">**webapi**</span></span>

<span data-ttu-id="4857a-321">`-au|--auth <AUTHENTICATION_TYPE>`: el tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="4857a-321">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="4857a-322">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="4857a-322">The possible values are:</span></span>

- <span data-ttu-id="4857a-323">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="4857a-323">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="4857a-324">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="4857a-324">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="4857a-325">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="4857a-325">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="4857a-326">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="4857a-326">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="4857a-327">`--aad-b2c-instance <INSTANCE>`: la instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="4857a-327">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="4857a-328">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4857a-328">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="4857a-329">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="4857a-329">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="4857a-330">`-ssp|--susi-policy-id <ID>`: el id. de inicio de sesión y de directiva de registro de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="4857a-330">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="4857a-331">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4857a-331">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="4857a-332">`--aad-instance <INSTANCE>`: la instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="4857a-332">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="4857a-333">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="4857a-333">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="4857a-334">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="4857a-334">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="4857a-335">`--client-id <ID>`: el id. de cliente para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="4857a-335">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="4857a-336">Úsela con las autenticaciones `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="4857a-336">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="4857a-337">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="4857a-337">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="4857a-338">`--domain <DOMAIN>`: el dominio para el inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="4857a-338">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="4857a-339">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4857a-339">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="4857a-340">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="4857a-340">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="4857a-341">`--tenant-id <ID>`: el id. de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="4857a-341">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="4857a-342">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="4857a-342">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="4857a-343">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="4857a-343">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="4857a-344">`-r|--org-read-access`: concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="4857a-344">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="4857a-345">Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="4857a-345">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="4857a-346">`--exclude-launch-settings`: excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="4857a-346">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="4857a-347">`-uld|--use-local-db`: especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="4857a-347">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="4857a-348">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4857a-348">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="4857a-349">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="4857a-349">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="4857a-350">`--no-https`: el proyecto no requiere HTTPS.</span><span class="sxs-lookup"><span data-stu-id="4857a-350">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="4857a-351">`app.UseHsts` y `app.UseHttpsRedirection` no se agregan a `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="4857a-351">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="4857a-352">Esta opción solo se aplica si no se usan `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="4857a-352">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="4857a-353">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="4857a-353">**mvc, razor**</span></span>

<span data-ttu-id="4857a-354">`-au|--auth <AUTHENTICATION_TYPE>`: el tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="4857a-354">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="4857a-355">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="4857a-355">The possible values are:</span></span>

- <span data-ttu-id="4857a-356">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="4857a-356">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="4857a-357">`Individual`: autenticación individual.</span><span class="sxs-lookup"><span data-stu-id="4857a-357">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="4857a-358">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="4857a-358">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="4857a-359">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="4857a-359">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="4857a-360">`MultiOrg`: autenticación organizativa para varios inquilinos.</span><span class="sxs-lookup"><span data-stu-id="4857a-360">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="4857a-361">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="4857a-361">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="4857a-362">`--aad-b2c-instance <INSTANCE>`: la instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="4857a-362">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="4857a-363">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4857a-363">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="4857a-364">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="4857a-364">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="4857a-365">`-ssp|--susi-policy-id <ID>`: el id. de inicio de sesión y de directiva de registro de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="4857a-365">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="4857a-366">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4857a-366">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="4857a-367">`-rp|--reset-password-policy-id <ID>`: el id. de la directiva de restablecimiento de contraseñas para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="4857a-367">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="4857a-368">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4857a-368">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="4857a-369">`-ep|--edit-profile-policy-id <ID>`: el id. de directiva de edición de perfiles para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="4857a-369">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="4857a-370">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4857a-370">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="4857a-371">`--aad-instance <INSTANCE>`: la instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="4857a-371">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="4857a-372">Úsela con las autenticaciones `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="4857a-372">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="4857a-373">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="4857a-373">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="4857a-374">`--client-id <ID>`: el id. de cliente para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="4857a-374">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="4857a-375">Úsela con las autenticaciones `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="4857a-375">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="4857a-376">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="4857a-376">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="4857a-377">`--domain <DOMAIN>`: el dominio para el inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="4857a-377">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="4857a-378">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4857a-378">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="4857a-379">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="4857a-379">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="4857a-380">`--tenant-id <ID>`: el id. de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="4857a-380">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="4857a-381">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="4857a-381">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="4857a-382">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="4857a-382">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="4857a-383">`--callback-path <PATH>`: la ruta de acceso de solicitud de la ruta de acceso de la base de la aplicación del URI de redirección.</span><span class="sxs-lookup"><span data-stu-id="4857a-383">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="4857a-384">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4857a-384">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="4857a-385">El valor predeterminado es `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="4857a-385">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="4857a-386">`-r|--org-read-access`: concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="4857a-386">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="4857a-387">Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="4857a-387">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="4857a-388">`--exclude-launch-settings`: excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="4857a-388">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="4857a-389">`--use-browserlink`: incluye BrowserLink en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="4857a-389">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="4857a-390">`-uld|--use-local-db`: especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="4857a-390">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="4857a-391">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4857a-391">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="4857a-392">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="4857a-392">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="4857a-393">`--no-https`: el proyecto no requiere HTTPS.</span><span class="sxs-lookup"><span data-stu-id="4857a-393">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="4857a-394">`app.UseHsts` y `app.UseHttpsRedirection` no se agregan a `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="4857a-394">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="4857a-395">Esta opción solo se aplica si no se usan `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="4857a-395">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="4857a-396">**page**</span><span class="sxs-lookup"><span data-stu-id="4857a-396">**page**</span></span>

<span data-ttu-id="4857a-397">`-na|--namespace <NAMESPACE_NAME>`: espacio de nombres para el código generado.</span><span class="sxs-lookup"><span data-stu-id="4857a-397">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="4857a-398">El valor predeterminado es `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="4857a-398">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="4857a-399">`-np|--no-pagemodel`: crea la página sin PageModel.</span><span class="sxs-lookup"><span data-stu-id="4857a-399">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="4857a-400">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="4857a-400">**viewimports**</span></span>

<span data-ttu-id="4857a-401">`-na|--namespace <NAMESPACE_NAME>`: espacio de nombres para el código generado.</span><span class="sxs-lookup"><span data-stu-id="4857a-401">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="4857a-402">El valor predeterminado es `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="4857a-402">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="4857a-403">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="4857a-403">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="4857a-404">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="4857a-404">**console, angular, react, reactredux**</span></span>

  <span data-ttu-id="4857a-405">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="4857a-405">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="4857a-406">**classlib**</span><span class="sxs-lookup"><span data-stu-id="4857a-406">**classlib**</span></span>

<span data-ttu-id="4857a-407">`-f|--framework <FRAMEWORK>`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="4857a-407">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="4857a-408">Valores: `netcoreapp2.0` para crear una biblioteca de clases de .NET Core o `netstandard2.0` para crear una biblioteca de clases de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="4857a-408">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="4857a-409">El valor predeterminado es `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="4857a-409">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="4857a-410">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="4857a-410">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="4857a-411">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="4857a-411">**mstest, xunit**</span></span>

<span data-ttu-id="4857a-412">`-p|--enable-pack`: habilita el empaquetado para el proyecto mediante [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="4857a-412">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="4857a-413">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="4857a-413">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="4857a-414">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="4857a-414">**globaljson**</span></span>

<span data-ttu-id="4857a-415">`--sdk-version <VERSION_NUMBER>`: especifica la versión del SDK de .NET Core que se usará con el archivo *global.json*.</span><span class="sxs-lookup"><span data-stu-id="4857a-415">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="4857a-416">**web**</span><span class="sxs-lookup"><span data-stu-id="4857a-416">**web**</span></span>

<span data-ttu-id="4857a-417">`--use-launch-settings`: incluye *launchSettings.json* en la salida de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="4857a-417">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="4857a-418">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="4857a-418">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="4857a-419">**webapi**</span><span class="sxs-lookup"><span data-stu-id="4857a-419">**webapi**</span></span>

<span data-ttu-id="4857a-420">`-au|--auth <AUTHENTICATION_TYPE>`: el tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="4857a-420">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="4857a-421">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="4857a-421">The possible values are:</span></span>

- <span data-ttu-id="4857a-422">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="4857a-422">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="4857a-423">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="4857a-423">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="4857a-424">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="4857a-424">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="4857a-425">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="4857a-425">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="4857a-426">`--aad-b2c-instance <INSTANCE>`: la instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="4857a-426">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="4857a-427">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4857a-427">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="4857a-428">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="4857a-428">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="4857a-429">`-ssp|--susi-policy-id <ID>`: el id. de inicio de sesión y de directiva de registro de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="4857a-429">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="4857a-430">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4857a-430">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="4857a-431">`--aad-instance <INSTANCE>`: la instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="4857a-431">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="4857a-432">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="4857a-432">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="4857a-433">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="4857a-433">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="4857a-434">`--client-id <ID>`: el id. de cliente para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="4857a-434">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="4857a-435">Úsela con las autenticaciones `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="4857a-435">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="4857a-436">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="4857a-436">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="4857a-437">`--domain <DOMAIN>`: el dominio para el inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="4857a-437">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="4857a-438">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4857a-438">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="4857a-439">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="4857a-439">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="4857a-440">`--tenant-id <ID>`: el id. de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="4857a-440">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="4857a-441">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="4857a-441">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="4857a-442">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="4857a-442">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="4857a-443">`-r|--org-read-access`: concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="4857a-443">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="4857a-444">Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="4857a-444">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="4857a-445">`--use-launch-settings`: incluye *launchSettings.json* en la salida de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="4857a-445">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="4857a-446">`-uld|--use-local-db`: especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="4857a-446">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="4857a-447">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4857a-447">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="4857a-448">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="4857a-448">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="4857a-449">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="4857a-449">**mvc, razor**</span></span>

<span data-ttu-id="4857a-450">`-au|--auth <AUTHENTICATION_TYPE>`: el tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="4857a-450">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="4857a-451">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="4857a-451">The possible values are:</span></span>

- <span data-ttu-id="4857a-452">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="4857a-452">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="4857a-453">`Individual`: autenticación individual.</span><span class="sxs-lookup"><span data-stu-id="4857a-453">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="4857a-454">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="4857a-454">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="4857a-455">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="4857a-455">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="4857a-456">`MultiOrg`: autenticación organizativa para varios inquilinos.</span><span class="sxs-lookup"><span data-stu-id="4857a-456">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="4857a-457">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="4857a-457">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="4857a-458">`--aad-b2c-instance <INSTANCE>`: la instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="4857a-458">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="4857a-459">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4857a-459">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="4857a-460">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="4857a-460">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="4857a-461">`-ssp|--susi-policy-id <ID>`: el id. de inicio de sesión y de directiva de registro de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="4857a-461">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="4857a-462">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4857a-462">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="4857a-463">`-rp|--reset-password-policy-id <ID>`: el id. de la directiva de restablecimiento de contraseñas para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="4857a-463">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="4857a-464">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4857a-464">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="4857a-465">`-ep|--edit-profile-policy-id <ID>`: el id. de directiva de edición de perfiles para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="4857a-465">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="4857a-466">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4857a-466">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="4857a-467">`--aad-instance <INSTANCE>`: la instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="4857a-467">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="4857a-468">Úsela con las autenticaciones `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="4857a-468">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="4857a-469">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="4857a-469">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="4857a-470">`--client-id <ID>`: el id. de cliente para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="4857a-470">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="4857a-471">Úsela con las autenticaciones `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="4857a-471">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="4857a-472">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="4857a-472">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="4857a-473">`--domain <DOMAIN>`: el dominio para el inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="4857a-473">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="4857a-474">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4857a-474">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="4857a-475">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="4857a-475">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="4857a-476">`--tenant-id <ID>`: el id. de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="4857a-476">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="4857a-477">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="4857a-477">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="4857a-478">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="4857a-478">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="4857a-479">`--callback-path <PATH>`: la ruta de acceso de solicitud de la ruta de acceso de la base de la aplicación del URI de redirección.</span><span class="sxs-lookup"><span data-stu-id="4857a-479">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="4857a-480">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4857a-480">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="4857a-481">El valor predeterminado es `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="4857a-481">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="4857a-482">`-r|--org-read-access`: concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="4857a-482">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="4857a-483">Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="4857a-483">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="4857a-484">`--use-launch-settings`: incluye *launchSettings.json* en la salida de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="4857a-484">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="4857a-485">`--use-browserlink`: incluye BrowserLink en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="4857a-485">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="4857a-486">`-uld|--use-local-db`: especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="4857a-486">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="4857a-487">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4857a-487">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="4857a-488">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="4857a-488">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="4857a-489">**page**</span><span class="sxs-lookup"><span data-stu-id="4857a-489">**page**</span></span>

<span data-ttu-id="4857a-490">`-na|--namespace <NAMESPACE_NAME>`: espacio de nombres para el código generado.</span><span class="sxs-lookup"><span data-stu-id="4857a-490">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="4857a-491">El valor predeterminado es `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="4857a-491">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="4857a-492">`-np|--no-pagemodel`: crea la página sin PageModel.</span><span class="sxs-lookup"><span data-stu-id="4857a-492">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="4857a-493">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="4857a-493">**viewimports**</span></span>

<span data-ttu-id="4857a-494">`-na|--namespace <NAMESPACE_NAME>`: espacio de nombres para el código generado.</span><span class="sxs-lookup"><span data-stu-id="4857a-494">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="4857a-495">El valor predeterminado es `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="4857a-495">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="4857a-496">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="4857a-496">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="4857a-497">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="4857a-497">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="4857a-498">`-f|--framework`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="4857a-498">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="4857a-499">Valores: `netcoreapp1.0` o `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="4857a-499">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="4857a-500">El valor predeterminado es `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="4857a-500">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="4857a-501">**classlib**</span><span class="sxs-lookup"><span data-stu-id="4857a-501">**classlib**</span></span>

<span data-ttu-id="4857a-502">`-f|--framework`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="4857a-502">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="4857a-503">Valores: `netcoreapp1.0`, `netcoreapp1.1` o de `netstandard1.0` a `netstandard1.6`.</span><span class="sxs-lookup"><span data-stu-id="4857a-503">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="4857a-504">El valor predeterminado es `netstandard1.4`.</span><span class="sxs-lookup"><span data-stu-id="4857a-504">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="4857a-505">**mvc**</span><span class="sxs-lookup"><span data-stu-id="4857a-505">**mvc**</span></span>

<span data-ttu-id="4857a-506">`-f|--framework`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="4857a-506">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="4857a-507">Valores: `netcoreapp1.0` o `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="4857a-507">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="4857a-508">El valor predeterminado es `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="4857a-508">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="4857a-509">`-au|--auth`: el tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="4857a-509">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="4857a-510">Valores: `None` o `Individual`.</span><span class="sxs-lookup"><span data-stu-id="4857a-510">Values: `None` or `Individual`.</span></span> <span data-ttu-id="4857a-511">El valor predeterminado es `None`.</span><span class="sxs-lookup"><span data-stu-id="4857a-511">The default value is `None`.</span></span>

<span data-ttu-id="4857a-512">`-uld|--use-local-db`: especifica si se va a usar o no LocalDB en lugar de SQLite.</span><span class="sxs-lookup"><span data-stu-id="4857a-512">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="4857a-513">Valores: `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="4857a-513">Values: `true` or `false`.</span></span> <span data-ttu-id="4857a-514">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="4857a-514">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="4857a-515">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="4857a-515">Examples</span></span>

<span data-ttu-id="4857a-516">Creación de un proyecto de aplicación de consola con F# en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="4857a-516">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang F#`

<span data-ttu-id="4857a-517">Creación de un proyecto de biblioteca de clases de .NET Standard en el directorio especificado (disponible solo con el SDK de .NET Core 2.0 o versiones posteriores):</span><span class="sxs-lookup"><span data-stu-id="4857a-517">Create a .NET Standard class library project in the specified directory (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="4857a-518">Creación de un proyecto de aplicación MVC de ASP.NET Core C# en el directorio actual sin autenticación:</span><span class="sxs-lookup"><span data-stu-id="4857a-518">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication:</span></span>

`dotnet new mvc -au None`

<span data-ttu-id="4857a-519">Cree una aplicación de xUnit.</span><span class="sxs-lookup"><span data-stu-id="4857a-519">Create a new xUnit application:</span></span>

`dotnet new xunit`

<span data-ttu-id="4857a-520">Enumere todas las plantillas disponibles para MVC:</span><span class="sxs-lookup"><span data-stu-id="4857a-520">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

<span data-ttu-id="4857a-521">Instalación de la versión 2.0 de las plantillas Aplicación de página única para ASP.NET Core (opción de comando solo disponible para .NET Core SDK 1.1 y versiones posteriores):</span><span class="sxs-lookup"><span data-stu-id="4857a-521">Install version 2.0 of the Single Page Application templates for ASP.NET Core (command option available for .NET Core SDK 1.1 and later versions only):</span></span>

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

<span data-ttu-id="4857a-522">Creación de un archivo *global.json* en el directorio actual que establezca la versión del SDK en 2.0.0 (solo disponible en el SDK de .NET Core 2.0 o versiones posteriores):</span><span class="sxs-lookup"><span data-stu-id="4857a-522">Create a *global.json* in the current directory setting the SDK version to 2.0.0 (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new globaljson --sdk-version 2.0.0`

## <a name="see-also"></a><span data-ttu-id="4857a-523">Vea también</span><span class="sxs-lookup"><span data-stu-id="4857a-523">See also</span></span>

* <span data-ttu-id="4857a-524">[Custom templates for dotnet new](custom-templates.md) (Plantillas personalizadas para dotnet new)</span><span class="sxs-lookup"><span data-stu-id="4857a-524">[Custom templates for dotnet new](custom-templates.md)</span></span>  
* [<span data-ttu-id="4857a-525">Creación de una plantilla personalizada para dotnet new</span><span class="sxs-lookup"><span data-stu-id="4857a-525">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)  
* [<span data-ttu-id="4857a-526">Repositorio de GitHub dotnet/dotnet-template-samples</span><span class="sxs-lookup"><span data-stu-id="4857a-526">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)  
* <span data-ttu-id="4857a-527">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new) (Plantillas disponibles para dotnet new)</span><span class="sxs-lookup"><span data-stu-id="4857a-527">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)</span></span>
