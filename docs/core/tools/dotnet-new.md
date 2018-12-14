---
title: 'Comando dotnet new: CLI de .NET Core'
description: El comando dotnet new crea proyectos de .NET Core basados en la plantilla especificada.
author: mairaw
ms.author: mairaw
ms.date: 10/24/2018
ms.openlocfilehash: a8d486f569f31d68d5659ac6a80d615474ef2506
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53131487"
---
# <a name="dotnet-new"></a><span data-ttu-id="ca658-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="ca658-103">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="ca658-104">nombre</span><span class="sxs-lookup"><span data-stu-id="ca658-104">Name</span></span>

<span data-ttu-id="ca658-105">`dotnet new`: crea un nuevo proyecto, archivo de configuración o solución según la plantilla especificada.</span><span class="sxs-lookup"><span data-stu-id="ca658-105">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="ca658-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="ca658-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="ca658-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="ca658-107">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output]
    [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="ca658-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="ca658-108">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="ca658-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="ca658-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="ca658-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="ca658-110">Description</span></span>

<span data-ttu-id="ca658-111">El comando `dotnet new` proporciona una manera cómoda de inicializar un proyecto .NET Core válido.</span><span class="sxs-lookup"><span data-stu-id="ca658-111">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span>

<span data-ttu-id="ca658-112">El comando llama al [motor de plantillas](https://github.com/dotnet/templating) para crear los artefactos en el disco basándose en las opciones y la plantilla especificadas.</span><span class="sxs-lookup"><span data-stu-id="ca658-112">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="ca658-113">Argumentos</span><span class="sxs-lookup"><span data-stu-id="ca658-113">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="ca658-114">La plantilla de la que se va a crear una instancia cuando se invoca el comando.</span><span class="sxs-lookup"><span data-stu-id="ca658-114">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="ca658-115">Cada plantilla puede tener opciones específicas que puede pasar.</span><span class="sxs-lookup"><span data-stu-id="ca658-115">Each template might have specific options you can pass.</span></span> <span data-ttu-id="ca658-116">Para obtener más información, vea [Opciones de plantilla](#template-options).</span><span class="sxs-lookup"><span data-stu-id="ca658-116">For more information, see [Template options](#template-options).</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="ca658-117">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="ca658-117">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="ca658-118">El comando contiene una lista predeterminada de plantillas.</span><span class="sxs-lookup"><span data-stu-id="ca658-118">The command contains a default list of templates.</span></span> <span data-ttu-id="ca658-119">Use `dotnet new -l` para obtener una lista de las plantillas disponibles.</span><span class="sxs-lookup"><span data-stu-id="ca658-119">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="ca658-120">En la tabla siguiente se muestran las plantillas que vienen preinstaladas con el SDK de .NET Core 2.1.300.</span><span class="sxs-lookup"><span data-stu-id="ca658-120">The following table shows the templates that come pre-installed with the .NET Core SDK 2.1.300.</span></span> <span data-ttu-id="ca658-121">El lenguaje predeterminado de la plantilla se muestra entre corchetes.</span><span class="sxs-lookup"><span data-stu-id="ca658-121">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="ca658-122">Descripción de plantilla</span><span class="sxs-lookup"><span data-stu-id="ca658-122">Template description</span></span>                          | <span data-ttu-id="ca658-123">Nombre de plantilla</span><span class="sxs-lookup"><span data-stu-id="ca658-123">Template name</span></span>    | <span data-ttu-id="ca658-124">Lenguajes</span><span class="sxs-lookup"><span data-stu-id="ca658-124">Languages</span></span>     |
|----------------------------------------------|------------------|---------------|
| <span data-ttu-id="ca658-125">Aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="ca658-125">Console application</span></span>                          | `console`        | <span data-ttu-id="ca658-126">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="ca658-126">[C#], F#, VB</span></span>  |
| <span data-ttu-id="ca658-127">Biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="ca658-127">Class library</span></span>                                | `classlib`       | <span data-ttu-id="ca658-128">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="ca658-128">[C#], F#, VB</span></span>  |
| <span data-ttu-id="ca658-129">Proyecto de prueba unitaria</span><span class="sxs-lookup"><span data-stu-id="ca658-129">Unit test project</span></span>                            | `mstest`         | <span data-ttu-id="ca658-130">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="ca658-130">[C#], F#, VB</span></span>  |
| <span data-ttu-id="ca658-131">Proyecto de prueba xUnit</span><span class="sxs-lookup"><span data-stu-id="ca658-131">xUnit test project</span></span>                           | `xunit`          | <span data-ttu-id="ca658-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="ca658-132">[C#], F#, VB</span></span>  |
| <span data-ttu-id="ca658-133">Proyecto de prueba de NUnit</span><span class="sxs-lookup"><span data-stu-id="ca658-133">NUnit test project</span></span>                           | `nunit`          | <span data-ttu-id="ca658-134">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="ca658-134">[C#], F#, VB</span></span>  |
| <span data-ttu-id="ca658-135">Página de Razor</span><span class="sxs-lookup"><span data-stu-id="ca658-135">Razor page</span></span>                                   | `page`           | <span data-ttu-id="ca658-136">[C#]</span><span class="sxs-lookup"><span data-stu-id="ca658-136">[C#]</span></span>          |
| <span data-ttu-id="ca658-137">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="ca658-137">MVC ViewImports</span></span>                              | `viewimports`    | <span data-ttu-id="ca658-138">[C#]</span><span class="sxs-lookup"><span data-stu-id="ca658-138">[C#]</span></span>          |
| <span data-ttu-id="ca658-139">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="ca658-139">MVC ViewStart</span></span>                                | `viewstart`      | <span data-ttu-id="ca658-140">[C#]</span><span class="sxs-lookup"><span data-stu-id="ca658-140">[C#]</span></span>          |
| <span data-ttu-id="ca658-141">Vacío de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="ca658-141">ASP.NET Core empty</span></span>                           | `web`            | <span data-ttu-id="ca658-142">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="ca658-142">[C#], F#</span></span>      |
| <span data-ttu-id="ca658-143">Aplicación web de ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="ca658-143">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`            | <span data-ttu-id="ca658-144">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="ca658-144">[C#], F#</span></span>      |
| <span data-ttu-id="ca658-145">Aplicación web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="ca658-145">ASP.NET Core Web App</span></span>                         | <span data-ttu-id="ca658-146">`razor`, `webapp`</span><span class="sxs-lookup"><span data-stu-id="ca658-146">`razor`, `webapp`</span></span>| <span data-ttu-id="ca658-147">[C#]</span><span class="sxs-lookup"><span data-stu-id="ca658-147">[C#]</span></span>          |
| <span data-ttu-id="ca658-148">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="ca658-148">ASP.NET Core with Angular</span></span>                    | `angular`        | <span data-ttu-id="ca658-149">[C#]</span><span class="sxs-lookup"><span data-stu-id="ca658-149">[C#]</span></span>          |
| <span data-ttu-id="ca658-150">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="ca658-150">ASP.NET Core with React.js</span></span>                   | `react`          | <span data-ttu-id="ca658-151">[C#]</span><span class="sxs-lookup"><span data-stu-id="ca658-151">[C#]</span></span>          |
| <span data-ttu-id="ca658-152">ASP.NET Core con React.js y Redux</span><span class="sxs-lookup"><span data-stu-id="ca658-152">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`     | <span data-ttu-id="ca658-153">[C#]</span><span class="sxs-lookup"><span data-stu-id="ca658-153">[C#]</span></span>          |
| <span data-ttu-id="ca658-154">API web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="ca658-154">ASP.NET Core Web API</span></span>                         | `webapi`         | <span data-ttu-id="ca658-155">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="ca658-155">[C#], F#</span></span>      |
| <span data-ttu-id="ca658-156">Biblioteca de clases de Razor</span><span class="sxs-lookup"><span data-stu-id="ca658-156">Razor class library</span></span>                          | `razorclasslib`  | <span data-ttu-id="ca658-157">[C#]</span><span class="sxs-lookup"><span data-stu-id="ca658-157">[C#]</span></span>          |
| <span data-ttu-id="ca658-158">archivo global.json</span><span class="sxs-lookup"><span data-stu-id="ca658-158">global.json file</span></span>                             | `globaljson`     |               |
| <span data-ttu-id="ca658-159">Configuración de NuGet</span><span class="sxs-lookup"><span data-stu-id="ca658-159">NuGet config</span></span>                                 | `nugetconfig`    |               |
| <span data-ttu-id="ca658-160">Configuración de la Web</span><span class="sxs-lookup"><span data-stu-id="ca658-160">Web config</span></span>                                   | `webconfig`      |               |
| <span data-ttu-id="ca658-161">Archivo de solución</span><span class="sxs-lookup"><span data-stu-id="ca658-161">Solution file</span></span>                                | `sln`            |               |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="ca658-162">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="ca658-162">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="ca658-163">El comando contiene una lista predeterminada de plantillas.</span><span class="sxs-lookup"><span data-stu-id="ca658-163">The command contains a default list of templates.</span></span> <span data-ttu-id="ca658-164">Use `dotnet new -l` para obtener una lista de las plantillas disponibles.</span><span class="sxs-lookup"><span data-stu-id="ca658-164">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="ca658-165">En la tabla siguiente se muestran las plantillas que vienen preinstaladas con el SDK de .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="ca658-165">The following table shows the templates that come pre-installed with the .NET Core SDK 2.0.</span></span> <span data-ttu-id="ca658-166">El lenguaje predeterminado de la plantilla se muestra entre corchetes.</span><span class="sxs-lookup"><span data-stu-id="ca658-166">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="ca658-167">Descripción de plantilla</span><span class="sxs-lookup"><span data-stu-id="ca658-167">Template description</span></span>                          | <span data-ttu-id="ca658-168">Nombre de plantilla</span><span class="sxs-lookup"><span data-stu-id="ca658-168">Template name</span></span> | <span data-ttu-id="ca658-169">Lenguajes</span><span class="sxs-lookup"><span data-stu-id="ca658-169">Languages</span></span>     |
|----------------------------------------------|---------------|---------------|
| <span data-ttu-id="ca658-170">Aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="ca658-170">Console application</span></span>                          | `console`     | <span data-ttu-id="ca658-171">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="ca658-171">[C#], F#, VB</span></span>  |
| <span data-ttu-id="ca658-172">Biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="ca658-172">Class library</span></span>                                | `classlib`    | <span data-ttu-id="ca658-173">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="ca658-173">[C#], F#, VB</span></span>  |
| <span data-ttu-id="ca658-174">Proyecto de prueba unitaria</span><span class="sxs-lookup"><span data-stu-id="ca658-174">Unit test project</span></span>                            | `mstest`      | <span data-ttu-id="ca658-175">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="ca658-175">[C#], F#, VB</span></span>  |
| <span data-ttu-id="ca658-176">Proyecto de prueba xUnit</span><span class="sxs-lookup"><span data-stu-id="ca658-176">xUnit test project</span></span>                           | `xunit`       | <span data-ttu-id="ca658-177">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="ca658-177">[C#], F#, VB</span></span>  |
| <span data-ttu-id="ca658-178">Vacío de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="ca658-178">ASP.NET Core empty</span></span>                           | `web`         | <span data-ttu-id="ca658-179">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="ca658-179">[C#], F#</span></span>      |
| <span data-ttu-id="ca658-180">Aplicación web de ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="ca658-180">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="ca658-181">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="ca658-181">[C#], F#</span></span>      |
| <span data-ttu-id="ca658-182">Aplicación web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="ca658-182">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="ca658-183">[C#]</span><span class="sxs-lookup"><span data-stu-id="ca658-183">[C#]</span></span>          |
| <span data-ttu-id="ca658-184">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="ca658-184">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="ca658-185">[C#]</span><span class="sxs-lookup"><span data-stu-id="ca658-185">[C#]</span></span>          |
| <span data-ttu-id="ca658-186">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="ca658-186">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="ca658-187">[C#]</span><span class="sxs-lookup"><span data-stu-id="ca658-187">[C#]</span></span>          |
| <span data-ttu-id="ca658-188">ASP.NET Core con React.js y Redux</span><span class="sxs-lookup"><span data-stu-id="ca658-188">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="ca658-189">[C#]</span><span class="sxs-lookup"><span data-stu-id="ca658-189">[C#]</span></span>          |
| <span data-ttu-id="ca658-190">API web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="ca658-190">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="ca658-191">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="ca658-191">[C#], F#</span></span>      |
| <span data-ttu-id="ca658-192">archivo global.json</span><span class="sxs-lookup"><span data-stu-id="ca658-192">global.json file</span></span>                             | `globaljson`  |               |
| <span data-ttu-id="ca658-193">Configuración de NuGet</span><span class="sxs-lookup"><span data-stu-id="ca658-193">NuGet config</span></span>                                 | `nugetconfig` |               |
| <span data-ttu-id="ca658-194">Configuración de la Web</span><span class="sxs-lookup"><span data-stu-id="ca658-194">Web config</span></span>                                   | `webconfig`   |               |
| <span data-ttu-id="ca658-195">Archivo de solución</span><span class="sxs-lookup"><span data-stu-id="ca658-195">Solution file</span></span>                                | `sln`         |               |
| <span data-ttu-id="ca658-196">Página de Razor</span><span class="sxs-lookup"><span data-stu-id="ca658-196">Razor page</span></span>                                   | `page`        |               |
| <span data-ttu-id="ca658-197">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="ca658-197">MVC ViewImports</span></span>                              | `viewimports` |               |
| <span data-ttu-id="ca658-198">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="ca658-198">MVC ViewStart</span></span>                                | `viewstart`   |               |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="ca658-199">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="ca658-199">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="ca658-200">El comando contiene una lista predeterminada de plantillas.</span><span class="sxs-lookup"><span data-stu-id="ca658-200">The command contains a default list of templates.</span></span> <span data-ttu-id="ca658-201">Use `dotnet new -all` para obtener una lista de las plantillas disponibles.</span><span class="sxs-lookup"><span data-stu-id="ca658-201">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="ca658-202">En la tabla siguiente se muestran las plantillas que vienen preinstaladas con el SDK de .NET 1.x.</span><span class="sxs-lookup"><span data-stu-id="ca658-202">The following table shows the templates that come pre-installed with the .NET Core SDK 1.x.</span></span> <span data-ttu-id="ca658-203">El lenguaje predeterminado de la plantilla se muestra entre corchetes.</span><span class="sxs-lookup"><span data-stu-id="ca658-203">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="ca658-204">Descripción de plantilla</span><span class="sxs-lookup"><span data-stu-id="ca658-204">Template description</span></span>  | <span data-ttu-id="ca658-205">Nombre de plantilla</span><span class="sxs-lookup"><span data-stu-id="ca658-205">Template name</span></span> | <span data-ttu-id="ca658-206">Lenguajes</span><span class="sxs-lookup"><span data-stu-id="ca658-206">Languages</span></span> |
|----------------------|---------------|-----------|
| <span data-ttu-id="ca658-207">Aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="ca658-207">Console application</span></span>  | `console`     | <span data-ttu-id="ca658-208">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="ca658-208">[C#], F#</span></span>  |
| <span data-ttu-id="ca658-209">Biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="ca658-209">Class library</span></span>        | `classlib`    | <span data-ttu-id="ca658-210">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="ca658-210">[C#], F#</span></span>  |
| <span data-ttu-id="ca658-211">Proyecto de prueba unitaria</span><span class="sxs-lookup"><span data-stu-id="ca658-211">Unit test project</span></span>    | `mstest`      | <span data-ttu-id="ca658-212">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="ca658-212">[C#], F#</span></span>  |
| <span data-ttu-id="ca658-213">Proyecto de prueba xUnit</span><span class="sxs-lookup"><span data-stu-id="ca658-213">xUnit test project</span></span>   | `xunit`       | <span data-ttu-id="ca658-214">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="ca658-214">[C#], F#</span></span>  |
| <span data-ttu-id="ca658-215">Vacío de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="ca658-215">ASP.NET Core empty</span></span>   | `web`         | <span data-ttu-id="ca658-216">[C#]</span><span class="sxs-lookup"><span data-stu-id="ca658-216">[C#]</span></span>      |
| <span data-ttu-id="ca658-217">Aplicación web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="ca658-217">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="ca658-218">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="ca658-218">[C#], F#</span></span>  |
| <span data-ttu-id="ca658-219">API web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="ca658-219">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="ca658-220">[C#]</span><span class="sxs-lookup"><span data-stu-id="ca658-220">[C#]</span></span>      |
| <span data-ttu-id="ca658-221">Configuración de NuGet</span><span class="sxs-lookup"><span data-stu-id="ca658-221">NuGet config</span></span>         | `nugetconfig` |           |
| <span data-ttu-id="ca658-222">Configuración de la Web</span><span class="sxs-lookup"><span data-stu-id="ca658-222">Web config</span></span>           | `webconfig`   |           |
| <span data-ttu-id="ca658-223">Archivo de solución</span><span class="sxs-lookup"><span data-stu-id="ca658-223">Solution file</span></span>        | `sln`         |           |

---

## <a name="options"></a><span data-ttu-id="ca658-224">Opciones</span><span class="sxs-lookup"><span data-stu-id="ca658-224">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="ca658-225">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="ca658-225">.NET Core 2.1</span></span>](#tab/netcore21)

`--force`

<span data-ttu-id="ca658-226">Fuerza la generación de contenido incluso aunque se vayan a cambiar los archivos existentes.</span><span class="sxs-lookup"><span data-stu-id="ca658-226">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="ca658-227">Esto es necesario cuando el directorio de salida ya contiene un proyecto.</span><span class="sxs-lookup"><span data-stu-id="ca658-227">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="ca658-228">Imprime la ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="ca658-228">Prints out help for the command.</span></span> <span data-ttu-id="ca658-229">Puede invocarse para el propio comando `dotnet new` o para cualquier plantilla, como `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="ca658-229">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="ca658-230">Instala un paquete de plantillas u origen desde los parámetros `PATH` o `NUGET_ID` proporcionados.</span><span class="sxs-lookup"><span data-stu-id="ca658-230">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="ca658-231">Si quiere instalar una versión preliminar de un paquete de plantilla, tendrá que especificar la versión en el formato de `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="ca658-231">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="ca658-232">De manera predeterminada, `dotnet new` pasa \* para la versión, que representa la última versión estable del paquete.</span><span class="sxs-lookup"><span data-stu-id="ca658-232">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="ca658-233">Vea un ejemplo en la sección [Ejemplos](#examples).</span><span class="sxs-lookup"><span data-stu-id="ca658-233">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="ca658-234">Para obtener información sobre cómo crear plantillas personalizadas, consulte [Custom templates for dotnet new](custom-templates.md) (Plantillas personalizadas para dotnet new).</span><span class="sxs-lookup"><span data-stu-id="ca658-234">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="ca658-235">Muestra las plantillas que contienen el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="ca658-235">Lists templates containing the specified name.</span></span> <span data-ttu-id="ca658-236">Si se invoca para el comando `dotnet new`, muestra las plantillas posibles disponibles para un directorio determinado.</span><span class="sxs-lookup"><span data-stu-id="ca658-236">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="ca658-237">Por ejemplo, si el directorio ya contiene un proyecto, no mostrará todas las plantillas del proyecto.</span><span class="sxs-lookup"><span data-stu-id="ca658-237">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="ca658-238">El lenguaje de la plantilla que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="ca658-238">The language of the template to create.</span></span> <span data-ttu-id="ca658-239">El lenguaje aceptado cambia según la plantilla (vea los valores predeterminados en la sección [argumentos](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="ca658-239">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="ca658-240">No es válido para algunas plantillas.</span><span class="sxs-lookup"><span data-stu-id="ca658-240">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="ca658-241">Algunos shells interpretan `#` como un carácter especial.</span><span class="sxs-lookup"><span data-stu-id="ca658-241">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="ca658-242">En esos casos, debe incluir el valor del parámetro de lenguaje, como `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="ca658-242">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="ca658-243">El nombre de la salida creada.</span><span class="sxs-lookup"><span data-stu-id="ca658-243">The name for the created output.</span></span> <span data-ttu-id="ca658-244">Si no se especifica ningún nombre, se usa el nombre del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="ca658-244">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="ca658-245">Especifica un origen de NuGet para usarlo durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="ca658-245">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="ca658-246">La ubicación para colocar la salida generada.</span><span class="sxs-lookup"><span data-stu-id="ca658-246">Location to place the generated output.</span></span> <span data-ttu-id="ca658-247">El valor predeterminado es el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="ca658-247">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="ca658-248">Filtra plantillas en función de los tipos disponibles.</span><span class="sxs-lookup"><span data-stu-id="ca658-248">Filters templates based on available types.</span></span> <span data-ttu-id="ca658-249">Los valores predefinidos son “project”, “item” y “other”.</span><span class="sxs-lookup"><span data-stu-id="ca658-249">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="ca658-250">Desinstala un paquete de plantillas u origen en los parámetros `PATH` o `NUGET_ID` proporcionados.</span><span class="sxs-lookup"><span data-stu-id="ca658-250">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="ca658-251">Para desinstalar una plantilla mediante `PATH`, debe usar el nombre completo de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="ca658-251">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="ca658-252">Por ejemplo, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* funcionará, pero *./GarciaSoftware.ConsoleTemplate.CSharp* desde la carpeta contenedora no lo hará.</span><span class="sxs-lookup"><span data-stu-id="ca658-252">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="ca658-253">Además, no debe incluir una barra diagonal para finalizar el directorio en la ruta de acceso a la plantilla.</span><span class="sxs-lookup"><span data-stu-id="ca658-253">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="ca658-254">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="ca658-254">.NET Core 2.0</span></span>](#tab/netcore20)

`--force`

<span data-ttu-id="ca658-255">Fuerza la generación de contenido incluso aunque se vayan a cambiar los archivos existentes.</span><span class="sxs-lookup"><span data-stu-id="ca658-255">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="ca658-256">Esto es necesario cuando el directorio de salida ya contiene un proyecto.</span><span class="sxs-lookup"><span data-stu-id="ca658-256">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="ca658-257">Imprime la ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="ca658-257">Prints out help for the command.</span></span> <span data-ttu-id="ca658-258">Puede invocarse para el propio comando `dotnet new` o para cualquier plantilla, como `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="ca658-258">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="ca658-259">Instala un paquete de plantillas u origen desde los parámetros `PATH` o `NUGET_ID` proporcionados.</span><span class="sxs-lookup"><span data-stu-id="ca658-259">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="ca658-260">Si quiere instalar una versión preliminar de un paquete de plantilla, tendrá que especificar la versión en el formato de `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="ca658-260">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="ca658-261">De manera predeterminada, `dotnet new` pasa \* para la versión, que representa la última versión estable del paquete.</span><span class="sxs-lookup"><span data-stu-id="ca658-261">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="ca658-262">Vea un ejemplo en la sección [Ejemplos](#examples).</span><span class="sxs-lookup"><span data-stu-id="ca658-262">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="ca658-263">Para obtener información sobre cómo crear plantillas personalizadas, consulte [Custom templates for dotnet new](custom-templates.md) (Plantillas personalizadas para dotnet new).</span><span class="sxs-lookup"><span data-stu-id="ca658-263">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="ca658-264">Muestra las plantillas que contienen el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="ca658-264">Lists templates containing the specified name.</span></span> <span data-ttu-id="ca658-265">Si se invoca para el comando `dotnet new`, muestra las plantillas posibles disponibles para un directorio determinado.</span><span class="sxs-lookup"><span data-stu-id="ca658-265">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="ca658-266">Por ejemplo, si el directorio ya contiene un proyecto, no mostrará todas las plantillas del proyecto.</span><span class="sxs-lookup"><span data-stu-id="ca658-266">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="ca658-267">El lenguaje de la plantilla que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="ca658-267">The language of the template to create.</span></span> <span data-ttu-id="ca658-268">El lenguaje aceptado cambia según la plantilla (vea los valores predeterminados en la sección [argumentos](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="ca658-268">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="ca658-269">No es válido para algunas plantillas.</span><span class="sxs-lookup"><span data-stu-id="ca658-269">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="ca658-270">Algunos shells interpretan `#` como un carácter especial.</span><span class="sxs-lookup"><span data-stu-id="ca658-270">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="ca658-271">En esos casos, debe incluir el valor del parámetro de lenguaje, como `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="ca658-271">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="ca658-272">El nombre de la salida creada.</span><span class="sxs-lookup"><span data-stu-id="ca658-272">The name for the created output.</span></span> <span data-ttu-id="ca658-273">Si no se especifica ningún nombre, se usa el nombre del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="ca658-273">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="ca658-274">La ubicación para colocar la salida generada.</span><span class="sxs-lookup"><span data-stu-id="ca658-274">Location to place the generated output.</span></span> <span data-ttu-id="ca658-275">El valor predeterminado es el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="ca658-275">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="ca658-276">Filtra plantillas en función de los tipos disponibles.</span><span class="sxs-lookup"><span data-stu-id="ca658-276">Filters templates based on available types.</span></span> <span data-ttu-id="ca658-277">Los valores predefinidos son “project”, “item” y “other”.</span><span class="sxs-lookup"><span data-stu-id="ca658-277">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="ca658-278">Desinstala un paquete de plantillas u origen en los parámetros `PATH` o `NUGET_ID` proporcionados.</span><span class="sxs-lookup"><span data-stu-id="ca658-278">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="ca658-279">Para desinstalar una plantilla mediante un origen `PATH`, debe usar el nombre completo de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="ca658-279">To uninstall a template using a source `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="ca658-280">Por ejemplo, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* funcionará, pero *./GarciaSoftware.ConsoleTemplate.CSharp* desde la carpeta contenedora no lo hará.</span><span class="sxs-lookup"><span data-stu-id="ca658-280">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span> <span data-ttu-id="ca658-281">Además, no debe incluir una barra diagonal para finalizar el directorio en la ruta de acceso a la plantilla.</span><span class="sxs-lookup"><span data-stu-id="ca658-281">Additionally, do not include a final terminating directory slash on your template path.</span></span>
> 
> <span data-ttu-id="ca658-282">Si no puede determinar el argumento `PATH` o `NUGET_ID` necesario para desinstalar una plantilla, la ejecución de `dotnet new --uninstall` sin un argumento enumerará todas las plantillas instaladas y el argumento requerido para desinstalarlas.</span><span class="sxs-lookup"><span data-stu-id="ca658-282">If you are unable to determine the `PATH` or `NUGET_ID` argument needed to uninstall a template, running `dotnet new --uninstall` without an argument will list all installed templates and the argument required to uninstall them.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="ca658-283">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="ca658-283">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="ca658-284">Muestra todas las plantillas de un tipo de proyecto específico cuando se ejecuta en el contexto del comando `dotnet new` por sí solo.</span><span class="sxs-lookup"><span data-stu-id="ca658-284">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="ca658-285">Cuando se ejecuta en el contexto de una plantilla específica, como `dotnet new web -all`, `-all` se interpreta como una marca para forzar la creación.</span><span class="sxs-lookup"><span data-stu-id="ca658-285">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="ca658-286">Esto es necesario cuando el directorio de salida ya contiene un proyecto.</span><span class="sxs-lookup"><span data-stu-id="ca658-286">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="ca658-287">Imprime la ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="ca658-287">Prints out help for the command.</span></span> <span data-ttu-id="ca658-288">Puede invocarse para el propio comando `dotnet new` o para cualquier plantilla, como `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="ca658-288">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="ca658-289">Muestra las plantillas que contienen el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="ca658-289">Lists templates containing the specified name.</span></span> <span data-ttu-id="ca658-290">Si se invoca para el comando `dotnet new`, muestra las plantillas posibles disponibles para un directorio determinado.</span><span class="sxs-lookup"><span data-stu-id="ca658-290">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="ca658-291">Por ejemplo, si el directorio ya contiene un proyecto, no mostrará todas las plantillas del proyecto.</span><span class="sxs-lookup"><span data-stu-id="ca658-291">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="ca658-292">El lenguaje de la plantilla que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="ca658-292">The language of the template to create.</span></span> <span data-ttu-id="ca658-293">El lenguaje aceptado cambia según la plantilla (vea los valores predeterminados en la sección [argumentos](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="ca658-293">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="ca658-294">No es válido para algunas plantillas.</span><span class="sxs-lookup"><span data-stu-id="ca658-294">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="ca658-295">Algunos shells interpretan `#` como un carácter especial.</span><span class="sxs-lookup"><span data-stu-id="ca658-295">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="ca658-296">En esos casos, debe incluir el valor del parámetro de lenguaje, como `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="ca658-296">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="ca658-297">El nombre de la salida creada.</span><span class="sxs-lookup"><span data-stu-id="ca658-297">The name for the created output.</span></span> <span data-ttu-id="ca658-298">Si no se especifica ningún nombre, se usa el nombre del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="ca658-298">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="ca658-299">La ubicación para colocar la salida generada.</span><span class="sxs-lookup"><span data-stu-id="ca658-299">Location to place the generated output.</span></span> <span data-ttu-id="ca658-300">El valor predeterminado es el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="ca658-300">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="ca658-301">Opciones de plantilla</span><span class="sxs-lookup"><span data-stu-id="ca658-301">Template options</span></span>

<span data-ttu-id="ca658-302">Cada plantilla de proyecto puede tener opciones adicionales disponibles.</span><span class="sxs-lookup"><span data-stu-id="ca658-302">Each project template may have additional options available.</span></span> <span data-ttu-id="ca658-303">Las plantillas principales tienen las siguientes opciones adicionales:</span><span class="sxs-lookup"><span data-stu-id="ca658-303">The core templates have the following additional options:</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="ca658-304">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="ca658-304">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="ca658-305">**console, angular, react, reactredux, razorclasslib**</span><span class="sxs-lookup"><span data-stu-id="ca658-305">**console, angular, react, reactredux, razorclasslib**</span></span>

  <span data-ttu-id="ca658-306">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="ca658-306">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="ca658-307">**classlib**</span><span class="sxs-lookup"><span data-stu-id="ca658-307">**classlib**</span></span>

<span data-ttu-id="ca658-308">`-f|--framework <FRAMEWORK>`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="ca658-308">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="ca658-309">Valores: `netcoreapp2.0` para crear una biblioteca de clases de .NET Core o `netstandard2.0` para crear una biblioteca de clases de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="ca658-309">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="ca658-310">El valor predeterminado es `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="ca658-310">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="ca658-311">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="ca658-311">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="ca658-312">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="ca658-312">**mstest, xunit**</span></span>

<span data-ttu-id="ca658-313">`-p|--enable-pack`: habilita el empaquetado para el proyecto mediante [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="ca658-313">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="ca658-314">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="ca658-314">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="ca658-315">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="ca658-315">**globaljson**</span></span>

<span data-ttu-id="ca658-316">`--sdk-version <VERSION_NUMBER>`: especifica la versión del SDK de .NET Core que se usará con el archivo *global.json*.</span><span class="sxs-lookup"><span data-stu-id="ca658-316">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="ca658-317">**web**</span><span class="sxs-lookup"><span data-stu-id="ca658-317">**web**</span></span>

<span data-ttu-id="ca658-318">`--exclude-launch-settings`: excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="ca658-318">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="ca658-319">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="ca658-319">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="ca658-320">`--no-https`: el proyecto no requiere HTTPS.</span><span class="sxs-lookup"><span data-stu-id="ca658-320">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="ca658-321">Esta opción solo se aplica si no se usan `IndividualAuth` u `OrganizationalAuth`.</span><span class="sxs-lookup"><span data-stu-id="ca658-321">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="ca658-322">**webapi**</span><span class="sxs-lookup"><span data-stu-id="ca658-322">**webapi**</span></span>

<span data-ttu-id="ca658-323">`-au|--auth <AUTHENTICATION_TYPE>`: el tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="ca658-323">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="ca658-324">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="ca658-324">The possible values are:</span></span>

- <span data-ttu-id="ca658-325">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="ca658-325">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="ca658-326">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="ca658-326">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="ca658-327">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="ca658-327">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="ca658-328">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="ca658-328">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="ca658-329">`--aad-b2c-instance <INSTANCE>`: la instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="ca658-329">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="ca658-330">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="ca658-330">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="ca658-331">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="ca658-331">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="ca658-332">`-ssp|--susi-policy-id <ID>`: el id. de inicio de sesión y de directiva de registro de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="ca658-332">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="ca658-333">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="ca658-333">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="ca658-334">`--aad-instance <INSTANCE>`: la instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="ca658-334">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="ca658-335">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="ca658-335">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="ca658-336">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="ca658-336">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="ca658-337">`--client-id <ID>`: el id. de cliente para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="ca658-337">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="ca658-338">Úsela con las autenticaciones `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="ca658-338">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="ca658-339">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="ca658-339">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="ca658-340">`--domain <DOMAIN>`: el dominio para el inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="ca658-340">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="ca658-341">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="ca658-341">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="ca658-342">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="ca658-342">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="ca658-343">`--tenant-id <ID>`: el id. de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="ca658-343">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="ca658-344">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="ca658-344">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="ca658-345">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="ca658-345">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="ca658-346">`-r|--org-read-access`: concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="ca658-346">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="ca658-347">Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="ca658-347">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="ca658-348">`--exclude-launch-settings`: excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="ca658-348">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="ca658-349">`-uld|--use-local-db`: especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="ca658-349">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="ca658-350">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="ca658-350">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="ca658-351">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="ca658-351">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="ca658-352">`--no-https`: el proyecto no requiere HTTPS.</span><span class="sxs-lookup"><span data-stu-id="ca658-352">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="ca658-353">`app.UseHsts` y `app.UseHttpsRedirection` no se agregan a `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="ca658-353">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="ca658-354">Esta opción solo se aplica si no se usan `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="ca658-354">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="ca658-355">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="ca658-355">**mvc, razor**</span></span>

<span data-ttu-id="ca658-356">`-au|--auth <AUTHENTICATION_TYPE>`: el tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="ca658-356">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="ca658-357">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="ca658-357">The possible values are:</span></span>

- <span data-ttu-id="ca658-358">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="ca658-358">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="ca658-359">`Individual`: autenticación individual.</span><span class="sxs-lookup"><span data-stu-id="ca658-359">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="ca658-360">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="ca658-360">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="ca658-361">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="ca658-361">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="ca658-362">`MultiOrg`: autenticación organizativa para varios inquilinos.</span><span class="sxs-lookup"><span data-stu-id="ca658-362">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="ca658-363">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="ca658-363">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="ca658-364">`--aad-b2c-instance <INSTANCE>`: la instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="ca658-364">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="ca658-365">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="ca658-365">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="ca658-366">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="ca658-366">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="ca658-367">`-ssp|--susi-policy-id <ID>`: el id. de inicio de sesión y de directiva de registro de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="ca658-367">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="ca658-368">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="ca658-368">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="ca658-369">`-rp|--reset-password-policy-id <ID>`: el id. de la directiva de restablecimiento de contraseñas para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="ca658-369">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="ca658-370">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="ca658-370">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="ca658-371">`-ep|--edit-profile-policy-id <ID>`: el id. de directiva de edición de perfiles para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="ca658-371">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="ca658-372">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="ca658-372">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="ca658-373">`--aad-instance <INSTANCE>`: la instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="ca658-373">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="ca658-374">Úsela con las autenticaciones `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="ca658-374">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="ca658-375">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="ca658-375">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="ca658-376">`--client-id <ID>`: el id. de cliente para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="ca658-376">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="ca658-377">Úsela con las autenticaciones `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="ca658-377">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="ca658-378">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="ca658-378">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="ca658-379">`--domain <DOMAIN>`: el dominio para el inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="ca658-379">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="ca658-380">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="ca658-380">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="ca658-381">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="ca658-381">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="ca658-382">`--tenant-id <ID>`: el id. de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="ca658-382">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="ca658-383">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="ca658-383">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="ca658-384">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="ca658-384">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="ca658-385">`--callback-path <PATH>`: la ruta de acceso de solicitud de la ruta de acceso de la base de la aplicación del URI de redirección.</span><span class="sxs-lookup"><span data-stu-id="ca658-385">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="ca658-386">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="ca658-386">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="ca658-387">El valor predeterminado es `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="ca658-387">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="ca658-388">`-r|--org-read-access`: concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="ca658-388">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="ca658-389">Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="ca658-389">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="ca658-390">`--exclude-launch-settings`: excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="ca658-390">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="ca658-391">`--use-browserlink`: incluye BrowserLink en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="ca658-391">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="ca658-392">`-uld|--use-local-db`: especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="ca658-392">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="ca658-393">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="ca658-393">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="ca658-394">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="ca658-394">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="ca658-395">`--no-https`: el proyecto no requiere HTTPS.</span><span class="sxs-lookup"><span data-stu-id="ca658-395">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="ca658-396">`app.UseHsts` y `app.UseHttpsRedirection` no se agregan a `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="ca658-396">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="ca658-397">Esta opción solo se aplica si no se usan `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="ca658-397">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="ca658-398">**page**</span><span class="sxs-lookup"><span data-stu-id="ca658-398">**page**</span></span>

<span data-ttu-id="ca658-399">`-na|--namespace <NAMESPACE_NAME>`: espacio de nombres para el código generado.</span><span class="sxs-lookup"><span data-stu-id="ca658-399">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="ca658-400">El valor predeterminado es `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="ca658-400">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="ca658-401">`-np|--no-pagemodel`: crea la página sin PageModel.</span><span class="sxs-lookup"><span data-stu-id="ca658-401">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="ca658-402">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="ca658-402">**viewimports**</span></span>

<span data-ttu-id="ca658-403">`-na|--namespace <NAMESPACE_NAME>`: espacio de nombres para el código generado.</span><span class="sxs-lookup"><span data-stu-id="ca658-403">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="ca658-404">El valor predeterminado es `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="ca658-404">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="ca658-405">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="ca658-405">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="ca658-406">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="ca658-406">**console, angular, react, reactredux**</span></span>

  <span data-ttu-id="ca658-407">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="ca658-407">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="ca658-408">**classlib**</span><span class="sxs-lookup"><span data-stu-id="ca658-408">**classlib**</span></span>

<span data-ttu-id="ca658-409">`-f|--framework <FRAMEWORK>`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="ca658-409">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="ca658-410">Valores: `netcoreapp2.0` para crear una biblioteca de clases de .NET Core o `netstandard2.0` para crear una biblioteca de clases de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="ca658-410">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="ca658-411">El valor predeterminado es `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="ca658-411">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="ca658-412">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="ca658-412">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="ca658-413">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="ca658-413">**mstest, xunit**</span></span>

<span data-ttu-id="ca658-414">`-p|--enable-pack`: habilita el empaquetado para el proyecto mediante [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="ca658-414">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="ca658-415">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="ca658-415">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="ca658-416">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="ca658-416">**globaljson**</span></span>

<span data-ttu-id="ca658-417">`--sdk-version <VERSION_NUMBER>`: especifica la versión del SDK de .NET Core que se usará con el archivo *global.json*.</span><span class="sxs-lookup"><span data-stu-id="ca658-417">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="ca658-418">**web**</span><span class="sxs-lookup"><span data-stu-id="ca658-418">**web**</span></span>

<span data-ttu-id="ca658-419">`--use-launch-settings`: incluye *launchSettings.json* en la salida de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="ca658-419">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="ca658-420">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="ca658-420">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="ca658-421">**webapi**</span><span class="sxs-lookup"><span data-stu-id="ca658-421">**webapi**</span></span>

<span data-ttu-id="ca658-422">`-au|--auth <AUTHENTICATION_TYPE>`: el tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="ca658-422">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="ca658-423">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="ca658-423">The possible values are:</span></span>

- <span data-ttu-id="ca658-424">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="ca658-424">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="ca658-425">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="ca658-425">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="ca658-426">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="ca658-426">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="ca658-427">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="ca658-427">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="ca658-428">`--aad-b2c-instance <INSTANCE>`: la instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="ca658-428">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="ca658-429">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="ca658-429">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="ca658-430">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="ca658-430">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="ca658-431">`-ssp|--susi-policy-id <ID>`: el id. de inicio de sesión y de directiva de registro de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="ca658-431">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="ca658-432">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="ca658-432">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="ca658-433">`--aad-instance <INSTANCE>`: la instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="ca658-433">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="ca658-434">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="ca658-434">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="ca658-435">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="ca658-435">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="ca658-436">`--client-id <ID>`: el id. de cliente para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="ca658-436">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="ca658-437">Úsela con las autenticaciones `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="ca658-437">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="ca658-438">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="ca658-438">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="ca658-439">`--domain <DOMAIN>`: el dominio para el inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="ca658-439">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="ca658-440">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="ca658-440">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="ca658-441">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="ca658-441">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="ca658-442">`--tenant-id <ID>`: el id. de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="ca658-442">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="ca658-443">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="ca658-443">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="ca658-444">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="ca658-444">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="ca658-445">`-r|--org-read-access`: concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="ca658-445">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="ca658-446">Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="ca658-446">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="ca658-447">`--use-launch-settings`: incluye *launchSettings.json* en la salida de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="ca658-447">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="ca658-448">`-uld|--use-local-db`: especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="ca658-448">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="ca658-449">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="ca658-449">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="ca658-450">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="ca658-450">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="ca658-451">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="ca658-451">**mvc, razor**</span></span>

<span data-ttu-id="ca658-452">`-au|--auth <AUTHENTICATION_TYPE>`: el tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="ca658-452">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="ca658-453">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="ca658-453">The possible values are:</span></span>

- <span data-ttu-id="ca658-454">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="ca658-454">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="ca658-455">`Individual`: autenticación individual.</span><span class="sxs-lookup"><span data-stu-id="ca658-455">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="ca658-456">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="ca658-456">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="ca658-457">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="ca658-457">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="ca658-458">`MultiOrg`: autenticación organizativa para varios inquilinos.</span><span class="sxs-lookup"><span data-stu-id="ca658-458">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="ca658-459">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="ca658-459">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="ca658-460">`--aad-b2c-instance <INSTANCE>`: la instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="ca658-460">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="ca658-461">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="ca658-461">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="ca658-462">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="ca658-462">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="ca658-463">`-ssp|--susi-policy-id <ID>`: el id. de inicio de sesión y de directiva de registro de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="ca658-463">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="ca658-464">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="ca658-464">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="ca658-465">`-rp|--reset-password-policy-id <ID>`: el id. de la directiva de restablecimiento de contraseñas para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="ca658-465">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="ca658-466">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="ca658-466">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="ca658-467">`-ep|--edit-profile-policy-id <ID>`: el id. de directiva de edición de perfiles para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="ca658-467">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="ca658-468">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="ca658-468">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="ca658-469">`--aad-instance <INSTANCE>`: la instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="ca658-469">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="ca658-470">Úsela con las autenticaciones `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="ca658-470">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="ca658-471">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="ca658-471">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="ca658-472">`--client-id <ID>`: el id. de cliente para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="ca658-472">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="ca658-473">Úsela con las autenticaciones `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="ca658-473">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="ca658-474">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="ca658-474">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="ca658-475">`--domain <DOMAIN>`: el dominio para el inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="ca658-475">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="ca658-476">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="ca658-476">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="ca658-477">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="ca658-477">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="ca658-478">`--tenant-id <ID>`: el id. de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="ca658-478">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="ca658-479">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="ca658-479">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="ca658-480">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="ca658-480">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="ca658-481">`--callback-path <PATH>`: la ruta de acceso de solicitud de la ruta de acceso de la base de la aplicación del URI de redirección.</span><span class="sxs-lookup"><span data-stu-id="ca658-481">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="ca658-482">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="ca658-482">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="ca658-483">El valor predeterminado es `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="ca658-483">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="ca658-484">`-r|--org-read-access`: concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="ca658-484">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="ca658-485">Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="ca658-485">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="ca658-486">`--use-launch-settings`: incluye *launchSettings.json* en la salida de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="ca658-486">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="ca658-487">`--use-browserlink`: incluye BrowserLink en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="ca658-487">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="ca658-488">`-uld|--use-local-db`: especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="ca658-488">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="ca658-489">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="ca658-489">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="ca658-490">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="ca658-490">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="ca658-491">**page**</span><span class="sxs-lookup"><span data-stu-id="ca658-491">**page**</span></span>

<span data-ttu-id="ca658-492">`-na|--namespace <NAMESPACE_NAME>`: espacio de nombres para el código generado.</span><span class="sxs-lookup"><span data-stu-id="ca658-492">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="ca658-493">El valor predeterminado es `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="ca658-493">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="ca658-494">`-np|--no-pagemodel`: crea la página sin PageModel.</span><span class="sxs-lookup"><span data-stu-id="ca658-494">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="ca658-495">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="ca658-495">**viewimports**</span></span>

<span data-ttu-id="ca658-496">`-na|--namespace <NAMESPACE_NAME>`: espacio de nombres para el código generado.</span><span class="sxs-lookup"><span data-stu-id="ca658-496">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="ca658-497">El valor predeterminado es `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="ca658-497">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="ca658-498">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="ca658-498">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="ca658-499">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="ca658-499">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="ca658-500">`-f|--framework`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="ca658-500">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="ca658-501">Valores: `netcoreapp1.0` o `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="ca658-501">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="ca658-502">El valor predeterminado es `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="ca658-502">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="ca658-503">**classlib**</span><span class="sxs-lookup"><span data-stu-id="ca658-503">**classlib**</span></span>

<span data-ttu-id="ca658-504">`-f|--framework`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="ca658-504">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="ca658-505">Valores: `netcoreapp1.0`, `netcoreapp1.1` o de `netstandard1.0` a `netstandard1.6`.</span><span class="sxs-lookup"><span data-stu-id="ca658-505">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="ca658-506">El valor predeterminado es `netstandard1.4`.</span><span class="sxs-lookup"><span data-stu-id="ca658-506">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="ca658-507">**mvc**</span><span class="sxs-lookup"><span data-stu-id="ca658-507">**mvc**</span></span>

<span data-ttu-id="ca658-508">`-f|--framework`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="ca658-508">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="ca658-509">Valores: `netcoreapp1.0` o `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="ca658-509">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="ca658-510">El valor predeterminado es `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="ca658-510">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="ca658-511">`-au|--auth`: el tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="ca658-511">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="ca658-512">Valores: `None` o `Individual`.</span><span class="sxs-lookup"><span data-stu-id="ca658-512">Values: `None` or `Individual`.</span></span> <span data-ttu-id="ca658-513">El valor predeterminado es `None`.</span><span class="sxs-lookup"><span data-stu-id="ca658-513">The default value is `None`.</span></span>

<span data-ttu-id="ca658-514">`-uld|--use-local-db`: especifica si se va a usar o no LocalDB en lugar de SQLite.</span><span class="sxs-lookup"><span data-stu-id="ca658-514">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="ca658-515">Valores: `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="ca658-515">Values: `true` or `false`.</span></span> <span data-ttu-id="ca658-516">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="ca658-516">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="ca658-517">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="ca658-517">Examples</span></span>

<span data-ttu-id="ca658-518">Creación de un proyecto de aplicación de consola con F# en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="ca658-518">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang F#`

<span data-ttu-id="ca658-519">Creación de un proyecto de biblioteca de clases de .NET Standard en el directorio especificado (disponible solo con el SDK de .NET Core 2.0 o versiones posteriores):</span><span class="sxs-lookup"><span data-stu-id="ca658-519">Create a .NET Standard class library project in the specified directory (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="ca658-520">Creación de un proyecto de aplicación MVC de ASP.NET Core C# en el directorio actual sin autenticación:</span><span class="sxs-lookup"><span data-stu-id="ca658-520">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication:</span></span>

`dotnet new mvc -au None`

<span data-ttu-id="ca658-521">Cree una aplicación de xUnit.</span><span class="sxs-lookup"><span data-stu-id="ca658-521">Create a new xUnit application:</span></span>

`dotnet new xunit`

<span data-ttu-id="ca658-522">Enumere todas las plantillas disponibles para MVC:</span><span class="sxs-lookup"><span data-stu-id="ca658-522">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

<span data-ttu-id="ca658-523">Instalación de la versión 2.0 de las plantillas Aplicación de página única para ASP.NET Core (opción de comando solo disponible para .NET Core SDK 1.1 y versiones posteriores):</span><span class="sxs-lookup"><span data-stu-id="ca658-523">Install version 2.0 of the Single Page Application templates for ASP.NET Core (command option available for .NET Core SDK 1.1 and later versions only):</span></span>

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

<span data-ttu-id="ca658-524">Creación de un archivo *global.json* en el directorio actual que establezca la versión del SDK en 2.0.0 (solo disponible en el SDK de .NET Core 2.0 o versiones posteriores):</span><span class="sxs-lookup"><span data-stu-id="ca658-524">Create a *global.json* in the current directory setting the SDK version to 2.0.0 (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new globaljson --sdk-version 2.0.0`

## <a name="see-also"></a><span data-ttu-id="ca658-525">Vea también</span><span class="sxs-lookup"><span data-stu-id="ca658-525">See also</span></span>

* <span data-ttu-id="ca658-526">[Custom templates for dotnet new](custom-templates.md) (Plantillas personalizadas para dotnet new)</span><span class="sxs-lookup"><span data-stu-id="ca658-526">[Custom templates for dotnet new](custom-templates.md)</span></span>  
* [<span data-ttu-id="ca658-527">Creación de una plantilla personalizada para dotnet new</span><span class="sxs-lookup"><span data-stu-id="ca658-527">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)  
* [<span data-ttu-id="ca658-528">Repositorio de GitHub dotnet/dotnet-template-samples</span><span class="sxs-lookup"><span data-stu-id="ca658-528">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)  
* <span data-ttu-id="ca658-529">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new) (Plantillas disponibles para dotnet new)</span><span class="sxs-lookup"><span data-stu-id="ca658-529">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)</span></span>
