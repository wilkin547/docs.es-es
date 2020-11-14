---
title: Comando dotnet new
description: El comando dotnet new crea proyectos de .NET Core basados en la plantilla especificada.
no-loc:
- ':::no-loc(Blazor):::'
- ':::no-loc(WebAssembly):::'
ms.date: 09/04/2020
ms.openlocfilehash: 2ee06c37cd950f3b9771db2f30fe353435641d67
ms.sourcegitcommit: 48466b8fb7332ececff5dc388f19f6b3ff503dd4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/05/2020
ms.locfileid: "93400596"
---
# <a name="dotnet-new"></a><span data-ttu-id="9cfb0-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="9cfb0-103">dotnet new</span></span>

<span data-ttu-id="9cfb0-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.0 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="9cfb0-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="9cfb0-105">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="9cfb0-105">Name</span></span>

<span data-ttu-id="9cfb0-106">`dotnet new`: crea un nuevo proyecto, archivo de configuración o solución según la plantilla especificada.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="9cfb0-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="9cfb0-107">Synopsis</span></span>

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install {PATH|NUGET_ID}]
    [-lang|--language {"C#"|"F#"|VB}] [-n|--name <OUTPUT_NAME>]
    [--nuget-source <SOURCE>] [-o|--output <OUTPUT_DIRECTORY>]
    [-u|--uninstall] [--update-apply] [--update-check] [Template options]

dotnet new <TEMPLATE> [-l|--list] [--type <TYPE>]

dotnet new -h|--help
```

## <a name="description"></a><span data-ttu-id="9cfb0-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="9cfb0-108">Description</span></span>

<span data-ttu-id="9cfb0-109">El comando `dotnet new` crea un proyecto de .NET Core u otros artefactos basados en una plantilla.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-109">The `dotnet new` command creates a .NET Core project or other artifacts based on a template.</span></span>

<span data-ttu-id="9cfb0-110">El comando llama al [motor de plantillas](https://github.com/dotnet/templating) para crear los artefactos en el disco basándose en las opciones y la plantilla especificadas.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-110">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="9cfb0-111">Restauración implícita</span><span class="sxs-lookup"><span data-stu-id="9cfb0-111">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="9cfb0-112">Argumentos</span><span class="sxs-lookup"><span data-stu-id="9cfb0-112">Arguments</span></span>

- **`TEMPLATE`**

  <span data-ttu-id="9cfb0-113">La plantilla de la que se va a crear una instancia cuando se invoca el comando.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-113">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="9cfb0-114">Cada plantilla puede tener opciones específicas que puede pasar.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-114">Each template might have specific options you can pass.</span></span> <span data-ttu-id="9cfb0-115">Para obtener más información, vea [Opciones de plantilla](#template-options).</span><span class="sxs-lookup"><span data-stu-id="9cfb0-115">For more information, see [Template options](#template-options).</span></span>

  <span data-ttu-id="9cfb0-116">Puede ejecutar `dotnet new --list` o `dotnet new -l` para ver una lista de todas las plantillas instaladas.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-116">You can run `dotnet new --list` or `dotnet new -l` to see a list of all installed templates.</span></span> <span data-ttu-id="9cfb0-117">Si el valor `TEMPLATE` no es una coincidencia exacta con el texto de la columna **Plantillas** o **Nombre corto** de la tabla devuelta, se realiza una coincidencia de subcadena con esas dos columnas.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-117">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column from the returned table, a substring match is performed on those two columns.</span></span>

  <span data-ttu-id="9cfb0-118">A partir del SDK de .NET Core 3.0, la CLI busca plantillas en NuGet.org al invocar el comando `dotnet new` en las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="9cfb0-118">Starting with .NET Core 3.0 SDK, the CLI searches for templates in NuGet.org when you invoke the `dotnet new` command in the following conditions:</span></span>

  - <span data-ttu-id="9cfb0-119">Si la CLI no encuentra ninguna coincidencia de plantilla al invocar `dotnet new`, ni siquiera parcial.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-119">If the CLI can't find a template match when invoking `dotnet new`, not even partial.</span></span>
  - <span data-ttu-id="9cfb0-120">Si hay disponible una versión más reciente de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-120">If there's a newer version of the template available.</span></span> <span data-ttu-id="9cfb0-121">En este caso, se crea el proyecto o el artefacto, pero la CLI le advierte de que hay una versión actualizada de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-121">In this case, the project or artifact is created but the CLI warns you about an updated version of the template.</span></span>

  <span data-ttu-id="9cfb0-122">En la tabla siguiente se muestran las plantillas que vienen preinstaladas en el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-122">The following table shows the templates that come pre-installed with the .NET Core SDK.</span></span> <span data-ttu-id="9cfb0-123">El lenguaje predeterminado de la plantilla se muestra entre corchetes.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-123">The default language for the template is shown inside the brackets.</span></span> <span data-ttu-id="9cfb0-124">Haga clic en el vínculo del nombre corto para ver las opciones específicas de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-124">Click on the short name link to see the specific template options.</span></span>

| <span data-ttu-id="9cfb0-125">Plantillas</span><span class="sxs-lookup"><span data-stu-id="9cfb0-125">Templates</span></span>                                    | <span data-ttu-id="9cfb0-126">Nombre corto</span><span class="sxs-lookup"><span data-stu-id="9cfb0-126">Short name</span></span>                      | <span data-ttu-id="9cfb0-127">Lenguaje</span><span class="sxs-lookup"><span data-stu-id="9cfb0-127">Language</span></span>     | <span data-ttu-id="9cfb0-128">Etiquetas</span><span class="sxs-lookup"><span data-stu-id="9cfb0-128">Tags</span></span>                                  | <span data-ttu-id="9cfb0-129">Inclusión</span><span class="sxs-lookup"><span data-stu-id="9cfb0-129">Introduced</span></span> |
|----------------------------------------------|---------------------------------|--------------|---------------------------------------|------------|
| <span data-ttu-id="9cfb0-130">Aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="9cfb0-130">Console Application</span></span>                          | [<span data-ttu-id="9cfb0-131">console</span><span class="sxs-lookup"><span data-stu-id="9cfb0-131">console</span></span>](#console)             | <span data-ttu-id="9cfb0-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="9cfb0-132">[C#], F#, VB</span></span> | <span data-ttu-id="9cfb0-133">Común/Consola</span><span class="sxs-lookup"><span data-stu-id="9cfb0-133">Common/Console</span></span>                        | <span data-ttu-id="9cfb0-134">1.0</span><span class="sxs-lookup"><span data-stu-id="9cfb0-134">1.0</span></span>        |
| <span data-ttu-id="9cfb0-135">Biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="9cfb0-135">Class library</span></span>                                | [<span data-ttu-id="9cfb0-136">classlib</span><span class="sxs-lookup"><span data-stu-id="9cfb0-136">classlib</span></span>](#classlib)           | <span data-ttu-id="9cfb0-137">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="9cfb0-137">[C#], F#, VB</span></span> | <span data-ttu-id="9cfb0-138">Común/Biblioteca</span><span class="sxs-lookup"><span data-stu-id="9cfb0-138">Common/Library</span></span>                        | <span data-ttu-id="9cfb0-139">1.0</span><span class="sxs-lookup"><span data-stu-id="9cfb0-139">1.0</span></span>        |
| <span data-ttu-id="9cfb0-140">Aplicación WPF</span><span class="sxs-lookup"><span data-stu-id="9cfb0-140">WPF Application</span></span>                              | [<span data-ttu-id="9cfb0-141">wpf</span><span class="sxs-lookup"><span data-stu-id="9cfb0-141">wpf</span></span>](#wpf)                     | <span data-ttu-id="9cfb0-142">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="9cfb0-142">[C#], VB</span></span>     | <span data-ttu-id="9cfb0-143">Común/WPF</span><span class="sxs-lookup"><span data-stu-id="9cfb0-143">Common/WPF</span></span>                            | <span data-ttu-id="9cfb0-144">3.0 (5.0 para VB)</span><span class="sxs-lookup"><span data-stu-id="9cfb0-144">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="9cfb0-145">Biblioteca de clases de WPF</span><span class="sxs-lookup"><span data-stu-id="9cfb0-145">WPF Class library</span></span>                            | [<span data-ttu-id="9cfb0-146">wpflib</span><span class="sxs-lookup"><span data-stu-id="9cfb0-146">wpflib</span></span>](#wpf)                  | <span data-ttu-id="9cfb0-147">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="9cfb0-147">[C#], VB</span></span>     | <span data-ttu-id="9cfb0-148">Común/WPF</span><span class="sxs-lookup"><span data-stu-id="9cfb0-148">Common/WPF</span></span>                            | <span data-ttu-id="9cfb0-149">3.0 (5.0 para VB)</span><span class="sxs-lookup"><span data-stu-id="9cfb0-149">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="9cfb0-150">Biblioteca de controles personalizados WPF</span><span class="sxs-lookup"><span data-stu-id="9cfb0-150">WPF Custom Control Library</span></span>                   | [<span data-ttu-id="9cfb0-151">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="9cfb0-151">wpfcustomcontrollib</span></span>](#wpf)     | <span data-ttu-id="9cfb0-152">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="9cfb0-152">[C#], VB</span></span>     | <span data-ttu-id="9cfb0-153">Común/WPF</span><span class="sxs-lookup"><span data-stu-id="9cfb0-153">Common/WPF</span></span>                            | <span data-ttu-id="9cfb0-154">3.0 (5.0 para VB)</span><span class="sxs-lookup"><span data-stu-id="9cfb0-154">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="9cfb0-155">Biblioteca de controles de usuario de WPF</span><span class="sxs-lookup"><span data-stu-id="9cfb0-155">WPF User Control Library</span></span>                     | [<span data-ttu-id="9cfb0-156">wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="9cfb0-156">wpfusercontrollib</span></span>](#wpf)       | <span data-ttu-id="9cfb0-157">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="9cfb0-157">[C#], VB</span></span>     | <span data-ttu-id="9cfb0-158">Común/WPF</span><span class="sxs-lookup"><span data-stu-id="9cfb0-158">Common/WPF</span></span>                            | <span data-ttu-id="9cfb0-159">3.0 (5.0 para VB)</span><span class="sxs-lookup"><span data-stu-id="9cfb0-159">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="9cfb0-160">Aplicación de Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="9cfb0-160">Windows Forms (WinForms) Application</span></span>         | [<span data-ttu-id="9cfb0-161">winforms</span><span class="sxs-lookup"><span data-stu-id="9cfb0-161">winforms</span></span>](#winforms)           | <span data-ttu-id="9cfb0-162">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="9cfb0-162">[C#], VB</span></span>     | <span data-ttu-id="9cfb0-163">Común/WinForms</span><span class="sxs-lookup"><span data-stu-id="9cfb0-163">Common/WinForms</span></span>                       | <span data-ttu-id="9cfb0-164">3.0 (5.0 para VB)</span><span class="sxs-lookup"><span data-stu-id="9cfb0-164">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="9cfb0-165">Biblioteca de clases de Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="9cfb0-165">Windows Forms (WinForms) Class library</span></span>       | [<span data-ttu-id="9cfb0-166">winformslib</span><span class="sxs-lookup"><span data-stu-id="9cfb0-166">winformslib</span></span>](#winforms)        | <span data-ttu-id="9cfb0-167">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="9cfb0-167">[C#], VB</span></span>     | <span data-ttu-id="9cfb0-168">Común/WinForms</span><span class="sxs-lookup"><span data-stu-id="9cfb0-168">Common/WinForms</span></span>                       | <span data-ttu-id="9cfb0-169">3.0 (5.0 para VB)</span><span class="sxs-lookup"><span data-stu-id="9cfb0-169">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="9cfb0-170">Servicio Worker</span><span class="sxs-lookup"><span data-stu-id="9cfb0-170">Worker Service</span></span>                               | [<span data-ttu-id="9cfb0-171">worker</span><span class="sxs-lookup"><span data-stu-id="9cfb0-171">worker</span></span>](#web-others)           | <span data-ttu-id="9cfb0-172">[C#]</span><span class="sxs-lookup"><span data-stu-id="9cfb0-172">[C#]</span></span>         | <span data-ttu-id="9cfb0-173">Común/Worker/Web</span><span class="sxs-lookup"><span data-stu-id="9cfb0-173">Common/Worker/Web</span></span>                     | <span data-ttu-id="9cfb0-174">3.0</span><span class="sxs-lookup"><span data-stu-id="9cfb0-174">3.0</span></span>        |
| <span data-ttu-id="9cfb0-175">Proyecto de prueba unitaria</span><span class="sxs-lookup"><span data-stu-id="9cfb0-175">Unit Test Project</span></span>                            | [<span data-ttu-id="9cfb0-176">mstest</span><span class="sxs-lookup"><span data-stu-id="9cfb0-176">mstest</span></span>](#test)                 | <span data-ttu-id="9cfb0-177">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="9cfb0-177">[C#], F#, VB</span></span> | <span data-ttu-id="9cfb0-178">Prueba/MSTest</span><span class="sxs-lookup"><span data-stu-id="9cfb0-178">Test/MSTest</span></span>                           | <span data-ttu-id="9cfb0-179">1.0</span><span class="sxs-lookup"><span data-stu-id="9cfb0-179">1.0</span></span>        |
| <span data-ttu-id="9cfb0-180">Proyecto de prueba de NUnit 3</span><span class="sxs-lookup"><span data-stu-id="9cfb0-180">NUnit 3 Test Project</span></span>                         | [<span data-ttu-id="9cfb0-181">nunit</span><span class="sxs-lookup"><span data-stu-id="9cfb0-181">nunit</span></span>](#nunit)                 | <span data-ttu-id="9cfb0-182">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="9cfb0-182">[C#], F#, VB</span></span> | <span data-ttu-id="9cfb0-183">Prueba/NUnit</span><span class="sxs-lookup"><span data-stu-id="9cfb0-183">Test/NUnit</span></span>                            | <span data-ttu-id="9cfb0-184">2.1.400</span><span class="sxs-lookup"><span data-stu-id="9cfb0-184">2.1.400</span></span>    |
| <span data-ttu-id="9cfb0-185">Elemento de prueba de NUnit 3</span><span class="sxs-lookup"><span data-stu-id="9cfb0-185">NUnit 3 Test Item</span></span>                            | `nunit-test`                    | <span data-ttu-id="9cfb0-186">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="9cfb0-186">[C#], F#, VB</span></span> | <span data-ttu-id="9cfb0-187">Prueba/NUnit</span><span class="sxs-lookup"><span data-stu-id="9cfb0-187">Test/NUnit</span></span>                            | <span data-ttu-id="9cfb0-188">2.2</span><span class="sxs-lookup"><span data-stu-id="9cfb0-188">2.2</span></span>        |
| <span data-ttu-id="9cfb0-189">Proyecto de prueba de xUnit</span><span class="sxs-lookup"><span data-stu-id="9cfb0-189">xUnit Test Project</span></span>                           | [<span data-ttu-id="9cfb0-190">xunit</span><span class="sxs-lookup"><span data-stu-id="9cfb0-190">xunit</span></span>](#test)                  | <span data-ttu-id="9cfb0-191">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="9cfb0-191">[C#], F#, VB</span></span> | <span data-ttu-id="9cfb0-192">Prueba/xUnit</span><span class="sxs-lookup"><span data-stu-id="9cfb0-192">Test/xUnit</span></span>                            | <span data-ttu-id="9cfb0-193">1.0</span><span class="sxs-lookup"><span data-stu-id="9cfb0-193">1.0</span></span>        |
| <span data-ttu-id="9cfb0-194">Componente Razor</span><span class="sxs-lookup"><span data-stu-id="9cfb0-194">Razor Component</span></span>                              | `razorcomponent`                | <span data-ttu-id="9cfb0-195">[C#]</span><span class="sxs-lookup"><span data-stu-id="9cfb0-195">[C#]</span></span>         | <span data-ttu-id="9cfb0-196">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="9cfb0-196">Web/ASP.NET</span></span>                           | <span data-ttu-id="9cfb0-197">3.0</span><span class="sxs-lookup"><span data-stu-id="9cfb0-197">3.0</span></span>        |
| <span data-ttu-id="9cfb0-198">Página de Razor</span><span class="sxs-lookup"><span data-stu-id="9cfb0-198">Razor Page</span></span>                                   | [<span data-ttu-id="9cfb0-199">page</span><span class="sxs-lookup"><span data-stu-id="9cfb0-199">page</span></span>](#page)                   | <span data-ttu-id="9cfb0-200">[C#]</span><span class="sxs-lookup"><span data-stu-id="9cfb0-200">[C#]</span></span>         | <span data-ttu-id="9cfb0-201">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="9cfb0-201">Web/ASP.NET</span></span>                           | <span data-ttu-id="9cfb0-202">2.0</span><span class="sxs-lookup"><span data-stu-id="9cfb0-202">2.0</span></span>        |
| <span data-ttu-id="9cfb0-203">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="9cfb0-203">MVC ViewImports</span></span>                              | [<span data-ttu-id="9cfb0-204">viewimports</span><span class="sxs-lookup"><span data-stu-id="9cfb0-204">viewimports</span></span>](#namespace)       | <span data-ttu-id="9cfb0-205">[C#]</span><span class="sxs-lookup"><span data-stu-id="9cfb0-205">[C#]</span></span>         | <span data-ttu-id="9cfb0-206">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="9cfb0-206">Web/ASP.NET</span></span>                           | <span data-ttu-id="9cfb0-207">2.0</span><span class="sxs-lookup"><span data-stu-id="9cfb0-207">2.0</span></span>        |
| <span data-ttu-id="9cfb0-208">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="9cfb0-208">MVC ViewStart</span></span>                                | `viewstart`                     | <span data-ttu-id="9cfb0-209">[C#]</span><span class="sxs-lookup"><span data-stu-id="9cfb0-209">[C#]</span></span>         | <span data-ttu-id="9cfb0-210">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="9cfb0-210">Web/ASP.NET</span></span>                           | <span data-ttu-id="9cfb0-211">2.0</span><span class="sxs-lookup"><span data-stu-id="9cfb0-211">2.0</span></span>        |
| <span data-ttu-id="9cfb0-212">:::no-loc(Blazor)::: Aplicación de servidor</span><span class="sxs-lookup"><span data-stu-id="9cfb0-212">:::no-loc(Blazor)::: Server App</span></span>                            | [<span data-ttu-id="9cfb0-213">blazorserver</span><span class="sxs-lookup"><span data-stu-id="9cfb0-213">blazorserver</span></span>](#blazorserver)   | <span data-ttu-id="9cfb0-214">[C#]</span><span class="sxs-lookup"><span data-stu-id="9cfb0-214">[C#]</span></span>         | <span data-ttu-id="9cfb0-215">Web/:::no-loc(Blazor):::</span><span class="sxs-lookup"><span data-stu-id="9cfb0-215">Web/:::no-loc(Blazor):::</span></span>                            | <span data-ttu-id="9cfb0-216">3.0</span><span class="sxs-lookup"><span data-stu-id="9cfb0-216">3.0</span></span>        |
| <span data-ttu-id="9cfb0-217">Aplicación de :::no-loc(Blazor)::: :::no-loc(WebAssembly):::</span><span class="sxs-lookup"><span data-stu-id="9cfb0-217">:::no-loc(Blazor)::: :::no-loc(WebAssembly)::: App</span></span>                       | [<span data-ttu-id="9cfb0-218">blazorwasm</span><span class="sxs-lookup"><span data-stu-id="9cfb0-218">blazorwasm</span></span>](#blazorwasm)       | <span data-ttu-id="9cfb0-219">[C#]</span><span class="sxs-lookup"><span data-stu-id="9cfb0-219">[C#]</span></span>         | <span data-ttu-id="9cfb0-220">Web/:::no-loc(Blazor):::/:::no-loc(WebAssembly):::</span><span class="sxs-lookup"><span data-stu-id="9cfb0-220">Web/:::no-loc(Blazor):::/:::no-loc(WebAssembly):::</span></span>                | <span data-ttu-id="9cfb0-221">3.1.300</span><span class="sxs-lookup"><span data-stu-id="9cfb0-221">3.1.300</span></span>    |
| <span data-ttu-id="9cfb0-222">Vacío de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="9cfb0-222">ASP.NET Core Empty</span></span>                           | [<span data-ttu-id="9cfb0-223">web</span><span class="sxs-lookup"><span data-stu-id="9cfb0-223">web</span></span>](#web)                     | <span data-ttu-id="9cfb0-224">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="9cfb0-224">[C#], F#</span></span>     | <span data-ttu-id="9cfb0-225">Web/Vacío</span><span class="sxs-lookup"><span data-stu-id="9cfb0-225">Web/Empty</span></span>                             | <span data-ttu-id="9cfb0-226">1.0</span><span class="sxs-lookup"><span data-stu-id="9cfb0-226">1.0</span></span>        |
| <span data-ttu-id="9cfb0-227">Aplicación web de ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="9cfb0-227">ASP.NET Core Web App (Model-View-Controller)</span></span> | [<span data-ttu-id="9cfb0-228">mvc</span><span class="sxs-lookup"><span data-stu-id="9cfb0-228">mvc</span></span>](#web-options)             | <span data-ttu-id="9cfb0-229">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="9cfb0-229">[C#], F#</span></span>     | <span data-ttu-id="9cfb0-230">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="9cfb0-230">Web/MVC</span></span>                               | <span data-ttu-id="9cfb0-231">1.0</span><span class="sxs-lookup"><span data-stu-id="9cfb0-231">1.0</span></span>        |
| <span data-ttu-id="9cfb0-232">Aplicación web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="9cfb0-232">ASP.NET Core Web App</span></span>                         | [<span data-ttu-id="9cfb0-233">webapp, razor</span><span class="sxs-lookup"><span data-stu-id="9cfb0-233">webapp, razor</span></span>](#web-options)   | <span data-ttu-id="9cfb0-234">[C#]</span><span class="sxs-lookup"><span data-stu-id="9cfb0-234">[C#]</span></span>         | <span data-ttu-id="9cfb0-235">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="9cfb0-235">Web/MVC/Razor Pages</span></span>                   | <span data-ttu-id="9cfb0-236">2.2, 2.0</span><span class="sxs-lookup"><span data-stu-id="9cfb0-236">2.2, 2.0</span></span>   |
| <span data-ttu-id="9cfb0-237">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="9cfb0-237">ASP.NET Core with Angular</span></span>                    | [<span data-ttu-id="9cfb0-238">angular</span><span class="sxs-lookup"><span data-stu-id="9cfb0-238">angular</span></span>](#spa)                 | <span data-ttu-id="9cfb0-239">[C#]</span><span class="sxs-lookup"><span data-stu-id="9cfb0-239">[C#]</span></span>         | <span data-ttu-id="9cfb0-240">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="9cfb0-240">Web/MVC/SPA</span></span>                           | <span data-ttu-id="9cfb0-241">2.0</span><span class="sxs-lookup"><span data-stu-id="9cfb0-241">2.0</span></span>        |
| <span data-ttu-id="9cfb0-242">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="9cfb0-242">ASP.NET Core with React.js</span></span>                   | [<span data-ttu-id="9cfb0-243">react</span><span class="sxs-lookup"><span data-stu-id="9cfb0-243">react</span></span>](#spa)                   | <span data-ttu-id="9cfb0-244">[C#]</span><span class="sxs-lookup"><span data-stu-id="9cfb0-244">[C#]</span></span>         | <span data-ttu-id="9cfb0-245">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="9cfb0-245">Web/MVC/SPA</span></span>                           | <span data-ttu-id="9cfb0-246">2.0</span><span class="sxs-lookup"><span data-stu-id="9cfb0-246">2.0</span></span>        |
| <span data-ttu-id="9cfb0-247">ASP.NET Core con React.js y Redux</span><span class="sxs-lookup"><span data-stu-id="9cfb0-247">ASP.NET Core with React.js and Redux</span></span>         | [<span data-ttu-id="9cfb0-248">reactredux</span><span class="sxs-lookup"><span data-stu-id="9cfb0-248">reactredux</span></span>](#reactredux)       | <span data-ttu-id="9cfb0-249">[C#]</span><span class="sxs-lookup"><span data-stu-id="9cfb0-249">[C#]</span></span>         | <span data-ttu-id="9cfb0-250">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="9cfb0-250">Web/MVC/SPA</span></span>                           | <span data-ttu-id="9cfb0-251">2.0</span><span class="sxs-lookup"><span data-stu-id="9cfb0-251">2.0</span></span>        |
| <span data-ttu-id="9cfb0-252">Biblioteca de clases de Razor</span><span class="sxs-lookup"><span data-stu-id="9cfb0-252">Razor Class Library</span></span>                          | [<span data-ttu-id="9cfb0-253">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="9cfb0-253">razorclasslib</span></span>](#razorclasslib) | <span data-ttu-id="9cfb0-254">[C#]</span><span class="sxs-lookup"><span data-stu-id="9cfb0-254">[C#]</span></span>         | <span data-ttu-id="9cfb0-255">Web/Razor/Biblioteca/Biblioteca de clases de Razor</span><span class="sxs-lookup"><span data-stu-id="9cfb0-255">Web/Razor/Library/Razor Class Library</span></span> | <span data-ttu-id="9cfb0-256">2.1</span><span class="sxs-lookup"><span data-stu-id="9cfb0-256">2.1</span></span>        |
| <span data-ttu-id="9cfb0-257">API web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="9cfb0-257">ASP.NET Core Web API</span></span>                         | [<span data-ttu-id="9cfb0-258">webapi</span><span class="sxs-lookup"><span data-stu-id="9cfb0-258">webapi</span></span>](#webapi)               | <span data-ttu-id="9cfb0-259">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="9cfb0-259">[C#], F#</span></span>     | <span data-ttu-id="9cfb0-260">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="9cfb0-260">Web/WebAPI</span></span>                            | <span data-ttu-id="9cfb0-261">1.0</span><span class="sxs-lookup"><span data-stu-id="9cfb0-261">1.0</span></span>        |
| <span data-ttu-id="9cfb0-262">Servicio gRPC de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="9cfb0-262">ASP.NET Core gRPC Service</span></span>                    | [<span data-ttu-id="9cfb0-263">grpc</span><span class="sxs-lookup"><span data-stu-id="9cfb0-263">grpc</span></span>](#web-others)             | <span data-ttu-id="9cfb0-264">[C#]</span><span class="sxs-lookup"><span data-stu-id="9cfb0-264">[C#]</span></span>         | <span data-ttu-id="9cfb0-265">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="9cfb0-265">Web/gRPC</span></span>                              | <span data-ttu-id="9cfb0-266">3.0</span><span class="sxs-lookup"><span data-stu-id="9cfb0-266">3.0</span></span>        |
| <span data-ttu-id="9cfb0-267">Archivo dotnet gitignore</span><span class="sxs-lookup"><span data-stu-id="9cfb0-267">dotnet gitignore file</span></span>                        | `gitignore`                     |              | <span data-ttu-id="9cfb0-268">Configuración</span><span class="sxs-lookup"><span data-stu-id="9cfb0-268">Config</span></span>                                | <span data-ttu-id="9cfb0-269">3.0</span><span class="sxs-lookup"><span data-stu-id="9cfb0-269">3.0</span></span>        |
| <span data-ttu-id="9cfb0-270">archivo global.json</span><span class="sxs-lookup"><span data-stu-id="9cfb0-270">global.json file</span></span>                             | [<span data-ttu-id="9cfb0-271">globaljson</span><span class="sxs-lookup"><span data-stu-id="9cfb0-271">globaljson</span></span>](#globaljson)       |              | <span data-ttu-id="9cfb0-272">Configuración</span><span class="sxs-lookup"><span data-stu-id="9cfb0-272">Config</span></span>                                | <span data-ttu-id="9cfb0-273">2.0</span><span class="sxs-lookup"><span data-stu-id="9cfb0-273">2.0</span></span>        |
| <span data-ttu-id="9cfb0-274">Configuración de NuGet</span><span class="sxs-lookup"><span data-stu-id="9cfb0-274">NuGet Config</span></span>                                 | `nugetconfig`                   |              | <span data-ttu-id="9cfb0-275">Configuración</span><span class="sxs-lookup"><span data-stu-id="9cfb0-275">Config</span></span>                                | <span data-ttu-id="9cfb0-276">1.0</span><span class="sxs-lookup"><span data-stu-id="9cfb0-276">1.0</span></span>        |
| <span data-ttu-id="9cfb0-277">Archivo de manifiesto de la herramienta local dotnet</span><span class="sxs-lookup"><span data-stu-id="9cfb0-277">Dotnet local tool manifest file</span></span>              | `tool-manifest`                 |              | <span data-ttu-id="9cfb0-278">Configuración</span><span class="sxs-lookup"><span data-stu-id="9cfb0-278">Config</span></span>                                | <span data-ttu-id="9cfb0-279">3.0</span><span class="sxs-lookup"><span data-stu-id="9cfb0-279">3.0</span></span>        |
| <span data-ttu-id="9cfb0-280">Configuración web</span><span class="sxs-lookup"><span data-stu-id="9cfb0-280">Web Config</span></span>                                   | `webconfig`                     |              | <span data-ttu-id="9cfb0-281">Configuración</span><span class="sxs-lookup"><span data-stu-id="9cfb0-281">Config</span></span>                                | <span data-ttu-id="9cfb0-282">1.0</span><span class="sxs-lookup"><span data-stu-id="9cfb0-282">1.0</span></span>        |
| <span data-ttu-id="9cfb0-283">Archivo de solución</span><span class="sxs-lookup"><span data-stu-id="9cfb0-283">Solution File</span></span>                                | `sln`                           |              | <span data-ttu-id="9cfb0-284">Soluciones</span><span class="sxs-lookup"><span data-stu-id="9cfb0-284">Solution</span></span>                              | <span data-ttu-id="9cfb0-285">1.0</span><span class="sxs-lookup"><span data-stu-id="9cfb0-285">1.0</span></span>        |
| <span data-ttu-id="9cfb0-286">Archivo de búfer de protocolo</span><span class="sxs-lookup"><span data-stu-id="9cfb0-286">Protocol Buffer File</span></span>                         | [<span data-ttu-id="9cfb0-287">proto</span><span class="sxs-lookup"><span data-stu-id="9cfb0-287">proto</span></span>](#namespace)             |              | <span data-ttu-id="9cfb0-288">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="9cfb0-288">Web/gRPC</span></span>                              | <span data-ttu-id="9cfb0-289">3.0</span><span class="sxs-lookup"><span data-stu-id="9cfb0-289">3.0</span></span>        |

## <a name="options"></a><span data-ttu-id="9cfb0-290">Opciones</span><span class="sxs-lookup"><span data-stu-id="9cfb0-290">Options</span></span>

- **`--dry-run`**

  <span data-ttu-id="9cfb0-291">Muestra un resumen de lo que sucedería si se ejecutara el comando determinado y el resultado fuera la creación de una plantilla.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-291">Displays a summary of what would happen if the given command were run if it would result in a template creation.</span></span> <span data-ttu-id="9cfb0-292">Disponible a partir del SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-292">Available since .NET Core 2.2 SDK.</span></span>

- **`--force`**

  <span data-ttu-id="9cfb0-293">Fuerza la generación de contenido incluso aunque se vayan a cambiar los archivos existentes.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-293">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="9cfb0-294">Es necesario si la plantilla elegida invalidará los archivos existentes en el directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-294">This is required when the template chosen would override existing files in the output directory.</span></span>

- **`-h|--help`**

  <span data-ttu-id="9cfb0-295">Imprime la ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-295">Prints out help for the command.</span></span> <span data-ttu-id="9cfb0-296">Puede invocarse para el propio comando `dotnet new` o para cualquier plantilla.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-296">It can be invoked for the `dotnet new` command itself or for any template.</span></span> <span data-ttu-id="9cfb0-297">Por ejemplo: `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-297">For example, `dotnet new mvc --help`.</span></span>

- **`-i|--install <PATH|NUGET_ID>`**

  <span data-ttu-id="9cfb0-298">Instala un paquete de plantillas desde los parámetros `PATH` o `NUGET_ID` proporcionados.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-298">Installs a template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="9cfb0-299">Si quiere instalar una versión preliminar de un paquete de plantilla, tendrá que especificar la versión en el formato de `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-299">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="9cfb0-300">De forma predeterminada, `dotnet new` pasa \* para la versión, que representa la última versión estable del paquete.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-300">By default, `dotnet new` passes \* for the version, which represents the latest stable package version.</span></span> <span data-ttu-id="9cfb0-301">Vea un ejemplo en la sección [Ejemplos](#examples).</span><span class="sxs-lookup"><span data-stu-id="9cfb0-301">See an example in the [Examples](#examples) section.</span></span>
  
  <span data-ttu-id="9cfb0-302">Si ya hay instalada una versión de la plantilla al ejecutar este comando, la plantilla se actualizará a la versión especificada o a la versión estable más reciente si no se ha especificado ninguna versión.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-302">If a version of the template was already installed when you run this command, the template will be updated to the specified version, or to the latest stable version if no version was specified.</span></span>

  <span data-ttu-id="9cfb0-303">Para obtener información sobre cómo crear plantillas personalizadas, consulte [Plantillas personalizadas para dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="9cfb0-303">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

- **`-l|--list`**

  <span data-ttu-id="9cfb0-304">Muestra las plantillas que contienen el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-304">Lists templates containing the specified name.</span></span> <span data-ttu-id="9cfb0-305">Si no se especifica ningún nombre, enumera todas las plantillas.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-305">If no name is specified, lists all templates.</span></span>

- **`-lang|--language {C#|F#|VB}`**

  <span data-ttu-id="9cfb0-306">El lenguaje de la plantilla que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-306">The language of the template to create.</span></span> <span data-ttu-id="9cfb0-307">El lenguaje aceptado cambia según la plantilla (vea los valores predeterminados en la sección [argumentos](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="9cfb0-307">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="9cfb0-308">No es válido para algunas plantillas.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-308">Not valid for some templates.</span></span>

  > [!NOTE]
  > <span data-ttu-id="9cfb0-309">Algunos shells interpretan `#` como un carácter especial.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-309">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="9cfb0-310">En esos casos, incluya el valor del parámetro de lenguaje entre comillas.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-310">In those cases, enclose the language parameter value in quotes.</span></span> <span data-ttu-id="9cfb0-311">Por ejemplo: `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-311">For example, `dotnet new console -lang "F#"`.</span></span>

- **`-n|--name <OUTPUT_NAME>`**

  <span data-ttu-id="9cfb0-312">El nombre de la salida creada.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-312">The name for the created output.</span></span> <span data-ttu-id="9cfb0-313">Si no se especifica ningún nombre, se usa el nombre del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-313">If no name is specified, the name of the current directory is used.</span></span>

- **`--nuget-source <SOURCE>`**

  <span data-ttu-id="9cfb0-314">Especifica un origen de NuGet para usarlo durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-314">Specifies a NuGet source to use during install.</span></span> <span data-ttu-id="9cfb0-315">Disponible a partir del SDK de .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-315">Available since .NET Core 2.1 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="9cfb0-316">La ubicación para colocar la salida generada.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-316">Location to place the generated output.</span></span> <span data-ttu-id="9cfb0-317">El valor predeterminado es el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-317">The default is the current directory.</span></span>

- **`--type <TYPE>`**

  <span data-ttu-id="9cfb0-318">Filtra plantillas en función de los tipos disponibles.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-318">Filters templates based on available types.</span></span> <span data-ttu-id="9cfb0-319">Los valores predefinidos son `project` e `item`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-319">Predefined values are `project` and `item`.</span></span>

- **`-u|--uninstall [PATH|NUGET_ID]`**

  <span data-ttu-id="9cfb0-320">Desinstala un paquete de plantillas en los parámetros `PATH` o `NUGET_ID` proporcionados.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-320">Uninstalls a template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="9cfb0-321">Si no se especifica el valor `<PATH|NUGET_ID>`, se muestran todos los paquetes de plantillas instalados actualmente y sus plantillas asociadas.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-321">When the `<PATH|NUGET_ID>` value isn't specified, all currently installed template packs and their associated templates are displayed.</span></span> <span data-ttu-id="9cfb0-322">Al especificar `NUGET_ID`, no incluya el número de versión.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-322">When specifying `NUGET_ID`, don't include the version number.</span></span>

  <span data-ttu-id="9cfb0-323">Si no especifica un parámetro en esta opción, el comando muestra las plantillas instaladas y detalles sobre ellas.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-323">If you don't specify a parameter to this option, the command lists the installed templates and details about them.</span></span>

  > [!NOTE]
  > <span data-ttu-id="9cfb0-324">Para desinstalar una plantilla mediante `PATH`, debe usar el nombre completo de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-324">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="9cfb0-325">Por ejemplo, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* funcionará, pero *./GarciaSoftware.ConsoleTemplate.CSharp* desde la carpeta contenedora no lo hará.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-325">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
  > <span data-ttu-id="9cfb0-326">No incluya ninguna barra diagonal para finalizar el directorio en la ruta de acceso a la plantilla.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-326">Don't include a final terminating directory slash on your template path.</span></span>

- **`--update-apply`**

  <span data-ttu-id="9cfb0-327">Comprueba si hay actualizaciones disponibles de los paquetes de plantillas instalados actualmente y las instala.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-327">Checks if there are updates available for the template packs that are currently installed and installs them.</span></span> <span data-ttu-id="9cfb0-328">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-328">Available since .NET Core 3.0 SDK.</span></span>

- **`--update-check`**

  <span data-ttu-id="9cfb0-329">Comprueba si hay actualizaciones disponibles de los paquetes de plantillas instalados actualmente.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-329">Checks if there are updates available for the template packs that are currently installed.</span></span> <span data-ttu-id="9cfb0-330">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-330">Available since .NET Core 3.0 SDK.</span></span>

## <a name="template-options"></a><span data-ttu-id="9cfb0-331">Opciones de plantilla</span><span class="sxs-lookup"><span data-stu-id="9cfb0-331">Template options</span></span>

<span data-ttu-id="9cfb0-332">Cada plantilla de proyecto puede tener opciones adicionales disponibles.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-332">Each project template may have additional options available.</span></span> <span data-ttu-id="9cfb0-333">Las plantillas principales tienen las siguientes opciones adicionales:</span><span class="sxs-lookup"><span data-stu-id="9cfb0-333">The core templates have the following additional options:</span></span>

### <a name="console"></a><span data-ttu-id="9cfb0-334">consola</span><span class="sxs-lookup"><span data-stu-id="9cfb0-334">console</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="9cfb0-335">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-335">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="9cfb0-336">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-336">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="9cfb0-337">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="9cfb0-337">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="9cfb0-338">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="9cfb0-338">SDK version</span></span> | <span data-ttu-id="9cfb0-339">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="9cfb0-339">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="9cfb0-340">3.1</span><span class="sxs-lookup"><span data-stu-id="9cfb0-340">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="9cfb0-341">3.0</span><span class="sxs-lookup"><span data-stu-id="9cfb0-341">3.0</span></span>         | `netcoreapp3.0` |

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="9cfb0-342">Establece la propiedad `LangVersion` en el archivo del proyecto creado.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-342">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="9cfb0-343">Por ejemplo, use `--langVersion 7.3` para emplear C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-343">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="9cfb0-344">No es compatible con F#.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-344">Not supported for F#.</span></span> <span data-ttu-id="9cfb0-345">Disponible a partir del SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-345">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="9cfb0-346">Para obtener una lista de las versiones predeterminadas de C#, vea [Valores predeterminados](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="9cfb0-346">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="9cfb0-347">Si se especifica, no se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-347">If specified, doesn't execute an implicit restore during project creation.</span></span> <span data-ttu-id="9cfb0-348">Disponible a partir del SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-348">Available since .NET Core 2.2 SDK.</span></span>

<span data-ttu-id="9cfb0-349">\*\*_</span><span class="sxs-lookup"><span data-stu-id="9cfb0-349">\*\*_</span></span>

### <a name="classlib"></a><span data-ttu-id="9cfb0-350">classlib</span><span class="sxs-lookup"><span data-stu-id="9cfb0-350">classlib</span></span>

- <span data-ttu-id="9cfb0-351">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="9cfb0-351">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="9cfb0-352">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-352">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="9cfb0-353">Valores: `netcoreapp<version>` para crear una biblioteca de clases de .NET Core o `netstandard<version>` para crear una biblioteca de clases de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-353">Values: `netcoreapp<version>` to create a .NET Core Class Library or `netstandard<version>` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="9cfb0-354">El valor predeterminado es `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-354">The default value is `netstandard2.0`.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="9cfb0-355">Establece la propiedad `LangVersion` en el archivo del proyecto creado.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-355">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="9cfb0-356">Por ejemplo, use `--langVersion 7.3` para emplear C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-356">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="9cfb0-357">No es compatible con F#.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-357">Not supported for F#.</span></span> <span data-ttu-id="9cfb0-358">Disponible a partir del SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-358">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="9cfb0-359">Para obtener una lista de las versiones predeterminadas de C#, vea [Valores predeterminados](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="9cfb0-359">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="9cfb0-360">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-360">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="9cfb0-361">\*\*_</span><span class="sxs-lookup"><span data-stu-id="9cfb0-361">\*\*_</span></span>

### <a name="wpf-wpflib-wpfcustomcontrollib-wpfusercontrollib"></a><a name="wpf"></a> <span data-ttu-id="9cfb0-362">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="9cfb0-362">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span></span>

- <span data-ttu-id="9cfb0-363">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="9cfb0-363">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="9cfb0-364">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-364">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="9cfb0-365">El valor predeterminado es `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-365">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="9cfb0-366">Disponible a partir del SDK de .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-366">Available since .NET Core 3.1 SDK.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="9cfb0-367">Establece la propiedad `LangVersion` en el archivo del proyecto creado.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-367">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="9cfb0-368">Por ejemplo, use `--langVersion 7.3` para emplear C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-368">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="9cfb0-369">Para obtener una lista de las versiones predeterminadas de C#, vea [Valores predeterminados](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="9cfb0-369">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="9cfb0-370">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-370">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="9cfb0-371">\*\*_</span><span class="sxs-lookup"><span data-stu-id="9cfb0-371">\*\*_</span></span>

### <a name="winforms-winformslib"></a><a name="winforms"></a> <span data-ttu-id="9cfb0-372">winforms, winformslib</span><span class="sxs-lookup"><span data-stu-id="9cfb0-372">winforms, winformslib</span></span>

- <span data-ttu-id="9cfb0-373">_ *`--langVersion <VERSION_NUMBER>`*\*</span><span class="sxs-lookup"><span data-stu-id="9cfb0-373">_ *`--langVersion <VERSION_NUMBER>`*\*</span></span>

  <span data-ttu-id="9cfb0-374">Establece la propiedad `LangVersion` en el archivo del proyecto creado.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-374">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="9cfb0-375">Por ejemplo, use `--langVersion 7.3` para emplear C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-375">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="9cfb0-376">Para obtener una lista de las versiones predeterminadas de C#, vea [Valores predeterminados](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="9cfb0-376">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="9cfb0-377">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-377">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="9cfb0-378">\*\*_</span><span class="sxs-lookup"><span data-stu-id="9cfb0-378">\*\*_</span></span>

### <a name="worker-grpc"></a><a name="web-others"></a> <span data-ttu-id="9cfb0-379">worker, grpc</span><span class="sxs-lookup"><span data-stu-id="9cfb0-379">worker, grpc</span></span>

- <span data-ttu-id="9cfb0-380">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="9cfb0-380">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="9cfb0-381">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-381">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="9cfb0-382">El valor predeterminado es `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-382">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="9cfb0-383">Disponible a partir del SDK de .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-383">Available since .NET Core 3.1 SDK.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="9cfb0-384">Excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-384">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="9cfb0-385">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-385">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="9cfb0-386">\*\*_</span><span class="sxs-lookup"><span data-stu-id="9cfb0-386">\*\*_</span></span>

### <a name="mstest-xunit"></a><a name="test"></a> <span data-ttu-id="9cfb0-387">mstest, xunit</span><span class="sxs-lookup"><span data-stu-id="9cfb0-387">mstest, xunit</span></span>

- <span data-ttu-id="9cfb0-388">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="9cfb0-388">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="9cfb0-389">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-389">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="9cfb0-390">Opción disponible a partir del SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-390">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="9cfb0-391">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="9cfb0-391">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="9cfb0-392">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="9cfb0-392">SDK version</span></span> | <span data-ttu-id="9cfb0-393">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="9cfb0-393">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="9cfb0-394">3.1</span><span class="sxs-lookup"><span data-stu-id="9cfb0-394">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="9cfb0-395">3.0</span><span class="sxs-lookup"><span data-stu-id="9cfb0-395">3.0</span></span>         | `netcoreapp3.0` |

- **`-p|--enable-pack`**

  <span data-ttu-id="9cfb0-396">Habilita el empaquetado del proyecto mediante [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="9cfb0-396">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="9cfb0-397">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-397">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="9cfb0-398">\*\*_</span><span class="sxs-lookup"><span data-stu-id="9cfb0-398">\*\*_</span></span>

### <a name="nunit"></a><span data-ttu-id="9cfb0-399">nunit</span><span class="sxs-lookup"><span data-stu-id="9cfb0-399">nunit</span></span>

- <span data-ttu-id="9cfb0-400">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="9cfb0-400">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="9cfb0-401">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-401">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="9cfb0-402">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="9cfb0-402">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="9cfb0-403">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="9cfb0-403">SDK version</span></span> | <span data-ttu-id="9cfb0-404">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="9cfb0-404">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="9cfb0-405">3.1</span><span class="sxs-lookup"><span data-stu-id="9cfb0-405">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="9cfb0-406">3.0</span><span class="sxs-lookup"><span data-stu-id="9cfb0-406">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="9cfb0-407">2.2</span><span class="sxs-lookup"><span data-stu-id="9cfb0-407">2.2</span></span>         | `netcoreapp2.2` |
  | <span data-ttu-id="9cfb0-408">2.1</span><span class="sxs-lookup"><span data-stu-id="9cfb0-408">2.1</span></span>         | `netcoreapp2.1` |

- **`-p|--enable-pack`**

  <span data-ttu-id="9cfb0-409">Habilita el empaquetado del proyecto mediante [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="9cfb0-409">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="9cfb0-410">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-410">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="9cfb0-411">\*\*_</span><span class="sxs-lookup"><span data-stu-id="9cfb0-411">\*\*_</span></span>

### <a name="page"></a><span data-ttu-id="9cfb0-412">página</span><span class="sxs-lookup"><span data-stu-id="9cfb0-412">page</span></span>

- <span data-ttu-id="9cfb0-413">_ *`-na|--namespace <NAMESPACE_NAME>`*\*</span><span class="sxs-lookup"><span data-stu-id="9cfb0-413">_ *`-na|--namespace <NAMESPACE_NAME>`*\*</span></span>

  <span data-ttu-id="9cfb0-414">Espacio de nombres del código generado.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-414">Namespace for the generated code.</span></span> <span data-ttu-id="9cfb0-415">El valor predeterminado es `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-415">The default value is `MyApp.Namespace`.</span></span>

- **`-np|--no-pagemodel`**

  <span data-ttu-id="9cfb0-416">Crea la página sin PageModel.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-416">Creates the page without a PageModel.</span></span>

<span data-ttu-id="9cfb0-417">\*\*_</span><span class="sxs-lookup"><span data-stu-id="9cfb0-417">\*\*_</span></span>

### <a name="viewimports-proto"></a><a name="namespace"></a> <span data-ttu-id="9cfb0-418">viewimports, proto</span><span class="sxs-lookup"><span data-stu-id="9cfb0-418">viewimports, proto</span></span>

- <span data-ttu-id="9cfb0-419">_ *`-na|--namespace <NAMESPACE_NAME>`*\*</span><span class="sxs-lookup"><span data-stu-id="9cfb0-419">_ *`-na|--namespace <NAMESPACE_NAME>`*\*</span></span>

  <span data-ttu-id="9cfb0-420">Espacio de nombres del código generado.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-420">Namespace for the generated code.</span></span> <span data-ttu-id="9cfb0-421">El valor predeterminado es `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-421">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="9cfb0-422">\*\*_</span><span class="sxs-lookup"><span data-stu-id="9cfb0-422">\*\*_</span></span>

### <a name="blazorserver"></a><span data-ttu-id="9cfb0-423">blazorserver</span><span class="sxs-lookup"><span data-stu-id="9cfb0-423">blazorserver</span></span>

- <span data-ttu-id="9cfb0-424">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="9cfb0-424">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="9cfb0-425">Tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-425">The type of authentication to use.</span></span> <span data-ttu-id="9cfb0-426">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="9cfb0-426">The possible values are:</span></span>

  - <span data-ttu-id="9cfb0-427">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="9cfb0-427">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="9cfb0-428">`Individual`: autenticación individual.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-428">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="9cfb0-429">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-429">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="9cfb0-430">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-430">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="9cfb0-431">`MultiOrg`: autenticación organizativa para varios inquilinos.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-431">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="9cfb0-432">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-432">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="9cfb0-433">Instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-433">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="9cfb0-434">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-434">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="9cfb0-435">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-435">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="9cfb0-436">Identificador de la directiva de registro e inicio de sesión de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-436">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="9cfb0-437">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-437">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="9cfb0-438">Identificador de la directiva de restablecimiento de contraseñas de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-438">The reset password policy ID for this project.</span></span> <span data-ttu-id="9cfb0-439">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-439">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="9cfb0-440">Identificador de la directiva de edición de perfiles de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-440">The edit profile policy ID for this project.</span></span> <span data-ttu-id="9cfb0-441">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-441">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="9cfb0-442">Instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-442">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="9cfb0-443">Úsela con las autenticaciones `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-443">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="9cfb0-444">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-444">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="9cfb0-445">Identificador de cliente de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-445">The Client ID for this project.</span></span> <span data-ttu-id="9cfb0-446">Úsela con las autenticaciones `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-446">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="9cfb0-447">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-447">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="9cfb0-448">Dominio del inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-448">The domain for the directory tenant.</span></span> <span data-ttu-id="9cfb0-449">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-449">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="9cfb0-450">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-450">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="9cfb0-451">Identificador de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-451">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="9cfb0-452">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-452">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="9cfb0-453">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-453">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="9cfb0-454">Ruta de acceso de solicitud de la ruta de acceso de la base de la aplicación del URI de redirección.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-454">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="9cfb0-455">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-455">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="9cfb0-456">El valor predeterminado es `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-456">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="9cfb0-457">Concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-457">Allows this application read-access to the directory.</span></span> <span data-ttu-id="9cfb0-458">Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-458">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="9cfb0-459">Excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-459">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="9cfb0-460">Desactiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-460">Turns off HTTPS.</span></span> <span data-ttu-id="9cfb0-461">Esta opción solo se aplica si no se usan `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg` en `--auth`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-461">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="9cfb0-462">Especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-462">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="9cfb0-463">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-463">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--no-restore`**

  <span data-ttu-id="9cfb0-464">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-464">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="9cfb0-465">\*\*_</span><span class="sxs-lookup"><span data-stu-id="9cfb0-465">\*\*_</span></span>

### <a name="blazorwasm"></a><span data-ttu-id="9cfb0-466">blazorwasm</span><span class="sxs-lookup"><span data-stu-id="9cfb0-466">blazorwasm</span></span>

- <span data-ttu-id="9cfb0-467">_ *`-f|--framework <FRAMEWORK>`*\*</span><span class="sxs-lookup"><span data-stu-id="9cfb0-467">_ *`-f|--framework <FRAMEWORK>`*\*</span></span>

  <span data-ttu-id="9cfb0-468">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-468">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="9cfb0-469">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="9cfb0-469">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="9cfb0-470">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="9cfb0-470">SDK version</span></span> | <span data-ttu-id="9cfb0-471">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="9cfb0-471">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="9cfb0-472">5.0</span><span class="sxs-lookup"><span data-stu-id="9cfb0-472">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="9cfb0-473">3.1</span><span class="sxs-lookup"><span data-stu-id="9cfb0-473">3.1</span></span>         | `netcoreapp3.1` |

- **`--no-restore`**

  <span data-ttu-id="9cfb0-474">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-474">Doesn't execute an implicit restore during project creation.</span></span>

- **`-ho|--hosted`**

  <span data-ttu-id="9cfb0-475">Incluye un host de ASP.NET Core para la aplicación :::no-loc(Blazor)::: :::no-loc(WebAssembly):::.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-475">Includes an ASP.NET Core host for the :::no-loc(Blazor)::: :::no-loc(WebAssembly)::: app.</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="9cfb0-476">Tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-476">The type of authentication to use.</span></span> <span data-ttu-id="9cfb0-477">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="9cfb0-477">The possible values are:</span></span>

  - <span data-ttu-id="9cfb0-478">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="9cfb0-478">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="9cfb0-479">`Individual`: autenticación individual.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-479">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="9cfb0-480">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-480">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="9cfb0-481">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-481">`SingleOrg` - Organizational authentication for a single tenant.</span></span>

- **`--authority <AUTHORITY>`**

  <span data-ttu-id="9cfb0-482">La autoridad del proveedor de OIDC.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-482">The authority of the OIDC provider.</span></span> <span data-ttu-id="9cfb0-483">Úsela con la autenticación `Individual`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-483">Use with `Individual` authentication.</span></span> <span data-ttu-id="9cfb0-484">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-484">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="9cfb0-485">Instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-485">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="9cfb0-486">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-486">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="9cfb0-487">El valor predeterminado es `https://aadB2CInstance.b2clogin.com/`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-487">The default value is `https://aadB2CInstance.b2clogin.com/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="9cfb0-488">Identificador de la directiva de registro e inicio de sesión de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-488">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="9cfb0-489">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-489">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="9cfb0-490">Instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-490">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="9cfb0-491">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-491">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="9cfb0-492">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-492">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="9cfb0-493">Identificador de cliente de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-493">The Client ID for this project.</span></span> <span data-ttu-id="9cfb0-494">Úselo con la autenticación `IndividualB2C`, `SingleOrg` o `Individual` en escenarios independientes.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-494">Use with `IndividualB2C`, `SingleOrg`, or `Individual` authentication in standalone scenarios.</span></span> <span data-ttu-id="9cfb0-495">El valor predeterminado es `33333333-3333-3333-33333333333333333`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-495">The default value is `33333333-3333-3333-33333333333333333`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="9cfb0-496">Dominio del inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-496">The domain for the directory tenant.</span></span> <span data-ttu-id="9cfb0-497">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-497">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="9cfb0-498">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-498">The default value is `qualified.domain.name`.</span></span>

- **`--app-id-uri <URI>`**

  <span data-ttu-id="9cfb0-499">El URI del id. de la aplicación de la API de servidor a la que quiere llamar.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-499">The App ID Uri for the server API you want to call.</span></span> <span data-ttu-id="9cfb0-500">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-500">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="9cfb0-501">El valor predeterminado es `api.id.uri`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-501">The default value is `api.id.uri`.</span></span>

- **`--api-client-id <ID>`**

  <span data-ttu-id="9cfb0-502">El id. de cliente de la API que el servidor hospeda.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-502">The Client ID for the API that the server hosts.</span></span> <span data-ttu-id="9cfb0-503">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-503">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="9cfb0-504">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-504">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`-s|--default-scope <SCOPE>`**

  <span data-ttu-id="9cfb0-505">El ámbito de la API que el cliente debe solicitar para aprovisionar un token de acceso.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-505">The API scope the client needs to request to provision an access token.</span></span> <span data-ttu-id="9cfb0-506">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-506">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="9cfb0-507">El valor predeterminado es `user_impersonation`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-507">The default value is `user_impersonation`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="9cfb0-508">Identificador de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-508">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="9cfb0-509">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-509">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="9cfb0-510">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-510">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="9cfb0-511">Concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-511">Allows this application read-access to the directory.</span></span> <span data-ttu-id="9cfb0-512">Solo se aplica a la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-512">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="9cfb0-513">Excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-513">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-p|--pwa`**

  <span data-ttu-id="9cfb0-514">Genera una aplicación web progresiva (PWA) que admite la instalación y el uso sin conexión.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-514">produces a Progressive Web Application (PWA) supporting installation and offline use.</span></span>

- **`--no-https`**

  <span data-ttu-id="9cfb0-515">Desactiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-515">Turns off HTTPS.</span></span> <span data-ttu-id="9cfb0-516">Esta opción solo se aplica si no se usan `Individual`, `IndividualB2C` o `SingleOrg` en `--auth`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-516">This option only applies if `Individual`, `IndividualB2C`, or `SingleOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="9cfb0-517">Especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-517">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="9cfb0-518">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-518">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--called-api-url <URL>`**

  <span data-ttu-id="9cfb0-519">Dirección URL de la API que se va a llamar desde la aplicación web.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-519">URL of the API to call from the web app.</span></span> <span data-ttu-id="9cfb0-520">Solo se aplica a la autenticación `SingleOrg` o `IndividualB2C` sin un host especificado de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-520">Only applies to `SingleOrg` or `IndividualB2C` authentication without an ASP.NET Core host specified.</span></span> <span data-ttu-id="9cfb0-521">El valor predeterminado es `https://graph.microsoft.com/v1.0/me`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-521">The default value is `https://graph.microsoft.com/v1.0/me`.</span></span>

- **`--calls-graph`**

  <span data-ttu-id="9cfb0-522">Especifica si la aplicación web llama a Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-522">Specifies if the web app calls Microsoft Graph.</span></span> <span data-ttu-id="9cfb0-523">Solo se aplica a la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-523">Only applies to `SingleOrg` authentication.</span></span>

- **`--called-api-scopes <SCOPES>`**

  <span data-ttu-id="9cfb0-524">Ámbitos para solicitar llamar a la API desde la aplicación web.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-524">Scopes to request to call the API from the web app.</span></span> <span data-ttu-id="9cfb0-525">Solo se aplica a la autenticación `SingleOrg` o `IndividualB2C` sin un host especificado de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-525">Only applies to `SingleOrg` or `IndividualB2C` authentication without an ASP.NET Core host specified.</span></span> <span data-ttu-id="9cfb0-526">De manera predeterminada, es `user.read`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-526">The default is `user.read`.</span></span>

<span data-ttu-id="9cfb0-527">\*\*_</span><span class="sxs-lookup"><span data-stu-id="9cfb0-527">\*\*_</span></span>

### <a name="web"></a><span data-ttu-id="9cfb0-528">web</span><span class="sxs-lookup"><span data-stu-id="9cfb0-528">web</span></span>

- <span data-ttu-id="9cfb0-529">_ *`--exclude-launch-settings`*\*</span><span class="sxs-lookup"><span data-stu-id="9cfb0-529">_ *`--exclude-launch-settings`*\*</span></span>

  <span data-ttu-id="9cfb0-530">Excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-530">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="9cfb0-531">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-531">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="9cfb0-532">Opción no disponible en el SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-532">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="9cfb0-533">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="9cfb0-533">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="9cfb0-534">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="9cfb0-534">SDK version</span></span> | <span data-ttu-id="9cfb0-535">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="9cfb0-535">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="9cfb0-536">3.1</span><span class="sxs-lookup"><span data-stu-id="9cfb0-536">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="9cfb0-537">3.0</span><span class="sxs-lookup"><span data-stu-id="9cfb0-537">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="9cfb0-538">2.1</span><span class="sxs-lookup"><span data-stu-id="9cfb0-538">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="9cfb0-539">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-539">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="9cfb0-540">Desactiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-540">Turns off HTTPS.</span></span>

<span data-ttu-id="9cfb0-541">\*\*_</span><span class="sxs-lookup"><span data-stu-id="9cfb0-541">\*\*_</span></span>

### <a name="mvc-webapp"></a><a name="web-options"></a> <span data-ttu-id="9cfb0-542">mvc, webapp</span><span class="sxs-lookup"><span data-stu-id="9cfb0-542">mvc, webapp</span></span>

- <span data-ttu-id="9cfb0-543">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="9cfb0-543">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="9cfb0-544">Tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-544">The type of authentication to use.</span></span> <span data-ttu-id="9cfb0-545">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="9cfb0-545">The possible values are:</span></span>

  - <span data-ttu-id="9cfb0-546">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="9cfb0-546">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="9cfb0-547">`Individual`: autenticación individual.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-547">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="9cfb0-548">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-548">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="9cfb0-549">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-549">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="9cfb0-550">`MultiOrg`: autenticación organizativa para varios inquilinos.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-550">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="9cfb0-551">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-551">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="9cfb0-552">Instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-552">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="9cfb0-553">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-553">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="9cfb0-554">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-554">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="9cfb0-555">Identificador de la directiva de registro e inicio de sesión de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-555">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="9cfb0-556">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-556">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="9cfb0-557">Identificador de la directiva de restablecimiento de contraseñas de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-557">The reset password policy ID for this project.</span></span> <span data-ttu-id="9cfb0-558">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-558">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="9cfb0-559">Identificador de la directiva de edición de perfiles de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-559">The edit profile policy ID for this project.</span></span> <span data-ttu-id="9cfb0-560">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-560">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="9cfb0-561">Instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-561">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="9cfb0-562">Úsela con las autenticaciones `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-562">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="9cfb0-563">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-563">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="9cfb0-564">Identificador de cliente de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-564">The Client ID for this project.</span></span> <span data-ttu-id="9cfb0-565">Úsela con las autenticaciones `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-565">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="9cfb0-566">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-566">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="9cfb0-567">Dominio del inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-567">The domain for the directory tenant.</span></span> <span data-ttu-id="9cfb0-568">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-568">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="9cfb0-569">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-569">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="9cfb0-570">Identificador de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-570">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="9cfb0-571">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-571">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="9cfb0-572">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-572">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="9cfb0-573">Ruta de acceso de solicitud de la ruta de acceso de la base de la aplicación del URI de redirección.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-573">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="9cfb0-574">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-574">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="9cfb0-575">El valor predeterminado es `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-575">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="9cfb0-576">Concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-576">Allows this application read-access to the directory.</span></span> <span data-ttu-id="9cfb0-577">Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-577">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="9cfb0-578">Excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-578">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="9cfb0-579">Desactiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-579">Turns off HTTPS.</span></span> <span data-ttu-id="9cfb0-580">Esta opción solo se aplica si no se usan `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-580">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="9cfb0-581">Especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-581">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="9cfb0-582">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-582">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="9cfb0-583">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-583">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="9cfb0-584">Opción disponible a partir del SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-584">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="9cfb0-585">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="9cfb0-585">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="9cfb0-586">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="9cfb0-586">SDK version</span></span> | <span data-ttu-id="9cfb0-587">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="9cfb0-587">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="9cfb0-588">3.1</span><span class="sxs-lookup"><span data-stu-id="9cfb0-588">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="9cfb0-589">3.0</span><span class="sxs-lookup"><span data-stu-id="9cfb0-589">3.0</span></span>         | `netcoreapp3.0` |

- **`--no-restore`**

  <span data-ttu-id="9cfb0-590">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-590">Doesn't execute an implicit restore during project creation.</span></span>

- **`--use-browserlink`**

  <span data-ttu-id="9cfb0-591">Incluye BrowserLink en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-591">Includes BrowserLink in the project.</span></span> <span data-ttu-id="9cfb0-592">Opción no disponible en el SDK de .NET Core 2.2 y 3.1.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-592">Option not available in .NET Core 2.2 and 3.1 SDK.</span></span>

- **`-rrc|--razor-runtime-compilation`**

  <span data-ttu-id="9cfb0-593">Determina si el proyecto está configurado para usar la [compilación en tiempo de ejecución de Razor](/aspnet/core/mvc/views/view-compilation#runtime-compilation) en las compilaciones de depuración.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-593">Determines if the project is configured to use [Razor runtime compilation](/aspnet/core/mvc/views/view-compilation#runtime-compilation) in Debug builds.</span></span> <span data-ttu-id="9cfb0-594">Opción disponible a partir del SDK de .NET Core 3.1.201.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-594">Option available since .NET Core 3.1.201 SDK.</span></span>

<span data-ttu-id="9cfb0-595">\*\*_</span><span class="sxs-lookup"><span data-stu-id="9cfb0-595">\*\*_</span></span>

### <a name="angular-react"></a><a name="spa"></a> <span data-ttu-id="9cfb0-596">angular, react</span><span class="sxs-lookup"><span data-stu-id="9cfb0-596">angular, react</span></span>

- <span data-ttu-id="9cfb0-597">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="9cfb0-597">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="9cfb0-598">Tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-598">The type of authentication to use.</span></span> <span data-ttu-id="9cfb0-599">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-599">Available since .NET Core 3.0 SDK.</span></span>
  
  <span data-ttu-id="9cfb0-600">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="9cfb0-600">The possible values are:</span></span>

  - <span data-ttu-id="9cfb0-601">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="9cfb0-601">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="9cfb0-602">`Individual`: autenticación individual.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-602">`Individual` - Individual authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="9cfb0-603">Excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-603">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="9cfb0-604">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-604">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="9cfb0-605">Desactiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-605">Turns off HTTPS.</span></span> <span data-ttu-id="9cfb0-606">Esta opción solo se aplica si la autenticación es `None`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-606">This option only applies if authentication is `None`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="9cfb0-607">Especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-607">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="9cfb0-608">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-608">Only applies to `Individual` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="9cfb0-609">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-609">Available since .NET Core 3.0 SDK.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="9cfb0-610">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-610">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="9cfb0-611">Opción no disponible en el SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-611">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="9cfb0-612">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="9cfb0-612">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="9cfb0-613">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="9cfb0-613">SDK version</span></span> | <span data-ttu-id="9cfb0-614">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="9cfb0-614">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="9cfb0-615">3.1</span><span class="sxs-lookup"><span data-stu-id="9cfb0-615">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="9cfb0-616">3.0</span><span class="sxs-lookup"><span data-stu-id="9cfb0-616">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="9cfb0-617">2.1</span><span class="sxs-lookup"><span data-stu-id="9cfb0-617">2.1</span></span>         | `netcoreapp2.0` |

<span data-ttu-id="9cfb0-618">\*\*_</span><span class="sxs-lookup"><span data-stu-id="9cfb0-618">\*\*_</span></span>

### <a name="reactredux"></a><span data-ttu-id="9cfb0-619">reactredux</span><span class="sxs-lookup"><span data-stu-id="9cfb0-619">reactredux</span></span>

- <span data-ttu-id="9cfb0-620">_ *`--exclude-launch-settings`*\*</span><span class="sxs-lookup"><span data-stu-id="9cfb0-620">_ *`--exclude-launch-settings`*\*</span></span>

  <span data-ttu-id="9cfb0-621">Excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-621">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="9cfb0-622">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-622">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="9cfb0-623">Opción no disponible en el SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-623">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="9cfb0-624">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="9cfb0-624">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="9cfb0-625">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="9cfb0-625">SDK version</span></span> | <span data-ttu-id="9cfb0-626">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="9cfb0-626">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="9cfb0-627">3.1</span><span class="sxs-lookup"><span data-stu-id="9cfb0-627">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="9cfb0-628">3.0</span><span class="sxs-lookup"><span data-stu-id="9cfb0-628">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="9cfb0-629">2.1</span><span class="sxs-lookup"><span data-stu-id="9cfb0-629">2.1</span></span>         | `netcoreapp2.0` |

- **`--no-restore`**

  <span data-ttu-id="9cfb0-630">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-630">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="9cfb0-631">Desactiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-631">Turns off HTTPS.</span></span>

<span data-ttu-id="9cfb0-632">\*\*_</span><span class="sxs-lookup"><span data-stu-id="9cfb0-632">\*\*_</span></span>

### <a name="razorclasslib"></a><span data-ttu-id="9cfb0-633">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="9cfb0-633">razorclasslib</span></span>

- <span data-ttu-id="9cfb0-634">_ *`--no-restore`*\*</span><span class="sxs-lookup"><span data-stu-id="9cfb0-634">_ *`--no-restore`*\*</span></span>

  <span data-ttu-id="9cfb0-635">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-635">Doesn't execute an implicit restore during project creation.</span></span>

- **`-s|--support-pages-and-views`**

  <span data-ttu-id="9cfb0-636">Permite agregar vistas y páginas de Razor tradicionales además de los componentes a esta biblioteca.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-636">Supports adding traditional Razor pages and Views in addition to components to this library.</span></span> <span data-ttu-id="9cfb0-637">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-637">Available since .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="9cfb0-638">\*\*_</span><span class="sxs-lookup"><span data-stu-id="9cfb0-638">\*\*_</span></span>
  
### <a name="webapi"></a><span data-ttu-id="9cfb0-639">webapi</span><span class="sxs-lookup"><span data-stu-id="9cfb0-639">webapi</span></span>

- <span data-ttu-id="9cfb0-640">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span><span class="sxs-lookup"><span data-stu-id="9cfb0-640">_ *`-au|--auth <AUTHENTICATION_TYPE>`*\*</span></span>

  <span data-ttu-id="9cfb0-641">Tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-641">The type of authentication to use.</span></span> <span data-ttu-id="9cfb0-642">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="9cfb0-642">The possible values are:</span></span>

  - <span data-ttu-id="9cfb0-643">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="9cfb0-643">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="9cfb0-644">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-644">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="9cfb0-645">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-645">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="9cfb0-646">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-646">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="9cfb0-647">Instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-647">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="9cfb0-648">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-648">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="9cfb0-649">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-649">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="9cfb0-650">Identificador de la directiva de registro e inicio de sesión de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-650">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="9cfb0-651">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-651">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="9cfb0-652">Instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-652">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="9cfb0-653">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-653">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="9cfb0-654">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-654">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="9cfb0-655">Identificador de cliente de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-655">The Client ID for this project.</span></span> <span data-ttu-id="9cfb0-656">Úsela con las autenticaciones `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-656">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="9cfb0-657">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-657">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="9cfb0-658">Dominio del inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-658">The domain for the directory tenant.</span></span> <span data-ttu-id="9cfb0-659">Úsela con las autenticaciones `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-659">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="9cfb0-660">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-660">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="9cfb0-661">Identificador de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-661">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="9cfb0-662">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-662">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="9cfb0-663">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-663">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="9cfb0-664">Concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-664">Allows this application read-access to the directory.</span></span> <span data-ttu-id="9cfb0-665">Solo se aplica a la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-665">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="9cfb0-666">Excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-666">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="9cfb0-667">Desactiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-667">Turns off HTTPS.</span></span> <span data-ttu-id="9cfb0-668">`app.UseHsts` y `app.UseHttpsRedirection` no se agregan a `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-668">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="9cfb0-669">Esta opción solo se aplica si no se usan `IndividualB2C` o `SingleOrg` en la autenticación.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-669">This option only applies if `IndividualB2C` or `SingleOrg` aren't being used for authentication.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="9cfb0-670">Especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-670">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="9cfb0-671">Solo se aplica a la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-671">Only applies to `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="9cfb0-672">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-672">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="9cfb0-673">Opción no disponible en el SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-673">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="9cfb0-674">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="9cfb0-674">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="9cfb0-675">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="9cfb0-675">SDK version</span></span> | <span data-ttu-id="9cfb0-676">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="9cfb0-676">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="9cfb0-677">3.1</span><span class="sxs-lookup"><span data-stu-id="9cfb0-677">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="9cfb0-678">3.0</span><span class="sxs-lookup"><span data-stu-id="9cfb0-678">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="9cfb0-679">2.1</span><span class="sxs-lookup"><span data-stu-id="9cfb0-679">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="9cfb0-680">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-680">Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="9cfb0-681">\*\*_</span><span class="sxs-lookup"><span data-stu-id="9cfb0-681">\*\*_</span></span>

### <a name="globaljson"></a><span data-ttu-id="9cfb0-682">globaljson</span><span class="sxs-lookup"><span data-stu-id="9cfb0-682">globaljson</span></span>

- <span data-ttu-id="9cfb0-683">_ *`--sdk-version <VERSION_NUMBER>`*\*</span><span class="sxs-lookup"><span data-stu-id="9cfb0-683">_ *`--sdk-version <VERSION_NUMBER>`*\*</span></span>

  <span data-ttu-id="9cfb0-684">Especifica la versión del SDK de .NET Core que se usará en el archivo *global.json*.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-684">Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

***

## <a name="examples"></a><span data-ttu-id="9cfb0-685">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="9cfb0-685">Examples</span></span>

- <span data-ttu-id="9cfb0-686">Creación de un proyecto de aplicación de consola de C# mediante la especificación del nombre de plantilla:</span><span class="sxs-lookup"><span data-stu-id="9cfb0-686">Create a C# console application project by specifying the template name:</span></span>

  ```dotnetcli
  dotnet new "Console Application"
  ```

- <span data-ttu-id="9cfb0-687">Creación de un proyecto de aplicación de consola con F# en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="9cfb0-687">Create an F# console application project in the current directory:</span></span>

  ```dotnetcli
  dotnet new console -lang "F#"
  ```

- <span data-ttu-id="9cfb0-688">Creación de un proyecto de biblioteca de clases de .NET Standard en el directorio especificado:</span><span class="sxs-lookup"><span data-stu-id="9cfb0-688">Create a .NET Standard class library project in the specified directory:</span></span>

  ```dotnetcli
  dotnet new classlib -lang VB -o MyLibrary
  ```

- <span data-ttu-id="9cfb0-689">Creación de un proyecto MVC de ASP.NET Core C# en el directorio actual sin autenticación:</span><span class="sxs-lookup"><span data-stu-id="9cfb0-689">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

  ```dotnetcli
  dotnet new mvc -au None
  ```

- <span data-ttu-id="9cfb0-690">Creación de un proyecto de xUnit:</span><span class="sxs-lookup"><span data-stu-id="9cfb0-690">Create a new xUnit project:</span></span>

  ```dotnetcli
  dotnet new xunit
  ```

- <span data-ttu-id="9cfb0-691">Enumeración de todas las plantillas disponibles en las plantillas de aplicación de página única (SPA):</span><span class="sxs-lookup"><span data-stu-id="9cfb0-691">List all templates available for Single Page Application (SPA) templates:</span></span>

  ```dotnetcli
  dotnet new spa -l
  ```

- <span data-ttu-id="9cfb0-692">Enumeración de todas las plantillas que coinciden con la subcadena *we*.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-692">List all templates matching the *we* substring.</span></span> <span data-ttu-id="9cfb0-693">No se encuentra ninguna coincidencia exacta, por lo que se ejecuta la coincidencia de subcadena con las columnas de nombre corto y de nombre.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-693">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

  ```dotnetcli
  dotnet new we -l
  ```

- <span data-ttu-id="9cfb0-694">Intento de invocar a la plantilla que coincide con *ng*.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-694">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="9cfb0-695">Si no se puede determinar una única coincidencia, se enumeran las plantillas que son coincidencias parciales.</span><span class="sxs-lookup"><span data-stu-id="9cfb0-695">If a single match can't be determined, list the templates that are partial matches.</span></span>

  ```dotnetcli
  dotnet new ng
  ```

- <span data-ttu-id="9cfb0-696">Instalación de la versión 2.0 de las plantillas de SPA de ASP.NET Core:</span><span class="sxs-lookup"><span data-stu-id="9cfb0-696">Install version 2.0 of the SPA templates for ASP.NET Core:</span></span>

  ```dotnetcli
  dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0
  ```

- <span data-ttu-id="9cfb0-697">Enumeración de las plantillas instaladas y detalles sobre ellas, incluido cómo desinstalarlas:</span><span class="sxs-lookup"><span data-stu-id="9cfb0-697">List the installed templates and details about them, including how to uninstall them:</span></span>

  ```dotnetcli
  dotnet new -u
  ```

- <span data-ttu-id="9cfb0-698">Creación de un archivo *global.json* en el directorio actual al establecer la versión del SDK en 3.1.101:</span><span class="sxs-lookup"><span data-stu-id="9cfb0-698">Create a *global.json* in the current directory setting the SDK version to 3.1.101:</span></span>

  ```dotnetcli
  dotnet new globaljson --sdk-version 3.1.101
  ```

## <a name="see-also"></a><span data-ttu-id="9cfb0-699">Vea también</span><span class="sxs-lookup"><span data-stu-id="9cfb0-699">See also</span></span>

- [<span data-ttu-id="9cfb0-700">Plantillas personalizadas para dotnet new</span><span class="sxs-lookup"><span data-stu-id="9cfb0-700">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="9cfb0-701">Creación de una plantilla personalizada para dotnet new</span><span class="sxs-lookup"><span data-stu-id="9cfb0-701">Create a custom template for dotnet new</span></span>](../tutorials/cli-templates-create-item-template.md)
- [<span data-ttu-id="9cfb0-702">Repositorio de GitHub dotnet/dotnet-template-samples</span><span class="sxs-lookup"><span data-stu-id="9cfb0-702">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- <span data-ttu-id="9cfb0-703">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new) (Plantillas disponibles para dotnet new)</span><span class="sxs-lookup"><span data-stu-id="9cfb0-703">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)</span></span>
