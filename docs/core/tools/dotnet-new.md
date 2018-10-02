---
title: 'Comando dotnet new: CLI de .NET Core'
description: El comando dotnet new crea proyectos de .NET Core basados en la plantilla especificada.
author: mairaw
ms.author: mairaw
ms.date: 07/31/2018
ms.openlocfilehash: 2c82dda2d93225edb360316637e22964135cd5e4
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43512560"
---
# <a name="dotnet-new"></a><span data-ttu-id="e0b26-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="e0b26-103">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="e0b26-104">nombre</span><span class="sxs-lookup"><span data-stu-id="e0b26-104">Name</span></span>

<span data-ttu-id="e0b26-105">`dotnet new`: crea un nuevo proyecto, archivo de configuración o solución según la plantilla especificada.</span><span class="sxs-lookup"><span data-stu-id="e0b26-105">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="e0b26-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="e0b26-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="e0b26-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="e0b26-107">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output]
    [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="e0b26-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="e0b26-108">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="e0b26-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="e0b26-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="e0b26-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="e0b26-110">Description</span></span>

<span data-ttu-id="e0b26-111">El comando `dotnet new` proporciona una manera cómoda de inicializar un proyecto .NET Core válido.</span><span class="sxs-lookup"><span data-stu-id="e0b26-111">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span>

<span data-ttu-id="e0b26-112">El comando llama al [motor de plantillas](https://github.com/dotnet/templating) para crear los artefactos en el disco basándose en las opciones y la plantilla especificadas.</span><span class="sxs-lookup"><span data-stu-id="e0b26-112">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="e0b26-113">Argumentos</span><span class="sxs-lookup"><span data-stu-id="e0b26-113">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="e0b26-114">La plantilla de la que se va a crear una instancia cuando se invoca el comando.</span><span class="sxs-lookup"><span data-stu-id="e0b26-114">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="e0b26-115">Cada plantilla puede tener opciones específicas que puede pasar.</span><span class="sxs-lookup"><span data-stu-id="e0b26-115">Each template might have specific options you can pass.</span></span> <span data-ttu-id="e0b26-116">Para obtener más información, vea [Opciones de plantilla](#template-options).</span><span class="sxs-lookup"><span data-stu-id="e0b26-116">For more information, see [Template options](#template-options).</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="e0b26-117">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="e0b26-117">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="e0b26-118">El comando contiene una lista predeterminada de plantillas.</span><span class="sxs-lookup"><span data-stu-id="e0b26-118">The command contains a default list of templates.</span></span> <span data-ttu-id="e0b26-119">Use `dotnet new -l` para obtener una lista de las plantillas disponibles.</span><span class="sxs-lookup"><span data-stu-id="e0b26-119">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="e0b26-120">En la tabla siguiente se muestran las plantillas que vienen preinstaladas con el SDK de .NET Core 2.1.300.</span><span class="sxs-lookup"><span data-stu-id="e0b26-120">The following table shows the templates that come pre-installed with the .NET Core SDK 2.1.300.</span></span> <span data-ttu-id="e0b26-121">El lenguaje predeterminado de la plantilla se muestra entre corchetes.</span><span class="sxs-lookup"><span data-stu-id="e0b26-121">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="e0b26-122">Descripción de plantilla</span><span class="sxs-lookup"><span data-stu-id="e0b26-122">Template description</span></span>                          | <span data-ttu-id="e0b26-123">Nombre de plantilla</span><span class="sxs-lookup"><span data-stu-id="e0b26-123">Template name</span></span>   | <span data-ttu-id="e0b26-124">Lenguajes</span><span class="sxs-lookup"><span data-stu-id="e0b26-124">Languages</span></span>     |
|----------------------------------------------|-----------------|---------------|
| <span data-ttu-id="e0b26-125">Aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="e0b26-125">Console application</span></span>                          | `console`       | <span data-ttu-id="e0b26-126">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e0b26-126">[C#], F#, VB</span></span>  |
| <span data-ttu-id="e0b26-127">Biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="e0b26-127">Class library</span></span>                                | `classlib`      | <span data-ttu-id="e0b26-128">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e0b26-128">[C#], F#, VB</span></span>  |
| <span data-ttu-id="e0b26-129">Proyecto de prueba unitaria</span><span class="sxs-lookup"><span data-stu-id="e0b26-129">Unit test project</span></span>                            | `mstest`        | <span data-ttu-id="e0b26-130">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e0b26-130">[C#], F#, VB</span></span>  |
| <span data-ttu-id="e0b26-131">Proyecto de prueba xUnit</span><span class="sxs-lookup"><span data-stu-id="e0b26-131">xUnit test project</span></span>                           | `xunit`         | <span data-ttu-id="e0b26-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e0b26-132">[C#], F#, VB</span></span>  |
| <span data-ttu-id="e0b26-133">Página de Razor</span><span class="sxs-lookup"><span data-stu-id="e0b26-133">Razor page</span></span>                                   | `page`          | <span data-ttu-id="e0b26-134">[C#]</span><span class="sxs-lookup"><span data-stu-id="e0b26-134">[C#]</span></span>          |
| <span data-ttu-id="e0b26-135">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="e0b26-135">MVC ViewImports</span></span>                              | `viewimports`   | <span data-ttu-id="e0b26-136">[C#]</span><span class="sxs-lookup"><span data-stu-id="e0b26-136">[C#]</span></span>          |
| <span data-ttu-id="e0b26-137">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="e0b26-137">MVC ViewStart</span></span>                                | `viewstart`     | <span data-ttu-id="e0b26-138">[C#]</span><span class="sxs-lookup"><span data-stu-id="e0b26-138">[C#]</span></span>          |
| <span data-ttu-id="e0b26-139">Vacío de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e0b26-139">ASP.NET Core empty</span></span>                           | `web`           | <span data-ttu-id="e0b26-140">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e0b26-140">[C#], F#</span></span>      |
| <span data-ttu-id="e0b26-141">Aplicación web de ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="e0b26-141">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`           | <span data-ttu-id="e0b26-142">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e0b26-142">[C#], F#</span></span>      |
| <span data-ttu-id="e0b26-143">Aplicación web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e0b26-143">ASP.NET Core Web App</span></span>                         | `razor`         | <span data-ttu-id="e0b26-144">[C#]</span><span class="sxs-lookup"><span data-stu-id="e0b26-144">[C#]</span></span>          |
| <span data-ttu-id="e0b26-145">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="e0b26-145">ASP.NET Core with Angular</span></span>                    | `angular`       | <span data-ttu-id="e0b26-146">[C#]</span><span class="sxs-lookup"><span data-stu-id="e0b26-146">[C#]</span></span>          |
| <span data-ttu-id="e0b26-147">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="e0b26-147">ASP.NET Core with React.js</span></span>                   | `react`         | <span data-ttu-id="e0b26-148">[C#]</span><span class="sxs-lookup"><span data-stu-id="e0b26-148">[C#]</span></span>          |
| <span data-ttu-id="e0b26-149">ASP.NET Core con React.js y Redux</span><span class="sxs-lookup"><span data-stu-id="e0b26-149">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`    | <span data-ttu-id="e0b26-150">[C#]</span><span class="sxs-lookup"><span data-stu-id="e0b26-150">[C#]</span></span>          |
| <span data-ttu-id="e0b26-151">API web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e0b26-151">ASP.NET Core Web API</span></span>                         | `webapi`        | <span data-ttu-id="e0b26-152">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e0b26-152">[C#], F#</span></span>      |
| <span data-ttu-id="e0b26-153">Biblioteca de clases de Razor</span><span class="sxs-lookup"><span data-stu-id="e0b26-153">Razor class library</span></span>                          | `razorclasslib` | <span data-ttu-id="e0b26-154">[C#]</span><span class="sxs-lookup"><span data-stu-id="e0b26-154">[C#]</span></span>          |
| <span data-ttu-id="e0b26-155">archivo global.json</span><span class="sxs-lookup"><span data-stu-id="e0b26-155">global.json file</span></span>                             | `globaljson`    |               |
| <span data-ttu-id="e0b26-156">Configuración de NuGet</span><span class="sxs-lookup"><span data-stu-id="e0b26-156">NuGet config</span></span>                                 | `nugetconfig`   |               |
| <span data-ttu-id="e0b26-157">Configuración de la Web</span><span class="sxs-lookup"><span data-stu-id="e0b26-157">Web config</span></span>                                   | `webconfig`     |               |
| <span data-ttu-id="e0b26-158">Archivo de solución</span><span class="sxs-lookup"><span data-stu-id="e0b26-158">Solution file</span></span>                                | `sln`           |               |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="e0b26-159">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="e0b26-159">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="e0b26-160">El comando contiene una lista predeterminada de plantillas.</span><span class="sxs-lookup"><span data-stu-id="e0b26-160">The command contains a default list of templates.</span></span> <span data-ttu-id="e0b26-161">Use `dotnet new -l` para obtener una lista de las plantillas disponibles.</span><span class="sxs-lookup"><span data-stu-id="e0b26-161">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="e0b26-162">En la tabla siguiente se muestran las plantillas que vienen preinstaladas con el SDK de .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="e0b26-162">The following table shows the templates that come pre-installed with the .NET Core SDK 2.0.</span></span> <span data-ttu-id="e0b26-163">El lenguaje predeterminado de la plantilla se muestra entre corchetes.</span><span class="sxs-lookup"><span data-stu-id="e0b26-163">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="e0b26-164">Descripción de plantilla</span><span class="sxs-lookup"><span data-stu-id="e0b26-164">Template description</span></span>                          | <span data-ttu-id="e0b26-165">Nombre de plantilla</span><span class="sxs-lookup"><span data-stu-id="e0b26-165">Template name</span></span> | <span data-ttu-id="e0b26-166">Lenguajes</span><span class="sxs-lookup"><span data-stu-id="e0b26-166">Languages</span></span>     |
|----------------------------------------------|---------------|---------------|
| <span data-ttu-id="e0b26-167">Aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="e0b26-167">Console application</span></span>                          | `console`     | <span data-ttu-id="e0b26-168">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e0b26-168">[C#], F#, VB</span></span>  |
| <span data-ttu-id="e0b26-169">Biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="e0b26-169">Class library</span></span>                                | `classlib`    | <span data-ttu-id="e0b26-170">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e0b26-170">[C#], F#, VB</span></span>  |
| <span data-ttu-id="e0b26-171">Proyecto de prueba unitaria</span><span class="sxs-lookup"><span data-stu-id="e0b26-171">Unit test project</span></span>                            | `mstest`      | <span data-ttu-id="e0b26-172">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e0b26-172">[C#], F#, VB</span></span>  |
| <span data-ttu-id="e0b26-173">Proyecto de prueba xUnit</span><span class="sxs-lookup"><span data-stu-id="e0b26-173">xUnit test project</span></span>                           | `xunit`       | <span data-ttu-id="e0b26-174">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e0b26-174">[C#], F#, VB</span></span>  |
| <span data-ttu-id="e0b26-175">Vacío de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e0b26-175">ASP.NET Core empty</span></span>                           | `web`         | <span data-ttu-id="e0b26-176">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e0b26-176">[C#], F#</span></span>      |
| <span data-ttu-id="e0b26-177">Aplicación web de ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="e0b26-177">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="e0b26-178">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e0b26-178">[C#], F#</span></span>      |
| <span data-ttu-id="e0b26-179">Aplicación web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e0b26-179">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="e0b26-180">[C#]</span><span class="sxs-lookup"><span data-stu-id="e0b26-180">[C#]</span></span>          |
| <span data-ttu-id="e0b26-181">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="e0b26-181">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="e0b26-182">[C#]</span><span class="sxs-lookup"><span data-stu-id="e0b26-182">[C#]</span></span>          |
| <span data-ttu-id="e0b26-183">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="e0b26-183">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="e0b26-184">[C#]</span><span class="sxs-lookup"><span data-stu-id="e0b26-184">[C#]</span></span>          |
| <span data-ttu-id="e0b26-185">ASP.NET Core con React.js y Redux</span><span class="sxs-lookup"><span data-stu-id="e0b26-185">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="e0b26-186">[C#]</span><span class="sxs-lookup"><span data-stu-id="e0b26-186">[C#]</span></span>          |
| <span data-ttu-id="e0b26-187">API web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e0b26-187">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="e0b26-188">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e0b26-188">[C#], F#</span></span>      |
| <span data-ttu-id="e0b26-189">archivo global.json</span><span class="sxs-lookup"><span data-stu-id="e0b26-189">global.json file</span></span>                             | `globaljson`  |               |
| <span data-ttu-id="e0b26-190">Configuración de NuGet</span><span class="sxs-lookup"><span data-stu-id="e0b26-190">NuGet config</span></span>                                 | `nugetconfig` |               |
| <span data-ttu-id="e0b26-191">Configuración de la Web</span><span class="sxs-lookup"><span data-stu-id="e0b26-191">Web config</span></span>                                   | `webconfig`   |               |
| <span data-ttu-id="e0b26-192">Archivo de solución</span><span class="sxs-lookup"><span data-stu-id="e0b26-192">Solution file</span></span>                                | `sln`         |               |
| <span data-ttu-id="e0b26-193">Página de Razor</span><span class="sxs-lookup"><span data-stu-id="e0b26-193">Razor page</span></span>                                   | `page`        |               |
| <span data-ttu-id="e0b26-194">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="e0b26-194">MVC ViewImports</span></span>                              | `viewimports` |               |
| <span data-ttu-id="e0b26-195">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="e0b26-195">MVC ViewStart</span></span>                                | `viewstart`   |               |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="e0b26-196">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="e0b26-196">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="e0b26-197">El comando contiene una lista predeterminada de plantillas.</span><span class="sxs-lookup"><span data-stu-id="e0b26-197">The command contains a default list of templates.</span></span> <span data-ttu-id="e0b26-198">Use `dotnet new -all` para obtener una lista de las plantillas disponibles.</span><span class="sxs-lookup"><span data-stu-id="e0b26-198">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="e0b26-199">En la tabla siguiente se muestran las plantillas que vienen preinstaladas con el SDK de .NET 1.x.</span><span class="sxs-lookup"><span data-stu-id="e0b26-199">The following table shows the templates that come pre-installed with the .NET Core SDK 1.x.</span></span> <span data-ttu-id="e0b26-200">El lenguaje predeterminado de la plantilla se muestra entre corchetes.</span><span class="sxs-lookup"><span data-stu-id="e0b26-200">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="e0b26-201">Descripción de plantilla</span><span class="sxs-lookup"><span data-stu-id="e0b26-201">Template description</span></span>  | <span data-ttu-id="e0b26-202">Nombre de plantilla</span><span class="sxs-lookup"><span data-stu-id="e0b26-202">Template name</span></span> | <span data-ttu-id="e0b26-203">Lenguajes</span><span class="sxs-lookup"><span data-stu-id="e0b26-203">Languages</span></span> |
|----------------------|---------------|-----------|
| <span data-ttu-id="e0b26-204">Aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="e0b26-204">Console application</span></span>  | `console`     | <span data-ttu-id="e0b26-205">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e0b26-205">[C#], F#</span></span>  |
| <span data-ttu-id="e0b26-206">Biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="e0b26-206">Class library</span></span>        | `classlib`    | <span data-ttu-id="e0b26-207">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e0b26-207">[C#], F#</span></span>  |
| <span data-ttu-id="e0b26-208">Proyecto de prueba unitaria</span><span class="sxs-lookup"><span data-stu-id="e0b26-208">Unit test project</span></span>    | `mstest`      | <span data-ttu-id="e0b26-209">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e0b26-209">[C#], F#</span></span>  |
| <span data-ttu-id="e0b26-210">Proyecto de prueba xUnit</span><span class="sxs-lookup"><span data-stu-id="e0b26-210">xUnit test project</span></span>   | `xunit`       | <span data-ttu-id="e0b26-211">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e0b26-211">[C#], F#</span></span>  |
| <span data-ttu-id="e0b26-212">Vacío de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e0b26-212">ASP.NET Core empty</span></span>   | `web`         | <span data-ttu-id="e0b26-213">[C#]</span><span class="sxs-lookup"><span data-stu-id="e0b26-213">[C#]</span></span>      |
| <span data-ttu-id="e0b26-214">Aplicación web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e0b26-214">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="e0b26-215">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e0b26-215">[C#], F#</span></span>  |
| <span data-ttu-id="e0b26-216">API web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e0b26-216">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="e0b26-217">[C#]</span><span class="sxs-lookup"><span data-stu-id="e0b26-217">[C#]</span></span>      |
| <span data-ttu-id="e0b26-218">Configuración de NuGet</span><span class="sxs-lookup"><span data-stu-id="e0b26-218">NuGet config</span></span>         | `nugetconfig` |           |
| <span data-ttu-id="e0b26-219">Configuración de la Web</span><span class="sxs-lookup"><span data-stu-id="e0b26-219">Web config</span></span>           | `webconfig`   |           |
| <span data-ttu-id="e0b26-220">Archivo de solución</span><span class="sxs-lookup"><span data-stu-id="e0b26-220">Solution file</span></span>        | `sln`         |           |

---

## <a name="options"></a><span data-ttu-id="e0b26-221">Opciones</span><span class="sxs-lookup"><span data-stu-id="e0b26-221">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="e0b26-222">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="e0b26-222">.NET Core 2.1</span></span>](#tab/netcore21)

`--force`

<span data-ttu-id="e0b26-223">Fuerza la generación de contenido incluso aunque se vayan a cambiar los archivos existentes.</span><span class="sxs-lookup"><span data-stu-id="e0b26-223">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="e0b26-224">Esto es necesario cuando el directorio de salida ya contiene un proyecto.</span><span class="sxs-lookup"><span data-stu-id="e0b26-224">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="e0b26-225">Imprime la ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="e0b26-225">Prints out help for the command.</span></span> <span data-ttu-id="e0b26-226">Puede invocarse para el propio comando `dotnet new` o para cualquier plantilla, como `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-226">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="e0b26-227">Instala un paquete de plantillas u origen desde los parámetros `PATH` o `NUGET_ID` proporcionados.</span><span class="sxs-lookup"><span data-stu-id="e0b26-227">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="e0b26-228">Si quiere instalar una versión preliminar de un paquete de plantilla, tendrá que especificar la versión en el formato de `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-228">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="e0b26-229">De manera predeterminada, `dotnet new` pasa \* para la versión, que representa la última versión estable del paquete.</span><span class="sxs-lookup"><span data-stu-id="e0b26-229">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="e0b26-230">Vea un ejemplo en la sección [Ejemplos](#examples).</span><span class="sxs-lookup"><span data-stu-id="e0b26-230">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="e0b26-231">Para obtener información sobre cómo crear plantillas personalizadas, consulte [Custom templates for dotnet new](custom-templates.md) (Plantillas personalizadas para dotnet new).</span><span class="sxs-lookup"><span data-stu-id="e0b26-231">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="e0b26-232">Muestra las plantillas que contienen el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="e0b26-232">Lists templates containing the specified name.</span></span> <span data-ttu-id="e0b26-233">Si se invoca para el comando `dotnet new`, muestra las plantillas posibles disponibles para un directorio determinado.</span><span class="sxs-lookup"><span data-stu-id="e0b26-233">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="e0b26-234">Por ejemplo, si el directorio ya contiene un proyecto, no mostrará todas las plantillas del proyecto.</span><span class="sxs-lookup"><span data-stu-id="e0b26-234">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="e0b26-235">El lenguaje de la plantilla que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="e0b26-235">The language of the template to create.</span></span> <span data-ttu-id="e0b26-236">El lenguaje aceptado cambia según la plantilla (vea los valores predeterminados en la sección [argumentos](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="e0b26-236">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="e0b26-237">No es válido para algunas plantillas.</span><span class="sxs-lookup"><span data-stu-id="e0b26-237">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="e0b26-238">Algunos shells interpretan `#` como un carácter especial.</span><span class="sxs-lookup"><span data-stu-id="e0b26-238">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="e0b26-239">En esos casos, debe incluir el valor del parámetro de lenguaje, como `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-239">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="e0b26-240">El nombre de la salida creada.</span><span class="sxs-lookup"><span data-stu-id="e0b26-240">The name for the created output.</span></span> <span data-ttu-id="e0b26-241">Si no se especifica ningún nombre, se usa el nombre del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="e0b26-241">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="e0b26-242">Especifica un origen de NuGet para usarlo durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="e0b26-242">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="e0b26-243">La ubicación para colocar la salida generada.</span><span class="sxs-lookup"><span data-stu-id="e0b26-243">Location to place the generated output.</span></span> <span data-ttu-id="e0b26-244">El valor predeterminado es el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="e0b26-244">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="e0b26-245">Filtra plantillas en función de los tipos disponibles.</span><span class="sxs-lookup"><span data-stu-id="e0b26-245">Filters templates based on available types.</span></span> <span data-ttu-id="e0b26-246">Los valores predefinidos son “project”, “item” y “other”.</span><span class="sxs-lookup"><span data-stu-id="e0b26-246">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="e0b26-247">Desinstala un paquete de plantillas u origen en los parámetros `PATH` o `NUGET_ID` proporcionados.</span><span class="sxs-lookup"><span data-stu-id="e0b26-247">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="e0b26-248">Para desinstalar una plantilla mediante `PATH`, debe usar el nombre completo de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="e0b26-248">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="e0b26-249">Por ejemplo, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* funcionará, pero *./GarciaSoftware.ConsoleTemplate.CSharp* desde la carpeta contenedora no lo hará.</span><span class="sxs-lookup"><span data-stu-id="e0b26-249">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="e0b26-250">Además, no debe incluir una barra diagonal para finalizar el directorio en la ruta de acceso a la plantilla.</span><span class="sxs-lookup"><span data-stu-id="e0b26-250">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="e0b26-251">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="e0b26-251">.NET Core 2.0</span></span>](#tab/netcore20)

`--force`

<span data-ttu-id="e0b26-252">Fuerza la generación de contenido incluso aunque se vayan a cambiar los archivos existentes.</span><span class="sxs-lookup"><span data-stu-id="e0b26-252">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="e0b26-253">Esto es necesario cuando el directorio de salida ya contiene un proyecto.</span><span class="sxs-lookup"><span data-stu-id="e0b26-253">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="e0b26-254">Imprime la ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="e0b26-254">Prints out help for the command.</span></span> <span data-ttu-id="e0b26-255">Puede invocarse para el propio comando `dotnet new` o para cualquier plantilla, como `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-255">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="e0b26-256">Instala un paquete de plantillas u origen desde los parámetros `PATH` o `NUGET_ID` proporcionados.</span><span class="sxs-lookup"><span data-stu-id="e0b26-256">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="e0b26-257">Si quiere instalar una versión preliminar de un paquete de plantilla, tendrá que especificar la versión en el formato de `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-257">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="e0b26-258">De manera predeterminada, `dotnet new` pasa \* para la versión, que representa la última versión estable del paquete.</span><span class="sxs-lookup"><span data-stu-id="e0b26-258">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="e0b26-259">Vea un ejemplo en la sección [Ejemplos](#examples).</span><span class="sxs-lookup"><span data-stu-id="e0b26-259">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="e0b26-260">Para obtener información sobre cómo crear plantillas personalizadas, consulte [Custom templates for dotnet new](custom-templates.md) (Plantillas personalizadas para dotnet new).</span><span class="sxs-lookup"><span data-stu-id="e0b26-260">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="e0b26-261">Muestra las plantillas que contienen el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="e0b26-261">Lists templates containing the specified name.</span></span> <span data-ttu-id="e0b26-262">Si se invoca para el comando `dotnet new`, muestra las plantillas posibles disponibles para un directorio determinado.</span><span class="sxs-lookup"><span data-stu-id="e0b26-262">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="e0b26-263">Por ejemplo, si el directorio ya contiene un proyecto, no mostrará todas las plantillas del proyecto.</span><span class="sxs-lookup"><span data-stu-id="e0b26-263">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="e0b26-264">El lenguaje de la plantilla que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="e0b26-264">The language of the template to create.</span></span> <span data-ttu-id="e0b26-265">El lenguaje aceptado cambia según la plantilla (vea los valores predeterminados en la sección [argumentos](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="e0b26-265">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="e0b26-266">No es válido para algunas plantillas.</span><span class="sxs-lookup"><span data-stu-id="e0b26-266">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="e0b26-267">Algunos shells interpretan `#` como un carácter especial.</span><span class="sxs-lookup"><span data-stu-id="e0b26-267">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="e0b26-268">En esos casos, debe incluir el valor del parámetro de lenguaje, como `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-268">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="e0b26-269">El nombre de la salida creada.</span><span class="sxs-lookup"><span data-stu-id="e0b26-269">The name for the created output.</span></span> <span data-ttu-id="e0b26-270">Si no se especifica ningún nombre, se usa el nombre del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="e0b26-270">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="e0b26-271">La ubicación para colocar la salida generada.</span><span class="sxs-lookup"><span data-stu-id="e0b26-271">Location to place the generated output.</span></span> <span data-ttu-id="e0b26-272">El valor predeterminado es el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="e0b26-272">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="e0b26-273">Filtra plantillas en función de los tipos disponibles.</span><span class="sxs-lookup"><span data-stu-id="e0b26-273">Filters templates based on available types.</span></span> <span data-ttu-id="e0b26-274">Los valores predefinidos son “project”, “item” y “other”.</span><span class="sxs-lookup"><span data-stu-id="e0b26-274">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="e0b26-275">Desinstala un paquete de plantillas u origen en los parámetros `PATH` o `NUGET_ID` proporcionados.</span><span class="sxs-lookup"><span data-stu-id="e0b26-275">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="e0b26-276">Para desinstalar una plantilla mediante `PATH`, debe usar el nombre completo de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="e0b26-276">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="e0b26-277">Por ejemplo, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* funcionará, pero *./GarciaSoftware.ConsoleTemplate.CSharp* desde la carpeta contenedora no lo hará.</span><span class="sxs-lookup"><span data-stu-id="e0b26-277">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="e0b26-278">Además, no debe incluir una barra diagonal para finalizar el directorio en la ruta de acceso a la plantilla.</span><span class="sxs-lookup"><span data-stu-id="e0b26-278">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="e0b26-279">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="e0b26-279">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="e0b26-280">Muestra todas las plantillas de un tipo de proyecto específico cuando se ejecuta en el contexto del comando `dotnet new` por sí solo.</span><span class="sxs-lookup"><span data-stu-id="e0b26-280">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="e0b26-281">Cuando se ejecuta en el contexto de una plantilla específica, como `dotnet new web -all`, `-all` se interpreta como una marca para forzar la creación.</span><span class="sxs-lookup"><span data-stu-id="e0b26-281">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="e0b26-282">Esto es necesario cuando el directorio de salida ya contiene un proyecto.</span><span class="sxs-lookup"><span data-stu-id="e0b26-282">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="e0b26-283">Imprime la ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="e0b26-283">Prints out help for the command.</span></span> <span data-ttu-id="e0b26-284">Puede invocarse para el propio comando `dotnet new` o para cualquier plantilla, como `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-284">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="e0b26-285">Muestra las plantillas que contienen el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="e0b26-285">Lists templates containing the specified name.</span></span> <span data-ttu-id="e0b26-286">Si se invoca para el comando `dotnet new`, muestra las plantillas posibles disponibles para un directorio determinado.</span><span class="sxs-lookup"><span data-stu-id="e0b26-286">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="e0b26-287">Por ejemplo, si el directorio ya contiene un proyecto, no mostrará todas las plantillas del proyecto.</span><span class="sxs-lookup"><span data-stu-id="e0b26-287">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="e0b26-288">El lenguaje de la plantilla que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="e0b26-288">The language of the template to create.</span></span> <span data-ttu-id="e0b26-289">El lenguaje aceptado cambia según la plantilla (vea los valores predeterminados en la sección [argumentos](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="e0b26-289">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="e0b26-290">No es válido para algunas plantillas.</span><span class="sxs-lookup"><span data-stu-id="e0b26-290">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="e0b26-291">Algunos shells interpretan `#` como un carácter especial.</span><span class="sxs-lookup"><span data-stu-id="e0b26-291">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="e0b26-292">En esos casos, debe incluir el valor del parámetro de lenguaje, como `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-292">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="e0b26-293">El nombre de la salida creada.</span><span class="sxs-lookup"><span data-stu-id="e0b26-293">The name for the created output.</span></span> <span data-ttu-id="e0b26-294">Si no se especifica ningún nombre, se usa el nombre del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="e0b26-294">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="e0b26-295">La ubicación para colocar la salida generada.</span><span class="sxs-lookup"><span data-stu-id="e0b26-295">Location to place the generated output.</span></span> <span data-ttu-id="e0b26-296">El valor predeterminado es el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="e0b26-296">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="e0b26-297">Opciones de plantilla</span><span class="sxs-lookup"><span data-stu-id="e0b26-297">Template options</span></span>

<span data-ttu-id="e0b26-298">Cada plantilla de proyecto puede tener opciones adicionales disponibles.</span><span class="sxs-lookup"><span data-stu-id="e0b26-298">Each project template may have additional options available.</span></span> <span data-ttu-id="e0b26-299">Las plantillas principales tienen las siguientes opciones adicionales:</span><span class="sxs-lookup"><span data-stu-id="e0b26-299">The core templates have the following additional options:</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="e0b26-300">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="e0b26-300">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="e0b26-301">**console, angular, react, reactredux, razorclasslib**</span><span class="sxs-lookup"><span data-stu-id="e0b26-301">**console, angular, react, reactredux, razorclasslib**</span></span>

  <span data-ttu-id="e0b26-302">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="e0b26-302">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e0b26-303">**classlib**</span><span class="sxs-lookup"><span data-stu-id="e0b26-303">**classlib**</span></span>

<span data-ttu-id="e0b26-304">`-f|--framework <FRAMEWORK>`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="e0b26-304">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e0b26-305">Valores: `netcoreapp2.0` para crear una biblioteca de clases de .NET Core o `netstandard2.0` para crear una biblioteca de clases de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="e0b26-305">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="e0b26-306">El valor predeterminado es `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-306">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="e0b26-307">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="e0b26-307">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e0b26-308">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="e0b26-308">**mstest, xunit**</span></span>

<span data-ttu-id="e0b26-309">`-p|--enable-pack`: habilita el empaquetado para el proyecto mediante [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="e0b26-309">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="e0b26-310">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="e0b26-310">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e0b26-311">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="e0b26-311">**globaljson**</span></span>

<span data-ttu-id="e0b26-312">`--sdk-version <VERSION_NUMBER>`: especifica la versión del SDK de .NET Core que se usará con el archivo *global.json*.</span><span class="sxs-lookup"><span data-stu-id="e0b26-312">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="e0b26-313">**web**</span><span class="sxs-lookup"><span data-stu-id="e0b26-313">**web**</span></span>

<span data-ttu-id="e0b26-314">`--exclude-launch-settings`: excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="e0b26-314">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="e0b26-315">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="e0b26-315">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e0b26-316">`--no-https`: el proyecto no requiere HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e0b26-316">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="e0b26-317">Esta opción solo se aplica si no se usan `IndividualAuth` u `OrganizationalAuth`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-317">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="e0b26-318">**webapi**</span><span class="sxs-lookup"><span data-stu-id="e0b26-318">**webapi**</span></span>

<span data-ttu-id="e0b26-319">`-au|--auth <AUTHENTICATION_TYPE>`: el tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="e0b26-319">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="e0b26-320">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="e0b26-320">The possible values are:</span></span>

- <span data-ttu-id="e0b26-321">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="e0b26-321">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="e0b26-322">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="e0b26-322">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="e0b26-323">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="e0b26-323">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="e0b26-324">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="e0b26-324">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="e0b26-325">`--aad-b2c-instance <INSTANCE>`: la instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="e0b26-325">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="e0b26-326">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-326">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="e0b26-327">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-327">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="e0b26-328">`-ssp|--susi-policy-id <ID>`: el id. de inicio de sesión y de directiva de registro de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="e0b26-328">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="e0b26-329">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-329">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="e0b26-330">`--aad-instance <INSTANCE>`: la instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="e0b26-330">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="e0b26-331">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-331">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="e0b26-332">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-332">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="e0b26-333">`--client-id <ID>`: el id. de cliente para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="e0b26-333">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="e0b26-334">Úsela con las autenticaciones `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-334">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="e0b26-335">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-335">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="e0b26-336">`--domain <DOMAIN>`: el dominio para el inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="e0b26-336">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="e0b26-337">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-337">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e0b26-338">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-338">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="e0b26-339">`--tenant-id <ID>`: el id. de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="e0b26-339">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="e0b26-340">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-340">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="e0b26-341">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-341">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="e0b26-342">`-r|--org-read-access`: concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="e0b26-342">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="e0b26-343">Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-343">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="e0b26-344">`--exclude-launch-settings`: excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="e0b26-344">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="e0b26-345">`-uld|--use-local-db`: especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="e0b26-345">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="e0b26-346">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-346">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="e0b26-347">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="e0b26-347">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e0b26-348">`--no-https`: el proyecto no requiere HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e0b26-348">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="e0b26-349">`app.UseHsts` y `app.UseHttpsRedirection` no se agregan a `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-349">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="e0b26-350">Esta opción solo se aplica si no se usan `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-350">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="e0b26-351">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="e0b26-351">**mvc, razor**</span></span>

<span data-ttu-id="e0b26-352">`-au|--auth <AUTHENTICATION_TYPE>`: el tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="e0b26-352">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="e0b26-353">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="e0b26-353">The possible values are:</span></span>

- <span data-ttu-id="e0b26-354">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="e0b26-354">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="e0b26-355">`Individual`: autenticación individual.</span><span class="sxs-lookup"><span data-stu-id="e0b26-355">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="e0b26-356">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="e0b26-356">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="e0b26-357">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="e0b26-357">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="e0b26-358">`MultiOrg`: autenticación organizativa para varios inquilinos.</span><span class="sxs-lookup"><span data-stu-id="e0b26-358">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="e0b26-359">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="e0b26-359">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="e0b26-360">`--aad-b2c-instance <INSTANCE>`: la instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="e0b26-360">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="e0b26-361">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-361">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="e0b26-362">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-362">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="e0b26-363">`-ssp|--susi-policy-id <ID>`: el id. de inicio de sesión y de directiva de registro de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="e0b26-363">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="e0b26-364">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-364">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="e0b26-365">`-rp|--reset-password-policy-id <ID>`: el id. de la directiva de restablecimiento de contraseñas para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="e0b26-365">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="e0b26-366">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-366">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="e0b26-367">`-ep|--edit-profile-policy-id <ID>`: el id. de directiva de edición de perfiles para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="e0b26-367">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="e0b26-368">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-368">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="e0b26-369">`--aad-instance <INSTANCE>`: la instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="e0b26-369">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="e0b26-370">Úsela con las autenticaciones `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-370">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="e0b26-371">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-371">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="e0b26-372">`--client-id <ID>`: el id. de cliente para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="e0b26-372">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="e0b26-373">Úsela con las autenticaciones `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-373">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="e0b26-374">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-374">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="e0b26-375">`--domain <DOMAIN>`: el dominio para el inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="e0b26-375">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="e0b26-376">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-376">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e0b26-377">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-377">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="e0b26-378">`--tenant-id <ID>`: el id. de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="e0b26-378">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="e0b26-379">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-379">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="e0b26-380">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-380">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="e0b26-381">`--callback-path <PATH>`: la ruta de acceso de solicitud de la ruta de acceso de la base de la aplicación del URI de redirección.</span><span class="sxs-lookup"><span data-stu-id="e0b26-381">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="e0b26-382">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-382">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e0b26-383">El valor predeterminado es `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-383">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="e0b26-384">`-r|--org-read-access`: concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="e0b26-384">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="e0b26-385">Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-385">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="e0b26-386">`--exclude-launch-settings`: excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="e0b26-386">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="e0b26-387">`--use-browserlink`: incluye BrowserLink en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="e0b26-387">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="e0b26-388">`-uld|--use-local-db`: especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="e0b26-388">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="e0b26-389">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-389">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="e0b26-390">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="e0b26-390">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e0b26-391">`--no-https`: el proyecto no requiere HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e0b26-391">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="e0b26-392">`app.UseHsts` y `app.UseHttpsRedirection` no se agregan a `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-392">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="e0b26-393">Esta opción solo se aplica si no se usan `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-393">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="e0b26-394">**page**</span><span class="sxs-lookup"><span data-stu-id="e0b26-394">**page**</span></span>

<span data-ttu-id="e0b26-395">`-na|--namespace <NAMESPACE_NAME>`: espacio de nombres para el código generado.</span><span class="sxs-lookup"><span data-stu-id="e0b26-395">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="e0b26-396">El valor predeterminado es `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-396">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="e0b26-397">`-np|--no-pagemodel`: crea la página sin PageModel.</span><span class="sxs-lookup"><span data-stu-id="e0b26-397">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="e0b26-398">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="e0b26-398">**viewimports**</span></span>

<span data-ttu-id="e0b26-399">`-na|--namespace <NAMESPACE_NAME>`: espacio de nombres para el código generado.</span><span class="sxs-lookup"><span data-stu-id="e0b26-399">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="e0b26-400">El valor predeterminado es `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-400">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="e0b26-401">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="e0b26-401">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="e0b26-402">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="e0b26-402">**console, angular, react, reactredux**</span></span>

  <span data-ttu-id="e0b26-403">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="e0b26-403">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e0b26-404">**classlib**</span><span class="sxs-lookup"><span data-stu-id="e0b26-404">**classlib**</span></span>

<span data-ttu-id="e0b26-405">`-f|--framework <FRAMEWORK>`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="e0b26-405">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e0b26-406">Valores: `netcoreapp2.0` para crear una biblioteca de clases de .NET Core o `netstandard2.0` para crear una biblioteca de clases de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="e0b26-406">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="e0b26-407">El valor predeterminado es `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-407">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="e0b26-408">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="e0b26-408">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e0b26-409">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="e0b26-409">**mstest, xunit**</span></span>

<span data-ttu-id="e0b26-410">`-p|--enable-pack`: habilita el empaquetado para el proyecto mediante [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="e0b26-410">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="e0b26-411">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="e0b26-411">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e0b26-412">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="e0b26-412">**globaljson**</span></span>

<span data-ttu-id="e0b26-413">`--sdk-version <VERSION_NUMBER>`: especifica la versión del SDK de .NET Core que se usará con el archivo *global.json*.</span><span class="sxs-lookup"><span data-stu-id="e0b26-413">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="e0b26-414">**web**</span><span class="sxs-lookup"><span data-stu-id="e0b26-414">**web**</span></span>

<span data-ttu-id="e0b26-415">`--use-launch-settings`: incluye *launchSettings.json* en la salida de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="e0b26-415">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="e0b26-416">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="e0b26-416">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e0b26-417">**webapi**</span><span class="sxs-lookup"><span data-stu-id="e0b26-417">**webapi**</span></span>

<span data-ttu-id="e0b26-418">`-au|--auth <AUTHENTICATION_TYPE>`: el tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="e0b26-418">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="e0b26-419">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="e0b26-419">The possible values are:</span></span>

- <span data-ttu-id="e0b26-420">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="e0b26-420">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="e0b26-421">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="e0b26-421">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="e0b26-422">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="e0b26-422">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="e0b26-423">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="e0b26-423">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="e0b26-424">`--aad-b2c-instance <INSTANCE>`: la instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="e0b26-424">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="e0b26-425">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-425">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="e0b26-426">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-426">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="e0b26-427">`-ssp|--susi-policy-id <ID>`: el id. de inicio de sesión y de directiva de registro de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="e0b26-427">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="e0b26-428">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-428">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="e0b26-429">`--aad-instance <INSTANCE>`: la instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="e0b26-429">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="e0b26-430">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-430">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="e0b26-431">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-431">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="e0b26-432">`--client-id <ID>`: el id. de cliente para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="e0b26-432">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="e0b26-433">Úsela con las autenticaciones `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-433">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="e0b26-434">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-434">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="e0b26-435">`--domain <DOMAIN>`: el dominio para el inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="e0b26-435">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="e0b26-436">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-436">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e0b26-437">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-437">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="e0b26-438">`--tenant-id <ID>`: el id. de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="e0b26-438">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="e0b26-439">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-439">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="e0b26-440">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-440">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="e0b26-441">`-r|--org-read-access`: concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="e0b26-441">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="e0b26-442">Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-442">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="e0b26-443">`--use-launch-settings`: incluye *launchSettings.json* en la salida de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="e0b26-443">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="e0b26-444">`-uld|--use-local-db`: especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="e0b26-444">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="e0b26-445">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-445">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="e0b26-446">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="e0b26-446">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e0b26-447">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="e0b26-447">**mvc, razor**</span></span>

<span data-ttu-id="e0b26-448">`-au|--auth <AUTHENTICATION_TYPE>`: el tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="e0b26-448">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="e0b26-449">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="e0b26-449">The possible values are:</span></span>

- <span data-ttu-id="e0b26-450">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="e0b26-450">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="e0b26-451">`Individual`: autenticación individual.</span><span class="sxs-lookup"><span data-stu-id="e0b26-451">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="e0b26-452">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="e0b26-452">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="e0b26-453">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="e0b26-453">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="e0b26-454">`MultiOrg`: autenticación organizativa para varios inquilinos.</span><span class="sxs-lookup"><span data-stu-id="e0b26-454">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="e0b26-455">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="e0b26-455">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="e0b26-456">`--aad-b2c-instance <INSTANCE>`: la instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="e0b26-456">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="e0b26-457">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-457">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="e0b26-458">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-458">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="e0b26-459">`-ssp|--susi-policy-id <ID>`: el id. de inicio de sesión y de directiva de registro de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="e0b26-459">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="e0b26-460">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-460">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="e0b26-461">`-rp|--reset-password-policy-id <ID>`: el id. de la directiva de restablecimiento de contraseñas para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="e0b26-461">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="e0b26-462">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-462">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="e0b26-463">`-ep|--edit-profile-policy-id <ID>`: el id. de directiva de edición de perfiles para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="e0b26-463">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="e0b26-464">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-464">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="e0b26-465">`--aad-instance <INSTANCE>`: la instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="e0b26-465">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="e0b26-466">Úsela con las autenticaciones `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-466">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="e0b26-467">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-467">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="e0b26-468">`--client-id <ID>`: el id. de cliente para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="e0b26-468">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="e0b26-469">Úsela con las autenticaciones `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-469">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="e0b26-470">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-470">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="e0b26-471">`--domain <DOMAIN>`: el dominio para el inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="e0b26-471">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="e0b26-472">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-472">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e0b26-473">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-473">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="e0b26-474">`--tenant-id <ID>`: el id. de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="e0b26-474">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="e0b26-475">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-475">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="e0b26-476">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-476">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="e0b26-477">`--callback-path <PATH>`: la ruta de acceso de solicitud de la ruta de acceso de la base de la aplicación del URI de redirección.</span><span class="sxs-lookup"><span data-stu-id="e0b26-477">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="e0b26-478">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-478">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e0b26-479">El valor predeterminado es `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-479">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="e0b26-480">`-r|--org-read-access`: concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="e0b26-480">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="e0b26-481">Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-481">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="e0b26-482">`--use-launch-settings`: incluye *launchSettings.json* en la salida de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="e0b26-482">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="e0b26-483">`--use-browserlink`: incluye BrowserLink en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="e0b26-483">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="e0b26-484">`-uld|--use-local-db`: especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="e0b26-484">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="e0b26-485">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-485">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="e0b26-486">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="e0b26-486">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e0b26-487">**page**</span><span class="sxs-lookup"><span data-stu-id="e0b26-487">**page**</span></span>

<span data-ttu-id="e0b26-488">`-na|--namespace <NAMESPACE_NAME>`: espacio de nombres para el código generado.</span><span class="sxs-lookup"><span data-stu-id="e0b26-488">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="e0b26-489">El valor predeterminado es `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-489">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="e0b26-490">`-np|--no-pagemodel`: crea la página sin PageModel.</span><span class="sxs-lookup"><span data-stu-id="e0b26-490">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="e0b26-491">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="e0b26-491">**viewimports**</span></span>

<span data-ttu-id="e0b26-492">`-na|--namespace <NAMESPACE_NAME>`: espacio de nombres para el código generado.</span><span class="sxs-lookup"><span data-stu-id="e0b26-492">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="e0b26-493">El valor predeterminado es `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-493">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="e0b26-494">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="e0b26-494">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="e0b26-495">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="e0b26-495">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="e0b26-496">`-f|--framework`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="e0b26-496">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e0b26-497">Valores: `netcoreapp1.0` o `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-497">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="e0b26-498">El valor predeterminado es `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-498">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="e0b26-499">**classlib**</span><span class="sxs-lookup"><span data-stu-id="e0b26-499">**classlib**</span></span>

<span data-ttu-id="e0b26-500">`-f|--framework`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="e0b26-500">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e0b26-501">Valores: `netcoreapp1.0`, `netcoreapp1.1` o de `netstandard1.0` a `netstandard1.6`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-501">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="e0b26-502">El valor predeterminado es `netstandard1.4`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-502">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="e0b26-503">**mvc**</span><span class="sxs-lookup"><span data-stu-id="e0b26-503">**mvc**</span></span>

<span data-ttu-id="e0b26-504">`-f|--framework`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="e0b26-504">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e0b26-505">Valores: `netcoreapp1.0` o `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-505">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="e0b26-506">El valor predeterminado es `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-506">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="e0b26-507">`-au|--auth`: el tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="e0b26-507">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="e0b26-508">Valores: `None` o `Individual`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-508">Values: `None` or `Individual`.</span></span> <span data-ttu-id="e0b26-509">El valor predeterminado es `None`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-509">The default value is `None`.</span></span>

<span data-ttu-id="e0b26-510">`-uld|--use-local-db`: especifica si se va a usar o no LocalDB en lugar de SQLite.</span><span class="sxs-lookup"><span data-stu-id="e0b26-510">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="e0b26-511">Valores: `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-511">Values: `true` or `false`.</span></span> <span data-ttu-id="e0b26-512">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="e0b26-512">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="e0b26-513">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="e0b26-513">Examples</span></span>

<span data-ttu-id="e0b26-514">Creación de un proyecto de aplicación de consola con F# en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="e0b26-514">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang F#`

<span data-ttu-id="e0b26-515">Creación de un proyecto de biblioteca de clases de .NET Standard en el directorio especificado (disponible solo con el SDK de .NET Core 2.0 o versiones posteriores):</span><span class="sxs-lookup"><span data-stu-id="e0b26-515">Create a .NET Standard class library project in the specified directory (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="e0b26-516">Creación de un proyecto de aplicación MVC de ASP.NET Core C# en el directorio actual sin autenticación:</span><span class="sxs-lookup"><span data-stu-id="e0b26-516">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication:</span></span>

`dotnet new mvc -au None`

<span data-ttu-id="e0b26-517">Cree una aplicación de xUnit.</span><span class="sxs-lookup"><span data-stu-id="e0b26-517">Create a new xUnit application:</span></span>

`dotnet new xunit`

<span data-ttu-id="e0b26-518">Enumere todas las plantillas disponibles para MVC:</span><span class="sxs-lookup"><span data-stu-id="e0b26-518">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

<span data-ttu-id="e0b26-519">Instalación de la versión 2.0 de las plantillas Aplicación de página única para ASP.NET Core (opción de comando solo disponible para .NET Core SDK 1.1 y versiones posteriores):</span><span class="sxs-lookup"><span data-stu-id="e0b26-519">Install version 2.0 of the Single Page Application templates for ASP.NET Core (command option available for .NET Core SDK 1.1 and later versions only):</span></span>

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

<span data-ttu-id="e0b26-520">Creación de un archivo *global.json* en el directorio actual que establezca la versión del SDK en 2.0.0 (solo disponible en el SDK de .NET Core 2.0 o versiones posteriores):</span><span class="sxs-lookup"><span data-stu-id="e0b26-520">Create a *global.json* in the current directory setting the SDK version to 2.0.0 (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new globaljson --sdk-version 2.0.0`

## <a name="see-also"></a><span data-ttu-id="e0b26-521">Vea también</span><span class="sxs-lookup"><span data-stu-id="e0b26-521">See also</span></span>

* <span data-ttu-id="e0b26-522">[Custom templates for dotnet new](custom-templates.md) (Plantillas personalizadas para dotnet new)</span><span class="sxs-lookup"><span data-stu-id="e0b26-522">[Custom templates for dotnet new](custom-templates.md)</span></span>  
* [<span data-ttu-id="e0b26-523">Creación de una plantilla personalizada para dotnet new</span><span class="sxs-lookup"><span data-stu-id="e0b26-523">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)  
* [<span data-ttu-id="e0b26-524">Repositorio de GitHub dotnet/dotnet-template-samples</span><span class="sxs-lookup"><span data-stu-id="e0b26-524">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)  
* <span data-ttu-id="e0b26-525">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new) (Plantillas disponibles para dotnet new)</span><span class="sxs-lookup"><span data-stu-id="e0b26-525">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)</span></span>
