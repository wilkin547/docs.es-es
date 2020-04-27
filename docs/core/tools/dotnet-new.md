---
title: Comando dotnet new
description: El comando dotnet new crea proyectos de .NET Core basados en la plantilla especificada.
ms.date: 04/10/2020
ms.openlocfilehash: 1979f98a6005a414acc64c5eaa086a88aca9f033
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102832"
---
# <a name="dotnet-new"></a><span data-ttu-id="68c06-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="68c06-103">dotnet new</span></span>

<span data-ttu-id="68c06-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.0 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="68c06-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="68c06-105">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="68c06-105">Name</span></span>

<span data-ttu-id="68c06-106">`dotnet new`: crea un nuevo proyecto, archivo de configuración o solución según la plantilla especificada.</span><span class="sxs-lookup"><span data-stu-id="68c06-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="68c06-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="68c06-107">Synopsis</span></span>

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install {PATH|NUGET_ID}]
    [-lang|--language {C#|F#|VB}] [-n|--name <OUTPUT_NAME>]
    [--nuget-source <SOURCE>] [-o|--output <OUTPUT_DIRECTORY>]
    [-u|--uninstall] [--update-apply] [--update-check] [Template options]

dotnet new <TEMPLATE> [-l|--list] [--type <TYPE>]

dotnet new -h|--help
```

## <a name="description"></a><span data-ttu-id="68c06-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="68c06-108">Description</span></span>

<span data-ttu-id="68c06-109">El comando `dotnet new` crea un proyecto de .NET Core u otros artefactos basados en una plantilla.</span><span class="sxs-lookup"><span data-stu-id="68c06-109">The `dotnet new` command creates a .NET Core project or other artifacts based on a template.</span></span>

<span data-ttu-id="68c06-110">El comando llama al [motor de plantillas](https://github.com/dotnet/templating) para crear los artefactos en el disco basándose en las opciones y la plantilla especificadas.</span><span class="sxs-lookup"><span data-stu-id="68c06-110">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="68c06-111">Restauración implícita</span><span class="sxs-lookup"><span data-stu-id="68c06-111">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="68c06-112">Argumentos</span><span class="sxs-lookup"><span data-stu-id="68c06-112">Arguments</span></span>

- **`TEMPLATE`**

  <span data-ttu-id="68c06-113">La plantilla de la que se va a crear una instancia cuando se invoca el comando.</span><span class="sxs-lookup"><span data-stu-id="68c06-113">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="68c06-114">Cada plantilla puede tener opciones específicas que puede pasar.</span><span class="sxs-lookup"><span data-stu-id="68c06-114">Each template might have specific options you can pass.</span></span> <span data-ttu-id="68c06-115">Para obtener más información, vea [Opciones de plantilla](#template-options).</span><span class="sxs-lookup"><span data-stu-id="68c06-115">For more information, see [Template options](#template-options).</span></span>

  <span data-ttu-id="68c06-116">Puede ejecutar `dotnet new --list` para ver una lista de todas las plantillas instaladas.</span><span class="sxs-lookup"><span data-stu-id="68c06-116">You can run `dotnet new --list` to see a list of all installed templates.</span></span> <span data-ttu-id="68c06-117">Si el valor `TEMPLATE` no es una coincidencia exacta con el texto de la columna **Plantillas** o **Nombre corto** de la tabla devuelta, se realiza una coincidencia de subcadena con esas dos columnas.</span><span class="sxs-lookup"><span data-stu-id="68c06-117">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column from the returned table, a substring match is performed on those two columns.</span></span>

  <span data-ttu-id="68c06-118">A partir del SDK de .NET Core 3.0, la CLI busca plantillas en NuGet.org al invocar el comando `dotnet new` en las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="68c06-118">Starting with .NET Core 3.0 SDK, the CLI searches for templates in NuGet.org when you invoke the `dotnet new` command in the following conditions:</span></span>

  - <span data-ttu-id="68c06-119">Si la CLI no encuentra ninguna coincidencia de plantilla al invocar `dotnet new`, ni siquiera parcial.</span><span class="sxs-lookup"><span data-stu-id="68c06-119">If the CLI can't find a template match when invoking `dotnet new`, not even partial.</span></span>
  - <span data-ttu-id="68c06-120">Si hay disponible una versión más reciente de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="68c06-120">If there's a newer version of the template available.</span></span> <span data-ttu-id="68c06-121">En este caso, se crea el proyecto o el artefacto, pero la CLI le advierte de que hay una versión actualizada de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="68c06-121">In this case, the project or artifact is created but the CLI warns you about an updated version of the template.</span></span>

  <span data-ttu-id="68c06-122">El comando contiene una lista predeterminada de plantillas.</span><span class="sxs-lookup"><span data-stu-id="68c06-122">The command contains a default list of templates.</span></span> <span data-ttu-id="68c06-123">Use `dotnet new -l` para obtener una lista de las plantillas disponibles.</span><span class="sxs-lookup"><span data-stu-id="68c06-123">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="68c06-124">En la tabla siguiente se muestran las plantillas que vienen preinstaladas en el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="68c06-124">The following table shows the templates that come pre-installed with the .NET Core SDK.</span></span> <span data-ttu-id="68c06-125">El lenguaje predeterminado de la plantilla se muestra entre corchetes.</span><span class="sxs-lookup"><span data-stu-id="68c06-125">The default language for the template is shown inside the brackets.</span></span> <span data-ttu-id="68c06-126">Haga clic en el vínculo del nombre corto para ver las opciones específicas de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="68c06-126">Click on the short name link to see the specific template options.</span></span>

| <span data-ttu-id="68c06-127">Plantillas</span><span class="sxs-lookup"><span data-stu-id="68c06-127">Templates</span></span>                                    | <span data-ttu-id="68c06-128">Nombre corto</span><span class="sxs-lookup"><span data-stu-id="68c06-128">Short name</span></span>                      | <span data-ttu-id="68c06-129">Lenguaje</span><span class="sxs-lookup"><span data-stu-id="68c06-129">Language</span></span>     | <span data-ttu-id="68c06-130">Etiquetas</span><span class="sxs-lookup"><span data-stu-id="68c06-130">Tags</span></span>                                  | <span data-ttu-id="68c06-131">Inclusión</span><span class="sxs-lookup"><span data-stu-id="68c06-131">Introduced</span></span> |
|----------------------------------------------|---------------------------------|--------------|---------------------------------------|------------|
| <span data-ttu-id="68c06-132">Aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="68c06-132">Console Application</span></span>                          | [<span data-ttu-id="68c06-133">console</span><span class="sxs-lookup"><span data-stu-id="68c06-133">console</span></span>](#console)             | <span data-ttu-id="68c06-134">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="68c06-134">[C#], F#, VB</span></span> | <span data-ttu-id="68c06-135">Común/Consola</span><span class="sxs-lookup"><span data-stu-id="68c06-135">Common/Console</span></span>                        | <span data-ttu-id="68c06-136">1.0</span><span class="sxs-lookup"><span data-stu-id="68c06-136">1.0</span></span>        |
| <span data-ttu-id="68c06-137">Biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="68c06-137">Class library</span></span>                                | [<span data-ttu-id="68c06-138">classlib</span><span class="sxs-lookup"><span data-stu-id="68c06-138">classlib</span></span>](#classlib)           | <span data-ttu-id="68c06-139">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="68c06-139">[C#], F#, VB</span></span> | <span data-ttu-id="68c06-140">Común/Biblioteca</span><span class="sxs-lookup"><span data-stu-id="68c06-140">Common/Library</span></span>                        | <span data-ttu-id="68c06-141">1.0</span><span class="sxs-lookup"><span data-stu-id="68c06-141">1.0</span></span>        |
| <span data-ttu-id="68c06-142">Aplicación WPF</span><span class="sxs-lookup"><span data-stu-id="68c06-142">WPF Application</span></span>                              | [<span data-ttu-id="68c06-143">wpf</span><span class="sxs-lookup"><span data-stu-id="68c06-143">wpf</span></span>](#wpf)                     | <span data-ttu-id="68c06-144">[C#]</span><span class="sxs-lookup"><span data-stu-id="68c06-144">[C#]</span></span>         | <span data-ttu-id="68c06-145">Común/WPF</span><span class="sxs-lookup"><span data-stu-id="68c06-145">Common/WPF</span></span>                            | <span data-ttu-id="68c06-146">3.0</span><span class="sxs-lookup"><span data-stu-id="68c06-146">3.0</span></span>        |
| <span data-ttu-id="68c06-147">Biblioteca de clases de WPF</span><span class="sxs-lookup"><span data-stu-id="68c06-147">WPF Class library</span></span>                            | [<span data-ttu-id="68c06-148">wpflib</span><span class="sxs-lookup"><span data-stu-id="68c06-148">wpflib</span></span>](#wpf)                  | <span data-ttu-id="68c06-149">[C#]</span><span class="sxs-lookup"><span data-stu-id="68c06-149">[C#]</span></span>         | <span data-ttu-id="68c06-150">Común/WPF</span><span class="sxs-lookup"><span data-stu-id="68c06-150">Common/WPF</span></span>                            | <span data-ttu-id="68c06-151">3.0</span><span class="sxs-lookup"><span data-stu-id="68c06-151">3.0</span></span>        |
| <span data-ttu-id="68c06-152">Biblioteca de controles personalizados WPF</span><span class="sxs-lookup"><span data-stu-id="68c06-152">WPF Custom Control Library</span></span>                   | [<span data-ttu-id="68c06-153">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="68c06-153">wpfcustomcontrollib</span></span>](#wpf)     | <span data-ttu-id="68c06-154">[C#]</span><span class="sxs-lookup"><span data-stu-id="68c06-154">[C#]</span></span>         | <span data-ttu-id="68c06-155">Común/WPF</span><span class="sxs-lookup"><span data-stu-id="68c06-155">Common/WPF</span></span>                            | <span data-ttu-id="68c06-156">3.0</span><span class="sxs-lookup"><span data-stu-id="68c06-156">3.0</span></span>        |
| <span data-ttu-id="68c06-157">Biblioteca de controles de usuario de WPF</span><span class="sxs-lookup"><span data-stu-id="68c06-157">WPF User Control Library</span></span>                     | [<span data-ttu-id="68c06-158">wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="68c06-158">wpfusercontrollib</span></span>](#wpf)       | <span data-ttu-id="68c06-159">[C#]</span><span class="sxs-lookup"><span data-stu-id="68c06-159">[C#]</span></span>         | <span data-ttu-id="68c06-160">Común/WPF</span><span class="sxs-lookup"><span data-stu-id="68c06-160">Common/WPF</span></span>                            | <span data-ttu-id="68c06-161">3.0</span><span class="sxs-lookup"><span data-stu-id="68c06-161">3.0</span></span>        |
| <span data-ttu-id="68c06-162">Aplicación de Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="68c06-162">Windows Forms (WinForms) Application</span></span>         | [<span data-ttu-id="68c06-163">winforms</span><span class="sxs-lookup"><span data-stu-id="68c06-163">winforms</span></span>](#winforms)           | <span data-ttu-id="68c06-164">[C#]</span><span class="sxs-lookup"><span data-stu-id="68c06-164">[C#]</span></span>         | <span data-ttu-id="68c06-165">Común/WinForms</span><span class="sxs-lookup"><span data-stu-id="68c06-165">Common/WinForms</span></span>                       | <span data-ttu-id="68c06-166">3.0</span><span class="sxs-lookup"><span data-stu-id="68c06-166">3.0</span></span>        |
| <span data-ttu-id="68c06-167">Biblioteca de clases de Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="68c06-167">Windows Forms (WinForms) Class library</span></span>       | [<span data-ttu-id="68c06-168">winformslib</span><span class="sxs-lookup"><span data-stu-id="68c06-168">winformslib</span></span>](#winforms)        | <span data-ttu-id="68c06-169">[C#]</span><span class="sxs-lookup"><span data-stu-id="68c06-169">[C#]</span></span>         | <span data-ttu-id="68c06-170">Común/WinForms</span><span class="sxs-lookup"><span data-stu-id="68c06-170">Common/WinForms</span></span>                       | <span data-ttu-id="68c06-171">3.0</span><span class="sxs-lookup"><span data-stu-id="68c06-171">3.0</span></span>        |
| <span data-ttu-id="68c06-172">Servicio Worker</span><span class="sxs-lookup"><span data-stu-id="68c06-172">Worker Service</span></span>                               | [<span data-ttu-id="68c06-173">worker</span><span class="sxs-lookup"><span data-stu-id="68c06-173">worker</span></span>](#web-others)           | <span data-ttu-id="68c06-174">[C#]</span><span class="sxs-lookup"><span data-stu-id="68c06-174">[C#]</span></span>         | <span data-ttu-id="68c06-175">Común/Worker/Web</span><span class="sxs-lookup"><span data-stu-id="68c06-175">Common/Worker/Web</span></span>                     | <span data-ttu-id="68c06-176">3.0</span><span class="sxs-lookup"><span data-stu-id="68c06-176">3.0</span></span>        |
| <span data-ttu-id="68c06-177">Proyecto de prueba unitaria</span><span class="sxs-lookup"><span data-stu-id="68c06-177">Unit Test Project</span></span>                            | [<span data-ttu-id="68c06-178">mstest</span><span class="sxs-lookup"><span data-stu-id="68c06-178">mstest</span></span>](#test)                 | <span data-ttu-id="68c06-179">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="68c06-179">[C#], F#, VB</span></span> | <span data-ttu-id="68c06-180">Prueba/MSTest</span><span class="sxs-lookup"><span data-stu-id="68c06-180">Test/MSTest</span></span>                           | <span data-ttu-id="68c06-181">1.0</span><span class="sxs-lookup"><span data-stu-id="68c06-181">1.0</span></span>        |
| <span data-ttu-id="68c06-182">Proyecto de prueba de NUnit 3</span><span class="sxs-lookup"><span data-stu-id="68c06-182">NUnit 3 Test Project</span></span>                         | [<span data-ttu-id="68c06-183">nunit</span><span class="sxs-lookup"><span data-stu-id="68c06-183">nunit</span></span>](#nunit)                  | <span data-ttu-id="68c06-184">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="68c06-184">[C#], F#, VB</span></span> | <span data-ttu-id="68c06-185">Prueba/NUnit</span><span class="sxs-lookup"><span data-stu-id="68c06-185">Test/NUnit</span></span>                            | <span data-ttu-id="68c06-186">2.1.400</span><span class="sxs-lookup"><span data-stu-id="68c06-186">2.1.400</span></span>    |
| <span data-ttu-id="68c06-187">Elemento de prueba de NUnit 3</span><span class="sxs-lookup"><span data-stu-id="68c06-187">NUnit 3 Test Item</span></span>                            | `nunit-test`                    | <span data-ttu-id="68c06-188">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="68c06-188">[C#], F#, VB</span></span> | <span data-ttu-id="68c06-189">Prueba/NUnit</span><span class="sxs-lookup"><span data-stu-id="68c06-189">Test/NUnit</span></span>                            | <span data-ttu-id="68c06-190">2.2</span><span class="sxs-lookup"><span data-stu-id="68c06-190">2.2</span></span>        |
| <span data-ttu-id="68c06-191">Proyecto de prueba de xUnit</span><span class="sxs-lookup"><span data-stu-id="68c06-191">xUnit Test Project</span></span>                           | [<span data-ttu-id="68c06-192">xunit</span><span class="sxs-lookup"><span data-stu-id="68c06-192">xunit</span></span>](#test)                  | <span data-ttu-id="68c06-193">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="68c06-193">[C#], F#, VB</span></span> | <span data-ttu-id="68c06-194">Prueba/xUnit</span><span class="sxs-lookup"><span data-stu-id="68c06-194">Test/xUnit</span></span>                            | <span data-ttu-id="68c06-195">1.0</span><span class="sxs-lookup"><span data-stu-id="68c06-195">1.0</span></span>        |
| <span data-ttu-id="68c06-196">Componente Razor</span><span class="sxs-lookup"><span data-stu-id="68c06-196">Razor Component</span></span>                              | `razorcomponent`                | <span data-ttu-id="68c06-197">[C#]</span><span class="sxs-lookup"><span data-stu-id="68c06-197">[C#]</span></span>         | <span data-ttu-id="68c06-198">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="68c06-198">Web/ASP.NET</span></span>                           | <span data-ttu-id="68c06-199">3.0</span><span class="sxs-lookup"><span data-stu-id="68c06-199">3.0</span></span>        |
| <span data-ttu-id="68c06-200">Página de Razor</span><span class="sxs-lookup"><span data-stu-id="68c06-200">Razor Page</span></span>                                   | [<span data-ttu-id="68c06-201">page</span><span class="sxs-lookup"><span data-stu-id="68c06-201">page</span></span>](#page)                   | <span data-ttu-id="68c06-202">[C#]</span><span class="sxs-lookup"><span data-stu-id="68c06-202">[C#]</span></span>         | <span data-ttu-id="68c06-203">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="68c06-203">Web/ASP.NET</span></span>                           | <span data-ttu-id="68c06-204">2.0</span><span class="sxs-lookup"><span data-stu-id="68c06-204">2.0</span></span>        |
| <span data-ttu-id="68c06-205">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="68c06-205">MVC ViewImports</span></span>                              | [<span data-ttu-id="68c06-206">viewimports</span><span class="sxs-lookup"><span data-stu-id="68c06-206">viewimports</span></span>](#namespace)       | <span data-ttu-id="68c06-207">[C#]</span><span class="sxs-lookup"><span data-stu-id="68c06-207">[C#]</span></span>         | <span data-ttu-id="68c06-208">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="68c06-208">Web/ASP.NET</span></span>                           | <span data-ttu-id="68c06-209">2.0</span><span class="sxs-lookup"><span data-stu-id="68c06-209">2.0</span></span>        |
| <span data-ttu-id="68c06-210">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="68c06-210">MVC ViewStart</span></span>                                | `viewstart`                     | <span data-ttu-id="68c06-211">[C#]</span><span class="sxs-lookup"><span data-stu-id="68c06-211">[C#]</span></span>         | <span data-ttu-id="68c06-212">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="68c06-212">Web/ASP.NET</span></span>                           | <span data-ttu-id="68c06-213">2.0</span><span class="sxs-lookup"><span data-stu-id="68c06-213">2.0</span></span>        |
| <span data-ttu-id="68c06-214">Aplicación de servidor Blazor</span><span class="sxs-lookup"><span data-stu-id="68c06-214">Blazor Server App</span></span>                            | [<span data-ttu-id="68c06-215">blazorserver</span><span class="sxs-lookup"><span data-stu-id="68c06-215">blazorserver</span></span>](#blazorserver)   | <span data-ttu-id="68c06-216">[C#]</span><span class="sxs-lookup"><span data-stu-id="68c06-216">[C#]</span></span>         | <span data-ttu-id="68c06-217">Web/Blazor</span><span class="sxs-lookup"><span data-stu-id="68c06-217">Web/Blazor</span></span>                            | <span data-ttu-id="68c06-218">3.0</span><span class="sxs-lookup"><span data-stu-id="68c06-218">3.0</span></span>        |
| <span data-ttu-id="68c06-219">Vacío de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="68c06-219">ASP.NET Core Empty</span></span>                           | [<span data-ttu-id="68c06-220">web</span><span class="sxs-lookup"><span data-stu-id="68c06-220">web</span></span>](#web)                     | <span data-ttu-id="68c06-221">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="68c06-221">[C#], F#</span></span>     | <span data-ttu-id="68c06-222">Web/Vacío</span><span class="sxs-lookup"><span data-stu-id="68c06-222">Web/Empty</span></span>                             | <span data-ttu-id="68c06-223">1.0</span><span class="sxs-lookup"><span data-stu-id="68c06-223">1.0</span></span>        |
| <span data-ttu-id="68c06-224">Aplicación web de ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="68c06-224">ASP.NET Core Web App (Model-View-Controller)</span></span> | [<span data-ttu-id="68c06-225">mvc</span><span class="sxs-lookup"><span data-stu-id="68c06-225">mvc</span></span>](#web-options)             | <span data-ttu-id="68c06-226">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="68c06-226">[C#], F#</span></span>     | <span data-ttu-id="68c06-227">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="68c06-227">Web/MVC</span></span>                               | <span data-ttu-id="68c06-228">1.0</span><span class="sxs-lookup"><span data-stu-id="68c06-228">1.0</span></span>        |
| <span data-ttu-id="68c06-229">Aplicación web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="68c06-229">ASP.NET Core Web App</span></span>                         | [<span data-ttu-id="68c06-230">webapp, razor</span><span class="sxs-lookup"><span data-stu-id="68c06-230">webapp, razor</span></span>](#web-options)   | <span data-ttu-id="68c06-231">[C#]</span><span class="sxs-lookup"><span data-stu-id="68c06-231">[C#]</span></span>         | <span data-ttu-id="68c06-232">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="68c06-232">Web/MVC/Razor Pages</span></span>                   | <span data-ttu-id="68c06-233">2.2, 2.0</span><span class="sxs-lookup"><span data-stu-id="68c06-233">2.2, 2.0</span></span>   |
| <span data-ttu-id="68c06-234">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="68c06-234">ASP.NET Core with Angular</span></span>                    | [<span data-ttu-id="68c06-235">angular</span><span class="sxs-lookup"><span data-stu-id="68c06-235">angular</span></span>](#spa)                 | <span data-ttu-id="68c06-236">[C#]</span><span class="sxs-lookup"><span data-stu-id="68c06-236">[C#]</span></span>         | <span data-ttu-id="68c06-237">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="68c06-237">Web/MVC/SPA</span></span>                           | <span data-ttu-id="68c06-238">2.0</span><span class="sxs-lookup"><span data-stu-id="68c06-238">2.0</span></span>        |
| <span data-ttu-id="68c06-239">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="68c06-239">ASP.NET Core with React.js</span></span>                   | [<span data-ttu-id="68c06-240">react</span><span class="sxs-lookup"><span data-stu-id="68c06-240">react</span></span>](#spa)                   | <span data-ttu-id="68c06-241">[C#]</span><span class="sxs-lookup"><span data-stu-id="68c06-241">[C#]</span></span>         | <span data-ttu-id="68c06-242">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="68c06-242">Web/MVC/SPA</span></span>                           | <span data-ttu-id="68c06-243">2.0</span><span class="sxs-lookup"><span data-stu-id="68c06-243">2.0</span></span>        |
| <span data-ttu-id="68c06-244">ASP.NET Core con React.js y Redux</span><span class="sxs-lookup"><span data-stu-id="68c06-244">ASP.NET Core with React.js and Redux</span></span>         | [<span data-ttu-id="68c06-245">reactredux</span><span class="sxs-lookup"><span data-stu-id="68c06-245">reactredux</span></span>](#reactredux)       | <span data-ttu-id="68c06-246">[C#]</span><span class="sxs-lookup"><span data-stu-id="68c06-246">[C#]</span></span>         | <span data-ttu-id="68c06-247">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="68c06-247">Web/MVC/SPA</span></span>                           | <span data-ttu-id="68c06-248">2.0</span><span class="sxs-lookup"><span data-stu-id="68c06-248">2.0</span></span>        |
| <span data-ttu-id="68c06-249">Biblioteca de clases de Razor</span><span class="sxs-lookup"><span data-stu-id="68c06-249">Razor Class Library</span></span>                          | [<span data-ttu-id="68c06-250">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="68c06-250">razorclasslib</span></span>](#razorclasslib) | <span data-ttu-id="68c06-251">[C#]</span><span class="sxs-lookup"><span data-stu-id="68c06-251">[C#]</span></span>         | <span data-ttu-id="68c06-252">Web/Razor/Biblioteca/Biblioteca de clases de Razor</span><span class="sxs-lookup"><span data-stu-id="68c06-252">Web/Razor/Library/Razor Class Library</span></span> | <span data-ttu-id="68c06-253">2.1</span><span class="sxs-lookup"><span data-stu-id="68c06-253">2.1</span></span>        |
| <span data-ttu-id="68c06-254">API web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="68c06-254">ASP.NET Core Web API</span></span>                         | [<span data-ttu-id="68c06-255">webapi</span><span class="sxs-lookup"><span data-stu-id="68c06-255">webapi</span></span>](#webapi)               | <span data-ttu-id="68c06-256">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="68c06-256">[C#], F#</span></span>     | <span data-ttu-id="68c06-257">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="68c06-257">Web/WebAPI</span></span>                            | <span data-ttu-id="68c06-258">1.0</span><span class="sxs-lookup"><span data-stu-id="68c06-258">1.0</span></span>        |
| <span data-ttu-id="68c06-259">Servicio gRPC de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="68c06-259">ASP.NET Core gRPC Service</span></span>                    | [<span data-ttu-id="68c06-260">grpc</span><span class="sxs-lookup"><span data-stu-id="68c06-260">grpc</span></span>](#web-others)             | <span data-ttu-id="68c06-261">[C#]</span><span class="sxs-lookup"><span data-stu-id="68c06-261">[C#]</span></span>         | <span data-ttu-id="68c06-262">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="68c06-262">Web/gRPC</span></span>                              | <span data-ttu-id="68c06-263">3.0</span><span class="sxs-lookup"><span data-stu-id="68c06-263">3.0</span></span>        |
| <span data-ttu-id="68c06-264">Archivo de búfer de protocolo</span><span class="sxs-lookup"><span data-stu-id="68c06-264">Protocol Buffer File</span></span>                         | [<span data-ttu-id="68c06-265">proto</span><span class="sxs-lookup"><span data-stu-id="68c06-265">proto</span></span>](#namespace)             |              | <span data-ttu-id="68c06-266">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="68c06-266">Web/gRPC</span></span>                              | <span data-ttu-id="68c06-267">3.0</span><span class="sxs-lookup"><span data-stu-id="68c06-267">3.0</span></span>        |
| <span data-ttu-id="68c06-268">Archivo dotnet gitignore</span><span class="sxs-lookup"><span data-stu-id="68c06-268">dotnet gitignore file</span></span>                        | `gitignore`                     |              | <span data-ttu-id="68c06-269">Configuración</span><span class="sxs-lookup"><span data-stu-id="68c06-269">Config</span></span>                                | <span data-ttu-id="68c06-270">3.0</span><span class="sxs-lookup"><span data-stu-id="68c06-270">3.0</span></span>        |
| <span data-ttu-id="68c06-271">archivo global.json</span><span class="sxs-lookup"><span data-stu-id="68c06-271">global.json file</span></span>                             | [<span data-ttu-id="68c06-272">globaljson</span><span class="sxs-lookup"><span data-stu-id="68c06-272">globaljson</span></span>](#globaljson)       |              | <span data-ttu-id="68c06-273">Configuración</span><span class="sxs-lookup"><span data-stu-id="68c06-273">Config</span></span>                                | <span data-ttu-id="68c06-274">2.0</span><span class="sxs-lookup"><span data-stu-id="68c06-274">2.0</span></span>        |
| <span data-ttu-id="68c06-275">Configuración de NuGet</span><span class="sxs-lookup"><span data-stu-id="68c06-275">NuGet Config</span></span>                                 | `nugetconfig`                   |              | <span data-ttu-id="68c06-276">Configuración</span><span class="sxs-lookup"><span data-stu-id="68c06-276">Config</span></span>                                | <span data-ttu-id="68c06-277">1.0</span><span class="sxs-lookup"><span data-stu-id="68c06-277">1.0</span></span>        |
| <span data-ttu-id="68c06-278">Archivo de manifiesto de la herramienta local dotnet</span><span class="sxs-lookup"><span data-stu-id="68c06-278">dotnet local tool manifest file</span></span>              | `tool-manifest`                 |              | <span data-ttu-id="68c06-279">Configuración</span><span class="sxs-lookup"><span data-stu-id="68c06-279">Config</span></span>                                | <span data-ttu-id="68c06-280">3.0</span><span class="sxs-lookup"><span data-stu-id="68c06-280">3.0</span></span>        |
| <span data-ttu-id="68c06-281">Configuración web</span><span class="sxs-lookup"><span data-stu-id="68c06-281">Web Config</span></span>                                   | `webconfig`                     |              | <span data-ttu-id="68c06-282">Configuración</span><span class="sxs-lookup"><span data-stu-id="68c06-282">Config</span></span>                                | <span data-ttu-id="68c06-283">1.0</span><span class="sxs-lookup"><span data-stu-id="68c06-283">1.0</span></span>        |
| <span data-ttu-id="68c06-284">Archivo de solución</span><span class="sxs-lookup"><span data-stu-id="68c06-284">Solution File</span></span>                                | `sln`                           |              | <span data-ttu-id="68c06-285">Soluciones</span><span class="sxs-lookup"><span data-stu-id="68c06-285">Solution</span></span>                              | <span data-ttu-id="68c06-286">1.0</span><span class="sxs-lookup"><span data-stu-id="68c06-286">1.0</span></span>        |

## <a name="options"></a><span data-ttu-id="68c06-287">Opciones</span><span class="sxs-lookup"><span data-stu-id="68c06-287">Options</span></span>

- **`--dry-run`**

  <span data-ttu-id="68c06-288">Muestra un resumen de lo que sucedería si se ejecutara el comando determinado.</span><span class="sxs-lookup"><span data-stu-id="68c06-288">Displays a summary of what would happen if the given command were run.</span></span> <span data-ttu-id="68c06-289">Disponible a partir del SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="68c06-289">Available since .NET Core 2.2 SDK.</span></span>

- **`--force`**

  <span data-ttu-id="68c06-290">Fuerza la generación de contenido incluso aunque se vayan a cambiar los archivos existentes.</span><span class="sxs-lookup"><span data-stu-id="68c06-290">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="68c06-291">Es necesario si la plantilla elegida invalidará los archivos existentes en el directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="68c06-291">This is required when the template chosen would override existing files in the output directory.</span></span>

- **`-h|--help`**

  <span data-ttu-id="68c06-292">Imprime la ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="68c06-292">Prints out help for the command.</span></span> <span data-ttu-id="68c06-293">Puede invocarse para el propio comando `dotnet new` o para cualquier plantilla.</span><span class="sxs-lookup"><span data-stu-id="68c06-293">It can be invoked for the `dotnet new` command itself or for any template.</span></span> <span data-ttu-id="68c06-294">Por ejemplo: `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="68c06-294">For example, `dotnet new mvc --help`.</span></span>

- **`-i|--install <PATH|NUGET_ID>`**

  <span data-ttu-id="68c06-295">Instala un paquete de plantillas desde los parámetros `PATH` o `NUGET_ID` proporcionados.</span><span class="sxs-lookup"><span data-stu-id="68c06-295">Installs a template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="68c06-296">Si quiere instalar una versión preliminar de un paquete de plantilla, tendrá que especificar la versión en el formato de `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="68c06-296">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="68c06-297">De forma predeterminada, `dotnet new` pasa \* para la versión, que representa la última versión estable del paquete.</span><span class="sxs-lookup"><span data-stu-id="68c06-297">By default, `dotnet new` passes \* for the version, which represents the latest stable package version.</span></span> <span data-ttu-id="68c06-298">Vea un ejemplo en la sección [Ejemplos](#examples).</span><span class="sxs-lookup"><span data-stu-id="68c06-298">See an example in the [Examples](#examples) section.</span></span>
  
  <span data-ttu-id="68c06-299">Si ya hay instalada una versión de la plantilla al ejecutar este comando, la plantilla se actualizará a la versión especificada o a la versión estable más reciente si no se ha especificado ninguna versión.</span><span class="sxs-lookup"><span data-stu-id="68c06-299">If a version of the template was already installed when you run this command, the template will be updated to the specified version, or to the latest stable version if no version was specified.</span></span>

  <span data-ttu-id="68c06-300">Para obtener información sobre cómo crear plantillas personalizadas, consulte [Plantillas personalizadas para dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="68c06-300">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

- **`-l|--list`**

  <span data-ttu-id="68c06-301">Muestra las plantillas que contienen el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="68c06-301">Lists templates containing the specified name.</span></span> <span data-ttu-id="68c06-302">Si no se especifica ningún nombre, enumera todas las plantillas.</span><span class="sxs-lookup"><span data-stu-id="68c06-302">If no name is specified, lists all templates.</span></span>

- **`-lang|--language {C#|F#|VB}`**

  <span data-ttu-id="68c06-303">El lenguaje de la plantilla que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="68c06-303">The language of the template to create.</span></span> <span data-ttu-id="68c06-304">El lenguaje aceptado cambia según la plantilla (vea los valores predeterminados en la sección [argumentos](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="68c06-304">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="68c06-305">No es válido para algunas plantillas.</span><span class="sxs-lookup"><span data-stu-id="68c06-305">Not valid for some templates.</span></span>

  > [!NOTE]
  > <span data-ttu-id="68c06-306">Algunos shells interpretan `#` como un carácter especial.</span><span class="sxs-lookup"><span data-stu-id="68c06-306">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="68c06-307">En esos casos, incluya el valor del parámetro de lenguaje entre comillas.</span><span class="sxs-lookup"><span data-stu-id="68c06-307">In those cases, enclose the language parameter value in quotes.</span></span> <span data-ttu-id="68c06-308">Por ejemplo: `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="68c06-308">For example, `dotnet new console -lang "F#"`.</span></span>

- **`-n|--name <OUTPUT_NAME>`**

  <span data-ttu-id="68c06-309">El nombre de la salida creada.</span><span class="sxs-lookup"><span data-stu-id="68c06-309">The name for the created output.</span></span> <span data-ttu-id="68c06-310">Si no se especifica ningún nombre, se usa el nombre del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="68c06-310">If no name is specified, the name of the current directory is used.</span></span>

- **`--nuget-source <SOURCE>`**

  <span data-ttu-id="68c06-311">Especifica un origen de NuGet para usarlo durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="68c06-311">Specifies a NuGet source to use during install.</span></span> <span data-ttu-id="68c06-312">Disponible a partir del SDK de .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="68c06-312">Available since .NET Core 2.1 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="68c06-313">La ubicación para colocar la salida generada.</span><span class="sxs-lookup"><span data-stu-id="68c06-313">Location to place the generated output.</span></span> <span data-ttu-id="68c06-314">El valor predeterminado es el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="68c06-314">The default is the current directory.</span></span>

- **`--type <TYPE>`**

  <span data-ttu-id="68c06-315">Filtra plantillas en función de los tipos disponibles.</span><span class="sxs-lookup"><span data-stu-id="68c06-315">Filters templates based on available types.</span></span> <span data-ttu-id="68c06-316">Los valores predefinidos son `project`, `item` u `other`.</span><span class="sxs-lookup"><span data-stu-id="68c06-316">Predefined values are `project`, `item`, or `other`.</span></span>

- **`-u|--uninstall [PATH|NUGET_ID]`**

  <span data-ttu-id="68c06-317">Desinstala un paquete de plantillas en los parámetros `PATH` o `NUGET_ID` proporcionados.</span><span class="sxs-lookup"><span data-stu-id="68c06-317">Uninstalls a template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="68c06-318">Si no se especifica el valor `<PATH|NUGET_ID>`, se muestran todos los paquetes de plantillas instalados actualmente y sus plantillas asociadas.</span><span class="sxs-lookup"><span data-stu-id="68c06-318">When the `<PATH|NUGET_ID>` value isn't specified, all currently installed template packs and their associated templates are displayed.</span></span> <span data-ttu-id="68c06-319">Al especificar `NUGET_ID`, no incluya el número de versión.</span><span class="sxs-lookup"><span data-stu-id="68c06-319">When specifying `NUGET_ID`, don't include the version number.</span></span>

  <span data-ttu-id="68c06-320">Si no especifica un parámetro en esta opción, el comando muestra las plantillas instaladas y detalles sobre ellas.</span><span class="sxs-lookup"><span data-stu-id="68c06-320">If you don't specify a parameter to this option, the command lists the installed templates and details about them.</span></span>

  > [!NOTE]
  > <span data-ttu-id="68c06-321">Para desinstalar una plantilla mediante `PATH`, debe usar el nombre completo de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="68c06-321">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="68c06-322">Por ejemplo, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* funcionará, pero *./GarciaSoftware.ConsoleTemplate.CSharp* desde la carpeta contenedora no lo hará.</span><span class="sxs-lookup"><span data-stu-id="68c06-322">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
  > <span data-ttu-id="68c06-323">No incluya ninguna barra diagonal para finalizar el directorio en la ruta de acceso a la plantilla.</span><span class="sxs-lookup"><span data-stu-id="68c06-323">Don't include a final terminating directory slash on your template path.</span></span>

- **`--update-apply`**

  <span data-ttu-id="68c06-324">Comprueba si hay actualizaciones disponibles de los paquetes de plantillas instalados actualmente y las instala.</span><span class="sxs-lookup"><span data-stu-id="68c06-324">Checks if there are updates available for the template packs that are currently installed and installs them.</span></span> <span data-ttu-id="68c06-325">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="68c06-325">Available since .NET Core 3.0 SDK.</span></span>

- **`--update-check`**

  <span data-ttu-id="68c06-326">Comprueba si hay actualizaciones disponibles de los paquetes de plantillas instalados actualmente.</span><span class="sxs-lookup"><span data-stu-id="68c06-326">Checks if there are updates available for the template packs that are currently installed.</span></span> <span data-ttu-id="68c06-327">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="68c06-327">Available since .NET Core 3.0 SDK.</span></span>

## <a name="template-options"></a><span data-ttu-id="68c06-328">Opciones de plantilla</span><span class="sxs-lookup"><span data-stu-id="68c06-328">Template options</span></span>

<span data-ttu-id="68c06-329">Cada plantilla de proyecto puede tener opciones adicionales disponibles.</span><span class="sxs-lookup"><span data-stu-id="68c06-329">Each project template may have additional options available.</span></span> <span data-ttu-id="68c06-330">Las plantillas principales tienen las siguientes opciones adicionales:</span><span class="sxs-lookup"><span data-stu-id="68c06-330">The core templates have the following additional options:</span></span>

### <a name="console"></a><span data-ttu-id="68c06-331">consola</span><span class="sxs-lookup"><span data-stu-id="68c06-331">console</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="68c06-332">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="68c06-332">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="68c06-333">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="68c06-333">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="68c06-334">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="68c06-334">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="68c06-335">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="68c06-335">SDK version</span></span> | <span data-ttu-id="68c06-336">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="68c06-336">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="68c06-337">3.1</span><span class="sxs-lookup"><span data-stu-id="68c06-337">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="68c06-338">3.0</span><span class="sxs-lookup"><span data-stu-id="68c06-338">3.0</span></span>         | `netcoreapp3.0` |

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="68c06-339">Establece la propiedad `LangVersion` en el archivo del proyecto creado.</span><span class="sxs-lookup"><span data-stu-id="68c06-339">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="68c06-340">Por ejemplo, use `--langVersion 7.3` para emplear C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="68c06-340">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="68c06-341">No es compatible con F#.</span><span class="sxs-lookup"><span data-stu-id="68c06-341">Not supported for F#.</span></span> <span data-ttu-id="68c06-342">Disponible a partir del SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="68c06-342">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="68c06-343">Para obtener una lista de las versiones predeterminadas de C#, vea [Valores predeterminados](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="68c06-343">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="68c06-344">Si se especifica, no se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="68c06-344">If specified, doesn't execute an implicit restore during project creation.</span></span> <span data-ttu-id="68c06-345">Disponible a partir del SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="68c06-345">Available since .NET Core 2.2 SDK.</span></span>

***

### <a name="classlib"></a><span data-ttu-id="68c06-346">classlib</span><span class="sxs-lookup"><span data-stu-id="68c06-346">classlib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="68c06-347">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="68c06-347">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="68c06-348">Valores: `netcoreapp<version>` para crear una biblioteca de clases de .NET Core o `netstandard<version>` para crear una biblioteca de clases de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="68c06-348">Values: `netcoreapp<version>` to create a .NET Core Class Library or `netstandard<version>` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="68c06-349">El valor predeterminado es `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="68c06-349">The default value is `netstandard2.0`.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="68c06-350">Establece la propiedad `LangVersion` en el archivo del proyecto creado.</span><span class="sxs-lookup"><span data-stu-id="68c06-350">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="68c06-351">Por ejemplo, use `--langVersion 7.3` para emplear C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="68c06-351">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="68c06-352">No es compatible con F#.</span><span class="sxs-lookup"><span data-stu-id="68c06-352">Not supported for F#.</span></span> <span data-ttu-id="68c06-353">Disponible a partir del SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="68c06-353">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="68c06-354">Para obtener una lista de las versiones predeterminadas de C#, vea [Valores predeterminados](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="68c06-354">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="68c06-355">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="68c06-355">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="wpf-wpflib-wpfcustomcontrollib-wpfusercontrollib"></a><a name="wpf"></a> <span data-ttu-id="68c06-356">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="68c06-356">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="68c06-357">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="68c06-357">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="68c06-358">El valor predeterminado es `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="68c06-358">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="68c06-359">Disponible a partir del SDK de .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="68c06-359">Available since .NET Core 3.1 SDK.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="68c06-360">Establece la propiedad `LangVersion` en el archivo del proyecto creado.</span><span class="sxs-lookup"><span data-stu-id="68c06-360">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="68c06-361">Por ejemplo, use `--langVersion 7.3` para emplear C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="68c06-361">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="68c06-362">Para obtener una lista de las versiones predeterminadas de C#, vea [Valores predeterminados](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="68c06-362">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="68c06-363">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="68c06-363">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="winforms-winformslib"></a><a name="winforms"></a> <span data-ttu-id="68c06-364">winforms, winformslib</span><span class="sxs-lookup"><span data-stu-id="68c06-364">winforms, winformslib</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="68c06-365">Establece la propiedad `LangVersion` en el archivo del proyecto creado.</span><span class="sxs-lookup"><span data-stu-id="68c06-365">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="68c06-366">Por ejemplo, use `--langVersion 7.3` para emplear C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="68c06-366">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="68c06-367">Para obtener una lista de las versiones predeterminadas de C#, vea [Valores predeterminados](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="68c06-367">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="68c06-368">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="68c06-368">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="worker-grpc"></a><a name="web-others"></a> <span data-ttu-id="68c06-369">worker, grpc</span><span class="sxs-lookup"><span data-stu-id="68c06-369">worker, grpc</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="68c06-370">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="68c06-370">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="68c06-371">El valor predeterminado es `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="68c06-371">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="68c06-372">Disponible a partir del SDK de .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="68c06-372">Available since .NET Core 3.1 SDK.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="68c06-373">Excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="68c06-373">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="68c06-374">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="68c06-374">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="mstest-xunit"></a><a name="test"></a> <span data-ttu-id="68c06-375">mstest, xunit</span><span class="sxs-lookup"><span data-stu-id="68c06-375">mstest, xunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="68c06-376">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="68c06-376">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="68c06-377">Opción disponible a partir del SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="68c06-377">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="68c06-378">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="68c06-378">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="68c06-379">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="68c06-379">SDK version</span></span> | <span data-ttu-id="68c06-380">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="68c06-380">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="68c06-381">3.1</span><span class="sxs-lookup"><span data-stu-id="68c06-381">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="68c06-382">3.0</span><span class="sxs-lookup"><span data-stu-id="68c06-382">3.0</span></span>         | `netcoreapp3.0` |

- **`-p|--enable-pack`**

  <span data-ttu-id="68c06-383">Habilita el empaquetado del proyecto mediante [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="68c06-383">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="68c06-384">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="68c06-384">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="nunit"></a><span data-ttu-id="68c06-385">nunit</span><span class="sxs-lookup"><span data-stu-id="68c06-385">nunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="68c06-386">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="68c06-386">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="68c06-387">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="68c06-387">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="68c06-388">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="68c06-388">SDK version</span></span> | <span data-ttu-id="68c06-389">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="68c06-389">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="68c06-390">3.1</span><span class="sxs-lookup"><span data-stu-id="68c06-390">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="68c06-391">3.0</span><span class="sxs-lookup"><span data-stu-id="68c06-391">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="68c06-392">2.2</span><span class="sxs-lookup"><span data-stu-id="68c06-392">2.2</span></span>         | `netcoreapp2.2` |
  | <span data-ttu-id="68c06-393">2.1</span><span class="sxs-lookup"><span data-stu-id="68c06-393">2.1</span></span>         | `netcoreapp2.1` |

- **`-p|--enable-pack`**

  <span data-ttu-id="68c06-394">Habilita el empaquetado del proyecto mediante [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="68c06-394">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="68c06-395">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="68c06-395">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="page"></a><span data-ttu-id="68c06-396">página</span><span class="sxs-lookup"><span data-stu-id="68c06-396">page</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="68c06-397">Espacio de nombres del código generado.</span><span class="sxs-lookup"><span data-stu-id="68c06-397">Namespace for the generated code.</span></span> <span data-ttu-id="68c06-398">El valor predeterminado es `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="68c06-398">The default value is `MyApp.Namespace`.</span></span>

- **`-np|--no-pagemodel`**

  <span data-ttu-id="68c06-399">Crea la página sin PageModel.</span><span class="sxs-lookup"><span data-stu-id="68c06-399">Creates the page without a PageModel.</span></span>

***

### <a name="viewimports-proto"></a><a name="namespace"></a> <span data-ttu-id="68c06-400">viewimports, proto</span><span class="sxs-lookup"><span data-stu-id="68c06-400">viewimports, proto</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="68c06-401">Espacio de nombres del código generado.</span><span class="sxs-lookup"><span data-stu-id="68c06-401">Namespace for the generated code.</span></span> <span data-ttu-id="68c06-402">El valor predeterminado es `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="68c06-402">The default value is `MyApp.Namespace`.</span></span>

***

### <a name="blazorserver"></a><span data-ttu-id="68c06-403">blazorserver</span><span class="sxs-lookup"><span data-stu-id="68c06-403">blazorserver</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="68c06-404">Tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="68c06-404">The type of authentication to use.</span></span> <span data-ttu-id="68c06-405">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="68c06-405">The possible values are:</span></span>

  - <span data-ttu-id="68c06-406">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="68c06-406">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="68c06-407">`Individual`: autenticación individual.</span><span class="sxs-lookup"><span data-stu-id="68c06-407">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="68c06-408">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="68c06-408">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="68c06-409">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="68c06-409">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="68c06-410">`MultiOrg`: autenticación organizativa para varios inquilinos.</span><span class="sxs-lookup"><span data-stu-id="68c06-410">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="68c06-411">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="68c06-411">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="68c06-412">Instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="68c06-412">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="68c06-413">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="68c06-413">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="68c06-414">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="68c06-414">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="68c06-415">Identificador de la directiva de registro e inicio de sesión de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="68c06-415">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="68c06-416">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="68c06-416">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="68c06-417">Identificador de la directiva de restablecimiento de contraseñas de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="68c06-417">The reset password policy ID for this project.</span></span> <span data-ttu-id="68c06-418">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="68c06-418">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="68c06-419">Identificador de la directiva de edición de perfiles de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="68c06-419">The edit profile policy ID for this project.</span></span> <span data-ttu-id="68c06-420">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="68c06-420">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="68c06-421">Instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="68c06-421">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="68c06-422">Úsela con las autenticaciones `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="68c06-422">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="68c06-423">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="68c06-423">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="68c06-424">Identificador de cliente de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="68c06-424">The Client ID for this project.</span></span> <span data-ttu-id="68c06-425">Úsela con las autenticaciones `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="68c06-425">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="68c06-426">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="68c06-426">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="68c06-427">Dominio del inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="68c06-427">The domain for the directory tenant.</span></span> <span data-ttu-id="68c06-428">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="68c06-428">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="68c06-429">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="68c06-429">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="68c06-430">Identificador de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="68c06-430">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="68c06-431">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="68c06-431">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="68c06-432">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="68c06-432">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="68c06-433">Ruta de acceso de solicitud de la ruta de acceso de la base de la aplicación del URI de redirección.</span><span class="sxs-lookup"><span data-stu-id="68c06-433">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="68c06-434">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="68c06-434">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="68c06-435">El valor predeterminado es `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="68c06-435">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="68c06-436">Concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="68c06-436">Allows this application read-access to the directory.</span></span> <span data-ttu-id="68c06-437">Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="68c06-437">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="68c06-438">Excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="68c06-438">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="68c06-439">Desactiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="68c06-439">Turns off HTTPS.</span></span> <span data-ttu-id="68c06-440">Esta opción solo se aplica si no se usan `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg` en `--auth`.</span><span class="sxs-lookup"><span data-stu-id="68c06-440">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="68c06-441">Especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="68c06-441">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="68c06-442">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="68c06-442">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--no-restore`**

  <span data-ttu-id="68c06-443">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="68c06-443">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="web"></a><span data-ttu-id="68c06-444">web</span><span class="sxs-lookup"><span data-stu-id="68c06-444">web</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="68c06-445">Excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="68c06-445">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="68c06-446">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="68c06-446">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="68c06-447">Opción no disponible en el SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="68c06-447">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="68c06-448">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="68c06-448">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="68c06-449">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="68c06-449">SDK version</span></span> | <span data-ttu-id="68c06-450">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="68c06-450">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="68c06-451">3.1</span><span class="sxs-lookup"><span data-stu-id="68c06-451">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="68c06-452">3.0</span><span class="sxs-lookup"><span data-stu-id="68c06-452">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="68c06-453">2.1</span><span class="sxs-lookup"><span data-stu-id="68c06-453">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="68c06-454">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="68c06-454">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="68c06-455">Desactiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="68c06-455">Turns off HTTPS.</span></span>

***

### <a name="mvc-webapp"></a><a name="web-options"></a> <span data-ttu-id="68c06-456">mvc, webapp</span><span class="sxs-lookup"><span data-stu-id="68c06-456">mvc, webapp</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="68c06-457">Tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="68c06-457">The type of authentication to use.</span></span> <span data-ttu-id="68c06-458">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="68c06-458">The possible values are:</span></span>

  - <span data-ttu-id="68c06-459">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="68c06-459">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="68c06-460">`Individual`: autenticación individual.</span><span class="sxs-lookup"><span data-stu-id="68c06-460">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="68c06-461">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="68c06-461">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="68c06-462">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="68c06-462">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="68c06-463">`MultiOrg`: autenticación organizativa para varios inquilinos.</span><span class="sxs-lookup"><span data-stu-id="68c06-463">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="68c06-464">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="68c06-464">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="68c06-465">Instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="68c06-465">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="68c06-466">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="68c06-466">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="68c06-467">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="68c06-467">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="68c06-468">Identificador de la directiva de registro e inicio de sesión de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="68c06-468">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="68c06-469">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="68c06-469">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="68c06-470">Identificador de la directiva de restablecimiento de contraseñas de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="68c06-470">The reset password policy ID for this project.</span></span> <span data-ttu-id="68c06-471">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="68c06-471">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="68c06-472">Identificador de la directiva de edición de perfiles de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="68c06-472">The edit profile policy ID for this project.</span></span> <span data-ttu-id="68c06-473">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="68c06-473">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="68c06-474">Instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="68c06-474">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="68c06-475">Úsela con las autenticaciones `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="68c06-475">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="68c06-476">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="68c06-476">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="68c06-477">Identificador de cliente de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="68c06-477">The Client ID for this project.</span></span> <span data-ttu-id="68c06-478">Úsela con las autenticaciones `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="68c06-478">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="68c06-479">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="68c06-479">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="68c06-480">Dominio del inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="68c06-480">The domain for the directory tenant.</span></span> <span data-ttu-id="68c06-481">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="68c06-481">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="68c06-482">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="68c06-482">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="68c06-483">Identificador de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="68c06-483">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="68c06-484">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="68c06-484">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="68c06-485">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="68c06-485">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="68c06-486">Ruta de acceso de solicitud de la ruta de acceso de la base de la aplicación del URI de redirección.</span><span class="sxs-lookup"><span data-stu-id="68c06-486">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="68c06-487">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="68c06-487">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="68c06-488">El valor predeterminado es `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="68c06-488">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="68c06-489">Concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="68c06-489">Allows this application read-access to the directory.</span></span> <span data-ttu-id="68c06-490">Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="68c06-490">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="68c06-491">Excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="68c06-491">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="68c06-492">Desactiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="68c06-492">Turns off HTTPS.</span></span> <span data-ttu-id="68c06-493">Esta opción solo se aplica si no se usan `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="68c06-493">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="68c06-494">Especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="68c06-494">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="68c06-495">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="68c06-495">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="68c06-496">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="68c06-496">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="68c06-497">Opción disponible a partir del SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="68c06-497">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="68c06-498">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="68c06-498">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="68c06-499">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="68c06-499">SDK version</span></span> | <span data-ttu-id="68c06-500">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="68c06-500">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="68c06-501">3.1</span><span class="sxs-lookup"><span data-stu-id="68c06-501">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="68c06-502">3.0</span><span class="sxs-lookup"><span data-stu-id="68c06-502">3.0</span></span>         | `netcoreapp3.0` |

- **`--no-restore`**

  <span data-ttu-id="68c06-503">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="68c06-503">Doesn't execute an implicit restore during project creation.</span></span>

- **`--use-browserlink`**

  <span data-ttu-id="68c06-504">Incluye BrowserLink en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="68c06-504">Includes BrowserLink in the project.</span></span> <span data-ttu-id="68c06-505">Opción no disponible en el SDK de .NET Core 2.2 y 3.1.</span><span class="sxs-lookup"><span data-stu-id="68c06-505">Option not available in .NET Core 2.2 and 3.1 SDK.</span></span>

- **`-rrc|--razor-runtime-compilation`**

  <span data-ttu-id="68c06-506">Determina si el proyecto está configurado para usar la [compilación en tiempo de ejecución de Razor](/aspnet/core/mvc/views/view-compilation#runtime-compilation) en las compilaciones de depuración.</span><span class="sxs-lookup"><span data-stu-id="68c06-506">Determines if the project is configured to use [Razor runtime compilation](/aspnet/core/mvc/views/view-compilation#runtime-compilation) in Debug builds.</span></span> <span data-ttu-id="68c06-507">Opción disponible a partir del SDK de .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="68c06-507">Option available since .NET Core 3.1 SDK.</span></span>

***

### <a name="angular-react"></a><a name="spa"></a> <span data-ttu-id="68c06-508">angular, react</span><span class="sxs-lookup"><span data-stu-id="68c06-508">angular, react</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="68c06-509">Tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="68c06-509">The type of authentication to use.</span></span> <span data-ttu-id="68c06-510">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="68c06-510">Available since .NET Core 3.0 SDK.</span></span>
  
  <span data-ttu-id="68c06-511">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="68c06-511">The possible values are:</span></span>

  - <span data-ttu-id="68c06-512">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="68c06-512">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="68c06-513">`Individual`: autenticación individual.</span><span class="sxs-lookup"><span data-stu-id="68c06-513">`Individual` - Individual authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="68c06-514">Excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="68c06-514">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="68c06-515">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="68c06-515">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="68c06-516">Desactiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="68c06-516">Turns off HTTPS.</span></span> <span data-ttu-id="68c06-517">Esta opción solo se aplica si la autenticación es `None`.</span><span class="sxs-lookup"><span data-stu-id="68c06-517">This option only applies if authentication is `None`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="68c06-518">Especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="68c06-518">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="68c06-519">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="68c06-519">Only applies to `Individual` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="68c06-520">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="68c06-520">Available since .NET Core 3.0 SDK.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="68c06-521">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="68c06-521">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="68c06-522">Opción no disponible en el SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="68c06-522">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="68c06-523">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="68c06-523">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="68c06-524">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="68c06-524">SDK version</span></span> | <span data-ttu-id="68c06-525">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="68c06-525">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="68c06-526">3.1</span><span class="sxs-lookup"><span data-stu-id="68c06-526">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="68c06-527">3.0</span><span class="sxs-lookup"><span data-stu-id="68c06-527">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="68c06-528">2.1</span><span class="sxs-lookup"><span data-stu-id="68c06-528">2.1</span></span>         | `netcoreapp2.0` |

***

### <a name="reactredux"></a><span data-ttu-id="68c06-529">reactredux</span><span class="sxs-lookup"><span data-stu-id="68c06-529">reactredux</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="68c06-530">Excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="68c06-530">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="68c06-531">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="68c06-531">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="68c06-532">Opción no disponible en el SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="68c06-532">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="68c06-533">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="68c06-533">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="68c06-534">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="68c06-534">SDK version</span></span> | <span data-ttu-id="68c06-535">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="68c06-535">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="68c06-536">3.1</span><span class="sxs-lookup"><span data-stu-id="68c06-536">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="68c06-537">3.0</span><span class="sxs-lookup"><span data-stu-id="68c06-537">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="68c06-538">2.1</span><span class="sxs-lookup"><span data-stu-id="68c06-538">2.1</span></span>         | `netcoreapp2.0` |

- **`--no-restore`**

  <span data-ttu-id="68c06-539">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="68c06-539">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="68c06-540">Desactiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="68c06-540">Turns off HTTPS.</span></span>

***

### <a name="razorclasslib"></a><span data-ttu-id="68c06-541">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="68c06-541">razorclasslib</span></span>

- **`--no-restore`**

  <span data-ttu-id="68c06-542">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="68c06-542">Doesn't execute an implicit restore during project creation.</span></span>

- **`-s|--support-pages-and-views`**

  <span data-ttu-id="68c06-543">Permite agregar vistas y páginas de Razor tradicionales además de los componentes a esta biblioteca.</span><span class="sxs-lookup"><span data-stu-id="68c06-543">Supports adding traditional Razor pages and Views in addition to components to this library.</span></span> <span data-ttu-id="68c06-544">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="68c06-544">Available since .NET Core 3.0 SDK.</span></span>

***
  
### <a name="webapi"></a><span data-ttu-id="68c06-545">webapi</span><span class="sxs-lookup"><span data-stu-id="68c06-545">webapi</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="68c06-546">Tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="68c06-546">The type of authentication to use.</span></span> <span data-ttu-id="68c06-547">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="68c06-547">The possible values are:</span></span>

  - <span data-ttu-id="68c06-548">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="68c06-548">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="68c06-549">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="68c06-549">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="68c06-550">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="68c06-550">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="68c06-551">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="68c06-551">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="68c06-552">Instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="68c06-552">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="68c06-553">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="68c06-553">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="68c06-554">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="68c06-554">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="68c06-555">Identificador de la directiva de registro e inicio de sesión de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="68c06-555">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="68c06-556">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="68c06-556">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="68c06-557">Instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="68c06-557">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="68c06-558">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="68c06-558">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="68c06-559">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="68c06-559">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="68c06-560">Identificador de cliente de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="68c06-560">The Client ID for this project.</span></span> <span data-ttu-id="68c06-561">Úsela con las autenticaciones `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="68c06-561">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="68c06-562">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="68c06-562">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="68c06-563">Dominio del inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="68c06-563">The domain for the directory tenant.</span></span> <span data-ttu-id="68c06-564">Úsela con las autenticaciones `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="68c06-564">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="68c06-565">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="68c06-565">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="68c06-566">Identificador de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="68c06-566">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="68c06-567">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="68c06-567">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="68c06-568">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="68c06-568">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="68c06-569">Concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="68c06-569">Allows this application read-access to the directory.</span></span> <span data-ttu-id="68c06-570">Solo se aplica a la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="68c06-570">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="68c06-571">Excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="68c06-571">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="68c06-572">Desactiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="68c06-572">Turns off HTTPS.</span></span> <span data-ttu-id="68c06-573">`app.UseHsts` y `app.UseHttpsRedirection` no se agregan a `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="68c06-573">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="68c06-574">Esta opción solo se aplica si no se usan `IndividualB2C` o `SingleOrg` en la autenticación.</span><span class="sxs-lookup"><span data-stu-id="68c06-574">This option only applies if `IndividualB2C` or `SingleOrg` aren't being used for authentication.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="68c06-575">Especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="68c06-575">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="68c06-576">Solo se aplica a la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="68c06-576">Only applies to `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="68c06-577">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="68c06-577">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="68c06-578">Opción no disponible en el SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="68c06-578">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="68c06-579">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="68c06-579">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="68c06-580">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="68c06-580">SDK version</span></span> | <span data-ttu-id="68c06-581">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="68c06-581">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="68c06-582">3.1</span><span class="sxs-lookup"><span data-stu-id="68c06-582">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="68c06-583">3.0</span><span class="sxs-lookup"><span data-stu-id="68c06-583">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="68c06-584">2.1</span><span class="sxs-lookup"><span data-stu-id="68c06-584">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="68c06-585">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="68c06-585">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="globaljson"></a><span data-ttu-id="68c06-586">globaljson</span><span class="sxs-lookup"><span data-stu-id="68c06-586">globaljson</span></span>

- **`--sdk-version <VERSION_NUMBER>`**

  <span data-ttu-id="68c06-587">Especifica la versión del SDK de .NET Core que se usará en el archivo *global.json*.</span><span class="sxs-lookup"><span data-stu-id="68c06-587">Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

***

## <a name="examples"></a><span data-ttu-id="68c06-588">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="68c06-588">Examples</span></span>

- <span data-ttu-id="68c06-589">Creación de un proyecto de aplicación de consola de C# mediante la especificación del nombre de plantilla:</span><span class="sxs-lookup"><span data-stu-id="68c06-589">Create a C# console application project by specifying the template name:</span></span>

  ```dotnetcli
  dotnet new "Console Application"
  ```

- <span data-ttu-id="68c06-590">Creación de un proyecto de aplicación de consola con F# en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="68c06-590">Create an F# console application project in the current directory:</span></span>

  ```dotnetcli
  dotnet new console -lang F#
  ```

- <span data-ttu-id="68c06-591">Creación de un proyecto de biblioteca de clases de .NET Standard en el directorio especificado:</span><span class="sxs-lookup"><span data-stu-id="68c06-591">Create a .NET Standard class library project in the specified directory:</span></span>

  ```dotnetcli
  dotnet new classlib -lang VB -o MyLibrary
  ```

- <span data-ttu-id="68c06-592">Creación de un proyecto MVC de ASP.NET Core C# en el directorio actual sin autenticación:</span><span class="sxs-lookup"><span data-stu-id="68c06-592">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

  ```dotnetcli
  dotnet new mvc -au None
  ```

- <span data-ttu-id="68c06-593">Creación de un proyecto de xUnit:</span><span class="sxs-lookup"><span data-stu-id="68c06-593">Create a new xUnit project:</span></span>

  ```dotnetcli
  dotnet new xunit
  ```

- <span data-ttu-id="68c06-594">Enumeración de todas las plantillas disponibles en las plantillas de aplicación de página única (SPA):</span><span class="sxs-lookup"><span data-stu-id="68c06-594">List all templates available for Single Page Application (SPA) templates:</span></span>

  ```dotnetcli
  dotnet new spa -l
  ```

- <span data-ttu-id="68c06-595">Enumeración de todas las plantillas que coinciden con la subcadena *we*.</span><span class="sxs-lookup"><span data-stu-id="68c06-595">List all templates matching the *we* substring.</span></span> <span data-ttu-id="68c06-596">No se encuentra ninguna coincidencia exacta, por lo que se ejecuta la coincidencia de subcadena con las columnas de nombre corto y de nombre.</span><span class="sxs-lookup"><span data-stu-id="68c06-596">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

  ```dotnetcli
  dotnet new we -l
  ```

- <span data-ttu-id="68c06-597">Intento de invocar a la plantilla que coincide con *ng*.</span><span class="sxs-lookup"><span data-stu-id="68c06-597">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="68c06-598">Si no se puede determinar una única coincidencia, se enumeran las plantillas que son coincidencias parciales.</span><span class="sxs-lookup"><span data-stu-id="68c06-598">If a single match can't be determined, list the templates that are partial matches.</span></span>

  ```dotnetcli
  dotnet new ng
  ```

- <span data-ttu-id="68c06-599">Instalación de la versión 2.0 de las plantillas de SPA de ASP.NET Core:</span><span class="sxs-lookup"><span data-stu-id="68c06-599">Install version 2.0 of the SPA templates for ASP.NET Core:</span></span>

  ```dotnetcli
  dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0
  ```

- <span data-ttu-id="68c06-600">Enumeración de las plantillas instaladas y detalles sobre ellas, incluido cómo desinstalarlas:</span><span class="sxs-lookup"><span data-stu-id="68c06-600">List the installed templates and details about them, including how to uninstall them:</span></span>

  ```dotnetcli
  dotnet new -u
  ```

- <span data-ttu-id="68c06-601">Creación de un archivo *global.json* en el directorio actual al establecer la versión del SDK en 3.1.101:</span><span class="sxs-lookup"><span data-stu-id="68c06-601">Create a *global.json* in the current directory setting the SDK version to 3.1.101:</span></span>

  ```dotnetcli
  dotnet new globaljson --sdk-version 3.1.101
  ```

## <a name="see-also"></a><span data-ttu-id="68c06-602">Vea también</span><span class="sxs-lookup"><span data-stu-id="68c06-602">See also</span></span>

- [<span data-ttu-id="68c06-603">Plantillas personalizadas para dotnet new</span><span class="sxs-lookup"><span data-stu-id="68c06-603">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="68c06-604">Creación de una plantilla personalizada para dotnet new</span><span class="sxs-lookup"><span data-stu-id="68c06-604">Create a custom template for dotnet new</span></span>](../tutorials/cli-templates-create-item-template.md)
- [<span data-ttu-id="68c06-605">Repositorio de GitHub dotnet/dotnet-template-samples</span><span class="sxs-lookup"><span data-stu-id="68c06-605">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- <span data-ttu-id="68c06-606">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new) (Plantillas disponibles para dotnet new)</span><span class="sxs-lookup"><span data-stu-id="68c06-606">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)</span></span>
