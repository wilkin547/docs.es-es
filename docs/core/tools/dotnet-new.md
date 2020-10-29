---
title: Comando dotnet new
description: El comando dotnet new crea proyectos de .NET Core basados en la plantilla especificada.
no-loc:
- ':::no-loc(Blazor):::'
- ':::no-loc(WebAssembly):::'
ms.date: 09/01/2020
ms.openlocfilehash: 4a4c8e2806fee663b5f6aa255a6f24250a072a85
ms.sourcegitcommit: 532b03d5bbab764d63356193b04cd2281bc01239
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/26/2020
ms.locfileid: "92526610"
---
# <a name="dotnet-new"></a><span data-ttu-id="81f4b-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="81f4b-103">dotnet new</span></span>

<span data-ttu-id="81f4b-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.0 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="81f4b-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="81f4b-105">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="81f4b-105">Name</span></span>

<span data-ttu-id="81f4b-106">`dotnet new`: crea un nuevo proyecto, archivo de configuración o solución según la plantilla especificada.</span><span class="sxs-lookup"><span data-stu-id="81f4b-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="81f4b-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="81f4b-107">Synopsis</span></span>

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install {PATH|NUGET_ID}]
    [-lang|--language {"C#"|"F#"|VB}] [-n|--name <OUTPUT_NAME>]
    [--nuget-source <SOURCE>] [-o|--output <OUTPUT_DIRECTORY>]
    [-u|--uninstall] [--update-apply] [--update-check] [Template options]

dotnet new <TEMPLATE> [-l|--list] [--type <TYPE>]

dotnet new -h|--help
```

## <a name="description"></a><span data-ttu-id="81f4b-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="81f4b-108">Description</span></span>

<span data-ttu-id="81f4b-109">El comando `dotnet new` crea un proyecto de .NET Core u otros artefactos basados en una plantilla.</span><span class="sxs-lookup"><span data-stu-id="81f4b-109">The `dotnet new` command creates a .NET Core project or other artifacts based on a template.</span></span>

<span data-ttu-id="81f4b-110">El comando llama al [motor de plantillas](https://github.com/dotnet/templating) para crear los artefactos en el disco basándose en las opciones y la plantilla especificadas.</span><span class="sxs-lookup"><span data-stu-id="81f4b-110">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="81f4b-111">Restauración implícita</span><span class="sxs-lookup"><span data-stu-id="81f4b-111">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="81f4b-112">Argumentos</span><span class="sxs-lookup"><span data-stu-id="81f4b-112">Arguments</span></span>

- **`TEMPLATE`**

  <span data-ttu-id="81f4b-113">La plantilla de la que se va a crear una instancia cuando se invoca el comando.</span><span class="sxs-lookup"><span data-stu-id="81f4b-113">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="81f4b-114">Cada plantilla puede tener opciones específicas que puede pasar.</span><span class="sxs-lookup"><span data-stu-id="81f4b-114">Each template might have specific options you can pass.</span></span> <span data-ttu-id="81f4b-115">Para obtener más información, vea [Opciones de plantilla](#template-options).</span><span class="sxs-lookup"><span data-stu-id="81f4b-115">For more information, see [Template options](#template-options).</span></span>

  <span data-ttu-id="81f4b-116">Puede ejecutar `dotnet new --list` o `dotnet new -l` para ver una lista de todas las plantillas instaladas.</span><span class="sxs-lookup"><span data-stu-id="81f4b-116">You can run `dotnet new --list` or `dotnet new -l` to see a list of all installed templates.</span></span> <span data-ttu-id="81f4b-117">Si el valor `TEMPLATE` no es una coincidencia exacta con el texto de la columna **Plantillas** o **Nombre corto** de la tabla devuelta, se realiza una coincidencia de subcadena con esas dos columnas.</span><span class="sxs-lookup"><span data-stu-id="81f4b-117">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column from the returned table, a substring match is performed on those two columns.</span></span>

  <span data-ttu-id="81f4b-118">A partir del SDK de .NET Core 3.0, la CLI busca plantillas en NuGet.org al invocar el comando `dotnet new` en las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="81f4b-118">Starting with .NET Core 3.0 SDK, the CLI searches for templates in NuGet.org when you invoke the `dotnet new` command in the following conditions:</span></span>

  - <span data-ttu-id="81f4b-119">Si la CLI no encuentra ninguna coincidencia de plantilla al invocar `dotnet new`, ni siquiera parcial.</span><span class="sxs-lookup"><span data-stu-id="81f4b-119">If the CLI can't find a template match when invoking `dotnet new`, not even partial.</span></span>
  - <span data-ttu-id="81f4b-120">Si hay disponible una versión más reciente de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="81f4b-120">If there's a newer version of the template available.</span></span> <span data-ttu-id="81f4b-121">En este caso, se crea el proyecto o el artefacto, pero la CLI le advierte de que hay una versión actualizada de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="81f4b-121">In this case, the project or artifact is created but the CLI warns you about an updated version of the template.</span></span>

  <span data-ttu-id="81f4b-122">En la tabla siguiente se muestran las plantillas que vienen preinstaladas en el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="81f4b-122">The following table shows the templates that come pre-installed with the .NET Core SDK.</span></span> <span data-ttu-id="81f4b-123">El lenguaje predeterminado de la plantilla se muestra entre corchetes.</span><span class="sxs-lookup"><span data-stu-id="81f4b-123">The default language for the template is shown inside the brackets.</span></span> <span data-ttu-id="81f4b-124">Haga clic en el vínculo del nombre corto para ver las opciones específicas de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="81f4b-124">Click on the short name link to see the specific template options.</span></span>

| <span data-ttu-id="81f4b-125">Plantillas</span><span class="sxs-lookup"><span data-stu-id="81f4b-125">Templates</span></span>                                    | <span data-ttu-id="81f4b-126">Nombre corto</span><span class="sxs-lookup"><span data-stu-id="81f4b-126">Short name</span></span>                      | <span data-ttu-id="81f4b-127">Lenguaje</span><span class="sxs-lookup"><span data-stu-id="81f4b-127">Language</span></span>     | <span data-ttu-id="81f4b-128">Etiquetas</span><span class="sxs-lookup"><span data-stu-id="81f4b-128">Tags</span></span>                                  | <span data-ttu-id="81f4b-129">Inclusión</span><span class="sxs-lookup"><span data-stu-id="81f4b-129">Introduced</span></span> |
|----------------------------------------------|---------------------------------|--------------|---------------------------------------|------------|
| <span data-ttu-id="81f4b-130">Aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="81f4b-130">Console Application</span></span>                          | [<span data-ttu-id="81f4b-131">console</span><span class="sxs-lookup"><span data-stu-id="81f4b-131">console</span></span>](#console)             | <span data-ttu-id="81f4b-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="81f4b-132">[C#], F#, VB</span></span> | <span data-ttu-id="81f4b-133">Común/Consola</span><span class="sxs-lookup"><span data-stu-id="81f4b-133">Common/Console</span></span>                        | <span data-ttu-id="81f4b-134">1.0</span><span class="sxs-lookup"><span data-stu-id="81f4b-134">1.0</span></span>        |
| <span data-ttu-id="81f4b-135">Biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="81f4b-135">Class library</span></span>                                | [<span data-ttu-id="81f4b-136">classlib</span><span class="sxs-lookup"><span data-stu-id="81f4b-136">classlib</span></span>](#classlib)           | <span data-ttu-id="81f4b-137">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="81f4b-137">[C#], F#, VB</span></span> | <span data-ttu-id="81f4b-138">Común/Biblioteca</span><span class="sxs-lookup"><span data-stu-id="81f4b-138">Common/Library</span></span>                        | <span data-ttu-id="81f4b-139">1.0</span><span class="sxs-lookup"><span data-stu-id="81f4b-139">1.0</span></span>        |
| <span data-ttu-id="81f4b-140">Aplicación WPF</span><span class="sxs-lookup"><span data-stu-id="81f4b-140">WPF Application</span></span>                              | [<span data-ttu-id="81f4b-141">wpf</span><span class="sxs-lookup"><span data-stu-id="81f4b-141">wpf</span></span>](#wpf)                     | <span data-ttu-id="81f4b-142">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="81f4b-142">[C#], VB</span></span>     | <span data-ttu-id="81f4b-143">Común/WPF</span><span class="sxs-lookup"><span data-stu-id="81f4b-143">Common/WPF</span></span>                            | <span data-ttu-id="81f4b-144">3.0 (5.0 para VB)</span><span class="sxs-lookup"><span data-stu-id="81f4b-144">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="81f4b-145">Biblioteca de clases de WPF</span><span class="sxs-lookup"><span data-stu-id="81f4b-145">WPF Class library</span></span>                            | [<span data-ttu-id="81f4b-146">wpflib</span><span class="sxs-lookup"><span data-stu-id="81f4b-146">wpflib</span></span>](#wpf)                  | <span data-ttu-id="81f4b-147">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="81f4b-147">[C#], VB</span></span>     | <span data-ttu-id="81f4b-148">Común/WPF</span><span class="sxs-lookup"><span data-stu-id="81f4b-148">Common/WPF</span></span>                            | <span data-ttu-id="81f4b-149">3.0 (5.0 para VB)</span><span class="sxs-lookup"><span data-stu-id="81f4b-149">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="81f4b-150">Biblioteca de controles personalizados WPF</span><span class="sxs-lookup"><span data-stu-id="81f4b-150">WPF Custom Control Library</span></span>                   | [<span data-ttu-id="81f4b-151">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="81f4b-151">wpfcustomcontrollib</span></span>](#wpf)     | <span data-ttu-id="81f4b-152">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="81f4b-152">[C#], VB</span></span>     | <span data-ttu-id="81f4b-153">Común/WPF</span><span class="sxs-lookup"><span data-stu-id="81f4b-153">Common/WPF</span></span>                            | <span data-ttu-id="81f4b-154">3.0 (5.0 para VB)</span><span class="sxs-lookup"><span data-stu-id="81f4b-154">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="81f4b-155">Biblioteca de controles de usuario de WPF</span><span class="sxs-lookup"><span data-stu-id="81f4b-155">WPF User Control Library</span></span>                     | [<span data-ttu-id="81f4b-156">wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="81f4b-156">wpfusercontrollib</span></span>](#wpf)       | <span data-ttu-id="81f4b-157">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="81f4b-157">[C#], VB</span></span>     | <span data-ttu-id="81f4b-158">Común/WPF</span><span class="sxs-lookup"><span data-stu-id="81f4b-158">Common/WPF</span></span>                            | <span data-ttu-id="81f4b-159">3.0 (5.0 para VB)</span><span class="sxs-lookup"><span data-stu-id="81f4b-159">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="81f4b-160">Aplicación de Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="81f4b-160">Windows Forms (WinForms) Application</span></span>         | [<span data-ttu-id="81f4b-161">winforms</span><span class="sxs-lookup"><span data-stu-id="81f4b-161">winforms</span></span>](#winforms)           | <span data-ttu-id="81f4b-162">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="81f4b-162">[C#], VB</span></span>     | <span data-ttu-id="81f4b-163">Común/WinForms</span><span class="sxs-lookup"><span data-stu-id="81f4b-163">Common/WinForms</span></span>                       | <span data-ttu-id="81f4b-164">3.0 (5.0 para VB)</span><span class="sxs-lookup"><span data-stu-id="81f4b-164">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="81f4b-165">Biblioteca de clases de Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="81f4b-165">Windows Forms (WinForms) Class library</span></span>       | [<span data-ttu-id="81f4b-166">winformslib</span><span class="sxs-lookup"><span data-stu-id="81f4b-166">winformslib</span></span>](#winforms)        | <span data-ttu-id="81f4b-167">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="81f4b-167">[C#], VB</span></span>     | <span data-ttu-id="81f4b-168">Común/WinForms</span><span class="sxs-lookup"><span data-stu-id="81f4b-168">Common/WinForms</span></span>                       | <span data-ttu-id="81f4b-169">3.0 (5.0 para VB)</span><span class="sxs-lookup"><span data-stu-id="81f4b-169">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="81f4b-170">Servicio Worker</span><span class="sxs-lookup"><span data-stu-id="81f4b-170">Worker Service</span></span>                               | [<span data-ttu-id="81f4b-171">worker</span><span class="sxs-lookup"><span data-stu-id="81f4b-171">worker</span></span>](#web-others)           | <span data-ttu-id="81f4b-172">[C#]</span><span class="sxs-lookup"><span data-stu-id="81f4b-172">[C#]</span></span>         | <span data-ttu-id="81f4b-173">Común/Worker/Web</span><span class="sxs-lookup"><span data-stu-id="81f4b-173">Common/Worker/Web</span></span>                     | <span data-ttu-id="81f4b-174">3.0</span><span class="sxs-lookup"><span data-stu-id="81f4b-174">3.0</span></span>        |
| <span data-ttu-id="81f4b-175">Proyecto de prueba unitaria</span><span class="sxs-lookup"><span data-stu-id="81f4b-175">Unit Test Project</span></span>                            | [<span data-ttu-id="81f4b-176">mstest</span><span class="sxs-lookup"><span data-stu-id="81f4b-176">mstest</span></span>](#test)                 | <span data-ttu-id="81f4b-177">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="81f4b-177">[C#], F#, VB</span></span> | <span data-ttu-id="81f4b-178">Prueba/MSTest</span><span class="sxs-lookup"><span data-stu-id="81f4b-178">Test/MSTest</span></span>                           | <span data-ttu-id="81f4b-179">1.0</span><span class="sxs-lookup"><span data-stu-id="81f4b-179">1.0</span></span>        |
| <span data-ttu-id="81f4b-180">Proyecto de prueba de NUnit 3</span><span class="sxs-lookup"><span data-stu-id="81f4b-180">NUnit 3 Test Project</span></span>                         | [<span data-ttu-id="81f4b-181">nunit</span><span class="sxs-lookup"><span data-stu-id="81f4b-181">nunit</span></span>](#nunit)                 | <span data-ttu-id="81f4b-182">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="81f4b-182">[C#], F#, VB</span></span> | <span data-ttu-id="81f4b-183">Prueba/NUnit</span><span class="sxs-lookup"><span data-stu-id="81f4b-183">Test/NUnit</span></span>                            | <span data-ttu-id="81f4b-184">2.1.400</span><span class="sxs-lookup"><span data-stu-id="81f4b-184">2.1.400</span></span>    |
| <span data-ttu-id="81f4b-185">Elemento de prueba de NUnit 3</span><span class="sxs-lookup"><span data-stu-id="81f4b-185">NUnit 3 Test Item</span></span>                            | `nunit-test`                    | <span data-ttu-id="81f4b-186">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="81f4b-186">[C#], F#, VB</span></span> | <span data-ttu-id="81f4b-187">Prueba/NUnit</span><span class="sxs-lookup"><span data-stu-id="81f4b-187">Test/NUnit</span></span>                            | <span data-ttu-id="81f4b-188">2.2</span><span class="sxs-lookup"><span data-stu-id="81f4b-188">2.2</span></span>        |
| <span data-ttu-id="81f4b-189">Proyecto de prueba de xUnit</span><span class="sxs-lookup"><span data-stu-id="81f4b-189">xUnit Test Project</span></span>                           | [<span data-ttu-id="81f4b-190">xunit</span><span class="sxs-lookup"><span data-stu-id="81f4b-190">xunit</span></span>](#test)                  | <span data-ttu-id="81f4b-191">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="81f4b-191">[C#], F#, VB</span></span> | <span data-ttu-id="81f4b-192">Prueba/xUnit</span><span class="sxs-lookup"><span data-stu-id="81f4b-192">Test/xUnit</span></span>                            | <span data-ttu-id="81f4b-193">1.0</span><span class="sxs-lookup"><span data-stu-id="81f4b-193">1.0</span></span>        |
| <span data-ttu-id="81f4b-194">Componente Razor</span><span class="sxs-lookup"><span data-stu-id="81f4b-194">Razor Component</span></span>                              | `razorcomponent`                | <span data-ttu-id="81f4b-195">[C#]</span><span class="sxs-lookup"><span data-stu-id="81f4b-195">[C#]</span></span>         | <span data-ttu-id="81f4b-196">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="81f4b-196">Web/ASP.NET</span></span>                           | <span data-ttu-id="81f4b-197">3.0</span><span class="sxs-lookup"><span data-stu-id="81f4b-197">3.0</span></span>        |
| <span data-ttu-id="81f4b-198">Página de Razor</span><span class="sxs-lookup"><span data-stu-id="81f4b-198">Razor Page</span></span>                                   | [<span data-ttu-id="81f4b-199">page</span><span class="sxs-lookup"><span data-stu-id="81f4b-199">page</span></span>](#page)                   | <span data-ttu-id="81f4b-200">[C#]</span><span class="sxs-lookup"><span data-stu-id="81f4b-200">[C#]</span></span>         | <span data-ttu-id="81f4b-201">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="81f4b-201">Web/ASP.NET</span></span>                           | <span data-ttu-id="81f4b-202">2.0</span><span class="sxs-lookup"><span data-stu-id="81f4b-202">2.0</span></span>        |
| <span data-ttu-id="81f4b-203">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="81f4b-203">MVC ViewImports</span></span>                              | [<span data-ttu-id="81f4b-204">viewimports</span><span class="sxs-lookup"><span data-stu-id="81f4b-204">viewimports</span></span>](#namespace)       | <span data-ttu-id="81f4b-205">[C#]</span><span class="sxs-lookup"><span data-stu-id="81f4b-205">[C#]</span></span>         | <span data-ttu-id="81f4b-206">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="81f4b-206">Web/ASP.NET</span></span>                           | <span data-ttu-id="81f4b-207">2.0</span><span class="sxs-lookup"><span data-stu-id="81f4b-207">2.0</span></span>        |
| <span data-ttu-id="81f4b-208">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="81f4b-208">MVC ViewStart</span></span>                                | `viewstart`                     | <span data-ttu-id="81f4b-209">[C#]</span><span class="sxs-lookup"><span data-stu-id="81f4b-209">[C#]</span></span>         | <span data-ttu-id="81f4b-210">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="81f4b-210">Web/ASP.NET</span></span>                           | <span data-ttu-id="81f4b-211">2.0</span><span class="sxs-lookup"><span data-stu-id="81f4b-211">2.0</span></span>        |
| <span data-ttu-id="81f4b-212">:::no-loc(Blazor)::: Aplicación de servidor</span><span class="sxs-lookup"><span data-stu-id="81f4b-212">:::no-loc(Blazor)::: Server App</span></span>                            | [<span data-ttu-id="81f4b-213">blazorserver</span><span class="sxs-lookup"><span data-stu-id="81f4b-213">blazorserver</span></span>](#blazorserver)   | <span data-ttu-id="81f4b-214">[C#]</span><span class="sxs-lookup"><span data-stu-id="81f4b-214">[C#]</span></span>         | <span data-ttu-id="81f4b-215">Web/:::no-loc(Blazor):::</span><span class="sxs-lookup"><span data-stu-id="81f4b-215">Web/:::no-loc(Blazor):::</span></span>                            | <span data-ttu-id="81f4b-216">3.0</span><span class="sxs-lookup"><span data-stu-id="81f4b-216">3.0</span></span>        |
| <span data-ttu-id="81f4b-217">Aplicación de :::no-loc(Blazor)::: :::no-loc(WebAssembly):::</span><span class="sxs-lookup"><span data-stu-id="81f4b-217">:::no-loc(Blazor)::: :::no-loc(WebAssembly)::: App</span></span>                       | `blazorwasm`                    | <span data-ttu-id="81f4b-218">[C#]</span><span class="sxs-lookup"><span data-stu-id="81f4b-218">[C#]</span></span>         | <span data-ttu-id="81f4b-219">Web/:::no-loc(Blazor):::/:::no-loc(WebAssembly):::</span><span class="sxs-lookup"><span data-stu-id="81f4b-219">Web/:::no-loc(Blazor):::/:::no-loc(WebAssembly):::</span></span>                | <span data-ttu-id="81f4b-220">3.1.300</span><span class="sxs-lookup"><span data-stu-id="81f4b-220">3.1.300</span></span>    |
| <span data-ttu-id="81f4b-221">Vacío de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="81f4b-221">ASP.NET Core Empty</span></span>                           | [<span data-ttu-id="81f4b-222">web</span><span class="sxs-lookup"><span data-stu-id="81f4b-222">web</span></span>](#web)                     | <span data-ttu-id="81f4b-223">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="81f4b-223">[C#], F#</span></span>     | <span data-ttu-id="81f4b-224">Web/Vacío</span><span class="sxs-lookup"><span data-stu-id="81f4b-224">Web/Empty</span></span>                             | <span data-ttu-id="81f4b-225">1.0</span><span class="sxs-lookup"><span data-stu-id="81f4b-225">1.0</span></span>        |
| <span data-ttu-id="81f4b-226">Aplicación web de ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="81f4b-226">ASP.NET Core Web App (Model-View-Controller)</span></span> | [<span data-ttu-id="81f4b-227">mvc</span><span class="sxs-lookup"><span data-stu-id="81f4b-227">mvc</span></span>](#web-options)             | <span data-ttu-id="81f4b-228">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="81f4b-228">[C#], F#</span></span>     | <span data-ttu-id="81f4b-229">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="81f4b-229">Web/MVC</span></span>                               | <span data-ttu-id="81f4b-230">1.0</span><span class="sxs-lookup"><span data-stu-id="81f4b-230">1.0</span></span>        |
| <span data-ttu-id="81f4b-231">Aplicación web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="81f4b-231">ASP.NET Core Web App</span></span>                         | [<span data-ttu-id="81f4b-232">webapp, razor</span><span class="sxs-lookup"><span data-stu-id="81f4b-232">webapp, razor</span></span>](#web-options)   | <span data-ttu-id="81f4b-233">[C#]</span><span class="sxs-lookup"><span data-stu-id="81f4b-233">[C#]</span></span>         | <span data-ttu-id="81f4b-234">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="81f4b-234">Web/MVC/Razor Pages</span></span>                   | <span data-ttu-id="81f4b-235">2.2, 2.0</span><span class="sxs-lookup"><span data-stu-id="81f4b-235">2.2, 2.0</span></span>   |
| <span data-ttu-id="81f4b-236">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="81f4b-236">ASP.NET Core with Angular</span></span>                    | [<span data-ttu-id="81f4b-237">angular</span><span class="sxs-lookup"><span data-stu-id="81f4b-237">angular</span></span>](#spa)                 | <span data-ttu-id="81f4b-238">[C#]</span><span class="sxs-lookup"><span data-stu-id="81f4b-238">[C#]</span></span>         | <span data-ttu-id="81f4b-239">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="81f4b-239">Web/MVC/SPA</span></span>                           | <span data-ttu-id="81f4b-240">2.0</span><span class="sxs-lookup"><span data-stu-id="81f4b-240">2.0</span></span>        |
| <span data-ttu-id="81f4b-241">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="81f4b-241">ASP.NET Core with React.js</span></span>                   | [<span data-ttu-id="81f4b-242">react</span><span class="sxs-lookup"><span data-stu-id="81f4b-242">react</span></span>](#spa)                   | <span data-ttu-id="81f4b-243">[C#]</span><span class="sxs-lookup"><span data-stu-id="81f4b-243">[C#]</span></span>         | <span data-ttu-id="81f4b-244">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="81f4b-244">Web/MVC/SPA</span></span>                           | <span data-ttu-id="81f4b-245">2.0</span><span class="sxs-lookup"><span data-stu-id="81f4b-245">2.0</span></span>        |
| <span data-ttu-id="81f4b-246">ASP.NET Core con React.js y Redux</span><span class="sxs-lookup"><span data-stu-id="81f4b-246">ASP.NET Core with React.js and Redux</span></span>         | [<span data-ttu-id="81f4b-247">reactredux</span><span class="sxs-lookup"><span data-stu-id="81f4b-247">reactredux</span></span>](#reactredux)       | <span data-ttu-id="81f4b-248">[C#]</span><span class="sxs-lookup"><span data-stu-id="81f4b-248">[C#]</span></span>         | <span data-ttu-id="81f4b-249">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="81f4b-249">Web/MVC/SPA</span></span>                           | <span data-ttu-id="81f4b-250">2.0</span><span class="sxs-lookup"><span data-stu-id="81f4b-250">2.0</span></span>        |
| <span data-ttu-id="81f4b-251">Biblioteca de clases de Razor</span><span class="sxs-lookup"><span data-stu-id="81f4b-251">Razor Class Library</span></span>                          | [<span data-ttu-id="81f4b-252">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="81f4b-252">razorclasslib</span></span>](#razorclasslib) | <span data-ttu-id="81f4b-253">[C#]</span><span class="sxs-lookup"><span data-stu-id="81f4b-253">[C#]</span></span>         | <span data-ttu-id="81f4b-254">Web/Razor/Biblioteca/Biblioteca de clases de Razor</span><span class="sxs-lookup"><span data-stu-id="81f4b-254">Web/Razor/Library/Razor Class Library</span></span> | <span data-ttu-id="81f4b-255">2.1</span><span class="sxs-lookup"><span data-stu-id="81f4b-255">2.1</span></span>        |
| <span data-ttu-id="81f4b-256">API web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="81f4b-256">ASP.NET Core Web API</span></span>                         | [<span data-ttu-id="81f4b-257">webapi</span><span class="sxs-lookup"><span data-stu-id="81f4b-257">webapi</span></span>](#webapi)               | <span data-ttu-id="81f4b-258">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="81f4b-258">[C#], F#</span></span>     | <span data-ttu-id="81f4b-259">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="81f4b-259">Web/WebAPI</span></span>                            | <span data-ttu-id="81f4b-260">1.0</span><span class="sxs-lookup"><span data-stu-id="81f4b-260">1.0</span></span>        |
| <span data-ttu-id="81f4b-261">Servicio gRPC de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="81f4b-261">ASP.NET Core gRPC Service</span></span>                    | [<span data-ttu-id="81f4b-262">grpc</span><span class="sxs-lookup"><span data-stu-id="81f4b-262">grpc</span></span>](#web-others)             | <span data-ttu-id="81f4b-263">[C#]</span><span class="sxs-lookup"><span data-stu-id="81f4b-263">[C#]</span></span>         | <span data-ttu-id="81f4b-264">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="81f4b-264">Web/gRPC</span></span>                              | <span data-ttu-id="81f4b-265">3.0</span><span class="sxs-lookup"><span data-stu-id="81f4b-265">3.0</span></span>        |
| <span data-ttu-id="81f4b-266">Archivo dotnet gitignore</span><span class="sxs-lookup"><span data-stu-id="81f4b-266">dotnet gitignore file</span></span>                        | `gitignore`                     |              | <span data-ttu-id="81f4b-267">Configuración</span><span class="sxs-lookup"><span data-stu-id="81f4b-267">Config</span></span>                                | <span data-ttu-id="81f4b-268">3.0</span><span class="sxs-lookup"><span data-stu-id="81f4b-268">3.0</span></span>        |
| <span data-ttu-id="81f4b-269">archivo global.json</span><span class="sxs-lookup"><span data-stu-id="81f4b-269">global.json file</span></span>                             | [<span data-ttu-id="81f4b-270">globaljson</span><span class="sxs-lookup"><span data-stu-id="81f4b-270">globaljson</span></span>](#globaljson)       |              | <span data-ttu-id="81f4b-271">Configuración</span><span class="sxs-lookup"><span data-stu-id="81f4b-271">Config</span></span>                                | <span data-ttu-id="81f4b-272">2.0</span><span class="sxs-lookup"><span data-stu-id="81f4b-272">2.0</span></span>        |
| <span data-ttu-id="81f4b-273">Configuración de NuGet</span><span class="sxs-lookup"><span data-stu-id="81f4b-273">NuGet Config</span></span>                                 | `nugetconfig`                   |              | <span data-ttu-id="81f4b-274">Configuración</span><span class="sxs-lookup"><span data-stu-id="81f4b-274">Config</span></span>                                | <span data-ttu-id="81f4b-275">1.0</span><span class="sxs-lookup"><span data-stu-id="81f4b-275">1.0</span></span>        |
| <span data-ttu-id="81f4b-276">Archivo de manifiesto de la herramienta local dotnet</span><span class="sxs-lookup"><span data-stu-id="81f4b-276">Dotnet local tool manifest file</span></span>              | `tool-manifest`                 |              | <span data-ttu-id="81f4b-277">Configuración</span><span class="sxs-lookup"><span data-stu-id="81f4b-277">Config</span></span>                                | <span data-ttu-id="81f4b-278">3.0</span><span class="sxs-lookup"><span data-stu-id="81f4b-278">3.0</span></span>        |
| <span data-ttu-id="81f4b-279">Configuración web</span><span class="sxs-lookup"><span data-stu-id="81f4b-279">Web Config</span></span>                                   | `webconfig`                     |              | <span data-ttu-id="81f4b-280">Configuración</span><span class="sxs-lookup"><span data-stu-id="81f4b-280">Config</span></span>                                | <span data-ttu-id="81f4b-281">1.0</span><span class="sxs-lookup"><span data-stu-id="81f4b-281">1.0</span></span>        |
| <span data-ttu-id="81f4b-282">Archivo de solución</span><span class="sxs-lookup"><span data-stu-id="81f4b-282">Solution File</span></span>                                | `sln`                           |              | <span data-ttu-id="81f4b-283">Soluciones</span><span class="sxs-lookup"><span data-stu-id="81f4b-283">Solution</span></span>                              | <span data-ttu-id="81f4b-284">1.0</span><span class="sxs-lookup"><span data-stu-id="81f4b-284">1.0</span></span>        |
| <span data-ttu-id="81f4b-285">Archivo de búfer de protocolo</span><span class="sxs-lookup"><span data-stu-id="81f4b-285">Protocol Buffer File</span></span>                         | [<span data-ttu-id="81f4b-286">proto</span><span class="sxs-lookup"><span data-stu-id="81f4b-286">proto</span></span>](#namespace)             |              | <span data-ttu-id="81f4b-287">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="81f4b-287">Web/gRPC</span></span>                              | <span data-ttu-id="81f4b-288">3.0</span><span class="sxs-lookup"><span data-stu-id="81f4b-288">3.0</span></span>        |

## <a name="options"></a><span data-ttu-id="81f4b-289">Opciones</span><span class="sxs-lookup"><span data-stu-id="81f4b-289">Options</span></span>

- **`--dry-run`**

  <span data-ttu-id="81f4b-290">Muestra un resumen de lo que sucedería si se ejecutara el comando determinado y el resultado fuera la creación de una plantilla.</span><span class="sxs-lookup"><span data-stu-id="81f4b-290">Displays a summary of what would happen if the given command were run if it would result in a template creation.</span></span> <span data-ttu-id="81f4b-291">Disponible a partir del SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="81f4b-291">Available since .NET Core 2.2 SDK.</span></span>

- **`--force`**

  <span data-ttu-id="81f4b-292">Fuerza la generación de contenido incluso aunque se vayan a cambiar los archivos existentes.</span><span class="sxs-lookup"><span data-stu-id="81f4b-292">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="81f4b-293">Es necesario si la plantilla elegida invalidará los archivos existentes en el directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="81f4b-293">This is required when the template chosen would override existing files in the output directory.</span></span>

- **`-h|--help`**

  <span data-ttu-id="81f4b-294">Imprime la ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="81f4b-294">Prints out help for the command.</span></span> <span data-ttu-id="81f4b-295">Puede invocarse para el propio comando `dotnet new` o para cualquier plantilla.</span><span class="sxs-lookup"><span data-stu-id="81f4b-295">It can be invoked for the `dotnet new` command itself or for any template.</span></span> <span data-ttu-id="81f4b-296">Por ejemplo: `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-296">For example, `dotnet new mvc --help`.</span></span>

- **`-i|--install <PATH|NUGET_ID>`**

  <span data-ttu-id="81f4b-297">Instala un paquete de plantillas desde los parámetros `PATH` o `NUGET_ID` proporcionados.</span><span class="sxs-lookup"><span data-stu-id="81f4b-297">Installs a template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="81f4b-298">Si quiere instalar una versión preliminar de un paquete de plantilla, tendrá que especificar la versión en el formato de `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-298">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="81f4b-299">De forma predeterminada, `dotnet new` pasa \* para la versión, que representa la última versión estable del paquete.</span><span class="sxs-lookup"><span data-stu-id="81f4b-299">By default, `dotnet new` passes \* for the version, which represents the latest stable package version.</span></span> <span data-ttu-id="81f4b-300">Vea un ejemplo en la sección [Ejemplos](#examples).</span><span class="sxs-lookup"><span data-stu-id="81f4b-300">See an example in the [Examples](#examples) section.</span></span>
  
  <span data-ttu-id="81f4b-301">Si ya hay instalada una versión de la plantilla al ejecutar este comando, la plantilla se actualizará a la versión especificada o a la versión estable más reciente si no se ha especificado ninguna versión.</span><span class="sxs-lookup"><span data-stu-id="81f4b-301">If a version of the template was already installed when you run this command, the template will be updated to the specified version, or to the latest stable version if no version was specified.</span></span>

  <span data-ttu-id="81f4b-302">Para obtener información sobre cómo crear plantillas personalizadas, consulte [Plantillas personalizadas para dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="81f4b-302">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

- **`-l|--list`**

  <span data-ttu-id="81f4b-303">Muestra las plantillas que contienen el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="81f4b-303">Lists templates containing the specified name.</span></span> <span data-ttu-id="81f4b-304">Si no se especifica ningún nombre, enumera todas las plantillas.</span><span class="sxs-lookup"><span data-stu-id="81f4b-304">If no name is specified, lists all templates.</span></span>

- **`-lang|--language {C#|F#|VB}`**

  <span data-ttu-id="81f4b-305">El lenguaje de la plantilla que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="81f4b-305">The language of the template to create.</span></span> <span data-ttu-id="81f4b-306">El lenguaje aceptado cambia según la plantilla (vea los valores predeterminados en la sección [argumentos](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="81f4b-306">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="81f4b-307">No es válido para algunas plantillas.</span><span class="sxs-lookup"><span data-stu-id="81f4b-307">Not valid for some templates.</span></span>

  > [!NOTE]
  > <span data-ttu-id="81f4b-308">Algunos shells interpretan `#` como un carácter especial.</span><span class="sxs-lookup"><span data-stu-id="81f4b-308">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="81f4b-309">En esos casos, incluya el valor del parámetro de lenguaje entre comillas.</span><span class="sxs-lookup"><span data-stu-id="81f4b-309">In those cases, enclose the language parameter value in quotes.</span></span> <span data-ttu-id="81f4b-310">Por ejemplo: `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-310">For example, `dotnet new console -lang "F#"`.</span></span>

- **`-n|--name <OUTPUT_NAME>`**

  <span data-ttu-id="81f4b-311">El nombre de la salida creada.</span><span class="sxs-lookup"><span data-stu-id="81f4b-311">The name for the created output.</span></span> <span data-ttu-id="81f4b-312">Si no se especifica ningún nombre, se usa el nombre del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="81f4b-312">If no name is specified, the name of the current directory is used.</span></span>

- **`--nuget-source <SOURCE>`**

  <span data-ttu-id="81f4b-313">Especifica un origen de NuGet para usarlo durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="81f4b-313">Specifies a NuGet source to use during install.</span></span> <span data-ttu-id="81f4b-314">Disponible a partir del SDK de .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="81f4b-314">Available since .NET Core 2.1 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="81f4b-315">La ubicación para colocar la salida generada.</span><span class="sxs-lookup"><span data-stu-id="81f4b-315">Location to place the generated output.</span></span> <span data-ttu-id="81f4b-316">El valor predeterminado es el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="81f4b-316">The default is the current directory.</span></span>

- **`--type <TYPE>`**

  <span data-ttu-id="81f4b-317">Filtra plantillas en función de los tipos disponibles.</span><span class="sxs-lookup"><span data-stu-id="81f4b-317">Filters templates based on available types.</span></span> <span data-ttu-id="81f4b-318">Los valores predefinidos son `project` e `item`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-318">Predefined values are `project` and `item`.</span></span>

- **`-u|--uninstall [PATH|NUGET_ID]`**

  <span data-ttu-id="81f4b-319">Desinstala un paquete de plantillas en los parámetros `PATH` o `NUGET_ID` proporcionados.</span><span class="sxs-lookup"><span data-stu-id="81f4b-319">Uninstalls a template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="81f4b-320">Si no se especifica el valor `<PATH|NUGET_ID>`, se muestran todos los paquetes de plantillas instalados actualmente y sus plantillas asociadas.</span><span class="sxs-lookup"><span data-stu-id="81f4b-320">When the `<PATH|NUGET_ID>` value isn't specified, all currently installed template packs and their associated templates are displayed.</span></span> <span data-ttu-id="81f4b-321">Al especificar `NUGET_ID`, no incluya el número de versión.</span><span class="sxs-lookup"><span data-stu-id="81f4b-321">When specifying `NUGET_ID`, don't include the version number.</span></span>

  <span data-ttu-id="81f4b-322">Si no especifica un parámetro en esta opción, el comando muestra las plantillas instaladas y detalles sobre ellas.</span><span class="sxs-lookup"><span data-stu-id="81f4b-322">If you don't specify a parameter to this option, the command lists the installed templates and details about them.</span></span>

  > [!NOTE]
  > <span data-ttu-id="81f4b-323">Para desinstalar una plantilla mediante `PATH`, debe usar el nombre completo de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="81f4b-323">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="81f4b-324">Por ejemplo, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* funcionará, pero *./GarciaSoftware.ConsoleTemplate.CSharp* desde la carpeta contenedora no lo hará.</span><span class="sxs-lookup"><span data-stu-id="81f4b-324">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
  > <span data-ttu-id="81f4b-325">No incluya ninguna barra diagonal para finalizar el directorio en la ruta de acceso a la plantilla.</span><span class="sxs-lookup"><span data-stu-id="81f4b-325">Don't include a final terminating directory slash on your template path.</span></span>

- **`--update-apply`**

  <span data-ttu-id="81f4b-326">Comprueba si hay actualizaciones disponibles de los paquetes de plantillas instalados actualmente y las instala.</span><span class="sxs-lookup"><span data-stu-id="81f4b-326">Checks if there are updates available for the template packs that are currently installed and installs them.</span></span> <span data-ttu-id="81f4b-327">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="81f4b-327">Available since .NET Core 3.0 SDK.</span></span>

- **`--update-check`**

  <span data-ttu-id="81f4b-328">Comprueba si hay actualizaciones disponibles de los paquetes de plantillas instalados actualmente.</span><span class="sxs-lookup"><span data-stu-id="81f4b-328">Checks if there are updates available for the template packs that are currently installed.</span></span> <span data-ttu-id="81f4b-329">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="81f4b-329">Available since .NET Core 3.0 SDK.</span></span>

## <a name="template-options"></a><span data-ttu-id="81f4b-330">Opciones de plantilla</span><span class="sxs-lookup"><span data-stu-id="81f4b-330">Template options</span></span>

<span data-ttu-id="81f4b-331">Cada plantilla de proyecto puede tener opciones adicionales disponibles.</span><span class="sxs-lookup"><span data-stu-id="81f4b-331">Each project template may have additional options available.</span></span> <span data-ttu-id="81f4b-332">Las plantillas principales tienen las siguientes opciones adicionales:</span><span class="sxs-lookup"><span data-stu-id="81f4b-332">The core templates have the following additional options:</span></span>

### <a name="console"></a><span data-ttu-id="81f4b-333">consola</span><span class="sxs-lookup"><span data-stu-id="81f4b-333">console</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="81f4b-334">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="81f4b-334">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="81f4b-335">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="81f4b-335">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="81f4b-336">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="81f4b-336">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="81f4b-337">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="81f4b-337">SDK version</span></span> | <span data-ttu-id="81f4b-338">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="81f4b-338">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="81f4b-339">3.1</span><span class="sxs-lookup"><span data-stu-id="81f4b-339">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="81f4b-340">3.0</span><span class="sxs-lookup"><span data-stu-id="81f4b-340">3.0</span></span>         | `netcoreapp3.0` |

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="81f4b-341">Establece la propiedad `LangVersion` en el archivo del proyecto creado.</span><span class="sxs-lookup"><span data-stu-id="81f4b-341">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="81f4b-342">Por ejemplo, use `--langVersion 7.3` para emplear C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="81f4b-342">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="81f4b-343">No es compatible con F#.</span><span class="sxs-lookup"><span data-stu-id="81f4b-343">Not supported for F#.</span></span> <span data-ttu-id="81f4b-344">Disponible a partir del SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="81f4b-344">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="81f4b-345">Para obtener una lista de las versiones predeterminadas de C#, vea [Valores predeterminados](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="81f4b-345">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="81f4b-346">Si se especifica, no se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="81f4b-346">If specified, doesn't execute an implicit restore during project creation.</span></span> <span data-ttu-id="81f4b-347">Disponible a partir del SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="81f4b-347">Available since .NET Core 2.2 SDK.</span></span>

<span data-ttu-id="81f4b-348">\*\*_</span><span class="sxs-lookup"><span data-stu-id="81f4b-348">\*\*_</span></span>

### <a name="classlib"></a><span data-ttu-id="81f4b-349">classlib</span><span class="sxs-lookup"><span data-stu-id="81f4b-349">classlib</span></span>

- <span data-ttu-id="81f4b-350">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="81f4b-350">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="81f4b-351">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="81f4b-351">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="81f4b-352">Valores: `netcoreapp<version>` para crear una biblioteca de clases de .NET Core o `netstandard<version>` para crear una biblioteca de clases de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="81f4b-352">Values: `netcoreapp<version>` to create a .NET Core Class Library or `netstandard<version>` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="81f4b-353">El valor predeterminado es `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-353">The default value is `netstandard2.0`.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="81f4b-354">Establece la propiedad `LangVersion` en el archivo del proyecto creado.</span><span class="sxs-lookup"><span data-stu-id="81f4b-354">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="81f4b-355">Por ejemplo, use `--langVersion 7.3` para emplear C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="81f4b-355">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="81f4b-356">No es compatible con F#.</span><span class="sxs-lookup"><span data-stu-id="81f4b-356">Not supported for F#.</span></span> <span data-ttu-id="81f4b-357">Disponible a partir del SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="81f4b-357">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="81f4b-358">Para obtener una lista de las versiones predeterminadas de C#, vea [Valores predeterminados](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="81f4b-358">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="81f4b-359">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="81f4b-359">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="81f4b-360">\*\*_</span><span class="sxs-lookup"><span data-stu-id="81f4b-360">\*\*_</span></span>

### <a name="wpf-wpflib-wpfcustomcontrollib-wpfusercontrollib"></a><a name="wpf"></a> <span data-ttu-id="81f4b-361">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="81f4b-361">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span></span>

- <span data-ttu-id="81f4b-362">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="81f4b-362">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="81f4b-363">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="81f4b-363">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="81f4b-364">El valor predeterminado es `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-364">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="81f4b-365">Disponible a partir del SDK de .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="81f4b-365">Available since .NET Core 3.1 SDK.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="81f4b-366">Establece la propiedad `LangVersion` en el archivo del proyecto creado.</span><span class="sxs-lookup"><span data-stu-id="81f4b-366">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="81f4b-367">Por ejemplo, use `--langVersion 7.3` para emplear C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="81f4b-367">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="81f4b-368">Para obtener una lista de las versiones predeterminadas de C#, vea [Valores predeterminados](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="81f4b-368">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="81f4b-369">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="81f4b-369">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="81f4b-370">\*\*_</span><span class="sxs-lookup"><span data-stu-id="81f4b-370">\*\*_</span></span>

### <a name="winforms-winformslib"></a><a name="winforms"></a> <span data-ttu-id="81f4b-371">winforms, winformslib</span><span class="sxs-lookup"><span data-stu-id="81f4b-371">winforms, winformslib</span></span>

- <span data-ttu-id="81f4b-372">_ *`--langVersion <VERSION_NUMBER>`*\*</span><span class="sxs-lookup"><span data-stu-id="81f4b-372">_ *`--langVersion <VERSION_NUMBER>`*\*</span></span>

  <span data-ttu-id="81f4b-373">Establece la propiedad `LangVersion` en el archivo del proyecto creado.</span><span class="sxs-lookup"><span data-stu-id="81f4b-373">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="81f4b-374">Por ejemplo, use `--langVersion 7.3` para emplear C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="81f4b-374">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="81f4b-375">Para obtener una lista de las versiones predeterminadas de C#, vea [Valores predeterminados](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="81f4b-375">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="81f4b-376">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="81f4b-376">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="81f4b-377">\*\*_</span><span class="sxs-lookup"><span data-stu-id="81f4b-377">\*\*_</span></span>

### <a name="worker-grpc"></a><a name="web-others"></a> <span data-ttu-id="81f4b-378">worker, grpc</span><span class="sxs-lookup"><span data-stu-id="81f4b-378">worker, grpc</span></span>

- <span data-ttu-id="81f4b-379">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="81f4b-379">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="81f4b-380">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="81f4b-380">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="81f4b-381">El valor predeterminado es `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-381">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="81f4b-382">Disponible a partir del SDK de .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="81f4b-382">Available since .NET Core 3.1 SDK.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="81f4b-383">Excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="81f4b-383">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="81f4b-384">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="81f4b-384">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="81f4b-385">\*\*_</span><span class="sxs-lookup"><span data-stu-id="81f4b-385">\*\*_</span></span>

### <a name="mstest-xunit"></a><a name="test"></a> <span data-ttu-id="81f4b-386">mstest, xunit</span><span class="sxs-lookup"><span data-stu-id="81f4b-386">mstest, xunit</span></span>

- <span data-ttu-id="81f4b-387">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="81f4b-387">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="81f4b-388">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="81f4b-388">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="81f4b-389">Opción disponible a partir del SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="81f4b-389">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="81f4b-390">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="81f4b-390">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="81f4b-391">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="81f4b-391">SDK version</span></span> | <span data-ttu-id="81f4b-392">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="81f4b-392">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="81f4b-393">3.1</span><span class="sxs-lookup"><span data-stu-id="81f4b-393">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="81f4b-394">3.0</span><span class="sxs-lookup"><span data-stu-id="81f4b-394">3.0</span></span>         | `netcoreapp3.0` |

- **`-p|--enable-pack`**

  <span data-ttu-id="81f4b-395">Habilita el empaquetado del proyecto mediante [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="81f4b-395">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="81f4b-396">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="81f4b-396">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="81f4b-397">\*\*_</span><span class="sxs-lookup"><span data-stu-id="81f4b-397">\*\*_</span></span>

### <a name="nunit"></a><span data-ttu-id="81f4b-398">nunit</span><span class="sxs-lookup"><span data-stu-id="81f4b-398">nunit</span></span>

- <span data-ttu-id="81f4b-399">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="81f4b-399">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="81f4b-400">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="81f4b-400">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="81f4b-401">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="81f4b-401">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="81f4b-402">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="81f4b-402">SDK version</span></span> | <span data-ttu-id="81f4b-403">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="81f4b-403">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="81f4b-404">3.1</span><span class="sxs-lookup"><span data-stu-id="81f4b-404">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="81f4b-405">3.0</span><span class="sxs-lookup"><span data-stu-id="81f4b-405">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="81f4b-406">2.2</span><span class="sxs-lookup"><span data-stu-id="81f4b-406">2.2</span></span>         | `netcoreapp2.2` |
  | <span data-ttu-id="81f4b-407">2.1</span><span class="sxs-lookup"><span data-stu-id="81f4b-407">2.1</span></span>         | `netcoreapp2.1` |

- **`-p|--enable-pack`**

  <span data-ttu-id="81f4b-408">Habilita el empaquetado del proyecto mediante [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="81f4b-408">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="81f4b-409">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="81f4b-409">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="81f4b-410">\*\*_</span><span class="sxs-lookup"><span data-stu-id="81f4b-410">\*\*_</span></span>

### <a name="page"></a><span data-ttu-id="81f4b-411">página</span><span class="sxs-lookup"><span data-stu-id="81f4b-411">page</span></span>

- <span data-ttu-id="81f4b-412">_ *`-na|--namespace <NAMESPACE_NAME>`*\*</span><span class="sxs-lookup"><span data-stu-id="81f4b-412">_ *`-na|--namespace <NAMESPACE_NAME>`*\*</span></span>

  <span data-ttu-id="81f4b-413">Espacio de nombres del código generado.</span><span class="sxs-lookup"><span data-stu-id="81f4b-413">Namespace for the generated code.</span></span> <span data-ttu-id="81f4b-414">El valor predeterminado es `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-414">The default value is `MyApp.Namespace`.</span></span>

- **`-np|--no-pagemodel`**

  <span data-ttu-id="81f4b-415">Crea la página sin PageModel.</span><span class="sxs-lookup"><span data-stu-id="81f4b-415">Creates the page without a PageModel.</span></span>

<span data-ttu-id="81f4b-416">\*\*_</span><span class="sxs-lookup"><span data-stu-id="81f4b-416">\*\*_</span></span>

### <a name="viewimports-proto"></a><a name="namespace"></a> <span data-ttu-id="81f4b-417">viewimports, proto</span><span class="sxs-lookup"><span data-stu-id="81f4b-417">viewimports, proto</span></span>

- <span data-ttu-id="81f4b-418">_ *`-na|--namespace <NAMESPACE_NAME>`*\*</span><span class="sxs-lookup"><span data-stu-id="81f4b-418">_ *`-na|--namespace <NAMESPACE_NAME>`*\*</span></span>

  <span data-ttu-id="81f4b-419">Espacio de nombres del código generado.</span><span class="sxs-lookup"><span data-stu-id="81f4b-419">Namespace for the generated code.</span></span> <span data-ttu-id="81f4b-420">El valor predeterminado es `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-420">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="81f4b-421">\*\*_</span><span class="sxs-lookup"><span data-stu-id="81f4b-421">\*\*_</span></span>

### <a name="blazorserver"></a><span data-ttu-id="81f4b-422">blazorserver</span><span class="sxs-lookup"><span data-stu-id="81f4b-422">blazorserver</span></span>

- <span data-ttu-id="81f4b-423">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="81f4b-423">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="81f4b-424">Tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="81f4b-424">The type of authentication to use.</span></span> <span data-ttu-id="81f4b-425">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="81f4b-425">The possible values are:</span></span>

  - <span data-ttu-id="81f4b-426">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="81f4b-426">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="81f4b-427">`Individual`: autenticación individual.</span><span class="sxs-lookup"><span data-stu-id="81f4b-427">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="81f4b-428">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="81f4b-428">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="81f4b-429">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="81f4b-429">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="81f4b-430">`MultiOrg`: autenticación organizativa para varios inquilinos.</span><span class="sxs-lookup"><span data-stu-id="81f4b-430">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="81f4b-431">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="81f4b-431">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="81f4b-432">Instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="81f4b-432">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="81f4b-433">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-433">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="81f4b-434">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-434">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="81f4b-435">Identificador de la directiva de registro e inicio de sesión de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="81f4b-435">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="81f4b-436">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-436">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="81f4b-437">Identificador de la directiva de restablecimiento de contraseñas de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="81f4b-437">The reset password policy ID for this project.</span></span> <span data-ttu-id="81f4b-438">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-438">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="81f4b-439">Identificador de la directiva de edición de perfiles de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="81f4b-439">The edit profile policy ID for this project.</span></span> <span data-ttu-id="81f4b-440">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-440">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="81f4b-441">Instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="81f4b-441">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="81f4b-442">Úsela con las autenticaciones `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-442">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="81f4b-443">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-443">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="81f4b-444">Identificador de cliente de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="81f4b-444">The Client ID for this project.</span></span> <span data-ttu-id="81f4b-445">Úsela con las autenticaciones `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-445">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="81f4b-446">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-446">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="81f4b-447">Dominio del inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="81f4b-447">The domain for the directory tenant.</span></span> <span data-ttu-id="81f4b-448">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-448">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="81f4b-449">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-449">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="81f4b-450">Identificador de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="81f4b-450">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="81f4b-451">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-451">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="81f4b-452">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-452">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="81f4b-453">Ruta de acceso de solicitud de la ruta de acceso de la base de la aplicación del URI de redirección.</span><span class="sxs-lookup"><span data-stu-id="81f4b-453">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="81f4b-454">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-454">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="81f4b-455">El valor predeterminado es `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-455">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="81f4b-456">Concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="81f4b-456">Allows this application read-access to the directory.</span></span> <span data-ttu-id="81f4b-457">Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-457">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="81f4b-458">Excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="81f4b-458">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="81f4b-459">Desactiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="81f4b-459">Turns off HTTPS.</span></span> <span data-ttu-id="81f4b-460">Esta opción solo se aplica si no se usan `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg` en `--auth`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-460">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="81f4b-461">Especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="81f4b-461">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="81f4b-462">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-462">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--no-restore`**

  <span data-ttu-id="81f4b-463">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="81f4b-463">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="81f4b-464">\*\*_</span><span class="sxs-lookup"><span data-stu-id="81f4b-464">\*\*_</span></span>

### <a name="web"></a><span data-ttu-id="81f4b-465">web</span><span class="sxs-lookup"><span data-stu-id="81f4b-465">web</span></span>

- <span data-ttu-id="81f4b-466">_ *`--exclude-launch-settings`*\*</span><span class="sxs-lookup"><span data-stu-id="81f4b-466">_ *`--exclude-launch-settings`*\*</span></span>

  <span data-ttu-id="81f4b-467">Excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="81f4b-467">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="81f4b-468">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="81f4b-468">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="81f4b-469">Opción no disponible en el SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="81f4b-469">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="81f4b-470">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="81f4b-470">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="81f4b-471">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="81f4b-471">SDK version</span></span> | <span data-ttu-id="81f4b-472">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="81f4b-472">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="81f4b-473">3.1</span><span class="sxs-lookup"><span data-stu-id="81f4b-473">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="81f4b-474">3.0</span><span class="sxs-lookup"><span data-stu-id="81f4b-474">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="81f4b-475">2.1</span><span class="sxs-lookup"><span data-stu-id="81f4b-475">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="81f4b-476">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="81f4b-476">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="81f4b-477">Desactiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="81f4b-477">Turns off HTTPS.</span></span>

<span data-ttu-id="81f4b-478">\*\*_</span><span class="sxs-lookup"><span data-stu-id="81f4b-478">\*\*_</span></span>

### <a name="mvc-webapp"></a><a name="web-options"></a> <span data-ttu-id="81f4b-479">mvc, webapp</span><span class="sxs-lookup"><span data-stu-id="81f4b-479">mvc, webapp</span></span>

- <span data-ttu-id="81f4b-480">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="81f4b-480">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="81f4b-481">Tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="81f4b-481">The type of authentication to use.</span></span> <span data-ttu-id="81f4b-482">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="81f4b-482">The possible values are:</span></span>

  - <span data-ttu-id="81f4b-483">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="81f4b-483">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="81f4b-484">`Individual`: autenticación individual.</span><span class="sxs-lookup"><span data-stu-id="81f4b-484">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="81f4b-485">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="81f4b-485">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="81f4b-486">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="81f4b-486">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="81f4b-487">`MultiOrg`: autenticación organizativa para varios inquilinos.</span><span class="sxs-lookup"><span data-stu-id="81f4b-487">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="81f4b-488">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="81f4b-488">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="81f4b-489">Instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="81f4b-489">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="81f4b-490">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-490">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="81f4b-491">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-491">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="81f4b-492">Identificador de la directiva de registro e inicio de sesión de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="81f4b-492">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="81f4b-493">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-493">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="81f4b-494">Identificador de la directiva de restablecimiento de contraseñas de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="81f4b-494">The reset password policy ID for this project.</span></span> <span data-ttu-id="81f4b-495">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-495">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="81f4b-496">Identificador de la directiva de edición de perfiles de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="81f4b-496">The edit profile policy ID for this project.</span></span> <span data-ttu-id="81f4b-497">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-497">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="81f4b-498">Instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="81f4b-498">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="81f4b-499">Úsela con las autenticaciones `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-499">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="81f4b-500">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-500">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="81f4b-501">Identificador de cliente de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="81f4b-501">The Client ID for this project.</span></span> <span data-ttu-id="81f4b-502">Úsela con las autenticaciones `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-502">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="81f4b-503">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-503">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="81f4b-504">Dominio del inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="81f4b-504">The domain for the directory tenant.</span></span> <span data-ttu-id="81f4b-505">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-505">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="81f4b-506">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-506">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="81f4b-507">Identificador de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="81f4b-507">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="81f4b-508">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-508">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="81f4b-509">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-509">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="81f4b-510">Ruta de acceso de solicitud de la ruta de acceso de la base de la aplicación del URI de redirección.</span><span class="sxs-lookup"><span data-stu-id="81f4b-510">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="81f4b-511">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-511">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="81f4b-512">El valor predeterminado es `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-512">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="81f4b-513">Concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="81f4b-513">Allows this application read-access to the directory.</span></span> <span data-ttu-id="81f4b-514">Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-514">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="81f4b-515">Excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="81f4b-515">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="81f4b-516">Desactiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="81f4b-516">Turns off HTTPS.</span></span> <span data-ttu-id="81f4b-517">Esta opción solo se aplica si no se usan `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-517">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="81f4b-518">Especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="81f4b-518">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="81f4b-519">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-519">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="81f4b-520">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="81f4b-520">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="81f4b-521">Opción disponible a partir del SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="81f4b-521">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="81f4b-522">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="81f4b-522">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="81f4b-523">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="81f4b-523">SDK version</span></span> | <span data-ttu-id="81f4b-524">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="81f4b-524">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="81f4b-525">3.1</span><span class="sxs-lookup"><span data-stu-id="81f4b-525">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="81f4b-526">3.0</span><span class="sxs-lookup"><span data-stu-id="81f4b-526">3.0</span></span>         | `netcoreapp3.0` |

- **`--no-restore`**

  <span data-ttu-id="81f4b-527">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="81f4b-527">Doesn't execute an implicit restore during project creation.</span></span>

- **`--use-browserlink`**

  <span data-ttu-id="81f4b-528">Incluye BrowserLink en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="81f4b-528">Includes BrowserLink in the project.</span></span> <span data-ttu-id="81f4b-529">Opción no disponible en el SDK de .NET Core 2.2 y 3.1.</span><span class="sxs-lookup"><span data-stu-id="81f4b-529">Option not available in .NET Core 2.2 and 3.1 SDK.</span></span>

- **`-rrc|--razor-runtime-compilation`**

  <span data-ttu-id="81f4b-530">Determina si el proyecto está configurado para usar la [compilación en tiempo de ejecución de Razor](/aspnet/core/mvc/views/view-compilation#runtime-compilation) en las compilaciones de depuración.</span><span class="sxs-lookup"><span data-stu-id="81f4b-530">Determines if the project is configured to use [Razor runtime compilation](/aspnet/core/mvc/views/view-compilation#runtime-compilation) in Debug builds.</span></span> <span data-ttu-id="81f4b-531">Opción disponible a partir del SDK de .NET Core 3.1.201.</span><span class="sxs-lookup"><span data-stu-id="81f4b-531">Option available since .NET Core 3.1.201 SDK.</span></span>

<span data-ttu-id="81f4b-532">\*\*_</span><span class="sxs-lookup"><span data-stu-id="81f4b-532">\*\*_</span></span>

### <a name="angular-react"></a><a name="spa"></a> <span data-ttu-id="81f4b-533">angular, react</span><span class="sxs-lookup"><span data-stu-id="81f4b-533">angular, react</span></span>

- <span data-ttu-id="81f4b-534">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="81f4b-534">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="81f4b-535">Tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="81f4b-535">The type of authentication to use.</span></span> <span data-ttu-id="81f4b-536">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="81f4b-536">Available since .NET Core 3.0 SDK.</span></span>
  
  <span data-ttu-id="81f4b-537">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="81f4b-537">The possible values are:</span></span>

  - <span data-ttu-id="81f4b-538">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="81f4b-538">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="81f4b-539">`Individual`: autenticación individual.</span><span class="sxs-lookup"><span data-stu-id="81f4b-539">`Individual` - Individual authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="81f4b-540">Excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="81f4b-540">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="81f4b-541">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="81f4b-541">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="81f4b-542">Desactiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="81f4b-542">Turns off HTTPS.</span></span> <span data-ttu-id="81f4b-543">Esta opción solo se aplica si la autenticación es `None`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-543">This option only applies if authentication is `None`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="81f4b-544">Especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="81f4b-544">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="81f4b-545">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-545">Only applies to `Individual` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="81f4b-546">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="81f4b-546">Available since .NET Core 3.0 SDK.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="81f4b-547">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="81f4b-547">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="81f4b-548">Opción no disponible en el SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="81f4b-548">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="81f4b-549">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="81f4b-549">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="81f4b-550">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="81f4b-550">SDK version</span></span> | <span data-ttu-id="81f4b-551">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="81f4b-551">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="81f4b-552">3.1</span><span class="sxs-lookup"><span data-stu-id="81f4b-552">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="81f4b-553">3.0</span><span class="sxs-lookup"><span data-stu-id="81f4b-553">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="81f4b-554">2.1</span><span class="sxs-lookup"><span data-stu-id="81f4b-554">2.1</span></span>         | `netcoreapp2.0` |

<span data-ttu-id="81f4b-555">\*\*_</span><span class="sxs-lookup"><span data-stu-id="81f4b-555">\*\*_</span></span>

### <a name="reactredux"></a><span data-ttu-id="81f4b-556">reactredux</span><span class="sxs-lookup"><span data-stu-id="81f4b-556">reactredux</span></span>

- <span data-ttu-id="81f4b-557">_ *`--exclude-launch-settings`*\*</span><span class="sxs-lookup"><span data-stu-id="81f4b-557">_ *`--exclude-launch-settings`*\*</span></span>

  <span data-ttu-id="81f4b-558">Excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="81f4b-558">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="81f4b-559">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="81f4b-559">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="81f4b-560">Opción no disponible en el SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="81f4b-560">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="81f4b-561">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="81f4b-561">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="81f4b-562">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="81f4b-562">SDK version</span></span> | <span data-ttu-id="81f4b-563">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="81f4b-563">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="81f4b-564">3.1</span><span class="sxs-lookup"><span data-stu-id="81f4b-564">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="81f4b-565">3.0</span><span class="sxs-lookup"><span data-stu-id="81f4b-565">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="81f4b-566">2.1</span><span class="sxs-lookup"><span data-stu-id="81f4b-566">2.1</span></span>         | `netcoreapp2.0` |

- **`--no-restore`**

  <span data-ttu-id="81f4b-567">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="81f4b-567">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="81f4b-568">Desactiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="81f4b-568">Turns off HTTPS.</span></span>

<span data-ttu-id="81f4b-569">\*\*_</span><span class="sxs-lookup"><span data-stu-id="81f4b-569">\*\*_</span></span>

### <a name="razorclasslib"></a><span data-ttu-id="81f4b-570">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="81f4b-570">razorclasslib</span></span>

- <span data-ttu-id="81f4b-571">_ *`--no-restore`*\*</span><span class="sxs-lookup"><span data-stu-id="81f4b-571">_ *`--no-restore`*\*</span></span>

  <span data-ttu-id="81f4b-572">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="81f4b-572">Doesn't execute an implicit restore during project creation.</span></span>

- **`-s|--support-pages-and-views`**

  <span data-ttu-id="81f4b-573">Permite agregar vistas y páginas de Razor tradicionales además de los componentes a esta biblioteca.</span><span class="sxs-lookup"><span data-stu-id="81f4b-573">Supports adding traditional Razor pages and Views in addition to components to this library.</span></span> <span data-ttu-id="81f4b-574">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="81f4b-574">Available since .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="81f4b-575">\*\*_</span><span class="sxs-lookup"><span data-stu-id="81f4b-575">\*\*_</span></span>
  
### <a name="webapi"></a><span data-ttu-id="81f4b-576">webapi</span><span class="sxs-lookup"><span data-stu-id="81f4b-576">webapi</span></span>

- <span data-ttu-id="81f4b-577">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="81f4b-577">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="81f4b-578">Tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="81f4b-578">The type of authentication to use.</span></span> <span data-ttu-id="81f4b-579">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="81f4b-579">The possible values are:</span></span>

  - <span data-ttu-id="81f4b-580">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="81f4b-580">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="81f4b-581">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="81f4b-581">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="81f4b-582">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="81f4b-582">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="81f4b-583">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="81f4b-583">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="81f4b-584">Instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="81f4b-584">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="81f4b-585">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-585">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="81f4b-586">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-586">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="81f4b-587">Identificador de la directiva de registro e inicio de sesión de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="81f4b-587">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="81f4b-588">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-588">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="81f4b-589">Instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="81f4b-589">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="81f4b-590">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-590">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="81f4b-591">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-591">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="81f4b-592">Identificador de cliente de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="81f4b-592">The Client ID for this project.</span></span> <span data-ttu-id="81f4b-593">Úsela con las autenticaciones `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-593">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="81f4b-594">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-594">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="81f4b-595">Dominio del inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="81f4b-595">The domain for the directory tenant.</span></span> <span data-ttu-id="81f4b-596">Úsela con las autenticaciones `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-596">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="81f4b-597">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-597">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="81f4b-598">Identificador de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="81f4b-598">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="81f4b-599">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-599">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="81f4b-600">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-600">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="81f4b-601">Concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="81f4b-601">Allows this application read-access to the directory.</span></span> <span data-ttu-id="81f4b-602">Solo se aplica a la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-602">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="81f4b-603">Excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="81f4b-603">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="81f4b-604">Desactiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="81f4b-604">Turns off HTTPS.</span></span> <span data-ttu-id="81f4b-605">`app.UseHsts` y `app.UseHttpsRedirection` no se agregan a `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-605">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="81f4b-606">Esta opción solo se aplica si no se usan `IndividualB2C` o `SingleOrg` en la autenticación.</span><span class="sxs-lookup"><span data-stu-id="81f4b-606">This option only applies if `IndividualB2C` or `SingleOrg` aren't being used for authentication.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="81f4b-607">Especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="81f4b-607">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="81f4b-608">Solo se aplica a la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="81f4b-608">Only applies to `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="81f4b-609">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="81f4b-609">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="81f4b-610">Opción no disponible en el SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="81f4b-610">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="81f4b-611">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="81f4b-611">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="81f4b-612">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="81f4b-612">SDK version</span></span> | <span data-ttu-id="81f4b-613">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="81f4b-613">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="81f4b-614">3.1</span><span class="sxs-lookup"><span data-stu-id="81f4b-614">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="81f4b-615">3.0</span><span class="sxs-lookup"><span data-stu-id="81f4b-615">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="81f4b-616">2.1</span><span class="sxs-lookup"><span data-stu-id="81f4b-616">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="81f4b-617">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="81f4b-617">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="81f4b-618">\*\*_</span><span class="sxs-lookup"><span data-stu-id="81f4b-618">\*\*_</span></span>

### <a name="globaljson"></a><span data-ttu-id="81f4b-619">globaljson</span><span class="sxs-lookup"><span data-stu-id="81f4b-619">globaljson</span></span>

- <span data-ttu-id="81f4b-620">_ *`--sdk-version <VERSION_NUMBER>`*\*</span><span class="sxs-lookup"><span data-stu-id="81f4b-620">_ *`--sdk-version <VERSION_NUMBER>`*\*</span></span>

  <span data-ttu-id="81f4b-621">Especifica la versión del SDK de .NET Core que se usará en el archivo *global.json* .</span><span class="sxs-lookup"><span data-stu-id="81f4b-621">Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

***

## <a name="examples"></a><span data-ttu-id="81f4b-622">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="81f4b-622">Examples</span></span>

- <span data-ttu-id="81f4b-623">Creación de un proyecto de aplicación de consola de C# mediante la especificación del nombre de plantilla:</span><span class="sxs-lookup"><span data-stu-id="81f4b-623">Create a C# console application project by specifying the template name:</span></span>

  ```dotnetcli
  dotnet new "Console Application"
  ```

- <span data-ttu-id="81f4b-624">Creación de un proyecto de aplicación de consola con F# en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="81f4b-624">Create an F# console application project in the current directory:</span></span>

  ```dotnetcli
  dotnet new console -lang "F#"
  ```

- <span data-ttu-id="81f4b-625">Creación de un proyecto de biblioteca de clases de .NET Standard en el directorio especificado:</span><span class="sxs-lookup"><span data-stu-id="81f4b-625">Create a .NET Standard class library project in the specified directory:</span></span>

  ```dotnetcli
  dotnet new classlib -lang VB -o MyLibrary
  ```

- <span data-ttu-id="81f4b-626">Creación de un proyecto MVC de ASP.NET Core C# en el directorio actual sin autenticación:</span><span class="sxs-lookup"><span data-stu-id="81f4b-626">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

  ```dotnetcli
  dotnet new mvc -au None
  ```

- <span data-ttu-id="81f4b-627">Creación de un proyecto de xUnit:</span><span class="sxs-lookup"><span data-stu-id="81f4b-627">Create a new xUnit project:</span></span>

  ```dotnetcli
  dotnet new xunit
  ```

- <span data-ttu-id="81f4b-628">Enumeración de todas las plantillas disponibles en las plantillas de aplicación de página única (SPA):</span><span class="sxs-lookup"><span data-stu-id="81f4b-628">List all templates available for Single Page Application (SPA) templates:</span></span>

  ```dotnetcli
  dotnet new spa -l
  ```

- <span data-ttu-id="81f4b-629">Enumeración de todas las plantillas que coinciden con la subcadena *we* .</span><span class="sxs-lookup"><span data-stu-id="81f4b-629">List all templates matching the *we* substring.</span></span> <span data-ttu-id="81f4b-630">No se encuentra ninguna coincidencia exacta, por lo que se ejecuta la coincidencia de subcadena con las columnas de nombre corto y de nombre.</span><span class="sxs-lookup"><span data-stu-id="81f4b-630">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

  ```dotnetcli
  dotnet new we -l
  ```

- <span data-ttu-id="81f4b-631">Intento de invocar a la plantilla que coincide con *ng* .</span><span class="sxs-lookup"><span data-stu-id="81f4b-631">Attempt to invoke the template matching *ng* .</span></span> <span data-ttu-id="81f4b-632">Si no se puede determinar una única coincidencia, se enumeran las plantillas que son coincidencias parciales.</span><span class="sxs-lookup"><span data-stu-id="81f4b-632">If a single match can't be determined, list the templates that are partial matches.</span></span>

  ```dotnetcli
  dotnet new ng
  ```

- <span data-ttu-id="81f4b-633">Instalación de la versión 2.0 de las plantillas de SPA de ASP.NET Core:</span><span class="sxs-lookup"><span data-stu-id="81f4b-633">Install version 2.0 of the SPA templates for ASP.NET Core:</span></span>

  ```dotnetcli
  dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0
  ```

- <span data-ttu-id="81f4b-634">Enumeración de las plantillas instaladas y detalles sobre ellas, incluido cómo desinstalarlas:</span><span class="sxs-lookup"><span data-stu-id="81f4b-634">List the installed templates and details about them, including how to uninstall them:</span></span>

  ```dotnetcli
  dotnet new -u
  ```

- <span data-ttu-id="81f4b-635">Creación de un archivo *global.json* en el directorio actual al establecer la versión del SDK en 3.1.101:</span><span class="sxs-lookup"><span data-stu-id="81f4b-635">Create a *global.json* in the current directory setting the SDK version to 3.1.101:</span></span>

  ```dotnetcli
  dotnet new globaljson --sdk-version 3.1.101
  ```

## <a name="see-also"></a><span data-ttu-id="81f4b-636">Vea también</span><span class="sxs-lookup"><span data-stu-id="81f4b-636">See also</span></span>

- [<span data-ttu-id="81f4b-637">Plantillas personalizadas para dotnet new</span><span class="sxs-lookup"><span data-stu-id="81f4b-637">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="81f4b-638">Creación de una plantilla personalizada para dotnet new</span><span class="sxs-lookup"><span data-stu-id="81f4b-638">Create a custom template for dotnet new</span></span>](../tutorials/cli-templates-create-item-template.md)
- [<span data-ttu-id="81f4b-639">Repositorio de GitHub dotnet/dotnet-template-samples</span><span class="sxs-lookup"><span data-stu-id="81f4b-639">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- <span data-ttu-id="81f4b-640">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new) (Plantillas disponibles para dotnet new)</span><span class="sxs-lookup"><span data-stu-id="81f4b-640">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)</span></span>
