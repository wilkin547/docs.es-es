---
title: Comando dotnet new
description: El comando dotnet new crea proyectos de .NET Core basados en la plantilla especificada.
ms.date: 10/24/2018
ms.openlocfilehash: 5177c920fee6fa946d2bf5d96644f26309ed0a99
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54516153"
---
# <a name="dotnet-new"></a><span data-ttu-id="3c379-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="3c379-103">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="3c379-104">nombre</span><span class="sxs-lookup"><span data-stu-id="3c379-104">Name</span></span>

<span data-ttu-id="3c379-105">`dotnet new`: crea un nuevo proyecto, archivo de configuración o solución según la plantilla especificada.</span><span class="sxs-lookup"><span data-stu-id="3c379-105">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="3c379-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="3c379-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="3c379-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="3c379-107">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output]
    [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="3c379-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="3c379-108">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="3c379-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="3c379-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="3c379-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="3c379-110">Description</span></span>

<span data-ttu-id="3c379-111">El comando `dotnet new` proporciona una manera cómoda de inicializar un proyecto .NET Core válido.</span><span class="sxs-lookup"><span data-stu-id="3c379-111">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span>

<span data-ttu-id="3c379-112">El comando llama al [motor de plantillas](https://github.com/dotnet/templating) para crear los artefactos en el disco basándose en las opciones y la plantilla especificadas.</span><span class="sxs-lookup"><span data-stu-id="3c379-112">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="3c379-113">Argumentos</span><span class="sxs-lookup"><span data-stu-id="3c379-113">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="3c379-114">La plantilla de la que se va a crear una instancia cuando se invoca el comando.</span><span class="sxs-lookup"><span data-stu-id="3c379-114">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="3c379-115">Cada plantilla puede tener opciones específicas que puede pasar.</span><span class="sxs-lookup"><span data-stu-id="3c379-115">Each template might have specific options you can pass.</span></span> <span data-ttu-id="3c379-116">Para obtener más información, vea [Opciones de plantilla](#template-options).</span><span class="sxs-lookup"><span data-stu-id="3c379-116">For more information, see [Template options](#template-options).</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="3c379-117">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="3c379-117">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="3c379-118">El comando contiene una lista predeterminada de plantillas.</span><span class="sxs-lookup"><span data-stu-id="3c379-118">The command contains a default list of templates.</span></span> <span data-ttu-id="3c379-119">Use `dotnet new -l` para obtener una lista de las plantillas disponibles.</span><span class="sxs-lookup"><span data-stu-id="3c379-119">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="3c379-120">En la tabla siguiente se muestran las plantillas que vienen preinstaladas con el SDK de .NET Core 2.1.300.</span><span class="sxs-lookup"><span data-stu-id="3c379-120">The following table shows the templates that come pre-installed with the .NET Core SDK 2.1.300.</span></span> <span data-ttu-id="3c379-121">El lenguaje predeterminado de la plantilla se muestra entre corchetes.</span><span class="sxs-lookup"><span data-stu-id="3c379-121">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="3c379-122">Descripción de plantilla</span><span class="sxs-lookup"><span data-stu-id="3c379-122">Template description</span></span>                          | <span data-ttu-id="3c379-123">Nombre de plantilla</span><span class="sxs-lookup"><span data-stu-id="3c379-123">Template name</span></span>    | <span data-ttu-id="3c379-124">Lenguajes</span><span class="sxs-lookup"><span data-stu-id="3c379-124">Languages</span></span>     |
|----------------------------------------------|------------------|---------------|
| <span data-ttu-id="3c379-125">Aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="3c379-125">Console application</span></span>                          | `console`        | <span data-ttu-id="3c379-126">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="3c379-126">[C#], F#, VB</span></span>  |
| <span data-ttu-id="3c379-127">Biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="3c379-127">Class library</span></span>                                | `classlib`       | <span data-ttu-id="3c379-128">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="3c379-128">[C#], F#, VB</span></span>  |
| <span data-ttu-id="3c379-129">Proyecto de prueba unitaria</span><span class="sxs-lookup"><span data-stu-id="3c379-129">Unit test project</span></span>                            | `mstest`         | <span data-ttu-id="3c379-130">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="3c379-130">[C#], F#, VB</span></span>  |
| <span data-ttu-id="3c379-131">Proyecto de prueba xUnit</span><span class="sxs-lookup"><span data-stu-id="3c379-131">xUnit test project</span></span>                           | `xunit`          | <span data-ttu-id="3c379-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="3c379-132">[C#], F#, VB</span></span>  |
| <span data-ttu-id="3c379-133">Proyecto de prueba de NUnit</span><span class="sxs-lookup"><span data-stu-id="3c379-133">NUnit test project</span></span>                           | `nunit`          | <span data-ttu-id="3c379-134">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="3c379-134">[C#], F#, VB</span></span>  |
| <span data-ttu-id="3c379-135">Página de Razor</span><span class="sxs-lookup"><span data-stu-id="3c379-135">Razor page</span></span>                                   | `page`           | <span data-ttu-id="3c379-136">[C#]</span><span class="sxs-lookup"><span data-stu-id="3c379-136">[C#]</span></span>          |
| <span data-ttu-id="3c379-137">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="3c379-137">MVC ViewImports</span></span>                              | `viewimports`    | <span data-ttu-id="3c379-138">[C#]</span><span class="sxs-lookup"><span data-stu-id="3c379-138">[C#]</span></span>          |
| <span data-ttu-id="3c379-139">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="3c379-139">MVC ViewStart</span></span>                                | `viewstart`      | <span data-ttu-id="3c379-140">[C#]</span><span class="sxs-lookup"><span data-stu-id="3c379-140">[C#]</span></span>          |
| <span data-ttu-id="3c379-141">Vacío de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="3c379-141">ASP.NET Core empty</span></span>                           | `web`            | <span data-ttu-id="3c379-142">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="3c379-142">[C#], F#</span></span>      |
| <span data-ttu-id="3c379-143">Aplicación web de ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="3c379-143">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`            | <span data-ttu-id="3c379-144">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="3c379-144">[C#], F#</span></span>      |
| <span data-ttu-id="3c379-145">Aplicación web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="3c379-145">ASP.NET Core Web App</span></span>                         | <span data-ttu-id="3c379-146">`razor`, `webapp`</span><span class="sxs-lookup"><span data-stu-id="3c379-146">`razor`, `webapp`</span></span>| <span data-ttu-id="3c379-147">[C#]</span><span class="sxs-lookup"><span data-stu-id="3c379-147">[C#]</span></span>          |
| <span data-ttu-id="3c379-148">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="3c379-148">ASP.NET Core with Angular</span></span>                    | `angular`        | <span data-ttu-id="3c379-149">[C#]</span><span class="sxs-lookup"><span data-stu-id="3c379-149">[C#]</span></span>          |
| <span data-ttu-id="3c379-150">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="3c379-150">ASP.NET Core with React.js</span></span>                   | `react`          | <span data-ttu-id="3c379-151">[C#]</span><span class="sxs-lookup"><span data-stu-id="3c379-151">[C#]</span></span>          |
| <span data-ttu-id="3c379-152">ASP.NET Core con React.js y Redux</span><span class="sxs-lookup"><span data-stu-id="3c379-152">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`     | <span data-ttu-id="3c379-153">[C#]</span><span class="sxs-lookup"><span data-stu-id="3c379-153">[C#]</span></span>          |
| <span data-ttu-id="3c379-154">API web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="3c379-154">ASP.NET Core Web API</span></span>                         | `webapi`         | <span data-ttu-id="3c379-155">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="3c379-155">[C#], F#</span></span>      |
| <span data-ttu-id="3c379-156">Biblioteca de clases de Razor</span><span class="sxs-lookup"><span data-stu-id="3c379-156">Razor class library</span></span>                          | `razorclasslib`  | <span data-ttu-id="3c379-157">[C#]</span><span class="sxs-lookup"><span data-stu-id="3c379-157">[C#]</span></span>          |
| <span data-ttu-id="3c379-158">archivo global.json</span><span class="sxs-lookup"><span data-stu-id="3c379-158">global.json file</span></span>                             | `globaljson`     |               |
| <span data-ttu-id="3c379-159">Configuración de NuGet</span><span class="sxs-lookup"><span data-stu-id="3c379-159">NuGet config</span></span>                                 | `nugetconfig`    |               |
| <span data-ttu-id="3c379-160">Configuración de la Web</span><span class="sxs-lookup"><span data-stu-id="3c379-160">Web config</span></span>                                   | `webconfig`      |               |
| <span data-ttu-id="3c379-161">Archivo de solución</span><span class="sxs-lookup"><span data-stu-id="3c379-161">Solution file</span></span>                                | `sln`            |               |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="3c379-162">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="3c379-162">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="3c379-163">El comando contiene una lista predeterminada de plantillas.</span><span class="sxs-lookup"><span data-stu-id="3c379-163">The command contains a default list of templates.</span></span> <span data-ttu-id="3c379-164">Use `dotnet new -l` para obtener una lista de las plantillas disponibles.</span><span class="sxs-lookup"><span data-stu-id="3c379-164">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="3c379-165">En la tabla siguiente se muestran las plantillas que vienen preinstaladas con el SDK de .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="3c379-165">The following table shows the templates that come pre-installed with the .NET Core SDK 2.0.</span></span> <span data-ttu-id="3c379-166">El lenguaje predeterminado de la plantilla se muestra entre corchetes.</span><span class="sxs-lookup"><span data-stu-id="3c379-166">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="3c379-167">Descripción de plantilla</span><span class="sxs-lookup"><span data-stu-id="3c379-167">Template description</span></span>                          | <span data-ttu-id="3c379-168">Nombre de plantilla</span><span class="sxs-lookup"><span data-stu-id="3c379-168">Template name</span></span> | <span data-ttu-id="3c379-169">Lenguajes</span><span class="sxs-lookup"><span data-stu-id="3c379-169">Languages</span></span>     |
|----------------------------------------------|---------------|---------------|
| <span data-ttu-id="3c379-170">Aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="3c379-170">Console application</span></span>                          | `console`     | <span data-ttu-id="3c379-171">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="3c379-171">[C#], F#, VB</span></span>  |
| <span data-ttu-id="3c379-172">Biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="3c379-172">Class library</span></span>                                | `classlib`    | <span data-ttu-id="3c379-173">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="3c379-173">[C#], F#, VB</span></span>  |
| <span data-ttu-id="3c379-174">Proyecto de prueba unitaria</span><span class="sxs-lookup"><span data-stu-id="3c379-174">Unit test project</span></span>                            | `mstest`      | <span data-ttu-id="3c379-175">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="3c379-175">[C#], F#, VB</span></span>  |
| <span data-ttu-id="3c379-176">Proyecto de prueba xUnit</span><span class="sxs-lookup"><span data-stu-id="3c379-176">xUnit test project</span></span>                           | `xunit`       | <span data-ttu-id="3c379-177">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="3c379-177">[C#], F#, VB</span></span>  |
| <span data-ttu-id="3c379-178">Vacío de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="3c379-178">ASP.NET Core empty</span></span>                           | `web`         | <span data-ttu-id="3c379-179">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="3c379-179">[C#], F#</span></span>      |
| <span data-ttu-id="3c379-180">Aplicación web de ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="3c379-180">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="3c379-181">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="3c379-181">[C#], F#</span></span>      |
| <span data-ttu-id="3c379-182">Aplicación web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="3c379-182">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="3c379-183">[C#]</span><span class="sxs-lookup"><span data-stu-id="3c379-183">[C#]</span></span>          |
| <span data-ttu-id="3c379-184">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="3c379-184">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="3c379-185">[C#]</span><span class="sxs-lookup"><span data-stu-id="3c379-185">[C#]</span></span>          |
| <span data-ttu-id="3c379-186">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="3c379-186">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="3c379-187">[C#]</span><span class="sxs-lookup"><span data-stu-id="3c379-187">[C#]</span></span>          |
| <span data-ttu-id="3c379-188">ASP.NET Core con React.js y Redux</span><span class="sxs-lookup"><span data-stu-id="3c379-188">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="3c379-189">[C#]</span><span class="sxs-lookup"><span data-stu-id="3c379-189">[C#]</span></span>          |
| <span data-ttu-id="3c379-190">API web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="3c379-190">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="3c379-191">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="3c379-191">[C#], F#</span></span>      |
| <span data-ttu-id="3c379-192">archivo global.json</span><span class="sxs-lookup"><span data-stu-id="3c379-192">global.json file</span></span>                             | `globaljson`  |               |
| <span data-ttu-id="3c379-193">Configuración de NuGet</span><span class="sxs-lookup"><span data-stu-id="3c379-193">NuGet config</span></span>                                 | `nugetconfig` |               |
| <span data-ttu-id="3c379-194">Configuración de la Web</span><span class="sxs-lookup"><span data-stu-id="3c379-194">Web config</span></span>                                   | `webconfig`   |               |
| <span data-ttu-id="3c379-195">Archivo de solución</span><span class="sxs-lookup"><span data-stu-id="3c379-195">Solution file</span></span>                                | `sln`         |               |
| <span data-ttu-id="3c379-196">Página de Razor</span><span class="sxs-lookup"><span data-stu-id="3c379-196">Razor page</span></span>                                   | `page`        |               |
| <span data-ttu-id="3c379-197">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="3c379-197">MVC ViewImports</span></span>                              | `viewimports` |               |
| <span data-ttu-id="3c379-198">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="3c379-198">MVC ViewStart</span></span>                                | `viewstart`   |               |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="3c379-199">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="3c379-199">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="3c379-200">El comando contiene una lista predeterminada de plantillas.</span><span class="sxs-lookup"><span data-stu-id="3c379-200">The command contains a default list of templates.</span></span> <span data-ttu-id="3c379-201">Use `dotnet new -all` para obtener una lista de las plantillas disponibles.</span><span class="sxs-lookup"><span data-stu-id="3c379-201">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="3c379-202">En la tabla siguiente se muestran las plantillas que vienen preinstaladas con el SDK de .NET 1.x.</span><span class="sxs-lookup"><span data-stu-id="3c379-202">The following table shows the templates that come pre-installed with the .NET Core SDK 1.x.</span></span> <span data-ttu-id="3c379-203">El lenguaje predeterminado de la plantilla se muestra entre corchetes.</span><span class="sxs-lookup"><span data-stu-id="3c379-203">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="3c379-204">Descripción de plantilla</span><span class="sxs-lookup"><span data-stu-id="3c379-204">Template description</span></span>  | <span data-ttu-id="3c379-205">Nombre de plantilla</span><span class="sxs-lookup"><span data-stu-id="3c379-205">Template name</span></span> | <span data-ttu-id="3c379-206">Lenguajes</span><span class="sxs-lookup"><span data-stu-id="3c379-206">Languages</span></span> |
|----------------------|---------------|-----------|
| <span data-ttu-id="3c379-207">Aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="3c379-207">Console application</span></span>  | `console`     | <span data-ttu-id="3c379-208">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="3c379-208">[C#], F#</span></span>  |
| <span data-ttu-id="3c379-209">Biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="3c379-209">Class library</span></span>        | `classlib`    | <span data-ttu-id="3c379-210">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="3c379-210">[C#], F#</span></span>  |
| <span data-ttu-id="3c379-211">Proyecto de prueba unitaria</span><span class="sxs-lookup"><span data-stu-id="3c379-211">Unit test project</span></span>    | `mstest`      | <span data-ttu-id="3c379-212">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="3c379-212">[C#], F#</span></span>  |
| <span data-ttu-id="3c379-213">Proyecto de prueba xUnit</span><span class="sxs-lookup"><span data-stu-id="3c379-213">xUnit test project</span></span>   | `xunit`       | <span data-ttu-id="3c379-214">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="3c379-214">[C#], F#</span></span>  |
| <span data-ttu-id="3c379-215">Vacío de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="3c379-215">ASP.NET Core empty</span></span>   | `web`         | <span data-ttu-id="3c379-216">[C#]</span><span class="sxs-lookup"><span data-stu-id="3c379-216">[C#]</span></span>      |
| <span data-ttu-id="3c379-217">Aplicación web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="3c379-217">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="3c379-218">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="3c379-218">[C#], F#</span></span>  |
| <span data-ttu-id="3c379-219">API web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="3c379-219">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="3c379-220">[C#]</span><span class="sxs-lookup"><span data-stu-id="3c379-220">[C#]</span></span>      |
| <span data-ttu-id="3c379-221">Configuración de NuGet</span><span class="sxs-lookup"><span data-stu-id="3c379-221">NuGet config</span></span>         | `nugetconfig` |           |
| <span data-ttu-id="3c379-222">Configuración de la Web</span><span class="sxs-lookup"><span data-stu-id="3c379-222">Web config</span></span>           | `webconfig`   |           |
| <span data-ttu-id="3c379-223">Archivo de solución</span><span class="sxs-lookup"><span data-stu-id="3c379-223">Solution file</span></span>        | `sln`         |           |

---

## <a name="options"></a><span data-ttu-id="3c379-224">Opciones</span><span class="sxs-lookup"><span data-stu-id="3c379-224">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="3c379-225">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="3c379-225">.NET Core 2.1</span></span>](#tab/netcore21)

`--force`

<span data-ttu-id="3c379-226">Fuerza la generación de contenido incluso aunque se vayan a cambiar los archivos existentes.</span><span class="sxs-lookup"><span data-stu-id="3c379-226">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="3c379-227">Esto es necesario cuando el directorio de salida ya contiene un proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c379-227">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="3c379-228">Imprime la ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="3c379-228">Prints out help for the command.</span></span> <span data-ttu-id="3c379-229">Puede invocarse para el propio comando `dotnet new` o para cualquier plantilla, como `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="3c379-229">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="3c379-230">Instala un paquete de plantillas u origen desde los parámetros `PATH` o `NUGET_ID` proporcionados.</span><span class="sxs-lookup"><span data-stu-id="3c379-230">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="3c379-231">Si quiere instalar una versión preliminar de un paquete de plantilla, tendrá que especificar la versión en el formato de `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="3c379-231">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="3c379-232">De manera predeterminada, `dotnet new` pasa \* para la versión, que representa la última versión estable del paquete.</span><span class="sxs-lookup"><span data-stu-id="3c379-232">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="3c379-233">Vea un ejemplo en la sección [Ejemplos](#examples).</span><span class="sxs-lookup"><span data-stu-id="3c379-233">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="3c379-234">Para obtener información sobre cómo crear plantillas personalizadas, consulte [Custom templates for dotnet new](custom-templates.md) (Plantillas personalizadas para dotnet new).</span><span class="sxs-lookup"><span data-stu-id="3c379-234">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="3c379-235">Muestra las plantillas que contienen el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="3c379-235">Lists templates containing the specified name.</span></span> <span data-ttu-id="3c379-236">Si se invoca para el comando `dotnet new`, muestra las plantillas posibles disponibles para un directorio determinado.</span><span class="sxs-lookup"><span data-stu-id="3c379-236">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="3c379-237">Por ejemplo, si el directorio ya contiene un proyecto, no mostrará todas las plantillas del proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c379-237">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="3c379-238">El lenguaje de la plantilla que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="3c379-238">The language of the template to create.</span></span> <span data-ttu-id="3c379-239">El lenguaje aceptado cambia según la plantilla (vea los valores predeterminados en la sección [argumentos](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="3c379-239">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="3c379-240">No es válido para algunas plantillas.</span><span class="sxs-lookup"><span data-stu-id="3c379-240">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="3c379-241">Algunos shells interpretan `#` como un carácter especial.</span><span class="sxs-lookup"><span data-stu-id="3c379-241">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="3c379-242">En esos casos, debe incluir el valor del parámetro de lenguaje, como `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="3c379-242">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="3c379-243">El nombre de la salida creada.</span><span class="sxs-lookup"><span data-stu-id="3c379-243">The name for the created output.</span></span> <span data-ttu-id="3c379-244">Si no se especifica ningún nombre, se usa el nombre del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="3c379-244">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="3c379-245">Especifica un origen de NuGet para usarlo durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="3c379-245">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="3c379-246">La ubicación para colocar la salida generada.</span><span class="sxs-lookup"><span data-stu-id="3c379-246">Location to place the generated output.</span></span> <span data-ttu-id="3c379-247">El valor predeterminado es el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="3c379-247">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="3c379-248">Filtra plantillas en función de los tipos disponibles.</span><span class="sxs-lookup"><span data-stu-id="3c379-248">Filters templates based on available types.</span></span> <span data-ttu-id="3c379-249">Los valores predefinidos son “project”, “item” y “other”.</span><span class="sxs-lookup"><span data-stu-id="3c379-249">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="3c379-250">Desinstala un paquete de plantillas u origen en los parámetros `PATH` o `NUGET_ID` proporcionados.</span><span class="sxs-lookup"><span data-stu-id="3c379-250">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="3c379-251">Para desinstalar una plantilla mediante `PATH`, debe usar el nombre completo de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="3c379-251">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="3c379-252">Por ejemplo, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* funcionará, pero *./GarciaSoftware.ConsoleTemplate.CSharp* desde la carpeta contenedora no lo hará.</span><span class="sxs-lookup"><span data-stu-id="3c379-252">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="3c379-253">Además, no debe incluir una barra diagonal para finalizar el directorio en la ruta de acceso a la plantilla.</span><span class="sxs-lookup"><span data-stu-id="3c379-253">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="3c379-254">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="3c379-254">.NET Core 2.0</span></span>](#tab/netcore20)

`--force`

<span data-ttu-id="3c379-255">Fuerza la generación de contenido incluso aunque se vayan a cambiar los archivos existentes.</span><span class="sxs-lookup"><span data-stu-id="3c379-255">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="3c379-256">Esto es necesario cuando el directorio de salida ya contiene un proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c379-256">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="3c379-257">Imprime la ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="3c379-257">Prints out help for the command.</span></span> <span data-ttu-id="3c379-258">Puede invocarse para el propio comando `dotnet new` o para cualquier plantilla, como `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="3c379-258">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="3c379-259">Instala un paquete de plantillas u origen desde los parámetros `PATH` o `NUGET_ID` proporcionados.</span><span class="sxs-lookup"><span data-stu-id="3c379-259">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="3c379-260">Si quiere instalar una versión preliminar de un paquete de plantilla, tendrá que especificar la versión en el formato de `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="3c379-260">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="3c379-261">De manera predeterminada, `dotnet new` pasa \* para la versión, que representa la última versión estable del paquete.</span><span class="sxs-lookup"><span data-stu-id="3c379-261">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="3c379-262">Vea un ejemplo en la sección [Ejemplos](#examples).</span><span class="sxs-lookup"><span data-stu-id="3c379-262">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="3c379-263">Para obtener información sobre cómo crear plantillas personalizadas, consulte [Custom templates for dotnet new](custom-templates.md) (Plantillas personalizadas para dotnet new).</span><span class="sxs-lookup"><span data-stu-id="3c379-263">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="3c379-264">Muestra las plantillas que contienen el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="3c379-264">Lists templates containing the specified name.</span></span> <span data-ttu-id="3c379-265">Si se invoca para el comando `dotnet new`, muestra las plantillas posibles disponibles para un directorio determinado.</span><span class="sxs-lookup"><span data-stu-id="3c379-265">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="3c379-266">Por ejemplo, si el directorio ya contiene un proyecto, no mostrará todas las plantillas del proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c379-266">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="3c379-267">El lenguaje de la plantilla que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="3c379-267">The language of the template to create.</span></span> <span data-ttu-id="3c379-268">El lenguaje aceptado cambia según la plantilla (vea los valores predeterminados en la sección [argumentos](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="3c379-268">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="3c379-269">No es válido para algunas plantillas.</span><span class="sxs-lookup"><span data-stu-id="3c379-269">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="3c379-270">Algunos shells interpretan `#` como un carácter especial.</span><span class="sxs-lookup"><span data-stu-id="3c379-270">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="3c379-271">En esos casos, debe incluir el valor del parámetro de lenguaje, como `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="3c379-271">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="3c379-272">El nombre de la salida creada.</span><span class="sxs-lookup"><span data-stu-id="3c379-272">The name for the created output.</span></span> <span data-ttu-id="3c379-273">Si no se especifica ningún nombre, se usa el nombre del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="3c379-273">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="3c379-274">La ubicación para colocar la salida generada.</span><span class="sxs-lookup"><span data-stu-id="3c379-274">Location to place the generated output.</span></span> <span data-ttu-id="3c379-275">El valor predeterminado es el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="3c379-275">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="3c379-276">Filtra plantillas en función de los tipos disponibles.</span><span class="sxs-lookup"><span data-stu-id="3c379-276">Filters templates based on available types.</span></span> <span data-ttu-id="3c379-277">Los valores predefinidos son “project”, “item” y “other”.</span><span class="sxs-lookup"><span data-stu-id="3c379-277">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="3c379-278">Desinstala un paquete de plantillas u origen en los parámetros `PATH` o `NUGET_ID` proporcionados.</span><span class="sxs-lookup"><span data-stu-id="3c379-278">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="3c379-279">Para desinstalar una plantilla mediante un origen `PATH`, debe usar el nombre completo de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="3c379-279">To uninstall a template using a source `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="3c379-280">Por ejemplo, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* funcionará, pero *./GarciaSoftware.ConsoleTemplate.CSharp* desde la carpeta contenedora no lo hará.</span><span class="sxs-lookup"><span data-stu-id="3c379-280">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span> <span data-ttu-id="3c379-281">Además, no debe incluir una barra diagonal para finalizar el directorio en la ruta de acceso a la plantilla.</span><span class="sxs-lookup"><span data-stu-id="3c379-281">Additionally, do not include a final terminating directory slash on your template path.</span></span>
> 
> <span data-ttu-id="3c379-282">Si no puede determinar el argumento `PATH` o `NUGET_ID` necesario para desinstalar una plantilla, la ejecución de `dotnet new --uninstall` sin un argumento enumerará todas las plantillas instaladas y el argumento requerido para desinstalarlas.</span><span class="sxs-lookup"><span data-stu-id="3c379-282">If you are unable to determine the `PATH` or `NUGET_ID` argument needed to uninstall a template, running `dotnet new --uninstall` without an argument will list all installed templates and the argument required to uninstall them.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="3c379-283">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="3c379-283">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="3c379-284">Muestra todas las plantillas de un tipo de proyecto específico cuando se ejecuta en el contexto del comando `dotnet new` por sí solo.</span><span class="sxs-lookup"><span data-stu-id="3c379-284">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="3c379-285">Cuando se ejecuta en el contexto de una plantilla específica, como `dotnet new web -all`, `-all` se interpreta como una marca para forzar la creación.</span><span class="sxs-lookup"><span data-stu-id="3c379-285">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="3c379-286">Esto es necesario cuando el directorio de salida ya contiene un proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c379-286">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="3c379-287">Imprime la ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="3c379-287">Prints out help for the command.</span></span> <span data-ttu-id="3c379-288">Puede invocarse para el propio comando `dotnet new` o para cualquier plantilla, como `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="3c379-288">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="3c379-289">Muestra las plantillas que contienen el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="3c379-289">Lists templates containing the specified name.</span></span> <span data-ttu-id="3c379-290">Si se invoca para el comando `dotnet new`, muestra las plantillas posibles disponibles para un directorio determinado.</span><span class="sxs-lookup"><span data-stu-id="3c379-290">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="3c379-291">Por ejemplo, si el directorio ya contiene un proyecto, no mostrará todas las plantillas del proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c379-291">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="3c379-292">El lenguaje de la plantilla que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="3c379-292">The language of the template to create.</span></span> <span data-ttu-id="3c379-293">El lenguaje aceptado cambia según la plantilla (vea los valores predeterminados en la sección [argumentos](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="3c379-293">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="3c379-294">No es válido para algunas plantillas.</span><span class="sxs-lookup"><span data-stu-id="3c379-294">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="3c379-295">Algunos shells interpretan `#` como un carácter especial.</span><span class="sxs-lookup"><span data-stu-id="3c379-295">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="3c379-296">En esos casos, debe incluir el valor del parámetro de lenguaje, como `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="3c379-296">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="3c379-297">El nombre de la salida creada.</span><span class="sxs-lookup"><span data-stu-id="3c379-297">The name for the created output.</span></span> <span data-ttu-id="3c379-298">Si no se especifica ningún nombre, se usa el nombre del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="3c379-298">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="3c379-299">La ubicación para colocar la salida generada.</span><span class="sxs-lookup"><span data-stu-id="3c379-299">Location to place the generated output.</span></span> <span data-ttu-id="3c379-300">El valor predeterminado es el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="3c379-300">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="3c379-301">Opciones de plantilla</span><span class="sxs-lookup"><span data-stu-id="3c379-301">Template options</span></span>

<span data-ttu-id="3c379-302">Cada plantilla de proyecto puede tener opciones adicionales disponibles.</span><span class="sxs-lookup"><span data-stu-id="3c379-302">Each project template may have additional options available.</span></span> <span data-ttu-id="3c379-303">Las plantillas principales tienen las siguientes opciones adicionales:</span><span class="sxs-lookup"><span data-stu-id="3c379-303">The core templates have the following additional options:</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="3c379-304">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="3c379-304">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="3c379-305">**console, angular, react, reactredux, razorclasslib**</span><span class="sxs-lookup"><span data-stu-id="3c379-305">**console, angular, react, reactredux, razorclasslib**</span></span>

  <span data-ttu-id="3c379-306">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c379-306">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="3c379-307">**classlib**</span><span class="sxs-lookup"><span data-stu-id="3c379-307">**classlib**</span></span>

<span data-ttu-id="3c379-308">`-f|--framework <FRAMEWORK>`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="3c379-308">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="3c379-309">Valores: `netcoreapp2.0` para crear una biblioteca de clases de .NET Core o `netstandard2.0` para crear una biblioteca de clases de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="3c379-309">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="3c379-310">El valor predeterminado es `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="3c379-310">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="3c379-311">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c379-311">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="3c379-312">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="3c379-312">**mstest, xunit**</span></span>

<span data-ttu-id="3c379-313">`-p|--enable-pack`: habilita el empaquetado para el proyecto mediante [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="3c379-313">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="3c379-314">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c379-314">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="3c379-315">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="3c379-315">**globaljson**</span></span>

<span data-ttu-id="3c379-316">`--sdk-version <VERSION_NUMBER>`: especifica la versión del SDK de .NET Core que se usará con el archivo *global.json*.</span><span class="sxs-lookup"><span data-stu-id="3c379-316">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="3c379-317">**web**</span><span class="sxs-lookup"><span data-stu-id="3c379-317">**web**</span></span>

<span data-ttu-id="3c379-318">`--exclude-launch-settings`: excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="3c379-318">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="3c379-319">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c379-319">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="3c379-320">`--no-https`: el proyecto no requiere HTTPS.</span><span class="sxs-lookup"><span data-stu-id="3c379-320">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="3c379-321">Esta opción solo se aplica si no se usan `IndividualAuth` u `OrganizationalAuth`.</span><span class="sxs-lookup"><span data-stu-id="3c379-321">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="3c379-322">**webapi**</span><span class="sxs-lookup"><span data-stu-id="3c379-322">**webapi**</span></span>

<span data-ttu-id="3c379-323">`-au|--auth <AUTHENTICATION_TYPE>`: el tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="3c379-323">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="3c379-324">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="3c379-324">The possible values are:</span></span>

- <span data-ttu-id="3c379-325">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="3c379-325">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="3c379-326">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="3c379-326">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="3c379-327">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="3c379-327">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="3c379-328">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="3c379-328">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="3c379-329">`--aad-b2c-instance <INSTANCE>`: la instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="3c379-329">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="3c379-330">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="3c379-330">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="3c379-331">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="3c379-331">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="3c379-332">`-ssp|--susi-policy-id <ID>`: el id. de inicio de sesión y de directiva de registro de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c379-332">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="3c379-333">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="3c379-333">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="3c379-334">`--aad-instance <INSTANCE>`: la instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="3c379-334">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="3c379-335">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="3c379-335">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="3c379-336">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="3c379-336">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="3c379-337">`--client-id <ID>`: el id. de cliente para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c379-337">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="3c379-338">Úsela con las autenticaciones `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="3c379-338">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="3c379-339">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="3c379-339">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="3c379-340">`--domain <DOMAIN>`: el dominio para el inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="3c379-340">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="3c379-341">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="3c379-341">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="3c379-342">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="3c379-342">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="3c379-343">`--tenant-id <ID>`: el id. de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="3c379-343">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="3c379-344">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="3c379-344">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="3c379-345">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="3c379-345">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="3c379-346">`-r|--org-read-access`: concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="3c379-346">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="3c379-347">Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="3c379-347">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="3c379-348">`--exclude-launch-settings`: excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="3c379-348">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="3c379-349">`-uld|--use-local-db`: especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="3c379-349">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="3c379-350">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="3c379-350">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="3c379-351">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c379-351">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="3c379-352">`--no-https`: el proyecto no requiere HTTPS.</span><span class="sxs-lookup"><span data-stu-id="3c379-352">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="3c379-353">`app.UseHsts` y `app.UseHttpsRedirection` no se agregan a `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="3c379-353">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="3c379-354">Esta opción solo se aplica si no se usan `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="3c379-354">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="3c379-355">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="3c379-355">**mvc, razor**</span></span>

<span data-ttu-id="3c379-356">`-au|--auth <AUTHENTICATION_TYPE>`: el tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="3c379-356">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="3c379-357">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="3c379-357">The possible values are:</span></span>

- <span data-ttu-id="3c379-358">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="3c379-358">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="3c379-359">`Individual`: autenticación individual.</span><span class="sxs-lookup"><span data-stu-id="3c379-359">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="3c379-360">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="3c379-360">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="3c379-361">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="3c379-361">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="3c379-362">`MultiOrg`: autenticación organizativa para varios inquilinos.</span><span class="sxs-lookup"><span data-stu-id="3c379-362">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="3c379-363">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="3c379-363">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="3c379-364">`--aad-b2c-instance <INSTANCE>`: la instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="3c379-364">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="3c379-365">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="3c379-365">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="3c379-366">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="3c379-366">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="3c379-367">`-ssp|--susi-policy-id <ID>`: el id. de inicio de sesión y de directiva de registro de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c379-367">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="3c379-368">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="3c379-368">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="3c379-369">`-rp|--reset-password-policy-id <ID>`: el id. de la directiva de restablecimiento de contraseñas para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c379-369">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="3c379-370">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="3c379-370">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="3c379-371">`-ep|--edit-profile-policy-id <ID>`: el id. de directiva de edición de perfiles para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c379-371">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="3c379-372">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="3c379-372">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="3c379-373">`--aad-instance <INSTANCE>`: la instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="3c379-373">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="3c379-374">Úsela con las autenticaciones `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="3c379-374">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="3c379-375">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="3c379-375">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="3c379-376">`--client-id <ID>`: el id. de cliente para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c379-376">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="3c379-377">Úsela con las autenticaciones `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="3c379-377">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="3c379-378">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="3c379-378">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="3c379-379">`--domain <DOMAIN>`: el dominio para el inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="3c379-379">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="3c379-380">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="3c379-380">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="3c379-381">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="3c379-381">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="3c379-382">`--tenant-id <ID>`: el id. de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="3c379-382">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="3c379-383">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="3c379-383">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="3c379-384">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="3c379-384">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="3c379-385">`--callback-path <PATH>`: la ruta de acceso de solicitud de la ruta de acceso de la base de la aplicación del URI de redirección.</span><span class="sxs-lookup"><span data-stu-id="3c379-385">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="3c379-386">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="3c379-386">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="3c379-387">El valor predeterminado es `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="3c379-387">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="3c379-388">`-r|--org-read-access`: concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="3c379-388">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="3c379-389">Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="3c379-389">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="3c379-390">`--exclude-launch-settings`: excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="3c379-390">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="3c379-391">`--use-browserlink`: incluye BrowserLink en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c379-391">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="3c379-392">`-uld|--use-local-db`: especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="3c379-392">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="3c379-393">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="3c379-393">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="3c379-394">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c379-394">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="3c379-395">`--no-https`: el proyecto no requiere HTTPS.</span><span class="sxs-lookup"><span data-stu-id="3c379-395">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="3c379-396">`app.UseHsts` y `app.UseHttpsRedirection` no se agregan a `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="3c379-396">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="3c379-397">Esta opción solo se aplica si no se usan `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="3c379-397">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="3c379-398">**page**</span><span class="sxs-lookup"><span data-stu-id="3c379-398">**page**</span></span>

<span data-ttu-id="3c379-399">`-na|--namespace <NAMESPACE_NAME>`: espacio de nombres para el código generado.</span><span class="sxs-lookup"><span data-stu-id="3c379-399">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="3c379-400">El valor predeterminado es `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="3c379-400">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="3c379-401">`-np|--no-pagemodel`: crea la página sin PageModel.</span><span class="sxs-lookup"><span data-stu-id="3c379-401">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="3c379-402">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="3c379-402">**viewimports**</span></span>

<span data-ttu-id="3c379-403">`-na|--namespace <NAMESPACE_NAME>`: espacio de nombres para el código generado.</span><span class="sxs-lookup"><span data-stu-id="3c379-403">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="3c379-404">El valor predeterminado es `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="3c379-404">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="3c379-405">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="3c379-405">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="3c379-406">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="3c379-406">**console, angular, react, reactredux**</span></span>

  <span data-ttu-id="3c379-407">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c379-407">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="3c379-408">**classlib**</span><span class="sxs-lookup"><span data-stu-id="3c379-408">**classlib**</span></span>

<span data-ttu-id="3c379-409">`-f|--framework <FRAMEWORK>`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="3c379-409">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="3c379-410">Valores: `netcoreapp2.0` para crear una biblioteca de clases de .NET Core o `netstandard2.0` para crear una biblioteca de clases de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="3c379-410">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="3c379-411">El valor predeterminado es `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="3c379-411">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="3c379-412">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c379-412">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="3c379-413">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="3c379-413">**mstest, xunit**</span></span>

<span data-ttu-id="3c379-414">`-p|--enable-pack`: habilita el empaquetado para el proyecto mediante [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="3c379-414">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="3c379-415">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c379-415">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="3c379-416">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="3c379-416">**globaljson**</span></span>

<span data-ttu-id="3c379-417">`--sdk-version <VERSION_NUMBER>`: especifica la versión del SDK de .NET Core que se usará con el archivo *global.json*.</span><span class="sxs-lookup"><span data-stu-id="3c379-417">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="3c379-418">**web**</span><span class="sxs-lookup"><span data-stu-id="3c379-418">**web**</span></span>

<span data-ttu-id="3c379-419">`--use-launch-settings`: incluye *launchSettings.json* en la salida de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="3c379-419">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="3c379-420">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c379-420">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="3c379-421">**webapi**</span><span class="sxs-lookup"><span data-stu-id="3c379-421">**webapi**</span></span>

<span data-ttu-id="3c379-422">`-au|--auth <AUTHENTICATION_TYPE>`: el tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="3c379-422">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="3c379-423">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="3c379-423">The possible values are:</span></span>

- <span data-ttu-id="3c379-424">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="3c379-424">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="3c379-425">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="3c379-425">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="3c379-426">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="3c379-426">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="3c379-427">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="3c379-427">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="3c379-428">`--aad-b2c-instance <INSTANCE>`: la instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="3c379-428">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="3c379-429">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="3c379-429">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="3c379-430">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="3c379-430">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="3c379-431">`-ssp|--susi-policy-id <ID>`: el id. de inicio de sesión y de directiva de registro de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c379-431">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="3c379-432">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="3c379-432">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="3c379-433">`--aad-instance <INSTANCE>`: la instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="3c379-433">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="3c379-434">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="3c379-434">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="3c379-435">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="3c379-435">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="3c379-436">`--client-id <ID>`: el id. de cliente para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c379-436">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="3c379-437">Úsela con las autenticaciones `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="3c379-437">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="3c379-438">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="3c379-438">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="3c379-439">`--domain <DOMAIN>`: el dominio para el inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="3c379-439">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="3c379-440">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="3c379-440">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="3c379-441">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="3c379-441">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="3c379-442">`--tenant-id <ID>`: el id. de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="3c379-442">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="3c379-443">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="3c379-443">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="3c379-444">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="3c379-444">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="3c379-445">`-r|--org-read-access`: concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="3c379-445">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="3c379-446">Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="3c379-446">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="3c379-447">`--use-launch-settings`: incluye *launchSettings.json* en la salida de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="3c379-447">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="3c379-448">`-uld|--use-local-db`: especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="3c379-448">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="3c379-449">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="3c379-449">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="3c379-450">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c379-450">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="3c379-451">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="3c379-451">**mvc, razor**</span></span>

<span data-ttu-id="3c379-452">`-au|--auth <AUTHENTICATION_TYPE>`: el tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="3c379-452">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="3c379-453">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="3c379-453">The possible values are:</span></span>

- <span data-ttu-id="3c379-454">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="3c379-454">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="3c379-455">`Individual`: autenticación individual.</span><span class="sxs-lookup"><span data-stu-id="3c379-455">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="3c379-456">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="3c379-456">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="3c379-457">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="3c379-457">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="3c379-458">`MultiOrg`: autenticación organizativa para varios inquilinos.</span><span class="sxs-lookup"><span data-stu-id="3c379-458">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="3c379-459">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="3c379-459">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="3c379-460">`--aad-b2c-instance <INSTANCE>`: la instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="3c379-460">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="3c379-461">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="3c379-461">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="3c379-462">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="3c379-462">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="3c379-463">`-ssp|--susi-policy-id <ID>`: el id. de inicio de sesión y de directiva de registro de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c379-463">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="3c379-464">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="3c379-464">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="3c379-465">`-rp|--reset-password-policy-id <ID>`: el id. de la directiva de restablecimiento de contraseñas para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c379-465">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="3c379-466">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="3c379-466">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="3c379-467">`-ep|--edit-profile-policy-id <ID>`: el id. de directiva de edición de perfiles para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c379-467">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="3c379-468">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="3c379-468">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="3c379-469">`--aad-instance <INSTANCE>`: la instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="3c379-469">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="3c379-470">Úsela con las autenticaciones `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="3c379-470">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="3c379-471">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="3c379-471">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="3c379-472">`--client-id <ID>`: el id. de cliente para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c379-472">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="3c379-473">Úsela con las autenticaciones `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="3c379-473">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="3c379-474">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="3c379-474">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="3c379-475">`--domain <DOMAIN>`: el dominio para el inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="3c379-475">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="3c379-476">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="3c379-476">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="3c379-477">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="3c379-477">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="3c379-478">`--tenant-id <ID>`: el id. de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="3c379-478">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="3c379-479">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="3c379-479">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="3c379-480">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="3c379-480">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="3c379-481">`--callback-path <PATH>`: la ruta de acceso de solicitud de la ruta de acceso de la base de la aplicación del URI de redirección.</span><span class="sxs-lookup"><span data-stu-id="3c379-481">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="3c379-482">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="3c379-482">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="3c379-483">El valor predeterminado es `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="3c379-483">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="3c379-484">`-r|--org-read-access`: concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="3c379-484">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="3c379-485">Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="3c379-485">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="3c379-486">`--use-launch-settings`: incluye *launchSettings.json* en la salida de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="3c379-486">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="3c379-487">`--use-browserlink`: incluye BrowserLink en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c379-487">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="3c379-488">`-uld|--use-local-db`: especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="3c379-488">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="3c379-489">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="3c379-489">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="3c379-490">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c379-490">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="3c379-491">**page**</span><span class="sxs-lookup"><span data-stu-id="3c379-491">**page**</span></span>

<span data-ttu-id="3c379-492">`-na|--namespace <NAMESPACE_NAME>`: espacio de nombres para el código generado.</span><span class="sxs-lookup"><span data-stu-id="3c379-492">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="3c379-493">El valor predeterminado es `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="3c379-493">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="3c379-494">`-np|--no-pagemodel`: crea la página sin PageModel.</span><span class="sxs-lookup"><span data-stu-id="3c379-494">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="3c379-495">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="3c379-495">**viewimports**</span></span>

<span data-ttu-id="3c379-496">`-na|--namespace <NAMESPACE_NAME>`: espacio de nombres para el código generado.</span><span class="sxs-lookup"><span data-stu-id="3c379-496">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="3c379-497">El valor predeterminado es `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="3c379-497">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="3c379-498">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="3c379-498">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="3c379-499">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="3c379-499">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="3c379-500">`-f|--framework`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="3c379-500">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="3c379-501">Valores: `netcoreapp1.0` o `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="3c379-501">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="3c379-502">El valor predeterminado es `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="3c379-502">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="3c379-503">**classlib**</span><span class="sxs-lookup"><span data-stu-id="3c379-503">**classlib**</span></span>

<span data-ttu-id="3c379-504">`-f|--framework`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="3c379-504">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="3c379-505">Valores: `netcoreapp1.0`, `netcoreapp1.1` o de `netstandard1.0` a `netstandard1.6`.</span><span class="sxs-lookup"><span data-stu-id="3c379-505">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="3c379-506">El valor predeterminado es `netstandard1.4`.</span><span class="sxs-lookup"><span data-stu-id="3c379-506">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="3c379-507">**mvc**</span><span class="sxs-lookup"><span data-stu-id="3c379-507">**mvc**</span></span>

<span data-ttu-id="3c379-508">`-f|--framework`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="3c379-508">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="3c379-509">Valores: `netcoreapp1.0` o `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="3c379-509">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="3c379-510">El valor predeterminado es `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="3c379-510">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="3c379-511">`-au|--auth`: el tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="3c379-511">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="3c379-512">Valores: `None` o `Individual`.</span><span class="sxs-lookup"><span data-stu-id="3c379-512">Values: `None` or `Individual`.</span></span> <span data-ttu-id="3c379-513">El valor predeterminado es `None`.</span><span class="sxs-lookup"><span data-stu-id="3c379-513">The default value is `None`.</span></span>

<span data-ttu-id="3c379-514">`-uld|--use-local-db`: especifica si se va a usar o no LocalDB en lugar de SQLite.</span><span class="sxs-lookup"><span data-stu-id="3c379-514">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="3c379-515">Valores: `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="3c379-515">Values: `true` or `false`.</span></span> <span data-ttu-id="3c379-516">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="3c379-516">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="3c379-517">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="3c379-517">Examples</span></span>

<span data-ttu-id="3c379-518">Creación de un proyecto de aplicación de consola con F# en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="3c379-518">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang F#`

<span data-ttu-id="3c379-519">Creación de un proyecto de biblioteca de clases de .NET Standard en el directorio especificado (disponible solo con el SDK de .NET Core 2.0 o versiones posteriores):</span><span class="sxs-lookup"><span data-stu-id="3c379-519">Create a .NET Standard class library project in the specified directory (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="3c379-520">Creación de un proyecto de aplicación MVC de ASP.NET Core C# en el directorio actual sin autenticación:</span><span class="sxs-lookup"><span data-stu-id="3c379-520">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication:</span></span>

`dotnet new mvc -au None`

<span data-ttu-id="3c379-521">Cree una aplicación de xUnit.</span><span class="sxs-lookup"><span data-stu-id="3c379-521">Create a new xUnit application:</span></span>

`dotnet new xunit`

<span data-ttu-id="3c379-522">Enumere todas las plantillas disponibles para MVC:</span><span class="sxs-lookup"><span data-stu-id="3c379-522">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

<span data-ttu-id="3c379-523">Instalación de la versión 2.0 de las plantillas Aplicación de página única para ASP.NET Core (opción de comando solo disponible para .NET Core SDK 1.1 y versiones posteriores):</span><span class="sxs-lookup"><span data-stu-id="3c379-523">Install version 2.0 of the Single Page Application templates for ASP.NET Core (command option available for .NET Core SDK 1.1 and later versions only):</span></span>

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

<span data-ttu-id="3c379-524">Creación de un archivo *global.json* en el directorio actual que establezca la versión del SDK en 2.0.0 (solo disponible en el SDK de .NET Core 2.0 o versiones posteriores):</span><span class="sxs-lookup"><span data-stu-id="3c379-524">Create a *global.json* in the current directory setting the SDK version to 2.0.0 (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new globaljson --sdk-version 2.0.0`

## <a name="see-also"></a><span data-ttu-id="3c379-525">Vea también</span><span class="sxs-lookup"><span data-stu-id="3c379-525">See also</span></span>

- <span data-ttu-id="3c379-526">[Custom templates for dotnet new](custom-templates.md) (Plantillas personalizadas para dotnet new)</span><span class="sxs-lookup"><span data-stu-id="3c379-526">[Custom templates for dotnet new](custom-templates.md)</span></span>
- [<span data-ttu-id="3c379-527">Creación de una plantilla personalizada para dotnet new</span><span class="sxs-lookup"><span data-stu-id="3c379-527">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)
- [<span data-ttu-id="3c379-528">Repositorio de GitHub dotnet/dotnet-template-samples</span><span class="sxs-lookup"><span data-stu-id="3c379-528">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- <span data-ttu-id="3c379-529">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new) (Plantillas disponibles para dotnet new)</span><span class="sxs-lookup"><span data-stu-id="3c379-529">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)</span></span>
