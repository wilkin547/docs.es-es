---
title: Comando dotnet new
description: El comando dotnet new crea proyectos de .NET en función de la plantilla especificada.
no-loc:
- Blazor
- WebAssembly
ms.date: 09/04/2020
ms.openlocfilehash: acaaf025555c46f720452b8c9d4f875b8656125a
ms.sourcegitcommit: b924ade6426cf61a4604c4e2ee54cb3592c29317
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "101096809"
---
# <a name="dotnet-new"></a><span data-ttu-id="e53a3-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="e53a3-103">dotnet new</span></span>

<span data-ttu-id="e53a3-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.0 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="e53a3-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="e53a3-105">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="e53a3-105">Name</span></span>

<span data-ttu-id="e53a3-106">`dotnet new`: crea un nuevo proyecto, archivo de configuración o solución según la plantilla especificada.</span><span class="sxs-lookup"><span data-stu-id="e53a3-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="e53a3-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="e53a3-107">Synopsis</span></span>

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install {PATH|NUGET_ID}]
    [-lang|--language {"C#"|"F#"|VB}] [-n|--name <OUTPUT_NAME>]
    [--nuget-source <SOURCE>] [-o|--output <OUTPUT_DIRECTORY>]
    [-u|--uninstall] [--update-apply] [--update-check] [Template options]

dotnet new <TEMPLATE> [-l|--list] [--type <TYPE>]

dotnet new -h|--help
```

## <a name="description"></a><span data-ttu-id="e53a3-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="e53a3-108">Description</span></span>

<span data-ttu-id="e53a3-109">El comando `dotnet new` crea un proyecto de .NET u otros artefactos basados en una plantilla.</span><span class="sxs-lookup"><span data-stu-id="e53a3-109">The `dotnet new` command creates a .NET project or other artifacts based on a template.</span></span>

<span data-ttu-id="e53a3-110">El comando llama al [motor de plantillas](https://github.com/dotnet/templating) para crear los artefactos en el disco basándose en las opciones y la plantilla especificadas.</span><span class="sxs-lookup"><span data-stu-id="e53a3-110">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

### <a name="implicit-restore"></a><span data-ttu-id="e53a3-111">Restauración implícita</span><span class="sxs-lookup"><span data-stu-id="e53a3-111">Implicit restore</span></span>

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a><span data-ttu-id="e53a3-112">Argumentos</span><span class="sxs-lookup"><span data-stu-id="e53a3-112">Arguments</span></span>

- **`TEMPLATE`**

  <span data-ttu-id="e53a3-113">La plantilla de la que se va a crear una instancia cuando se invoca el comando.</span><span class="sxs-lookup"><span data-stu-id="e53a3-113">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="e53a3-114">Cada plantilla puede tener opciones específicas que puede pasar.</span><span class="sxs-lookup"><span data-stu-id="e53a3-114">Each template might have specific options you can pass.</span></span> <span data-ttu-id="e53a3-115">Para obtener más información, vea [Opciones de plantilla](#template-options).</span><span class="sxs-lookup"><span data-stu-id="e53a3-115">For more information, see [Template options](#template-options).</span></span>

  <span data-ttu-id="e53a3-116">Puede ejecutar `dotnet new --list` o `dotnet new -l` para ver una lista de todas las plantillas instaladas.</span><span class="sxs-lookup"><span data-stu-id="e53a3-116">You can run `dotnet new --list` or `dotnet new -l` to see a list of all installed templates.</span></span> <span data-ttu-id="e53a3-117">Si el valor `TEMPLATE` no es una coincidencia exacta con el texto de la columna **Plantillas** o **Nombre corto** de la tabla devuelta, se realiza una coincidencia de subcadena con esas dos columnas.</span><span class="sxs-lookup"><span data-stu-id="e53a3-117">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column from the returned table, a substring match is performed on those two columns.</span></span>

  <span data-ttu-id="e53a3-118">A partir del SDK de .NET Core 3.0, la CLI busca plantillas en NuGet.org al invocar el comando `dotnet new` en las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="e53a3-118">Starting with .NET Core 3.0 SDK, the CLI searches for templates in NuGet.org when you invoke the `dotnet new` command in the following conditions:</span></span>

  - <span data-ttu-id="e53a3-119">Si la CLI no encuentra ninguna coincidencia de plantilla al invocar `dotnet new`, ni siquiera parcial.</span><span class="sxs-lookup"><span data-stu-id="e53a3-119">If the CLI can't find a template match when invoking `dotnet new`, not even partial.</span></span>
  - <span data-ttu-id="e53a3-120">Si hay disponible una versión más reciente de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="e53a3-120">If there's a newer version of the template available.</span></span> <span data-ttu-id="e53a3-121">En este caso, se crea el proyecto o el artefacto, pero la CLI le advierte de que hay una versión actualizada de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="e53a3-121">In this case, the project or artifact is created but the CLI warns you about an updated version of the template.</span></span>

  <span data-ttu-id="e53a3-122">En la tabla siguiente se muestran las plantillas que vienen preinstaladas con el SDK de .NET.</span><span class="sxs-lookup"><span data-stu-id="e53a3-122">The following table shows the templates that come pre-installed with the .NET SDK.</span></span> <span data-ttu-id="e53a3-123">El lenguaje predeterminado de la plantilla se muestra entre corchetes.</span><span class="sxs-lookup"><span data-stu-id="e53a3-123">The default language for the template is shown inside the brackets.</span></span> <span data-ttu-id="e53a3-124">Haga clic en el vínculo del nombre corto para ver las opciones específicas de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="e53a3-124">Click on the short name link to see the specific template options.</span></span>

| <span data-ttu-id="e53a3-125">Plantillas</span><span class="sxs-lookup"><span data-stu-id="e53a3-125">Templates</span></span>                                    | <span data-ttu-id="e53a3-126">Nombre corto</span><span class="sxs-lookup"><span data-stu-id="e53a3-126">Short name</span></span>                        | <span data-ttu-id="e53a3-127">Lenguaje</span><span class="sxs-lookup"><span data-stu-id="e53a3-127">Language</span></span>     | <span data-ttu-id="e53a3-128">Etiquetas</span><span class="sxs-lookup"><span data-stu-id="e53a3-128">Tags</span></span>                                  | <span data-ttu-id="e53a3-129">Inclusión</span><span class="sxs-lookup"><span data-stu-id="e53a3-129">Introduced</span></span> |
|----------------------------------------------|-----------------------------------|--------------|---------------------------------------|------------|
| <span data-ttu-id="e53a3-130">Aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="e53a3-130">Console Application</span></span>                          | [`console`](#console)             | <span data-ttu-id="e53a3-131">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e53a3-131">[C#], F#, VB</span></span> | <span data-ttu-id="e53a3-132">Común/Consola</span><span class="sxs-lookup"><span data-stu-id="e53a3-132">Common/Console</span></span>                        | <span data-ttu-id="e53a3-133">1.0</span><span class="sxs-lookup"><span data-stu-id="e53a3-133">1.0</span></span>        |
| <span data-ttu-id="e53a3-134">Biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="e53a3-134">Class library</span></span>                                | [`classlib`](#classlib)           | <span data-ttu-id="e53a3-135">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e53a3-135">[C#], F#, VB</span></span> | <span data-ttu-id="e53a3-136">Común/Biblioteca</span><span class="sxs-lookup"><span data-stu-id="e53a3-136">Common/Library</span></span>                        | <span data-ttu-id="e53a3-137">1.0</span><span class="sxs-lookup"><span data-stu-id="e53a3-137">1.0</span></span>        |
| <span data-ttu-id="e53a3-138">Aplicación WPF</span><span class="sxs-lookup"><span data-stu-id="e53a3-138">WPF Application</span></span>                              | [`wpf`](#wpf)                     | <span data-ttu-id="e53a3-139">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="e53a3-139">[C#], VB</span></span>     | <span data-ttu-id="e53a3-140">Común/WPF</span><span class="sxs-lookup"><span data-stu-id="e53a3-140">Common/WPF</span></span>                            | <span data-ttu-id="e53a3-141">3.0 (5.0 para VB)</span><span class="sxs-lookup"><span data-stu-id="e53a3-141">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="e53a3-142">Biblioteca de clases de WPF</span><span class="sxs-lookup"><span data-stu-id="e53a3-142">WPF Class library</span></span>                            | [`wpflib`](#wpf)                  | <span data-ttu-id="e53a3-143">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="e53a3-143">[C#], VB</span></span>     | <span data-ttu-id="e53a3-144">Común/WPF</span><span class="sxs-lookup"><span data-stu-id="e53a3-144">Common/WPF</span></span>                            | <span data-ttu-id="e53a3-145">3.0 (5.0 para VB)</span><span class="sxs-lookup"><span data-stu-id="e53a3-145">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="e53a3-146">Biblioteca de controles personalizados WPF</span><span class="sxs-lookup"><span data-stu-id="e53a3-146">WPF Custom Control Library</span></span>                   | [`wpfcustomcontrollib`](#wpf)     | <span data-ttu-id="e53a3-147">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="e53a3-147">[C#], VB</span></span>     | <span data-ttu-id="e53a3-148">Común/WPF</span><span class="sxs-lookup"><span data-stu-id="e53a3-148">Common/WPF</span></span>                            | <span data-ttu-id="e53a3-149">3.0 (5.0 para VB)</span><span class="sxs-lookup"><span data-stu-id="e53a3-149">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="e53a3-150">Biblioteca de controles de usuario de WPF</span><span class="sxs-lookup"><span data-stu-id="e53a3-150">WPF User Control Library</span></span>                     | [`wpfusercontrollib`](#wpf)       | <span data-ttu-id="e53a3-151">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="e53a3-151">[C#], VB</span></span>     | <span data-ttu-id="e53a3-152">Común/WPF</span><span class="sxs-lookup"><span data-stu-id="e53a3-152">Common/WPF</span></span>                            | <span data-ttu-id="e53a3-153">3.0 (5.0 para VB)</span><span class="sxs-lookup"><span data-stu-id="e53a3-153">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="e53a3-154">Aplicación de Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="e53a3-154">Windows Forms (WinForms) Application</span></span>         | [`winforms`](#winforms)           | <span data-ttu-id="e53a3-155">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="e53a3-155">[C#], VB</span></span>     | <span data-ttu-id="e53a3-156">Común/WinForms</span><span class="sxs-lookup"><span data-stu-id="e53a3-156">Common/WinForms</span></span>                       | <span data-ttu-id="e53a3-157">3.0 (5.0 para VB)</span><span class="sxs-lookup"><span data-stu-id="e53a3-157">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="e53a3-158">Biblioteca de clases de Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="e53a3-158">Windows Forms (WinForms) Class library</span></span>       | [`winformslib`](#winforms)        | <span data-ttu-id="e53a3-159">[C#], VB</span><span class="sxs-lookup"><span data-stu-id="e53a3-159">[C#], VB</span></span>     | <span data-ttu-id="e53a3-160">Común/WinForms</span><span class="sxs-lookup"><span data-stu-id="e53a3-160">Common/WinForms</span></span>                       | <span data-ttu-id="e53a3-161">3.0 (5.0 para VB)</span><span class="sxs-lookup"><span data-stu-id="e53a3-161">3.0 (5.0 for VB)</span></span>|
| <span data-ttu-id="e53a3-162">Servicio Worker</span><span class="sxs-lookup"><span data-stu-id="e53a3-162">Worker Service</span></span>                               | [`worker`](#web-others)           | <span data-ttu-id="e53a3-163">[C#]</span><span class="sxs-lookup"><span data-stu-id="e53a3-163">[C#]</span></span>         | <span data-ttu-id="e53a3-164">Común/Worker/Web</span><span class="sxs-lookup"><span data-stu-id="e53a3-164">Common/Worker/Web</span></span>                     | <span data-ttu-id="e53a3-165">3.0</span><span class="sxs-lookup"><span data-stu-id="e53a3-165">3.0</span></span>        |
| <span data-ttu-id="e53a3-166">Proyecto de prueba unitaria</span><span class="sxs-lookup"><span data-stu-id="e53a3-166">Unit Test Project</span></span>                            | [`mstest`](#test)                 | <span data-ttu-id="e53a3-167">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e53a3-167">[C#], F#, VB</span></span> | <span data-ttu-id="e53a3-168">Prueba/MSTest</span><span class="sxs-lookup"><span data-stu-id="e53a3-168">Test/MSTest</span></span>                           | <span data-ttu-id="e53a3-169">1.0</span><span class="sxs-lookup"><span data-stu-id="e53a3-169">1.0</span></span>        |
| <span data-ttu-id="e53a3-170">Proyecto de prueba de NUnit 3</span><span class="sxs-lookup"><span data-stu-id="e53a3-170">NUnit 3 Test Project</span></span>                         | [`nunit`](#nunit)                 | <span data-ttu-id="e53a3-171">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e53a3-171">[C#], F#, VB</span></span> | <span data-ttu-id="e53a3-172">Prueba/NUnit</span><span class="sxs-lookup"><span data-stu-id="e53a3-172">Test/NUnit</span></span>                            | <span data-ttu-id="e53a3-173">2.1.400</span><span class="sxs-lookup"><span data-stu-id="e53a3-173">2.1.400</span></span>    |
| <span data-ttu-id="e53a3-174">Elemento de prueba de NUnit 3</span><span class="sxs-lookup"><span data-stu-id="e53a3-174">NUnit 3 Test Item</span></span>                            | `nunit-test`                      | <span data-ttu-id="e53a3-175">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e53a3-175">[C#], F#, VB</span></span> | <span data-ttu-id="e53a3-176">Prueba/NUnit</span><span class="sxs-lookup"><span data-stu-id="e53a3-176">Test/NUnit</span></span>                            | <span data-ttu-id="e53a3-177">2.2</span><span class="sxs-lookup"><span data-stu-id="e53a3-177">2.2</span></span>        |
| <span data-ttu-id="e53a3-178">Proyecto de prueba de xUnit</span><span class="sxs-lookup"><span data-stu-id="e53a3-178">xUnit Test Project</span></span>                           | [`xunit`](#test)                  | <span data-ttu-id="e53a3-179">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e53a3-179">[C#], F#, VB</span></span> | <span data-ttu-id="e53a3-180">Prueba/xUnit</span><span class="sxs-lookup"><span data-stu-id="e53a3-180">Test/xUnit</span></span>                            | <span data-ttu-id="e53a3-181">1.0</span><span class="sxs-lookup"><span data-stu-id="e53a3-181">1.0</span></span>        |
| <span data-ttu-id="e53a3-182">Componente Razor</span><span class="sxs-lookup"><span data-stu-id="e53a3-182">Razor Component</span></span>                              | `razorcomponent`                  | <span data-ttu-id="e53a3-183">[C#]</span><span class="sxs-lookup"><span data-stu-id="e53a3-183">[C#]</span></span>         | <span data-ttu-id="e53a3-184">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="e53a3-184">Web/ASP.NET</span></span>                           | <span data-ttu-id="e53a3-185">3.0</span><span class="sxs-lookup"><span data-stu-id="e53a3-185">3.0</span></span>        |
| <span data-ttu-id="e53a3-186">Página de Razor</span><span class="sxs-lookup"><span data-stu-id="e53a3-186">Razor Page</span></span>                                   | [`page`](#page)                   | <span data-ttu-id="e53a3-187">[C#]</span><span class="sxs-lookup"><span data-stu-id="e53a3-187">[C#]</span></span>         | <span data-ttu-id="e53a3-188">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="e53a3-188">Web/ASP.NET</span></span>                           | <span data-ttu-id="e53a3-189">2.0</span><span class="sxs-lookup"><span data-stu-id="e53a3-189">2.0</span></span>        |
| <span data-ttu-id="e53a3-190">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="e53a3-190">MVC ViewImports</span></span>                              | [`viewimports`](#namespace)       | <span data-ttu-id="e53a3-191">[C#]</span><span class="sxs-lookup"><span data-stu-id="e53a3-191">[C#]</span></span>         | <span data-ttu-id="e53a3-192">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="e53a3-192">Web/ASP.NET</span></span>                           | <span data-ttu-id="e53a3-193">2.0</span><span class="sxs-lookup"><span data-stu-id="e53a3-193">2.0</span></span>        |
| <span data-ttu-id="e53a3-194">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="e53a3-194">MVC ViewStart</span></span>                                | `viewstart`                       | <span data-ttu-id="e53a3-195">[C#]</span><span class="sxs-lookup"><span data-stu-id="e53a3-195">[C#]</span></span>         | <span data-ttu-id="e53a3-196">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="e53a3-196">Web/ASP.NET</span></span>                           | <span data-ttu-id="e53a3-197">2.0</span><span class="sxs-lookup"><span data-stu-id="e53a3-197">2.0</span></span>        |
| <span data-ttu-id="e53a3-198">Blazor Aplicación de servidor</span><span class="sxs-lookup"><span data-stu-id="e53a3-198">Blazor Server App</span></span>                            | [`blazorserver`](#blazorserver)   | <span data-ttu-id="e53a3-199">[C#]</span><span class="sxs-lookup"><span data-stu-id="e53a3-199">[C#]</span></span>         | <span data-ttu-id="e53a3-200">Web/Blazor</span><span class="sxs-lookup"><span data-stu-id="e53a3-200">Web/Blazor</span></span>                            | <span data-ttu-id="e53a3-201">3.0</span><span class="sxs-lookup"><span data-stu-id="e53a3-201">3.0</span></span>        |
| <span data-ttu-id="e53a3-202">Aplicación de Blazor WebAssembly</span><span class="sxs-lookup"><span data-stu-id="e53a3-202">Blazor WebAssembly App</span></span>                       | [`blazorwasm`](#blazorwasm)       | <span data-ttu-id="e53a3-203">[C#]</span><span class="sxs-lookup"><span data-stu-id="e53a3-203">[C#]</span></span>         | <span data-ttu-id="e53a3-204">Web/Blazor/WebAssembly</span><span class="sxs-lookup"><span data-stu-id="e53a3-204">Web/Blazor/WebAssembly</span></span>                | <span data-ttu-id="e53a3-205">3.1.300</span><span class="sxs-lookup"><span data-stu-id="e53a3-205">3.1.300</span></span>    |
| <span data-ttu-id="e53a3-206">Vacío de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e53a3-206">ASP.NET Core Empty</span></span>                           | [`web`](#web)                     | <span data-ttu-id="e53a3-207">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e53a3-207">[C#], F#</span></span>     | <span data-ttu-id="e53a3-208">Web/Vacío</span><span class="sxs-lookup"><span data-stu-id="e53a3-208">Web/Empty</span></span>                             | <span data-ttu-id="e53a3-209">1.0</span><span class="sxs-lookup"><span data-stu-id="e53a3-209">1.0</span></span>        |
| <span data-ttu-id="e53a3-210">Aplicación web de ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="e53a3-210">ASP.NET Core Web App (Model-View-Controller)</span></span> | [`mvc`](#web-options)             | <span data-ttu-id="e53a3-211">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e53a3-211">[C#], F#</span></span>     | <span data-ttu-id="e53a3-212">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="e53a3-212">Web/MVC</span></span>                               | <span data-ttu-id="e53a3-213">1.0</span><span class="sxs-lookup"><span data-stu-id="e53a3-213">1.0</span></span>        |
| <span data-ttu-id="e53a3-214">Aplicación web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e53a3-214">ASP.NET Core Web App</span></span>                         | [`webapp, razor`](#web-options)   | <span data-ttu-id="e53a3-215">[C#]</span><span class="sxs-lookup"><span data-stu-id="e53a3-215">[C#]</span></span>         | <span data-ttu-id="e53a3-216">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="e53a3-216">Web/MVC/Razor Pages</span></span>                   | <span data-ttu-id="e53a3-217">2.2, 2.0</span><span class="sxs-lookup"><span data-stu-id="e53a3-217">2.2, 2.0</span></span>   |
| <span data-ttu-id="e53a3-218">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="e53a3-218">ASP.NET Core with Angular</span></span>                    | [`angular`](#spa)                 | <span data-ttu-id="e53a3-219">[C#]</span><span class="sxs-lookup"><span data-stu-id="e53a3-219">[C#]</span></span>         | <span data-ttu-id="e53a3-220">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="e53a3-220">Web/MVC/SPA</span></span>                           | <span data-ttu-id="e53a3-221">2.0</span><span class="sxs-lookup"><span data-stu-id="e53a3-221">2.0</span></span>        |
| <span data-ttu-id="e53a3-222">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="e53a3-222">ASP.NET Core with React.js</span></span>                   | [`react`](#spa)                   | <span data-ttu-id="e53a3-223">[C#]</span><span class="sxs-lookup"><span data-stu-id="e53a3-223">[C#]</span></span>         | <span data-ttu-id="e53a3-224">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="e53a3-224">Web/MVC/SPA</span></span>                           | <span data-ttu-id="e53a3-225">2.0</span><span class="sxs-lookup"><span data-stu-id="e53a3-225">2.0</span></span>        |
| <span data-ttu-id="e53a3-226">ASP.NET Core con React.js y Redux</span><span class="sxs-lookup"><span data-stu-id="e53a3-226">ASP.NET Core with React.js and Redux</span></span>         | [`reactredux`](#reactredux)       | <span data-ttu-id="e53a3-227">[C#]</span><span class="sxs-lookup"><span data-stu-id="e53a3-227">[C#]</span></span>         | <span data-ttu-id="e53a3-228">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="e53a3-228">Web/MVC/SPA</span></span>                           | <span data-ttu-id="e53a3-229">2.0</span><span class="sxs-lookup"><span data-stu-id="e53a3-229">2.0</span></span>        |
| <span data-ttu-id="e53a3-230">Biblioteca de clases de Razor</span><span class="sxs-lookup"><span data-stu-id="e53a3-230">Razor Class Library</span></span>                          | [`razorclasslib`](#razorclasslib) | <span data-ttu-id="e53a3-231">[C#]</span><span class="sxs-lookup"><span data-stu-id="e53a3-231">[C#]</span></span>         | <span data-ttu-id="e53a3-232">Web/Razor/Biblioteca/Biblioteca de clases de Razor</span><span class="sxs-lookup"><span data-stu-id="e53a3-232">Web/Razor/Library/Razor Class Library</span></span> | <span data-ttu-id="e53a3-233">2.1</span><span class="sxs-lookup"><span data-stu-id="e53a3-233">2.1</span></span>        |
| <span data-ttu-id="e53a3-234">API web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e53a3-234">ASP.NET Core Web API</span></span>                         | [`webapi`](#webapi)               | <span data-ttu-id="e53a3-235">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e53a3-235">[C#], F#</span></span>     | <span data-ttu-id="e53a3-236">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="e53a3-236">Web/WebAPI</span></span>                            | <span data-ttu-id="e53a3-237">1.0</span><span class="sxs-lookup"><span data-stu-id="e53a3-237">1.0</span></span>        |
| <span data-ttu-id="e53a3-238">Servicio gRPC de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e53a3-238">ASP.NET Core gRPC Service</span></span>                    | [`grpc`](#web-others)             | <span data-ttu-id="e53a3-239">[C#]</span><span class="sxs-lookup"><span data-stu-id="e53a3-239">[C#]</span></span>         | <span data-ttu-id="e53a3-240">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="e53a3-240">Web/gRPC</span></span>                              | <span data-ttu-id="e53a3-241">3.0</span><span class="sxs-lookup"><span data-stu-id="e53a3-241">3.0</span></span>        |
| <span data-ttu-id="e53a3-242">Archivo dotnet gitignore</span><span class="sxs-lookup"><span data-stu-id="e53a3-242">dotnet gitignore file</span></span>                        | `gitignore`                       |              | <span data-ttu-id="e53a3-243">Configuración</span><span class="sxs-lookup"><span data-stu-id="e53a3-243">Config</span></span>                                | <span data-ttu-id="e53a3-244">3.0</span><span class="sxs-lookup"><span data-stu-id="e53a3-244">3.0</span></span>        |
| <span data-ttu-id="e53a3-245">archivo global.json</span><span class="sxs-lookup"><span data-stu-id="e53a3-245">global.json file</span></span>                             | [`globaljson`](#globaljson)       |              | <span data-ttu-id="e53a3-246">Configuración</span><span class="sxs-lookup"><span data-stu-id="e53a3-246">Config</span></span>                                | <span data-ttu-id="e53a3-247">2.0</span><span class="sxs-lookup"><span data-stu-id="e53a3-247">2.0</span></span>        |
| <span data-ttu-id="e53a3-248">Configuración de NuGet</span><span class="sxs-lookup"><span data-stu-id="e53a3-248">NuGet Config</span></span>                                 | `nugetconfig`                     |              | <span data-ttu-id="e53a3-249">Configuración</span><span class="sxs-lookup"><span data-stu-id="e53a3-249">Config</span></span>                                | <span data-ttu-id="e53a3-250">1.0</span><span class="sxs-lookup"><span data-stu-id="e53a3-250">1.0</span></span>        |
| <span data-ttu-id="e53a3-251">Archivo de manifiesto de la herramienta local dotnet</span><span class="sxs-lookup"><span data-stu-id="e53a3-251">Dotnet local tool manifest file</span></span>              | `tool-manifest`                   |              | <span data-ttu-id="e53a3-252">Configuración</span><span class="sxs-lookup"><span data-stu-id="e53a3-252">Config</span></span>                                | <span data-ttu-id="e53a3-253">3.0</span><span class="sxs-lookup"><span data-stu-id="e53a3-253">3.0</span></span>        |
| <span data-ttu-id="e53a3-254">Configuración web</span><span class="sxs-lookup"><span data-stu-id="e53a3-254">Web Config</span></span>                                   | `webconfig`                       |              | <span data-ttu-id="e53a3-255">Configuración</span><span class="sxs-lookup"><span data-stu-id="e53a3-255">Config</span></span>                                | <span data-ttu-id="e53a3-256">1.0</span><span class="sxs-lookup"><span data-stu-id="e53a3-256">1.0</span></span>        |
| <span data-ttu-id="e53a3-257">Archivo de solución</span><span class="sxs-lookup"><span data-stu-id="e53a3-257">Solution File</span></span>                                | `sln`                             |              | <span data-ttu-id="e53a3-258">Soluciones</span><span class="sxs-lookup"><span data-stu-id="e53a3-258">Solution</span></span>                              | <span data-ttu-id="e53a3-259">1.0</span><span class="sxs-lookup"><span data-stu-id="e53a3-259">1.0</span></span>        |
| <span data-ttu-id="e53a3-260">Archivo de búfer de protocolo</span><span class="sxs-lookup"><span data-stu-id="e53a3-260">Protocol Buffer File</span></span>                         | [`proto`](#namespace)             |              | <span data-ttu-id="e53a3-261">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="e53a3-261">Web/gRPC</span></span>                              | <span data-ttu-id="e53a3-262">3.0</span><span class="sxs-lookup"><span data-stu-id="e53a3-262">3.0</span></span>        |

## <a name="options"></a><span data-ttu-id="e53a3-263">Opciones</span><span class="sxs-lookup"><span data-stu-id="e53a3-263">Options</span></span>

- **`--dry-run`**

  <span data-ttu-id="e53a3-264">Muestra un resumen de lo que sucedería si se ejecutara el comando determinado y el resultado fuera la creación de una plantilla.</span><span class="sxs-lookup"><span data-stu-id="e53a3-264">Displays a summary of what would happen if the given command were run if it would result in a template creation.</span></span> <span data-ttu-id="e53a3-265">Disponible a partir del SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="e53a3-265">Available since .NET Core 2.2 SDK.</span></span>

- **`--force`**

  <span data-ttu-id="e53a3-266">Fuerza la generación de contenido incluso aunque se vayan a cambiar los archivos existentes.</span><span class="sxs-lookup"><span data-stu-id="e53a3-266">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="e53a3-267">Es necesario si la plantilla elegida invalidará los archivos existentes en el directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="e53a3-267">This is required when the template chosen would override existing files in the output directory.</span></span>

- **`-h|--help`**

  <span data-ttu-id="e53a3-268">Imprime la ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="e53a3-268">Prints out help for the command.</span></span> <span data-ttu-id="e53a3-269">Puede invocarse para el propio comando `dotnet new` o para cualquier plantilla.</span><span class="sxs-lookup"><span data-stu-id="e53a3-269">It can be invoked for the `dotnet new` command itself or for any template.</span></span> <span data-ttu-id="e53a3-270">Por ejemplo: `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-270">For example, `dotnet new mvc --help`.</span></span>

- **`-i|--install <PATH|NUGET_ID>`**

  <span data-ttu-id="e53a3-271">Instala un paquete de plantillas desde los parámetros `PATH` o `NUGET_ID` proporcionados.</span><span class="sxs-lookup"><span data-stu-id="e53a3-271">Installs a template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="e53a3-272">Si quiere instalar una versión preliminar de un paquete de plantilla, tendrá que especificar la versión en el formato de `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-272">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="e53a3-273">De forma predeterminada, `dotnet new` pasa \* para la versión, que representa la última versión estable del paquete.</span><span class="sxs-lookup"><span data-stu-id="e53a3-273">By default, `dotnet new` passes \* for the version, which represents the latest stable package version.</span></span> <span data-ttu-id="e53a3-274">Vea un ejemplo en la sección [Ejemplos](#examples).</span><span class="sxs-lookup"><span data-stu-id="e53a3-274">See an example in the [Examples](#examples) section.</span></span>
  
  <span data-ttu-id="e53a3-275">Si ya hay instalada una versión de la plantilla al ejecutar este comando, la plantilla se actualizará a la versión especificada o a la versión estable más reciente si no se ha especificado ninguna versión.</span><span class="sxs-lookup"><span data-stu-id="e53a3-275">If a version of the template was already installed when you run this command, the template will be updated to the specified version, or to the latest stable version if no version was specified.</span></span>

  <span data-ttu-id="e53a3-276">Para obtener información sobre cómo crear plantillas personalizadas, consulte [Plantillas personalizadas para dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="e53a3-276">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

- **`-l|--list`**

  <span data-ttu-id="e53a3-277">Muestra las plantillas que contienen el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="e53a3-277">Lists templates containing the specified name.</span></span> <span data-ttu-id="e53a3-278">Si no se especifica ningún nombre, enumera todas las plantillas.</span><span class="sxs-lookup"><span data-stu-id="e53a3-278">If no name is specified, lists all templates.</span></span>

- **`-lang|--language {C#|F#|VB}`**

  <span data-ttu-id="e53a3-279">El lenguaje de la plantilla que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="e53a3-279">The language of the template to create.</span></span> <span data-ttu-id="e53a3-280">El lenguaje aceptado cambia según la plantilla (vea los valores predeterminados en la sección [argumentos](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="e53a3-280">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="e53a3-281">No es válido para algunas plantillas.</span><span class="sxs-lookup"><span data-stu-id="e53a3-281">Not valid for some templates.</span></span>

  > [!NOTE]
  > <span data-ttu-id="e53a3-282">Algunos shells interpretan `#` como un carácter especial.</span><span class="sxs-lookup"><span data-stu-id="e53a3-282">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="e53a3-283">En esos casos, incluya el valor del parámetro de lenguaje entre comillas.</span><span class="sxs-lookup"><span data-stu-id="e53a3-283">In those cases, enclose the language parameter value in quotes.</span></span> <span data-ttu-id="e53a3-284">Por ejemplo: `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-284">For example, `dotnet new console -lang "F#"`.</span></span>

- **`-n|--name <OUTPUT_NAME>`**

  <span data-ttu-id="e53a3-285">El nombre de la salida creada.</span><span class="sxs-lookup"><span data-stu-id="e53a3-285">The name for the created output.</span></span> <span data-ttu-id="e53a3-286">Si no se especifica ningún nombre, se usa el nombre del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="e53a3-286">If no name is specified, the name of the current directory is used.</span></span>

- **`--nuget-source <SOURCE>`**

  <span data-ttu-id="e53a3-287">Especifica un origen de NuGet para usarlo durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="e53a3-287">Specifies a NuGet source to use during install.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="e53a3-288">La ubicación para colocar la salida generada.</span><span class="sxs-lookup"><span data-stu-id="e53a3-288">Location to place the generated output.</span></span> <span data-ttu-id="e53a3-289">El valor predeterminado es el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="e53a3-289">The default is the current directory.</span></span>

- **`--type <TYPE>`**

  <span data-ttu-id="e53a3-290">Filtra plantillas en función de los tipos disponibles.</span><span class="sxs-lookup"><span data-stu-id="e53a3-290">Filters templates based on available types.</span></span> <span data-ttu-id="e53a3-291">Los valores predefinidos son `project` e `item`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-291">Predefined values are `project` and `item`.</span></span>

- **`-u|--uninstall [PATH|NUGET_ID]`**

  <span data-ttu-id="e53a3-292">Desinstala un paquete de plantillas en los parámetros `PATH` o `NUGET_ID` proporcionados.</span><span class="sxs-lookup"><span data-stu-id="e53a3-292">Uninstalls a template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="e53a3-293">Si no se especifica el valor `<PATH|NUGET_ID>`, se muestran todos los paquetes de plantillas instalados actualmente y sus plantillas asociadas.</span><span class="sxs-lookup"><span data-stu-id="e53a3-293">When the `<PATH|NUGET_ID>` value isn't specified, all currently installed template packs and their associated templates are displayed.</span></span> <span data-ttu-id="e53a3-294">Al especificar `NUGET_ID`, no incluya el número de versión.</span><span class="sxs-lookup"><span data-stu-id="e53a3-294">When specifying `NUGET_ID`, don't include the version number.</span></span>

  <span data-ttu-id="e53a3-295">Si no especifica un parámetro en esta opción, el comando muestra las plantillas instaladas y detalles sobre ellas.</span><span class="sxs-lookup"><span data-stu-id="e53a3-295">If you don't specify a parameter to this option, the command lists the installed templates and details about them.</span></span>

  > [!NOTE]
  > <span data-ttu-id="e53a3-296">Para desinstalar una plantilla mediante `PATH`, debe usar el nombre completo de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="e53a3-296">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="e53a3-297">Por ejemplo, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* funcionará, pero *./GarciaSoftware.ConsoleTemplate.CSharp* desde la carpeta contenedora no lo hará.</span><span class="sxs-lookup"><span data-stu-id="e53a3-297">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
  > <span data-ttu-id="e53a3-298">No incluya ninguna barra diagonal para finalizar el directorio en la ruta de acceso a la plantilla.</span><span class="sxs-lookup"><span data-stu-id="e53a3-298">Don't include a final terminating directory slash on your template path.</span></span>

- **`--update-apply`**

  <span data-ttu-id="e53a3-299">Comprueba si hay actualizaciones disponibles de los paquetes de plantillas instalados actualmente y las instala.</span><span class="sxs-lookup"><span data-stu-id="e53a3-299">Checks if there are updates available for the template packs that are currently installed and installs them.</span></span> <span data-ttu-id="e53a3-300">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="e53a3-300">Available since .NET Core 3.0 SDK.</span></span>

- **`--update-check`**

  <span data-ttu-id="e53a3-301">Comprueba si hay actualizaciones disponibles de los paquetes de plantillas instalados actualmente.</span><span class="sxs-lookup"><span data-stu-id="e53a3-301">Checks if there are updates available for the template packs that are currently installed.</span></span> <span data-ttu-id="e53a3-302">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="e53a3-302">Available since .NET Core 3.0 SDK.</span></span>

## <a name="template-options"></a><span data-ttu-id="e53a3-303">Opciones de plantilla</span><span class="sxs-lookup"><span data-stu-id="e53a3-303">Template options</span></span>

<span data-ttu-id="e53a3-304">Cada plantilla de proyecto puede tener opciones adicionales disponibles.</span><span class="sxs-lookup"><span data-stu-id="e53a3-304">Each project template may have additional options available.</span></span> <span data-ttu-id="e53a3-305">Las plantillas principales tienen las siguientes opciones adicionales:</span><span class="sxs-lookup"><span data-stu-id="e53a3-305">The core templates have the following additional options:</span></span>

### `console`

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="e53a3-306">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="e53a3-306">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e53a3-307">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="e53a3-307">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="e53a3-308">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="e53a3-308">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="e53a3-309">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="e53a3-309">SDK version</span></span> | <span data-ttu-id="e53a3-310">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="e53a3-310">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="e53a3-311">5.0</span><span class="sxs-lookup"><span data-stu-id="e53a3-311">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="e53a3-312">3.1</span><span class="sxs-lookup"><span data-stu-id="e53a3-312">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="e53a3-313">3.0</span><span class="sxs-lookup"><span data-stu-id="e53a3-313">3.0</span></span>         | `netcoreapp3.0` |

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="e53a3-314">Establece la propiedad `LangVersion` en el archivo del proyecto creado.</span><span class="sxs-lookup"><span data-stu-id="e53a3-314">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="e53a3-315">Por ejemplo, use `--langVersion 7.3` para emplear C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="e53a3-315">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="e53a3-316">No es compatible con F#.</span><span class="sxs-lookup"><span data-stu-id="e53a3-316">Not supported for F#.</span></span> <span data-ttu-id="e53a3-317">Disponible a partir del SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="e53a3-317">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="e53a3-318">Para obtener una lista de las versiones predeterminadas de C#, vea [Valores predeterminados](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="e53a3-318">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="e53a3-319">Si se especifica, no se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="e53a3-319">If specified, doesn't execute an implicit restore during project creation.</span></span> <span data-ttu-id="e53a3-320">Disponible a partir del SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="e53a3-320">Available since .NET Core 2.2 SDK.</span></span>

***

### `classlib`

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="e53a3-321">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="e53a3-321">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e53a3-322">Valores: `net5.0` o `netcoreapp<version>` para crear una biblioteca de clases de .NET, o bien `netstandard<version>` para crear una de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="e53a3-322">Values: `net5.0` or `netcoreapp<version>` to create a .NET Class Library or `netstandard<version>` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="e53a3-323">El valor predeterminado para el SDK de .NET 5.0 es `net5.0`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-323">The default value for .NET 5.0 SDK is `net5.0`.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="e53a3-324">Establece la propiedad `LangVersion` en el archivo del proyecto creado.</span><span class="sxs-lookup"><span data-stu-id="e53a3-324">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="e53a3-325">Por ejemplo, use `--langVersion 7.3` para emplear C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="e53a3-325">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="e53a3-326">No es compatible con F#.</span><span class="sxs-lookup"><span data-stu-id="e53a3-326">Not supported for F#.</span></span> <span data-ttu-id="e53a3-327">Disponible a partir del SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="e53a3-327">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="e53a3-328">Para obtener una lista de las versiones predeterminadas de C#, vea [Valores predeterminados](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="e53a3-328">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="e53a3-329">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="e53a3-329">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="wpf-wpflib-wpfcustomcontrollib-wpfusercontrollib"></a><a name="wpf"></a> <span data-ttu-id="e53a3-330">`wpf`, `wpflib`, `wpfcustomcontrollib`, `wpfusercontrollib`</span><span class="sxs-lookup"><span data-stu-id="e53a3-330">`wpf`, `wpflib`, `wpfcustomcontrollib`, `wpfusercontrollib`</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="e53a3-331">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="e53a3-331">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e53a3-332">El valor predeterminado es `net5.0`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-332">The default value is `net5.0`.</span></span> <span data-ttu-id="e53a3-333">Disponible a partir del SDK de .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="e53a3-333">Available since .NET Core 3.1 SDK.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="e53a3-334">Establece la propiedad `LangVersion` en el archivo del proyecto creado.</span><span class="sxs-lookup"><span data-stu-id="e53a3-334">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="e53a3-335">Por ejemplo, use `--langVersion 7.3` para emplear C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="e53a3-335">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="e53a3-336">Para obtener una lista de las versiones predeterminadas de C#, vea [Valores predeterminados](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="e53a3-336">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="e53a3-337">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="e53a3-337">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="winforms-winformslib"></a><a name="winforms"></a> <span data-ttu-id="e53a3-338">`winforms`, `winformslib`</span><span class="sxs-lookup"><span data-stu-id="e53a3-338">`winforms`, `winformslib`</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="e53a3-339">Establece la propiedad `LangVersion` en el archivo del proyecto creado.</span><span class="sxs-lookup"><span data-stu-id="e53a3-339">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="e53a3-340">Por ejemplo, use `--langVersion 7.3` para emplear C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="e53a3-340">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="e53a3-341">Para obtener una lista de las versiones predeterminadas de C#, vea [Valores predeterminados](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="e53a3-341">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="e53a3-342">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="e53a3-342">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="worker-grpc"></a><a name="web-others"></a> <span data-ttu-id="e53a3-343">`worker`, `grpc`</span><span class="sxs-lookup"><span data-stu-id="e53a3-343">`worker`, `grpc`</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="e53a3-344">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="e53a3-344">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e53a3-345">El valor predeterminado es `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-345">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="e53a3-346">Disponible a partir del SDK de .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="e53a3-346">Available since .NET Core 3.1 SDK.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="e53a3-347">Excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="e53a3-347">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="e53a3-348">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="e53a3-348">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="mstest-xunit"></a><a name="test"></a> <span data-ttu-id="e53a3-349">`mstest`, `xunit`</span><span class="sxs-lookup"><span data-stu-id="e53a3-349">`mstest`, `xunit`</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="e53a3-350">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="e53a3-350">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e53a3-351">Opción disponible a partir del SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="e53a3-351">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="e53a3-352">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="e53a3-352">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="e53a3-353">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="e53a3-353">SDK version</span></span> | <span data-ttu-id="e53a3-354">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="e53a3-354">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="e53a3-355">5.0</span><span class="sxs-lookup"><span data-stu-id="e53a3-355">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="e53a3-356">3.1</span><span class="sxs-lookup"><span data-stu-id="e53a3-356">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="e53a3-357">3.0</span><span class="sxs-lookup"><span data-stu-id="e53a3-357">3.0</span></span>         | `netcoreapp3.0` |

- **`-p|--enable-pack`**

  <span data-ttu-id="e53a3-358">Habilita el empaquetado del proyecto mediante [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="e53a3-358">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="e53a3-359">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="e53a3-359">Doesn't execute an implicit restore during project creation.</span></span>

***

### `nunit`

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="e53a3-360">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="e53a3-360">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="e53a3-361">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="e53a3-361">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="e53a3-362">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="e53a3-362">SDK version</span></span> | <span data-ttu-id="e53a3-363">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="e53a3-363">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="e53a3-364">5.0</span><span class="sxs-lookup"><span data-stu-id="e53a3-364">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="e53a3-365">3.1</span><span class="sxs-lookup"><span data-stu-id="e53a3-365">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="e53a3-366">3.0</span><span class="sxs-lookup"><span data-stu-id="e53a3-366">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="e53a3-367">2.2</span><span class="sxs-lookup"><span data-stu-id="e53a3-367">2.2</span></span>         | `netcoreapp2.2` |
  | <span data-ttu-id="e53a3-368">2.1</span><span class="sxs-lookup"><span data-stu-id="e53a3-368">2.1</span></span>         | `netcoreapp2.1` |

- **`-p|--enable-pack`**

  <span data-ttu-id="e53a3-369">Habilita el empaquetado del proyecto mediante [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="e53a3-369">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="e53a3-370">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="e53a3-370">Doesn't execute an implicit restore during project creation.</span></span>

***

### `page`

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="e53a3-371">Espacio de nombres del código generado.</span><span class="sxs-lookup"><span data-stu-id="e53a3-371">Namespace for the generated code.</span></span> <span data-ttu-id="e53a3-372">El valor predeterminado es `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-372">The default value is `MyApp.Namespace`.</span></span>

- **`-np|--no-pagemodel`**

  <span data-ttu-id="e53a3-373">Crea la página sin PageModel.</span><span class="sxs-lookup"><span data-stu-id="e53a3-373">Creates the page without a PageModel.</span></span>

***

### <a name="viewimports-proto"></a><a name="namespace"></a> <span data-ttu-id="e53a3-374">`viewimports`, `proto`</span><span class="sxs-lookup"><span data-stu-id="e53a3-374">`viewimports`, `proto`</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="e53a3-375">Espacio de nombres del código generado.</span><span class="sxs-lookup"><span data-stu-id="e53a3-375">Namespace for the generated code.</span></span> <span data-ttu-id="e53a3-376">El valor predeterminado es `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-376">The default value is `MyApp.Namespace`.</span></span>

***

### `blazorserver`

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="e53a3-377">Tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="e53a3-377">The type of authentication to use.</span></span> <span data-ttu-id="e53a3-378">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="e53a3-378">The possible values are:</span></span>

  - <span data-ttu-id="e53a3-379">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="e53a3-379">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="e53a3-380">`Individual`: autenticación individual.</span><span class="sxs-lookup"><span data-stu-id="e53a3-380">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="e53a3-381">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="e53a3-381">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="e53a3-382">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="e53a3-382">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="e53a3-383">`MultiOrg`: autenticación organizativa para varios inquilinos.</span><span class="sxs-lookup"><span data-stu-id="e53a3-383">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="e53a3-384">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="e53a3-384">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="e53a3-385">Instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="e53a3-385">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="e53a3-386">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-386">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="e53a3-387">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-387">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="e53a3-388">Identificador de la directiva de registro e inicio de sesión de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="e53a3-388">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="e53a3-389">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-389">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="e53a3-390">Identificador de la directiva de restablecimiento de contraseñas de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="e53a3-390">The reset password policy ID for this project.</span></span> <span data-ttu-id="e53a3-391">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-391">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="e53a3-392">Identificador de la directiva de edición de perfiles de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="e53a3-392">The edit profile policy ID for this project.</span></span> <span data-ttu-id="e53a3-393">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-393">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="e53a3-394">Instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="e53a3-394">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="e53a3-395">Úsela con las autenticaciones `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-395">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="e53a3-396">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-396">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="e53a3-397">Identificador de cliente de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="e53a3-397">The Client ID for this project.</span></span> <span data-ttu-id="e53a3-398">Úsela con las autenticaciones `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-398">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="e53a3-399">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-399">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="e53a3-400">Dominio del inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="e53a3-400">The domain for the directory tenant.</span></span> <span data-ttu-id="e53a3-401">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-401">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e53a3-402">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-402">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="e53a3-403">Identificador de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="e53a3-403">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="e53a3-404">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-404">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="e53a3-405">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-405">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="e53a3-406">Ruta de acceso de solicitud de la ruta de acceso de la base de la aplicación del URI de redirección.</span><span class="sxs-lookup"><span data-stu-id="e53a3-406">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="e53a3-407">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-407">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e53a3-408">El valor predeterminado es `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-408">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="e53a3-409">Concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="e53a3-409">Allows this application read-access to the directory.</span></span> <span data-ttu-id="e53a3-410">Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-410">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="e53a3-411">Excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="e53a3-411">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="e53a3-412">Desactiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e53a3-412">Turns off HTTPS.</span></span> <span data-ttu-id="e53a3-413">Esta opción solo se aplica si no se usan `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg` en `--auth`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-413">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="e53a3-414">Especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="e53a3-414">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="e53a3-415">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-415">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--no-restore`**

  <span data-ttu-id="e53a3-416">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="e53a3-416">Doesn't execute an implicit restore during project creation.</span></span>

***

### `blazorwasm`

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="e53a3-417">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="e53a3-417">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="e53a3-418">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="e53a3-418">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="e53a3-419">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="e53a3-419">SDK version</span></span> | <span data-ttu-id="e53a3-420">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="e53a3-420">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="e53a3-421">5.0</span><span class="sxs-lookup"><span data-stu-id="e53a3-421">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="e53a3-422">3.1</span><span class="sxs-lookup"><span data-stu-id="e53a3-422">3.1</span></span>         | `netcoreapp3.1` |

- **`--no-restore`**

  <span data-ttu-id="e53a3-423">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="e53a3-423">Doesn't execute an implicit restore during project creation.</span></span>

- **`-ho|--hosted`**

  <span data-ttu-id="e53a3-424">Incluye un host de ASP.NET Core para la aplicación Blazor WebAssembly.</span><span class="sxs-lookup"><span data-stu-id="e53a3-424">Includes an ASP.NET Core host for the Blazor WebAssembly app.</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="e53a3-425">Tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="e53a3-425">The type of authentication to use.</span></span> <span data-ttu-id="e53a3-426">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="e53a3-426">The possible values are:</span></span>

  - <span data-ttu-id="e53a3-427">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="e53a3-427">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="e53a3-428">`Individual`: autenticación individual.</span><span class="sxs-lookup"><span data-stu-id="e53a3-428">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="e53a3-429">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="e53a3-429">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="e53a3-430">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="e53a3-430">`SingleOrg` - Organizational authentication for a single tenant.</span></span>

- **`--authority <AUTHORITY>`**

  <span data-ttu-id="e53a3-431">La autoridad del proveedor de OIDC.</span><span class="sxs-lookup"><span data-stu-id="e53a3-431">The authority of the OIDC provider.</span></span> <span data-ttu-id="e53a3-432">Úsela con la autenticación `Individual`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-432">Use with `Individual` authentication.</span></span> <span data-ttu-id="e53a3-433">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-433">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="e53a3-434">Instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="e53a3-434">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="e53a3-435">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-435">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="e53a3-436">El valor predeterminado es `https://aadB2CInstance.b2clogin.com/`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-436">The default value is `https://aadB2CInstance.b2clogin.com/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="e53a3-437">Identificador de la directiva de registro e inicio de sesión de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="e53a3-437">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="e53a3-438">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-438">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="e53a3-439">Instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="e53a3-439">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="e53a3-440">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-440">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="e53a3-441">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-441">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="e53a3-442">Identificador de cliente de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="e53a3-442">The Client ID for this project.</span></span> <span data-ttu-id="e53a3-443">Úselo con la autenticación `IndividualB2C`, `SingleOrg` o `Individual` en escenarios independientes.</span><span class="sxs-lookup"><span data-stu-id="e53a3-443">Use with `IndividualB2C`, `SingleOrg`, or `Individual` authentication in standalone scenarios.</span></span> <span data-ttu-id="e53a3-444">El valor predeterminado es `33333333-3333-3333-33333333333333333`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-444">The default value is `33333333-3333-3333-33333333333333333`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="e53a3-445">Dominio del inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="e53a3-445">The domain for the directory tenant.</span></span> <span data-ttu-id="e53a3-446">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-446">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e53a3-447">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-447">The default value is `qualified.domain.name`.</span></span>

- **`--app-id-uri <URI>`**

  <span data-ttu-id="e53a3-448">El URI del id. de la aplicación de la API de servidor a la que quiere llamar.</span><span class="sxs-lookup"><span data-stu-id="e53a3-448">The App ID Uri for the server API you want to call.</span></span> <span data-ttu-id="e53a3-449">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-449">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e53a3-450">El valor predeterminado es `api.id.uri`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-450">The default value is `api.id.uri`.</span></span>

- **`--api-client-id <ID>`**

  <span data-ttu-id="e53a3-451">El id. de cliente de la API que el servidor hospeda.</span><span class="sxs-lookup"><span data-stu-id="e53a3-451">The Client ID for the API that the server hosts.</span></span> <span data-ttu-id="e53a3-452">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-452">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e53a3-453">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-453">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`-s|--default-scope <SCOPE>`**

  <span data-ttu-id="e53a3-454">El ámbito de la API que el cliente debe solicitar para aprovisionar un token de acceso.</span><span class="sxs-lookup"><span data-stu-id="e53a3-454">The API scope the client needs to request to provision an access token.</span></span> <span data-ttu-id="e53a3-455">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-455">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e53a3-456">El valor predeterminado es `user_impersonation`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-456">The default value is `user_impersonation`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="e53a3-457">Identificador de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="e53a3-457">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="e53a3-458">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-458">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="e53a3-459">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-459">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="e53a3-460">Concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="e53a3-460">Allows this application read-access to the directory.</span></span> <span data-ttu-id="e53a3-461">Solo se aplica a la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-461">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="e53a3-462">Excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="e53a3-462">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-p|--pwa`**

  <span data-ttu-id="e53a3-463">Genera una aplicación web progresiva (PWA) que admite la instalación y el uso sin conexión.</span><span class="sxs-lookup"><span data-stu-id="e53a3-463">produces a Progressive Web Application (PWA) supporting installation and offline use.</span></span>

- **`--no-https`**

  <span data-ttu-id="e53a3-464">Desactiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e53a3-464">Turns off HTTPS.</span></span> <span data-ttu-id="e53a3-465">Esta opción solo se aplica si no se usan `Individual`, `IndividualB2C` o `SingleOrg` en `--auth`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-465">This option only applies if `Individual`, `IndividualB2C`, or `SingleOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="e53a3-466">Especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="e53a3-466">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="e53a3-467">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-467">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--called-api-url <URL>`**

  <span data-ttu-id="e53a3-468">Dirección URL de la API que se va a llamar desde la aplicación web.</span><span class="sxs-lookup"><span data-stu-id="e53a3-468">URL of the API to call from the web app.</span></span> <span data-ttu-id="e53a3-469">Solo se aplica a la autenticación `SingleOrg` o `IndividualB2C` sin un host especificado de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="e53a3-469">Only applies to `SingleOrg` or `IndividualB2C` authentication without an ASP.NET Core host specified.</span></span> <span data-ttu-id="e53a3-470">El valor predeterminado es `https://graph.microsoft.com/v1.0/me`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-470">The default value is `https://graph.microsoft.com/v1.0/me`.</span></span>

- **`--calls-graph`**

  <span data-ttu-id="e53a3-471">Especifica si la aplicación web llama a Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="e53a3-471">Specifies if the web app calls Microsoft Graph.</span></span> <span data-ttu-id="e53a3-472">Solo se aplica a la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-472">Only applies to `SingleOrg` authentication.</span></span>

- **`--called-api-scopes <SCOPES>`**

  <span data-ttu-id="e53a3-473">Ámbitos para solicitar llamar a la API desde la aplicación web.</span><span class="sxs-lookup"><span data-stu-id="e53a3-473">Scopes to request to call the API from the web app.</span></span> <span data-ttu-id="e53a3-474">Solo se aplica a la autenticación `SingleOrg` o `IndividualB2C` sin un host especificado de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="e53a3-474">Only applies to `SingleOrg` or `IndividualB2C` authentication without an ASP.NET Core host specified.</span></span> <span data-ttu-id="e53a3-475">De manera predeterminada, es `user.read`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-475">The default is `user.read`.</span></span>

***

### `web`

- **`--exclude-launch-settings`**

  <span data-ttu-id="e53a3-476">Excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="e53a3-476">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="e53a3-477">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="e53a3-477">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e53a3-478">Opción no disponible en el SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="e53a3-478">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="e53a3-479">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="e53a3-479">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="e53a3-480">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="e53a3-480">SDK version</span></span> | <span data-ttu-id="e53a3-481">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="e53a3-481">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="e53a3-482">5.0</span><span class="sxs-lookup"><span data-stu-id="e53a3-482">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="e53a3-483">3.1</span><span class="sxs-lookup"><span data-stu-id="e53a3-483">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="e53a3-484">3.0</span><span class="sxs-lookup"><span data-stu-id="e53a3-484">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="e53a3-485">2.1</span><span class="sxs-lookup"><span data-stu-id="e53a3-485">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="e53a3-486">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="e53a3-486">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="e53a3-487">Desactiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e53a3-487">Turns off HTTPS.</span></span>

***

### <a name="mvc-webapp"></a><a name="web-options"></a> <span data-ttu-id="e53a3-488">`mvc`, `webapp`</span><span class="sxs-lookup"><span data-stu-id="e53a3-488">`mvc`, `webapp`</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="e53a3-489">Tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="e53a3-489">The type of authentication to use.</span></span> <span data-ttu-id="e53a3-490">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="e53a3-490">The possible values are:</span></span>

  - <span data-ttu-id="e53a3-491">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="e53a3-491">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="e53a3-492">`Individual`: autenticación individual.</span><span class="sxs-lookup"><span data-stu-id="e53a3-492">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="e53a3-493">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="e53a3-493">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="e53a3-494">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="e53a3-494">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="e53a3-495">`MultiOrg`: autenticación organizativa para varios inquilinos.</span><span class="sxs-lookup"><span data-stu-id="e53a3-495">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="e53a3-496">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="e53a3-496">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="e53a3-497">Instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="e53a3-497">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="e53a3-498">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-498">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="e53a3-499">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-499">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="e53a3-500">Identificador de la directiva de registro e inicio de sesión de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="e53a3-500">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="e53a3-501">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-501">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="e53a3-502">Identificador de la directiva de restablecimiento de contraseñas de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="e53a3-502">The reset password policy ID for this project.</span></span> <span data-ttu-id="e53a3-503">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-503">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="e53a3-504">Identificador de la directiva de edición de perfiles de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="e53a3-504">The edit profile policy ID for this project.</span></span> <span data-ttu-id="e53a3-505">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-505">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="e53a3-506">Instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="e53a3-506">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="e53a3-507">Úsela con las autenticaciones `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-507">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="e53a3-508">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-508">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="e53a3-509">Identificador de cliente de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="e53a3-509">The Client ID for this project.</span></span> <span data-ttu-id="e53a3-510">Úsela con las autenticaciones `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-510">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="e53a3-511">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-511">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="e53a3-512">Dominio del inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="e53a3-512">The domain for the directory tenant.</span></span> <span data-ttu-id="e53a3-513">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-513">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e53a3-514">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-514">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="e53a3-515">Identificador de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="e53a3-515">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="e53a3-516">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-516">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="e53a3-517">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-517">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="e53a3-518">Ruta de acceso de solicitud de la ruta de acceso de la base de la aplicación del URI de redirección.</span><span class="sxs-lookup"><span data-stu-id="e53a3-518">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="e53a3-519">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-519">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e53a3-520">El valor predeterminado es `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-520">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="e53a3-521">Concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="e53a3-521">Allows this application read-access to the directory.</span></span> <span data-ttu-id="e53a3-522">Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-522">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="e53a3-523">Excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="e53a3-523">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="e53a3-524">Desactiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e53a3-524">Turns off HTTPS.</span></span> <span data-ttu-id="e53a3-525">Esta opción solo se aplica si no se usan `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-525">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="e53a3-526">Especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="e53a3-526">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="e53a3-527">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-527">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="e53a3-528">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="e53a3-528">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e53a3-529">Opción disponible a partir del SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="e53a3-529">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="e53a3-530">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="e53a3-530">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="e53a3-531">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="e53a3-531">SDK version</span></span> | <span data-ttu-id="e53a3-532">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="e53a3-532">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="e53a3-533">5.0</span><span class="sxs-lookup"><span data-stu-id="e53a3-533">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="e53a3-534">3.1</span><span class="sxs-lookup"><span data-stu-id="e53a3-534">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="e53a3-535">3.0</span><span class="sxs-lookup"><span data-stu-id="e53a3-535">3.0</span></span>         | `netcoreapp3.0` |

- **`--no-restore`**

  <span data-ttu-id="e53a3-536">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="e53a3-536">Doesn't execute an implicit restore during project creation.</span></span>

- **`--use-browserlink`**

  <span data-ttu-id="e53a3-537">Incluye BrowserLink en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="e53a3-537">Includes BrowserLink in the project.</span></span> <span data-ttu-id="e53a3-538">Opción no disponible en el SDK de .NET Core 2.2 y 3.1.</span><span class="sxs-lookup"><span data-stu-id="e53a3-538">Option not available in .NET Core 2.2 and 3.1 SDK.</span></span>

- **`-rrc|--razor-runtime-compilation`**

  <span data-ttu-id="e53a3-539">Determina si el proyecto está configurado para usar la [compilación en tiempo de ejecución de Razor](/aspnet/core/mvc/views/view-compilation#runtime-compilation) en las compilaciones de depuración.</span><span class="sxs-lookup"><span data-stu-id="e53a3-539">Determines if the project is configured to use [Razor runtime compilation](/aspnet/core/mvc/views/view-compilation#runtime-compilation) in Debug builds.</span></span> <span data-ttu-id="e53a3-540">Opción disponible a partir del SDK de .NET Core 3.1.201.</span><span class="sxs-lookup"><span data-stu-id="e53a3-540">Option available since .NET Core 3.1.201 SDK.</span></span>

***

### <a name="angular-react"></a><a name="spa"></a> <span data-ttu-id="e53a3-541">`angular`, `react`</span><span class="sxs-lookup"><span data-stu-id="e53a3-541">`angular`, `react`</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="e53a3-542">Tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="e53a3-542">The type of authentication to use.</span></span> <span data-ttu-id="e53a3-543">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="e53a3-543">Available since .NET Core 3.0 SDK.</span></span>
  
  <span data-ttu-id="e53a3-544">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="e53a3-544">The possible values are:</span></span>

  - <span data-ttu-id="e53a3-545">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="e53a3-545">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="e53a3-546">`Individual`: autenticación individual.</span><span class="sxs-lookup"><span data-stu-id="e53a3-546">`Individual` - Individual authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="e53a3-547">Excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="e53a3-547">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="e53a3-548">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="e53a3-548">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="e53a3-549">Desactiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e53a3-549">Turns off HTTPS.</span></span> <span data-ttu-id="e53a3-550">Esta opción solo se aplica si la autenticación es `None`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-550">This option only applies if authentication is `None`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="e53a3-551">Especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="e53a3-551">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="e53a3-552">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-552">Only applies to `Individual` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e53a3-553">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="e53a3-553">Available since .NET Core 3.0 SDK.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="e53a3-554">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="e53a3-554">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e53a3-555">Opción no disponible en el SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="e53a3-555">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="e53a3-556">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="e53a3-556">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="e53a3-557">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="e53a3-557">SDK version</span></span> | <span data-ttu-id="e53a3-558">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="e53a3-558">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="e53a3-559">5.0</span><span class="sxs-lookup"><span data-stu-id="e53a3-559">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="e53a3-560">3.1</span><span class="sxs-lookup"><span data-stu-id="e53a3-560">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="e53a3-561">3.0</span><span class="sxs-lookup"><span data-stu-id="e53a3-561">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="e53a3-562">2.1</span><span class="sxs-lookup"><span data-stu-id="e53a3-562">2.1</span></span>         | `netcoreapp2.0` |

***

### `reactredux`

- **`--exclude-launch-settings`**

  <span data-ttu-id="e53a3-563">Excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="e53a3-563">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="e53a3-564">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="e53a3-564">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e53a3-565">Opción no disponible en el SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="e53a3-565">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="e53a3-566">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="e53a3-566">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="e53a3-567">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="e53a3-567">SDK version</span></span> | <span data-ttu-id="e53a3-568">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="e53a3-568">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="e53a3-569">5.0</span><span class="sxs-lookup"><span data-stu-id="e53a3-569">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="e53a3-570">3.1</span><span class="sxs-lookup"><span data-stu-id="e53a3-570">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="e53a3-571">3.0</span><span class="sxs-lookup"><span data-stu-id="e53a3-571">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="e53a3-572">2.1</span><span class="sxs-lookup"><span data-stu-id="e53a3-572">2.1</span></span>         | `netcoreapp2.0` |

- **`--no-restore`**

  <span data-ttu-id="e53a3-573">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="e53a3-573">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="e53a3-574">Desactiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e53a3-574">Turns off HTTPS.</span></span>

***

### `razorclasslib`

- **`--no-restore`**

  <span data-ttu-id="e53a3-575">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="e53a3-575">Doesn't execute an implicit restore during project creation.</span></span>

- **`-s|--support-pages-and-views`**

  <span data-ttu-id="e53a3-576">Permite agregar vistas y páginas de Razor tradicionales además de los componentes a esta biblioteca.</span><span class="sxs-lookup"><span data-stu-id="e53a3-576">Supports adding traditional Razor pages and Views in addition to components to this library.</span></span> <span data-ttu-id="e53a3-577">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="e53a3-577">Available since .NET Core 3.0 SDK.</span></span>

***
  
### `webapi`

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="e53a3-578">Tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="e53a3-578">The type of authentication to use.</span></span> <span data-ttu-id="e53a3-579">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="e53a3-579">The possible values are:</span></span>

  - <span data-ttu-id="e53a3-580">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="e53a3-580">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="e53a3-581">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="e53a3-581">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="e53a3-582">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="e53a3-582">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="e53a3-583">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="e53a3-583">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="e53a3-584">Instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="e53a3-584">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="e53a3-585">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-585">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="e53a3-586">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-586">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="e53a3-587">Identificador de la directiva de registro e inicio de sesión de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="e53a3-587">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="e53a3-588">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-588">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="e53a3-589">Instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="e53a3-589">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="e53a3-590">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-590">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="e53a3-591">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-591">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="e53a3-592">Identificador de cliente de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="e53a3-592">The Client ID for this project.</span></span> <span data-ttu-id="e53a3-593">Úsela con las autenticaciones `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-593">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="e53a3-594">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-594">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="e53a3-595">Dominio del inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="e53a3-595">The domain for the directory tenant.</span></span> <span data-ttu-id="e53a3-596">Úsela con las autenticaciones `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-596">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="e53a3-597">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-597">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="e53a3-598">Identificador de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="e53a3-598">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="e53a3-599">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-599">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="e53a3-600">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-600">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="e53a3-601">Concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="e53a3-601">Allows this application read-access to the directory.</span></span> <span data-ttu-id="e53a3-602">Solo se aplica a la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-602">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="e53a3-603">Excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="e53a3-603">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="e53a3-604">Desactiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e53a3-604">Turns off HTTPS.</span></span> <span data-ttu-id="e53a3-605">`app.UseHsts` y `app.UseHttpsRedirection` no se agregan a `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-605">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="e53a3-606">Esta opción solo se aplica si no se usan `IndividualB2C` o `SingleOrg` en la autenticación.</span><span class="sxs-lookup"><span data-stu-id="e53a3-606">This option only applies if `IndividualB2C` or `SingleOrg` aren't being used for authentication.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="e53a3-607">Especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="e53a3-607">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="e53a3-608">Solo se aplica a la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e53a3-608">Only applies to `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="e53a3-609">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="e53a3-609">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e53a3-610">Opción no disponible en el SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="e53a3-610">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="e53a3-611">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="e53a3-611">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="e53a3-612">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="e53a3-612">SDK version</span></span> | <span data-ttu-id="e53a3-613">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="e53a3-613">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="e53a3-614">5.0</span><span class="sxs-lookup"><span data-stu-id="e53a3-614">5.0</span></span>         | `net5.0`        |
  | <span data-ttu-id="e53a3-615">3.1</span><span class="sxs-lookup"><span data-stu-id="e53a3-615">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="e53a3-616">3.0</span><span class="sxs-lookup"><span data-stu-id="e53a3-616">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="e53a3-617">2.1</span><span class="sxs-lookup"><span data-stu-id="e53a3-617">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="e53a3-618">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="e53a3-618">Doesn't execute an implicit restore during project creation.</span></span>

***

### `globaljson`

- **`--sdk-version <VERSION_NUMBER>`**

  <span data-ttu-id="e53a3-619">Especifica la versión del SDK de .NET que se va a usar en el archivo *global.json*.</span><span class="sxs-lookup"><span data-stu-id="e53a3-619">Specifies the version of the .NET SDK to use in the *global.json* file.</span></span>

***

## <a name="examples"></a><span data-ttu-id="e53a3-620">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="e53a3-620">Examples</span></span>

- <span data-ttu-id="e53a3-621">Creación de un proyecto de aplicación de consola de C# mediante la especificación del nombre de plantilla:</span><span class="sxs-lookup"><span data-stu-id="e53a3-621">Create a C# console application project by specifying the template name:</span></span>

  ```dotnetcli
  dotnet new "Console Application"
  ```

- <span data-ttu-id="e53a3-622">Creación de un proyecto de aplicación de consola con F# en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="e53a3-622">Create an F# console application project in the current directory:</span></span>

  ```dotnetcli
  dotnet new console -lang "F#"
  ```

- <span data-ttu-id="e53a3-623">Creación de un proyecto de biblioteca de clases de .NET Standard en el directorio especificado:</span><span class="sxs-lookup"><span data-stu-id="e53a3-623">Create a .NET Standard class library project in the specified directory:</span></span>

  ```dotnetcli
  dotnet new classlib -lang VB -o MyLibrary
  ```

- <span data-ttu-id="e53a3-624">Creación de un proyecto MVC de ASP.NET Core C# en el directorio actual sin autenticación:</span><span class="sxs-lookup"><span data-stu-id="e53a3-624">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

  ```dotnetcli
  dotnet new mvc -au None
  ```

- <span data-ttu-id="e53a3-625">Creación de un proyecto de xUnit:</span><span class="sxs-lookup"><span data-stu-id="e53a3-625">Create a new xUnit project:</span></span>

  ```dotnetcli
  dotnet new xunit
  ```

- <span data-ttu-id="e53a3-626">Enumeración de todas las plantillas disponibles en las plantillas de aplicación de página única (SPA):</span><span class="sxs-lookup"><span data-stu-id="e53a3-626">List all templates available for Single Page Application (SPA) templates:</span></span>

  ```dotnetcli
  dotnet new spa -l
  ```

- <span data-ttu-id="e53a3-627">Enumeración de todas las plantillas que coinciden con la subcadena *we*.</span><span class="sxs-lookup"><span data-stu-id="e53a3-627">List all templates matching the *we* substring.</span></span> <span data-ttu-id="e53a3-628">No se encuentra ninguna coincidencia exacta, por lo que se ejecuta la coincidencia de subcadena con las columnas de nombre corto y de nombre.</span><span class="sxs-lookup"><span data-stu-id="e53a3-628">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

  ```dotnetcli
  dotnet new we -l
  ```

- <span data-ttu-id="e53a3-629">Intento de invocar a la plantilla que coincide con *ng*.</span><span class="sxs-lookup"><span data-stu-id="e53a3-629">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="e53a3-630">Si no se puede determinar una única coincidencia, se enumeran las plantillas que son coincidencias parciales.</span><span class="sxs-lookup"><span data-stu-id="e53a3-630">If a single match can't be determined, list the templates that are partial matches.</span></span>

  ```dotnetcli
  dotnet new ng
  ```

- <span data-ttu-id="e53a3-631">Instalación de la versión 2.0 de las plantillas de SPA de ASP.NET Core:</span><span class="sxs-lookup"><span data-stu-id="e53a3-631">Install version 2.0 of the SPA templates for ASP.NET Core:</span></span>

  ```dotnetcli
  dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0
  ```

- <span data-ttu-id="e53a3-632">Enumeración de las plantillas instaladas y detalles sobre ellas, incluido cómo desinstalarlas:</span><span class="sxs-lookup"><span data-stu-id="e53a3-632">List the installed templates and details about them, including how to uninstall them:</span></span>

  ```dotnetcli
  dotnet new -u
  ```

- <span data-ttu-id="e53a3-633">Creación de un archivo *global.json* en el directorio actual al establecer la versión del SDK en 3.1.101:</span><span class="sxs-lookup"><span data-stu-id="e53a3-633">Create a *global.json* in the current directory setting the SDK version to 3.1.101:</span></span>

  ```dotnetcli
  dotnet new globaljson --sdk-version 3.1.101
  ```

## <a name="see-also"></a><span data-ttu-id="e53a3-634">Vea también</span><span class="sxs-lookup"><span data-stu-id="e53a3-634">See also</span></span>

- [<span data-ttu-id="e53a3-635">Plantillas personalizadas para dotnet new</span><span class="sxs-lookup"><span data-stu-id="e53a3-635">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="e53a3-636">Creación de una plantilla personalizada para dotnet new</span><span class="sxs-lookup"><span data-stu-id="e53a3-636">Create a custom template for dotnet new</span></span>](../tutorials/cli-templates-create-item-template.md)
- [<span data-ttu-id="e53a3-637">Repositorio de GitHub dotnet/dotnet-template-samples</span><span class="sxs-lookup"><span data-stu-id="e53a3-637">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- <span data-ttu-id="e53a3-638">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new) (Plantillas disponibles para dotnet new)</span><span class="sxs-lookup"><span data-stu-id="e53a3-638">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)</span></span>
