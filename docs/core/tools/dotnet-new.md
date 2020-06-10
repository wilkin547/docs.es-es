---
title: Comando dotnet new
description: El comando dotnet new crea proyectos de .NET Core basados en la plantilla especificada.
ms.date: 04/10/2020
ms.openlocfilehash: 39301ad95761848b60b45cb5c18ede937f70c32c
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84283980"
---
# <a name="dotnet-new"></a><span data-ttu-id="3c589-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="3c589-103">dotnet new</span></span>

<span data-ttu-id="3c589-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.0 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="3c589-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="3c589-105">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="3c589-105">Name</span></span>

<span data-ttu-id="3c589-106">`dotnet new`: crea un nuevo proyecto, archivo de configuración o solución según la plantilla especificada.</span><span class="sxs-lookup"><span data-stu-id="3c589-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="3c589-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="3c589-107">Synopsis</span></span>

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install {PATH|NUGET_ID}]
    [-lang|--language {"C#"|"F#"|VB}] [-n|--name <OUTPUT_NAME>]
    [--nuget-source <SOURCE>] [-o|--output <OUTPUT_DIRECTORY>]
    [-u|--uninstall] [--update-apply] [--update-check] [Template options]

dotnet new <TEMPLATE> [-l|--list] [--type <TYPE>]

dotnet new -h|--help
```

## <a name="description"></a><span data-ttu-id="3c589-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="3c589-108">Description</span></span>

<span data-ttu-id="3c589-109">El comando `dotnet new` crea un proyecto de .NET Core u otros artefactos basados en una plantilla.</span><span class="sxs-lookup"><span data-stu-id="3c589-109">The `dotnet new` command creates a .NET Core project or other artifacts based on a template.</span></span>

<span data-ttu-id="3c589-110">El comando llama al [motor de plantillas](https://github.com/dotnet/templating) para crear los artefactos en el disco basándose en las opciones y la plantilla especificadas.</span><span class="sxs-lookup"><span data-stu-id="3c589-110">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="3c589-111">Restauración implícita</span><span class="sxs-lookup"><span data-stu-id="3c589-111">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="3c589-112">Argumentos</span><span class="sxs-lookup"><span data-stu-id="3c589-112">Arguments</span></span>

- **`TEMPLATE`**

  <span data-ttu-id="3c589-113">La plantilla de la que se va a crear una instancia cuando se invoca el comando.</span><span class="sxs-lookup"><span data-stu-id="3c589-113">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="3c589-114">Cada plantilla puede tener opciones específicas que puede pasar.</span><span class="sxs-lookup"><span data-stu-id="3c589-114">Each template might have specific options you can pass.</span></span> <span data-ttu-id="3c589-115">Para obtener más información, vea [Opciones de plantilla](#template-options).</span><span class="sxs-lookup"><span data-stu-id="3c589-115">For more information, see [Template options](#template-options).</span></span>

  <span data-ttu-id="3c589-116">Puede ejecutar `dotnet new --list` o `dotnet new -l` para ver una lista de todas las plantillas instaladas.</span><span class="sxs-lookup"><span data-stu-id="3c589-116">You can run `dotnet new --list` or `dotnet new -l` to see a list of all installed templates.</span></span> <span data-ttu-id="3c589-117">Si el valor `TEMPLATE` no es una coincidencia exacta con el texto de la columna **Plantillas** o **Nombre corto** de la tabla devuelta, se realiza una coincidencia de subcadena con esas dos columnas.</span><span class="sxs-lookup"><span data-stu-id="3c589-117">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column from the returned table, a substring match is performed on those two columns.</span></span>

  <span data-ttu-id="3c589-118">A partir del SDK de .NET Core 3.0, la CLI busca plantillas en NuGet.org al invocar el comando `dotnet new` en las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="3c589-118">Starting with .NET Core 3.0 SDK, the CLI searches for templates in NuGet.org when you invoke the `dotnet new` command in the following conditions:</span></span>

  - <span data-ttu-id="3c589-119">Si la CLI no encuentra ninguna coincidencia de plantilla al invocar `dotnet new`, ni siquiera parcial.</span><span class="sxs-lookup"><span data-stu-id="3c589-119">If the CLI can't find a template match when invoking `dotnet new`, not even partial.</span></span>
  - <span data-ttu-id="3c589-120">Si hay disponible una versión más reciente de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="3c589-120">If there's a newer version of the template available.</span></span> <span data-ttu-id="3c589-121">En este caso, se crea el proyecto o el artefacto, pero la CLI le advierte de que hay una versión actualizada de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="3c589-121">In this case, the project or artifact is created but the CLI warns you about an updated version of the template.</span></span>

  <span data-ttu-id="3c589-122">En la tabla siguiente se muestran las plantillas que vienen preinstaladas en el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3c589-122">The following table shows the templates that come pre-installed with the .NET Core SDK.</span></span> <span data-ttu-id="3c589-123">El lenguaje predeterminado de la plantilla se muestra entre corchetes.</span><span class="sxs-lookup"><span data-stu-id="3c589-123">The default language for the template is shown inside the brackets.</span></span> <span data-ttu-id="3c589-124">Haga clic en el vínculo del nombre corto para ver las opciones específicas de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="3c589-124">Click on the short name link to see the specific template options.</span></span>

| <span data-ttu-id="3c589-125">Plantillas</span><span class="sxs-lookup"><span data-stu-id="3c589-125">Templates</span></span>                                    | <span data-ttu-id="3c589-126">Nombre corto</span><span class="sxs-lookup"><span data-stu-id="3c589-126">Short name</span></span>                      | <span data-ttu-id="3c589-127">Lenguaje</span><span class="sxs-lookup"><span data-stu-id="3c589-127">Language</span></span>     | <span data-ttu-id="3c589-128">Etiquetas</span><span class="sxs-lookup"><span data-stu-id="3c589-128">Tags</span></span>                                  | <span data-ttu-id="3c589-129">Inclusión</span><span class="sxs-lookup"><span data-stu-id="3c589-129">Introduced</span></span> |
|----------------------------------------------|---------------------------------|--------------|---------------------------------------|------------|
| <span data-ttu-id="3c589-130">Aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="3c589-130">Console Application</span></span>                          | [<span data-ttu-id="3c589-131">console</span><span class="sxs-lookup"><span data-stu-id="3c589-131">console</span></span>](#console)             | <span data-ttu-id="3c589-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="3c589-132">[C#], F#, VB</span></span> | <span data-ttu-id="3c589-133">Común/Consola</span><span class="sxs-lookup"><span data-stu-id="3c589-133">Common/Console</span></span>                        | <span data-ttu-id="3c589-134">1.0</span><span class="sxs-lookup"><span data-stu-id="3c589-134">1.0</span></span>        |
| <span data-ttu-id="3c589-135">Biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="3c589-135">Class library</span></span>                                | [<span data-ttu-id="3c589-136">classlib</span><span class="sxs-lookup"><span data-stu-id="3c589-136">classlib</span></span>](#classlib)           | <span data-ttu-id="3c589-137">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="3c589-137">[C#], F#, VB</span></span> | <span data-ttu-id="3c589-138">Común/Biblioteca</span><span class="sxs-lookup"><span data-stu-id="3c589-138">Common/Library</span></span>                        | <span data-ttu-id="3c589-139">1.0</span><span class="sxs-lookup"><span data-stu-id="3c589-139">1.0</span></span>        |
| <span data-ttu-id="3c589-140">Aplicación WPF</span><span class="sxs-lookup"><span data-stu-id="3c589-140">WPF Application</span></span>                              | [<span data-ttu-id="3c589-141">wpf</span><span class="sxs-lookup"><span data-stu-id="3c589-141">wpf</span></span>](#wpf)                     | <span data-ttu-id="3c589-142">[C#]</span><span class="sxs-lookup"><span data-stu-id="3c589-142">[C#]</span></span>         | <span data-ttu-id="3c589-143">Común/WPF</span><span class="sxs-lookup"><span data-stu-id="3c589-143">Common/WPF</span></span>                            | <span data-ttu-id="3c589-144">3.0</span><span class="sxs-lookup"><span data-stu-id="3c589-144">3.0</span></span>        |
| <span data-ttu-id="3c589-145">Biblioteca de clases de WPF</span><span class="sxs-lookup"><span data-stu-id="3c589-145">WPF Class library</span></span>                            | [<span data-ttu-id="3c589-146">wpflib</span><span class="sxs-lookup"><span data-stu-id="3c589-146">wpflib</span></span>](#wpf)                  | <span data-ttu-id="3c589-147">[C#]</span><span class="sxs-lookup"><span data-stu-id="3c589-147">[C#]</span></span>         | <span data-ttu-id="3c589-148">Común/WPF</span><span class="sxs-lookup"><span data-stu-id="3c589-148">Common/WPF</span></span>                            | <span data-ttu-id="3c589-149">3.0</span><span class="sxs-lookup"><span data-stu-id="3c589-149">3.0</span></span>        |
| <span data-ttu-id="3c589-150">Biblioteca de controles personalizados WPF</span><span class="sxs-lookup"><span data-stu-id="3c589-150">WPF Custom Control Library</span></span>                   | [<span data-ttu-id="3c589-151">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="3c589-151">wpfcustomcontrollib</span></span>](#wpf)     | <span data-ttu-id="3c589-152">[C#]</span><span class="sxs-lookup"><span data-stu-id="3c589-152">[C#]</span></span>         | <span data-ttu-id="3c589-153">Común/WPF</span><span class="sxs-lookup"><span data-stu-id="3c589-153">Common/WPF</span></span>                            | <span data-ttu-id="3c589-154">3.0</span><span class="sxs-lookup"><span data-stu-id="3c589-154">3.0</span></span>        |
| <span data-ttu-id="3c589-155">Biblioteca de controles de usuario de WPF</span><span class="sxs-lookup"><span data-stu-id="3c589-155">WPF User Control Library</span></span>                     | [<span data-ttu-id="3c589-156">wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="3c589-156">wpfusercontrollib</span></span>](#wpf)       | <span data-ttu-id="3c589-157">[C#]</span><span class="sxs-lookup"><span data-stu-id="3c589-157">[C#]</span></span>         | <span data-ttu-id="3c589-158">Común/WPF</span><span class="sxs-lookup"><span data-stu-id="3c589-158">Common/WPF</span></span>                            | <span data-ttu-id="3c589-159">3.0</span><span class="sxs-lookup"><span data-stu-id="3c589-159">3.0</span></span>        |
| <span data-ttu-id="3c589-160">Aplicación de Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="3c589-160">Windows Forms (WinForms) Application</span></span>         | [<span data-ttu-id="3c589-161">winforms</span><span class="sxs-lookup"><span data-stu-id="3c589-161">winforms</span></span>](#winforms)           | <span data-ttu-id="3c589-162">[C#]</span><span class="sxs-lookup"><span data-stu-id="3c589-162">[C#]</span></span>         | <span data-ttu-id="3c589-163">Común/WinForms</span><span class="sxs-lookup"><span data-stu-id="3c589-163">Common/WinForms</span></span>                       | <span data-ttu-id="3c589-164">3.0</span><span class="sxs-lookup"><span data-stu-id="3c589-164">3.0</span></span>        |
| <span data-ttu-id="3c589-165">Biblioteca de clases de Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="3c589-165">Windows Forms (WinForms) Class library</span></span>       | [<span data-ttu-id="3c589-166">winformslib</span><span class="sxs-lookup"><span data-stu-id="3c589-166">winformslib</span></span>](#winforms)        | <span data-ttu-id="3c589-167">[C#]</span><span class="sxs-lookup"><span data-stu-id="3c589-167">[C#]</span></span>         | <span data-ttu-id="3c589-168">Común/WinForms</span><span class="sxs-lookup"><span data-stu-id="3c589-168">Common/WinForms</span></span>                       | <span data-ttu-id="3c589-169">3.0</span><span class="sxs-lookup"><span data-stu-id="3c589-169">3.0</span></span>        |
| <span data-ttu-id="3c589-170">Servicio Worker</span><span class="sxs-lookup"><span data-stu-id="3c589-170">Worker Service</span></span>                               | [<span data-ttu-id="3c589-171">worker</span><span class="sxs-lookup"><span data-stu-id="3c589-171">worker</span></span>](#web-others)           | <span data-ttu-id="3c589-172">[C#]</span><span class="sxs-lookup"><span data-stu-id="3c589-172">[C#]</span></span>         | <span data-ttu-id="3c589-173">Común/Worker/Web</span><span class="sxs-lookup"><span data-stu-id="3c589-173">Common/Worker/Web</span></span>                     | <span data-ttu-id="3c589-174">3.0</span><span class="sxs-lookup"><span data-stu-id="3c589-174">3.0</span></span>        |
| <span data-ttu-id="3c589-175">Proyecto de prueba unitaria</span><span class="sxs-lookup"><span data-stu-id="3c589-175">Unit Test Project</span></span>                            | [<span data-ttu-id="3c589-176">mstest</span><span class="sxs-lookup"><span data-stu-id="3c589-176">mstest</span></span>](#test)                 | <span data-ttu-id="3c589-177">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="3c589-177">[C#], F#, VB</span></span> | <span data-ttu-id="3c589-178">Prueba/MSTest</span><span class="sxs-lookup"><span data-stu-id="3c589-178">Test/MSTest</span></span>                           | <span data-ttu-id="3c589-179">1.0</span><span class="sxs-lookup"><span data-stu-id="3c589-179">1.0</span></span>        |
| <span data-ttu-id="3c589-180">Proyecto de prueba de NUnit 3</span><span class="sxs-lookup"><span data-stu-id="3c589-180">NUnit 3 Test Project</span></span>                         | [<span data-ttu-id="3c589-181">nunit</span><span class="sxs-lookup"><span data-stu-id="3c589-181">nunit</span></span>](#nunit)                  | <span data-ttu-id="3c589-182">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="3c589-182">[C#], F#, VB</span></span> | <span data-ttu-id="3c589-183">Prueba/NUnit</span><span class="sxs-lookup"><span data-stu-id="3c589-183">Test/NUnit</span></span>                            | <span data-ttu-id="3c589-184">2.1.400</span><span class="sxs-lookup"><span data-stu-id="3c589-184">2.1.400</span></span>    |
| <span data-ttu-id="3c589-185">Elemento de prueba de NUnit 3</span><span class="sxs-lookup"><span data-stu-id="3c589-185">NUnit 3 Test Item</span></span>                            | `nunit-test`                    | <span data-ttu-id="3c589-186">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="3c589-186">[C#], F#, VB</span></span> | <span data-ttu-id="3c589-187">Prueba/NUnit</span><span class="sxs-lookup"><span data-stu-id="3c589-187">Test/NUnit</span></span>                            | <span data-ttu-id="3c589-188">2.2</span><span class="sxs-lookup"><span data-stu-id="3c589-188">2.2</span></span>        |
| <span data-ttu-id="3c589-189">Proyecto de prueba de xUnit</span><span class="sxs-lookup"><span data-stu-id="3c589-189">xUnit Test Project</span></span>                           | [<span data-ttu-id="3c589-190">xunit</span><span class="sxs-lookup"><span data-stu-id="3c589-190">xunit</span></span>](#test)                  | <span data-ttu-id="3c589-191">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="3c589-191">[C#], F#, VB</span></span> | <span data-ttu-id="3c589-192">Prueba/xUnit</span><span class="sxs-lookup"><span data-stu-id="3c589-192">Test/xUnit</span></span>                            | <span data-ttu-id="3c589-193">1.0</span><span class="sxs-lookup"><span data-stu-id="3c589-193">1.0</span></span>        |
| <span data-ttu-id="3c589-194">Componente Razor</span><span class="sxs-lookup"><span data-stu-id="3c589-194">Razor Component</span></span>                              | `razorcomponent`                | <span data-ttu-id="3c589-195">[C#]</span><span class="sxs-lookup"><span data-stu-id="3c589-195">[C#]</span></span>         | <span data-ttu-id="3c589-196">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="3c589-196">Web/ASP.NET</span></span>                           | <span data-ttu-id="3c589-197">3.0</span><span class="sxs-lookup"><span data-stu-id="3c589-197">3.0</span></span>        |
| <span data-ttu-id="3c589-198">Página de Razor</span><span class="sxs-lookup"><span data-stu-id="3c589-198">Razor Page</span></span>                                   | [<span data-ttu-id="3c589-199">page</span><span class="sxs-lookup"><span data-stu-id="3c589-199">page</span></span>](#page)                   | <span data-ttu-id="3c589-200">[C#]</span><span class="sxs-lookup"><span data-stu-id="3c589-200">[C#]</span></span>         | <span data-ttu-id="3c589-201">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="3c589-201">Web/ASP.NET</span></span>                           | <span data-ttu-id="3c589-202">2.0</span><span class="sxs-lookup"><span data-stu-id="3c589-202">2.0</span></span>        |
| <span data-ttu-id="3c589-203">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="3c589-203">MVC ViewImports</span></span>                              | [<span data-ttu-id="3c589-204">viewimports</span><span class="sxs-lookup"><span data-stu-id="3c589-204">viewimports</span></span>](#namespace)       | <span data-ttu-id="3c589-205">[C#]</span><span class="sxs-lookup"><span data-stu-id="3c589-205">[C#]</span></span>         | <span data-ttu-id="3c589-206">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="3c589-206">Web/ASP.NET</span></span>                           | <span data-ttu-id="3c589-207">2.0</span><span class="sxs-lookup"><span data-stu-id="3c589-207">2.0</span></span>        |
| <span data-ttu-id="3c589-208">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="3c589-208">MVC ViewStart</span></span>                                | `viewstart`                     | <span data-ttu-id="3c589-209">[C#]</span><span class="sxs-lookup"><span data-stu-id="3c589-209">[C#]</span></span>         | <span data-ttu-id="3c589-210">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="3c589-210">Web/ASP.NET</span></span>                           | <span data-ttu-id="3c589-211">2.0</span><span class="sxs-lookup"><span data-stu-id="3c589-211">2.0</span></span>        |
| <span data-ttu-id="3c589-212">Aplicación de servidor Blazor</span><span class="sxs-lookup"><span data-stu-id="3c589-212">Blazor Server App</span></span>                            | [<span data-ttu-id="3c589-213">blazorserver</span><span class="sxs-lookup"><span data-stu-id="3c589-213">blazorserver</span></span>](#blazorserver)   | <span data-ttu-id="3c589-214">[C#]</span><span class="sxs-lookup"><span data-stu-id="3c589-214">[C#]</span></span>         | <span data-ttu-id="3c589-215">Web/Blazor</span><span class="sxs-lookup"><span data-stu-id="3c589-215">Web/Blazor</span></span>                            | <span data-ttu-id="3c589-216">3.0</span><span class="sxs-lookup"><span data-stu-id="3c589-216">3.0</span></span>        |
| <span data-ttu-id="3c589-217">Aplicación WebAssembly de Blazor</span><span class="sxs-lookup"><span data-stu-id="3c589-217">Blazor WebAssembly App</span></span>                       | `blazorwasm`                    | <span data-ttu-id="3c589-218">[C#]</span><span class="sxs-lookup"><span data-stu-id="3c589-218">[C#]</span></span>         | <span data-ttu-id="3c589-219">Web/Blazor/WebAssembly</span><span class="sxs-lookup"><span data-stu-id="3c589-219">Web/Blazor/WebAssembly</span></span>                            | <span data-ttu-id="3c589-220">3.1.300</span><span class="sxs-lookup"><span data-stu-id="3c589-220">3.1.300</span></span>    |
| <span data-ttu-id="3c589-221">Vacío de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="3c589-221">ASP.NET Core Empty</span></span>                           | [<span data-ttu-id="3c589-222">web</span><span class="sxs-lookup"><span data-stu-id="3c589-222">web</span></span>](#web)                     | <span data-ttu-id="3c589-223">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="3c589-223">[C#], F#</span></span>     | <span data-ttu-id="3c589-224">Web/Vacío</span><span class="sxs-lookup"><span data-stu-id="3c589-224">Web/Empty</span></span>                             | <span data-ttu-id="3c589-225">1.0</span><span class="sxs-lookup"><span data-stu-id="3c589-225">1.0</span></span>        |
| <span data-ttu-id="3c589-226">Aplicación web de ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="3c589-226">ASP.NET Core Web App (Model-View-Controller)</span></span> | [<span data-ttu-id="3c589-227">mvc</span><span class="sxs-lookup"><span data-stu-id="3c589-227">mvc</span></span>](#web-options)             | <span data-ttu-id="3c589-228">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="3c589-228">[C#], F#</span></span>     | <span data-ttu-id="3c589-229">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="3c589-229">Web/MVC</span></span>                               | <span data-ttu-id="3c589-230">1.0</span><span class="sxs-lookup"><span data-stu-id="3c589-230">1.0</span></span>        |
| <span data-ttu-id="3c589-231">Aplicación web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="3c589-231">ASP.NET Core Web App</span></span>                         | [<span data-ttu-id="3c589-232">webapp, razor</span><span class="sxs-lookup"><span data-stu-id="3c589-232">webapp, razor</span></span>](#web-options)   | <span data-ttu-id="3c589-233">[C#]</span><span class="sxs-lookup"><span data-stu-id="3c589-233">[C#]</span></span>         | <span data-ttu-id="3c589-234">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="3c589-234">Web/MVC/Razor Pages</span></span>                   | <span data-ttu-id="3c589-235">2.2, 2.0</span><span class="sxs-lookup"><span data-stu-id="3c589-235">2.2, 2.0</span></span>   |
| <span data-ttu-id="3c589-236">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="3c589-236">ASP.NET Core with Angular</span></span>                    | [<span data-ttu-id="3c589-237">angular</span><span class="sxs-lookup"><span data-stu-id="3c589-237">angular</span></span>](#spa)                 | <span data-ttu-id="3c589-238">[C#]</span><span class="sxs-lookup"><span data-stu-id="3c589-238">[C#]</span></span>         | <span data-ttu-id="3c589-239">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="3c589-239">Web/MVC/SPA</span></span>                           | <span data-ttu-id="3c589-240">2.0</span><span class="sxs-lookup"><span data-stu-id="3c589-240">2.0</span></span>        |
| <span data-ttu-id="3c589-241">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="3c589-241">ASP.NET Core with React.js</span></span>                   | [<span data-ttu-id="3c589-242">react</span><span class="sxs-lookup"><span data-stu-id="3c589-242">react</span></span>](#spa)                   | <span data-ttu-id="3c589-243">[C#]</span><span class="sxs-lookup"><span data-stu-id="3c589-243">[C#]</span></span>         | <span data-ttu-id="3c589-244">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="3c589-244">Web/MVC/SPA</span></span>                           | <span data-ttu-id="3c589-245">2.0</span><span class="sxs-lookup"><span data-stu-id="3c589-245">2.0</span></span>        |
| <span data-ttu-id="3c589-246">ASP.NET Core con React.js y Redux</span><span class="sxs-lookup"><span data-stu-id="3c589-246">ASP.NET Core with React.js and Redux</span></span>         | [<span data-ttu-id="3c589-247">reactredux</span><span class="sxs-lookup"><span data-stu-id="3c589-247">reactredux</span></span>](#reactredux)       | <span data-ttu-id="3c589-248">[C#]</span><span class="sxs-lookup"><span data-stu-id="3c589-248">[C#]</span></span>         | <span data-ttu-id="3c589-249">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="3c589-249">Web/MVC/SPA</span></span>                           | <span data-ttu-id="3c589-250">2.0</span><span class="sxs-lookup"><span data-stu-id="3c589-250">2.0</span></span>        |
| <span data-ttu-id="3c589-251">Biblioteca de clases de Razor</span><span class="sxs-lookup"><span data-stu-id="3c589-251">Razor Class Library</span></span>                          | [<span data-ttu-id="3c589-252">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="3c589-252">razorclasslib</span></span>](#razorclasslib) | <span data-ttu-id="3c589-253">[C#]</span><span class="sxs-lookup"><span data-stu-id="3c589-253">[C#]</span></span>         | <span data-ttu-id="3c589-254">Web/Razor/Biblioteca/Biblioteca de clases de Razor</span><span class="sxs-lookup"><span data-stu-id="3c589-254">Web/Razor/Library/Razor Class Library</span></span> | <span data-ttu-id="3c589-255">2.1</span><span class="sxs-lookup"><span data-stu-id="3c589-255">2.1</span></span>        |
| <span data-ttu-id="3c589-256">API web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="3c589-256">ASP.NET Core Web API</span></span>                         | [<span data-ttu-id="3c589-257">webapi</span><span class="sxs-lookup"><span data-stu-id="3c589-257">webapi</span></span>](#webapi)               | <span data-ttu-id="3c589-258">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="3c589-258">[C#], F#</span></span>     | <span data-ttu-id="3c589-259">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="3c589-259">Web/WebAPI</span></span>                            | <span data-ttu-id="3c589-260">1.0</span><span class="sxs-lookup"><span data-stu-id="3c589-260">1.0</span></span>        |
| <span data-ttu-id="3c589-261">Servicio gRPC de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="3c589-261">ASP.NET Core gRPC Service</span></span>                    | [<span data-ttu-id="3c589-262">grpc</span><span class="sxs-lookup"><span data-stu-id="3c589-262">grpc</span></span>](#web-others)             | <span data-ttu-id="3c589-263">[C#]</span><span class="sxs-lookup"><span data-stu-id="3c589-263">[C#]</span></span>         | <span data-ttu-id="3c589-264">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="3c589-264">Web/gRPC</span></span>                              | <span data-ttu-id="3c589-265">3.0</span><span class="sxs-lookup"><span data-stu-id="3c589-265">3.0</span></span>        |
| <span data-ttu-id="3c589-266">Archivo dotnet gitignore</span><span class="sxs-lookup"><span data-stu-id="3c589-266">dotnet gitignore file</span></span>                        | `gitignore`                     |              | <span data-ttu-id="3c589-267">Configuración</span><span class="sxs-lookup"><span data-stu-id="3c589-267">Config</span></span>                                | <span data-ttu-id="3c589-268">3.0</span><span class="sxs-lookup"><span data-stu-id="3c589-268">3.0</span></span>        |
| <span data-ttu-id="3c589-269">archivo global.json</span><span class="sxs-lookup"><span data-stu-id="3c589-269">global.json file</span></span>                             | [<span data-ttu-id="3c589-270">globaljson</span><span class="sxs-lookup"><span data-stu-id="3c589-270">globaljson</span></span>](#globaljson)       |              | <span data-ttu-id="3c589-271">Configuración</span><span class="sxs-lookup"><span data-stu-id="3c589-271">Config</span></span>                                | <span data-ttu-id="3c589-272">2.0</span><span class="sxs-lookup"><span data-stu-id="3c589-272">2.0</span></span>        |
| <span data-ttu-id="3c589-273">Configuración de NuGet</span><span class="sxs-lookup"><span data-stu-id="3c589-273">NuGet Config</span></span>                                 | `nugetconfig`                   |              | <span data-ttu-id="3c589-274">Configuración</span><span class="sxs-lookup"><span data-stu-id="3c589-274">Config</span></span>                                | <span data-ttu-id="3c589-275">1.0</span><span class="sxs-lookup"><span data-stu-id="3c589-275">1.0</span></span>        |
| <span data-ttu-id="3c589-276">Archivo de manifiesto de la herramienta local dotnet</span><span class="sxs-lookup"><span data-stu-id="3c589-276">Dotnet local tool manifest file</span></span>              | `tool-manifest`                 |              | <span data-ttu-id="3c589-277">Configuración</span><span class="sxs-lookup"><span data-stu-id="3c589-277">Config</span></span>                                | <span data-ttu-id="3c589-278">3.0</span><span class="sxs-lookup"><span data-stu-id="3c589-278">3.0</span></span>        |
| <span data-ttu-id="3c589-279">Configuración web</span><span class="sxs-lookup"><span data-stu-id="3c589-279">Web Config</span></span>                                   | `webconfig`                     |              | <span data-ttu-id="3c589-280">Configuración</span><span class="sxs-lookup"><span data-stu-id="3c589-280">Config</span></span>                                | <span data-ttu-id="3c589-281">1.0</span><span class="sxs-lookup"><span data-stu-id="3c589-281">1.0</span></span>        |
| <span data-ttu-id="3c589-282">Archivo de solución</span><span class="sxs-lookup"><span data-stu-id="3c589-282">Solution File</span></span>                                | `sln`                           |              | <span data-ttu-id="3c589-283">Soluciones</span><span class="sxs-lookup"><span data-stu-id="3c589-283">Solution</span></span>                              | <span data-ttu-id="3c589-284">1.0</span><span class="sxs-lookup"><span data-stu-id="3c589-284">1.0</span></span>        |
| <span data-ttu-id="3c589-285">Archivo de búfer de protocolo</span><span class="sxs-lookup"><span data-stu-id="3c589-285">Protocol Buffer File</span></span>                         | [<span data-ttu-id="3c589-286">proto</span><span class="sxs-lookup"><span data-stu-id="3c589-286">proto</span></span>](#namespace)             |              | <span data-ttu-id="3c589-287">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="3c589-287">Web/gRPC</span></span>                              | <span data-ttu-id="3c589-288">3.0</span><span class="sxs-lookup"><span data-stu-id="3c589-288">3.0</span></span>        |

## <a name="options"></a><span data-ttu-id="3c589-289">Opciones</span><span class="sxs-lookup"><span data-stu-id="3c589-289">Options</span></span>

- **`--dry-run`**

  <span data-ttu-id="3c589-290">Muestra un resumen de lo que sucedería si se ejecutara el comando determinado y el resultado fuera la creación de una plantilla.</span><span class="sxs-lookup"><span data-stu-id="3c589-290">Displays a summary of what would happen if the given command were run if it would result in a template creation.</span></span> <span data-ttu-id="3c589-291">Disponible a partir del SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="3c589-291">Available since .NET Core 2.2 SDK.</span></span>

- **`--force`**

  <span data-ttu-id="3c589-292">Fuerza la generación de contenido incluso aunque se vayan a cambiar los archivos existentes.</span><span class="sxs-lookup"><span data-stu-id="3c589-292">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="3c589-293">Es necesario si la plantilla elegida invalidará los archivos existentes en el directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="3c589-293">This is required when the template chosen would override existing files in the output directory.</span></span>

- **`-h|--help`**

  <span data-ttu-id="3c589-294">Imprime la ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="3c589-294">Prints out help for the command.</span></span> <span data-ttu-id="3c589-295">Puede invocarse para el propio comando `dotnet new` o para cualquier plantilla.</span><span class="sxs-lookup"><span data-stu-id="3c589-295">It can be invoked for the `dotnet new` command itself or for any template.</span></span> <span data-ttu-id="3c589-296">Por ejemplo: `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="3c589-296">For example, `dotnet new mvc --help`.</span></span>

- **`-i|--install <PATH|NUGET_ID>`**

  <span data-ttu-id="3c589-297">Instala un paquete de plantillas desde los parámetros `PATH` o `NUGET_ID` proporcionados.</span><span class="sxs-lookup"><span data-stu-id="3c589-297">Installs a template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="3c589-298">Si quiere instalar una versión preliminar de un paquete de plantilla, tendrá que especificar la versión en el formato de `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="3c589-298">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="3c589-299">De forma predeterminada, `dotnet new` pasa \* para la versión, que representa la última versión estable del paquete.</span><span class="sxs-lookup"><span data-stu-id="3c589-299">By default, `dotnet new` passes \* for the version, which represents the latest stable package version.</span></span> <span data-ttu-id="3c589-300">Vea un ejemplo en la sección [Ejemplos](#examples).</span><span class="sxs-lookup"><span data-stu-id="3c589-300">See an example in the [Examples](#examples) section.</span></span>
  
  <span data-ttu-id="3c589-301">Si ya hay instalada una versión de la plantilla al ejecutar este comando, la plantilla se actualizará a la versión especificada o a la versión estable más reciente si no se ha especificado ninguna versión.</span><span class="sxs-lookup"><span data-stu-id="3c589-301">If a version of the template was already installed when you run this command, the template will be updated to the specified version, or to the latest stable version if no version was specified.</span></span>

  <span data-ttu-id="3c589-302">Para obtener información sobre cómo crear plantillas personalizadas, consulte [Plantillas personalizadas para dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="3c589-302">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

- **`-l|--list`**

  <span data-ttu-id="3c589-303">Muestra las plantillas que contienen el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="3c589-303">Lists templates containing the specified name.</span></span> <span data-ttu-id="3c589-304">Si no se especifica ningún nombre, enumera todas las plantillas.</span><span class="sxs-lookup"><span data-stu-id="3c589-304">If no name is specified, lists all templates.</span></span>

- **`-lang|--language {C#|F#|VB}`**

  <span data-ttu-id="3c589-305">El lenguaje de la plantilla que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="3c589-305">The language of the template to create.</span></span> <span data-ttu-id="3c589-306">El lenguaje aceptado cambia según la plantilla (vea los valores predeterminados en la sección [argumentos](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="3c589-306">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="3c589-307">No es válido para algunas plantillas.</span><span class="sxs-lookup"><span data-stu-id="3c589-307">Not valid for some templates.</span></span>

  > [!NOTE]
  > <span data-ttu-id="3c589-308">Algunos shells interpretan `#` como un carácter especial.</span><span class="sxs-lookup"><span data-stu-id="3c589-308">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="3c589-309">En esos casos, incluya el valor del parámetro de lenguaje entre comillas.</span><span class="sxs-lookup"><span data-stu-id="3c589-309">In those cases, enclose the language parameter value in quotes.</span></span> <span data-ttu-id="3c589-310">Por ejemplo: `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="3c589-310">For example, `dotnet new console -lang "F#"`.</span></span>

- **`-n|--name <OUTPUT_NAME>`**

  <span data-ttu-id="3c589-311">El nombre de la salida creada.</span><span class="sxs-lookup"><span data-stu-id="3c589-311">The name for the created output.</span></span> <span data-ttu-id="3c589-312">Si no se especifica ningún nombre, se usa el nombre del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="3c589-312">If no name is specified, the name of the current directory is used.</span></span>

- **`--nuget-source <SOURCE>`**

  <span data-ttu-id="3c589-313">Especifica un origen de NuGet para usarlo durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="3c589-313">Specifies a NuGet source to use during install.</span></span> <span data-ttu-id="3c589-314">Disponible a partir del SDK de .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="3c589-314">Available since .NET Core 2.1 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="3c589-315">La ubicación para colocar la salida generada.</span><span class="sxs-lookup"><span data-stu-id="3c589-315">Location to place the generated output.</span></span> <span data-ttu-id="3c589-316">El valor predeterminado es el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="3c589-316">The default is the current directory.</span></span>

- **`--type <TYPE>`**

  <span data-ttu-id="3c589-317">Filtra plantillas en función de los tipos disponibles.</span><span class="sxs-lookup"><span data-stu-id="3c589-317">Filters templates based on available types.</span></span> <span data-ttu-id="3c589-318">Los valores predefinidos son `project`, `item` y `other`.</span><span class="sxs-lookup"><span data-stu-id="3c589-318">Predefined values are `project`, `item`, and `other`.</span></span>

- **`-u|--uninstall [PATH|NUGET_ID]`**

  <span data-ttu-id="3c589-319">Desinstala un paquete de plantillas en los parámetros `PATH` o `NUGET_ID` proporcionados.</span><span class="sxs-lookup"><span data-stu-id="3c589-319">Uninstalls a template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="3c589-320">Si no se especifica el valor `<PATH|NUGET_ID>`, se muestran todos los paquetes de plantillas instalados actualmente y sus plantillas asociadas.</span><span class="sxs-lookup"><span data-stu-id="3c589-320">When the `<PATH|NUGET_ID>` value isn't specified, all currently installed template packs and their associated templates are displayed.</span></span> <span data-ttu-id="3c589-321">Al especificar `NUGET_ID`, no incluya el número de versión.</span><span class="sxs-lookup"><span data-stu-id="3c589-321">When specifying `NUGET_ID`, don't include the version number.</span></span>

  <span data-ttu-id="3c589-322">Si no especifica un parámetro en esta opción, el comando muestra las plantillas instaladas y detalles sobre ellas.</span><span class="sxs-lookup"><span data-stu-id="3c589-322">If you don't specify a parameter to this option, the command lists the installed templates and details about them.</span></span>

  > [!NOTE]
  > <span data-ttu-id="3c589-323">Para desinstalar una plantilla mediante `PATH`, debe usar el nombre completo de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="3c589-323">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="3c589-324">Por ejemplo, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* funcionará, pero *./GarciaSoftware.ConsoleTemplate.CSharp* desde la carpeta contenedora no lo hará.</span><span class="sxs-lookup"><span data-stu-id="3c589-324">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
  > <span data-ttu-id="3c589-325">No incluya ninguna barra diagonal para finalizar el directorio en la ruta de acceso a la plantilla.</span><span class="sxs-lookup"><span data-stu-id="3c589-325">Don't include a final terminating directory slash on your template path.</span></span>

- **`--update-apply`**

  <span data-ttu-id="3c589-326">Comprueba si hay actualizaciones disponibles de los paquetes de plantillas instalados actualmente y las instala.</span><span class="sxs-lookup"><span data-stu-id="3c589-326">Checks if there are updates available for the template packs that are currently installed and installs them.</span></span> <span data-ttu-id="3c589-327">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="3c589-327">Available since .NET Core 3.0 SDK.</span></span>

- **`--update-check`**

  <span data-ttu-id="3c589-328">Comprueba si hay actualizaciones disponibles de los paquetes de plantillas instalados actualmente.</span><span class="sxs-lookup"><span data-stu-id="3c589-328">Checks if there are updates available for the template packs that are currently installed.</span></span> <span data-ttu-id="3c589-329">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="3c589-329">Available since .NET Core 3.0 SDK.</span></span>

## <a name="template-options"></a><span data-ttu-id="3c589-330">Opciones de plantilla</span><span class="sxs-lookup"><span data-stu-id="3c589-330">Template options</span></span>

<span data-ttu-id="3c589-331">Cada plantilla de proyecto puede tener opciones adicionales disponibles.</span><span class="sxs-lookup"><span data-stu-id="3c589-331">Each project template may have additional options available.</span></span> <span data-ttu-id="3c589-332">Las plantillas principales tienen las siguientes opciones adicionales:</span><span class="sxs-lookup"><span data-stu-id="3c589-332">The core templates have the following additional options:</span></span>

### <a name="console"></a><span data-ttu-id="3c589-333">consola</span><span class="sxs-lookup"><span data-stu-id="3c589-333">console</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="3c589-334">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="3c589-334">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="3c589-335">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="3c589-335">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="3c589-336">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="3c589-336">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="3c589-337">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="3c589-337">SDK version</span></span> | <span data-ttu-id="3c589-338">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="3c589-338">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="3c589-339">3.1</span><span class="sxs-lookup"><span data-stu-id="3c589-339">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="3c589-340">3.0</span><span class="sxs-lookup"><span data-stu-id="3c589-340">3.0</span></span>         | `netcoreapp3.0` |

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="3c589-341">Establece la propiedad `LangVersion` en el archivo del proyecto creado.</span><span class="sxs-lookup"><span data-stu-id="3c589-341">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="3c589-342">Por ejemplo, use `--langVersion 7.3` para emplear C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="3c589-342">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="3c589-343">No es compatible con F#.</span><span class="sxs-lookup"><span data-stu-id="3c589-343">Not supported for F#.</span></span> <span data-ttu-id="3c589-344">Disponible a partir del SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="3c589-344">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="3c589-345">Para obtener una lista de las versiones predeterminadas de C#, vea [Valores predeterminados](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="3c589-345">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="3c589-346">Si se especifica, no se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c589-346">If specified, doesn't execute an implicit restore during project creation.</span></span> <span data-ttu-id="3c589-347">Disponible a partir del SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="3c589-347">Available since .NET Core 2.2 SDK.</span></span>

***

### <a name="classlib"></a><span data-ttu-id="3c589-348">classlib</span><span class="sxs-lookup"><span data-stu-id="3c589-348">classlib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="3c589-349">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="3c589-349">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="3c589-350">Valores: `netcoreapp<version>` para crear una biblioteca de clases de .NET Core o `netstandard<version>` para crear una biblioteca de clases de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="3c589-350">Values: `netcoreapp<version>` to create a .NET Core Class Library or `netstandard<version>` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="3c589-351">El valor predeterminado es `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="3c589-351">The default value is `netstandard2.0`.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="3c589-352">Establece la propiedad `LangVersion` en el archivo del proyecto creado.</span><span class="sxs-lookup"><span data-stu-id="3c589-352">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="3c589-353">Por ejemplo, use `--langVersion 7.3` para emplear C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="3c589-353">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="3c589-354">No es compatible con F#.</span><span class="sxs-lookup"><span data-stu-id="3c589-354">Not supported for F#.</span></span> <span data-ttu-id="3c589-355">Disponible a partir del SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="3c589-355">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="3c589-356">Para obtener una lista de las versiones predeterminadas de C#, vea [Valores predeterminados](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="3c589-356">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="3c589-357">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c589-357">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="wpf-wpflib-wpfcustomcontrollib-wpfusercontrollib"></a><a name="wpf"></a> <span data-ttu-id="3c589-358">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="3c589-358">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="3c589-359">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="3c589-359">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="3c589-360">El valor predeterminado es `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="3c589-360">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="3c589-361">Disponible a partir del SDK de .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="3c589-361">Available since .NET Core 3.1 SDK.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="3c589-362">Establece la propiedad `LangVersion` en el archivo del proyecto creado.</span><span class="sxs-lookup"><span data-stu-id="3c589-362">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="3c589-363">Por ejemplo, use `--langVersion 7.3` para emplear C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="3c589-363">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="3c589-364">Para obtener una lista de las versiones predeterminadas de C#, vea [Valores predeterminados](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="3c589-364">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="3c589-365">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c589-365">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="winforms-winformslib"></a><a name="winforms"></a> <span data-ttu-id="3c589-366">winforms, winformslib</span><span class="sxs-lookup"><span data-stu-id="3c589-366">winforms, winformslib</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="3c589-367">Establece la propiedad `LangVersion` en el archivo del proyecto creado.</span><span class="sxs-lookup"><span data-stu-id="3c589-367">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="3c589-368">Por ejemplo, use `--langVersion 7.3` para emplear C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="3c589-368">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="3c589-369">Para obtener una lista de las versiones predeterminadas de C#, vea [Valores predeterminados](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="3c589-369">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="3c589-370">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c589-370">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="worker-grpc"></a><a name="web-others"></a> <span data-ttu-id="3c589-371">worker, grpc</span><span class="sxs-lookup"><span data-stu-id="3c589-371">worker, grpc</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="3c589-372">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="3c589-372">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="3c589-373">El valor predeterminado es `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="3c589-373">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="3c589-374">Disponible a partir del SDK de .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="3c589-374">Available since .NET Core 3.1 SDK.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="3c589-375">Excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="3c589-375">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="3c589-376">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c589-376">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="mstest-xunit"></a><a name="test"></a> <span data-ttu-id="3c589-377">mstest, xunit</span><span class="sxs-lookup"><span data-stu-id="3c589-377">mstest, xunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="3c589-378">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="3c589-378">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="3c589-379">Opción disponible a partir del SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="3c589-379">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="3c589-380">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="3c589-380">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="3c589-381">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="3c589-381">SDK version</span></span> | <span data-ttu-id="3c589-382">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="3c589-382">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="3c589-383">3.1</span><span class="sxs-lookup"><span data-stu-id="3c589-383">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="3c589-384">3.0</span><span class="sxs-lookup"><span data-stu-id="3c589-384">3.0</span></span>         | `netcoreapp3.0` |

- **`-p|--enable-pack`**

  <span data-ttu-id="3c589-385">Habilita el empaquetado del proyecto mediante [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="3c589-385">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="3c589-386">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c589-386">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="nunit"></a><span data-ttu-id="3c589-387">nunit</span><span class="sxs-lookup"><span data-stu-id="3c589-387">nunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="3c589-388">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="3c589-388">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="3c589-389">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="3c589-389">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="3c589-390">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="3c589-390">SDK version</span></span> | <span data-ttu-id="3c589-391">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="3c589-391">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="3c589-392">3.1</span><span class="sxs-lookup"><span data-stu-id="3c589-392">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="3c589-393">3.0</span><span class="sxs-lookup"><span data-stu-id="3c589-393">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="3c589-394">2.2</span><span class="sxs-lookup"><span data-stu-id="3c589-394">2.2</span></span>         | `netcoreapp2.2` |
  | <span data-ttu-id="3c589-395">2.1</span><span class="sxs-lookup"><span data-stu-id="3c589-395">2.1</span></span>         | `netcoreapp2.1` |

- **`-p|--enable-pack`**

  <span data-ttu-id="3c589-396">Habilita el empaquetado del proyecto mediante [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="3c589-396">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="3c589-397">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c589-397">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="page"></a><span data-ttu-id="3c589-398">página</span><span class="sxs-lookup"><span data-stu-id="3c589-398">page</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="3c589-399">Espacio de nombres del código generado.</span><span class="sxs-lookup"><span data-stu-id="3c589-399">Namespace for the generated code.</span></span> <span data-ttu-id="3c589-400">El valor predeterminado es `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="3c589-400">The default value is `MyApp.Namespace`.</span></span>

- **`-np|--no-pagemodel`**

  <span data-ttu-id="3c589-401">Crea la página sin PageModel.</span><span class="sxs-lookup"><span data-stu-id="3c589-401">Creates the page without a PageModel.</span></span>

***

### <a name="viewimports-proto"></a><a name="namespace"></a> <span data-ttu-id="3c589-402">viewimports, proto</span><span class="sxs-lookup"><span data-stu-id="3c589-402">viewimports, proto</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="3c589-403">Espacio de nombres del código generado.</span><span class="sxs-lookup"><span data-stu-id="3c589-403">Namespace for the generated code.</span></span> <span data-ttu-id="3c589-404">El valor predeterminado es `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="3c589-404">The default value is `MyApp.Namespace`.</span></span>

***

### <a name="blazorserver"></a><span data-ttu-id="3c589-405">blazorserver</span><span class="sxs-lookup"><span data-stu-id="3c589-405">blazorserver</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="3c589-406">Tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="3c589-406">The type of authentication to use.</span></span> <span data-ttu-id="3c589-407">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="3c589-407">The possible values are:</span></span>

  - <span data-ttu-id="3c589-408">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="3c589-408">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="3c589-409">`Individual`: autenticación individual.</span><span class="sxs-lookup"><span data-stu-id="3c589-409">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="3c589-410">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="3c589-410">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="3c589-411">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="3c589-411">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="3c589-412">`MultiOrg`: autenticación organizativa para varios inquilinos.</span><span class="sxs-lookup"><span data-stu-id="3c589-412">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="3c589-413">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="3c589-413">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="3c589-414">Instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="3c589-414">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="3c589-415">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="3c589-415">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="3c589-416">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="3c589-416">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="3c589-417">Identificador de la directiva de registro e inicio de sesión de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c589-417">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="3c589-418">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="3c589-418">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="3c589-419">Identificador de la directiva de restablecimiento de contraseñas de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c589-419">The reset password policy ID for this project.</span></span> <span data-ttu-id="3c589-420">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="3c589-420">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="3c589-421">Identificador de la directiva de edición de perfiles de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c589-421">The edit profile policy ID for this project.</span></span> <span data-ttu-id="3c589-422">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="3c589-422">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="3c589-423">Instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="3c589-423">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="3c589-424">Úsela con las autenticaciones `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="3c589-424">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="3c589-425">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="3c589-425">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="3c589-426">Identificador de cliente de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c589-426">The Client ID for this project.</span></span> <span data-ttu-id="3c589-427">Úsela con las autenticaciones `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="3c589-427">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="3c589-428">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="3c589-428">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="3c589-429">Dominio del inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="3c589-429">The domain for the directory tenant.</span></span> <span data-ttu-id="3c589-430">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="3c589-430">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="3c589-431">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="3c589-431">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="3c589-432">Identificador de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="3c589-432">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="3c589-433">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="3c589-433">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="3c589-434">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="3c589-434">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="3c589-435">Ruta de acceso de solicitud de la ruta de acceso de la base de la aplicación del URI de redirección.</span><span class="sxs-lookup"><span data-stu-id="3c589-435">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="3c589-436">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="3c589-436">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="3c589-437">El valor predeterminado es `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="3c589-437">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="3c589-438">Concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="3c589-438">Allows this application read-access to the directory.</span></span> <span data-ttu-id="3c589-439">Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="3c589-439">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="3c589-440">Excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="3c589-440">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="3c589-441">Desactiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="3c589-441">Turns off HTTPS.</span></span> <span data-ttu-id="3c589-442">Esta opción solo se aplica si no se usan `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg` en `--auth`.</span><span class="sxs-lookup"><span data-stu-id="3c589-442">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="3c589-443">Especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="3c589-443">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="3c589-444">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="3c589-444">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--no-restore`**

  <span data-ttu-id="3c589-445">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c589-445">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="web"></a><span data-ttu-id="3c589-446">web</span><span class="sxs-lookup"><span data-stu-id="3c589-446">web</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="3c589-447">Excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="3c589-447">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="3c589-448">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="3c589-448">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="3c589-449">Opción no disponible en el SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="3c589-449">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="3c589-450">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="3c589-450">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="3c589-451">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="3c589-451">SDK version</span></span> | <span data-ttu-id="3c589-452">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="3c589-452">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="3c589-453">3.1</span><span class="sxs-lookup"><span data-stu-id="3c589-453">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="3c589-454">3.0</span><span class="sxs-lookup"><span data-stu-id="3c589-454">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="3c589-455">2.1</span><span class="sxs-lookup"><span data-stu-id="3c589-455">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="3c589-456">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c589-456">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="3c589-457">Desactiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="3c589-457">Turns off HTTPS.</span></span>

***

### <a name="mvc-webapp"></a><a name="web-options"></a> <span data-ttu-id="3c589-458">mvc, webapp</span><span class="sxs-lookup"><span data-stu-id="3c589-458">mvc, webapp</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="3c589-459">Tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="3c589-459">The type of authentication to use.</span></span> <span data-ttu-id="3c589-460">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="3c589-460">The possible values are:</span></span>

  - <span data-ttu-id="3c589-461">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="3c589-461">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="3c589-462">`Individual`: autenticación individual.</span><span class="sxs-lookup"><span data-stu-id="3c589-462">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="3c589-463">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="3c589-463">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="3c589-464">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="3c589-464">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="3c589-465">`MultiOrg`: autenticación organizativa para varios inquilinos.</span><span class="sxs-lookup"><span data-stu-id="3c589-465">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="3c589-466">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="3c589-466">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="3c589-467">Instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="3c589-467">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="3c589-468">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="3c589-468">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="3c589-469">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="3c589-469">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="3c589-470">Identificador de la directiva de registro e inicio de sesión de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c589-470">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="3c589-471">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="3c589-471">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="3c589-472">Identificador de la directiva de restablecimiento de contraseñas de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c589-472">The reset password policy ID for this project.</span></span> <span data-ttu-id="3c589-473">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="3c589-473">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="3c589-474">Identificador de la directiva de edición de perfiles de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c589-474">The edit profile policy ID for this project.</span></span> <span data-ttu-id="3c589-475">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="3c589-475">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="3c589-476">Instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="3c589-476">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="3c589-477">Úsela con las autenticaciones `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="3c589-477">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="3c589-478">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="3c589-478">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="3c589-479">Identificador de cliente de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c589-479">The Client ID for this project.</span></span> <span data-ttu-id="3c589-480">Úsela con las autenticaciones `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="3c589-480">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="3c589-481">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="3c589-481">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="3c589-482">Dominio del inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="3c589-482">The domain for the directory tenant.</span></span> <span data-ttu-id="3c589-483">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="3c589-483">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="3c589-484">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="3c589-484">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="3c589-485">Identificador de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="3c589-485">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="3c589-486">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="3c589-486">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="3c589-487">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="3c589-487">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="3c589-488">Ruta de acceso de solicitud de la ruta de acceso de la base de la aplicación del URI de redirección.</span><span class="sxs-lookup"><span data-stu-id="3c589-488">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="3c589-489">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="3c589-489">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="3c589-490">El valor predeterminado es `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="3c589-490">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="3c589-491">Concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="3c589-491">Allows this application read-access to the directory.</span></span> <span data-ttu-id="3c589-492">Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="3c589-492">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="3c589-493">Excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="3c589-493">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="3c589-494">Desactiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="3c589-494">Turns off HTTPS.</span></span> <span data-ttu-id="3c589-495">Esta opción solo se aplica si no se usan `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="3c589-495">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="3c589-496">Especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="3c589-496">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="3c589-497">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="3c589-497">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="3c589-498">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="3c589-498">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="3c589-499">Opción disponible a partir del SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="3c589-499">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="3c589-500">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="3c589-500">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="3c589-501">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="3c589-501">SDK version</span></span> | <span data-ttu-id="3c589-502">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="3c589-502">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="3c589-503">3.1</span><span class="sxs-lookup"><span data-stu-id="3c589-503">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="3c589-504">3.0</span><span class="sxs-lookup"><span data-stu-id="3c589-504">3.0</span></span>         | `netcoreapp3.0` |

- **`--no-restore`**

  <span data-ttu-id="3c589-505">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c589-505">Doesn't execute an implicit restore during project creation.</span></span>

- **`--use-browserlink`**

  <span data-ttu-id="3c589-506">Incluye BrowserLink en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c589-506">Includes BrowserLink in the project.</span></span> <span data-ttu-id="3c589-507">Opción no disponible en el SDK de .NET Core 2.2 y 3.1.</span><span class="sxs-lookup"><span data-stu-id="3c589-507">Option not available in .NET Core 2.2 and 3.1 SDK.</span></span>

- **`-rrc|--razor-runtime-compilation`**

  <span data-ttu-id="3c589-508">Determina si el proyecto está configurado para usar la [compilación en tiempo de ejecución de Razor](/aspnet/core/mvc/views/view-compilation#runtime-compilation) en las compilaciones de depuración.</span><span class="sxs-lookup"><span data-stu-id="3c589-508">Determines if the project is configured to use [Razor runtime compilation](/aspnet/core/mvc/views/view-compilation#runtime-compilation) in Debug builds.</span></span> <span data-ttu-id="3c589-509">Opción disponible a partir del SDK de .NET Core 3.1.201.</span><span class="sxs-lookup"><span data-stu-id="3c589-509">Option available since .NET Core 3.1.201 SDK.</span></span>

***

### <a name="angular-react"></a><a name="spa"></a> <span data-ttu-id="3c589-510">angular, react</span><span class="sxs-lookup"><span data-stu-id="3c589-510">angular, react</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="3c589-511">Tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="3c589-511">The type of authentication to use.</span></span> <span data-ttu-id="3c589-512">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="3c589-512">Available since .NET Core 3.0 SDK.</span></span>
  
  <span data-ttu-id="3c589-513">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="3c589-513">The possible values are:</span></span>

  - <span data-ttu-id="3c589-514">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="3c589-514">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="3c589-515">`Individual`: autenticación individual.</span><span class="sxs-lookup"><span data-stu-id="3c589-515">`Individual` - Individual authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="3c589-516">Excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="3c589-516">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="3c589-517">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c589-517">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="3c589-518">Desactiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="3c589-518">Turns off HTTPS.</span></span> <span data-ttu-id="3c589-519">Esta opción solo se aplica si la autenticación es `None`.</span><span class="sxs-lookup"><span data-stu-id="3c589-519">This option only applies if authentication is `None`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="3c589-520">Especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="3c589-520">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="3c589-521">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="3c589-521">Only applies to `Individual` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="3c589-522">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="3c589-522">Available since .NET Core 3.0 SDK.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="3c589-523">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="3c589-523">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="3c589-524">Opción no disponible en el SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="3c589-524">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="3c589-525">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="3c589-525">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="3c589-526">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="3c589-526">SDK version</span></span> | <span data-ttu-id="3c589-527">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="3c589-527">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="3c589-528">3.1</span><span class="sxs-lookup"><span data-stu-id="3c589-528">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="3c589-529">3.0</span><span class="sxs-lookup"><span data-stu-id="3c589-529">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="3c589-530">2.1</span><span class="sxs-lookup"><span data-stu-id="3c589-530">2.1</span></span>         | `netcoreapp2.0` |

***

### <a name="reactredux"></a><span data-ttu-id="3c589-531">reactredux</span><span class="sxs-lookup"><span data-stu-id="3c589-531">reactredux</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="3c589-532">Excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="3c589-532">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="3c589-533">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="3c589-533">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="3c589-534">Opción no disponible en el SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="3c589-534">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="3c589-535">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="3c589-535">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="3c589-536">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="3c589-536">SDK version</span></span> | <span data-ttu-id="3c589-537">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="3c589-537">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="3c589-538">3.1</span><span class="sxs-lookup"><span data-stu-id="3c589-538">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="3c589-539">3.0</span><span class="sxs-lookup"><span data-stu-id="3c589-539">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="3c589-540">2.1</span><span class="sxs-lookup"><span data-stu-id="3c589-540">2.1</span></span>         | `netcoreapp2.0` |

- **`--no-restore`**

  <span data-ttu-id="3c589-541">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c589-541">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="3c589-542">Desactiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="3c589-542">Turns off HTTPS.</span></span>

***

### <a name="razorclasslib"></a><span data-ttu-id="3c589-543">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="3c589-543">razorclasslib</span></span>

- **`--no-restore`**

  <span data-ttu-id="3c589-544">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c589-544">Doesn't execute an implicit restore during project creation.</span></span>

- **`-s|--support-pages-and-views`**

  <span data-ttu-id="3c589-545">Permite agregar vistas y páginas de Razor tradicionales además de los componentes a esta biblioteca.</span><span class="sxs-lookup"><span data-stu-id="3c589-545">Supports adding traditional Razor pages and Views in addition to components to this library.</span></span> <span data-ttu-id="3c589-546">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="3c589-546">Available since .NET Core 3.0 SDK.</span></span>

***
  
### <a name="webapi"></a><span data-ttu-id="3c589-547">webapi</span><span class="sxs-lookup"><span data-stu-id="3c589-547">webapi</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="3c589-548">Tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="3c589-548">The type of authentication to use.</span></span> <span data-ttu-id="3c589-549">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="3c589-549">The possible values are:</span></span>

  - <span data-ttu-id="3c589-550">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="3c589-550">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="3c589-551">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="3c589-551">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="3c589-552">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="3c589-552">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="3c589-553">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="3c589-553">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="3c589-554">Instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="3c589-554">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="3c589-555">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="3c589-555">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="3c589-556">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="3c589-556">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="3c589-557">Identificador de la directiva de registro e inicio de sesión de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c589-557">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="3c589-558">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="3c589-558">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="3c589-559">Instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="3c589-559">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="3c589-560">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="3c589-560">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="3c589-561">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="3c589-561">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="3c589-562">Identificador de cliente de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c589-562">The Client ID for this project.</span></span> <span data-ttu-id="3c589-563">Úsela con las autenticaciones `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="3c589-563">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="3c589-564">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="3c589-564">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="3c589-565">Dominio del inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="3c589-565">The domain for the directory tenant.</span></span> <span data-ttu-id="3c589-566">Úsela con las autenticaciones `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="3c589-566">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="3c589-567">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="3c589-567">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="3c589-568">Identificador de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="3c589-568">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="3c589-569">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="3c589-569">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="3c589-570">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="3c589-570">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="3c589-571">Concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="3c589-571">Allows this application read-access to the directory.</span></span> <span data-ttu-id="3c589-572">Solo se aplica a la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="3c589-572">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="3c589-573">Excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="3c589-573">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="3c589-574">Desactiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="3c589-574">Turns off HTTPS.</span></span> <span data-ttu-id="3c589-575">`app.UseHsts` y `app.UseHttpsRedirection` no se agregan a `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="3c589-575">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="3c589-576">Esta opción solo se aplica si no se usan `IndividualB2C` o `SingleOrg` en la autenticación.</span><span class="sxs-lookup"><span data-stu-id="3c589-576">This option only applies if `IndividualB2C` or `SingleOrg` aren't being used for authentication.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="3c589-577">Especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="3c589-577">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="3c589-578">Solo se aplica a la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="3c589-578">Only applies to `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="3c589-579">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="3c589-579">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="3c589-580">Opción no disponible en el SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="3c589-580">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="3c589-581">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="3c589-581">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="3c589-582">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="3c589-582">SDK version</span></span> | <span data-ttu-id="3c589-583">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="3c589-583">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="3c589-584">3.1</span><span class="sxs-lookup"><span data-stu-id="3c589-584">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="3c589-585">3.0</span><span class="sxs-lookup"><span data-stu-id="3c589-585">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="3c589-586">2.1</span><span class="sxs-lookup"><span data-stu-id="3c589-586">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="3c589-587">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="3c589-587">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="globaljson"></a><span data-ttu-id="3c589-588">globaljson</span><span class="sxs-lookup"><span data-stu-id="3c589-588">globaljson</span></span>

- **`--sdk-version <VERSION_NUMBER>`**

  <span data-ttu-id="3c589-589">Especifica la versión del SDK de .NET Core que se usará en el archivo *global.json*.</span><span class="sxs-lookup"><span data-stu-id="3c589-589">Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

***

## <a name="examples"></a><span data-ttu-id="3c589-590">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="3c589-590">Examples</span></span>

- <span data-ttu-id="3c589-591">Creación de un proyecto de aplicación de consola de C# mediante la especificación del nombre de plantilla:</span><span class="sxs-lookup"><span data-stu-id="3c589-591">Create a C# console application project by specifying the template name:</span></span>

  ```dotnetcli
  dotnet new "Console Application"
  ```

- <span data-ttu-id="3c589-592">Creación de un proyecto de aplicación de consola con F# en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="3c589-592">Create an F# console application project in the current directory:</span></span>

  ```dotnetcli
  dotnet new console -lang "F#"
  ```

- <span data-ttu-id="3c589-593">Creación de un proyecto de biblioteca de clases de .NET Standard en el directorio especificado:</span><span class="sxs-lookup"><span data-stu-id="3c589-593">Create a .NET Standard class library project in the specified directory:</span></span>

  ```dotnetcli
  dotnet new classlib -lang VB -o MyLibrary
  ```

- <span data-ttu-id="3c589-594">Creación de un proyecto MVC de ASP.NET Core C# en el directorio actual sin autenticación:</span><span class="sxs-lookup"><span data-stu-id="3c589-594">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

  ```dotnetcli
  dotnet new mvc -au None
  ```

- <span data-ttu-id="3c589-595">Creación de un proyecto de xUnit:</span><span class="sxs-lookup"><span data-stu-id="3c589-595">Create a new xUnit project:</span></span>

  ```dotnetcli
  dotnet new xunit
  ```

- <span data-ttu-id="3c589-596">Enumeración de todas las plantillas disponibles en las plantillas de aplicación de página única (SPA):</span><span class="sxs-lookup"><span data-stu-id="3c589-596">List all templates available for Single Page Application (SPA) templates:</span></span>

  ```dotnetcli
  dotnet new spa -l
  ```

- <span data-ttu-id="3c589-597">Enumeración de todas las plantillas que coinciden con la subcadena *we*.</span><span class="sxs-lookup"><span data-stu-id="3c589-597">List all templates matching the *we* substring.</span></span> <span data-ttu-id="3c589-598">No se encuentra ninguna coincidencia exacta, por lo que se ejecuta la coincidencia de subcadena con las columnas de nombre corto y de nombre.</span><span class="sxs-lookup"><span data-stu-id="3c589-598">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

  ```dotnetcli
  dotnet new we -l
  ```

- <span data-ttu-id="3c589-599">Intento de invocar a la plantilla que coincide con *ng*.</span><span class="sxs-lookup"><span data-stu-id="3c589-599">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="3c589-600">Si no se puede determinar una única coincidencia, se enumeran las plantillas que son coincidencias parciales.</span><span class="sxs-lookup"><span data-stu-id="3c589-600">If a single match can't be determined, list the templates that are partial matches.</span></span>

  ```dotnetcli
  dotnet new ng
  ```

- <span data-ttu-id="3c589-601">Instalación de la versión 2.0 de las plantillas de SPA de ASP.NET Core:</span><span class="sxs-lookup"><span data-stu-id="3c589-601">Install version 2.0 of the SPA templates for ASP.NET Core:</span></span>

  ```dotnetcli
  dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0
  ```

- <span data-ttu-id="3c589-602">Enumeración de las plantillas instaladas y detalles sobre ellas, incluido cómo desinstalarlas:</span><span class="sxs-lookup"><span data-stu-id="3c589-602">List the installed templates and details about them, including how to uninstall them:</span></span>

  ```dotnetcli
  dotnet new -u
  ```

- <span data-ttu-id="3c589-603">Creación de un archivo *global.json* en el directorio actual al establecer la versión del SDK en 3.1.101:</span><span class="sxs-lookup"><span data-stu-id="3c589-603">Create a *global.json* in the current directory setting the SDK version to 3.1.101:</span></span>

  ```dotnetcli
  dotnet new globaljson --sdk-version 3.1.101
  ```

## <a name="see-also"></a><span data-ttu-id="3c589-604">Vea también</span><span class="sxs-lookup"><span data-stu-id="3c589-604">See also</span></span>

- [<span data-ttu-id="3c589-605">Plantillas personalizadas para dotnet new</span><span class="sxs-lookup"><span data-stu-id="3c589-605">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="3c589-606">Creación de una plantilla personalizada para dotnet new</span><span class="sxs-lookup"><span data-stu-id="3c589-606">Create a custom template for dotnet new</span></span>](../tutorials/cli-templates-create-item-template.md)
- [<span data-ttu-id="3c589-607">Repositorio de GitHub dotnet/dotnet-template-samples</span><span class="sxs-lookup"><span data-stu-id="3c589-607">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- <span data-ttu-id="3c589-608">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new) (Plantillas disponibles para dotnet new)</span><span class="sxs-lookup"><span data-stu-id="3c589-608">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)</span></span>
