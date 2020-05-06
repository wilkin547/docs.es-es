---
title: Comando dotnet new
description: El comando dotnet new crea proyectos de .NET Core basados en la plantilla especificada.
ms.date: 04/10/2020
ms.openlocfilehash: 9a68baafa7ac3e6ad2fdc8f1c6e8621d6e15f1ff
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2020
ms.locfileid: "82506862"
---
# <a name="dotnet-new"></a><span data-ttu-id="b6eef-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="b6eef-103">dotnet new</span></span>

<span data-ttu-id="b6eef-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.0 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="b6eef-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="b6eef-105">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="b6eef-105">Name</span></span>

<span data-ttu-id="b6eef-106">`dotnet new`: crea un nuevo proyecto, archivo de configuración o solución según la plantilla especificada.</span><span class="sxs-lookup"><span data-stu-id="b6eef-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="b6eef-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="b6eef-107">Synopsis</span></span>

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install {PATH|NUGET_ID}]
    [-lang|--language {C#|F#|VB}] [-n|--name <OUTPUT_NAME>]
    [--nuget-source <SOURCE>] [-o|--output <OUTPUT_DIRECTORY>]
    [-u|--uninstall] [--update-apply] [--update-check] [Template options]

dotnet new <TEMPLATE> [-l|--list] [--type <TYPE>]

dotnet new -h|--help
```

## <a name="description"></a><span data-ttu-id="b6eef-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="b6eef-108">Description</span></span>

<span data-ttu-id="b6eef-109">El comando `dotnet new` crea un proyecto de .NET Core u otros artefactos basados en una plantilla.</span><span class="sxs-lookup"><span data-stu-id="b6eef-109">The `dotnet new` command creates a .NET Core project or other artifacts based on a template.</span></span>

<span data-ttu-id="b6eef-110">El comando llama al [motor de plantillas](https://github.com/dotnet/templating) para crear los artefactos en el disco basándose en las opciones y la plantilla especificadas.</span><span class="sxs-lookup"><span data-stu-id="b6eef-110">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="b6eef-111">Restauración implícita</span><span class="sxs-lookup"><span data-stu-id="b6eef-111">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="b6eef-112">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b6eef-112">Arguments</span></span>

- **`TEMPLATE`**

  <span data-ttu-id="b6eef-113">La plantilla de la que se va a crear una instancia cuando se invoca el comando.</span><span class="sxs-lookup"><span data-stu-id="b6eef-113">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="b6eef-114">Cada plantilla puede tener opciones específicas que puede pasar.</span><span class="sxs-lookup"><span data-stu-id="b6eef-114">Each template might have specific options you can pass.</span></span> <span data-ttu-id="b6eef-115">Para obtener más información, vea [Opciones de plantilla](#template-options).</span><span class="sxs-lookup"><span data-stu-id="b6eef-115">For more information, see [Template options](#template-options).</span></span>

  <span data-ttu-id="b6eef-116">Puede ejecutar `dotnet new --list` o `dotnet new -l` para ver una lista de todas las plantillas instaladas.</span><span class="sxs-lookup"><span data-stu-id="b6eef-116">You can run `dotnet new --list` or `dotnet new -l` to see a list of all installed templates.</span></span> <span data-ttu-id="b6eef-117">Si el valor `TEMPLATE` no es una coincidencia exacta con el texto de la columna **Plantillas** o **Nombre corto** de la tabla devuelta, se realiza una coincidencia de subcadena con esas dos columnas.</span><span class="sxs-lookup"><span data-stu-id="b6eef-117">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column from the returned table, a substring match is performed on those two columns.</span></span>

  <span data-ttu-id="b6eef-118">A partir del SDK de .NET Core 3.0, la CLI busca plantillas en NuGet.org al invocar el comando `dotnet new` en las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="b6eef-118">Starting with .NET Core 3.0 SDK, the CLI searches for templates in NuGet.org when you invoke the `dotnet new` command in the following conditions:</span></span>

  - <span data-ttu-id="b6eef-119">Si la CLI no encuentra ninguna coincidencia de plantilla al invocar `dotnet new`, ni siquiera parcial.</span><span class="sxs-lookup"><span data-stu-id="b6eef-119">If the CLI can't find a template match when invoking `dotnet new`, not even partial.</span></span>
  - <span data-ttu-id="b6eef-120">Si hay disponible una versión más reciente de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="b6eef-120">If there's a newer version of the template available.</span></span> <span data-ttu-id="b6eef-121">En este caso, se crea el proyecto o el artefacto, pero la CLI le advierte de que hay una versión actualizada de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="b6eef-121">In this case, the project or artifact is created but the CLI warns you about an updated version of the template.</span></span>

  <span data-ttu-id="b6eef-122">En la tabla siguiente se muestran las plantillas que vienen preinstaladas en el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b6eef-122">The following table shows the templates that come pre-installed with the .NET Core SDK.</span></span> <span data-ttu-id="b6eef-123">El lenguaje predeterminado de la plantilla se muestra entre corchetes.</span><span class="sxs-lookup"><span data-stu-id="b6eef-123">The default language for the template is shown inside the brackets.</span></span> <span data-ttu-id="b6eef-124">Haga clic en el vínculo del nombre corto para ver las opciones específicas de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="b6eef-124">Click on the short name link to see the specific template options.</span></span>

| <span data-ttu-id="b6eef-125">Plantillas</span><span class="sxs-lookup"><span data-stu-id="b6eef-125">Templates</span></span>                                    | <span data-ttu-id="b6eef-126">Nombre corto</span><span class="sxs-lookup"><span data-stu-id="b6eef-126">Short name</span></span>                      | <span data-ttu-id="b6eef-127">Lenguaje</span><span class="sxs-lookup"><span data-stu-id="b6eef-127">Language</span></span>     | <span data-ttu-id="b6eef-128">Etiquetas</span><span class="sxs-lookup"><span data-stu-id="b6eef-128">Tags</span></span>                                  | <span data-ttu-id="b6eef-129">Inclusión</span><span class="sxs-lookup"><span data-stu-id="b6eef-129">Introduced</span></span> |
|----------------------------------------------|---------------------------------|--------------|---------------------------------------|------------|
| <span data-ttu-id="b6eef-130">Aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="b6eef-130">Console Application</span></span>                          | [<span data-ttu-id="b6eef-131">console</span><span class="sxs-lookup"><span data-stu-id="b6eef-131">console</span></span>](#console)             | <span data-ttu-id="b6eef-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="b6eef-132">[C#], F#, VB</span></span> | <span data-ttu-id="b6eef-133">Común/Consola</span><span class="sxs-lookup"><span data-stu-id="b6eef-133">Common/Console</span></span>                        | <span data-ttu-id="b6eef-134">1.0</span><span class="sxs-lookup"><span data-stu-id="b6eef-134">1.0</span></span>        |
| <span data-ttu-id="b6eef-135">Biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="b6eef-135">Class library</span></span>                                | [<span data-ttu-id="b6eef-136">classlib</span><span class="sxs-lookup"><span data-stu-id="b6eef-136">classlib</span></span>](#classlib)           | <span data-ttu-id="b6eef-137">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="b6eef-137">[C#], F#, VB</span></span> | <span data-ttu-id="b6eef-138">Común/Biblioteca</span><span class="sxs-lookup"><span data-stu-id="b6eef-138">Common/Library</span></span>                        | <span data-ttu-id="b6eef-139">1.0</span><span class="sxs-lookup"><span data-stu-id="b6eef-139">1.0</span></span>        |
| <span data-ttu-id="b6eef-140">Aplicación WPF</span><span class="sxs-lookup"><span data-stu-id="b6eef-140">WPF Application</span></span>                              | [<span data-ttu-id="b6eef-141">wpf</span><span class="sxs-lookup"><span data-stu-id="b6eef-141">wpf</span></span>](#wpf)                     | <span data-ttu-id="b6eef-142">[C#]</span><span class="sxs-lookup"><span data-stu-id="b6eef-142">[C#]</span></span>         | <span data-ttu-id="b6eef-143">Común/WPF</span><span class="sxs-lookup"><span data-stu-id="b6eef-143">Common/WPF</span></span>                            | <span data-ttu-id="b6eef-144">3.0</span><span class="sxs-lookup"><span data-stu-id="b6eef-144">3.0</span></span>        |
| <span data-ttu-id="b6eef-145">Biblioteca de clases de WPF</span><span class="sxs-lookup"><span data-stu-id="b6eef-145">WPF Class library</span></span>                            | [<span data-ttu-id="b6eef-146">wpflib</span><span class="sxs-lookup"><span data-stu-id="b6eef-146">wpflib</span></span>](#wpf)                  | <span data-ttu-id="b6eef-147">[C#]</span><span class="sxs-lookup"><span data-stu-id="b6eef-147">[C#]</span></span>         | <span data-ttu-id="b6eef-148">Común/WPF</span><span class="sxs-lookup"><span data-stu-id="b6eef-148">Common/WPF</span></span>                            | <span data-ttu-id="b6eef-149">3.0</span><span class="sxs-lookup"><span data-stu-id="b6eef-149">3.0</span></span>        |
| <span data-ttu-id="b6eef-150">Biblioteca de controles personalizados WPF</span><span class="sxs-lookup"><span data-stu-id="b6eef-150">WPF Custom Control Library</span></span>                   | [<span data-ttu-id="b6eef-151">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="b6eef-151">wpfcustomcontrollib</span></span>](#wpf)     | <span data-ttu-id="b6eef-152">[C#]</span><span class="sxs-lookup"><span data-stu-id="b6eef-152">[C#]</span></span>         | <span data-ttu-id="b6eef-153">Común/WPF</span><span class="sxs-lookup"><span data-stu-id="b6eef-153">Common/WPF</span></span>                            | <span data-ttu-id="b6eef-154">3.0</span><span class="sxs-lookup"><span data-stu-id="b6eef-154">3.0</span></span>        |
| <span data-ttu-id="b6eef-155">Biblioteca de controles de usuario de WPF</span><span class="sxs-lookup"><span data-stu-id="b6eef-155">WPF User Control Library</span></span>                     | [<span data-ttu-id="b6eef-156">wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="b6eef-156">wpfusercontrollib</span></span>](#wpf)       | <span data-ttu-id="b6eef-157">[C#]</span><span class="sxs-lookup"><span data-stu-id="b6eef-157">[C#]</span></span>         | <span data-ttu-id="b6eef-158">Común/WPF</span><span class="sxs-lookup"><span data-stu-id="b6eef-158">Common/WPF</span></span>                            | <span data-ttu-id="b6eef-159">3.0</span><span class="sxs-lookup"><span data-stu-id="b6eef-159">3.0</span></span>        |
| <span data-ttu-id="b6eef-160">Aplicación de Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="b6eef-160">Windows Forms (WinForms) Application</span></span>         | [<span data-ttu-id="b6eef-161">winforms</span><span class="sxs-lookup"><span data-stu-id="b6eef-161">winforms</span></span>](#winforms)           | <span data-ttu-id="b6eef-162">[C#]</span><span class="sxs-lookup"><span data-stu-id="b6eef-162">[C#]</span></span>         | <span data-ttu-id="b6eef-163">Común/WinForms</span><span class="sxs-lookup"><span data-stu-id="b6eef-163">Common/WinForms</span></span>                       | <span data-ttu-id="b6eef-164">3.0</span><span class="sxs-lookup"><span data-stu-id="b6eef-164">3.0</span></span>        |
| <span data-ttu-id="b6eef-165">Biblioteca de clases de Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="b6eef-165">Windows Forms (WinForms) Class library</span></span>       | [<span data-ttu-id="b6eef-166">winformslib</span><span class="sxs-lookup"><span data-stu-id="b6eef-166">winformslib</span></span>](#winforms)        | <span data-ttu-id="b6eef-167">[C#]</span><span class="sxs-lookup"><span data-stu-id="b6eef-167">[C#]</span></span>         | <span data-ttu-id="b6eef-168">Común/WinForms</span><span class="sxs-lookup"><span data-stu-id="b6eef-168">Common/WinForms</span></span>                       | <span data-ttu-id="b6eef-169">3.0</span><span class="sxs-lookup"><span data-stu-id="b6eef-169">3.0</span></span>        |
| <span data-ttu-id="b6eef-170">Servicio Worker</span><span class="sxs-lookup"><span data-stu-id="b6eef-170">Worker Service</span></span>                               | [<span data-ttu-id="b6eef-171">worker</span><span class="sxs-lookup"><span data-stu-id="b6eef-171">worker</span></span>](#web-others)           | <span data-ttu-id="b6eef-172">[C#]</span><span class="sxs-lookup"><span data-stu-id="b6eef-172">[C#]</span></span>         | <span data-ttu-id="b6eef-173">Común/Worker/Web</span><span class="sxs-lookup"><span data-stu-id="b6eef-173">Common/Worker/Web</span></span>                     | <span data-ttu-id="b6eef-174">3.0</span><span class="sxs-lookup"><span data-stu-id="b6eef-174">3.0</span></span>        |
| <span data-ttu-id="b6eef-175">Proyecto de prueba unitaria</span><span class="sxs-lookup"><span data-stu-id="b6eef-175">Unit Test Project</span></span>                            | [<span data-ttu-id="b6eef-176">mstest</span><span class="sxs-lookup"><span data-stu-id="b6eef-176">mstest</span></span>](#test)                 | <span data-ttu-id="b6eef-177">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="b6eef-177">[C#], F#, VB</span></span> | <span data-ttu-id="b6eef-178">Prueba/MSTest</span><span class="sxs-lookup"><span data-stu-id="b6eef-178">Test/MSTest</span></span>                           | <span data-ttu-id="b6eef-179">1.0</span><span class="sxs-lookup"><span data-stu-id="b6eef-179">1.0</span></span>        |
| <span data-ttu-id="b6eef-180">Proyecto de prueba de NUnit 3</span><span class="sxs-lookup"><span data-stu-id="b6eef-180">NUnit 3 Test Project</span></span>                         | [<span data-ttu-id="b6eef-181">nunit</span><span class="sxs-lookup"><span data-stu-id="b6eef-181">nunit</span></span>](#nunit)                  | <span data-ttu-id="b6eef-182">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="b6eef-182">[C#], F#, VB</span></span> | <span data-ttu-id="b6eef-183">Prueba/NUnit</span><span class="sxs-lookup"><span data-stu-id="b6eef-183">Test/NUnit</span></span>                            | <span data-ttu-id="b6eef-184">2.1.400</span><span class="sxs-lookup"><span data-stu-id="b6eef-184">2.1.400</span></span>    |
| <span data-ttu-id="b6eef-185">Elemento de prueba de NUnit 3</span><span class="sxs-lookup"><span data-stu-id="b6eef-185">NUnit 3 Test Item</span></span>                            | `nunit-test`                    | <span data-ttu-id="b6eef-186">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="b6eef-186">[C#], F#, VB</span></span> | <span data-ttu-id="b6eef-187">Prueba/NUnit</span><span class="sxs-lookup"><span data-stu-id="b6eef-187">Test/NUnit</span></span>                            | <span data-ttu-id="b6eef-188">2.2</span><span class="sxs-lookup"><span data-stu-id="b6eef-188">2.2</span></span>        |
| <span data-ttu-id="b6eef-189">Proyecto de prueba de xUnit</span><span class="sxs-lookup"><span data-stu-id="b6eef-189">xUnit Test Project</span></span>                           | [<span data-ttu-id="b6eef-190">xunit</span><span class="sxs-lookup"><span data-stu-id="b6eef-190">xunit</span></span>](#test)                  | <span data-ttu-id="b6eef-191">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="b6eef-191">[C#], F#, VB</span></span> | <span data-ttu-id="b6eef-192">Prueba/xUnit</span><span class="sxs-lookup"><span data-stu-id="b6eef-192">Test/xUnit</span></span>                            | <span data-ttu-id="b6eef-193">1.0</span><span class="sxs-lookup"><span data-stu-id="b6eef-193">1.0</span></span>        |
| <span data-ttu-id="b6eef-194">Componente Razor</span><span class="sxs-lookup"><span data-stu-id="b6eef-194">Razor Component</span></span>                              | `razorcomponent`                | <span data-ttu-id="b6eef-195">[C#]</span><span class="sxs-lookup"><span data-stu-id="b6eef-195">[C#]</span></span>         | <span data-ttu-id="b6eef-196">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="b6eef-196">Web/ASP.NET</span></span>                           | <span data-ttu-id="b6eef-197">3.0</span><span class="sxs-lookup"><span data-stu-id="b6eef-197">3.0</span></span>        |
| <span data-ttu-id="b6eef-198">Página de Razor</span><span class="sxs-lookup"><span data-stu-id="b6eef-198">Razor Page</span></span>                                   | [<span data-ttu-id="b6eef-199">page</span><span class="sxs-lookup"><span data-stu-id="b6eef-199">page</span></span>](#page)                   | <span data-ttu-id="b6eef-200">[C#]</span><span class="sxs-lookup"><span data-stu-id="b6eef-200">[C#]</span></span>         | <span data-ttu-id="b6eef-201">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="b6eef-201">Web/ASP.NET</span></span>                           | <span data-ttu-id="b6eef-202">2.0</span><span class="sxs-lookup"><span data-stu-id="b6eef-202">2.0</span></span>        |
| <span data-ttu-id="b6eef-203">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="b6eef-203">MVC ViewImports</span></span>                              | [<span data-ttu-id="b6eef-204">viewimports</span><span class="sxs-lookup"><span data-stu-id="b6eef-204">viewimports</span></span>](#namespace)       | <span data-ttu-id="b6eef-205">[C#]</span><span class="sxs-lookup"><span data-stu-id="b6eef-205">[C#]</span></span>         | <span data-ttu-id="b6eef-206">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="b6eef-206">Web/ASP.NET</span></span>                           | <span data-ttu-id="b6eef-207">2.0</span><span class="sxs-lookup"><span data-stu-id="b6eef-207">2.0</span></span>        |
| <span data-ttu-id="b6eef-208">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="b6eef-208">MVC ViewStart</span></span>                                | `viewstart`                     | <span data-ttu-id="b6eef-209">[C#]</span><span class="sxs-lookup"><span data-stu-id="b6eef-209">[C#]</span></span>         | <span data-ttu-id="b6eef-210">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="b6eef-210">Web/ASP.NET</span></span>                           | <span data-ttu-id="b6eef-211">2.0</span><span class="sxs-lookup"><span data-stu-id="b6eef-211">2.0</span></span>        |
| <span data-ttu-id="b6eef-212">Aplicación de servidor Blazor</span><span class="sxs-lookup"><span data-stu-id="b6eef-212">Blazor Server App</span></span>                            | [<span data-ttu-id="b6eef-213">blazorserver</span><span class="sxs-lookup"><span data-stu-id="b6eef-213">blazorserver</span></span>](#blazorserver)   | <span data-ttu-id="b6eef-214">[C#]</span><span class="sxs-lookup"><span data-stu-id="b6eef-214">[C#]</span></span>         | <span data-ttu-id="b6eef-215">Web/Blazor</span><span class="sxs-lookup"><span data-stu-id="b6eef-215">Web/Blazor</span></span>                            | <span data-ttu-id="b6eef-216">3.0</span><span class="sxs-lookup"><span data-stu-id="b6eef-216">3.0</span></span>        |
| <span data-ttu-id="b6eef-217">Vacío de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b6eef-217">ASP.NET Core Empty</span></span>                           | [<span data-ttu-id="b6eef-218">web</span><span class="sxs-lookup"><span data-stu-id="b6eef-218">web</span></span>](#web)                     | <span data-ttu-id="b6eef-219">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="b6eef-219">[C#], F#</span></span>     | <span data-ttu-id="b6eef-220">Web/Vacío</span><span class="sxs-lookup"><span data-stu-id="b6eef-220">Web/Empty</span></span>                             | <span data-ttu-id="b6eef-221">1.0</span><span class="sxs-lookup"><span data-stu-id="b6eef-221">1.0</span></span>        |
| <span data-ttu-id="b6eef-222">Aplicación web de ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="b6eef-222">ASP.NET Core Web App (Model-View-Controller)</span></span> | [<span data-ttu-id="b6eef-223">mvc</span><span class="sxs-lookup"><span data-stu-id="b6eef-223">mvc</span></span>](#web-options)             | <span data-ttu-id="b6eef-224">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="b6eef-224">[C#], F#</span></span>     | <span data-ttu-id="b6eef-225">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="b6eef-225">Web/MVC</span></span>                               | <span data-ttu-id="b6eef-226">1.0</span><span class="sxs-lookup"><span data-stu-id="b6eef-226">1.0</span></span>        |
| <span data-ttu-id="b6eef-227">Aplicación web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b6eef-227">ASP.NET Core Web App</span></span>                         | [<span data-ttu-id="b6eef-228">webapp, razor</span><span class="sxs-lookup"><span data-stu-id="b6eef-228">webapp, razor</span></span>](#web-options)   | <span data-ttu-id="b6eef-229">[C#]</span><span class="sxs-lookup"><span data-stu-id="b6eef-229">[C#]</span></span>         | <span data-ttu-id="b6eef-230">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="b6eef-230">Web/MVC/Razor Pages</span></span>                   | <span data-ttu-id="b6eef-231">2.2, 2.0</span><span class="sxs-lookup"><span data-stu-id="b6eef-231">2.2, 2.0</span></span>   |
| <span data-ttu-id="b6eef-232">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="b6eef-232">ASP.NET Core with Angular</span></span>                    | [<span data-ttu-id="b6eef-233">angular</span><span class="sxs-lookup"><span data-stu-id="b6eef-233">angular</span></span>](#spa)                 | <span data-ttu-id="b6eef-234">[C#]</span><span class="sxs-lookup"><span data-stu-id="b6eef-234">[C#]</span></span>         | <span data-ttu-id="b6eef-235">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="b6eef-235">Web/MVC/SPA</span></span>                           | <span data-ttu-id="b6eef-236">2.0</span><span class="sxs-lookup"><span data-stu-id="b6eef-236">2.0</span></span>        |
| <span data-ttu-id="b6eef-237">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="b6eef-237">ASP.NET Core with React.js</span></span>                   | [<span data-ttu-id="b6eef-238">react</span><span class="sxs-lookup"><span data-stu-id="b6eef-238">react</span></span>](#spa)                   | <span data-ttu-id="b6eef-239">[C#]</span><span class="sxs-lookup"><span data-stu-id="b6eef-239">[C#]</span></span>         | <span data-ttu-id="b6eef-240">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="b6eef-240">Web/MVC/SPA</span></span>                           | <span data-ttu-id="b6eef-241">2.0</span><span class="sxs-lookup"><span data-stu-id="b6eef-241">2.0</span></span>        |
| <span data-ttu-id="b6eef-242">ASP.NET Core con React.js y Redux</span><span class="sxs-lookup"><span data-stu-id="b6eef-242">ASP.NET Core with React.js and Redux</span></span>         | [<span data-ttu-id="b6eef-243">reactredux</span><span class="sxs-lookup"><span data-stu-id="b6eef-243">reactredux</span></span>](#reactredux)       | <span data-ttu-id="b6eef-244">[C#]</span><span class="sxs-lookup"><span data-stu-id="b6eef-244">[C#]</span></span>         | <span data-ttu-id="b6eef-245">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="b6eef-245">Web/MVC/SPA</span></span>                           | <span data-ttu-id="b6eef-246">2.0</span><span class="sxs-lookup"><span data-stu-id="b6eef-246">2.0</span></span>        |
| <span data-ttu-id="b6eef-247">Biblioteca de clases de Razor</span><span class="sxs-lookup"><span data-stu-id="b6eef-247">Razor Class Library</span></span>                          | [<span data-ttu-id="b6eef-248">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="b6eef-248">razorclasslib</span></span>](#razorclasslib) | <span data-ttu-id="b6eef-249">[C#]</span><span class="sxs-lookup"><span data-stu-id="b6eef-249">[C#]</span></span>         | <span data-ttu-id="b6eef-250">Web/Razor/Biblioteca/Biblioteca de clases de Razor</span><span class="sxs-lookup"><span data-stu-id="b6eef-250">Web/Razor/Library/Razor Class Library</span></span> | <span data-ttu-id="b6eef-251">2.1</span><span class="sxs-lookup"><span data-stu-id="b6eef-251">2.1</span></span>        |
| <span data-ttu-id="b6eef-252">API web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b6eef-252">ASP.NET Core Web API</span></span>                         | [<span data-ttu-id="b6eef-253">webapi</span><span class="sxs-lookup"><span data-stu-id="b6eef-253">webapi</span></span>](#webapi)               | <span data-ttu-id="b6eef-254">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="b6eef-254">[C#], F#</span></span>     | <span data-ttu-id="b6eef-255">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="b6eef-255">Web/WebAPI</span></span>                            | <span data-ttu-id="b6eef-256">1.0</span><span class="sxs-lookup"><span data-stu-id="b6eef-256">1.0</span></span>        |
| <span data-ttu-id="b6eef-257">Servicio gRPC de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b6eef-257">ASP.NET Core gRPC Service</span></span>                    | [<span data-ttu-id="b6eef-258">grpc</span><span class="sxs-lookup"><span data-stu-id="b6eef-258">grpc</span></span>](#web-others)             | <span data-ttu-id="b6eef-259">[C#]</span><span class="sxs-lookup"><span data-stu-id="b6eef-259">[C#]</span></span>         | <span data-ttu-id="b6eef-260">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="b6eef-260">Web/gRPC</span></span>                              | <span data-ttu-id="b6eef-261">3.0</span><span class="sxs-lookup"><span data-stu-id="b6eef-261">3.0</span></span>        |
| <span data-ttu-id="b6eef-262">Archivo dotnet gitignore</span><span class="sxs-lookup"><span data-stu-id="b6eef-262">dotnet gitignore file</span></span>                        | `gitignore`                     |              | <span data-ttu-id="b6eef-263">Configuración</span><span class="sxs-lookup"><span data-stu-id="b6eef-263">Config</span></span>                                | <span data-ttu-id="b6eef-264">3.0</span><span class="sxs-lookup"><span data-stu-id="b6eef-264">3.0</span></span>        |
| <span data-ttu-id="b6eef-265">archivo global.json</span><span class="sxs-lookup"><span data-stu-id="b6eef-265">global.json file</span></span>                             | [<span data-ttu-id="b6eef-266">globaljson</span><span class="sxs-lookup"><span data-stu-id="b6eef-266">globaljson</span></span>](#globaljson)       |              | <span data-ttu-id="b6eef-267">Configuración</span><span class="sxs-lookup"><span data-stu-id="b6eef-267">Config</span></span>                                | <span data-ttu-id="b6eef-268">2.0</span><span class="sxs-lookup"><span data-stu-id="b6eef-268">2.0</span></span>        |
| <span data-ttu-id="b6eef-269">Configuración de NuGet</span><span class="sxs-lookup"><span data-stu-id="b6eef-269">NuGet Config</span></span>                                 | `nugetconfig`                   |              | <span data-ttu-id="b6eef-270">Configuración</span><span class="sxs-lookup"><span data-stu-id="b6eef-270">Config</span></span>                                | <span data-ttu-id="b6eef-271">1.0</span><span class="sxs-lookup"><span data-stu-id="b6eef-271">1.0</span></span>        |
| <span data-ttu-id="b6eef-272">Archivo de manifiesto de la herramienta local dotnet</span><span class="sxs-lookup"><span data-stu-id="b6eef-272">Dotnet local tool manifest file</span></span>              | `tool-manifest`                 |              | <span data-ttu-id="b6eef-273">Configuración</span><span class="sxs-lookup"><span data-stu-id="b6eef-273">Config</span></span>                                | <span data-ttu-id="b6eef-274">3.0</span><span class="sxs-lookup"><span data-stu-id="b6eef-274">3.0</span></span>        |
| <span data-ttu-id="b6eef-275">Configuración web</span><span class="sxs-lookup"><span data-stu-id="b6eef-275">Web Config</span></span>                                   | `webconfig`                     |              | <span data-ttu-id="b6eef-276">Configuración</span><span class="sxs-lookup"><span data-stu-id="b6eef-276">Config</span></span>                                | <span data-ttu-id="b6eef-277">1.0</span><span class="sxs-lookup"><span data-stu-id="b6eef-277">1.0</span></span>        |
| <span data-ttu-id="b6eef-278">Archivo de solución</span><span class="sxs-lookup"><span data-stu-id="b6eef-278">Solution File</span></span>                                | `sln`                           |              | <span data-ttu-id="b6eef-279">Soluciones</span><span class="sxs-lookup"><span data-stu-id="b6eef-279">Solution</span></span>                              | <span data-ttu-id="b6eef-280">1.0</span><span class="sxs-lookup"><span data-stu-id="b6eef-280">1.0</span></span>        |
| <span data-ttu-id="b6eef-281">Archivo de búfer de protocolo</span><span class="sxs-lookup"><span data-stu-id="b6eef-281">Protocol Buffer File</span></span>                         | [<span data-ttu-id="b6eef-282">proto</span><span class="sxs-lookup"><span data-stu-id="b6eef-282">proto</span></span>](#namespace)             |              | <span data-ttu-id="b6eef-283">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="b6eef-283">Web/gRPC</span></span>                              | <span data-ttu-id="b6eef-284">3.0</span><span class="sxs-lookup"><span data-stu-id="b6eef-284">3.0</span></span>        |

## <a name="options"></a><span data-ttu-id="b6eef-285">Opciones</span><span class="sxs-lookup"><span data-stu-id="b6eef-285">Options</span></span>

- **`--dry-run`**

  <span data-ttu-id="b6eef-286">Muestra un resumen de lo que sucedería si se ejecutara el comando determinado y el resultado fuera la creación de una plantilla.</span><span class="sxs-lookup"><span data-stu-id="b6eef-286">Displays a summary of what would happen if the given command were run if it would result in a template creation.</span></span> <span data-ttu-id="b6eef-287">Disponible a partir del SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="b6eef-287">Available since .NET Core 2.2 SDK.</span></span>

- **`--force`**

  <span data-ttu-id="b6eef-288">Fuerza la generación de contenido incluso aunque se vayan a cambiar los archivos existentes.</span><span class="sxs-lookup"><span data-stu-id="b6eef-288">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="b6eef-289">Es necesario si la plantilla elegida invalidará los archivos existentes en el directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="b6eef-289">This is required when the template chosen would override existing files in the output directory.</span></span>

- **`-h|--help`**

  <span data-ttu-id="b6eef-290">Imprime la ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="b6eef-290">Prints out help for the command.</span></span> <span data-ttu-id="b6eef-291">Puede invocarse para el propio comando `dotnet new` o para cualquier plantilla.</span><span class="sxs-lookup"><span data-stu-id="b6eef-291">It can be invoked for the `dotnet new` command itself or for any template.</span></span> <span data-ttu-id="b6eef-292">Por ejemplo: `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-292">For example, `dotnet new mvc --help`.</span></span>

- **`-i|--install <PATH|NUGET_ID>`**

  <span data-ttu-id="b6eef-293">Instala un paquete de plantillas desde los parámetros `PATH` o `NUGET_ID` proporcionados.</span><span class="sxs-lookup"><span data-stu-id="b6eef-293">Installs a template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="b6eef-294">Si quiere instalar una versión preliminar de un paquete de plantilla, tendrá que especificar la versión en el formato de `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-294">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="b6eef-295">De forma predeterminada, `dotnet new` pasa \* para la versión, que representa la última versión estable del paquete.</span><span class="sxs-lookup"><span data-stu-id="b6eef-295">By default, `dotnet new` passes \* for the version, which represents the latest stable package version.</span></span> <span data-ttu-id="b6eef-296">Vea un ejemplo en la sección [Ejemplos](#examples).</span><span class="sxs-lookup"><span data-stu-id="b6eef-296">See an example in the [Examples](#examples) section.</span></span>
  
  <span data-ttu-id="b6eef-297">Si ya hay instalada una versión de la plantilla al ejecutar este comando, la plantilla se actualizará a la versión especificada o a la versión estable más reciente si no se ha especificado ninguna versión.</span><span class="sxs-lookup"><span data-stu-id="b6eef-297">If a version of the template was already installed when you run this command, the template will be updated to the specified version, or to the latest stable version if no version was specified.</span></span>

  <span data-ttu-id="b6eef-298">Para obtener información sobre cómo crear plantillas personalizadas, consulte [Plantillas personalizadas para dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="b6eef-298">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

- **`-l|--list`**

  <span data-ttu-id="b6eef-299">Muestra las plantillas que contienen el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="b6eef-299">Lists templates containing the specified name.</span></span> <span data-ttu-id="b6eef-300">Si no se especifica ningún nombre, enumera todas las plantillas.</span><span class="sxs-lookup"><span data-stu-id="b6eef-300">If no name is specified, lists all templates.</span></span>

- **`-lang|--language {C#|F#|VB}`**

  <span data-ttu-id="b6eef-301">El lenguaje de la plantilla que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="b6eef-301">The language of the template to create.</span></span> <span data-ttu-id="b6eef-302">El lenguaje aceptado cambia según la plantilla (vea los valores predeterminados en la sección [argumentos](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="b6eef-302">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="b6eef-303">No es válido para algunas plantillas.</span><span class="sxs-lookup"><span data-stu-id="b6eef-303">Not valid for some templates.</span></span>

  > [!NOTE]
  > <span data-ttu-id="b6eef-304">Algunos shells interpretan `#` como un carácter especial.</span><span class="sxs-lookup"><span data-stu-id="b6eef-304">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="b6eef-305">En esos casos, incluya el valor del parámetro de lenguaje entre comillas.</span><span class="sxs-lookup"><span data-stu-id="b6eef-305">In those cases, enclose the language parameter value in quotes.</span></span> <span data-ttu-id="b6eef-306">Por ejemplo: `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-306">For example, `dotnet new console -lang "F#"`.</span></span>

- **`-n|--name <OUTPUT_NAME>`**

  <span data-ttu-id="b6eef-307">El nombre de la salida creada.</span><span class="sxs-lookup"><span data-stu-id="b6eef-307">The name for the created output.</span></span> <span data-ttu-id="b6eef-308">Si no se especifica ningún nombre, se usa el nombre del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="b6eef-308">If no name is specified, the name of the current directory is used.</span></span>

- **`--nuget-source <SOURCE>`**

  <span data-ttu-id="b6eef-309">Especifica un origen de NuGet para usarlo durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="b6eef-309">Specifies a NuGet source to use during install.</span></span> <span data-ttu-id="b6eef-310">Disponible a partir del SDK de .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="b6eef-310">Available since .NET Core 2.1 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="b6eef-311">La ubicación para colocar la salida generada.</span><span class="sxs-lookup"><span data-stu-id="b6eef-311">Location to place the generated output.</span></span> <span data-ttu-id="b6eef-312">El valor predeterminado es el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="b6eef-312">The default is the current directory.</span></span>

- **`--type <TYPE>`**

  <span data-ttu-id="b6eef-313">Filtra plantillas en función de los tipos disponibles.</span><span class="sxs-lookup"><span data-stu-id="b6eef-313">Filters templates based on available types.</span></span> <span data-ttu-id="b6eef-314">Los valores predefinidos son `project`, `item` y `other`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-314">Predefined values are `project`, `item`, and `other`.</span></span>

- **`-u|--uninstall [PATH|NUGET_ID]`**

  <span data-ttu-id="b6eef-315">Desinstala un paquete de plantillas en los parámetros `PATH` o `NUGET_ID` proporcionados.</span><span class="sxs-lookup"><span data-stu-id="b6eef-315">Uninstalls a template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="b6eef-316">Si no se especifica el valor `<PATH|NUGET_ID>`, se muestran todos los paquetes de plantillas instalados actualmente y sus plantillas asociadas.</span><span class="sxs-lookup"><span data-stu-id="b6eef-316">When the `<PATH|NUGET_ID>` value isn't specified, all currently installed template packs and their associated templates are displayed.</span></span> <span data-ttu-id="b6eef-317">Al especificar `NUGET_ID`, no incluya el número de versión.</span><span class="sxs-lookup"><span data-stu-id="b6eef-317">When specifying `NUGET_ID`, don't include the version number.</span></span>

  <span data-ttu-id="b6eef-318">Si no especifica un parámetro en esta opción, el comando muestra las plantillas instaladas y detalles sobre ellas.</span><span class="sxs-lookup"><span data-stu-id="b6eef-318">If you don't specify a parameter to this option, the command lists the installed templates and details about them.</span></span>

  > [!NOTE]
  > <span data-ttu-id="b6eef-319">Para desinstalar una plantilla mediante `PATH`, debe usar el nombre completo de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="b6eef-319">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="b6eef-320">Por ejemplo, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* funcionará, pero *./GarciaSoftware.ConsoleTemplate.CSharp* desde la carpeta contenedora no lo hará.</span><span class="sxs-lookup"><span data-stu-id="b6eef-320">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
  > <span data-ttu-id="b6eef-321">No incluya ninguna barra diagonal para finalizar el directorio en la ruta de acceso a la plantilla.</span><span class="sxs-lookup"><span data-stu-id="b6eef-321">Don't include a final terminating directory slash on your template path.</span></span>

- **`--update-apply`**

  <span data-ttu-id="b6eef-322">Comprueba si hay actualizaciones disponibles de los paquetes de plantillas instalados actualmente y las instala.</span><span class="sxs-lookup"><span data-stu-id="b6eef-322">Checks if there are updates available for the template packs that are currently installed and installs them.</span></span> <span data-ttu-id="b6eef-323">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="b6eef-323">Available since .NET Core 3.0 SDK.</span></span>

- **`--update-check`**

  <span data-ttu-id="b6eef-324">Comprueba si hay actualizaciones disponibles de los paquetes de plantillas instalados actualmente.</span><span class="sxs-lookup"><span data-stu-id="b6eef-324">Checks if there are updates available for the template packs that are currently installed.</span></span> <span data-ttu-id="b6eef-325">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="b6eef-325">Available since .NET Core 3.0 SDK.</span></span>

## <a name="template-options"></a><span data-ttu-id="b6eef-326">Opciones de plantilla</span><span class="sxs-lookup"><span data-stu-id="b6eef-326">Template options</span></span>

<span data-ttu-id="b6eef-327">Cada plantilla de proyecto puede tener opciones adicionales disponibles.</span><span class="sxs-lookup"><span data-stu-id="b6eef-327">Each project template may have additional options available.</span></span> <span data-ttu-id="b6eef-328">Las plantillas principales tienen las siguientes opciones adicionales:</span><span class="sxs-lookup"><span data-stu-id="b6eef-328">The core templates have the following additional options:</span></span>

### <a name="console"></a><span data-ttu-id="b6eef-329">consola</span><span class="sxs-lookup"><span data-stu-id="b6eef-329">console</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="b6eef-330">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="b6eef-330">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="b6eef-331">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="b6eef-331">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="b6eef-332">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="b6eef-332">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="b6eef-333">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="b6eef-333">SDK version</span></span> | <span data-ttu-id="b6eef-334">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="b6eef-334">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="b6eef-335">3.1</span><span class="sxs-lookup"><span data-stu-id="b6eef-335">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="b6eef-336">3.0</span><span class="sxs-lookup"><span data-stu-id="b6eef-336">3.0</span></span>         | `netcoreapp3.0` |

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="b6eef-337">Establece la propiedad `LangVersion` en el archivo del proyecto creado.</span><span class="sxs-lookup"><span data-stu-id="b6eef-337">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="b6eef-338">Por ejemplo, use `--langVersion 7.3` para emplear C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="b6eef-338">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="b6eef-339">No es compatible con F#.</span><span class="sxs-lookup"><span data-stu-id="b6eef-339">Not supported for F#.</span></span> <span data-ttu-id="b6eef-340">Disponible a partir del SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="b6eef-340">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="b6eef-341">Para obtener una lista de las versiones predeterminadas de C#, vea [Valores predeterminados](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="b6eef-341">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="b6eef-342">Si se especifica, no se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="b6eef-342">If specified, doesn't execute an implicit restore during project creation.</span></span> <span data-ttu-id="b6eef-343">Disponible a partir del SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="b6eef-343">Available since .NET Core 2.2 SDK.</span></span>

***

### <a name="classlib"></a><span data-ttu-id="b6eef-344">classlib</span><span class="sxs-lookup"><span data-stu-id="b6eef-344">classlib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="b6eef-345">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="b6eef-345">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="b6eef-346">Valores: `netcoreapp<version>` para crear una biblioteca de clases de .NET Core o `netstandard<version>` para crear una biblioteca de clases de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="b6eef-346">Values: `netcoreapp<version>` to create a .NET Core Class Library or `netstandard<version>` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="b6eef-347">El valor predeterminado es `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-347">The default value is `netstandard2.0`.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="b6eef-348">Establece la propiedad `LangVersion` en el archivo del proyecto creado.</span><span class="sxs-lookup"><span data-stu-id="b6eef-348">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="b6eef-349">Por ejemplo, use `--langVersion 7.3` para emplear C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="b6eef-349">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="b6eef-350">No es compatible con F#.</span><span class="sxs-lookup"><span data-stu-id="b6eef-350">Not supported for F#.</span></span> <span data-ttu-id="b6eef-351">Disponible a partir del SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="b6eef-351">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="b6eef-352">Para obtener una lista de las versiones predeterminadas de C#, vea [Valores predeterminados](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="b6eef-352">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="b6eef-353">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="b6eef-353">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="wpf-wpflib-wpfcustomcontrollib-wpfusercontrollib"></a><a name="wpf"></a> <span data-ttu-id="b6eef-354">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="b6eef-354">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="b6eef-355">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="b6eef-355">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="b6eef-356">El valor predeterminado es `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-356">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="b6eef-357">Disponible a partir del SDK de .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="b6eef-357">Available since .NET Core 3.1 SDK.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="b6eef-358">Establece la propiedad `LangVersion` en el archivo del proyecto creado.</span><span class="sxs-lookup"><span data-stu-id="b6eef-358">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="b6eef-359">Por ejemplo, use `--langVersion 7.3` para emplear C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="b6eef-359">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="b6eef-360">Para obtener una lista de las versiones predeterminadas de C#, vea [Valores predeterminados](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="b6eef-360">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="b6eef-361">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="b6eef-361">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="winforms-winformslib"></a><a name="winforms"></a> <span data-ttu-id="b6eef-362">winforms, winformslib</span><span class="sxs-lookup"><span data-stu-id="b6eef-362">winforms, winformslib</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="b6eef-363">Establece la propiedad `LangVersion` en el archivo del proyecto creado.</span><span class="sxs-lookup"><span data-stu-id="b6eef-363">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="b6eef-364">Por ejemplo, use `--langVersion 7.3` para emplear C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="b6eef-364">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="b6eef-365">Para obtener una lista de las versiones predeterminadas de C#, vea [Valores predeterminados](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="b6eef-365">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="b6eef-366">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="b6eef-366">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="worker-grpc"></a><a name="web-others"></a> <span data-ttu-id="b6eef-367">worker, grpc</span><span class="sxs-lookup"><span data-stu-id="b6eef-367">worker, grpc</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="b6eef-368">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="b6eef-368">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="b6eef-369">El valor predeterminado es `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-369">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="b6eef-370">Disponible a partir del SDK de .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="b6eef-370">Available since .NET Core 3.1 SDK.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="b6eef-371">Excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="b6eef-371">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="b6eef-372">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="b6eef-372">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="mstest-xunit"></a><a name="test"></a> <span data-ttu-id="b6eef-373">mstest, xunit</span><span class="sxs-lookup"><span data-stu-id="b6eef-373">mstest, xunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="b6eef-374">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="b6eef-374">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="b6eef-375">Opción disponible a partir del SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="b6eef-375">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="b6eef-376">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="b6eef-376">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="b6eef-377">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="b6eef-377">SDK version</span></span> | <span data-ttu-id="b6eef-378">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="b6eef-378">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="b6eef-379">3.1</span><span class="sxs-lookup"><span data-stu-id="b6eef-379">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="b6eef-380">3.0</span><span class="sxs-lookup"><span data-stu-id="b6eef-380">3.0</span></span>         | `netcoreapp3.0` |

- **`-p|--enable-pack`**

  <span data-ttu-id="b6eef-381">Habilita el empaquetado del proyecto mediante [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="b6eef-381">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="b6eef-382">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="b6eef-382">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="nunit"></a><span data-ttu-id="b6eef-383">nunit</span><span class="sxs-lookup"><span data-stu-id="b6eef-383">nunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="b6eef-384">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="b6eef-384">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="b6eef-385">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="b6eef-385">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="b6eef-386">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="b6eef-386">SDK version</span></span> | <span data-ttu-id="b6eef-387">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="b6eef-387">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="b6eef-388">3.1</span><span class="sxs-lookup"><span data-stu-id="b6eef-388">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="b6eef-389">3.0</span><span class="sxs-lookup"><span data-stu-id="b6eef-389">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="b6eef-390">2.2</span><span class="sxs-lookup"><span data-stu-id="b6eef-390">2.2</span></span>         | `netcoreapp2.2` |
  | <span data-ttu-id="b6eef-391">2.1</span><span class="sxs-lookup"><span data-stu-id="b6eef-391">2.1</span></span>         | `netcoreapp2.1` |

- **`-p|--enable-pack`**

  <span data-ttu-id="b6eef-392">Habilita el empaquetado del proyecto mediante [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="b6eef-392">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="b6eef-393">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="b6eef-393">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="page"></a><span data-ttu-id="b6eef-394">página</span><span class="sxs-lookup"><span data-stu-id="b6eef-394">page</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="b6eef-395">Espacio de nombres del código generado.</span><span class="sxs-lookup"><span data-stu-id="b6eef-395">Namespace for the generated code.</span></span> <span data-ttu-id="b6eef-396">El valor predeterminado es `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-396">The default value is `MyApp.Namespace`.</span></span>

- **`-np|--no-pagemodel`**

  <span data-ttu-id="b6eef-397">Crea la página sin PageModel.</span><span class="sxs-lookup"><span data-stu-id="b6eef-397">Creates the page without a PageModel.</span></span>

***

### <a name="viewimports-proto"></a><a name="namespace"></a> <span data-ttu-id="b6eef-398">viewimports, proto</span><span class="sxs-lookup"><span data-stu-id="b6eef-398">viewimports, proto</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="b6eef-399">Espacio de nombres del código generado.</span><span class="sxs-lookup"><span data-stu-id="b6eef-399">Namespace for the generated code.</span></span> <span data-ttu-id="b6eef-400">El valor predeterminado es `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-400">The default value is `MyApp.Namespace`.</span></span>

***

### <a name="blazorserver"></a><span data-ttu-id="b6eef-401">blazorserver</span><span class="sxs-lookup"><span data-stu-id="b6eef-401">blazorserver</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="b6eef-402">Tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="b6eef-402">The type of authentication to use.</span></span> <span data-ttu-id="b6eef-403">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="b6eef-403">The possible values are:</span></span>

  - <span data-ttu-id="b6eef-404">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="b6eef-404">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="b6eef-405">`Individual`: autenticación individual.</span><span class="sxs-lookup"><span data-stu-id="b6eef-405">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="b6eef-406">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="b6eef-406">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="b6eef-407">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="b6eef-407">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="b6eef-408">`MultiOrg`: autenticación organizativa para varios inquilinos.</span><span class="sxs-lookup"><span data-stu-id="b6eef-408">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="b6eef-409">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="b6eef-409">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="b6eef-410">Instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="b6eef-410">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="b6eef-411">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-411">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="b6eef-412">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-412">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="b6eef-413">Identificador de la directiva de registro e inicio de sesión de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="b6eef-413">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="b6eef-414">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-414">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="b6eef-415">Identificador de la directiva de restablecimiento de contraseñas de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="b6eef-415">The reset password policy ID for this project.</span></span> <span data-ttu-id="b6eef-416">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-416">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="b6eef-417">Identificador de la directiva de edición de perfiles de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="b6eef-417">The edit profile policy ID for this project.</span></span> <span data-ttu-id="b6eef-418">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-418">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="b6eef-419">Instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="b6eef-419">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="b6eef-420">Úsela con las autenticaciones `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-420">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="b6eef-421">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-421">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="b6eef-422">Identificador de cliente de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="b6eef-422">The Client ID for this project.</span></span> <span data-ttu-id="b6eef-423">Úsela con las autenticaciones `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-423">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="b6eef-424">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-424">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="b6eef-425">Dominio del inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="b6eef-425">The domain for the directory tenant.</span></span> <span data-ttu-id="b6eef-426">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-426">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="b6eef-427">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-427">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="b6eef-428">Identificador de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="b6eef-428">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="b6eef-429">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-429">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="b6eef-430">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-430">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="b6eef-431">Ruta de acceso de solicitud de la ruta de acceso de la base de la aplicación del URI de redirección.</span><span class="sxs-lookup"><span data-stu-id="b6eef-431">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="b6eef-432">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-432">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="b6eef-433">El valor predeterminado es `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-433">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="b6eef-434">Concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="b6eef-434">Allows this application read-access to the directory.</span></span> <span data-ttu-id="b6eef-435">Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-435">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="b6eef-436">Excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="b6eef-436">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="b6eef-437">Desactiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="b6eef-437">Turns off HTTPS.</span></span> <span data-ttu-id="b6eef-438">Esta opción solo se aplica si no se usan `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg` en `--auth`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-438">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="b6eef-439">Especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="b6eef-439">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="b6eef-440">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-440">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--no-restore`**

  <span data-ttu-id="b6eef-441">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="b6eef-441">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="web"></a><span data-ttu-id="b6eef-442">web</span><span class="sxs-lookup"><span data-stu-id="b6eef-442">web</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="b6eef-443">Excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="b6eef-443">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="b6eef-444">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="b6eef-444">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="b6eef-445">Opción no disponible en el SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="b6eef-445">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="b6eef-446">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="b6eef-446">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="b6eef-447">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="b6eef-447">SDK version</span></span> | <span data-ttu-id="b6eef-448">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="b6eef-448">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="b6eef-449">3.1</span><span class="sxs-lookup"><span data-stu-id="b6eef-449">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="b6eef-450">3.0</span><span class="sxs-lookup"><span data-stu-id="b6eef-450">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="b6eef-451">2.1</span><span class="sxs-lookup"><span data-stu-id="b6eef-451">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="b6eef-452">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="b6eef-452">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="b6eef-453">Desactiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="b6eef-453">Turns off HTTPS.</span></span>

***

### <a name="mvc-webapp"></a><a name="web-options"></a> <span data-ttu-id="b6eef-454">mvc, webapp</span><span class="sxs-lookup"><span data-stu-id="b6eef-454">mvc, webapp</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="b6eef-455">Tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="b6eef-455">The type of authentication to use.</span></span> <span data-ttu-id="b6eef-456">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="b6eef-456">The possible values are:</span></span>

  - <span data-ttu-id="b6eef-457">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="b6eef-457">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="b6eef-458">`Individual`: autenticación individual.</span><span class="sxs-lookup"><span data-stu-id="b6eef-458">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="b6eef-459">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="b6eef-459">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="b6eef-460">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="b6eef-460">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="b6eef-461">`MultiOrg`: autenticación organizativa para varios inquilinos.</span><span class="sxs-lookup"><span data-stu-id="b6eef-461">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="b6eef-462">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="b6eef-462">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="b6eef-463">Instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="b6eef-463">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="b6eef-464">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-464">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="b6eef-465">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-465">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="b6eef-466">Identificador de la directiva de registro e inicio de sesión de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="b6eef-466">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="b6eef-467">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-467">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="b6eef-468">Identificador de la directiva de restablecimiento de contraseñas de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="b6eef-468">The reset password policy ID for this project.</span></span> <span data-ttu-id="b6eef-469">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-469">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="b6eef-470">Identificador de la directiva de edición de perfiles de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="b6eef-470">The edit profile policy ID for this project.</span></span> <span data-ttu-id="b6eef-471">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-471">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="b6eef-472">Instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="b6eef-472">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="b6eef-473">Úsela con las autenticaciones `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-473">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="b6eef-474">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-474">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="b6eef-475">Identificador de cliente de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="b6eef-475">The Client ID for this project.</span></span> <span data-ttu-id="b6eef-476">Úsela con las autenticaciones `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-476">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="b6eef-477">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-477">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="b6eef-478">Dominio del inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="b6eef-478">The domain for the directory tenant.</span></span> <span data-ttu-id="b6eef-479">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-479">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="b6eef-480">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-480">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="b6eef-481">Identificador de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="b6eef-481">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="b6eef-482">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-482">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="b6eef-483">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-483">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="b6eef-484">Ruta de acceso de solicitud de la ruta de acceso de la base de la aplicación del URI de redirección.</span><span class="sxs-lookup"><span data-stu-id="b6eef-484">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="b6eef-485">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-485">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="b6eef-486">El valor predeterminado es `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-486">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="b6eef-487">Concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="b6eef-487">Allows this application read-access to the directory.</span></span> <span data-ttu-id="b6eef-488">Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-488">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="b6eef-489">Excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="b6eef-489">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="b6eef-490">Desactiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="b6eef-490">Turns off HTTPS.</span></span> <span data-ttu-id="b6eef-491">Esta opción solo se aplica si no se usan `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-491">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="b6eef-492">Especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="b6eef-492">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="b6eef-493">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-493">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="b6eef-494">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="b6eef-494">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="b6eef-495">Opción disponible a partir del SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="b6eef-495">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="b6eef-496">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="b6eef-496">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="b6eef-497">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="b6eef-497">SDK version</span></span> | <span data-ttu-id="b6eef-498">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="b6eef-498">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="b6eef-499">3.1</span><span class="sxs-lookup"><span data-stu-id="b6eef-499">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="b6eef-500">3.0</span><span class="sxs-lookup"><span data-stu-id="b6eef-500">3.0</span></span>         | `netcoreapp3.0` |

- **`--no-restore`**

  <span data-ttu-id="b6eef-501">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="b6eef-501">Doesn't execute an implicit restore during project creation.</span></span>

- **`--use-browserlink`**

  <span data-ttu-id="b6eef-502">Incluye BrowserLink en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="b6eef-502">Includes BrowserLink in the project.</span></span> <span data-ttu-id="b6eef-503">Opción no disponible en el SDK de .NET Core 2.2 y 3.1.</span><span class="sxs-lookup"><span data-stu-id="b6eef-503">Option not available in .NET Core 2.2 and 3.1 SDK.</span></span>

- **`-rrc|--razor-runtime-compilation`**

  <span data-ttu-id="b6eef-504">Determina si el proyecto está configurado para usar la [compilación en tiempo de ejecución de Razor](/aspnet/core/mvc/views/view-compilation#runtime-compilation) en las compilaciones de depuración.</span><span class="sxs-lookup"><span data-stu-id="b6eef-504">Determines if the project is configured to use [Razor runtime compilation](/aspnet/core/mvc/views/view-compilation#runtime-compilation) in Debug builds.</span></span> <span data-ttu-id="b6eef-505">Opción disponible a partir del SDK de .NET Core 3.1.201.</span><span class="sxs-lookup"><span data-stu-id="b6eef-505">Option available since .NET Core 3.1.201 SDK.</span></span>

***

### <a name="angular-react"></a><a name="spa"></a> <span data-ttu-id="b6eef-506">angular, react</span><span class="sxs-lookup"><span data-stu-id="b6eef-506">angular, react</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="b6eef-507">Tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="b6eef-507">The type of authentication to use.</span></span> <span data-ttu-id="b6eef-508">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="b6eef-508">Available since .NET Core 3.0 SDK.</span></span>
  
  <span data-ttu-id="b6eef-509">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="b6eef-509">The possible values are:</span></span>

  - <span data-ttu-id="b6eef-510">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="b6eef-510">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="b6eef-511">`Individual`: autenticación individual.</span><span class="sxs-lookup"><span data-stu-id="b6eef-511">`Individual` - Individual authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="b6eef-512">Excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="b6eef-512">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="b6eef-513">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="b6eef-513">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="b6eef-514">Desactiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="b6eef-514">Turns off HTTPS.</span></span> <span data-ttu-id="b6eef-515">Esta opción solo se aplica si la autenticación es `None`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-515">This option only applies if authentication is `None`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="b6eef-516">Especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="b6eef-516">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="b6eef-517">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-517">Only applies to `Individual` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="b6eef-518">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="b6eef-518">Available since .NET Core 3.0 SDK.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="b6eef-519">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="b6eef-519">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="b6eef-520">Opción no disponible en el SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="b6eef-520">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="b6eef-521">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="b6eef-521">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="b6eef-522">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="b6eef-522">SDK version</span></span> | <span data-ttu-id="b6eef-523">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="b6eef-523">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="b6eef-524">3.1</span><span class="sxs-lookup"><span data-stu-id="b6eef-524">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="b6eef-525">3.0</span><span class="sxs-lookup"><span data-stu-id="b6eef-525">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="b6eef-526">2.1</span><span class="sxs-lookup"><span data-stu-id="b6eef-526">2.1</span></span>         | `netcoreapp2.0` |

***

### <a name="reactredux"></a><span data-ttu-id="b6eef-527">reactredux</span><span class="sxs-lookup"><span data-stu-id="b6eef-527">reactredux</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="b6eef-528">Excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="b6eef-528">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="b6eef-529">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="b6eef-529">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="b6eef-530">Opción no disponible en el SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="b6eef-530">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="b6eef-531">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="b6eef-531">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="b6eef-532">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="b6eef-532">SDK version</span></span> | <span data-ttu-id="b6eef-533">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="b6eef-533">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="b6eef-534">3.1</span><span class="sxs-lookup"><span data-stu-id="b6eef-534">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="b6eef-535">3.0</span><span class="sxs-lookup"><span data-stu-id="b6eef-535">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="b6eef-536">2.1</span><span class="sxs-lookup"><span data-stu-id="b6eef-536">2.1</span></span>         | `netcoreapp2.0` |

- **`--no-restore`**

  <span data-ttu-id="b6eef-537">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="b6eef-537">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="b6eef-538">Desactiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="b6eef-538">Turns off HTTPS.</span></span>

***

### <a name="razorclasslib"></a><span data-ttu-id="b6eef-539">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="b6eef-539">razorclasslib</span></span>

- **`--no-restore`**

  <span data-ttu-id="b6eef-540">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="b6eef-540">Doesn't execute an implicit restore during project creation.</span></span>

- **`-s|--support-pages-and-views`**

  <span data-ttu-id="b6eef-541">Permite agregar vistas y páginas de Razor tradicionales además de los componentes a esta biblioteca.</span><span class="sxs-lookup"><span data-stu-id="b6eef-541">Supports adding traditional Razor pages and Views in addition to components to this library.</span></span> <span data-ttu-id="b6eef-542">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="b6eef-542">Available since .NET Core 3.0 SDK.</span></span>

***
  
### <a name="webapi"></a><span data-ttu-id="b6eef-543">webapi</span><span class="sxs-lookup"><span data-stu-id="b6eef-543">webapi</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="b6eef-544">Tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="b6eef-544">The type of authentication to use.</span></span> <span data-ttu-id="b6eef-545">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="b6eef-545">The possible values are:</span></span>

  - <span data-ttu-id="b6eef-546">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="b6eef-546">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="b6eef-547">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="b6eef-547">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="b6eef-548">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="b6eef-548">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="b6eef-549">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="b6eef-549">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="b6eef-550">Instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="b6eef-550">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="b6eef-551">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-551">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="b6eef-552">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-552">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="b6eef-553">Identificador de la directiva de registro e inicio de sesión de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="b6eef-553">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="b6eef-554">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-554">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="b6eef-555">Instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="b6eef-555">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="b6eef-556">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-556">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="b6eef-557">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-557">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="b6eef-558">Identificador de cliente de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="b6eef-558">The Client ID for this project.</span></span> <span data-ttu-id="b6eef-559">Úsela con las autenticaciones `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-559">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="b6eef-560">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-560">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="b6eef-561">Dominio del inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="b6eef-561">The domain for the directory tenant.</span></span> <span data-ttu-id="b6eef-562">Úsela con las autenticaciones `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-562">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="b6eef-563">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-563">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="b6eef-564">Identificador de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="b6eef-564">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="b6eef-565">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-565">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="b6eef-566">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-566">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="b6eef-567">Concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="b6eef-567">Allows this application read-access to the directory.</span></span> <span data-ttu-id="b6eef-568">Solo se aplica a la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-568">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="b6eef-569">Excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="b6eef-569">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="b6eef-570">Desactiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="b6eef-570">Turns off HTTPS.</span></span> <span data-ttu-id="b6eef-571">`app.UseHsts` y `app.UseHttpsRedirection` no se agregan a `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-571">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="b6eef-572">Esta opción solo se aplica si no se usan `IndividualB2C` o `SingleOrg` en la autenticación.</span><span class="sxs-lookup"><span data-stu-id="b6eef-572">This option only applies if `IndividualB2C` or `SingleOrg` aren't being used for authentication.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="b6eef-573">Especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="b6eef-573">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="b6eef-574">Solo se aplica a la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="b6eef-574">Only applies to `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="b6eef-575">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="b6eef-575">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="b6eef-576">Opción no disponible en el SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="b6eef-576">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="b6eef-577">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="b6eef-577">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="b6eef-578">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="b6eef-578">SDK version</span></span> | <span data-ttu-id="b6eef-579">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="b6eef-579">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="b6eef-580">3.1</span><span class="sxs-lookup"><span data-stu-id="b6eef-580">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="b6eef-581">3.0</span><span class="sxs-lookup"><span data-stu-id="b6eef-581">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="b6eef-582">2.1</span><span class="sxs-lookup"><span data-stu-id="b6eef-582">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="b6eef-583">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="b6eef-583">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="globaljson"></a><span data-ttu-id="b6eef-584">globaljson</span><span class="sxs-lookup"><span data-stu-id="b6eef-584">globaljson</span></span>

- **`--sdk-version <VERSION_NUMBER>`**

  <span data-ttu-id="b6eef-585">Especifica la versión del SDK de .NET Core que se usará en el archivo *global.json*.</span><span class="sxs-lookup"><span data-stu-id="b6eef-585">Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

***

## <a name="examples"></a><span data-ttu-id="b6eef-586">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="b6eef-586">Examples</span></span>

- <span data-ttu-id="b6eef-587">Creación de un proyecto de aplicación de consola de C# mediante la especificación del nombre de plantilla:</span><span class="sxs-lookup"><span data-stu-id="b6eef-587">Create a C# console application project by specifying the template name:</span></span>

  ```dotnetcli
  dotnet new "Console Application"
  ```

- <span data-ttu-id="b6eef-588">Creación de un proyecto de aplicación de consola con F# en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="b6eef-588">Create an F# console application project in the current directory:</span></span>

  ```dotnetcli
  dotnet new console -lang F#
  ```

- <span data-ttu-id="b6eef-589">Creación de un proyecto de biblioteca de clases de .NET Standard en el directorio especificado:</span><span class="sxs-lookup"><span data-stu-id="b6eef-589">Create a .NET Standard class library project in the specified directory:</span></span>

  ```dotnetcli
  dotnet new classlib -lang VB -o MyLibrary
  ```

- <span data-ttu-id="b6eef-590">Creación de un proyecto MVC de ASP.NET Core C# en el directorio actual sin autenticación:</span><span class="sxs-lookup"><span data-stu-id="b6eef-590">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

  ```dotnetcli
  dotnet new mvc -au None
  ```

- <span data-ttu-id="b6eef-591">Creación de un proyecto de xUnit:</span><span class="sxs-lookup"><span data-stu-id="b6eef-591">Create a new xUnit project:</span></span>

  ```dotnetcli
  dotnet new xunit
  ```

- <span data-ttu-id="b6eef-592">Enumeración de todas las plantillas disponibles en las plantillas de aplicación de página única (SPA):</span><span class="sxs-lookup"><span data-stu-id="b6eef-592">List all templates available for Single Page Application (SPA) templates:</span></span>

  ```dotnetcli
  dotnet new spa -l
  ```

- <span data-ttu-id="b6eef-593">Enumeración de todas las plantillas que coinciden con la subcadena *we*.</span><span class="sxs-lookup"><span data-stu-id="b6eef-593">List all templates matching the *we* substring.</span></span> <span data-ttu-id="b6eef-594">No se encuentra ninguna coincidencia exacta, por lo que se ejecuta la coincidencia de subcadena con las columnas de nombre corto y de nombre.</span><span class="sxs-lookup"><span data-stu-id="b6eef-594">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

  ```dotnetcli
  dotnet new we -l
  ```

- <span data-ttu-id="b6eef-595">Intento de invocar a la plantilla que coincide con *ng*.</span><span class="sxs-lookup"><span data-stu-id="b6eef-595">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="b6eef-596">Si no se puede determinar una única coincidencia, se enumeran las plantillas que son coincidencias parciales.</span><span class="sxs-lookup"><span data-stu-id="b6eef-596">If a single match can't be determined, list the templates that are partial matches.</span></span>

  ```dotnetcli
  dotnet new ng
  ```

- <span data-ttu-id="b6eef-597">Instalación de la versión 2.0 de las plantillas de SPA de ASP.NET Core:</span><span class="sxs-lookup"><span data-stu-id="b6eef-597">Install version 2.0 of the SPA templates for ASP.NET Core:</span></span>

  ```dotnetcli
  dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0
  ```

- <span data-ttu-id="b6eef-598">Enumeración de las plantillas instaladas y detalles sobre ellas, incluido cómo desinstalarlas:</span><span class="sxs-lookup"><span data-stu-id="b6eef-598">List the installed templates and details about them, including how to uninstall them:</span></span>

  ```dotnetcli
  dotnet new -u
  ```

- <span data-ttu-id="b6eef-599">Creación de un archivo *global.json* en el directorio actual al establecer la versión del SDK en 3.1.101:</span><span class="sxs-lookup"><span data-stu-id="b6eef-599">Create a *global.json* in the current directory setting the SDK version to 3.1.101:</span></span>

  ```dotnetcli
  dotnet new globaljson --sdk-version 3.1.101
  ```

## <a name="see-also"></a><span data-ttu-id="b6eef-600">Vea también</span><span class="sxs-lookup"><span data-stu-id="b6eef-600">See also</span></span>

- [<span data-ttu-id="b6eef-601">Plantillas personalizadas para dotnet new</span><span class="sxs-lookup"><span data-stu-id="b6eef-601">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="b6eef-602">Creación de una plantilla personalizada para dotnet new</span><span class="sxs-lookup"><span data-stu-id="b6eef-602">Create a custom template for dotnet new</span></span>](../tutorials/cli-templates-create-item-template.md)
- [<span data-ttu-id="b6eef-603">Repositorio de GitHub dotnet/dotnet-template-samples</span><span class="sxs-lookup"><span data-stu-id="b6eef-603">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- <span data-ttu-id="b6eef-604">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new) (Plantillas disponibles para dotnet new)</span><span class="sxs-lookup"><span data-stu-id="b6eef-604">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)</span></span>
