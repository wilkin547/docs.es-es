---
title: Comando dotnet new
description: El comando dotnet new crea proyectos de .NET en función de la plantilla especificada.
no-loc:
- Blazor
- WebAssembly
ms.date: 09/04/2020
ms.openlocfilehash: 3ee644f05ea5929ffc7b11054ef1d974b811f418
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634460"
---
# <a name="dotnet-new"></a><span data-ttu-id="da7f3-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="da7f3-103">dotnet new</span></span>

<span data-ttu-id="da7f3-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.0 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="da7f3-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="da7f3-105">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="da7f3-105">Name</span></span>

<span data-ttu-id="da7f3-106">`dotnet new`: crea un nuevo proyecto, archivo de configuración o solución según la plantilla especificada.</span><span class="sxs-lookup"><span data-stu-id="da7f3-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="da7f3-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="da7f3-107">Synopsis</span></span>

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install {PATH|NUGET_ID}]
    [-lang|--language {"C#"|"F#"|VB}] [-n|--name <OUTPUT_NAME>]
    [--nuget-source <SOURCE>] [-o|--output <OUTPUT_DIRECTORY>]
    [-u|--uninstall] [--update-apply] [--update-check] [Template options]

dotnet new <TEMPLATE> [-l|--list] [--type <TYPE>]

dotnet new -h|--help
```

## <a name="description"></a><span data-ttu-id="da7f3-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="da7f3-108">Description</span></span>

<span data-ttu-id="da7f3-109">El comando `dotnet new` crea un proyecto de .NET u otros artefactos basados en una plantilla.</span><span class="sxs-lookup"><span data-stu-id="da7f3-109">The `dotnet new` command creates a .NET project or other artifacts based on a template.</span></span>

<span data-ttu-id="da7f3-110">El comando llama al [motor de plantillas](https://github.com/dotnet/templating) para crear los artefactos en el disco basándose en las opciones y la plantilla especificadas.</span><span class="sxs-lookup"><span data-stu-id="da7f3-110">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="da7f3-111">Restauración implícita</span><span class="sxs-lookup"><span data-stu-id="da7f3-111">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="da7f3-112">Argumentos</span><span class="sxs-lookup"><span data-stu-id="da7f3-112">Arguments</span></span>

- **`TEMPLATE`**

  <span data-ttu-id="da7f3-113">La plantilla de la que se va a crear una instancia cuando se invoca el comando.</span><span class="sxs-lookup"><span data-stu-id="da7f3-113">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="da7f3-114">Cada plantilla puede tener opciones específicas que puede pasar.</span><span class="sxs-lookup"><span data-stu-id="da7f3-114">Each template might have specific options you can pass.</span></span> <span data-ttu-id="da7f3-115">Para obtener más información, vea [Opciones de plantilla](#template-options).</span><span class="sxs-lookup"><span data-stu-id="da7f3-115">For more information, see [Template options](#template-options).</span></span>

  <span data-ttu-id="da7f3-116">Puede ejecutar `dotnet new --list` o `dotnet new -l` para ver una lista de todas las plantillas instaladas.</span><span class="sxs-lookup"><span data-stu-id="da7f3-116">You can run `dotnet new --list` or `dotnet new -l` to see a list of all installed templates.</span></span> <span data-ttu-id="da7f3-117">Si el valor `TEMPLATE` no es una coincidencia exacta con el texto de la columna **Plantillas** o **Nombre corto** de la tabla devuelta, se realiza una coincidencia de subcadena con esas dos columnas.</span><span class="sxs-lookup"><span data-stu-id="da7f3-117">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column from the returned table, a substring match is performed on those two columns.</span></span>

  <span data-ttu-id="da7f3-118">A partir del SDK de .NET Core 3.0, la CLI busca plantillas en NuGet.org al invocar el comando `dotnet new` en las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="da7f3-118">Starting with .NET Core 3.0 SDK, the CLI searches for templates in NuGet.org when you invoke the `dotnet new` command in the following conditions:</span></span>

  - <span data-ttu-id="da7f3-119">Si la CLI no encuentra ninguna coincidencia de plantilla al invocar `dotnet new`, ni siquiera parcial.</span><span class="sxs-lookup"><span data-stu-id="da7f3-119">If the CLI can't find a template match when invoking `dotnet new`, not even partial.</span></span>
  - <span data-ttu-id="da7f3-120">Si hay disponible una versión más reciente de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="da7f3-120">If there's a newer version of the template available.</span></span> <span data-ttu-id="da7f3-121">En este caso, se crea el proyecto o el artefacto, pero la CLI le advierte de que hay una versión actualizada de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="da7f3-121">In this case, the project or artifact is created but the CLI warns you about an updated version of the template.</span></span>

  <span data-ttu-id="da7f3-122">En la tabla siguiente se muestran las plantillas que vienen preinstaladas con el SDK de .NET.</span><span class="sxs-lookup"><span data-stu-id="da7f3-122">The following table shows the templates that come pre-installed with the .NET SDK.</span></span> <span data-ttu-id="da7f3-123">El lenguaje predeterminado de la plantilla se muestra entre corchetes.</span><span class="sxs-lookup"><span data-stu-id="da7f3-123">The default language for the template is shown inside the brackets.</span></span> <span data-ttu-id="da7f3-124">Haga clic en el vínculo del nombre corto para ver las opciones específicas de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="da7f3-124">Click on the short name link to see the specific template options.</span></span>

| <span data-ttu-id="da7f3-125">Plantillas</span><span class="sxs-lookup"><span data-stu-id="da7f3-125">Templates</span></span>                                    | <span data-ttu-id="da7f3-126">Nombre corto</span><span class="sxs-lookup"><span data-stu-id="da7f3-126">Short name</span></span>                      | <span data-ttu-id="da7f3-127">Lenguaje</span><span class="sxs-lookup"><span data-stu-id="da7f3-127">Language</span></span>     | <span data-ttu-id="da7f3-128">Etiquetas</span><span class="sxs-lookup"><span data-stu-id="da7f3-128">Tags</span></span>                                  | <span data-ttu-id="da7f3-129">Inclusión</span><span class="sxs-lookup"><span data-stu-id="da7f3-129">Introduced</span></span> |
|----------------------------------------------|---------------------------------|--------------|---------------------------------------|------------|
| <span data-ttu-id="da7f3-130">Aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="da7f3-130">Console Application</span></span>                          | [<span data-ttu-id="da7f3-131">console</span><span class="sxs-lookup"><span data-stu-id="da7f3-131">console</span></span>](#console)             | <span data-ttu-id="da7f3-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="da7f3-132">[C#], F#, VB</span></span> | <span data-ttu-id="da7f3-133">Común/Consola</span><span class="sxs-lookup"><span data-stu-id="da7f3-133">Common/Console</span></span>                        | <span data-ttu-id="da7f3-134">1.0</span><span class="sxs-lookup"><span data-stu-id="da7f3-134">1.0</span></span>        |
| <span data-ttu-id="da7f3-135">Biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="da7f3-135">Class library</span></span>                                | [<span data-ttu-id="da7f3-136">classlib</span><span class="sxs-lookup"><span data-stu-id="da7f3-136">classlib</span></span>](#classlib)           | <span data-ttu-id="da7f3-137">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="da7f3-137">[C#], F#, VB</span></span> | <span data-ttu-id="da7f3-138">Común/Biblioteca</span><span class="sxs-lookup"><span data-stu-id="da7f3-138">Common/Library</span></span>                        | <span data-ttu-id="da7f3-139">1.0</span><span class="sxs-lookup"><span data-stu-id="da7f3-139">1.0</span></span>        |
| <span data-ttu-id="da7f3-140">Aplicación WPF</span><span class="sxs-lookup"><span data-stu-id="da7f3-140">WPF Application</span></span>                              | [<span data-ttu-id="da7f3-141">wpf</span><span class="sxs-lookup"><span data-stu-id="da7f3-141">wpf</span></span>](#wpf)                     | <span data-ttu-id="da7f3-142">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="da7f3-142">[C#], VB</span></span>     | <span data-ttu-id="da7f3-143">Común/WPF</span><span class="sxs-lookup"><span data-stu-id="da7f3-143">Common/WPF</span></span>                            | <span data-ttu-id="da7f3-144">3.0 (5.0 para VB)</span><span class="sxs-lookup"><span data-stu-id="da7f3-144">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="da7f3-145">Biblioteca de clases de WPF</span><span class="sxs-lookup"><span data-stu-id="da7f3-145">WPF Class library</span></span>                            | [<span data-ttu-id="da7f3-146">wpflib</span><span class="sxs-lookup"><span data-stu-id="da7f3-146">wpflib</span></span>](#wpf)                  | <span data-ttu-id="da7f3-147">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="da7f3-147">[C#], VB</span></span>     | <span data-ttu-id="da7f3-148">Común/WPF</span><span class="sxs-lookup"><span data-stu-id="da7f3-148">Common/WPF</span></span>                            | <span data-ttu-id="da7f3-149">3.0 (5.0 para VB)</span><span class="sxs-lookup"><span data-stu-id="da7f3-149">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="da7f3-150">Biblioteca de controles personalizados WPF</span><span class="sxs-lookup"><span data-stu-id="da7f3-150">WPF Custom Control Library</span></span>                   | [<span data-ttu-id="da7f3-151">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="da7f3-151">wpfcustomcontrollib</span></span>](#wpf)     | <span data-ttu-id="da7f3-152">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="da7f3-152">[C#], VB</span></span>     | <span data-ttu-id="da7f3-153">Común/WPF</span><span class="sxs-lookup"><span data-stu-id="da7f3-153">Common/WPF</span></span>                            | <span data-ttu-id="da7f3-154">3.0 (5.0 para VB)</span><span class="sxs-lookup"><span data-stu-id="da7f3-154">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="da7f3-155">Biblioteca de controles de usuario de WPF</span><span class="sxs-lookup"><span data-stu-id="da7f3-155">WPF User Control Library</span></span>                     | [<span data-ttu-id="da7f3-156">wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="da7f3-156">wpfusercontrollib</span></span>](#wpf)       | <span data-ttu-id="da7f3-157">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="da7f3-157">[C#], VB</span></span>     | <span data-ttu-id="da7f3-158">Común/WPF</span><span class="sxs-lookup"><span data-stu-id="da7f3-158">Common/WPF</span></span>                            | <span data-ttu-id="da7f3-159">3.0 (5.0 para VB)</span><span class="sxs-lookup"><span data-stu-id="da7f3-159">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="da7f3-160">Aplicación de Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="da7f3-160">Windows Forms (WinForms) Application</span></span>         | [<span data-ttu-id="da7f3-161">winforms</span><span class="sxs-lookup"><span data-stu-id="da7f3-161">winforms</span></span>](#winforms)           | <span data-ttu-id="da7f3-162">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="da7f3-162">[C#], VB</span></span>     | <span data-ttu-id="da7f3-163">Común/WinForms</span><span class="sxs-lookup"><span data-stu-id="da7f3-163">Common/WinForms</span></span>                       | <span data-ttu-id="da7f3-164">3.0 (5.0 para VB)</span><span class="sxs-lookup"><span data-stu-id="da7f3-164">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="da7f3-165">Biblioteca de clases de Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="da7f3-165">Windows Forms (WinForms) Class library</span></span>       | [<span data-ttu-id="da7f3-166">winformslib</span><span class="sxs-lookup"><span data-stu-id="da7f3-166">winformslib</span></span>](#winforms)        | <span data-ttu-id="da7f3-167">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="da7f3-167">[C#], VB</span></span>     | <span data-ttu-id="da7f3-168">Común/WinForms</span><span class="sxs-lookup"><span data-stu-id="da7f3-168">Common/WinForms</span></span>                       | <span data-ttu-id="da7f3-169">3.0 (5.0 para VB)</span><span class="sxs-lookup"><span data-stu-id="da7f3-169">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="da7f3-170">Servicio Worker</span><span class="sxs-lookup"><span data-stu-id="da7f3-170">Worker Service</span></span>                               | [<span data-ttu-id="da7f3-171">worker</span><span class="sxs-lookup"><span data-stu-id="da7f3-171">worker</span></span>](#web-others)           | <span data-ttu-id="da7f3-172">[C#]</span><span class="sxs-lookup"><span data-stu-id="da7f3-172">[C#]</span></span>         | <span data-ttu-id="da7f3-173">Común/Worker/Web</span><span class="sxs-lookup"><span data-stu-id="da7f3-173">Common/Worker/Web</span></span>                     | <span data-ttu-id="da7f3-174">3.0</span><span class="sxs-lookup"><span data-stu-id="da7f3-174">3.0</span></span>        |
| <span data-ttu-id="da7f3-175">Proyecto de prueba unitaria</span><span class="sxs-lookup"><span data-stu-id="da7f3-175">Unit Test Project</span></span>                            | [<span data-ttu-id="da7f3-176">mstest</span><span class="sxs-lookup"><span data-stu-id="da7f3-176">mstest</span></span>](#test)                 | <span data-ttu-id="da7f3-177">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="da7f3-177">[C#], F#, VB</span></span> | <span data-ttu-id="da7f3-178">Prueba/MSTest</span><span class="sxs-lookup"><span data-stu-id="da7f3-178">Test/MSTest</span></span>                           | <span data-ttu-id="da7f3-179">1.0</span><span class="sxs-lookup"><span data-stu-id="da7f3-179">1.0</span></span>        |
| <span data-ttu-id="da7f3-180">Proyecto de prueba de NUnit 3</span><span class="sxs-lookup"><span data-stu-id="da7f3-180">NUnit 3 Test Project</span></span>                         | [<span data-ttu-id="da7f3-181">nunit</span><span class="sxs-lookup"><span data-stu-id="da7f3-181">nunit</span></span>](#nunit)                 | <span data-ttu-id="da7f3-182">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="da7f3-182">[C#], F#, VB</span></span> | <span data-ttu-id="da7f3-183">Prueba/NUnit</span><span class="sxs-lookup"><span data-stu-id="da7f3-183">Test/NUnit</span></span>                            | <span data-ttu-id="da7f3-184">2.1.400</span><span class="sxs-lookup"><span data-stu-id="da7f3-184">2.1.400</span></span>    |
| <span data-ttu-id="da7f3-185">Elemento de prueba de NUnit 3</span><span class="sxs-lookup"><span data-stu-id="da7f3-185">NUnit 3 Test Item</span></span>                            | `nunit-test`                    | <span data-ttu-id="da7f3-186">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="da7f3-186">[C#], F#, VB</span></span> | <span data-ttu-id="da7f3-187">Prueba/NUnit</span><span class="sxs-lookup"><span data-stu-id="da7f3-187">Test/NUnit</span></span>                            | <span data-ttu-id="da7f3-188">2.2</span><span class="sxs-lookup"><span data-stu-id="da7f3-188">2.2</span></span>        |
| <span data-ttu-id="da7f3-189">Proyecto de prueba de xUnit</span><span class="sxs-lookup"><span data-stu-id="da7f3-189">xUnit Test Project</span></span>                           | [<span data-ttu-id="da7f3-190">xunit</span><span class="sxs-lookup"><span data-stu-id="da7f3-190">xunit</span></span>](#test)                  | <span data-ttu-id="da7f3-191">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="da7f3-191">[C#], F#, VB</span></span> | <span data-ttu-id="da7f3-192">Prueba/xUnit</span><span class="sxs-lookup"><span data-stu-id="da7f3-192">Test/xUnit</span></span>                            | <span data-ttu-id="da7f3-193">1.0</span><span class="sxs-lookup"><span data-stu-id="da7f3-193">1.0</span></span>        |
| <span data-ttu-id="da7f3-194">Componente Razor</span><span class="sxs-lookup"><span data-stu-id="da7f3-194">Razor Component</span></span>                              | `razorcomponent`                | <span data-ttu-id="da7f3-195">[C#]</span><span class="sxs-lookup"><span data-stu-id="da7f3-195">[C#]</span></span>         | <span data-ttu-id="da7f3-196">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="da7f3-196">Web/ASP.NET</span></span>                           | <span data-ttu-id="da7f3-197">3.0</span><span class="sxs-lookup"><span data-stu-id="da7f3-197">3.0</span></span>        |
| <span data-ttu-id="da7f3-198">Página de Razor</span><span class="sxs-lookup"><span data-stu-id="da7f3-198">Razor Page</span></span>                                   | [<span data-ttu-id="da7f3-199">page</span><span class="sxs-lookup"><span data-stu-id="da7f3-199">page</span></span>](#page)                   | <span data-ttu-id="da7f3-200">[C#]</span><span class="sxs-lookup"><span data-stu-id="da7f3-200">[C#]</span></span>         | <span data-ttu-id="da7f3-201">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="da7f3-201">Web/ASP.NET</span></span>                           | <span data-ttu-id="da7f3-202">2.0</span><span class="sxs-lookup"><span data-stu-id="da7f3-202">2.0</span></span>        |
| <span data-ttu-id="da7f3-203">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="da7f3-203">MVC ViewImports</span></span>                              | [<span data-ttu-id="da7f3-204">viewimports</span><span class="sxs-lookup"><span data-stu-id="da7f3-204">viewimports</span></span>](#namespace)       | <span data-ttu-id="da7f3-205">[C#]</span><span class="sxs-lookup"><span data-stu-id="da7f3-205">[C#]</span></span>         | <span data-ttu-id="da7f3-206">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="da7f3-206">Web/ASP.NET</span></span>                           | <span data-ttu-id="da7f3-207">2.0</span><span class="sxs-lookup"><span data-stu-id="da7f3-207">2.0</span></span>        |
| <span data-ttu-id="da7f3-208">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="da7f3-208">MVC ViewStart</span></span>                                | `viewstart`                     | <span data-ttu-id="da7f3-209">[C#]</span><span class="sxs-lookup"><span data-stu-id="da7f3-209">[C#]</span></span>         | <span data-ttu-id="da7f3-210">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="da7f3-210">Web/ASP.NET</span></span>                           | <span data-ttu-id="da7f3-211">2.0</span><span class="sxs-lookup"><span data-stu-id="da7f3-211">2.0</span></span>        |
| <span data-ttu-id="da7f3-212">Blazor Aplicación de servidor</span><span class="sxs-lookup"><span data-stu-id="da7f3-212">Blazor Server App</span></span>                            | [<span data-ttu-id="da7f3-213">blazorserver</span><span class="sxs-lookup"><span data-stu-id="da7f3-213">blazorserver</span></span>](#blazorserver)   | <span data-ttu-id="da7f3-214">[C#]</span><span class="sxs-lookup"><span data-stu-id="da7f3-214">[C#]</span></span>         | <span data-ttu-id="da7f3-215">Web/Blazor</span><span class="sxs-lookup"><span data-stu-id="da7f3-215">Web/Blazor</span></span>                            | <span data-ttu-id="da7f3-216">3.0</span><span class="sxs-lookup"><span data-stu-id="da7f3-216">3.0</span></span>        |
| <span data-ttu-id="da7f3-217">Aplicación de Blazor WebAssembly</span><span class="sxs-lookup"><span data-stu-id="da7f3-217">Blazor WebAssembly App</span></span>                       | [<span data-ttu-id="da7f3-218">blazorwasm</span><span class="sxs-lookup"><span data-stu-id="da7f3-218">blazorwasm</span></span>](#blazorwasm)       | <span data-ttu-id="da7f3-219">[C#]</span><span class="sxs-lookup"><span data-stu-id="da7f3-219">[C#]</span></span>         | <span data-ttu-id="da7f3-220">Web/Blazor/WebAssembly</span><span class="sxs-lookup"><span data-stu-id="da7f3-220">Web/Blazor/WebAssembly</span></span>                | <span data-ttu-id="da7f3-221">3.1.300</span><span class="sxs-lookup"><span data-stu-id="da7f3-221">3.1.300</span></span>    |
| <span data-ttu-id="da7f3-222">Vacío de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="da7f3-222">ASP.NET Core Empty</span></span>                           | [<span data-ttu-id="da7f3-223">web</span><span class="sxs-lookup"><span data-stu-id="da7f3-223">web</span></span>](#web)                     | <span data-ttu-id="da7f3-224">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="da7f3-224">[C#], F#</span></span>     | <span data-ttu-id="da7f3-225">Web/Vacío</span><span class="sxs-lookup"><span data-stu-id="da7f3-225">Web/Empty</span></span>                             | <span data-ttu-id="da7f3-226">1.0</span><span class="sxs-lookup"><span data-stu-id="da7f3-226">1.0</span></span>        |
| <span data-ttu-id="da7f3-227">Aplicación web de ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="da7f3-227">ASP.NET Core Web App (Model-View-Controller)</span></span> | [<span data-ttu-id="da7f3-228">mvc</span><span class="sxs-lookup"><span data-stu-id="da7f3-228">mvc</span></span>](#web-options)             | <span data-ttu-id="da7f3-229">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="da7f3-229">[C#], F#</span></span>     | <span data-ttu-id="da7f3-230">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="da7f3-230">Web/MVC</span></span>                               | <span data-ttu-id="da7f3-231">1.0</span><span class="sxs-lookup"><span data-stu-id="da7f3-231">1.0</span></span>        |
| <span data-ttu-id="da7f3-232">Aplicación web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="da7f3-232">ASP.NET Core Web App</span></span>                         | [<span data-ttu-id="da7f3-233">webapp, razor</span><span class="sxs-lookup"><span data-stu-id="da7f3-233">webapp, razor</span></span>](#web-options)   | <span data-ttu-id="da7f3-234">[C#]</span><span class="sxs-lookup"><span data-stu-id="da7f3-234">[C#]</span></span>         | <span data-ttu-id="da7f3-235">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="da7f3-235">Web/MVC/Razor Pages</span></span>                   | <span data-ttu-id="da7f3-236">2.2, 2.0</span><span class="sxs-lookup"><span data-stu-id="da7f3-236">2.2, 2.0</span></span>   |
| <span data-ttu-id="da7f3-237">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="da7f3-237">ASP.NET Core with Angular</span></span>                    | [<span data-ttu-id="da7f3-238">angular</span><span class="sxs-lookup"><span data-stu-id="da7f3-238">angular</span></span>](#spa)                 | <span data-ttu-id="da7f3-239">[C#]</span><span class="sxs-lookup"><span data-stu-id="da7f3-239">[C#]</span></span>         | <span data-ttu-id="da7f3-240">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="da7f3-240">Web/MVC/SPA</span></span>                           | <span data-ttu-id="da7f3-241">2.0</span><span class="sxs-lookup"><span data-stu-id="da7f3-241">2.0</span></span>        |
| <span data-ttu-id="da7f3-242">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="da7f3-242">ASP.NET Core with React.js</span></span>                   | [<span data-ttu-id="da7f3-243">react</span><span class="sxs-lookup"><span data-stu-id="da7f3-243">react</span></span>](#spa)                   | <span data-ttu-id="da7f3-244">[C#]</span><span class="sxs-lookup"><span data-stu-id="da7f3-244">[C#]</span></span>         | <span data-ttu-id="da7f3-245">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="da7f3-245">Web/MVC/SPA</span></span>                           | <span data-ttu-id="da7f3-246">2.0</span><span class="sxs-lookup"><span data-stu-id="da7f3-246">2.0</span></span>        |
| <span data-ttu-id="da7f3-247">ASP.NET Core con React.js y Redux</span><span class="sxs-lookup"><span data-stu-id="da7f3-247">ASP.NET Core with React.js and Redux</span></span>         | [<span data-ttu-id="da7f3-248">reactredux</span><span class="sxs-lookup"><span data-stu-id="da7f3-248">reactredux</span></span>](#reactredux)       | <span data-ttu-id="da7f3-249">[C#]</span><span class="sxs-lookup"><span data-stu-id="da7f3-249">[C#]</span></span>         | <span data-ttu-id="da7f3-250">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="da7f3-250">Web/MVC/SPA</span></span>                           | <span data-ttu-id="da7f3-251">2.0</span><span class="sxs-lookup"><span data-stu-id="da7f3-251">2.0</span></span>        |
| <span data-ttu-id="da7f3-252">Biblioteca de clases de Razor</span><span class="sxs-lookup"><span data-stu-id="da7f3-252">Razor Class Library</span></span>                          | [<span data-ttu-id="da7f3-253">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="da7f3-253">razorclasslib</span></span>](#razorclasslib) | <span data-ttu-id="da7f3-254">[C#]</span><span class="sxs-lookup"><span data-stu-id="da7f3-254">[C#]</span></span>         | <span data-ttu-id="da7f3-255">Web/Razor/Biblioteca/Biblioteca de clases de Razor</span><span class="sxs-lookup"><span data-stu-id="da7f3-255">Web/Razor/Library/Razor Class Library</span></span> | <span data-ttu-id="da7f3-256">2.1</span><span class="sxs-lookup"><span data-stu-id="da7f3-256">2.1</span></span>        |
| <span data-ttu-id="da7f3-257">API web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="da7f3-257">ASP.NET Core Web API</span></span>                         | [<span data-ttu-id="da7f3-258">webapi</span><span class="sxs-lookup"><span data-stu-id="da7f3-258">webapi</span></span>](#webapi)               | <span data-ttu-id="da7f3-259">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="da7f3-259">[C#], F#</span></span>     | <span data-ttu-id="da7f3-260">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="da7f3-260">Web/WebAPI</span></span>                            | <span data-ttu-id="da7f3-261">1.0</span><span class="sxs-lookup"><span data-stu-id="da7f3-261">1.0</span></span>        |
| <span data-ttu-id="da7f3-262">Servicio gRPC de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="da7f3-262">ASP.NET Core gRPC Service</span></span>                    | [<span data-ttu-id="da7f3-263">grpc</span><span class="sxs-lookup"><span data-stu-id="da7f3-263">grpc</span></span>](#web-others)             | <span data-ttu-id="da7f3-264">[C#]</span><span class="sxs-lookup"><span data-stu-id="da7f3-264">[C#]</span></span>         | <span data-ttu-id="da7f3-265">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="da7f3-265">Web/gRPC</span></span>                              | <span data-ttu-id="da7f3-266">3.0</span><span class="sxs-lookup"><span data-stu-id="da7f3-266">3.0</span></span>        |
| <span data-ttu-id="da7f3-267">Archivo dotnet gitignore</span><span class="sxs-lookup"><span data-stu-id="da7f3-267">dotnet gitignore file</span></span>                        | `gitignore`                     |              | <span data-ttu-id="da7f3-268">Configuración</span><span class="sxs-lookup"><span data-stu-id="da7f3-268">Config</span></span>                                | <span data-ttu-id="da7f3-269">3.0</span><span class="sxs-lookup"><span data-stu-id="da7f3-269">3.0</span></span>        |
| <span data-ttu-id="da7f3-270">archivo global.json</span><span class="sxs-lookup"><span data-stu-id="da7f3-270">global.json file</span></span>                             | [<span data-ttu-id="da7f3-271">globaljson</span><span class="sxs-lookup"><span data-stu-id="da7f3-271">globaljson</span></span>](#globaljson)       |              | <span data-ttu-id="da7f3-272">Configuración</span><span class="sxs-lookup"><span data-stu-id="da7f3-272">Config</span></span>                                | <span data-ttu-id="da7f3-273">2.0</span><span class="sxs-lookup"><span data-stu-id="da7f3-273">2.0</span></span>        |
| <span data-ttu-id="da7f3-274">Configuración de NuGet</span><span class="sxs-lookup"><span data-stu-id="da7f3-274">NuGet Config</span></span>                                 | `nugetconfig`                   |              | <span data-ttu-id="da7f3-275">Configuración</span><span class="sxs-lookup"><span data-stu-id="da7f3-275">Config</span></span>                                | <span data-ttu-id="da7f3-276">1.0</span><span class="sxs-lookup"><span data-stu-id="da7f3-276">1.0</span></span>        |
| <span data-ttu-id="da7f3-277">Archivo de manifiesto de la herramienta local dotnet</span><span class="sxs-lookup"><span data-stu-id="da7f3-277">Dotnet local tool manifest file</span></span>              | `tool-manifest`                 |              | <span data-ttu-id="da7f3-278">Configuración</span><span class="sxs-lookup"><span data-stu-id="da7f3-278">Config</span></span>                                | <span data-ttu-id="da7f3-279">3.0</span><span class="sxs-lookup"><span data-stu-id="da7f3-279">3.0</span></span>        |
| <span data-ttu-id="da7f3-280">Configuración web</span><span class="sxs-lookup"><span data-stu-id="da7f3-280">Web Config</span></span>                                   | `webconfig`                     |              | <span data-ttu-id="da7f3-281">Configuración</span><span class="sxs-lookup"><span data-stu-id="da7f3-281">Config</span></span>                                | <span data-ttu-id="da7f3-282">1.0</span><span class="sxs-lookup"><span data-stu-id="da7f3-282">1.0</span></span>        |
| <span data-ttu-id="da7f3-283">Archivo de solución</span><span class="sxs-lookup"><span data-stu-id="da7f3-283">Solution File</span></span>                                | `sln`                           |              | <span data-ttu-id="da7f3-284">Soluciones</span><span class="sxs-lookup"><span data-stu-id="da7f3-284">Solution</span></span>                              | <span data-ttu-id="da7f3-285">1.0</span><span class="sxs-lookup"><span data-stu-id="da7f3-285">1.0</span></span>        |
| <span data-ttu-id="da7f3-286">Archivo de búfer de protocolo</span><span class="sxs-lookup"><span data-stu-id="da7f3-286">Protocol Buffer File</span></span>                         | [<span data-ttu-id="da7f3-287">proto</span><span class="sxs-lookup"><span data-stu-id="da7f3-287">proto</span></span>](#namespace)             |              | <span data-ttu-id="da7f3-288">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="da7f3-288">Web/gRPC</span></span>                              | <span data-ttu-id="da7f3-289">3.0</span><span class="sxs-lookup"><span data-stu-id="da7f3-289">3.0</span></span>        |

## <a name="options"></a><span data-ttu-id="da7f3-290">Opciones</span><span class="sxs-lookup"><span data-stu-id="da7f3-290">Options</span></span>

- **`--dry-run`**

  <span data-ttu-id="da7f3-291">Muestra un resumen de lo que sucedería si se ejecutara el comando determinado y el resultado fuera la creación de una plantilla.</span><span class="sxs-lookup"><span data-stu-id="da7f3-291">Displays a summary of what would happen if the given command were run if it would result in a template creation.</span></span> <span data-ttu-id="da7f3-292">Disponible a partir del SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="da7f3-292">Available since .NET Core 2.2 SDK.</span></span>

- **`--force`**

  <span data-ttu-id="da7f3-293">Fuerza la generación de contenido incluso aunque se vayan a cambiar los archivos existentes.</span><span class="sxs-lookup"><span data-stu-id="da7f3-293">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="da7f3-294">Es necesario si la plantilla elegida invalidará los archivos existentes en el directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="da7f3-294">This is required when the template chosen would override existing files in the output directory.</span></span>

- **`-h|--help`**

  <span data-ttu-id="da7f3-295">Imprime la ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="da7f3-295">Prints out help for the command.</span></span> <span data-ttu-id="da7f3-296">Puede invocarse para el propio comando `dotnet new` o para cualquier plantilla.</span><span class="sxs-lookup"><span data-stu-id="da7f3-296">It can be invoked for the `dotnet new` command itself or for any template.</span></span> <span data-ttu-id="da7f3-297">Por ejemplo: `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-297">For example, `dotnet new mvc --help`.</span></span>

- **`-i|--install <PATH|NUGET_ID>`**

  <span data-ttu-id="da7f3-298">Instala un paquete de plantillas desde los parámetros `PATH` o `NUGET_ID` proporcionados.</span><span class="sxs-lookup"><span data-stu-id="da7f3-298">Installs a template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="da7f3-299">Si quiere instalar una versión preliminar de un paquete de plantilla, tendrá que especificar la versión en el formato de `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-299">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="da7f3-300">De forma predeterminada, `dotnet new` pasa \* para la versión, que representa la última versión estable del paquete.</span><span class="sxs-lookup"><span data-stu-id="da7f3-300">By default, `dotnet new` passes \* for the version, which represents the latest stable package version.</span></span> <span data-ttu-id="da7f3-301">Vea un ejemplo en la sección [Ejemplos](#examples).</span><span class="sxs-lookup"><span data-stu-id="da7f3-301">See an example in the [Examples](#examples) section.</span></span>
  
  <span data-ttu-id="da7f3-302">Si ya hay instalada una versión de la plantilla al ejecutar este comando, la plantilla se actualizará a la versión especificada o a la versión estable más reciente si no se ha especificado ninguna versión.</span><span class="sxs-lookup"><span data-stu-id="da7f3-302">If a version of the template was already installed when you run this command, the template will be updated to the specified version, or to the latest stable version if no version was specified.</span></span>

  <span data-ttu-id="da7f3-303">Para obtener información sobre cómo crear plantillas personalizadas, consulte [Plantillas personalizadas para dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="da7f3-303">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

- **`-l|--list`**

  <span data-ttu-id="da7f3-304">Muestra las plantillas que contienen el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="da7f3-304">Lists templates containing the specified name.</span></span> <span data-ttu-id="da7f3-305">Si no se especifica ningún nombre, enumera todas las plantillas.</span><span class="sxs-lookup"><span data-stu-id="da7f3-305">If no name is specified, lists all templates.</span></span>

- **`-lang|--language {C#|F#|VB}`**

  <span data-ttu-id="da7f3-306">El lenguaje de la plantilla que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="da7f3-306">The language of the template to create.</span></span> <span data-ttu-id="da7f3-307">El lenguaje aceptado cambia según la plantilla (vea los valores predeterminados en la sección [argumentos](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="da7f3-307">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="da7f3-308">No es válido para algunas plantillas.</span><span class="sxs-lookup"><span data-stu-id="da7f3-308">Not valid for some templates.</span></span>

  > [!NOTE]
  > <span data-ttu-id="da7f3-309">Algunos shells interpretan `#` como un carácter especial.</span><span class="sxs-lookup"><span data-stu-id="da7f3-309">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="da7f3-310">En esos casos, incluya el valor del parámetro de lenguaje entre comillas.</span><span class="sxs-lookup"><span data-stu-id="da7f3-310">In those cases, enclose the language parameter value in quotes.</span></span> <span data-ttu-id="da7f3-311">Por ejemplo: `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-311">For example, `dotnet new console -lang "F#"`.</span></span>

- **`-n|--name <OUTPUT_NAME>`**

  <span data-ttu-id="da7f3-312">El nombre de la salida creada.</span><span class="sxs-lookup"><span data-stu-id="da7f3-312">The name for the created output.</span></span> <span data-ttu-id="da7f3-313">Si no se especifica ningún nombre, se usa el nombre del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="da7f3-313">If no name is specified, the name of the current directory is used.</span></span>

- **`--nuget-source <SOURCE>`**

  <span data-ttu-id="da7f3-314">Especifica un origen de NuGet para usarlo durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="da7f3-314">Specifies a NuGet source to use during install.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="da7f3-315">La ubicación para colocar la salida generada.</span><span class="sxs-lookup"><span data-stu-id="da7f3-315">Location to place the generated output.</span></span> <span data-ttu-id="da7f3-316">El valor predeterminado es el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="da7f3-316">The default is the current directory.</span></span>

- **`--type <TYPE>`**

  <span data-ttu-id="da7f3-317">Filtra plantillas en función de los tipos disponibles.</span><span class="sxs-lookup"><span data-stu-id="da7f3-317">Filters templates based on available types.</span></span> <span data-ttu-id="da7f3-318">Los valores predefinidos son `project` e `item`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-318">Predefined values are `project` and `item`.</span></span>

- **`-u|--uninstall [PATH|NUGET_ID]`**

  <span data-ttu-id="da7f3-319">Desinstala un paquete de plantillas en los parámetros `PATH` o `NUGET_ID` proporcionados.</span><span class="sxs-lookup"><span data-stu-id="da7f3-319">Uninstalls a template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="da7f3-320">Si no se especifica el valor `<PATH|NUGET_ID>`, se muestran todos los paquetes de plantillas instalados actualmente y sus plantillas asociadas.</span><span class="sxs-lookup"><span data-stu-id="da7f3-320">When the `<PATH|NUGET_ID>` value isn't specified, all currently installed template packs and their associated templates are displayed.</span></span> <span data-ttu-id="da7f3-321">Al especificar `NUGET_ID`, no incluya el número de versión.</span><span class="sxs-lookup"><span data-stu-id="da7f3-321">When specifying `NUGET_ID`, don't include the version number.</span></span>

  <span data-ttu-id="da7f3-322">Si no especifica un parámetro en esta opción, el comando muestra las plantillas instaladas y detalles sobre ellas.</span><span class="sxs-lookup"><span data-stu-id="da7f3-322">If you don't specify a parameter to this option, the command lists the installed templates and details about them.</span></span>

  > [!NOTE]
  > <span data-ttu-id="da7f3-323">Para desinstalar una plantilla mediante `PATH`, debe usar el nombre completo de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="da7f3-323">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="da7f3-324">Por ejemplo, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* funcionará, pero *./GarciaSoftware.ConsoleTemplate.CSharp* desde la carpeta contenedora no lo hará.</span><span class="sxs-lookup"><span data-stu-id="da7f3-324">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
  > <span data-ttu-id="da7f3-325">No incluya ninguna barra diagonal para finalizar el directorio en la ruta de acceso a la plantilla.</span><span class="sxs-lookup"><span data-stu-id="da7f3-325">Don't include a final terminating directory slash on your template path.</span></span>

- **`--update-apply`**

  <span data-ttu-id="da7f3-326">Comprueba si hay actualizaciones disponibles de los paquetes de plantillas instalados actualmente y las instala.</span><span class="sxs-lookup"><span data-stu-id="da7f3-326">Checks if there are updates available for the template packs that are currently installed and installs them.</span></span> <span data-ttu-id="da7f3-327">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="da7f3-327">Available since .NET Core 3.0 SDK.</span></span>

- **`--update-check`**

  <span data-ttu-id="da7f3-328">Comprueba si hay actualizaciones disponibles de los paquetes de plantillas instalados actualmente.</span><span class="sxs-lookup"><span data-stu-id="da7f3-328">Checks if there are updates available for the template packs that are currently installed.</span></span> <span data-ttu-id="da7f3-329">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="da7f3-329">Available since .NET Core 3.0 SDK.</span></span>

## <a name="template-options"></a><span data-ttu-id="da7f3-330">Opciones de plantilla</span><span class="sxs-lookup"><span data-stu-id="da7f3-330">Template options</span></span>

<span data-ttu-id="da7f3-331">Cada plantilla de proyecto puede tener opciones adicionales disponibles.</span><span class="sxs-lookup"><span data-stu-id="da7f3-331">Each project template may have additional options available.</span></span> <span data-ttu-id="da7f3-332">Las plantillas principales tienen las siguientes opciones adicionales:</span><span class="sxs-lookup"><span data-stu-id="da7f3-332">The core templates have the following additional options:</span></span>

### <a name="console"></a><span data-ttu-id="da7f3-333">consola</span><span class="sxs-lookup"><span data-stu-id="da7f3-333">console</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="da7f3-334">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="da7f3-334">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="da7f3-335">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="da7f3-335">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="da7f3-336">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="da7f3-336">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="da7f3-337">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="da7f3-337">SDK version</span></span> | <span data-ttu-id="da7f3-338">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="da7f3-338">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="da7f3-339">5.0</span><span class="sxs-lookup"><span data-stu-id="da7f3-339">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="da7f3-340">3.1</span><span class="sxs-lookup"><span data-stu-id="da7f3-340">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="da7f3-341">3.0</span><span class="sxs-lookup"><span data-stu-id="da7f3-341">3.0</span></span>         | `netcoreapp3.0` |

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="da7f3-342">Establece la propiedad `LangVersion` en el archivo del proyecto creado.</span><span class="sxs-lookup"><span data-stu-id="da7f3-342">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="da7f3-343">Por ejemplo, use `--langVersion 7.3` para emplear C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="da7f3-343">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="da7f3-344">No es compatible con F#.</span><span class="sxs-lookup"><span data-stu-id="da7f3-344">Not supported for F#.</span></span> <span data-ttu-id="da7f3-345">Disponible a partir del SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="da7f3-345">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="da7f3-346">Para obtener una lista de las versiones predeterminadas de C#, vea [Valores predeterminados](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="da7f3-346">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="da7f3-347">Si se especifica, no se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="da7f3-347">If specified, doesn't execute an implicit restore during project creation.</span></span> <span data-ttu-id="da7f3-348">Disponible a partir del SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="da7f3-348">Available since .NET Core 2.2 SDK.</span></span>

<span data-ttu-id="da7f3-349">\*\*_</span><span class="sxs-lookup"><span data-stu-id="da7f3-349">\*\*_</span></span>

### <a name="classlib"></a><span data-ttu-id="da7f3-350">classlib</span><span class="sxs-lookup"><span data-stu-id="da7f3-350">classlib</span></span>

- <span data-ttu-id="da7f3-351">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="da7f3-351">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="da7f3-352">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="da7f3-352">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="da7f3-353">Valores: `net5.0` o `netcoreapp<version>` para crear una biblioteca de clases de .NET, o bien `netstandard<version>` para crear una de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="da7f3-353">Values: `net5.0` or `netcoreapp<version>` to create a .NET Class Library or `netstandard<version>` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="da7f3-354">El valor predeterminado para el SDK de .NET 5.0 es `net5.0`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-354">The default value for .NET 5.0 SDK is `net5.0`.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="da7f3-355">Establece la propiedad `LangVersion` en el archivo del proyecto creado.</span><span class="sxs-lookup"><span data-stu-id="da7f3-355">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="da7f3-356">Por ejemplo, use `--langVersion 7.3` para emplear C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="da7f3-356">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="da7f3-357">No es compatible con F#.</span><span class="sxs-lookup"><span data-stu-id="da7f3-357">Not supported for F#.</span></span> <span data-ttu-id="da7f3-358">Disponible a partir del SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="da7f3-358">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="da7f3-359">Para obtener una lista de las versiones predeterminadas de C#, vea [Valores predeterminados](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="da7f3-359">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="da7f3-360">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="da7f3-360">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="da7f3-361">\*\*_</span><span class="sxs-lookup"><span data-stu-id="da7f3-361">\*\*_</span></span>

### <a name="wpf-wpflib-wpfcustomcontrollib-wpfusercontrollib"></a><a name="wpf"></a> <span data-ttu-id="da7f3-362">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="da7f3-362">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span></span>

- <span data-ttu-id="da7f3-363">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="da7f3-363">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="da7f3-364">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="da7f3-364">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="da7f3-365">El valor predeterminado es `net5.0`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-365">The default value is `net5.0`.</span></span> <span data-ttu-id="da7f3-366">Disponible a partir del SDK de .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="da7f3-366">Available since .NET Core 3.1 SDK.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="da7f3-367">Establece la propiedad `LangVersion` en el archivo del proyecto creado.</span><span class="sxs-lookup"><span data-stu-id="da7f3-367">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="da7f3-368">Por ejemplo, use `--langVersion 7.3` para emplear C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="da7f3-368">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="da7f3-369">Para obtener una lista de las versiones predeterminadas de C#, vea [Valores predeterminados](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="da7f3-369">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="da7f3-370">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="da7f3-370">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="da7f3-371">\*\*_</span><span class="sxs-lookup"><span data-stu-id="da7f3-371">\*\*_</span></span>

### <a name="winforms-winformslib"></a><a name="winforms"></a> <span data-ttu-id="da7f3-372">winforms, winformslib</span><span class="sxs-lookup"><span data-stu-id="da7f3-372">winforms, winformslib</span></span>

- <span data-ttu-id="da7f3-373">_ *`--langVersion <VERSION_NUMBER>`*\*</span><span class="sxs-lookup"><span data-stu-id="da7f3-373">_ *`--langVersion <VERSION_NUMBER>`*\*</span></span>

  <span data-ttu-id="da7f3-374">Establece la propiedad `LangVersion` en el archivo del proyecto creado.</span><span class="sxs-lookup"><span data-stu-id="da7f3-374">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="da7f3-375">Por ejemplo, use `--langVersion 7.3` para emplear C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="da7f3-375">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="da7f3-376">Para obtener una lista de las versiones predeterminadas de C#, vea [Valores predeterminados](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="da7f3-376">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="da7f3-377">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="da7f3-377">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="da7f3-378">\*\*_</span><span class="sxs-lookup"><span data-stu-id="da7f3-378">\*\*_</span></span>

### <a name="worker-grpc"></a><a name="web-others"></a> <span data-ttu-id="da7f3-379">worker, grpc</span><span class="sxs-lookup"><span data-stu-id="da7f3-379">worker, grpc</span></span>

- <span data-ttu-id="da7f3-380">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="da7f3-380">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="da7f3-381">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="da7f3-381">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="da7f3-382">El valor predeterminado es `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-382">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="da7f3-383">Disponible a partir del SDK de .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="da7f3-383">Available since .NET Core 3.1 SDK.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="da7f3-384">Excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="da7f3-384">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="da7f3-385">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="da7f3-385">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="da7f3-386">\*\*_</span><span class="sxs-lookup"><span data-stu-id="da7f3-386">\*\*_</span></span>

### <a name="mstest-xunit"></a><a name="test"></a> <span data-ttu-id="da7f3-387">mstest, xunit</span><span class="sxs-lookup"><span data-stu-id="da7f3-387">mstest, xunit</span></span>

- <span data-ttu-id="da7f3-388">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="da7f3-388">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="da7f3-389">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="da7f3-389">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="da7f3-390">Opción disponible a partir del SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="da7f3-390">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="da7f3-391">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="da7f3-391">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="da7f3-392">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="da7f3-392">SDK version</span></span> | <span data-ttu-id="da7f3-393">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="da7f3-393">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="da7f3-394">5.0</span><span class="sxs-lookup"><span data-stu-id="da7f3-394">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="da7f3-395">3.1</span><span class="sxs-lookup"><span data-stu-id="da7f3-395">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="da7f3-396">3.0</span><span class="sxs-lookup"><span data-stu-id="da7f3-396">3.0</span></span>         | `netcoreapp3.0` |

- **`-p|--enable-pack`**

  <span data-ttu-id="da7f3-397">Habilita el empaquetado del proyecto mediante [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="da7f3-397">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="da7f3-398">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="da7f3-398">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="da7f3-399">\*\*_</span><span class="sxs-lookup"><span data-stu-id="da7f3-399">\*\*_</span></span>

### <a name="nunit"></a><span data-ttu-id="da7f3-400">nunit</span><span class="sxs-lookup"><span data-stu-id="da7f3-400">nunit</span></span>

- <span data-ttu-id="da7f3-401">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="da7f3-401">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="da7f3-402">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="da7f3-402">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="da7f3-403">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="da7f3-403">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="da7f3-404">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="da7f3-404">SDK version</span></span> | <span data-ttu-id="da7f3-405">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="da7f3-405">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="da7f3-406">5.0</span><span class="sxs-lookup"><span data-stu-id="da7f3-406">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="da7f3-407">3.1</span><span class="sxs-lookup"><span data-stu-id="da7f3-407">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="da7f3-408">3.0</span><span class="sxs-lookup"><span data-stu-id="da7f3-408">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="da7f3-409">2.2</span><span class="sxs-lookup"><span data-stu-id="da7f3-409">2.2</span></span>         | `netcoreapp2.2` |
  | <span data-ttu-id="da7f3-410">2.1</span><span class="sxs-lookup"><span data-stu-id="da7f3-410">2.1</span></span>         | `netcoreapp2.1` |

- **`-p|--enable-pack`**

  <span data-ttu-id="da7f3-411">Habilita el empaquetado del proyecto mediante [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="da7f3-411">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="da7f3-412">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="da7f3-412">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="da7f3-413">\*\*_</span><span class="sxs-lookup"><span data-stu-id="da7f3-413">\*\*_</span></span>

### <a name="page"></a><span data-ttu-id="da7f3-414">página</span><span class="sxs-lookup"><span data-stu-id="da7f3-414">page</span></span>

- <span data-ttu-id="da7f3-415">_ *`-na|--namespace <NAMESPACE_NAME>`*\*</span><span class="sxs-lookup"><span data-stu-id="da7f3-415">_ *`-na|--namespace <NAMESPACE_NAME>`*\*</span></span>

  <span data-ttu-id="da7f3-416">Espacio de nombres del código generado.</span><span class="sxs-lookup"><span data-stu-id="da7f3-416">Namespace for the generated code.</span></span> <span data-ttu-id="da7f3-417">El valor predeterminado es `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-417">The default value is `MyApp.Namespace`.</span></span>

- **`-np|--no-pagemodel`**

  <span data-ttu-id="da7f3-418">Crea la página sin PageModel.</span><span class="sxs-lookup"><span data-stu-id="da7f3-418">Creates the page without a PageModel.</span></span>

<span data-ttu-id="da7f3-419">\*\*_</span><span class="sxs-lookup"><span data-stu-id="da7f3-419">\*\*_</span></span>

### <a name="viewimports-proto"></a><a name="namespace"></a> <span data-ttu-id="da7f3-420">viewimports, proto</span><span class="sxs-lookup"><span data-stu-id="da7f3-420">viewimports, proto</span></span>

- <span data-ttu-id="da7f3-421">_ *`-na|--namespace <NAMESPACE_NAME>`*\*</span><span class="sxs-lookup"><span data-stu-id="da7f3-421">_ *`-na|--namespace <NAMESPACE_NAME>`*\*</span></span>

  <span data-ttu-id="da7f3-422">Espacio de nombres del código generado.</span><span class="sxs-lookup"><span data-stu-id="da7f3-422">Namespace for the generated code.</span></span> <span data-ttu-id="da7f3-423">El valor predeterminado es `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-423">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="da7f3-424">\*\*_</span><span class="sxs-lookup"><span data-stu-id="da7f3-424">\*\*_</span></span>

### <a name="blazorserver"></a><span data-ttu-id="da7f3-425">blazorserver</span><span class="sxs-lookup"><span data-stu-id="da7f3-425">blazorserver</span></span>

- <span data-ttu-id="da7f3-426">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="da7f3-426">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="da7f3-427">Tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="da7f3-427">The type of authentication to use.</span></span> <span data-ttu-id="da7f3-428">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="da7f3-428">The possible values are:</span></span>

  - <span data-ttu-id="da7f3-429">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="da7f3-429">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="da7f3-430">`Individual`: autenticación individual.</span><span class="sxs-lookup"><span data-stu-id="da7f3-430">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="da7f3-431">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="da7f3-431">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="da7f3-432">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="da7f3-432">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="da7f3-433">`MultiOrg`: autenticación organizativa para varios inquilinos.</span><span class="sxs-lookup"><span data-stu-id="da7f3-433">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="da7f3-434">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="da7f3-434">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="da7f3-435">Instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="da7f3-435">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="da7f3-436">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-436">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="da7f3-437">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-437">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="da7f3-438">Identificador de la directiva de registro e inicio de sesión de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="da7f3-438">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="da7f3-439">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-439">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="da7f3-440">Identificador de la directiva de restablecimiento de contraseñas de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="da7f3-440">The reset password policy ID for this project.</span></span> <span data-ttu-id="da7f3-441">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-441">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="da7f3-442">Identificador de la directiva de edición de perfiles de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="da7f3-442">The edit profile policy ID for this project.</span></span> <span data-ttu-id="da7f3-443">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-443">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="da7f3-444">Instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="da7f3-444">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="da7f3-445">Úsela con las autenticaciones `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-445">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="da7f3-446">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-446">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="da7f3-447">Identificador de cliente de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="da7f3-447">The Client ID for this project.</span></span> <span data-ttu-id="da7f3-448">Úsela con las autenticaciones `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-448">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="da7f3-449">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-449">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="da7f3-450">Dominio del inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="da7f3-450">The domain for the directory tenant.</span></span> <span data-ttu-id="da7f3-451">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-451">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="da7f3-452">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-452">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="da7f3-453">Identificador de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="da7f3-453">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="da7f3-454">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-454">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="da7f3-455">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-455">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="da7f3-456">Ruta de acceso de solicitud de la ruta de acceso de la base de la aplicación del URI de redirección.</span><span class="sxs-lookup"><span data-stu-id="da7f3-456">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="da7f3-457">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-457">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="da7f3-458">El valor predeterminado es `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-458">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="da7f3-459">Concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="da7f3-459">Allows this application read-access to the directory.</span></span> <span data-ttu-id="da7f3-460">Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-460">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="da7f3-461">Excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="da7f3-461">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="da7f3-462">Desactiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="da7f3-462">Turns off HTTPS.</span></span> <span data-ttu-id="da7f3-463">Esta opción solo se aplica si no se usan `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg` en `--auth`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-463">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="da7f3-464">Especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="da7f3-464">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="da7f3-465">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-465">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--no-restore`**

  <span data-ttu-id="da7f3-466">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="da7f3-466">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="da7f3-467">\*\*_</span><span class="sxs-lookup"><span data-stu-id="da7f3-467">\*\*_</span></span>

### <a name="blazorwasm"></a><span data-ttu-id="da7f3-468">blazorwasm</span><span class="sxs-lookup"><span data-stu-id="da7f3-468">blazorwasm</span></span>

- <span data-ttu-id="da7f3-469">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="da7f3-469">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="da7f3-470">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="da7f3-470">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="da7f3-471">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="da7f3-471">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="da7f3-472">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="da7f3-472">SDK version</span></span> | <span data-ttu-id="da7f3-473">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="da7f3-473">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="da7f3-474">5.0</span><span class="sxs-lookup"><span data-stu-id="da7f3-474">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="da7f3-475">3.1</span><span class="sxs-lookup"><span data-stu-id="da7f3-475">3.1</span></span>         | `netcoreapp3.1` |

- **`--no-restore`**

  <span data-ttu-id="da7f3-476">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="da7f3-476">Doesn't execute an implicit restore during project creation.</span></span>

- **`-ho|--hosted`**

  <span data-ttu-id="da7f3-477">Incluye un host de ASP.NET Core para la aplicación Blazor WebAssembly.</span><span class="sxs-lookup"><span data-stu-id="da7f3-477">Includes an ASP.NET Core host for the Blazor WebAssembly app.</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="da7f3-478">Tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="da7f3-478">The type of authentication to use.</span></span> <span data-ttu-id="da7f3-479">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="da7f3-479">The possible values are:</span></span>

  - <span data-ttu-id="da7f3-480">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="da7f3-480">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="da7f3-481">`Individual`: autenticación individual.</span><span class="sxs-lookup"><span data-stu-id="da7f3-481">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="da7f3-482">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="da7f3-482">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="da7f3-483">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="da7f3-483">`SingleOrg` - Organizational authentication for a single tenant.</span></span>

- **`--authority <AUTHORITY>`**

  <span data-ttu-id="da7f3-484">La autoridad del proveedor de OIDC.</span><span class="sxs-lookup"><span data-stu-id="da7f3-484">The authority of the OIDC provider.</span></span> <span data-ttu-id="da7f3-485">Úsela con la autenticación `Individual`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-485">Use with `Individual` authentication.</span></span> <span data-ttu-id="da7f3-486">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-486">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="da7f3-487">Instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="da7f3-487">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="da7f3-488">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-488">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="da7f3-489">El valor predeterminado es `https://aadB2CInstance.b2clogin.com/`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-489">The default value is `https://aadB2CInstance.b2clogin.com/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="da7f3-490">Identificador de la directiva de registro e inicio de sesión de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="da7f3-490">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="da7f3-491">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-491">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="da7f3-492">Instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="da7f3-492">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="da7f3-493">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-493">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="da7f3-494">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-494">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="da7f3-495">Identificador de cliente de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="da7f3-495">The Client ID for this project.</span></span> <span data-ttu-id="da7f3-496">Úselo con la autenticación `IndividualB2C`, `SingleOrg` o `Individual` en escenarios independientes.</span><span class="sxs-lookup"><span data-stu-id="da7f3-496">Use with `IndividualB2C`, `SingleOrg`, or `Individual` authentication in standalone scenarios.</span></span> <span data-ttu-id="da7f3-497">El valor predeterminado es `33333333-3333-3333-33333333333333333`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-497">The default value is `33333333-3333-3333-33333333333333333`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="da7f3-498">Dominio del inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="da7f3-498">The domain for the directory tenant.</span></span> <span data-ttu-id="da7f3-499">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-499">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="da7f3-500">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-500">The default value is `qualified.domain.name`.</span></span>

- **`--app-id-uri <URI>`**

  <span data-ttu-id="da7f3-501">El URI del id. de la aplicación de la API de servidor a la que quiere llamar.</span><span class="sxs-lookup"><span data-stu-id="da7f3-501">The App ID Uri for the server API you want to call.</span></span> <span data-ttu-id="da7f3-502">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-502">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="da7f3-503">El valor predeterminado es `api.id.uri`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-503">The default value is `api.id.uri`.</span></span>

- **`--api-client-id <ID>`**

  <span data-ttu-id="da7f3-504">El id. de cliente de la API que el servidor hospeda.</span><span class="sxs-lookup"><span data-stu-id="da7f3-504">The Client ID for the API that the server hosts.</span></span> <span data-ttu-id="da7f3-505">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-505">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="da7f3-506">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-506">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`-s|--default-scope <SCOPE>`**

  <span data-ttu-id="da7f3-507">El ámbito de la API que el cliente debe solicitar para aprovisionar un token de acceso.</span><span class="sxs-lookup"><span data-stu-id="da7f3-507">The API scope the client needs to request to provision an access token.</span></span> <span data-ttu-id="da7f3-508">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-508">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="da7f3-509">El valor predeterminado es `user_impersonation`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-509">The default value is `user_impersonation`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="da7f3-510">Identificador de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="da7f3-510">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="da7f3-511">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-511">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="da7f3-512">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-512">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="da7f3-513">Concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="da7f3-513">Allows this application read-access to the directory.</span></span> <span data-ttu-id="da7f3-514">Solo se aplica a la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-514">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="da7f3-515">Excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="da7f3-515">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-p|--pwa`**

  <span data-ttu-id="da7f3-516">Genera una aplicación web progresiva (PWA) que admite la instalación y el uso sin conexión.</span><span class="sxs-lookup"><span data-stu-id="da7f3-516">produces a Progressive Web Application (PWA) supporting installation and offline use.</span></span>

- **`--no-https`**

  <span data-ttu-id="da7f3-517">Desactiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="da7f3-517">Turns off HTTPS.</span></span> <span data-ttu-id="da7f3-518">Esta opción solo se aplica si no se usan `Individual`, `IndividualB2C` o `SingleOrg` en `--auth`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-518">This option only applies if `Individual`, `IndividualB2C`, or `SingleOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="da7f3-519">Especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="da7f3-519">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="da7f3-520">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-520">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--called-api-url <URL>`**

  <span data-ttu-id="da7f3-521">Dirección URL de la API que se va a llamar desde la aplicación web.</span><span class="sxs-lookup"><span data-stu-id="da7f3-521">URL of the API to call from the web app.</span></span> <span data-ttu-id="da7f3-522">Solo se aplica a la autenticación `SingleOrg` o `IndividualB2C` sin un host especificado de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="da7f3-522">Only applies to `SingleOrg` or `IndividualB2C` authentication without an ASP.NET Core host specified.</span></span> <span data-ttu-id="da7f3-523">El valor predeterminado es `https://graph.microsoft.com/v1.0/me`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-523">The default value is `https://graph.microsoft.com/v1.0/me`.</span></span>

- **`--calls-graph`**

  <span data-ttu-id="da7f3-524">Especifica si la aplicación web llama a Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="da7f3-524">Specifies if the web app calls Microsoft Graph.</span></span> <span data-ttu-id="da7f3-525">Solo se aplica a la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-525">Only applies to `SingleOrg` authentication.</span></span>

- **`--called-api-scopes <SCOPES>`**

  <span data-ttu-id="da7f3-526">Ámbitos para solicitar llamar a la API desde la aplicación web.</span><span class="sxs-lookup"><span data-stu-id="da7f3-526">Scopes to request to call the API from the web app.</span></span> <span data-ttu-id="da7f3-527">Solo se aplica a la autenticación `SingleOrg` o `IndividualB2C` sin un host especificado de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="da7f3-527">Only applies to `SingleOrg` or `IndividualB2C` authentication without an ASP.NET Core host specified.</span></span> <span data-ttu-id="da7f3-528">De manera predeterminada, es `user.read`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-528">The default is `user.read`.</span></span>

<span data-ttu-id="da7f3-529">\*\*_</span><span class="sxs-lookup"><span data-stu-id="da7f3-529">\*\*_</span></span>

### <a name="web"></a><span data-ttu-id="da7f3-530">web</span><span class="sxs-lookup"><span data-stu-id="da7f3-530">web</span></span>

- <span data-ttu-id="da7f3-531">_ *`--exclude-launch-settings`*\*</span><span class="sxs-lookup"><span data-stu-id="da7f3-531">_ *`--exclude-launch-settings`*\*</span></span>

  <span data-ttu-id="da7f3-532">Excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="da7f3-532">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="da7f3-533">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="da7f3-533">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="da7f3-534">Opción no disponible en el SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="da7f3-534">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="da7f3-535">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="da7f3-535">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="da7f3-536">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="da7f3-536">SDK version</span></span> | <span data-ttu-id="da7f3-537">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="da7f3-537">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="da7f3-538">5.0</span><span class="sxs-lookup"><span data-stu-id="da7f3-538">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="da7f3-539">3.1</span><span class="sxs-lookup"><span data-stu-id="da7f3-539">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="da7f3-540">3.0</span><span class="sxs-lookup"><span data-stu-id="da7f3-540">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="da7f3-541">2.1</span><span class="sxs-lookup"><span data-stu-id="da7f3-541">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="da7f3-542">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="da7f3-542">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="da7f3-543">Desactiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="da7f3-543">Turns off HTTPS.</span></span>

<span data-ttu-id="da7f3-544">\*\*_</span><span class="sxs-lookup"><span data-stu-id="da7f3-544">\*\*_</span></span>

### <a name="mvc-webapp"></a><a name="web-options"></a> <span data-ttu-id="da7f3-545">mvc, webapp</span><span class="sxs-lookup"><span data-stu-id="da7f3-545">mvc, webapp</span></span>

- <span data-ttu-id="da7f3-546">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="da7f3-546">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="da7f3-547">Tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="da7f3-547">The type of authentication to use.</span></span> <span data-ttu-id="da7f3-548">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="da7f3-548">The possible values are:</span></span>

  - <span data-ttu-id="da7f3-549">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="da7f3-549">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="da7f3-550">`Individual`: autenticación individual.</span><span class="sxs-lookup"><span data-stu-id="da7f3-550">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="da7f3-551">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="da7f3-551">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="da7f3-552">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="da7f3-552">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="da7f3-553">`MultiOrg`: autenticación organizativa para varios inquilinos.</span><span class="sxs-lookup"><span data-stu-id="da7f3-553">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="da7f3-554">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="da7f3-554">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="da7f3-555">Instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="da7f3-555">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="da7f3-556">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-556">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="da7f3-557">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-557">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="da7f3-558">Identificador de la directiva de registro e inicio de sesión de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="da7f3-558">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="da7f3-559">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-559">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="da7f3-560">Identificador de la directiva de restablecimiento de contraseñas de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="da7f3-560">The reset password policy ID for this project.</span></span> <span data-ttu-id="da7f3-561">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-561">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="da7f3-562">Identificador de la directiva de edición de perfiles de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="da7f3-562">The edit profile policy ID for this project.</span></span> <span data-ttu-id="da7f3-563">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-563">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="da7f3-564">Instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="da7f3-564">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="da7f3-565">Úsela con las autenticaciones `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-565">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="da7f3-566">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-566">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="da7f3-567">Identificador de cliente de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="da7f3-567">The Client ID for this project.</span></span> <span data-ttu-id="da7f3-568">Úsela con las autenticaciones `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-568">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="da7f3-569">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-569">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="da7f3-570">Dominio del inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="da7f3-570">The domain for the directory tenant.</span></span> <span data-ttu-id="da7f3-571">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-571">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="da7f3-572">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-572">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="da7f3-573">Identificador de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="da7f3-573">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="da7f3-574">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-574">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="da7f3-575">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-575">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="da7f3-576">Ruta de acceso de solicitud de la ruta de acceso de la base de la aplicación del URI de redirección.</span><span class="sxs-lookup"><span data-stu-id="da7f3-576">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="da7f3-577">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-577">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="da7f3-578">El valor predeterminado es `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-578">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="da7f3-579">Concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="da7f3-579">Allows this application read-access to the directory.</span></span> <span data-ttu-id="da7f3-580">Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-580">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="da7f3-581">Excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="da7f3-581">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="da7f3-582">Desactiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="da7f3-582">Turns off HTTPS.</span></span> <span data-ttu-id="da7f3-583">Esta opción solo se aplica si no se usan `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-583">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="da7f3-584">Especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="da7f3-584">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="da7f3-585">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-585">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="da7f3-586">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="da7f3-586">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="da7f3-587">Opción disponible a partir del SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="da7f3-587">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="da7f3-588">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="da7f3-588">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="da7f3-589">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="da7f3-589">SDK version</span></span> | <span data-ttu-id="da7f3-590">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="da7f3-590">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="da7f3-591">5.0</span><span class="sxs-lookup"><span data-stu-id="da7f3-591">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="da7f3-592">3.1</span><span class="sxs-lookup"><span data-stu-id="da7f3-592">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="da7f3-593">3.0</span><span class="sxs-lookup"><span data-stu-id="da7f3-593">3.0</span></span>         | `netcoreapp3.0` |

- **`--no-restore`**

  <span data-ttu-id="da7f3-594">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="da7f3-594">Doesn't execute an implicit restore during project creation.</span></span>

- **`--use-browserlink`**

  <span data-ttu-id="da7f3-595">Incluye BrowserLink en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="da7f3-595">Includes BrowserLink in the project.</span></span> <span data-ttu-id="da7f3-596">Opción no disponible en el SDK de .NET Core 2.2 y 3.1.</span><span class="sxs-lookup"><span data-stu-id="da7f3-596">Option not available in .NET Core 2.2 and 3.1 SDK.</span></span>

- **`-rrc|--razor-runtime-compilation`**

  <span data-ttu-id="da7f3-597">Determina si el proyecto está configurado para usar la [compilación en tiempo de ejecución de Razor](/aspnet/core/mvc/views/view-compilation#runtime-compilation) en las compilaciones de depuración.</span><span class="sxs-lookup"><span data-stu-id="da7f3-597">Determines if the project is configured to use [Razor runtime compilation](/aspnet/core/mvc/views/view-compilation#runtime-compilation) in Debug builds.</span></span> <span data-ttu-id="da7f3-598">Opción disponible a partir del SDK de .NET Core 3.1.201.</span><span class="sxs-lookup"><span data-stu-id="da7f3-598">Option available since .NET Core 3.1.201 SDK.</span></span>

<span data-ttu-id="da7f3-599">\*\*_</span><span class="sxs-lookup"><span data-stu-id="da7f3-599">\*\*_</span></span>

### <a name="angular-react"></a><a name="spa"></a> <span data-ttu-id="da7f3-600">angular, react</span><span class="sxs-lookup"><span data-stu-id="da7f3-600">angular, react</span></span>

- <span data-ttu-id="da7f3-601">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="da7f3-601">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="da7f3-602">Tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="da7f3-602">The type of authentication to use.</span></span> <span data-ttu-id="da7f3-603">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="da7f3-603">Available since .NET Core 3.0 SDK.</span></span>
  
  <span data-ttu-id="da7f3-604">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="da7f3-604">The possible values are:</span></span>

  - <span data-ttu-id="da7f3-605">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="da7f3-605">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="da7f3-606">`Individual`: autenticación individual.</span><span class="sxs-lookup"><span data-stu-id="da7f3-606">`Individual` - Individual authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="da7f3-607">Excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="da7f3-607">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="da7f3-608">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="da7f3-608">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="da7f3-609">Desactiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="da7f3-609">Turns off HTTPS.</span></span> <span data-ttu-id="da7f3-610">Esta opción solo se aplica si la autenticación es `None`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-610">This option only applies if authentication is `None`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="da7f3-611">Especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="da7f3-611">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="da7f3-612">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-612">Only applies to `Individual` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="da7f3-613">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="da7f3-613">Available since .NET Core 3.0 SDK.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="da7f3-614">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="da7f3-614">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="da7f3-615">Opción no disponible en el SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="da7f3-615">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="da7f3-616">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="da7f3-616">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="da7f3-617">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="da7f3-617">SDK version</span></span> | <span data-ttu-id="da7f3-618">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="da7f3-618">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="da7f3-619">5.0</span><span class="sxs-lookup"><span data-stu-id="da7f3-619">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="da7f3-620">3.1</span><span class="sxs-lookup"><span data-stu-id="da7f3-620">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="da7f3-621">3.0</span><span class="sxs-lookup"><span data-stu-id="da7f3-621">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="da7f3-622">2.1</span><span class="sxs-lookup"><span data-stu-id="da7f3-622">2.1</span></span>         | `netcoreapp2.0` |

<span data-ttu-id="da7f3-623">\*\*_</span><span class="sxs-lookup"><span data-stu-id="da7f3-623">\*\*_</span></span>

### <a name="reactredux"></a><span data-ttu-id="da7f3-624">reactredux</span><span class="sxs-lookup"><span data-stu-id="da7f3-624">reactredux</span></span>

- <span data-ttu-id="da7f3-625">_ *`--exclude-launch-settings`*\*</span><span class="sxs-lookup"><span data-stu-id="da7f3-625">_ *`--exclude-launch-settings`*\*</span></span>

  <span data-ttu-id="da7f3-626">Excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="da7f3-626">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="da7f3-627">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="da7f3-627">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="da7f3-628">Opción no disponible en el SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="da7f3-628">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="da7f3-629">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="da7f3-629">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="da7f3-630">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="da7f3-630">SDK version</span></span> | <span data-ttu-id="da7f3-631">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="da7f3-631">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="da7f3-632">5.0</span><span class="sxs-lookup"><span data-stu-id="da7f3-632">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="da7f3-633">3.1</span><span class="sxs-lookup"><span data-stu-id="da7f3-633">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="da7f3-634">3.0</span><span class="sxs-lookup"><span data-stu-id="da7f3-634">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="da7f3-635">2.1</span><span class="sxs-lookup"><span data-stu-id="da7f3-635">2.1</span></span>         | `netcoreapp2.0` |

- **`--no-restore`**

  <span data-ttu-id="da7f3-636">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="da7f3-636">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="da7f3-637">Desactiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="da7f3-637">Turns off HTTPS.</span></span>

<span data-ttu-id="da7f3-638">\*\*_</span><span class="sxs-lookup"><span data-stu-id="da7f3-638">\*\*_</span></span>

### <a name="razorclasslib"></a><span data-ttu-id="da7f3-639">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="da7f3-639">razorclasslib</span></span>

- <span data-ttu-id="da7f3-640">_ *`--no-restore`*\*</span><span class="sxs-lookup"><span data-stu-id="da7f3-640">_ *`--no-restore`*\*</span></span>

  <span data-ttu-id="da7f3-641">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="da7f3-641">Doesn't execute an implicit restore during project creation.</span></span>

- **`-s|--support-pages-and-views`**

  <span data-ttu-id="da7f3-642">Permite agregar vistas y páginas de Razor tradicionales además de los componentes a esta biblioteca.</span><span class="sxs-lookup"><span data-stu-id="da7f3-642">Supports adding traditional Razor pages and Views in addition to components to this library.</span></span> <span data-ttu-id="da7f3-643">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="da7f3-643">Available since .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="da7f3-644">\*\*_</span><span class="sxs-lookup"><span data-stu-id="da7f3-644">\*\*_</span></span>
  
### <a name="webapi"></a><span data-ttu-id="da7f3-645">webapi</span><span class="sxs-lookup"><span data-stu-id="da7f3-645">webapi</span></span>

- <span data-ttu-id="da7f3-646">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="da7f3-646">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="da7f3-647">Tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="da7f3-647">The type of authentication to use.</span></span> <span data-ttu-id="da7f3-648">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="da7f3-648">The possible values are:</span></span>

  - <span data-ttu-id="da7f3-649">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="da7f3-649">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="da7f3-650">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="da7f3-650">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="da7f3-651">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="da7f3-651">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="da7f3-652">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="da7f3-652">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="da7f3-653">Instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="da7f3-653">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="da7f3-654">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-654">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="da7f3-655">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-655">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="da7f3-656">Identificador de la directiva de registro e inicio de sesión de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="da7f3-656">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="da7f3-657">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-657">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="da7f3-658">Instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="da7f3-658">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="da7f3-659">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-659">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="da7f3-660">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-660">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="da7f3-661">Identificador de cliente de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="da7f3-661">The Client ID for this project.</span></span> <span data-ttu-id="da7f3-662">Úsela con las autenticaciones `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-662">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="da7f3-663">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-663">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="da7f3-664">Dominio del inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="da7f3-664">The domain for the directory tenant.</span></span> <span data-ttu-id="da7f3-665">Úsela con las autenticaciones `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-665">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="da7f3-666">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-666">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="da7f3-667">Identificador de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="da7f3-667">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="da7f3-668">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-668">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="da7f3-669">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-669">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="da7f3-670">Concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="da7f3-670">Allows this application read-access to the directory.</span></span> <span data-ttu-id="da7f3-671">Solo se aplica a la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-671">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="da7f3-672">Excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="da7f3-672">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="da7f3-673">Desactiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="da7f3-673">Turns off HTTPS.</span></span> <span data-ttu-id="da7f3-674">`app.UseHsts` y `app.UseHttpsRedirection` no se agregan a `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-674">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="da7f3-675">Esta opción solo se aplica si no se usan `IndividualB2C` o `SingleOrg` en la autenticación.</span><span class="sxs-lookup"><span data-stu-id="da7f3-675">This option only applies if `IndividualB2C` or `SingleOrg` aren't being used for authentication.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="da7f3-676">Especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="da7f3-676">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="da7f3-677">Solo se aplica a la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="da7f3-677">Only applies to `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="da7f3-678">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="da7f3-678">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="da7f3-679">Opción no disponible en el SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="da7f3-679">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="da7f3-680">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="da7f3-680">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="da7f3-681">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="da7f3-681">SDK version</span></span> | <span data-ttu-id="da7f3-682">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="da7f3-682">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="da7f3-683">5.0</span><span class="sxs-lookup"><span data-stu-id="da7f3-683">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="da7f3-684">3.1</span><span class="sxs-lookup"><span data-stu-id="da7f3-684">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="da7f3-685">3.0</span><span class="sxs-lookup"><span data-stu-id="da7f3-685">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="da7f3-686">2.1</span><span class="sxs-lookup"><span data-stu-id="da7f3-686">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="da7f3-687">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="da7f3-687">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="da7f3-688">\*\*_</span><span class="sxs-lookup"><span data-stu-id="da7f3-688">\*\*_</span></span>

### <a name="globaljson"></a><span data-ttu-id="da7f3-689">globaljson</span><span class="sxs-lookup"><span data-stu-id="da7f3-689">globaljson</span></span>

- <span data-ttu-id="da7f3-690">_ *`--sdk-version <VERSION_NUMBER>`*\*</span><span class="sxs-lookup"><span data-stu-id="da7f3-690">_ *`--sdk-version <VERSION_NUMBER>`*\*</span></span>

  <span data-ttu-id="da7f3-691">Especifica la versión del SDK de .NET que se va a usar en el archivo *global.json*.</span><span class="sxs-lookup"><span data-stu-id="da7f3-691">Specifies the version of the .NET SDK to use in the *global.json* file.</span></span>

***

## <a name="examples"></a><span data-ttu-id="da7f3-692">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="da7f3-692">Examples</span></span>

- <span data-ttu-id="da7f3-693">Creación de un proyecto de aplicación de consola de C# mediante la especificación del nombre de plantilla:</span><span class="sxs-lookup"><span data-stu-id="da7f3-693">Create a C# console application project by specifying the template name:</span></span>

  ```dotnetcli
  dotnet new "Console Application"
  ```

- <span data-ttu-id="da7f3-694">Creación de un proyecto de aplicación de consola con F# en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="da7f3-694">Create an F# console application project in the current directory:</span></span>

  ```dotnetcli
  dotnet new console -lang "F#"
  ```

- <span data-ttu-id="da7f3-695">Creación de un proyecto de biblioteca de clases de .NET Standard en el directorio especificado:</span><span class="sxs-lookup"><span data-stu-id="da7f3-695">Create a .NET Standard class library project in the specified directory:</span></span>

  ```dotnetcli
  dotnet new classlib -lang VB -o MyLibrary
  ```

- <span data-ttu-id="da7f3-696">Creación de un proyecto MVC de ASP.NET Core C# en el directorio actual sin autenticación:</span><span class="sxs-lookup"><span data-stu-id="da7f3-696">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

  ```dotnetcli
  dotnet new mvc -au None
  ```

- <span data-ttu-id="da7f3-697">Creación de un proyecto de xUnit:</span><span class="sxs-lookup"><span data-stu-id="da7f3-697">Create a new xUnit project:</span></span>

  ```dotnetcli
  dotnet new xunit
  ```

- <span data-ttu-id="da7f3-698">Enumeración de todas las plantillas disponibles en las plantillas de aplicación de página única (SPA):</span><span class="sxs-lookup"><span data-stu-id="da7f3-698">List all templates available for Single Page Application (SPA) templates:</span></span>

  ```dotnetcli
  dotnet new spa -l
  ```

- <span data-ttu-id="da7f3-699">Enumeración de todas las plantillas que coinciden con la subcadena *we*.</span><span class="sxs-lookup"><span data-stu-id="da7f3-699">List all templates matching the *we* substring.</span></span> <span data-ttu-id="da7f3-700">No se encuentra ninguna coincidencia exacta, por lo que se ejecuta la coincidencia de subcadena con las columnas de nombre corto y de nombre.</span><span class="sxs-lookup"><span data-stu-id="da7f3-700">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

  ```dotnetcli
  dotnet new we -l
  ```

- <span data-ttu-id="da7f3-701">Intento de invocar a la plantilla que coincide con *ng*.</span><span class="sxs-lookup"><span data-stu-id="da7f3-701">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="da7f3-702">Si no se puede determinar una única coincidencia, se enumeran las plantillas que son coincidencias parciales.</span><span class="sxs-lookup"><span data-stu-id="da7f3-702">If a single match can't be determined, list the templates that are partial matches.</span></span>

  ```dotnetcli
  dotnet new ng
  ```

- <span data-ttu-id="da7f3-703">Instalación de la versión 2.0 de las plantillas de SPA de ASP.NET Core:</span><span class="sxs-lookup"><span data-stu-id="da7f3-703">Install version 2.0 of the SPA templates for ASP.NET Core:</span></span>

  ```dotnetcli
  dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0
  ```

- <span data-ttu-id="da7f3-704">Enumeración de las plantillas instaladas y detalles sobre ellas, incluido cómo desinstalarlas:</span><span class="sxs-lookup"><span data-stu-id="da7f3-704">List the installed templates and details about them, including how to uninstall them:</span></span>

  ```dotnetcli
  dotnet new -u
  ```

- <span data-ttu-id="da7f3-705">Creación de un archivo *global.json* en el directorio actual al establecer la versión del SDK en 3.1.101:</span><span class="sxs-lookup"><span data-stu-id="da7f3-705">Create a *global.json* in the current directory setting the SDK version to 3.1.101:</span></span>

  ```dotnetcli
  dotnet new globaljson --sdk-version 3.1.101
  ```

## <a name="see-also"></a><span data-ttu-id="da7f3-706">Vea también</span><span class="sxs-lookup"><span data-stu-id="da7f3-706">See also</span></span>

- [<span data-ttu-id="da7f3-707">Plantillas personalizadas para dotnet new</span><span class="sxs-lookup"><span data-stu-id="da7f3-707">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="da7f3-708">Creación de una plantilla personalizada para dotnet new</span><span class="sxs-lookup"><span data-stu-id="da7f3-708">Create a custom template for dotnet new</span></span>](../tutorials/cli-templates-create-item-template.md)
- [<span data-ttu-id="da7f3-709">Repositorio de GitHub dotnet/dotnet-template-samples</span><span class="sxs-lookup"><span data-stu-id="da7f3-709">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- <span data-ttu-id="da7f3-710">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new) (Plantillas disponibles para dotnet new)</span><span class="sxs-lookup"><span data-stu-id="da7f3-710">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)</span></span>
