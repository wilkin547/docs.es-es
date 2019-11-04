---
title: Comando dotnet new
description: El comando dotnet new crea proyectos de .NET Core basados en la plantilla especificada.
ms.date: 05/06/2019
ms.openlocfilehash: c9529e135f48c80f445c91038294a3e7266486f1
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "73420473"
---
# <a name="dotnet-new"></a><span data-ttu-id="7efda-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="7efda-103">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="7efda-104">Name</span><span class="sxs-lookup"><span data-stu-id="7efda-104">Name</span></span>

<span data-ttu-id="7efda-105">`dotnet new`: crea un nuevo proyecto, archivo de configuración o solución según la plantilla especificada.</span><span class="sxs-lookup"><span data-stu-id="7efda-105">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="7efda-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="7efda-106">Synopsis</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="7efda-107">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="7efda-107">.NET Core 2.2</span></span>](#tab/netcore22)

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="7efda-108">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="7efda-108">.NET Core 2.1</span></span>](#tab/netcore21)

```dotnetcli
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="7efda-109">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="7efda-109">.NET Core 2.0</span></span>](#tab/netcore20)

```dotnetcli
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="7efda-110">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="7efda-110">.NET Core 1.x</span></span>](#tab/netcore1x)

```dotnetcli
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="7efda-111">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="7efda-111">Description</span></span>

<span data-ttu-id="7efda-112">El comando `dotnet new` proporciona una manera cómoda de inicializar un proyecto .NET Core válido.</span><span class="sxs-lookup"><span data-stu-id="7efda-112">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span>

<span data-ttu-id="7efda-113">El comando llama al [motor de plantillas](https://github.com/dotnet/templating) para crear los artefactos en el disco basándose en las opciones y la plantilla especificadas.</span><span class="sxs-lookup"><span data-stu-id="7efda-113">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="7efda-114">Argumentos</span><span class="sxs-lookup"><span data-stu-id="7efda-114">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="7efda-115">La plantilla de la que se va a crear una instancia cuando se invoca el comando.</span><span class="sxs-lookup"><span data-stu-id="7efda-115">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="7efda-116">Cada plantilla puede tener opciones específicas que puede pasar.</span><span class="sxs-lookup"><span data-stu-id="7efda-116">Each template might have specific options you can pass.</span></span> <span data-ttu-id="7efda-117">Para obtener más información, vea [Opciones de plantilla](#template-options).</span><span class="sxs-lookup"><span data-stu-id="7efda-117">For more information, see [Template options](#template-options).</span></span>

<span data-ttu-id="7efda-118">Si el valor `TEMPLATE` no es una coincidencia exacta con el texto de la columna **Plantillas** o **Nombre corto**, se realiza una coincidencia de subcadena con esas dos columnas.</span><span class="sxs-lookup"><span data-stu-id="7efda-118">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column, a substring match is performed on those two columns.</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="7efda-119">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="7efda-119">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="7efda-120">El comando contiene una lista predeterminada de plantillas.</span><span class="sxs-lookup"><span data-stu-id="7efda-120">The command contains a default list of templates.</span></span> <span data-ttu-id="7efda-121">Use `dotnet new -l` para obtener una lista de las plantillas disponibles.</span><span class="sxs-lookup"><span data-stu-id="7efda-121">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="7efda-122">En la tabla siguiente se muestran las plantillas que vienen preinstaladas en el SDK de .NET Core 2.2.100.</span><span class="sxs-lookup"><span data-stu-id="7efda-122">The following table shows the templates that come pre-installed with the .NET Core SDK 2.2.100.</span></span> <span data-ttu-id="7efda-123">El lenguaje predeterminado de la plantilla se muestra entre corchetes.</span><span class="sxs-lookup"><span data-stu-id="7efda-123">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="7efda-124">Plantillas</span><span class="sxs-lookup"><span data-stu-id="7efda-124">Templates</span></span>                                    | <span data-ttu-id="7efda-125">Nombre corto</span><span class="sxs-lookup"><span data-stu-id="7efda-125">Short Name</span></span>        | <span data-ttu-id="7efda-126">Lenguaje</span><span class="sxs-lookup"><span data-stu-id="7efda-126">Language</span></span>     | <span data-ttu-id="7efda-127">Etiquetas</span><span class="sxs-lookup"><span data-stu-id="7efda-127">Tags</span></span>                                  |
|----------------------------------------------|-------------------|--------------|---------------------------------------|
| <span data-ttu-id="7efda-128">Aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="7efda-128">Console Application</span></span>                          | `console`         | <span data-ttu-id="7efda-129">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="7efda-129">[C#], F#, VB</span></span> | <span data-ttu-id="7efda-130">Común/Consola</span><span class="sxs-lookup"><span data-stu-id="7efda-130">Common/Console</span></span>                        |
| <span data-ttu-id="7efda-131">Biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="7efda-131">Class library</span></span>                                | `classlib`        | <span data-ttu-id="7efda-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="7efda-132">[C#], F#, VB</span></span> | <span data-ttu-id="7efda-133">Común/Biblioteca</span><span class="sxs-lookup"><span data-stu-id="7efda-133">Common/Library</span></span>                        |
| <span data-ttu-id="7efda-134">Proyecto de prueba unitaria</span><span class="sxs-lookup"><span data-stu-id="7efda-134">Unit Test Project</span></span>                            | `mstest`          | <span data-ttu-id="7efda-135">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="7efda-135">[C#], F#, VB</span></span> | <span data-ttu-id="7efda-136">Prueba/MSTest</span><span class="sxs-lookup"><span data-stu-id="7efda-136">Test/MSTest</span></span>                           |
| <span data-ttu-id="7efda-137">Proyecto de prueba de NUnit 3</span><span class="sxs-lookup"><span data-stu-id="7efda-137">NUnit 3 Test Project</span></span>                         | `nunit`           | <span data-ttu-id="7efda-138">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="7efda-138">[C#], F#, VB</span></span> | <span data-ttu-id="7efda-139">Prueba/NUnit</span><span class="sxs-lookup"><span data-stu-id="7efda-139">Test/NUnit</span></span>                            |
| <span data-ttu-id="7efda-140">Elemento de prueba de NUnit 3</span><span class="sxs-lookup"><span data-stu-id="7efda-140">NUnit 3 Test Item</span></span>                            | `nunit-test`      | <span data-ttu-id="7efda-141">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="7efda-141">[C#], F#, VB</span></span> | <span data-ttu-id="7efda-142">Prueba/NUnit</span><span class="sxs-lookup"><span data-stu-id="7efda-142">Test/NUnit</span></span>                            |
| <span data-ttu-id="7efda-143">Proyecto de prueba de xUnit</span><span class="sxs-lookup"><span data-stu-id="7efda-143">xUnit Test Project</span></span>                           | `xunit`           | <span data-ttu-id="7efda-144">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="7efda-144">[C#], F#, VB</span></span> | <span data-ttu-id="7efda-145">Prueba/xUnit</span><span class="sxs-lookup"><span data-stu-id="7efda-145">Test/xUnit</span></span>                            |
| <span data-ttu-id="7efda-146">Página de Razor</span><span class="sxs-lookup"><span data-stu-id="7efda-146">Razor Page</span></span>                                   | `page`            | <span data-ttu-id="7efda-147">[C#]</span><span class="sxs-lookup"><span data-stu-id="7efda-147">[C#]</span></span>         | <span data-ttu-id="7efda-148">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="7efda-148">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="7efda-149">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="7efda-149">MVC ViewImports</span></span>                              | `viewimports`     | <span data-ttu-id="7efda-150">[C#]</span><span class="sxs-lookup"><span data-stu-id="7efda-150">[C#]</span></span>         | <span data-ttu-id="7efda-151">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="7efda-151">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="7efda-152">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="7efda-152">MVC ViewStart</span></span>                                | `viewstart`       | <span data-ttu-id="7efda-153">[C#]</span><span class="sxs-lookup"><span data-stu-id="7efda-153">[C#]</span></span>         | <span data-ttu-id="7efda-154">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="7efda-154">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="7efda-155">Vacío de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="7efda-155">ASP.NET Core Empty</span></span>                           | `web`             | <span data-ttu-id="7efda-156">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="7efda-156">[C#], F#</span></span>     | <span data-ttu-id="7efda-157">Web/Vacío</span><span class="sxs-lookup"><span data-stu-id="7efda-157">Web/Empty</span></span>                             |
| <span data-ttu-id="7efda-158">Aplicación web de ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="7efda-158">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`             | <span data-ttu-id="7efda-159">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="7efda-159">[C#], F#</span></span>     | <span data-ttu-id="7efda-160">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="7efda-160">Web/MVC</span></span>                               |
| <span data-ttu-id="7efda-161">Aplicación web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="7efda-161">ASP.NET Core Web App</span></span>                         | <span data-ttu-id="7efda-162">`webapp`, `razor`</span><span class="sxs-lookup"><span data-stu-id="7efda-162">`webapp`, `razor`</span></span> | <span data-ttu-id="7efda-163">[C#]</span><span class="sxs-lookup"><span data-stu-id="7efda-163">[C#]</span></span>         | <span data-ttu-id="7efda-164">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="7efda-164">Web/MVC/Razor Pages</span></span>                   |
| <span data-ttu-id="7efda-165">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="7efda-165">ASP.NET Core with Angular</span></span>                    | `angular`         | <span data-ttu-id="7efda-166">[C#]</span><span class="sxs-lookup"><span data-stu-id="7efda-166">[C#]</span></span>         | <span data-ttu-id="7efda-167">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="7efda-167">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="7efda-168">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="7efda-168">ASP.NET Core with React.js</span></span>                   | `react`           | <span data-ttu-id="7efda-169">[C#]</span><span class="sxs-lookup"><span data-stu-id="7efda-169">[C#]</span></span>         | <span data-ttu-id="7efda-170">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="7efda-170">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="7efda-171">ASP.NET Core con React.js y Redux</span><span class="sxs-lookup"><span data-stu-id="7efda-171">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`      | <span data-ttu-id="7efda-172">[C#]</span><span class="sxs-lookup"><span data-stu-id="7efda-172">[C#]</span></span>         | <span data-ttu-id="7efda-173">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="7efda-173">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="7efda-174">Biblioteca de clases de Razor</span><span class="sxs-lookup"><span data-stu-id="7efda-174">Razor Class Library</span></span>                          | `razorclasslib`   | <span data-ttu-id="7efda-175">[C#]</span><span class="sxs-lookup"><span data-stu-id="7efda-175">[C#]</span></span>         | <span data-ttu-id="7efda-176">Web/Razor/Biblioteca/Biblioteca de clases de Razor</span><span class="sxs-lookup"><span data-stu-id="7efda-176">Web/Razor/Library/Razor Class Library</span></span> |
| <span data-ttu-id="7efda-177">API web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="7efda-177">ASP.NET Core Web API</span></span>                         | `webapi`          | <span data-ttu-id="7efda-178">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="7efda-178">[C#], F#</span></span>     | <span data-ttu-id="7efda-179">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="7efda-179">Web/WebAPI</span></span>                            |
| <span data-ttu-id="7efda-180">archivo global.json</span><span class="sxs-lookup"><span data-stu-id="7efda-180">global.json file</span></span>                             | `globaljson`      |              | <span data-ttu-id="7efda-181">Configuración</span><span class="sxs-lookup"><span data-stu-id="7efda-181">Config</span></span>                                |
| <span data-ttu-id="7efda-182">Configuración de NuGet</span><span class="sxs-lookup"><span data-stu-id="7efda-182">NuGet Config</span></span>                                 | `nugetconfig`     |              | <span data-ttu-id="7efda-183">Configuración</span><span class="sxs-lookup"><span data-stu-id="7efda-183">Config</span></span>                                |
| <span data-ttu-id="7efda-184">Configuración web</span><span class="sxs-lookup"><span data-stu-id="7efda-184">Web Config</span></span>                                   | `webconfig`       |              | <span data-ttu-id="7efda-185">Configuración</span><span class="sxs-lookup"><span data-stu-id="7efda-185">Config</span></span>                                |
| <span data-ttu-id="7efda-186">Archivo de solución</span><span class="sxs-lookup"><span data-stu-id="7efda-186">Solution File</span></span>                                | `sln`             |              | <span data-ttu-id="7efda-187">Soluciones</span><span class="sxs-lookup"><span data-stu-id="7efda-187">Solution</span></span>                              |

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="7efda-188">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="7efda-188">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="7efda-189">El comando contiene una lista predeterminada de plantillas.</span><span class="sxs-lookup"><span data-stu-id="7efda-189">The command contains a default list of templates.</span></span> <span data-ttu-id="7efda-190">Use `dotnet new -l` para obtener una lista de las plantillas disponibles.</span><span class="sxs-lookup"><span data-stu-id="7efda-190">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="7efda-191">En la tabla siguiente se muestran las plantillas que vienen preinstaladas con el SDK de .NET Core 2.1.300.</span><span class="sxs-lookup"><span data-stu-id="7efda-191">The following table shows the templates that come pre-installed with the .NET Core SDK 2.1.300.</span></span> <span data-ttu-id="7efda-192">El lenguaje predeterminado de la plantilla se muestra entre corchetes.</span><span class="sxs-lookup"><span data-stu-id="7efda-192">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="7efda-193">Plantillas</span><span class="sxs-lookup"><span data-stu-id="7efda-193">Templates</span></span>                                    | <span data-ttu-id="7efda-194">Nombre corto</span><span class="sxs-lookup"><span data-stu-id="7efda-194">Short Name</span></span>      | <span data-ttu-id="7efda-195">Lenguaje</span><span class="sxs-lookup"><span data-stu-id="7efda-195">Language</span></span>     | <span data-ttu-id="7efda-196">Etiquetas</span><span class="sxs-lookup"><span data-stu-id="7efda-196">Tags</span></span>                                  |
|----------------------------------------------|-----------------|--------------|---------------------------------------|
| <span data-ttu-id="7efda-197">Aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="7efda-197">Console Application</span></span>                          | `console`       | <span data-ttu-id="7efda-198">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="7efda-198">[C#], F#, VB</span></span> | <span data-ttu-id="7efda-199">Común/Consola</span><span class="sxs-lookup"><span data-stu-id="7efda-199">Common/Console</span></span>                        |
| <span data-ttu-id="7efda-200">Biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="7efda-200">Class library</span></span>                                | `classlib`      | <span data-ttu-id="7efda-201">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="7efda-201">[C#], F#, VB</span></span> | <span data-ttu-id="7efda-202">Común/Biblioteca</span><span class="sxs-lookup"><span data-stu-id="7efda-202">Common/Library</span></span>                        |
| <span data-ttu-id="7efda-203">Proyecto de prueba unitaria</span><span class="sxs-lookup"><span data-stu-id="7efda-203">Unit Test Project</span></span>                            | `mstest`        | <span data-ttu-id="7efda-204">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="7efda-204">[C#], F#, VB</span></span> | <span data-ttu-id="7efda-205">Prueba/MSTest</span><span class="sxs-lookup"><span data-stu-id="7efda-205">Test/MSTest</span></span>                           |
| <span data-ttu-id="7efda-206">Proyecto de prueba de xUnit</span><span class="sxs-lookup"><span data-stu-id="7efda-206">xUnit Test Project</span></span>                           | `xunit`         | <span data-ttu-id="7efda-207">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="7efda-207">[C#], F#, VB</span></span> | <span data-ttu-id="7efda-208">Prueba/xUnit</span><span class="sxs-lookup"><span data-stu-id="7efda-208">Test/xUnit</span></span>                            |
| <span data-ttu-id="7efda-209">Página de Razor</span><span class="sxs-lookup"><span data-stu-id="7efda-209">Razor Page</span></span>                                   | `page`          | <span data-ttu-id="7efda-210">[C#]</span><span class="sxs-lookup"><span data-stu-id="7efda-210">[C#]</span></span>         | <span data-ttu-id="7efda-211">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="7efda-211">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="7efda-212">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="7efda-212">MVC ViewImports</span></span>                              | `viewimports`   | <span data-ttu-id="7efda-213">[C#]</span><span class="sxs-lookup"><span data-stu-id="7efda-213">[C#]</span></span>         | <span data-ttu-id="7efda-214">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="7efda-214">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="7efda-215">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="7efda-215">MVC ViewStart</span></span>                                | `viewstart`     | <span data-ttu-id="7efda-216">[C#]</span><span class="sxs-lookup"><span data-stu-id="7efda-216">[C#]</span></span>         | <span data-ttu-id="7efda-217">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="7efda-217">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="7efda-218">Vacío de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="7efda-218">ASP.NET Core Empty</span></span>                           | `web`           | <span data-ttu-id="7efda-219">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="7efda-219">[C#], F#</span></span>     | <span data-ttu-id="7efda-220">Web/Vacío</span><span class="sxs-lookup"><span data-stu-id="7efda-220">Web/Empty</span></span>                             |
| <span data-ttu-id="7efda-221">Aplicación web de ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="7efda-221">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`           | <span data-ttu-id="7efda-222">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="7efda-222">[C#], F#</span></span>     | <span data-ttu-id="7efda-223">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="7efda-223">Web/MVC</span></span>                               |
| <span data-ttu-id="7efda-224">Aplicación web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="7efda-224">ASP.NET Core Web App</span></span>                         | `razor`         | <span data-ttu-id="7efda-225">[C#]</span><span class="sxs-lookup"><span data-stu-id="7efda-225">[C#]</span></span>         | <span data-ttu-id="7efda-226">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="7efda-226">Web/MVC/Razor Pages</span></span>                   |
| <span data-ttu-id="7efda-227">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="7efda-227">ASP.NET Core with Angular</span></span>                    | `angular`       | <span data-ttu-id="7efda-228">[C#]</span><span class="sxs-lookup"><span data-stu-id="7efda-228">[C#]</span></span>         | <span data-ttu-id="7efda-229">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="7efda-229">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="7efda-230">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="7efda-230">ASP.NET Core with React.js</span></span>                   | `react`         | <span data-ttu-id="7efda-231">[C#]</span><span class="sxs-lookup"><span data-stu-id="7efda-231">[C#]</span></span>         | <span data-ttu-id="7efda-232">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="7efda-232">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="7efda-233">ASP.NET Core con React.js y Redux</span><span class="sxs-lookup"><span data-stu-id="7efda-233">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`    | <span data-ttu-id="7efda-234">[C#]</span><span class="sxs-lookup"><span data-stu-id="7efda-234">[C#]</span></span>         | <span data-ttu-id="7efda-235">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="7efda-235">Web/MVC/SPA</span></span>                           | 
| <span data-ttu-id="7efda-236">Biblioteca de clases de Razor</span><span class="sxs-lookup"><span data-stu-id="7efda-236">Razor Class Library</span></span>                          | `razorclasslib` | <span data-ttu-id="7efda-237">[C#]</span><span class="sxs-lookup"><span data-stu-id="7efda-237">[C#]</span></span>         | <span data-ttu-id="7efda-238">Web/Razor/Biblioteca/Biblioteca de clases de Razor</span><span class="sxs-lookup"><span data-stu-id="7efda-238">Web/Razor/Library/Razor Class Library</span></span> |
| <span data-ttu-id="7efda-239">API web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="7efda-239">ASP.NET Core Web API</span></span>                         | `webapi`        | <span data-ttu-id="7efda-240">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="7efda-240">[C#], F#</span></span>     | <span data-ttu-id="7efda-241">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="7efda-241">Web/WebAPI</span></span>                            |
| <span data-ttu-id="7efda-242">archivo global.json</span><span class="sxs-lookup"><span data-stu-id="7efda-242">global.json file</span></span>                             | `globaljson`    |              | <span data-ttu-id="7efda-243">Configuración</span><span class="sxs-lookup"><span data-stu-id="7efda-243">Config</span></span>                                |
| <span data-ttu-id="7efda-244">Configuración de NuGet</span><span class="sxs-lookup"><span data-stu-id="7efda-244">NuGet Config</span></span>                                 | `nugetconfig`   |              | <span data-ttu-id="7efda-245">Configuración</span><span class="sxs-lookup"><span data-stu-id="7efda-245">Config</span></span>                                |
| <span data-ttu-id="7efda-246">Configuración web</span><span class="sxs-lookup"><span data-stu-id="7efda-246">Web Config</span></span>                                   | `webconfig`     |              | <span data-ttu-id="7efda-247">Configuración</span><span class="sxs-lookup"><span data-stu-id="7efda-247">Config</span></span>                                |
| <span data-ttu-id="7efda-248">Archivo de solución</span><span class="sxs-lookup"><span data-stu-id="7efda-248">Solution File</span></span>                                | `sln`           |              | <span data-ttu-id="7efda-249">Soluciones</span><span class="sxs-lookup"><span data-stu-id="7efda-249">Solution</span></span>                              |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="7efda-250">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="7efda-250">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="7efda-251">El comando contiene una lista predeterminada de plantillas.</span><span class="sxs-lookup"><span data-stu-id="7efda-251">The command contains a default list of templates.</span></span> <span data-ttu-id="7efda-252">Use `dotnet new -l` para obtener una lista de las plantillas disponibles.</span><span class="sxs-lookup"><span data-stu-id="7efda-252">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="7efda-253">En la tabla siguiente se muestran las plantillas que vienen preinstaladas en el SDK de .NET Core 2.0.0.</span><span class="sxs-lookup"><span data-stu-id="7efda-253">The following table shows the templates that come pre-installed with the .NET Core SDK 2.0.0.</span></span> <span data-ttu-id="7efda-254">El lenguaje predeterminado de la plantilla se muestra entre corchetes.</span><span class="sxs-lookup"><span data-stu-id="7efda-254">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="7efda-255">Plantillas</span><span class="sxs-lookup"><span data-stu-id="7efda-255">Templates</span></span>                                    | <span data-ttu-id="7efda-256">Nombre corto</span><span class="sxs-lookup"><span data-stu-id="7efda-256">Short Name</span></span>    | <span data-ttu-id="7efda-257">Lenguaje</span><span class="sxs-lookup"><span data-stu-id="7efda-257">Language</span></span>     | <span data-ttu-id="7efda-258">Etiquetas</span><span class="sxs-lookup"><span data-stu-id="7efda-258">Tags</span></span>                |
|----------------------------------------------|---------------|--------------|---------------------|
| <span data-ttu-id="7efda-259">Aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="7efda-259">Console Application</span></span>                          | `console`     | <span data-ttu-id="7efda-260">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="7efda-260">[C#], F#, VB</span></span> | <span data-ttu-id="7efda-261">Común/Consola</span><span class="sxs-lookup"><span data-stu-id="7efda-261">Common/Console</span></span>      |
| <span data-ttu-id="7efda-262">Biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="7efda-262">Class library</span></span>                                | `classlib`    | <span data-ttu-id="7efda-263">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="7efda-263">[C#], F#, VB</span></span> | <span data-ttu-id="7efda-264">Común/Biblioteca</span><span class="sxs-lookup"><span data-stu-id="7efda-264">Common/Library</span></span>      |
| <span data-ttu-id="7efda-265">Proyecto de prueba unitaria</span><span class="sxs-lookup"><span data-stu-id="7efda-265">Unit Test Project</span></span>                            | `mstest`      | <span data-ttu-id="7efda-266">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="7efda-266">[C#], F#, VB</span></span> | <span data-ttu-id="7efda-267">Prueba/MSTest</span><span class="sxs-lookup"><span data-stu-id="7efda-267">Test/MSTest</span></span>         |
| <span data-ttu-id="7efda-268">Proyecto de prueba de xUnit</span><span class="sxs-lookup"><span data-stu-id="7efda-268">xUnit Test Project</span></span>                           | `xunit`       | <span data-ttu-id="7efda-269">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="7efda-269">[C#], F#, VB</span></span> | <span data-ttu-id="7efda-270">Prueba/xUnit</span><span class="sxs-lookup"><span data-stu-id="7efda-270">Test/xUnit</span></span>          |
| <span data-ttu-id="7efda-271">Vacío de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="7efda-271">ASP.NET Core Empty</span></span>                           | `web`         | <span data-ttu-id="7efda-272">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="7efda-272">[C#], F#</span></span>     | <span data-ttu-id="7efda-273">Web/Vacío</span><span class="sxs-lookup"><span data-stu-id="7efda-273">Web/Empty</span></span>           |
| <span data-ttu-id="7efda-274">Aplicación web de ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="7efda-274">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="7efda-275">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="7efda-275">[C#], F#</span></span>     | <span data-ttu-id="7efda-276">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="7efda-276">Web/MVC</span></span>             |
| <span data-ttu-id="7efda-277">Aplicación web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="7efda-277">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="7efda-278">[C#]</span><span class="sxs-lookup"><span data-stu-id="7efda-278">[C#]</span></span>         | <span data-ttu-id="7efda-279">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="7efda-279">Web/MVC/Razor Pages</span></span> |
| <span data-ttu-id="7efda-280">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="7efda-280">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="7efda-281">[C#]</span><span class="sxs-lookup"><span data-stu-id="7efda-281">[C#]</span></span>         | <span data-ttu-id="7efda-282">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="7efda-282">Web/MVC/SPA</span></span>         |
| <span data-ttu-id="7efda-283">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="7efda-283">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="7efda-284">[C#]</span><span class="sxs-lookup"><span data-stu-id="7efda-284">[C#]</span></span>         | <span data-ttu-id="7efda-285">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="7efda-285">Web/MVC/SPA</span></span>         |
| <span data-ttu-id="7efda-286">ASP.NET Core con React.js y Redux</span><span class="sxs-lookup"><span data-stu-id="7efda-286">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="7efda-287">[C#]</span><span class="sxs-lookup"><span data-stu-id="7efda-287">[C#]</span></span>         | <span data-ttu-id="7efda-288">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="7efda-288">Web/MVC/SPA</span></span>         |
| <span data-ttu-id="7efda-289">API web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="7efda-289">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="7efda-290">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="7efda-290">[C#], F#</span></span>     | <span data-ttu-id="7efda-291">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="7efda-291">Web/WebAPI</span></span>          |
| <span data-ttu-id="7efda-292">archivo global.json</span><span class="sxs-lookup"><span data-stu-id="7efda-292">global.json file</span></span>                             | `globaljson`  |              | <span data-ttu-id="7efda-293">Configuración</span><span class="sxs-lookup"><span data-stu-id="7efda-293">Config</span></span>              |
| <span data-ttu-id="7efda-294">Configuración de NuGet</span><span class="sxs-lookup"><span data-stu-id="7efda-294">Nuget Config</span></span>                                 | `nugetconfig` |              | <span data-ttu-id="7efda-295">Configuración</span><span class="sxs-lookup"><span data-stu-id="7efda-295">Config</span></span>              |
| <span data-ttu-id="7efda-296">Configuración web</span><span class="sxs-lookup"><span data-stu-id="7efda-296">Web Config</span></span>                                   | `webconfig`   |              | <span data-ttu-id="7efda-297">Configuración</span><span class="sxs-lookup"><span data-stu-id="7efda-297">Config</span></span>              |
| <span data-ttu-id="7efda-298">Archivo de solución</span><span class="sxs-lookup"><span data-stu-id="7efda-298">Solution File</span></span>                                | `sln`         |              | <span data-ttu-id="7efda-299">Soluciones</span><span class="sxs-lookup"><span data-stu-id="7efda-299">Solution</span></span>            |
| <span data-ttu-id="7efda-300">Página de Razor</span><span class="sxs-lookup"><span data-stu-id="7efda-300">Razor Page</span></span>                                   | `page`        |              | <span data-ttu-id="7efda-301">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="7efda-301">Web/ASP.NET</span></span>         |
| <span data-ttu-id="7efda-302">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="7efda-302">MVC ViewImports</span></span>                              | `viewimports` |              | <span data-ttu-id="7efda-303">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="7efda-303">Web/ASP.NET</span></span>         |
| <span data-ttu-id="7efda-304">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="7efda-304">MVC ViewStart</span></span>                                | `viewstart`   |              | <span data-ttu-id="7efda-305">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="7efda-305">Web/ASP.NET</span></span>         |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="7efda-306">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="7efda-306">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="7efda-307">El comando contiene una lista predeterminada de plantillas.</span><span class="sxs-lookup"><span data-stu-id="7efda-307">The command contains a default list of templates.</span></span> <span data-ttu-id="7efda-308">Use `dotnet new -all` para obtener una lista de las plantillas disponibles.</span><span class="sxs-lookup"><span data-stu-id="7efda-308">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="7efda-309">En la tabla siguiente se muestran las plantillas que vienen preinstaladas en el SDK de .NET Core 1.0.1.</span><span class="sxs-lookup"><span data-stu-id="7efda-309">The following table shows the templates that come pre-installed with the .NET Core SDK 1.0.1.</span></span> <span data-ttu-id="7efda-310">El lenguaje predeterminado de la plantilla se muestra entre corchetes.</span><span class="sxs-lookup"><span data-stu-id="7efda-310">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="7efda-311">Plantillas</span><span class="sxs-lookup"><span data-stu-id="7efda-311">Templates</span></span>            | <span data-ttu-id="7efda-312">Nombre corto</span><span class="sxs-lookup"><span data-stu-id="7efda-312">Short Name</span></span>    | <span data-ttu-id="7efda-313">Lenguaje</span><span class="sxs-lookup"><span data-stu-id="7efda-313">Language</span></span> | <span data-ttu-id="7efda-314">Etiquetas</span><span class="sxs-lookup"><span data-stu-id="7efda-314">Tags</span></span>           |
|----------------------|---------------|----------|----------------|
| <span data-ttu-id="7efda-315">Aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="7efda-315">Console Application</span></span>  | `console`     | <span data-ttu-id="7efda-316">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="7efda-316">[C#], F#</span></span> | <span data-ttu-id="7efda-317">Común/Consola</span><span class="sxs-lookup"><span data-stu-id="7efda-317">Common/Console</span></span> |
| <span data-ttu-id="7efda-318">Biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="7efda-318">Class library</span></span>        | `classlib`    | <span data-ttu-id="7efda-319">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="7efda-319">[C#], F#</span></span> | <span data-ttu-id="7efda-320">Común/Biblioteca</span><span class="sxs-lookup"><span data-stu-id="7efda-320">Common/Library</span></span> |
| <span data-ttu-id="7efda-321">Proyecto de prueba unitaria</span><span class="sxs-lookup"><span data-stu-id="7efda-321">Unit Test Project</span></span>    | `mstest`      | <span data-ttu-id="7efda-322">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="7efda-322">[C#], F#</span></span> | <span data-ttu-id="7efda-323">Prueba/MSTest</span><span class="sxs-lookup"><span data-stu-id="7efda-323">Test/MSTest</span></span>    |
| <span data-ttu-id="7efda-324">Proyecto de prueba de xUnit</span><span class="sxs-lookup"><span data-stu-id="7efda-324">xUnit Test Project</span></span>   | `xunit`       | <span data-ttu-id="7efda-325">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="7efda-325">[C#], F#</span></span> | <span data-ttu-id="7efda-326">Prueba/xUnit</span><span class="sxs-lookup"><span data-stu-id="7efda-326">Test/xUnit</span></span>     |
| <span data-ttu-id="7efda-327">Vacío de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="7efda-327">ASP.NET Core Empty</span></span>   | `web`         | <span data-ttu-id="7efda-328">[C#]</span><span class="sxs-lookup"><span data-stu-id="7efda-328">[C#]</span></span>     | <span data-ttu-id="7efda-329">Web/Vacío</span><span class="sxs-lookup"><span data-stu-id="7efda-329">Web/Empty</span></span>      |
| <span data-ttu-id="7efda-330">Aplicación web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="7efda-330">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="7efda-331">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="7efda-331">[C#], F#</span></span> | <span data-ttu-id="7efda-332">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="7efda-332">Web/MVC</span></span>        |
| <span data-ttu-id="7efda-333">API web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="7efda-333">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="7efda-334">[C#]</span><span class="sxs-lookup"><span data-stu-id="7efda-334">[C#]</span></span>     | <span data-ttu-id="7efda-335">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="7efda-335">Web/WebAPI</span></span>     |
| <span data-ttu-id="7efda-336">Configuración de NuGet</span><span class="sxs-lookup"><span data-stu-id="7efda-336">Nuget Config</span></span>         | `nugetconfig` |          | <span data-ttu-id="7efda-337">Configuración</span><span class="sxs-lookup"><span data-stu-id="7efda-337">Config</span></span>         |
| <span data-ttu-id="7efda-338">Configuración web</span><span class="sxs-lookup"><span data-stu-id="7efda-338">Web Config</span></span>           | `webconfig`   |          | <span data-ttu-id="7efda-339">Configuración</span><span class="sxs-lookup"><span data-stu-id="7efda-339">Config</span></span>         |
| <span data-ttu-id="7efda-340">Archivo de solución</span><span class="sxs-lookup"><span data-stu-id="7efda-340">Solution File</span></span>        | `sln`         |          | <span data-ttu-id="7efda-341">Soluciones</span><span class="sxs-lookup"><span data-stu-id="7efda-341">Solution</span></span>       |

---

## <a name="options"></a><span data-ttu-id="7efda-342">Opciones</span><span class="sxs-lookup"><span data-stu-id="7efda-342">Options</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="7efda-343">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="7efda-343">.NET Core 2.2</span></span>](#tab/netcore22)

`--dry-run`

<span data-ttu-id="7efda-344">Muestra un resumen de lo que sucedería si se ejecutara el comando determinado y el resultado fuera la creación de una plantilla.</span><span class="sxs-lookup"><span data-stu-id="7efda-344">Displays a summary of what would happen if the given command were run if it would result in a template creation.</span></span>

`--force`

<span data-ttu-id="7efda-345">Fuerza la generación de contenido incluso aunque se vayan a cambiar los archivos existentes.</span><span class="sxs-lookup"><span data-stu-id="7efda-345">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="7efda-346">Esto es necesario cuando el directorio de salida ya contiene un proyecto.</span><span class="sxs-lookup"><span data-stu-id="7efda-346">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="7efda-347">Imprime la ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="7efda-347">Prints out help for the command.</span></span> <span data-ttu-id="7efda-348">Puede invocarse para el propio comando `dotnet new` o para cualquier plantilla, como `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="7efda-348">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="7efda-349">Instala un paquete de plantillas u origen desde los parámetros `PATH` o `NUGET_ID` proporcionados.</span><span class="sxs-lookup"><span data-stu-id="7efda-349">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="7efda-350">Si quiere instalar una versión preliminar de un paquete de plantilla, tendrá que especificar la versión en el formato de `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="7efda-350">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="7efda-351">De manera predeterminada, `dotnet new` pasa \* para la versión, que representa la última versión estable del paquete.</span><span class="sxs-lookup"><span data-stu-id="7efda-351">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="7efda-352">Vea un ejemplo en la sección [Ejemplos](#examples).</span><span class="sxs-lookup"><span data-stu-id="7efda-352">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="7efda-353">Para obtener información sobre cómo crear plantillas personalizadas, consulte [Custom templates for dotnet new](custom-templates.md) (Plantillas personalizadas para dotnet new).</span><span class="sxs-lookup"><span data-stu-id="7efda-353">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="7efda-354">Muestra las plantillas que contienen el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="7efda-354">Lists templates containing the specified name.</span></span> <span data-ttu-id="7efda-355">Si se invoca para el comando `dotnet new`, muestra las plantillas posibles disponibles para un directorio determinado.</span><span class="sxs-lookup"><span data-stu-id="7efda-355">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="7efda-356">Por ejemplo, si el directorio ya contiene un proyecto, no mostrará todas las plantillas del proyecto.</span><span class="sxs-lookup"><span data-stu-id="7efda-356">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="7efda-357">El lenguaje de la plantilla que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="7efda-357">The language of the template to create.</span></span> <span data-ttu-id="7efda-358">El lenguaje aceptado cambia según la plantilla (vea los valores predeterminados en la sección [argumentos](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="7efda-358">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="7efda-359">No es válido para algunas plantillas.</span><span class="sxs-lookup"><span data-stu-id="7efda-359">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="7efda-360">Algunos shells interpretan `#` como un carácter especial.</span><span class="sxs-lookup"><span data-stu-id="7efda-360">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="7efda-361">En esos casos, debe incluir el valor del parámetro de lenguaje, como `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="7efda-361">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="7efda-362">El nombre de la salida creada.</span><span class="sxs-lookup"><span data-stu-id="7efda-362">The name for the created output.</span></span> <span data-ttu-id="7efda-363">Si no se especifica ningún nombre, se usa el nombre del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="7efda-363">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="7efda-364">Especifica un origen de NuGet para usarlo durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="7efda-364">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="7efda-365">La ubicación para colocar la salida generada.</span><span class="sxs-lookup"><span data-stu-id="7efda-365">Location to place the generated output.</span></span> <span data-ttu-id="7efda-366">El valor predeterminado es el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="7efda-366">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="7efda-367">Filtra plantillas en función de los tipos disponibles.</span><span class="sxs-lookup"><span data-stu-id="7efda-367">Filters templates based on available types.</span></span> <span data-ttu-id="7efda-368">Los valores predefinidos son "project", "item" u "other".</span><span class="sxs-lookup"><span data-stu-id="7efda-368">Predefined values are "project", "item", or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="7efda-369">Desinstala un paquete de plantillas u origen en los parámetros `PATH` o `NUGET_ID` proporcionados.</span><span class="sxs-lookup"><span data-stu-id="7efda-369">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="7efda-370">Al excluir el valor `<PATH|NUGET_ID>`, se muestran todos los paquetes de plantillas instalados actualmente y sus plantillas asociadas.</span><span class="sxs-lookup"><span data-stu-id="7efda-370">When excluding the `<PATH|NUGET_ID>` value, all currently installed template packs and their associated templates are displayed.</span></span>

> [!NOTE]
> <span data-ttu-id="7efda-371">Para desinstalar una plantilla mediante `PATH`, debe usar el nombre completo de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="7efda-371">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="7efda-372">Por ejemplo, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* funcionará, pero *./GarciaSoftware.ConsoleTemplate.CSharp* desde la carpeta contenedora no lo hará.</span><span class="sxs-lookup"><span data-stu-id="7efda-372">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="7efda-373">Además, no debe incluir una barra diagonal para finalizar el directorio en la ruta de acceso a la plantilla.</span><span class="sxs-lookup"><span data-stu-id="7efda-373">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="7efda-374">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="7efda-374">.NET Core 2.1</span></span>](#tab/netcore21)

`--force`

<span data-ttu-id="7efda-375">Fuerza la generación de contenido incluso aunque se vayan a cambiar los archivos existentes.</span><span class="sxs-lookup"><span data-stu-id="7efda-375">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="7efda-376">Esto es necesario cuando el directorio de salida ya contiene un proyecto.</span><span class="sxs-lookup"><span data-stu-id="7efda-376">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="7efda-377">Imprime la ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="7efda-377">Prints out help for the command.</span></span> <span data-ttu-id="7efda-378">Puede invocarse para el propio comando `dotnet new` o para cualquier plantilla, como `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="7efda-378">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="7efda-379">Instala un paquete de plantillas u origen desde los parámetros `PATH` o `NUGET_ID` proporcionados.</span><span class="sxs-lookup"><span data-stu-id="7efda-379">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="7efda-380">Si quiere instalar una versión preliminar de un paquete de plantilla, tendrá que especificar la versión en el formato de `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="7efda-380">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="7efda-381">De manera predeterminada, `dotnet new` pasa \* para la versión, que representa la última versión estable del paquete.</span><span class="sxs-lookup"><span data-stu-id="7efda-381">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="7efda-382">Vea un ejemplo en la sección [Ejemplos](#examples).</span><span class="sxs-lookup"><span data-stu-id="7efda-382">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="7efda-383">Para obtener información sobre cómo crear plantillas personalizadas, consulte [Custom templates for dotnet new](custom-templates.md) (Plantillas personalizadas para dotnet new).</span><span class="sxs-lookup"><span data-stu-id="7efda-383">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="7efda-384">Muestra las plantillas que contienen el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="7efda-384">Lists templates containing the specified name.</span></span> <span data-ttu-id="7efda-385">Si se invoca para el comando `dotnet new`, muestra las plantillas posibles disponibles para un directorio determinado.</span><span class="sxs-lookup"><span data-stu-id="7efda-385">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="7efda-386">Por ejemplo, si el directorio ya contiene un proyecto, no mostrará todas las plantillas del proyecto.</span><span class="sxs-lookup"><span data-stu-id="7efda-386">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="7efda-387">El lenguaje de la plantilla que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="7efda-387">The language of the template to create.</span></span> <span data-ttu-id="7efda-388">El lenguaje aceptado cambia según la plantilla (vea los valores predeterminados en la sección [argumentos](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="7efda-388">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="7efda-389">No es válido para algunas plantillas.</span><span class="sxs-lookup"><span data-stu-id="7efda-389">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="7efda-390">Algunos shells interpretan `#` como un carácter especial.</span><span class="sxs-lookup"><span data-stu-id="7efda-390">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="7efda-391">En esos casos, debe incluir el valor del parámetro de lenguaje, como `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="7efda-391">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="7efda-392">El nombre de la salida creada.</span><span class="sxs-lookup"><span data-stu-id="7efda-392">The name for the created output.</span></span> <span data-ttu-id="7efda-393">Si no se especifica ningún nombre, se usa el nombre del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="7efda-393">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="7efda-394">Especifica un origen de NuGet para usarlo durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="7efda-394">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="7efda-395">La ubicación para colocar la salida generada.</span><span class="sxs-lookup"><span data-stu-id="7efda-395">Location to place the generated output.</span></span> <span data-ttu-id="7efda-396">El valor predeterminado es el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="7efda-396">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="7efda-397">Filtra plantillas en función de los tipos disponibles.</span><span class="sxs-lookup"><span data-stu-id="7efda-397">Filters templates based on available types.</span></span> <span data-ttu-id="7efda-398">Los valores predefinidos son “project”, “item” y “other”.</span><span class="sxs-lookup"><span data-stu-id="7efda-398">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="7efda-399">Desinstala un paquete de plantillas u origen en los parámetros `PATH` o `NUGET_ID` proporcionados.</span><span class="sxs-lookup"><span data-stu-id="7efda-399">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="7efda-400">Para desinstalar una plantilla mediante `PATH`, debe usar el nombre completo de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="7efda-400">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="7efda-401">Por ejemplo, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* funcionará, pero *./GarciaSoftware.ConsoleTemplate.CSharp* desde la carpeta contenedora no lo hará.</span><span class="sxs-lookup"><span data-stu-id="7efda-401">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="7efda-402">Además, no debe incluir una barra diagonal para finalizar el directorio en la ruta de acceso a la plantilla.</span><span class="sxs-lookup"><span data-stu-id="7efda-402">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="7efda-403">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="7efda-403">.NET Core 2.0</span></span>](#tab/netcore20)

`--force`

<span data-ttu-id="7efda-404">Fuerza la generación de contenido incluso aunque se vayan a cambiar los archivos existentes.</span><span class="sxs-lookup"><span data-stu-id="7efda-404">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="7efda-405">Esto es necesario cuando el directorio de salida ya contiene un proyecto.</span><span class="sxs-lookup"><span data-stu-id="7efda-405">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="7efda-406">Imprime la ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="7efda-406">Prints out help for the command.</span></span> <span data-ttu-id="7efda-407">Puede invocarse para el propio comando `dotnet new` o para cualquier plantilla, como `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="7efda-407">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="7efda-408">Instala un paquete de plantillas u origen desde los parámetros `PATH` o `NUGET_ID` proporcionados.</span><span class="sxs-lookup"><span data-stu-id="7efda-408">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="7efda-409">Si quiere instalar una versión preliminar de un paquete de plantilla, tendrá que especificar la versión en el formato de `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="7efda-409">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="7efda-410">De manera predeterminada, `dotnet new` pasa \* para la versión, que representa la última versión estable del paquete.</span><span class="sxs-lookup"><span data-stu-id="7efda-410">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="7efda-411">Vea un ejemplo en la sección [Ejemplos](#examples).</span><span class="sxs-lookup"><span data-stu-id="7efda-411">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="7efda-412">Para obtener información sobre cómo crear plantillas personalizadas, consulte [Custom templates for dotnet new](custom-templates.md) (Plantillas personalizadas para dotnet new).</span><span class="sxs-lookup"><span data-stu-id="7efda-412">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="7efda-413">Muestra las plantillas que contienen el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="7efda-413">Lists templates containing the specified name.</span></span> <span data-ttu-id="7efda-414">Si se invoca para el comando `dotnet new`, muestra las plantillas posibles disponibles para un directorio determinado.</span><span class="sxs-lookup"><span data-stu-id="7efda-414">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="7efda-415">Por ejemplo, si el directorio ya contiene un proyecto, no mostrará todas las plantillas del proyecto.</span><span class="sxs-lookup"><span data-stu-id="7efda-415">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="7efda-416">El lenguaje de la plantilla que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="7efda-416">The language of the template to create.</span></span> <span data-ttu-id="7efda-417">El lenguaje aceptado cambia según la plantilla (vea los valores predeterminados en la sección [argumentos](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="7efda-417">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="7efda-418">No es válido para algunas plantillas.</span><span class="sxs-lookup"><span data-stu-id="7efda-418">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="7efda-419">Algunos shells interpretan `#` como un carácter especial.</span><span class="sxs-lookup"><span data-stu-id="7efda-419">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="7efda-420">En esos casos, debe incluir el valor del parámetro de lenguaje, como `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="7efda-420">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="7efda-421">El nombre de la salida creada.</span><span class="sxs-lookup"><span data-stu-id="7efda-421">The name for the created output.</span></span> <span data-ttu-id="7efda-422">Si no se especifica ningún nombre, se usa el nombre del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="7efda-422">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="7efda-423">La ubicación para colocar la salida generada.</span><span class="sxs-lookup"><span data-stu-id="7efda-423">Location to place the generated output.</span></span> <span data-ttu-id="7efda-424">El valor predeterminado es el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="7efda-424">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="7efda-425">Filtra plantillas en función de los tipos disponibles.</span><span class="sxs-lookup"><span data-stu-id="7efda-425">Filters templates based on available types.</span></span> <span data-ttu-id="7efda-426">Los valores predefinidos son “project”, “item” y “other”.</span><span class="sxs-lookup"><span data-stu-id="7efda-426">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="7efda-427">Desinstala un paquete de plantillas u origen en los parámetros `PATH` o `NUGET_ID` proporcionados.</span><span class="sxs-lookup"><span data-stu-id="7efda-427">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="7efda-428">Para desinstalar una plantilla mediante un origen `PATH`, debe usar el nombre completo de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="7efda-428">To uninstall a template using a source `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="7efda-429">Por ejemplo, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* funcionará, pero *./GarciaSoftware.ConsoleTemplate.CSharp* desde la carpeta contenedora no lo hará.</span><span class="sxs-lookup"><span data-stu-id="7efda-429">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span> <span data-ttu-id="7efda-430">Además, no debe incluir una barra diagonal para finalizar el directorio en la ruta de acceso a la plantilla.</span><span class="sxs-lookup"><span data-stu-id="7efda-430">Additionally, do not include a final terminating directory slash on your template path.</span></span>
> 
> <span data-ttu-id="7efda-431">Si no puede determinar el argumento `PATH` o `NUGET_ID` necesario para desinstalar una plantilla, la ejecución de `dotnet new --uninstall` sin un argumento enumerará todas las plantillas instaladas y el argumento requerido para desinstalarlas.</span><span class="sxs-lookup"><span data-stu-id="7efda-431">If you are unable to determine the `PATH` or `NUGET_ID` argument needed to uninstall a template, running `dotnet new --uninstall` without an argument will list all installed templates and the argument required to uninstall them.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="7efda-432">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="7efda-432">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="7efda-433">Muestra todas las plantillas de un tipo de proyecto específico cuando se ejecuta en el contexto del comando `dotnet new` por sí solo.</span><span class="sxs-lookup"><span data-stu-id="7efda-433">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="7efda-434">Cuando se ejecuta en el contexto de una plantilla específica, como `dotnet new web -all`, `-all` se interpreta como una marca para forzar la creación.</span><span class="sxs-lookup"><span data-stu-id="7efda-434">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="7efda-435">Esto es necesario cuando el directorio de salida ya contiene un proyecto.</span><span class="sxs-lookup"><span data-stu-id="7efda-435">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="7efda-436">Imprime la ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="7efda-436">Prints out help for the command.</span></span> <span data-ttu-id="7efda-437">Puede invocarse para el propio comando `dotnet new` o para cualquier plantilla, como `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="7efda-437">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="7efda-438">Muestra las plantillas que contienen el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="7efda-438">Lists templates containing the specified name.</span></span> <span data-ttu-id="7efda-439">Si se invoca para el comando `dotnet new`, muestra las plantillas posibles disponibles para un directorio determinado.</span><span class="sxs-lookup"><span data-stu-id="7efda-439">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="7efda-440">Por ejemplo, si el directorio ya contiene un proyecto, no mostrará todas las plantillas del proyecto.</span><span class="sxs-lookup"><span data-stu-id="7efda-440">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="7efda-441">El lenguaje de la plantilla que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="7efda-441">The language of the template to create.</span></span> <span data-ttu-id="7efda-442">El lenguaje aceptado cambia según la plantilla (vea los valores predeterminados en la sección [argumentos](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="7efda-442">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="7efda-443">No es válido para algunas plantillas.</span><span class="sxs-lookup"><span data-stu-id="7efda-443">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="7efda-444">Algunos shells interpretan `#` como un carácter especial.</span><span class="sxs-lookup"><span data-stu-id="7efda-444">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="7efda-445">En esos casos, debe incluir el valor del parámetro de lenguaje, como `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="7efda-445">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="7efda-446">El nombre de la salida creada.</span><span class="sxs-lookup"><span data-stu-id="7efda-446">The name for the created output.</span></span> <span data-ttu-id="7efda-447">Si no se especifica ningún nombre, se usa el nombre del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="7efda-447">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="7efda-448">La ubicación para colocar la salida generada.</span><span class="sxs-lookup"><span data-stu-id="7efda-448">Location to place the generated output.</span></span> <span data-ttu-id="7efda-449">El valor predeterminado es el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="7efda-449">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="7efda-450">Opciones de plantilla</span><span class="sxs-lookup"><span data-stu-id="7efda-450">Template options</span></span>

<span data-ttu-id="7efda-451">Cada plantilla de proyecto puede tener opciones adicionales disponibles.</span><span class="sxs-lookup"><span data-stu-id="7efda-451">Each project template may have additional options available.</span></span> <span data-ttu-id="7efda-452">Las plantillas principales tienen las siguientes opciones adicionales:</span><span class="sxs-lookup"><span data-stu-id="7efda-452">The core templates have the following additional options:</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="7efda-453">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="7efda-453">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="7efda-454">**console**</span><span class="sxs-lookup"><span data-stu-id="7efda-454">**console**</span></span>

<span data-ttu-id="7efda-455">`--langVersion <VERSION_NUMBER>`: establece la propiedad `LangVersion` en el archivo de proyecto creado.</span><span class="sxs-lookup"><span data-stu-id="7efda-455">`--langVersion <VERSION_NUMBER>` - Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="7efda-456">Por ejemplo, use `--langVersion 7.3` para emplear C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="7efda-456">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="7efda-457">No es compatible con F#.</span><span class="sxs-lookup"><span data-stu-id="7efda-457">Not supported for F#.</span></span>

<span data-ttu-id="7efda-458">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="7efda-458">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="7efda-459">**angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="7efda-459">**angular, react, reactredux**</span></span>

<span data-ttu-id="7efda-460">`--exclude-launch-settings`: excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="7efda-460">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="7efda-461">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="7efda-461">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="7efda-462">`--no-https`: el proyecto no requiere HTTPS.</span><span class="sxs-lookup"><span data-stu-id="7efda-462">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="7efda-463">Esta opción solo se aplica si no se usan `IndividualAuth` u `OrganizationalAuth`.</span><span class="sxs-lookup"><span data-stu-id="7efda-463">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="7efda-464">**razorclasslib**</span><span class="sxs-lookup"><span data-stu-id="7efda-464">**razorclasslib**</span></span>

<span data-ttu-id="7efda-465">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="7efda-465">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="7efda-466">**classlib**</span><span class="sxs-lookup"><span data-stu-id="7efda-466">**classlib**</span></span>

<span data-ttu-id="7efda-467">`-f|--framework <FRAMEWORK>`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="7efda-467">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="7efda-468">Valores: `netcoreapp2.2` para crear una biblioteca de clases de .NET Core o `netstandard2.0` para crear una biblioteca de clases de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="7efda-468">Values: `netcoreapp2.2` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="7efda-469">El valor predeterminado es `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="7efda-469">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="7efda-470">`--langVersion <VERSION_NUMBER>`: establece la propiedad `LangVersion` en el archivo de proyecto creado.</span><span class="sxs-lookup"><span data-stu-id="7efda-470">`--langVersion <VERSION_NUMBER>` - Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="7efda-471">Por ejemplo, use `--langVersion 7.3` para emplear C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="7efda-471">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="7efda-472">No es compatible con F#.</span><span class="sxs-lookup"><span data-stu-id="7efda-472">Not supported for F#.</span></span>

<span data-ttu-id="7efda-473">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="7efda-473">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="7efda-474">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="7efda-474">**mstest, xunit**</span></span>

<span data-ttu-id="7efda-475">`-p|--enable-pack`: habilita el empaquetado para el proyecto mediante [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="7efda-475">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="7efda-476">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="7efda-476">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="7efda-477">**nunit**</span><span class="sxs-lookup"><span data-stu-id="7efda-477">**nunit**</span></span>

<span data-ttu-id="7efda-478">`-f|--framework <FRAMEWORK>`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="7efda-478">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="7efda-479">El valor predeterminado es `netcoreapp2.1`.</span><span class="sxs-lookup"><span data-stu-id="7efda-479">The default value is `netcoreapp2.1`.</span></span>

<span data-ttu-id="7efda-480">`-p|--enable-pack`: habilita el empaquetado para el proyecto mediante [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="7efda-480">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="7efda-481">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="7efda-481">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="7efda-482">**page**</span><span class="sxs-lookup"><span data-stu-id="7efda-482">**page**</span></span>

<span data-ttu-id="7efda-483">`-na|--namespace <NAMESPACE_NAME>`: espacio de nombres del código generado.</span><span class="sxs-lookup"><span data-stu-id="7efda-483">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="7efda-484">El valor predeterminado es `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="7efda-484">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="7efda-485">`-np|--no-pagemodel`: crea la página sin PageModel.</span><span class="sxs-lookup"><span data-stu-id="7efda-485">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="7efda-486">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="7efda-486">**viewimports**</span></span>

<span data-ttu-id="7efda-487">`-na|--namespace <NAMESPACE_NAME>`: espacio de nombres del código generado.</span><span class="sxs-lookup"><span data-stu-id="7efda-487">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="7efda-488">El valor predeterminado es `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="7efda-488">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="7efda-489">**web**</span><span class="sxs-lookup"><span data-stu-id="7efda-489">**web**</span></span>

<span data-ttu-id="7efda-490">`--exclude-launch-settings`: excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="7efda-490">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="7efda-491">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="7efda-491">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="7efda-492">`--no-https`: el proyecto no requiere HTTPS.</span><span class="sxs-lookup"><span data-stu-id="7efda-492">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="7efda-493">Esta opción solo se aplica si no se usan `IndividualAuth` u `OrganizationalAuth`.</span><span class="sxs-lookup"><span data-stu-id="7efda-493">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="7efda-494">**mvc, webapp**</span><span class="sxs-lookup"><span data-stu-id="7efda-494">**mvc, webapp**</span></span>

<span data-ttu-id="7efda-495">`-au|--auth <AUTHENTICATION_TYPE>`: el tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="7efda-495">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="7efda-496">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="7efda-496">The possible values are:</span></span>

- <span data-ttu-id="7efda-497">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="7efda-497">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="7efda-498">`Individual`: autenticación individual.</span><span class="sxs-lookup"><span data-stu-id="7efda-498">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="7efda-499">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="7efda-499">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="7efda-500">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="7efda-500">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="7efda-501">`MultiOrg`: autenticación organizativa para varios inquilinos.</span><span class="sxs-lookup"><span data-stu-id="7efda-501">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="7efda-502">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="7efda-502">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="7efda-503">`--aad-b2c-instance <INSTANCE>`: la instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="7efda-503">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="7efda-504">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="7efda-504">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="7efda-505">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="7efda-505">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="7efda-506">`-ssp|--susi-policy-id <ID>`: el id. de inicio de sesión y de directiva de registro de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="7efda-506">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="7efda-507">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="7efda-507">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="7efda-508">`-rp|--reset-password-policy-id <ID>`: el id. de la directiva de restablecimiento de contraseñas para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="7efda-508">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="7efda-509">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="7efda-509">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="7efda-510">`-ep|--edit-profile-policy-id <ID>`: el id. de directiva de edición de perfiles para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="7efda-510">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="7efda-511">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="7efda-511">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="7efda-512">`--aad-instance <INSTANCE>`: la instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="7efda-512">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="7efda-513">Úsela con las autenticaciones `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="7efda-513">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="7efda-514">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="7efda-514">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="7efda-515">`--client-id <ID>`: el id. de cliente para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="7efda-515">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="7efda-516">Úsela con las autenticaciones `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="7efda-516">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="7efda-517">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="7efda-517">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="7efda-518">`--domain <DOMAIN>`: el dominio para el inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="7efda-518">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="7efda-519">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="7efda-519">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="7efda-520">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="7efda-520">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="7efda-521">`--tenant-id <ID>`: el id. de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="7efda-521">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="7efda-522">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="7efda-522">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="7efda-523">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="7efda-523">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="7efda-524">`--callback-path <PATH>`: la ruta de acceso de solicitud de la ruta de acceso de la base de la aplicación del URI de redirección.</span><span class="sxs-lookup"><span data-stu-id="7efda-524">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="7efda-525">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="7efda-525">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="7efda-526">El valor predeterminado es `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="7efda-526">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="7efda-527">`-r|--org-read-access`: concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="7efda-527">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="7efda-528">Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="7efda-528">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="7efda-529">`--exclude-launch-settings`: excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="7efda-529">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="7efda-530">`--no-https`: el proyecto no requiere HTTPS.</span><span class="sxs-lookup"><span data-stu-id="7efda-530">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="7efda-531">`app.UseHsts` y `app.UseHttpsRedirection` no se agregan a `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="7efda-531">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="7efda-532">Esta opción solo se aplica si no se usan `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="7efda-532">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="7efda-533">`-uld|--use-local-db`: especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="7efda-533">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="7efda-534">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="7efda-534">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="7efda-535">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="7efda-535">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="7efda-536">**webapi**</span><span class="sxs-lookup"><span data-stu-id="7efda-536">**webapi**</span></span>

<span data-ttu-id="7efda-537">`-au|--auth <AUTHENTICATION_TYPE>`: el tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="7efda-537">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="7efda-538">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="7efda-538">The possible values are:</span></span>

- <span data-ttu-id="7efda-539">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="7efda-539">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="7efda-540">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="7efda-540">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="7efda-541">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="7efda-541">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="7efda-542">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="7efda-542">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="7efda-543">`--aad-b2c-instance <INSTANCE>`: la instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="7efda-543">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="7efda-544">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="7efda-544">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="7efda-545">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="7efda-545">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="7efda-546">`-ssp|--susi-policy-id <ID>`: el id. de inicio de sesión y de directiva de registro de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="7efda-546">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="7efda-547">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="7efda-547">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="7efda-548">`--aad-instance <INSTANCE>`: la instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="7efda-548">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="7efda-549">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="7efda-549">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="7efda-550">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="7efda-550">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="7efda-551">`--client-id <ID>`: el id. de cliente para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="7efda-551">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="7efda-552">Úsela con las autenticaciones `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="7efda-552">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="7efda-553">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="7efda-553">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="7efda-554">`--domain <DOMAIN>`: el dominio para el inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="7efda-554">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="7efda-555">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="7efda-555">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="7efda-556">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="7efda-556">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="7efda-557">`--tenant-id <ID>`: el id. de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="7efda-557">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="7efda-558">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="7efda-558">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="7efda-559">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="7efda-559">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="7efda-560">`-r|--org-read-access`: concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="7efda-560">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="7efda-561">Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="7efda-561">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="7efda-562">`--exclude-launch-settings`: excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="7efda-562">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="7efda-563">`--no-https`: el proyecto no requiere HTTPS.</span><span class="sxs-lookup"><span data-stu-id="7efda-563">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="7efda-564">`app.UseHsts` y `app.UseHttpsRedirection` no se agregan a `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="7efda-564">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="7efda-565">Esta opción solo se aplica si no se usan `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="7efda-565">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="7efda-566">`-uld|--use-local-db`: especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="7efda-566">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="7efda-567">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="7efda-567">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="7efda-568">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="7efda-568">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="7efda-569">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="7efda-569">**globaljson**</span></span>

<span data-ttu-id="7efda-570">`--sdk-version <VERSION_NUMBER>`: especifica la versión del SDK de .NET Core que se usará con el archivo *global.json*.</span><span class="sxs-lookup"><span data-stu-id="7efda-570">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="7efda-571">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="7efda-571">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="7efda-572">**console, angular, react, reactredux, razorclasslib**</span><span class="sxs-lookup"><span data-stu-id="7efda-572">**console, angular, react, reactredux, razorclasslib**</span></span>

<span data-ttu-id="7efda-573">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="7efda-573">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="7efda-574">**classlib**</span><span class="sxs-lookup"><span data-stu-id="7efda-574">**classlib**</span></span>

<span data-ttu-id="7efda-575">`-f|--framework <FRAMEWORK>`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="7efda-575">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="7efda-576">Valores: `netcoreapp2.1` para crear una biblioteca de clases de .NET Core o `netstandard2.0` para crear una biblioteca de clases de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="7efda-576">Values: `netcoreapp2.1` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="7efda-577">El valor predeterminado es `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="7efda-577">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="7efda-578">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="7efda-578">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="7efda-579">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="7efda-579">**mstest, xunit**</span></span>

<span data-ttu-id="7efda-580">`-p|--enable-pack`: habilita el empaquetado para el proyecto mediante [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="7efda-580">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="7efda-581">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="7efda-581">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="7efda-582">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="7efda-582">**globaljson**</span></span>

<span data-ttu-id="7efda-583">`--sdk-version <VERSION_NUMBER>`: especifica la versión del SDK de .NET Core que se usará con el archivo *global.json*.</span><span class="sxs-lookup"><span data-stu-id="7efda-583">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="7efda-584">**web**</span><span class="sxs-lookup"><span data-stu-id="7efda-584">**web**</span></span>

<span data-ttu-id="7efda-585">`--exclude-launch-settings`: excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="7efda-585">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="7efda-586">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="7efda-586">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="7efda-587">`--no-https`: el proyecto no requiere HTTPS.</span><span class="sxs-lookup"><span data-stu-id="7efda-587">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="7efda-588">Esta opción solo se aplica si no se usan `IndividualAuth` u `OrganizationalAuth`.</span><span class="sxs-lookup"><span data-stu-id="7efda-588">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="7efda-589">**webapi**</span><span class="sxs-lookup"><span data-stu-id="7efda-589">**webapi**</span></span>

<span data-ttu-id="7efda-590">`-au|--auth <AUTHENTICATION_TYPE>`: el tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="7efda-590">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="7efda-591">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="7efda-591">The possible values are:</span></span>

- <span data-ttu-id="7efda-592">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="7efda-592">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="7efda-593">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="7efda-593">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="7efda-594">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="7efda-594">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="7efda-595">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="7efda-595">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="7efda-596">`--aad-b2c-instance <INSTANCE>`: la instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="7efda-596">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="7efda-597">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="7efda-597">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="7efda-598">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="7efda-598">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="7efda-599">`-ssp|--susi-policy-id <ID>`: el id. de inicio de sesión y de directiva de registro de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="7efda-599">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="7efda-600">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="7efda-600">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="7efda-601">`--aad-instance <INSTANCE>`: la instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="7efda-601">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="7efda-602">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="7efda-602">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="7efda-603">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="7efda-603">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="7efda-604">`--client-id <ID>`: el id. de cliente para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="7efda-604">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="7efda-605">Úsela con las autenticaciones `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="7efda-605">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="7efda-606">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="7efda-606">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="7efda-607">`--domain <DOMAIN>`: el dominio para el inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="7efda-607">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="7efda-608">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="7efda-608">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="7efda-609">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="7efda-609">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="7efda-610">`--tenant-id <ID>`: el id. de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="7efda-610">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="7efda-611">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="7efda-611">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="7efda-612">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="7efda-612">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="7efda-613">`-r|--org-read-access`: concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="7efda-613">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="7efda-614">Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="7efda-614">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="7efda-615">`--exclude-launch-settings`: excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="7efda-615">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="7efda-616">`-uld|--use-local-db`: especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="7efda-616">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="7efda-617">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="7efda-617">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="7efda-618">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="7efda-618">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="7efda-619">`--no-https`: el proyecto no requiere HTTPS.</span><span class="sxs-lookup"><span data-stu-id="7efda-619">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="7efda-620">`app.UseHsts` y `app.UseHttpsRedirection` no se agregan a `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="7efda-620">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="7efda-621">Esta opción solo se aplica si no se usan `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="7efda-621">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="7efda-622">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="7efda-622">**mvc, razor**</span></span>

<span data-ttu-id="7efda-623">`-au|--auth <AUTHENTICATION_TYPE>`: el tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="7efda-623">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="7efda-624">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="7efda-624">The possible values are:</span></span>

- <span data-ttu-id="7efda-625">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="7efda-625">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="7efda-626">`Individual`: autenticación individual.</span><span class="sxs-lookup"><span data-stu-id="7efda-626">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="7efda-627">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="7efda-627">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="7efda-628">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="7efda-628">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="7efda-629">`MultiOrg`: autenticación organizativa para varios inquilinos.</span><span class="sxs-lookup"><span data-stu-id="7efda-629">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="7efda-630">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="7efda-630">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="7efda-631">`--aad-b2c-instance <INSTANCE>`: la instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="7efda-631">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="7efda-632">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="7efda-632">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="7efda-633">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="7efda-633">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="7efda-634">`-ssp|--susi-policy-id <ID>`: el id. de inicio de sesión y de directiva de registro de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="7efda-634">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="7efda-635">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="7efda-635">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="7efda-636">`-rp|--reset-password-policy-id <ID>`: el id. de la directiva de restablecimiento de contraseñas para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="7efda-636">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="7efda-637">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="7efda-637">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="7efda-638">`-ep|--edit-profile-policy-id <ID>`: el id. de directiva de edición de perfiles para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="7efda-638">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="7efda-639">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="7efda-639">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="7efda-640">`--aad-instance <INSTANCE>`: la instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="7efda-640">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="7efda-641">Úsela con las autenticaciones `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="7efda-641">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="7efda-642">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="7efda-642">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="7efda-643">`--client-id <ID>`: el id. de cliente para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="7efda-643">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="7efda-644">Úsela con las autenticaciones `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="7efda-644">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="7efda-645">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="7efda-645">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="7efda-646">`--domain <DOMAIN>`: el dominio para el inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="7efda-646">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="7efda-647">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="7efda-647">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="7efda-648">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="7efda-648">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="7efda-649">`--tenant-id <ID>`: el id. de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="7efda-649">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="7efda-650">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="7efda-650">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="7efda-651">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="7efda-651">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="7efda-652">`--callback-path <PATH>`: la ruta de acceso de solicitud de la ruta de acceso de la base de la aplicación del URI de redirección.</span><span class="sxs-lookup"><span data-stu-id="7efda-652">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="7efda-653">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="7efda-653">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="7efda-654">El valor predeterminado es `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="7efda-654">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="7efda-655">`-r|--org-read-access`: concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="7efda-655">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="7efda-656">Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="7efda-656">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="7efda-657">`--exclude-launch-settings`: excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="7efda-657">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="7efda-658">`--use-browserlink`: incluye BrowserLink en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="7efda-658">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="7efda-659">`-uld|--use-local-db`: especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="7efda-659">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="7efda-660">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="7efda-660">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="7efda-661">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="7efda-661">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="7efda-662">`--no-https`: el proyecto no requiere HTTPS.</span><span class="sxs-lookup"><span data-stu-id="7efda-662">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="7efda-663">`app.UseHsts` y `app.UseHttpsRedirection` no se agregan a `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="7efda-663">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="7efda-664">Esta opción solo se aplica si no se usan `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="7efda-664">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="7efda-665">**page**</span><span class="sxs-lookup"><span data-stu-id="7efda-665">**page**</span></span>

<span data-ttu-id="7efda-666">`-na|--namespace <NAMESPACE_NAME>`: espacio de nombres del código generado.</span><span class="sxs-lookup"><span data-stu-id="7efda-666">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="7efda-667">El valor predeterminado es `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="7efda-667">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="7efda-668">`-np|--no-pagemodel`: crea la página sin PageModel.</span><span class="sxs-lookup"><span data-stu-id="7efda-668">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="7efda-669">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="7efda-669">**viewimports**</span></span>

<span data-ttu-id="7efda-670">`-na|--namespace <NAMESPACE_NAME>`: espacio de nombres del código generado.</span><span class="sxs-lookup"><span data-stu-id="7efda-670">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="7efda-671">El valor predeterminado es `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="7efda-671">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="7efda-672">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="7efda-672">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="7efda-673">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="7efda-673">**console, angular, react, reactredux**</span></span>

<span data-ttu-id="7efda-674">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="7efda-674">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="7efda-675">**classlib**</span><span class="sxs-lookup"><span data-stu-id="7efda-675">**classlib**</span></span>

<span data-ttu-id="7efda-676">`-f|--framework <FRAMEWORK>`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="7efda-676">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="7efda-677">Valores: `netcoreapp2.0` para crear una biblioteca de clases de .NET Core o `netstandard2.0` para crear una biblioteca de clases de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="7efda-677">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="7efda-678">El valor predeterminado es `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="7efda-678">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="7efda-679">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="7efda-679">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="7efda-680">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="7efda-680">**mstest, xunit**</span></span>

<span data-ttu-id="7efda-681">`-p|--enable-pack`: habilita el empaquetado para el proyecto mediante [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="7efda-681">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="7efda-682">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="7efda-682">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="7efda-683">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="7efda-683">**globaljson**</span></span>

<span data-ttu-id="7efda-684">`--sdk-version <VERSION_NUMBER>`: especifica la versión del SDK de .NET Core que se usará con el archivo *global.json*.</span><span class="sxs-lookup"><span data-stu-id="7efda-684">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="7efda-685">**web**</span><span class="sxs-lookup"><span data-stu-id="7efda-685">**web**</span></span>

<span data-ttu-id="7efda-686">`--use-launch-settings`: incluye *launchSettings.json* en la salida de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="7efda-686">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="7efda-687">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="7efda-687">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="7efda-688">**webapi**</span><span class="sxs-lookup"><span data-stu-id="7efda-688">**webapi**</span></span>

<span data-ttu-id="7efda-689">`-au|--auth <AUTHENTICATION_TYPE>`: el tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="7efda-689">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="7efda-690">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="7efda-690">The possible values are:</span></span>

- <span data-ttu-id="7efda-691">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="7efda-691">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="7efda-692">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="7efda-692">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="7efda-693">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="7efda-693">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="7efda-694">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="7efda-694">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="7efda-695">`--aad-b2c-instance <INSTANCE>`: la instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="7efda-695">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="7efda-696">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="7efda-696">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="7efda-697">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="7efda-697">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="7efda-698">`-ssp|--susi-policy-id <ID>`: el id. de inicio de sesión y de directiva de registro de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="7efda-698">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="7efda-699">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="7efda-699">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="7efda-700">`--aad-instance <INSTANCE>`: la instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="7efda-700">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="7efda-701">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="7efda-701">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="7efda-702">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="7efda-702">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="7efda-703">`--client-id <ID>`: el id. de cliente para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="7efda-703">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="7efda-704">Úsela con las autenticaciones `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="7efda-704">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="7efda-705">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="7efda-705">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="7efda-706">`--domain <DOMAIN>`: el dominio para el inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="7efda-706">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="7efda-707">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="7efda-707">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="7efda-708">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="7efda-708">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="7efda-709">`--tenant-id <ID>`: el id. de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="7efda-709">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="7efda-710">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="7efda-710">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="7efda-711">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="7efda-711">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="7efda-712">`-r|--org-read-access`: concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="7efda-712">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="7efda-713">Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="7efda-713">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="7efda-714">`--use-launch-settings`: incluye *launchSettings.json* en la salida de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="7efda-714">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="7efda-715">`-uld|--use-local-db`: especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="7efda-715">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="7efda-716">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="7efda-716">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="7efda-717">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="7efda-717">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="7efda-718">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="7efda-718">**mvc, razor**</span></span>

<span data-ttu-id="7efda-719">`-au|--auth <AUTHENTICATION_TYPE>`: el tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="7efda-719">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="7efda-720">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="7efda-720">The possible values are:</span></span>

- <span data-ttu-id="7efda-721">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="7efda-721">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="7efda-722">`Individual`: autenticación individual.</span><span class="sxs-lookup"><span data-stu-id="7efda-722">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="7efda-723">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="7efda-723">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="7efda-724">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="7efda-724">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="7efda-725">`MultiOrg`: autenticación organizativa para varios inquilinos.</span><span class="sxs-lookup"><span data-stu-id="7efda-725">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="7efda-726">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="7efda-726">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="7efda-727">`--aad-b2c-instance <INSTANCE>`: la instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="7efda-727">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="7efda-728">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="7efda-728">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="7efda-729">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="7efda-729">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="7efda-730">`-ssp|--susi-policy-id <ID>`: el id. de inicio de sesión y de directiva de registro de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="7efda-730">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="7efda-731">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="7efda-731">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="7efda-732">`-rp|--reset-password-policy-id <ID>`: el id. de la directiva de restablecimiento de contraseñas para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="7efda-732">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="7efda-733">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="7efda-733">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="7efda-734">`-ep|--edit-profile-policy-id <ID>`: el id. de directiva de edición de perfiles para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="7efda-734">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="7efda-735">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="7efda-735">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="7efda-736">`--aad-instance <INSTANCE>`: la instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="7efda-736">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="7efda-737">Úsela con las autenticaciones `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="7efda-737">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="7efda-738">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="7efda-738">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="7efda-739">`--client-id <ID>`: el id. de cliente para este proyecto.</span><span class="sxs-lookup"><span data-stu-id="7efda-739">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="7efda-740">Úsela con las autenticaciones `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="7efda-740">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="7efda-741">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="7efda-741">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="7efda-742">`--domain <DOMAIN>`: el dominio para el inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="7efda-742">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="7efda-743">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="7efda-743">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="7efda-744">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="7efda-744">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="7efda-745">`--tenant-id <ID>`: el id. de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="7efda-745">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="7efda-746">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="7efda-746">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="7efda-747">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="7efda-747">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="7efda-748">`--callback-path <PATH>`: la ruta de acceso de solicitud de la ruta de acceso de la base de la aplicación del URI de redirección.</span><span class="sxs-lookup"><span data-stu-id="7efda-748">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="7efda-749">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="7efda-749">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="7efda-750">El valor predeterminado es `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="7efda-750">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="7efda-751">`-r|--org-read-access`: concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="7efda-751">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="7efda-752">Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="7efda-752">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="7efda-753">`--use-launch-settings`: incluye *launchSettings.json* en la salida de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="7efda-753">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="7efda-754">`--use-browserlink`: incluye BrowserLink en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="7efda-754">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="7efda-755">`-uld|--use-local-db`: especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="7efda-755">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="7efda-756">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="7efda-756">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="7efda-757">`--no-restore`: no se ejecuta una restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="7efda-757">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="7efda-758">**page**</span><span class="sxs-lookup"><span data-stu-id="7efda-758">**page**</span></span>

<span data-ttu-id="7efda-759">`-na|--namespace <NAMESPACE_NAME>`: espacio de nombres para el código generado.</span><span class="sxs-lookup"><span data-stu-id="7efda-759">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="7efda-760">El valor predeterminado es `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="7efda-760">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="7efda-761">`-np|--no-pagemodel`: crea la página sin PageModel.</span><span class="sxs-lookup"><span data-stu-id="7efda-761">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="7efda-762">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="7efda-762">**viewimports**</span></span>

<span data-ttu-id="7efda-763">`-na|--namespace <NAMESPACE_NAME>`: espacio de nombres para el código generado.</span><span class="sxs-lookup"><span data-stu-id="7efda-763">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="7efda-764">El valor predeterminado es `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="7efda-764">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="7efda-765">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="7efda-765">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="7efda-766">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="7efda-766">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="7efda-767">`-f|--framework <FRAMEWORK>`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="7efda-767">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="7efda-768">Valores: `netcoreapp1.0` o `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="7efda-768">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="7efda-769">El valor predeterminado es `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="7efda-769">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="7efda-770">**classlib**</span><span class="sxs-lookup"><span data-stu-id="7efda-770">**classlib**</span></span>

<span data-ttu-id="7efda-771">`-f|--framework <FRAMEWORK>`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="7efda-771">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="7efda-772">Valores: `netcoreapp1.0`, `netcoreapp1.1` o de `netstandard1.0` a `netstandard1.6`.</span><span class="sxs-lookup"><span data-stu-id="7efda-772">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="7efda-773">El valor predeterminado es `netstandard1.4`.</span><span class="sxs-lookup"><span data-stu-id="7efda-773">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="7efda-774">**mvc**</span><span class="sxs-lookup"><span data-stu-id="7efda-774">**mvc**</span></span>

<span data-ttu-id="7efda-775">`-f|--framework <FRAMEWORK>`: especifica el [marco de trabajo](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="7efda-775">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="7efda-776">Valores: `netcoreapp1.0` o `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="7efda-776">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="7efda-777">El valor predeterminado es `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="7efda-777">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="7efda-778">`-au|--auth <AUTHENTICATION_TYPE>`: el tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="7efda-778">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="7efda-779">Valores: `None` o `Individual`.</span><span class="sxs-lookup"><span data-stu-id="7efda-779">Values: `None` or `Individual`.</span></span> <span data-ttu-id="7efda-780">El valor predeterminado es `None`.</span><span class="sxs-lookup"><span data-stu-id="7efda-780">The default value is `None`.</span></span>

<span data-ttu-id="7efda-781">`-uld|--use-local-db`: especifica si se va a usar o no LocalDB en lugar de SQLite.</span><span class="sxs-lookup"><span data-stu-id="7efda-781">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="7efda-782">Valores: `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="7efda-782">Values: `true` or `false`.</span></span> <span data-ttu-id="7efda-783">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="7efda-783">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="7efda-784">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="7efda-784">Examples</span></span>

<span data-ttu-id="7efda-785">Creación de un proyecto de aplicación de consola de C# mediante la especificación del nombre de plantilla:</span><span class="sxs-lookup"><span data-stu-id="7efda-785">Create a C# console application project by specifying the template name:</span></span>

`dotnet new "Console Application"`

<span data-ttu-id="7efda-786">Creación de un proyecto de aplicación de consola con F# en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="7efda-786">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang F#`

<span data-ttu-id="7efda-787">Creación de un proyecto de biblioteca de clases de .NET Standard en el directorio especificado (disponible solo con el SDK de .NET Core 2.0 o versiones posteriores):</span><span class="sxs-lookup"><span data-stu-id="7efda-787">Create a .NET Standard class library project in the specified directory (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="7efda-788">Creación de un proyecto MVC de ASP.NET Core C# en el directorio actual sin autenticación:</span><span class="sxs-lookup"><span data-stu-id="7efda-788">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

`dotnet new mvc -au None`

<span data-ttu-id="7efda-789">Creación de un proyecto de xUnit:</span><span class="sxs-lookup"><span data-stu-id="7efda-789">Create a new xUnit project:</span></span>

`dotnet new xunit`

<span data-ttu-id="7efda-790">Enumere todas las plantillas disponibles para MVC:</span><span class="sxs-lookup"><span data-stu-id="7efda-790">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

<span data-ttu-id="7efda-791">Enumeración de todas las plantillas que coinciden con la subcadena *we*.</span><span class="sxs-lookup"><span data-stu-id="7efda-791">List all templates matching the *we* substring.</span></span> <span data-ttu-id="7efda-792">No se encuentra ninguna coincidencia exacta, por lo que se ejecuta la coincidencia de subcadena con las columnas de nombre corto y de nombre.</span><span class="sxs-lookup"><span data-stu-id="7efda-792">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

`dotnet new we -l`

<span data-ttu-id="7efda-793">Intento de invocar a la plantilla que coincide con *ng*.</span><span class="sxs-lookup"><span data-stu-id="7efda-793">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="7efda-794">Si no se puede determinar una única coincidencia, se enumeran las plantillas que son coincidencias parciales.</span><span class="sxs-lookup"><span data-stu-id="7efda-794">If a single match can't be determined, list the templates that are partial matches.</span></span>

`dotnet new ng`

<span data-ttu-id="7efda-795">Instalación de la versión 2.0 de las plantillas Aplicación de página única para ASP.NET Core (opción de comando solo disponible para .NET Core SDK 1.1 y versiones posteriores):</span><span class="sxs-lookup"><span data-stu-id="7efda-795">Install version 2.0 of the Single Page Application templates for ASP.NET Core (command option available for .NET Core SDK 1.1 and later versions only):</span></span>

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

<span data-ttu-id="7efda-796">Creación de un archivo *global.json* en el directorio actual que establezca la versión del SDK en 2.0.0 (solo disponible en el SDK de .NET Core 2.0 o versiones posteriores):</span><span class="sxs-lookup"><span data-stu-id="7efda-796">Create a *global.json* in the current directory setting the SDK version to 2.0.0 (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new globaljson --sdk-version 2.0.0`

## <a name="see-also"></a><span data-ttu-id="7efda-797">Vea también</span><span class="sxs-lookup"><span data-stu-id="7efda-797">See also</span></span>

- <span data-ttu-id="7efda-798">[Custom templates for dotnet new](custom-templates.md) (Plantillas personalizadas para dotnet new)</span><span class="sxs-lookup"><span data-stu-id="7efda-798">[Custom templates for dotnet new](custom-templates.md)</span></span>
- [<span data-ttu-id="7efda-799">Creación de una plantilla personalizada para dotnet new</span><span class="sxs-lookup"><span data-stu-id="7efda-799">Create a custom template for dotnet new</span></span>](../tutorials/cli-templates-create-item-template.md)
- [<span data-ttu-id="7efda-800">Repositorio de GitHub dotnet/dotnet-template-samples</span><span class="sxs-lookup"><span data-stu-id="7efda-800">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- <span data-ttu-id="7efda-801">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new) (Plantillas disponibles para dotnet new)</span><span class="sxs-lookup"><span data-stu-id="7efda-801">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)</span></span>
