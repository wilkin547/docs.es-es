---
title: Comando dotnet new
description: El comando dotnet new crea proyectos de .NET Core basados en la plantilla especificada.
ms.date: 02/13/2020
ms.openlocfilehash: d3c609419596b123f5bfb3ca85cf292a61154a70
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79398032"
---
# <a name="dotnet-new"></a><span data-ttu-id="76e87-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="76e87-103">dotnet new</span></span>

<span data-ttu-id="76e87-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.0 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="76e87-104">**This article applies to:** ✔️ .NET Core 2.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="76e87-105">Name</span><span class="sxs-lookup"><span data-stu-id="76e87-105">Name</span></span>

<span data-ttu-id="76e87-106">`dotnet new`: crea un nuevo proyecto, archivo de configuración o solución según la plantilla especificada.</span><span class="sxs-lookup"><span data-stu-id="76e87-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="76e87-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="76e87-107">Synopsis</span></span>

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install] [-lang|--language] [-n|--name]
    [--nuget-source] [-o|--output] [-u|--uninstall] [--update-apply] [--update-check] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

## <a name="description"></a><span data-ttu-id="76e87-108">Description</span><span class="sxs-lookup"><span data-stu-id="76e87-108">Description</span></span>

<span data-ttu-id="76e87-109">El comando `dotnet new` crea un proyecto de .NET Core u otros artefactos basados en una plantilla.</span><span class="sxs-lookup"><span data-stu-id="76e87-109">The `dotnet new` command creates a .NET Core project or other artifacts based on a template.</span></span>

<span data-ttu-id="76e87-110">El comando llama al [motor de plantillas](https://github.com/dotnet/templating) para crear los artefactos en el disco basándose en las opciones y la plantilla especificadas.</span><span class="sxs-lookup"><span data-stu-id="76e87-110">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="76e87-111">Argumentos</span><span class="sxs-lookup"><span data-stu-id="76e87-111">Arguments</span></span>

- **`TEMPLATE`**

  <span data-ttu-id="76e87-112">La plantilla de la que se va a crear una instancia cuando se invoca el comando.</span><span class="sxs-lookup"><span data-stu-id="76e87-112">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="76e87-113">Cada plantilla puede tener opciones específicas que puede pasar.</span><span class="sxs-lookup"><span data-stu-id="76e87-113">Each template might have specific options you can pass.</span></span> <span data-ttu-id="76e87-114">Para obtener más información, vea [Opciones de plantilla](#template-options).</span><span class="sxs-lookup"><span data-stu-id="76e87-114">For more information, see [Template options](#template-options).</span></span>

  <span data-ttu-id="76e87-115">Puede ejecutar `dotnet new --list` para ver una lista de todas las plantillas instaladas.</span><span class="sxs-lookup"><span data-stu-id="76e87-115">You can run `dotnet new --list` to see a list of all installed templates.</span></span> <span data-ttu-id="76e87-116">Si el valor `TEMPLATE` no es una coincidencia exacta con el texto de la columna **Plantillas** o **Nombre corto** de la tabla devuelta, se realiza una coincidencia de subcadena con esas dos columnas.</span><span class="sxs-lookup"><span data-stu-id="76e87-116">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column from the returned table, a substring match is performed on those two columns.</span></span>

  <span data-ttu-id="76e87-117">A partir del SDK de .NET Core 3.0, la CLI busca plantillas en NuGet.org al invocar el comando `dotnet new` en las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="76e87-117">Starting with .NET Core 3.0 SDK, the CLI searches for templates in NuGet.org when you invoke the `dotnet new` command in the following conditions:</span></span>

  - <span data-ttu-id="76e87-118">Si la CLI no encuentra ninguna coincidencia de plantilla al invocar `dotnet new`, ni siquiera parcial.</span><span class="sxs-lookup"><span data-stu-id="76e87-118">If the CLI can’t find a template match when invoking `dotnet new`, not even partial.</span></span>
  - <span data-ttu-id="76e87-119">Si hay disponible una versión más reciente de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="76e87-119">If there’s a newer version of the template available.</span></span> <span data-ttu-id="76e87-120">En este caso, se crea el proyecto o el artefacto, pero la CLI le advierte de que hay una versión actualizada de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="76e87-120">In this case, the project or artifact is created but the CLI warns you about an updated version of the template.</span></span>

  <span data-ttu-id="76e87-121">El comando contiene una lista predeterminada de plantillas.</span><span class="sxs-lookup"><span data-stu-id="76e87-121">The command contains a default list of templates.</span></span> <span data-ttu-id="76e87-122">Use `dotnet new -l` para obtener una lista de las plantillas disponibles.</span><span class="sxs-lookup"><span data-stu-id="76e87-122">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="76e87-123">En la tabla siguiente se muestran las plantillas que vienen preinstaladas en el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="76e87-123">The following table shows the templates that come pre-installed with the .NET Core SDK.</span></span> <span data-ttu-id="76e87-124">El lenguaje predeterminado de la plantilla se muestra entre corchetes.</span><span class="sxs-lookup"><span data-stu-id="76e87-124">The default language for the template is shown inside the brackets.</span></span> <span data-ttu-id="76e87-125">Haga clic en el vínculo del nombre corto para ver las opciones específicas de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="76e87-125">Click on the short name link to see the specific template options.</span></span>

| <span data-ttu-id="76e87-126">Plantillas</span><span class="sxs-lookup"><span data-stu-id="76e87-126">Templates</span></span>                                    | <span data-ttu-id="76e87-127">Nombre corto</span><span class="sxs-lookup"><span data-stu-id="76e87-127">Short name</span></span>                      | <span data-ttu-id="76e87-128">Lenguaje</span><span class="sxs-lookup"><span data-stu-id="76e87-128">Language</span></span>     | <span data-ttu-id="76e87-129">Etiquetas</span><span class="sxs-lookup"><span data-stu-id="76e87-129">Tags</span></span>                                  | <span data-ttu-id="76e87-130">Inclusión</span><span class="sxs-lookup"><span data-stu-id="76e87-130">Introduced</span></span> |
|----------------------------------------------|---------------------------------|--------------|---------------------------------------|------------|
| <span data-ttu-id="76e87-131">Aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="76e87-131">Console Application</span></span>                          | [<span data-ttu-id="76e87-132">console</span><span class="sxs-lookup"><span data-stu-id="76e87-132">console</span></span>](#console)             | <span data-ttu-id="76e87-133">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="76e87-133">[C#], F#, VB</span></span> | <span data-ttu-id="76e87-134">Común/Consola</span><span class="sxs-lookup"><span data-stu-id="76e87-134">Common/Console</span></span>                        | <span data-ttu-id="76e87-135">1.0</span><span class="sxs-lookup"><span data-stu-id="76e87-135">1.0</span></span>        |
| <span data-ttu-id="76e87-136">Biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="76e87-136">Class library</span></span>                                | [<span data-ttu-id="76e87-137">classlib</span><span class="sxs-lookup"><span data-stu-id="76e87-137">classlib</span></span>](#classlib)           | <span data-ttu-id="76e87-138">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="76e87-138">[C#], F#, VB</span></span> | <span data-ttu-id="76e87-139">Común/Biblioteca</span><span class="sxs-lookup"><span data-stu-id="76e87-139">Common/Library</span></span>                        | <span data-ttu-id="76e87-140">1.0</span><span class="sxs-lookup"><span data-stu-id="76e87-140">1.0</span></span>        |
| <span data-ttu-id="76e87-141">Aplicación WPF</span><span class="sxs-lookup"><span data-stu-id="76e87-141">WPF Application</span></span>                              | [<span data-ttu-id="76e87-142">wpf</span><span class="sxs-lookup"><span data-stu-id="76e87-142">wpf</span></span>](#wpf)                     | <span data-ttu-id="76e87-143">[C#]</span><span class="sxs-lookup"><span data-stu-id="76e87-143">[C#]</span></span>         | <span data-ttu-id="76e87-144">Común/WPF</span><span class="sxs-lookup"><span data-stu-id="76e87-144">Common/WPF</span></span>                            | <span data-ttu-id="76e87-145">3.0</span><span class="sxs-lookup"><span data-stu-id="76e87-145">3.0</span></span>        |
| <span data-ttu-id="76e87-146">Biblioteca de clases de WPF</span><span class="sxs-lookup"><span data-stu-id="76e87-146">WPF Class library</span></span>                            | [<span data-ttu-id="76e87-147">wpflib</span><span class="sxs-lookup"><span data-stu-id="76e87-147">wpflib</span></span>](#wpf)                  | <span data-ttu-id="76e87-148">[C#]</span><span class="sxs-lookup"><span data-stu-id="76e87-148">[C#]</span></span>         | <span data-ttu-id="76e87-149">Común/WPF</span><span class="sxs-lookup"><span data-stu-id="76e87-149">Common/WPF</span></span>                            | <span data-ttu-id="76e87-150">3.0</span><span class="sxs-lookup"><span data-stu-id="76e87-150">3.0</span></span>        |
| <span data-ttu-id="76e87-151">Biblioteca de controles personalizados WPF</span><span class="sxs-lookup"><span data-stu-id="76e87-151">WPF Custom Control Library</span></span>                   | [<span data-ttu-id="76e87-152">wpfcustomcontrollib</span><span class="sxs-lookup"><span data-stu-id="76e87-152">wpfcustomcontrollib</span></span>](#wpf)     | <span data-ttu-id="76e87-153">[C#]</span><span class="sxs-lookup"><span data-stu-id="76e87-153">[C#]</span></span>         | <span data-ttu-id="76e87-154">Común/WPF</span><span class="sxs-lookup"><span data-stu-id="76e87-154">Common/WPF</span></span>                            | <span data-ttu-id="76e87-155">3.0</span><span class="sxs-lookup"><span data-stu-id="76e87-155">3.0</span></span>        |
| <span data-ttu-id="76e87-156">Biblioteca de controles de usuario de WPF</span><span class="sxs-lookup"><span data-stu-id="76e87-156">WPF User Control Library</span></span>                     | [<span data-ttu-id="76e87-157">wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="76e87-157">wpfusercontrollib</span></span>](#wpf)       | <span data-ttu-id="76e87-158">[C#]</span><span class="sxs-lookup"><span data-stu-id="76e87-158">[C#]</span></span>         | <span data-ttu-id="76e87-159">Común/WPF</span><span class="sxs-lookup"><span data-stu-id="76e87-159">Common/WPF</span></span>                            | <span data-ttu-id="76e87-160">3.0</span><span class="sxs-lookup"><span data-stu-id="76e87-160">3.0</span></span>        |
| <span data-ttu-id="76e87-161">Aplicación de Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="76e87-161">Windows Forms (WinForms) Application</span></span>         | [<span data-ttu-id="76e87-162">winforms</span><span class="sxs-lookup"><span data-stu-id="76e87-162">winforms</span></span>](#winforms)           | <span data-ttu-id="76e87-163">[C#]</span><span class="sxs-lookup"><span data-stu-id="76e87-163">[C#]</span></span>         | <span data-ttu-id="76e87-164">Común/WinForms</span><span class="sxs-lookup"><span data-stu-id="76e87-164">Common/WinForms</span></span>                       | <span data-ttu-id="76e87-165">3.0</span><span class="sxs-lookup"><span data-stu-id="76e87-165">3.0</span></span>        |
| <span data-ttu-id="76e87-166">Biblioteca de clases de Windows Forms (WinForms)</span><span class="sxs-lookup"><span data-stu-id="76e87-166">Windows Forms (WinForms) Class library</span></span>       | [<span data-ttu-id="76e87-167">winformslib</span><span class="sxs-lookup"><span data-stu-id="76e87-167">winformslib</span></span>](#winforms)        | <span data-ttu-id="76e87-168">[C#]</span><span class="sxs-lookup"><span data-stu-id="76e87-168">[C#]</span></span>         | <span data-ttu-id="76e87-169">Común/WinForms</span><span class="sxs-lookup"><span data-stu-id="76e87-169">Common/WinForms</span></span>                       | <span data-ttu-id="76e87-170">3.0</span><span class="sxs-lookup"><span data-stu-id="76e87-170">3.0</span></span>        |
| <span data-ttu-id="76e87-171">Servicio Worker</span><span class="sxs-lookup"><span data-stu-id="76e87-171">Worker Service</span></span>                               | [<span data-ttu-id="76e87-172">worker</span><span class="sxs-lookup"><span data-stu-id="76e87-172">worker</span></span>](#web-others)           | <span data-ttu-id="76e87-173">[C#]</span><span class="sxs-lookup"><span data-stu-id="76e87-173">[C#]</span></span>         | <span data-ttu-id="76e87-174">Común/Worker/Web</span><span class="sxs-lookup"><span data-stu-id="76e87-174">Common/Worker/Web</span></span>                     | <span data-ttu-id="76e87-175">3.0</span><span class="sxs-lookup"><span data-stu-id="76e87-175">3.0</span></span>        |
| <span data-ttu-id="76e87-176">Proyecto de prueba unitaria</span><span class="sxs-lookup"><span data-stu-id="76e87-176">Unit Test Project</span></span>                            | [<span data-ttu-id="76e87-177">mstest</span><span class="sxs-lookup"><span data-stu-id="76e87-177">mstest</span></span>](#test)                 | <span data-ttu-id="76e87-178">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="76e87-178">[C#], F#, VB</span></span> | <span data-ttu-id="76e87-179">Prueba/MSTest</span><span class="sxs-lookup"><span data-stu-id="76e87-179">Test/MSTest</span></span>                           | <span data-ttu-id="76e87-180">1.0</span><span class="sxs-lookup"><span data-stu-id="76e87-180">1.0</span></span>        |
| <span data-ttu-id="76e87-181">Proyecto de prueba de NUnit 3</span><span class="sxs-lookup"><span data-stu-id="76e87-181">NUnit 3 Test Project</span></span>                         | [<span data-ttu-id="76e87-182">nunit</span><span class="sxs-lookup"><span data-stu-id="76e87-182">nunit</span></span>](#nunit)                  | <span data-ttu-id="76e87-183">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="76e87-183">[C#], F#, VB</span></span> | <span data-ttu-id="76e87-184">Prueba/NUnit</span><span class="sxs-lookup"><span data-stu-id="76e87-184">Test/NUnit</span></span>                            | <span data-ttu-id="76e87-185">2.1.400</span><span class="sxs-lookup"><span data-stu-id="76e87-185">2.1.400</span></span>    |
| <span data-ttu-id="76e87-186">Elemento de prueba de NUnit 3</span><span class="sxs-lookup"><span data-stu-id="76e87-186">NUnit 3 Test Item</span></span>                            | `nunit-test`                    | <span data-ttu-id="76e87-187">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="76e87-187">[C#], F#, VB</span></span> | <span data-ttu-id="76e87-188">Prueba/NUnit</span><span class="sxs-lookup"><span data-stu-id="76e87-188">Test/NUnit</span></span>                            | <span data-ttu-id="76e87-189">2.2</span><span class="sxs-lookup"><span data-stu-id="76e87-189">2.2</span></span>        |
| <span data-ttu-id="76e87-190">Proyecto de prueba de xUnit</span><span class="sxs-lookup"><span data-stu-id="76e87-190">xUnit Test Project</span></span>                           | [<span data-ttu-id="76e87-191">xunit</span><span class="sxs-lookup"><span data-stu-id="76e87-191">xunit</span></span>](#test)                  | <span data-ttu-id="76e87-192">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="76e87-192">[C#], F#, VB</span></span> | <span data-ttu-id="76e87-193">Prueba/xUnit</span><span class="sxs-lookup"><span data-stu-id="76e87-193">Test/xUnit</span></span>                            | <span data-ttu-id="76e87-194">1.0</span><span class="sxs-lookup"><span data-stu-id="76e87-194">1.0</span></span>        |
| <span data-ttu-id="76e87-195">Componente Razor</span><span class="sxs-lookup"><span data-stu-id="76e87-195">Razor Component</span></span>                              | `razorcomponent`                | <span data-ttu-id="76e87-196">[C#]</span><span class="sxs-lookup"><span data-stu-id="76e87-196">[C#]</span></span>         | <span data-ttu-id="76e87-197">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="76e87-197">Web/ASP.NET</span></span>                           | <span data-ttu-id="76e87-198">3.0</span><span class="sxs-lookup"><span data-stu-id="76e87-198">3.0</span></span>        |
| <span data-ttu-id="76e87-199">Página de Razor</span><span class="sxs-lookup"><span data-stu-id="76e87-199">Razor Page</span></span>                                   | [<span data-ttu-id="76e87-200">page</span><span class="sxs-lookup"><span data-stu-id="76e87-200">page</span></span>](#page)                   | <span data-ttu-id="76e87-201">[C#]</span><span class="sxs-lookup"><span data-stu-id="76e87-201">[C#]</span></span>         | <span data-ttu-id="76e87-202">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="76e87-202">Web/ASP.NET</span></span>                           | <span data-ttu-id="76e87-203">2.0</span><span class="sxs-lookup"><span data-stu-id="76e87-203">2.0</span></span>        |
| <span data-ttu-id="76e87-204">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="76e87-204">MVC ViewImports</span></span>                              | [<span data-ttu-id="76e87-205">viewimports</span><span class="sxs-lookup"><span data-stu-id="76e87-205">viewimports</span></span>](#namespace)       | <span data-ttu-id="76e87-206">[C#]</span><span class="sxs-lookup"><span data-stu-id="76e87-206">[C#]</span></span>         | <span data-ttu-id="76e87-207">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="76e87-207">Web/ASP.NET</span></span>                           | <span data-ttu-id="76e87-208">2.0</span><span class="sxs-lookup"><span data-stu-id="76e87-208">2.0</span></span>        |
| <span data-ttu-id="76e87-209">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="76e87-209">MVC ViewStart</span></span>                                | `viewstart`                     | <span data-ttu-id="76e87-210">[C#]</span><span class="sxs-lookup"><span data-stu-id="76e87-210">[C#]</span></span>         | <span data-ttu-id="76e87-211">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="76e87-211">Web/ASP.NET</span></span>                           | <span data-ttu-id="76e87-212">2.0</span><span class="sxs-lookup"><span data-stu-id="76e87-212">2.0</span></span>        |
| <span data-ttu-id="76e87-213">Aplicación de servidor Blazor</span><span class="sxs-lookup"><span data-stu-id="76e87-213">Blazor Server App</span></span>                            | [<span data-ttu-id="76e87-214">blazorserver</span><span class="sxs-lookup"><span data-stu-id="76e87-214">blazorserver</span></span>](#blazorserver)   | <span data-ttu-id="76e87-215">[C#]</span><span class="sxs-lookup"><span data-stu-id="76e87-215">[C#]</span></span>         | <span data-ttu-id="76e87-216">Web/Blazor</span><span class="sxs-lookup"><span data-stu-id="76e87-216">Web/Blazor</span></span>                            | <span data-ttu-id="76e87-217">3.0</span><span class="sxs-lookup"><span data-stu-id="76e87-217">3.0</span></span>        |
| <span data-ttu-id="76e87-218">Vacío de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="76e87-218">ASP.NET Core Empty</span></span>                           | [<span data-ttu-id="76e87-219">web</span><span class="sxs-lookup"><span data-stu-id="76e87-219">web</span></span>](#web)                     | <span data-ttu-id="76e87-220">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="76e87-220">[C#], F#</span></span>     | <span data-ttu-id="76e87-221">Web/Vacío</span><span class="sxs-lookup"><span data-stu-id="76e87-221">Web/Empty</span></span>                             | <span data-ttu-id="76e87-222">1.0</span><span class="sxs-lookup"><span data-stu-id="76e87-222">1.0</span></span>        |
| <span data-ttu-id="76e87-223">Aplicación web de ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="76e87-223">ASP.NET Core Web App (Model-View-Controller)</span></span> | [<span data-ttu-id="76e87-224">mvc</span><span class="sxs-lookup"><span data-stu-id="76e87-224">mvc</span></span>](#web-options)             | <span data-ttu-id="76e87-225">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="76e87-225">[C#], F#</span></span>     | <span data-ttu-id="76e87-226">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="76e87-226">Web/MVC</span></span>                               | <span data-ttu-id="76e87-227">1.0</span><span class="sxs-lookup"><span data-stu-id="76e87-227">1.0</span></span>        |
| <span data-ttu-id="76e87-228">Aplicación web de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="76e87-228">ASP.NET Core Web App</span></span>                         | [<span data-ttu-id="76e87-229">webapp, razor</span><span class="sxs-lookup"><span data-stu-id="76e87-229">webapp, razor</span></span>](#web-options)   | <span data-ttu-id="76e87-230">[C#]</span><span class="sxs-lookup"><span data-stu-id="76e87-230">[C#]</span></span>         | <span data-ttu-id="76e87-231">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="76e87-231">Web/MVC/Razor Pages</span></span>                   | <span data-ttu-id="76e87-232">2.2, 2.0</span><span class="sxs-lookup"><span data-stu-id="76e87-232">2.2, 2.0</span></span>   |
| <span data-ttu-id="76e87-233">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="76e87-233">ASP.NET Core with Angular</span></span>                    | [<span data-ttu-id="76e87-234">angular</span><span class="sxs-lookup"><span data-stu-id="76e87-234">angular</span></span>](#spa)                 | <span data-ttu-id="76e87-235">[C#]</span><span class="sxs-lookup"><span data-stu-id="76e87-235">[C#]</span></span>         | <span data-ttu-id="76e87-236">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="76e87-236">Web/MVC/SPA</span></span>                           | <span data-ttu-id="76e87-237">2.0</span><span class="sxs-lookup"><span data-stu-id="76e87-237">2.0</span></span>        |
| <span data-ttu-id="76e87-238">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="76e87-238">ASP.NET Core with React.js</span></span>                   | [<span data-ttu-id="76e87-239">react</span><span class="sxs-lookup"><span data-stu-id="76e87-239">react</span></span>](#spa)                   | <span data-ttu-id="76e87-240">[C#]</span><span class="sxs-lookup"><span data-stu-id="76e87-240">[C#]</span></span>         | <span data-ttu-id="76e87-241">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="76e87-241">Web/MVC/SPA</span></span>                           | <span data-ttu-id="76e87-242">2.0</span><span class="sxs-lookup"><span data-stu-id="76e87-242">2.0</span></span>        |
| <span data-ttu-id="76e87-243">ASP.NET Core con React.js y Redux</span><span class="sxs-lookup"><span data-stu-id="76e87-243">ASP.NET Core with React.js and Redux</span></span>         | [<span data-ttu-id="76e87-244">reactredux</span><span class="sxs-lookup"><span data-stu-id="76e87-244">reactredux</span></span>](#reactredux)       | <span data-ttu-id="76e87-245">[C#]</span><span class="sxs-lookup"><span data-stu-id="76e87-245">[C#]</span></span>         | <span data-ttu-id="76e87-246">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="76e87-246">Web/MVC/SPA</span></span>                           | <span data-ttu-id="76e87-247">2.0</span><span class="sxs-lookup"><span data-stu-id="76e87-247">2.0</span></span>        |
| <span data-ttu-id="76e87-248">Biblioteca de clases de Razor</span><span class="sxs-lookup"><span data-stu-id="76e87-248">Razor Class Library</span></span>                          | [<span data-ttu-id="76e87-249">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="76e87-249">razorclasslib</span></span>](#razorclasslib) | <span data-ttu-id="76e87-250">[C#]</span><span class="sxs-lookup"><span data-stu-id="76e87-250">[C#]</span></span>         | <span data-ttu-id="76e87-251">Web/Razor/Biblioteca/Biblioteca de clases de Razor</span><span class="sxs-lookup"><span data-stu-id="76e87-251">Web/Razor/Library/Razor Class Library</span></span> | <span data-ttu-id="76e87-252">2.1</span><span class="sxs-lookup"><span data-stu-id="76e87-252">2.1</span></span>        |
| <span data-ttu-id="76e87-253">ASP.NET Core Web API</span><span class="sxs-lookup"><span data-stu-id="76e87-253">ASP.NET Core Web API</span></span>                         | [<span data-ttu-id="76e87-254">webapi</span><span class="sxs-lookup"><span data-stu-id="76e87-254">webapi</span></span>](#webapi)               | <span data-ttu-id="76e87-255">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="76e87-255">[C#], F#</span></span>     | <span data-ttu-id="76e87-256">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="76e87-256">Web/WebAPI</span></span>                            | <span data-ttu-id="76e87-257">1.0</span><span class="sxs-lookup"><span data-stu-id="76e87-257">1.0</span></span>        |
| <span data-ttu-id="76e87-258">Servicio gRPC de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="76e87-258">ASP.NET Core gRPC Service</span></span>                    | [<span data-ttu-id="76e87-259">grpc</span><span class="sxs-lookup"><span data-stu-id="76e87-259">grpc</span></span>](#web-others)             | <span data-ttu-id="76e87-260">[C#]</span><span class="sxs-lookup"><span data-stu-id="76e87-260">[C#]</span></span>         | <span data-ttu-id="76e87-261">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="76e87-261">Web/gRPC</span></span>                              | <span data-ttu-id="76e87-262">3.0</span><span class="sxs-lookup"><span data-stu-id="76e87-262">3.0</span></span>        |
| <span data-ttu-id="76e87-263">Archivo de búfer de protocolo</span><span class="sxs-lookup"><span data-stu-id="76e87-263">Protocol Buffer File</span></span>                         | [<span data-ttu-id="76e87-264">proto</span><span class="sxs-lookup"><span data-stu-id="76e87-264">proto</span></span>](#namespace)             |              | <span data-ttu-id="76e87-265">Web/gRPC</span><span class="sxs-lookup"><span data-stu-id="76e87-265">Web/gRPC</span></span>                              | <span data-ttu-id="76e87-266">3.0</span><span class="sxs-lookup"><span data-stu-id="76e87-266">3.0</span></span>        |
| <span data-ttu-id="76e87-267">Archivo dotnet gitignore</span><span class="sxs-lookup"><span data-stu-id="76e87-267">dotnet gitignore file</span></span>                        | `gitignore`                     |              | <span data-ttu-id="76e87-268">Configuración</span><span class="sxs-lookup"><span data-stu-id="76e87-268">Config</span></span>                                | <span data-ttu-id="76e87-269">3.0</span><span class="sxs-lookup"><span data-stu-id="76e87-269">3.0</span></span>        |
| <span data-ttu-id="76e87-270">archivo global.json</span><span class="sxs-lookup"><span data-stu-id="76e87-270">global.json file</span></span>                             | [<span data-ttu-id="76e87-271">globaljson</span><span class="sxs-lookup"><span data-stu-id="76e87-271">globaljson</span></span>](#globaljson)       |              | <span data-ttu-id="76e87-272">Configuración</span><span class="sxs-lookup"><span data-stu-id="76e87-272">Config</span></span>                                | <span data-ttu-id="76e87-273">2.0</span><span class="sxs-lookup"><span data-stu-id="76e87-273">2.0</span></span>        |
| <span data-ttu-id="76e87-274">Configuración de NuGet</span><span class="sxs-lookup"><span data-stu-id="76e87-274">NuGet Config</span></span>                                 | `nugetconfig`                   |              | <span data-ttu-id="76e87-275">Configuración</span><span class="sxs-lookup"><span data-stu-id="76e87-275">Config</span></span>                                | <span data-ttu-id="76e87-276">1.0</span><span class="sxs-lookup"><span data-stu-id="76e87-276">1.0</span></span>        |
| <span data-ttu-id="76e87-277">Archivo de manifiesto de la herramienta local dotnet</span><span class="sxs-lookup"><span data-stu-id="76e87-277">dotnet local tool manifest file</span></span>              | `tool-manifest`                 |              | <span data-ttu-id="76e87-278">Configuración</span><span class="sxs-lookup"><span data-stu-id="76e87-278">Config</span></span>                                | <span data-ttu-id="76e87-279">3.0</span><span class="sxs-lookup"><span data-stu-id="76e87-279">3.0</span></span>        |
| <span data-ttu-id="76e87-280">Configuración web</span><span class="sxs-lookup"><span data-stu-id="76e87-280">Web Config</span></span>                                   | `webconfig`                     |              | <span data-ttu-id="76e87-281">Configuración</span><span class="sxs-lookup"><span data-stu-id="76e87-281">Config</span></span>                                | <span data-ttu-id="76e87-282">1.0</span><span class="sxs-lookup"><span data-stu-id="76e87-282">1.0</span></span>        |
| <span data-ttu-id="76e87-283">Archivo de solución</span><span class="sxs-lookup"><span data-stu-id="76e87-283">Solution File</span></span>                                | `sln`                           |              | <span data-ttu-id="76e87-284">Soluciones</span><span class="sxs-lookup"><span data-stu-id="76e87-284">Solution</span></span>                              | <span data-ttu-id="76e87-285">1.0</span><span class="sxs-lookup"><span data-stu-id="76e87-285">1.0</span></span>        |

## <a name="options"></a><span data-ttu-id="76e87-286">Opciones</span><span class="sxs-lookup"><span data-stu-id="76e87-286">Options</span></span>

- **`--dry-run`**

  <span data-ttu-id="76e87-287">Muestra un resumen de lo que sucedería si se ejecutara el comando determinado.</span><span class="sxs-lookup"><span data-stu-id="76e87-287">Displays a summary of what would happen if the given command were run.</span></span> <span data-ttu-id="76e87-288">Disponible a partir del SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="76e87-288">Available since .NET Core 2.2 SDK.</span></span>

- **`--force`**

  <span data-ttu-id="76e87-289">Fuerza la generación de contenido incluso aunque se vayan a cambiar los archivos existentes.</span><span class="sxs-lookup"><span data-stu-id="76e87-289">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="76e87-290">Es necesario si la plantilla elegida invalidará los archivos existentes en el directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="76e87-290">This is required when the template chosen would override existing files in the output directory.</span></span>

- **`-h|--help`**

  <span data-ttu-id="76e87-291">Imprime la ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="76e87-291">Prints out help for the command.</span></span> <span data-ttu-id="76e87-292">Puede invocarse para el propio comando `dotnet new` o para cualquier plantilla.</span><span class="sxs-lookup"><span data-stu-id="76e87-292">It can be invoked for the `dotnet new` command itself or for any template.</span></span> <span data-ttu-id="76e87-293">Por ejemplo, `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="76e87-293">For example, `dotnet new mvc --help`.</span></span>

- **`-i|--install <PATH|NUGET_ID>`**

  <span data-ttu-id="76e87-294">Instala un paquete de plantillas desde los parámetros `PATH` o `NUGET_ID` proporcionados.</span><span class="sxs-lookup"><span data-stu-id="76e87-294">Installs a template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="76e87-295">Si quiere instalar una versión preliminar de un paquete de plantilla, tendrá que especificar la versión en el formato de `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="76e87-295">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="76e87-296">De forma predeterminada, `dotnet new` pasa \* para la versión, que representa la última versión estable del paquete.</span><span class="sxs-lookup"><span data-stu-id="76e87-296">By default, `dotnet new` passes \* for the version, which represents the latest stable package version.</span></span> <span data-ttu-id="76e87-297">Vea un ejemplo en la sección [Ejemplos](#examples).</span><span class="sxs-lookup"><span data-stu-id="76e87-297">See an example in the [Examples](#examples) section.</span></span>
  
  <span data-ttu-id="76e87-298">Si ya hay instalada una versión de la plantilla al ejecutar este comando, la plantilla se actualizará a la versión especificada o a la versión estable más reciente si no se ha especificado ninguna versión.</span><span class="sxs-lookup"><span data-stu-id="76e87-298">If a version of the template was already installed when you run this command, the template will be updated to the specified version, or to the latest stable version if no version was specified.</span></span>

  <span data-ttu-id="76e87-299">Para obtener información sobre cómo crear plantillas personalizadas, consulte [Custom templates for dotnet new](custom-templates.md) (Plantillas personalizadas para dotnet new).</span><span class="sxs-lookup"><span data-stu-id="76e87-299">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

- **`-l|--list`**

  <span data-ttu-id="76e87-300">Muestra las plantillas que contienen el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="76e87-300">Lists templates containing the specified name.</span></span> <span data-ttu-id="76e87-301">Si no se especifica ningún nombre, enumera todas las plantillas.</span><span class="sxs-lookup"><span data-stu-id="76e87-301">If no name is specified, lists all templates.</span></span>

- **`-lang|--language {C#|F#|VB}`**

  <span data-ttu-id="76e87-302">El lenguaje de la plantilla que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="76e87-302">The language of the template to create.</span></span> <span data-ttu-id="76e87-303">El lenguaje aceptado cambia según la plantilla (vea los valores predeterminados en la sección [argumentos](#arguments)).</span><span class="sxs-lookup"><span data-stu-id="76e87-303">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="76e87-304">No es válido para algunas plantillas.</span><span class="sxs-lookup"><span data-stu-id="76e87-304">Not valid for some templates.</span></span>

  > [!NOTE]
  > <span data-ttu-id="76e87-305">Algunos shells interpretan `#` como un carácter especial.</span><span class="sxs-lookup"><span data-stu-id="76e87-305">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="76e87-306">En esos casos, incluya el valor del parámetro de lenguaje entre comillas.</span><span class="sxs-lookup"><span data-stu-id="76e87-306">In those cases, enclose the language parameter value in quotes.</span></span> <span data-ttu-id="76e87-307">Por ejemplo, `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="76e87-307">For example, `dotnet new console -lang "F#"`.</span></span>

- **`-n|--name <OUTPUT_NAME>`**

  <span data-ttu-id="76e87-308">El nombre de la salida creada.</span><span class="sxs-lookup"><span data-stu-id="76e87-308">The name for the created output.</span></span> <span data-ttu-id="76e87-309">Si no se especifica ningún nombre, se usa el nombre del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="76e87-309">If no name is specified, the name of the current directory is used.</span></span>

- **`--nuget-source`**

  <span data-ttu-id="76e87-310">Especifica un origen de NuGet para usarlo durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="76e87-310">Specifies a NuGet source to use during install.</span></span> <span data-ttu-id="76e87-311">Disponible a partir del SDK de .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="76e87-311">Available since .NET Core 2.1 SDK.</span></span>

- **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="76e87-312">La ubicación para colocar la salida generada.</span><span class="sxs-lookup"><span data-stu-id="76e87-312">Location to place the generated output.</span></span> <span data-ttu-id="76e87-313">El valor predeterminado es el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="76e87-313">The default is the current directory.</span></span>

- **`--type`**

  <span data-ttu-id="76e87-314">Filtra plantillas en función de los tipos disponibles.</span><span class="sxs-lookup"><span data-stu-id="76e87-314">Filters templates based on available types.</span></span> <span data-ttu-id="76e87-315">Los valores predefinidos son "project", "item" u "other".</span><span class="sxs-lookup"><span data-stu-id="76e87-315">Predefined values are "project", "item", or "other".</span></span>

- **`-u|--uninstall [PATH|NUGET_ID]`**

  <span data-ttu-id="76e87-316">Desinstala un paquete de plantillas en los parámetros `PATH` o `NUGET_ID` proporcionados.</span><span class="sxs-lookup"><span data-stu-id="76e87-316">Uninstalls a template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="76e87-317">Si no se especifica el valor `<PATH|NUGET_ID>`, se muestran todos los paquetes de plantillas instalados actualmente y sus plantillas asociadas.</span><span class="sxs-lookup"><span data-stu-id="76e87-317">When the `<PATH|NUGET_ID>` value isn't specified, all currently installed template packs and their associated templates are displayed.</span></span> <span data-ttu-id="76e87-318">Al especificar `NUGET_ID`, no incluya el número de versión.</span><span class="sxs-lookup"><span data-stu-id="76e87-318">When specifying `NUGET_ID`, don't include the version number.</span></span>

  <span data-ttu-id="76e87-319">Si no especifica un parámetro en esta opción, el comando muestra las plantillas instaladas y detalles sobre ellas.</span><span class="sxs-lookup"><span data-stu-id="76e87-319">If you don't specify a parameter to this option, the command lists the installed templates and details about them.</span></span>

  > [!NOTE]
  > <span data-ttu-id="76e87-320">Para desinstalar una plantilla mediante `PATH`, debe usar el nombre completo de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="76e87-320">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="76e87-321">Por ejemplo, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* funcionará, pero *./GarciaSoftware.ConsoleTemplate.CSharp* desde la carpeta contenedora no lo hará.</span><span class="sxs-lookup"><span data-stu-id="76e87-321">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
  > <span data-ttu-id="76e87-322">No incluya ninguna barra diagonal para finalizar el directorio en la ruta de acceso a la plantilla.</span><span class="sxs-lookup"><span data-stu-id="76e87-322">Don't include a final terminating directory slash on your template path.</span></span>

- **`--update-apply`**

  <span data-ttu-id="76e87-323">Comprueba si hay actualizaciones disponibles de los paquetes de plantillas instalados actualmente y las instala.</span><span class="sxs-lookup"><span data-stu-id="76e87-323">Checks if there are updates available for the template packs that are currently installed and installs them.</span></span> <span data-ttu-id="76e87-324">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="76e87-324">Available since .NET Core 3.0 SDK.</span></span>

- **`--update-check`**

  <span data-ttu-id="76e87-325">Comprueba si hay actualizaciones disponibles de los paquetes de plantillas instalados actualmente.</span><span class="sxs-lookup"><span data-stu-id="76e87-325">Checks if there are updates available for the template packs that are currently installed.</span></span> <span data-ttu-id="76e87-326">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="76e87-326">Available since .NET Core 3.0 SDK.</span></span>

## <a name="template-options"></a><span data-ttu-id="76e87-327">Opciones de plantilla</span><span class="sxs-lookup"><span data-stu-id="76e87-327">Template options</span></span>

<span data-ttu-id="76e87-328">Cada plantilla de proyecto puede tener opciones adicionales disponibles.</span><span class="sxs-lookup"><span data-stu-id="76e87-328">Each project template may have additional options available.</span></span> <span data-ttu-id="76e87-329">Las plantillas principales tienen las siguientes opciones adicionales:</span><span class="sxs-lookup"><span data-stu-id="76e87-329">The core templates have the following additional options:</span></span>

### <a name="console"></a><span data-ttu-id="76e87-330">consola</span><span class="sxs-lookup"><span data-stu-id="76e87-330">console</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="76e87-331">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="76e87-331">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="76e87-332">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="76e87-332">Available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="76e87-333">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="76e87-333">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="76e87-334">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="76e87-334">SDK version</span></span> | <span data-ttu-id="76e87-335">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="76e87-335">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="76e87-336">3.1</span><span class="sxs-lookup"><span data-stu-id="76e87-336">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="76e87-337">3.0</span><span class="sxs-lookup"><span data-stu-id="76e87-337">3.0</span></span>         | `netcoreapp3.0` |

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="76e87-338">Establece la propiedad `LangVersion` en el archivo del proyecto creado.</span><span class="sxs-lookup"><span data-stu-id="76e87-338">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="76e87-339">Por ejemplo, use `--langVersion 7.3` para emplear C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="76e87-339">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="76e87-340">No es compatible con F#.</span><span class="sxs-lookup"><span data-stu-id="76e87-340">Not supported for F#.</span></span> <span data-ttu-id="76e87-341">Disponible a partir del SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="76e87-341">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="76e87-342">Para obtener una lista de las versiones predeterminadas de C#, vea [Valores predeterminados](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="76e87-342">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="76e87-343">Si se especifica, no se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="76e87-343">If specified, doesn't execute an implicit restore during project creation.</span></span> <span data-ttu-id="76e87-344">Disponible a partir del SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="76e87-344">Available since .NET Core 2.2 SDK.</span></span>

***

### <a name="classlib"></a><span data-ttu-id="76e87-345">classlib</span><span class="sxs-lookup"><span data-stu-id="76e87-345">classlib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="76e87-346">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="76e87-346">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="76e87-347">Valores: `netcoreapp<version>` para crear una biblioteca de clases de .NET Core o `netstandard<version>` para crear una biblioteca de clases de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="76e87-347">Values: `netcoreapp<version>` to create a .NET Core Class Library or `netstandard<version>` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="76e87-348">El valor predeterminado es `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="76e87-348">The default value is `netstandard2.0`.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="76e87-349">Establece la propiedad `LangVersion` en el archivo del proyecto creado.</span><span class="sxs-lookup"><span data-stu-id="76e87-349">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="76e87-350">Por ejemplo, use `--langVersion 7.3` para emplear C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="76e87-350">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="76e87-351">No es compatible con F#.</span><span class="sxs-lookup"><span data-stu-id="76e87-351">Not supported for F#.</span></span> <span data-ttu-id="76e87-352">Disponible a partir del SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="76e87-352">Available since .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="76e87-353">Para obtener una lista de las versiones predeterminadas de C#, vea [Valores predeterminados](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="76e87-353">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="76e87-354">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="76e87-354">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="wpf"></a> <span data-ttu-id="76e87-355">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span><span class="sxs-lookup"><span data-stu-id="76e87-355">wpf, wpflib, wpfcustomcontrollib, wpfusercontrollib</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="76e87-356">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="76e87-356">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="76e87-357">El valor predeterminado es `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="76e87-357">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="76e87-358">Disponible a partir del SDK de .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="76e87-358">Available since .NET Core 3.1 SDK.</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="76e87-359">Establece la propiedad `LangVersion` en el archivo del proyecto creado.</span><span class="sxs-lookup"><span data-stu-id="76e87-359">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="76e87-360">Por ejemplo, use `--langVersion 7.3` para emplear C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="76e87-360">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="76e87-361">Para obtener una lista de las versiones predeterminadas de C#, vea [Valores predeterminados](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="76e87-361">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="76e87-362">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="76e87-362">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="winforms"></a> <span data-ttu-id="76e87-363">winforms, winformslib</span><span class="sxs-lookup"><span data-stu-id="76e87-363">winforms, winformslib</span></span>

- **`--langVersion <VERSION_NUMBER>`**

  <span data-ttu-id="76e87-364">Establece la propiedad `LangVersion` en el archivo del proyecto creado.</span><span class="sxs-lookup"><span data-stu-id="76e87-364">Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="76e87-365">Por ejemplo, use `--langVersion 7.3` para emplear C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="76e87-365">For example, use `--langVersion 7.3` to use C# 7.3.</span></span>

  <span data-ttu-id="76e87-366">Para obtener una lista de las versiones predeterminadas de C#, vea [Valores predeterminados](../../csharp/language-reference/configure-language-version.md#defaults).</span><span class="sxs-lookup"><span data-stu-id="76e87-366">For a list of default C# versions, see [Defaults](../../csharp/language-reference/configure-language-version.md#defaults).</span></span>

- **`--no-restore`**

  <span data-ttu-id="76e87-367">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="76e87-367">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="web-others"></a> <span data-ttu-id="76e87-368">worker, grpc</span><span class="sxs-lookup"><span data-stu-id="76e87-368">worker, grpc</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="76e87-369">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="76e87-369">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="76e87-370">El valor predeterminado es `netcoreapp3.1`.</span><span class="sxs-lookup"><span data-stu-id="76e87-370">The default value is `netcoreapp3.1`.</span></span> <span data-ttu-id="76e87-371">Disponible a partir del SDK de .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="76e87-371">Available since .NET Core 3.1 SDK.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="76e87-372">Excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="76e87-372">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="76e87-373">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="76e87-373">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="test"></a> <span data-ttu-id="76e87-374">mstest, xunit</span><span class="sxs-lookup"><span data-stu-id="76e87-374">mstest, xunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="76e87-375">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="76e87-375">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="76e87-376">Opción disponible a partir del SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="76e87-376">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="76e87-377">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="76e87-377">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="76e87-378">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="76e87-378">SDK version</span></span> | <span data-ttu-id="76e87-379">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="76e87-379">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="76e87-380">3.1</span><span class="sxs-lookup"><span data-stu-id="76e87-380">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="76e87-381">3.0</span><span class="sxs-lookup"><span data-stu-id="76e87-381">3.0</span></span>         | `netcoreapp3.0` |

- **`-p|--enable-pack`**

  <span data-ttu-id="76e87-382">Habilita el empaquetado del proyecto mediante [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="76e87-382">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="76e87-383">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="76e87-383">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="nunit"></a><span data-ttu-id="76e87-384">nunit</span><span class="sxs-lookup"><span data-stu-id="76e87-384">nunit</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="76e87-385">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="76e87-385">Specifies the [framework](../../standard/frameworks.md) to target.</span></span>

  <span data-ttu-id="76e87-386">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="76e87-386">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="76e87-387">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="76e87-387">SDK version</span></span> | <span data-ttu-id="76e87-388">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="76e87-388">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="76e87-389">3.1</span><span class="sxs-lookup"><span data-stu-id="76e87-389">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="76e87-390">3.0</span><span class="sxs-lookup"><span data-stu-id="76e87-390">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="76e87-391">2.2</span><span class="sxs-lookup"><span data-stu-id="76e87-391">2.2</span></span>         | `netcoreapp2.2` |
  | <span data-ttu-id="76e87-392">2.1</span><span class="sxs-lookup"><span data-stu-id="76e87-392">2.1</span></span>         | `netcoreapp2.1` |

- **`-p|--enable-pack`**

  <span data-ttu-id="76e87-393">Habilita el empaquetado del proyecto mediante [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="76e87-393">Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

- **`--no-restore`**

  <span data-ttu-id="76e87-394">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="76e87-394">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="page"></a><span data-ttu-id="76e87-395">página</span><span class="sxs-lookup"><span data-stu-id="76e87-395">page</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="76e87-396">Espacio de nombres del código generado.</span><span class="sxs-lookup"><span data-stu-id="76e87-396">Namespace for the generated code.</span></span> <span data-ttu-id="76e87-397">El valor predeterminado es `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="76e87-397">The default value is `MyApp.Namespace`.</span></span>

- **`-np|--no-pagemodel`**

  <span data-ttu-id="76e87-398">Crea la página sin PageModel.</span><span class="sxs-lookup"><span data-stu-id="76e87-398">Creates the page without a PageModel.</span></span>

***

### <a name="namespace"></a> <span data-ttu-id="76e87-399">viewimports, proto</span><span class="sxs-lookup"><span data-stu-id="76e87-399">viewimports, proto</span></span>

- **`-na|--namespace <NAMESPACE_NAME>`**

  <span data-ttu-id="76e87-400">Espacio de nombres del código generado.</span><span class="sxs-lookup"><span data-stu-id="76e87-400">Namespace for the generated code.</span></span> <span data-ttu-id="76e87-401">El valor predeterminado es `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="76e87-401">The default value is `MyApp.Namespace`.</span></span>

***

### <a name="blazorserver"></a><span data-ttu-id="76e87-402">blazorserver</span><span class="sxs-lookup"><span data-stu-id="76e87-402">blazorserver</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="76e87-403">Tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="76e87-403">The type of authentication to use.</span></span> <span data-ttu-id="76e87-404">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="76e87-404">The possible values are:</span></span>

  - <span data-ttu-id="76e87-405">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="76e87-405">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="76e87-406">`Individual`: autenticación individual.</span><span class="sxs-lookup"><span data-stu-id="76e87-406">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="76e87-407">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="76e87-407">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="76e87-408">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="76e87-408">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="76e87-409">`MultiOrg`: autenticación organizativa para varios inquilinos.</span><span class="sxs-lookup"><span data-stu-id="76e87-409">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="76e87-410">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="76e87-410">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="76e87-411">Instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="76e87-411">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="76e87-412">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="76e87-412">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="76e87-413">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="76e87-413">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="76e87-414">Identificador de la directiva de registro e inicio de sesión de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="76e87-414">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="76e87-415">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="76e87-415">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="76e87-416">Identificador de la directiva de restablecimiento de contraseñas de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="76e87-416">The reset password policy ID for this project.</span></span> <span data-ttu-id="76e87-417">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="76e87-417">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="76e87-418">Identificador de la directiva de edición de perfiles de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="76e87-418">The edit profile policy ID for this project.</span></span> <span data-ttu-id="76e87-419">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="76e87-419">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="76e87-420">Instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="76e87-420">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="76e87-421">Úsela con las autenticaciones `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="76e87-421">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="76e87-422">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="76e87-422">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="76e87-423">Identificador de cliente de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="76e87-423">The Client ID for this project.</span></span> <span data-ttu-id="76e87-424">Úsela con las autenticaciones `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="76e87-424">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="76e87-425">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="76e87-425">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="76e87-426">Dominio del inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="76e87-426">The domain for the directory tenant.</span></span> <span data-ttu-id="76e87-427">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="76e87-427">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="76e87-428">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="76e87-428">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="76e87-429">Identificador de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="76e87-429">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="76e87-430">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="76e87-430">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="76e87-431">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="76e87-431">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="76e87-432">Ruta de acceso de solicitud de la ruta de acceso de la base de la aplicación del URI de redirección.</span><span class="sxs-lookup"><span data-stu-id="76e87-432">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="76e87-433">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="76e87-433">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="76e87-434">El valor predeterminado es `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="76e87-434">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="76e87-435">Concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="76e87-435">Allows this application read-access to the directory.</span></span> <span data-ttu-id="76e87-436">Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="76e87-436">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="76e87-437">Excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="76e87-437">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="76e87-438">Desactiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="76e87-438">Turns off HTTPS.</span></span> <span data-ttu-id="76e87-439">Esta opción solo se aplica si no se usan `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg` en `--auth`.</span><span class="sxs-lookup"><span data-stu-id="76e87-439">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used for `--auth`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="76e87-440">Especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="76e87-440">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="76e87-441">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="76e87-441">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`--no-restore`**

  <span data-ttu-id="76e87-442">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="76e87-442">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="web"></a><span data-ttu-id="76e87-443">web</span><span class="sxs-lookup"><span data-stu-id="76e87-443">web</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="76e87-444">Excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="76e87-444">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="76e87-445">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="76e87-445">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="76e87-446">Opción no disponible en el SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="76e87-446">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="76e87-447">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="76e87-447">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="76e87-448">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="76e87-448">SDK version</span></span> | <span data-ttu-id="76e87-449">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="76e87-449">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="76e87-450">3.1</span><span class="sxs-lookup"><span data-stu-id="76e87-450">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="76e87-451">3.0</span><span class="sxs-lookup"><span data-stu-id="76e87-451">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="76e87-452">2.1</span><span class="sxs-lookup"><span data-stu-id="76e87-452">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="76e87-453">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="76e87-453">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="76e87-454">Desactiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="76e87-454">Turns off HTTPS.</span></span>

***

### <a name="web-options"></a> <span data-ttu-id="76e87-455">mvc, webapp</span><span class="sxs-lookup"><span data-stu-id="76e87-455">mvc, webapp</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="76e87-456">Tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="76e87-456">The type of authentication to use.</span></span> <span data-ttu-id="76e87-457">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="76e87-457">The possible values are:</span></span>

  - <span data-ttu-id="76e87-458">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="76e87-458">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="76e87-459">`Individual`: autenticación individual.</span><span class="sxs-lookup"><span data-stu-id="76e87-459">`Individual` - Individual authentication.</span></span>
  - <span data-ttu-id="76e87-460">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="76e87-460">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="76e87-461">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="76e87-461">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="76e87-462">`MultiOrg`: autenticación organizativa para varios inquilinos.</span><span class="sxs-lookup"><span data-stu-id="76e87-462">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
  - <span data-ttu-id="76e87-463">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="76e87-463">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="76e87-464">Instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="76e87-464">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="76e87-465">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="76e87-465">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="76e87-466">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="76e87-466">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="76e87-467">Identificador de la directiva de registro e inicio de sesión de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="76e87-467">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="76e87-468">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="76e87-468">Use with `IndividualB2C` authentication.</span></span>

- **`-rp|--reset-password-policy-id <ID>`**

  <span data-ttu-id="76e87-469">Identificador de la directiva de restablecimiento de contraseñas de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="76e87-469">The reset password policy ID for this project.</span></span> <span data-ttu-id="76e87-470">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="76e87-470">Use with `IndividualB2C` authentication.</span></span>

- **`-ep|--edit-profile-policy-id <ID>`**

  <span data-ttu-id="76e87-471">Identificador de la directiva de edición de perfiles de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="76e87-471">The edit profile policy ID for this project.</span></span> <span data-ttu-id="76e87-472">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="76e87-472">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="76e87-473">Instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="76e87-473">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="76e87-474">Úsela con las autenticaciones `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="76e87-474">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="76e87-475">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="76e87-475">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="76e87-476">Identificador de cliente de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="76e87-476">The Client ID for this project.</span></span> <span data-ttu-id="76e87-477">Úsela con las autenticaciones `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="76e87-477">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="76e87-478">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="76e87-478">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="76e87-479">Dominio del inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="76e87-479">The domain for the directory tenant.</span></span> <span data-ttu-id="76e87-480">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="76e87-480">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="76e87-481">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="76e87-481">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="76e87-482">Identificador de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="76e87-482">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="76e87-483">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="76e87-483">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="76e87-484">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="76e87-484">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`--callback-path <PATH>`**

  <span data-ttu-id="76e87-485">Ruta de acceso de solicitud de la ruta de acceso de la base de la aplicación del URI de redirección.</span><span class="sxs-lookup"><span data-stu-id="76e87-485">The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="76e87-486">Úsela con las autenticaciones `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="76e87-486">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="76e87-487">El valor predeterminado es `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="76e87-487">The default value is `/signin-oidc`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="76e87-488">Concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="76e87-488">Allows this application read-access to the directory.</span></span> <span data-ttu-id="76e87-489">Solo se aplica a las autenticaciones `SingleOrg` y `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="76e87-489">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="76e87-490">Excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="76e87-490">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="76e87-491">Desactiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="76e87-491">Turns off HTTPS.</span></span> <span data-ttu-id="76e87-492">Esta opción solo se aplica si no se usan `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="76e87-492">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="76e87-493">Especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="76e87-493">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="76e87-494">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="76e87-494">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="76e87-495">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="76e87-495">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="76e87-496">Opción disponible a partir del SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="76e87-496">Option available since .NET Core 3.0 SDK.</span></span>

  <span data-ttu-id="76e87-497">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="76e87-497">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="76e87-498">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="76e87-498">SDK version</span></span> | <span data-ttu-id="76e87-499">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="76e87-499">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="76e87-500">3.1</span><span class="sxs-lookup"><span data-stu-id="76e87-500">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="76e87-501">3.0</span><span class="sxs-lookup"><span data-stu-id="76e87-501">3.0</span></span>         | `netcoreapp3.0` |

- **`--no-restore`**

  <span data-ttu-id="76e87-502">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="76e87-502">Doesn't execute an implicit restore during project creation.</span></span>

- **`--use-browserlink`**

  <span data-ttu-id="76e87-503">Incluye BrowserLink en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="76e87-503">Includes BrowserLink in the project.</span></span> <span data-ttu-id="76e87-504">Opción no disponible en el SDK de .NET Core 2.2 y 3.1.</span><span class="sxs-lookup"><span data-stu-id="76e87-504">Option not available in .NET Core 2.2 and 3.1 SDK.</span></span>

***

### <a name="spa"></a> <span data-ttu-id="76e87-505">angular, react</span><span class="sxs-lookup"><span data-stu-id="76e87-505">angular, react</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="76e87-506">Tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="76e87-506">The type of authentication to use.</span></span> <span data-ttu-id="76e87-507">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="76e87-507">Available since .NET Core 3.0 SDK.</span></span>
  
  <span data-ttu-id="76e87-508">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="76e87-508">The possible values are:</span></span>

  - <span data-ttu-id="76e87-509">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="76e87-509">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="76e87-510">`Individual`: autenticación individual.</span><span class="sxs-lookup"><span data-stu-id="76e87-510">`Individual` - Individual authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="76e87-511">Excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="76e87-511">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-restore`**

  <span data-ttu-id="76e87-512">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="76e87-512">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="76e87-513">Desactiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="76e87-513">Turns off HTTPS.</span></span> <span data-ttu-id="76e87-514">Esta opción solo se aplica si la autenticación es `None`.</span><span class="sxs-lookup"><span data-stu-id="76e87-514">This option only applies if authentication is `None`.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="76e87-515">Especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="76e87-515">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="76e87-516">Solo se aplica a las autenticaciones `Individual` y `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="76e87-516">Only applies to `Individual` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="76e87-517">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="76e87-517">Available since .NET Core 3.0 SDK.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="76e87-518">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="76e87-518">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="76e87-519">Opción no disponible en el SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="76e87-519">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="76e87-520">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="76e87-520">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="76e87-521">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="76e87-521">SDK version</span></span> | <span data-ttu-id="76e87-522">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="76e87-522">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="76e87-523">3.1</span><span class="sxs-lookup"><span data-stu-id="76e87-523">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="76e87-524">3.0</span><span class="sxs-lookup"><span data-stu-id="76e87-524">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="76e87-525">2.1</span><span class="sxs-lookup"><span data-stu-id="76e87-525">2.1</span></span>         | `netcoreapp2.0` |

***

### <a name="reactredux"></a><span data-ttu-id="76e87-526">reactredux</span><span class="sxs-lookup"><span data-stu-id="76e87-526">reactredux</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="76e87-527">Excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="76e87-527">Excludes *launchSettings.json* from the generated template.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="76e87-528">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="76e87-528">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="76e87-529">Opción no disponible en el SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="76e87-529">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="76e87-530">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="76e87-530">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="76e87-531">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="76e87-531">SDK version</span></span> | <span data-ttu-id="76e87-532">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="76e87-532">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="76e87-533">3.1</span><span class="sxs-lookup"><span data-stu-id="76e87-533">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="76e87-534">3.0</span><span class="sxs-lookup"><span data-stu-id="76e87-534">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="76e87-535">2.1</span><span class="sxs-lookup"><span data-stu-id="76e87-535">2.1</span></span>         | `netcoreapp2.0` |

- **`--no-restore`**

  <span data-ttu-id="76e87-536">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="76e87-536">Doesn't execute an implicit restore during project creation.</span></span>

- **`--no-https`**

  <span data-ttu-id="76e87-537">Desactiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="76e87-537">Turns off HTTPS.</span></span>

***

### <a name="razorclasslib"></a><span data-ttu-id="76e87-538">razorclasslib</span><span class="sxs-lookup"><span data-stu-id="76e87-538">razorclasslib</span></span>

- **`--no-restore`**

  <span data-ttu-id="76e87-539">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="76e87-539">Doesn't execute an implicit restore during project creation.</span></span>

- **`-s|--support-pages-and-views`**

  <span data-ttu-id="76e87-540">Permite agregar vistas y páginas de Razor tradicionales además de los componentes a esta biblioteca.</span><span class="sxs-lookup"><span data-stu-id="76e87-540">Supports adding traditional Razor pages and Views in addition to components to this library.</span></span> <span data-ttu-id="76e87-541">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="76e87-541">Available since .NET Core 3.0 SDK.</span></span>

***
  
### <a name="webapi"></a><span data-ttu-id="76e87-542">webapi</span><span class="sxs-lookup"><span data-stu-id="76e87-542">webapi</span></span>

- **`-au|--auth <AUTHENTICATION_TYPE>`**

  <span data-ttu-id="76e87-543">Tipo de autenticación que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="76e87-543">The type of authentication to use.</span></span> <span data-ttu-id="76e87-544">Los valores posibles son:</span><span class="sxs-lookup"><span data-stu-id="76e87-544">The possible values are:</span></span>

  - <span data-ttu-id="76e87-545">`None`: sin autenticación (valor predeterminado).</span><span class="sxs-lookup"><span data-stu-id="76e87-545">`None` - No authentication (Default).</span></span>
  - <span data-ttu-id="76e87-546">`IndividualB2C`: autenticación individual con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="76e87-546">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
  - <span data-ttu-id="76e87-547">`SingleOrg`: autenticación organizativa para un solo inquilino.</span><span class="sxs-lookup"><span data-stu-id="76e87-547">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
  - <span data-ttu-id="76e87-548">`Windows`: autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="76e87-548">`Windows` - Windows authentication.</span></span>

- **`--aad-b2c-instance <INSTANCE>`**

  <span data-ttu-id="76e87-549">Instancia de Azure Active Directory B2C con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="76e87-549">The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="76e87-550">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="76e87-550">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="76e87-551">El valor predeterminado es `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="76e87-551">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

- **`-ssp|--susi-policy-id <ID>`**

  <span data-ttu-id="76e87-552">Identificador de la directiva de registro e inicio de sesión de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="76e87-552">The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="76e87-553">Úsela con la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="76e87-553">Use with `IndividualB2C` authentication.</span></span>

- **`--aad-instance <INSTANCE>`**

  <span data-ttu-id="76e87-554">Instancia de Azure Active Directory con la que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="76e87-554">The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="76e87-555">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="76e87-555">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="76e87-556">El valor predeterminado es `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="76e87-556">The default value is `https://login.microsoftonline.com/`.</span></span>

- **`--client-id <ID>`**

  <span data-ttu-id="76e87-557">Identificador de cliente de este proyecto.</span><span class="sxs-lookup"><span data-stu-id="76e87-557">The Client ID for this project.</span></span> <span data-ttu-id="76e87-558">Úsela con las autenticaciones `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="76e87-558">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="76e87-559">El valor predeterminado es `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="76e87-559">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

- **`--domain <DOMAIN>`**

  <span data-ttu-id="76e87-560">Dominio del inquilino del directorio.</span><span class="sxs-lookup"><span data-stu-id="76e87-560">The domain for the directory tenant.</span></span> <span data-ttu-id="76e87-561">Úsela con las autenticaciones `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="76e87-561">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="76e87-562">El valor predeterminado es `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="76e87-562">The default value is `qualified.domain.name`.</span></span>

- **`--tenant-id <ID>`**

  <span data-ttu-id="76e87-563">Identificador de inquilino del directorio con el que se realiza la conexión.</span><span class="sxs-lookup"><span data-stu-id="76e87-563">The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="76e87-564">Úsela con la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="76e87-564">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="76e87-565">El valor predeterminado es `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="76e87-565">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

- **`-r|--org-read-access`**

  <span data-ttu-id="76e87-566">Concede a esta aplicación acceso de lectura al directorio.</span><span class="sxs-lookup"><span data-stu-id="76e87-566">Allows this application read-access to the directory.</span></span> <span data-ttu-id="76e87-567">Solo se aplica a la autenticación `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="76e87-567">Only applies to `SingleOrg` authentication.</span></span>

- **`--exclude-launch-settings`**

  <span data-ttu-id="76e87-568">Excluye *launchSettings.json* de la plantilla generada.</span><span class="sxs-lookup"><span data-stu-id="76e87-568">Excludes *launchSettings.json* from the generated template.</span></span>

- **`--no-https`**

  <span data-ttu-id="76e87-569">Desactiva HTTPS.</span><span class="sxs-lookup"><span data-stu-id="76e87-569">Turns off HTTPS.</span></span> <span data-ttu-id="76e87-570">`app.UseHsts` y `app.UseHttpsRedirection` no se agregan a `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="76e87-570">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="76e87-571">Esta opción solo se aplica si no se usan `IndividualB2C` o `SingleOrg` en la autenticación.</span><span class="sxs-lookup"><span data-stu-id="76e87-571">This option only applies if `IndividualB2C` or `SingleOrg` aren't being used for authentication.</span></span>

- **`-uld|--use-local-db`**

  <span data-ttu-id="76e87-572">Especifica que se debería usar LocalDB en vez de SQLite.</span><span class="sxs-lookup"><span data-stu-id="76e87-572">Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="76e87-573">Solo se aplica a la autenticación `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="76e87-573">Only applies to `IndividualB2C` authentication.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="76e87-574">Especifica el [marco](../../standard/frameworks.md) de destino.</span><span class="sxs-lookup"><span data-stu-id="76e87-574">Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="76e87-575">Opción no disponible en el SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="76e87-575">Option not available in .NET Core 2.2 SDK.</span></span>

  <span data-ttu-id="76e87-576">En la tabla siguiente se enumeran los valores predeterminados según el número de versión del SDK que esté usando:</span><span class="sxs-lookup"><span data-stu-id="76e87-576">The following table lists the default values according to the SDK version number you're using:</span></span>

  | <span data-ttu-id="76e87-577">Versión del SDK</span><span class="sxs-lookup"><span data-stu-id="76e87-577">SDK version</span></span> | <span data-ttu-id="76e87-578">Valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="76e87-578">Default value</span></span>   |
  |-------------|-----------------|
  | <span data-ttu-id="76e87-579">3.1</span><span class="sxs-lookup"><span data-stu-id="76e87-579">3.1</span></span>         | `netcoreapp3.1` |
  | <span data-ttu-id="76e87-580">3.0</span><span class="sxs-lookup"><span data-stu-id="76e87-580">3.0</span></span>         | `netcoreapp3.0` |
  | <span data-ttu-id="76e87-581">2.1</span><span class="sxs-lookup"><span data-stu-id="76e87-581">2.1</span></span>         | `netcoreapp2.1` |

- **`--no-restore`**

  <span data-ttu-id="76e87-582">No se ejecuta ninguna restauración implícita durante la creación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="76e87-582">Doesn't execute an implicit restore during project creation.</span></span>

***

### <a name="globaljson"></a><span data-ttu-id="76e87-583">globaljson</span><span class="sxs-lookup"><span data-stu-id="76e87-583">globaljson</span></span>

- **`--sdk-version <VERSION_NUMBER>`**

  <span data-ttu-id="76e87-584">Especifica la versión del SDK de .NET Core que se usará en el archivo *global.json*.</span><span class="sxs-lookup"><span data-stu-id="76e87-584">Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

***

## <a name="examples"></a><span data-ttu-id="76e87-585">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="76e87-585">Examples</span></span>

- <span data-ttu-id="76e87-586">Creación de un proyecto de aplicación de consola de C# mediante la especificación del nombre de plantilla:</span><span class="sxs-lookup"><span data-stu-id="76e87-586">Create a C# console application project by specifying the template name:</span></span>

  ```dotnetcli
  dotnet new "Console Application"
  ```

- <span data-ttu-id="76e87-587">Creación de un proyecto de aplicación de consola con F# en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="76e87-587">Create an F# console application project in the current directory:</span></span>

  ```dotnetcli
  dotnet new console -lang F#
  ```

- <span data-ttu-id="76e87-588">Creación de un proyecto de biblioteca de clases de .NET Standard en el directorio especificado:</span><span class="sxs-lookup"><span data-stu-id="76e87-588">Create a .NET Standard class library project in the specified directory:</span></span>

  ```dotnetcli
  dotnet new classlib -lang VB -o MyLibrary
  ```

- <span data-ttu-id="76e87-589">Creación de un proyecto MVC de ASP.NET Core C# en el directorio actual sin autenticación:</span><span class="sxs-lookup"><span data-stu-id="76e87-589">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

  ```dotnetcli
  dotnet new mvc -au None
  ```

- <span data-ttu-id="76e87-590">Creación de un proyecto de xUnit:</span><span class="sxs-lookup"><span data-stu-id="76e87-590">Create a new xUnit project:</span></span>

  ```dotnetcli
  dotnet new xunit
  ```

- <span data-ttu-id="76e87-591">Enumeración de todas las plantillas disponibles en las plantillas de aplicación de página única (SPA):</span><span class="sxs-lookup"><span data-stu-id="76e87-591">List all templates available for Single Page Application (SPA) templates:</span></span>

  ```dotnetcli
  dotnet new spa -l
  ```

- <span data-ttu-id="76e87-592">Enumeración de todas las plantillas que coinciden con la subcadena *we*.</span><span class="sxs-lookup"><span data-stu-id="76e87-592">List all templates matching the *we* substring.</span></span> <span data-ttu-id="76e87-593">No se encuentra ninguna coincidencia exacta, por lo que se ejecuta la coincidencia de subcadena con las columnas de nombre corto y de nombre.</span><span class="sxs-lookup"><span data-stu-id="76e87-593">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

  ```dotnetcli
  dotnet new we -l
  ```

- <span data-ttu-id="76e87-594">Intento de invocar a la plantilla que coincide con *ng*.</span><span class="sxs-lookup"><span data-stu-id="76e87-594">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="76e87-595">Si no se puede determinar una única coincidencia, se enumeran las plantillas que son coincidencias parciales.</span><span class="sxs-lookup"><span data-stu-id="76e87-595">If a single match can't be determined, list the templates that are partial matches.</span></span>

  ```dotnetcli
  dotnet new ng
  ```

- <span data-ttu-id="76e87-596">Instalación de la versión 2.0 de las plantillas de SPA de ASP.NET Core:</span><span class="sxs-lookup"><span data-stu-id="76e87-596">Install version 2.0 of the SPA templates for ASP.NET Core:</span></span>

  ```dotnetcli
  dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0
  ```

- <span data-ttu-id="76e87-597">Enumeración de las plantillas instaladas y detalles sobre ellas, incluido cómo desinstalarlas:</span><span class="sxs-lookup"><span data-stu-id="76e87-597">List the installed templates and details about them, including how to uninstall them:</span></span>

  ```dotnetcli
  dotnet new -u
  ```

- <span data-ttu-id="76e87-598">Creación de un archivo *global.json* en el directorio actual al establecer la versión del SDK en 3.1.101:</span><span class="sxs-lookup"><span data-stu-id="76e87-598">Create a *global.json* in the current directory setting the SDK version to 3.1.101:</span></span>

  ```dotnetcli
  dotnet new globaljson --sdk-version 3.1.101
  ```

## <a name="see-also"></a><span data-ttu-id="76e87-599">Vea también</span><span class="sxs-lookup"><span data-stu-id="76e87-599">See also</span></span>

- <span data-ttu-id="76e87-600">[Custom templates for dotnet new](custom-templates.md) (Plantillas personalizadas para dotnet new)</span><span class="sxs-lookup"><span data-stu-id="76e87-600">[Custom templates for dotnet new](custom-templates.md)</span></span>
- [<span data-ttu-id="76e87-601">Creación de una plantilla personalizada para dotnet new</span><span class="sxs-lookup"><span data-stu-id="76e87-601">Create a custom template for dotnet new</span></span>](../tutorials/cli-templates-create-item-template.md)
- [<span data-ttu-id="76e87-602">Repositorio de GitHub dotnet/dotnet-template-samples</span><span class="sxs-lookup"><span data-stu-id="76e87-602">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- <span data-ttu-id="76e87-603">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new) (Plantillas disponibles para dotnet new)</span><span class="sxs-lookup"><span data-stu-id="76e87-603">[Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)</span></span>
