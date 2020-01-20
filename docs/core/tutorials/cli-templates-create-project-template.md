---
title: Creación de una plantilla de proyecto para dotnet new
description: Obtenga información sobre cómo crear una plantilla de proyecto para el comando dotnet new.
author: thraka
ms.date: 06/25/2019
ms.topic: tutorial
ms.author: adegeo
ms.openlocfilehash: 64b029f87135c3424d01a6833619f0aec3833883
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75340364"
---
# <a name="tutorial-create-a-project-template"></a><span data-ttu-id="a97b7-103">Tutorial: Creación de una plantilla de proyecto</span><span class="sxs-lookup"><span data-stu-id="a97b7-103">Tutorial: Create a project template</span></span>

<span data-ttu-id="a97b7-104">Con .NET Core, puede crear e implementar plantillas que generan proyectos, archivos e inclusos recursos.</span><span class="sxs-lookup"><span data-stu-id="a97b7-104">With .NET Core, you can create and deploy templates that generate projects, files, even resources.</span></span> <span data-ttu-id="a97b7-105">Este tutorial es el segundo de una serie que enseña a crear, instalar y desinstalar plantillas para usarlas con el comando `dotnet new`.</span><span class="sxs-lookup"><span data-stu-id="a97b7-105">This tutorial is part two of a series that teaches you how to create, install, and uninstall, templates for use with the `dotnet new` command.</span></span>

<span data-ttu-id="a97b7-106">En esta parte de la serie, aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="a97b7-106">In this part of the series you'll learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="a97b7-107">Crear los recursos de una plantilla de proyecto.</span><span class="sxs-lookup"><span data-stu-id="a97b7-107">Create the resources of a project template</span></span>
> * <span data-ttu-id="a97b7-108">Crear el archivo y la carpeta de configuración de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="a97b7-108">Create the template config folder and file</span></span>
> * <span data-ttu-id="a97b7-109">Instalar una plantilla desde una ruta de acceso de archivo.</span><span class="sxs-lookup"><span data-stu-id="a97b7-109">Install a template from a file path</span></span>
> * <span data-ttu-id="a97b7-110">Probar una plantilla de elemento.</span><span class="sxs-lookup"><span data-stu-id="a97b7-110">Test an item template</span></span>
> * <span data-ttu-id="a97b7-111">Desinstalar una plantilla de elemento.</span><span class="sxs-lookup"><span data-stu-id="a97b7-111">Uninstall an item template</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a97b7-112">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a97b7-112">Prerequisites</span></span>

* <span data-ttu-id="a97b7-113">Complete la [parte 1](cli-templates-create-item-template.md) de esta serie de tutoriales.</span><span class="sxs-lookup"><span data-stu-id="a97b7-113">Complete [part 1](cli-templates-create-item-template.md) of this tutorial series.</span></span>
* <span data-ttu-id="a97b7-114">Abra un terminal y vaya a la carpeta _working\templates_.</span><span class="sxs-lookup"><span data-stu-id="a97b7-114">Open a terminal and navigate to the _working\templates_ folder.</span></span>

## <a name="create-a-project-template"></a><span data-ttu-id="a97b7-115">Creación de una plantilla de proyecto</span><span class="sxs-lookup"><span data-stu-id="a97b7-115">Create a project template</span></span>

<span data-ttu-id="a97b7-116">Las plantillas de proyecto generan proyectos listos para ejecutarse que facilita a los usuarios empezar a trabajar con un espacio de trabajo de código.</span><span class="sxs-lookup"><span data-stu-id="a97b7-116">Project templates produce ready-to-run projects that make it easy for users to start with a working set of code.</span></span> <span data-ttu-id="a97b7-117">.NET Core incluye algunas plantillas de proyecto, como una aplicación de consola o una biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="a97b7-117">.NET Core includes a few project templates such as a console application or a class library.</span></span> <span data-ttu-id="a97b7-118">En este ejemplo, creará un proyecto de consola nuevo que habilita C# 8.0 y genera un punto de entrada `async main`.</span><span class="sxs-lookup"><span data-stu-id="a97b7-118">In this example, you'll create a new console project that enables C# 8.0 and produces an `async main` entry point.</span></span>

<span data-ttu-id="a97b7-119">En el terminal, vaya a la carpeta _working\templates_ y cree una subcarpeta denominada _consoleasync_.</span><span class="sxs-lookup"><span data-stu-id="a97b7-119">In your terminal, navigate to the _working\templates_ folder and create a new subfolder named _consoleasync_.</span></span> <span data-ttu-id="a97b7-120">Entre a la subcarpeta y ejecute `dotnet new console` para generar la aplicación de consola estándar.</span><span class="sxs-lookup"><span data-stu-id="a97b7-120">Enter the subfolder and run `dotnet new console` to generate the standard console application.</span></span> <span data-ttu-id="a97b7-121">Para crear una plantilla nueva, tendrá que editar los archivos que genere esta plantilla.</span><span class="sxs-lookup"><span data-stu-id="a97b7-121">You'll be editing the files produced by this template to create a new template.</span></span>

```console
working
└───templates
    └───consoleasync
            consoleasync.csproj
            Program.cs
```

## <a name="modify-programcs"></a><span data-ttu-id="a97b7-122">Modificación de Program.cs</span><span class="sxs-lookup"><span data-stu-id="a97b7-122">Modify Program.cs</span></span>

<span data-ttu-id="a97b7-123">Abra el archivo _program.cs_.</span><span class="sxs-lookup"><span data-stu-id="a97b7-123">Open up the _program.cs_ file.</span></span> <span data-ttu-id="a97b7-124">El proyecto de la consola no usa un punto de entrada asincrónico, por lo que vamos a agregarlo.</span><span class="sxs-lookup"><span data-stu-id="a97b7-124">The console project doesn't use an asynchronous entry point, so let's add that.</span></span> <span data-ttu-id="a97b7-125">Cambie el código por lo siguiente y guarde el archivo:</span><span class="sxs-lookup"><span data-stu-id="a97b7-125">Change your code to the following and save the file:</span></span>

```csharp
using System;
using System.Threading.Tasks;

namespace consoleasync
{
    class Program
    {
        static async Task Main(string[] args)
        {
            await Console.Out.WriteAsync("Hello World with C# 8.0!");
        }
    }
}
```

## <a name="modify-consoleasynccsproj"></a><span data-ttu-id="a97b7-126">Modificación de consoleasync.csproj</span><span class="sxs-lookup"><span data-stu-id="a97b7-126">Modify consoleasync.csproj</span></span>

<span data-ttu-id="a97b7-127">Actualicemos la versión del lenguaje C# que usa el proyecto a la versión 8.0.</span><span class="sxs-lookup"><span data-stu-id="a97b7-127">Let's update the C# language version the project uses to version 8.0.</span></span> <span data-ttu-id="a97b7-128">Edite el archivo _consoleasync.csproj_ y agregue el valor `<LangVersion>` a un nodo `<PropertyGroup>`.</span><span class="sxs-lookup"><span data-stu-id="a97b7-128">Edit the _consoleasync.csproj_ file and add the `<LangVersion>` setting to a `<PropertyGroup>` node.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.2</TargetFramework>

    <LangVersion>8.0</LangVersion>

  </PropertyGroup>
  
</Project>
```

## <a name="build-the-project"></a><span data-ttu-id="a97b7-129">Compilar el proyecto</span><span class="sxs-lookup"><span data-stu-id="a97b7-129">Build the project</span></span>

<span data-ttu-id="a97b7-130">Antes de completar una plantilla de proyecto, debe probarla para asegurarse de que se compila y ejecuta correctamente.</span><span class="sxs-lookup"><span data-stu-id="a97b7-130">Before you complete a project template, you should test it to make sure it compiles and runs correctly.</span></span> <span data-ttu-id="a97b7-131">En el terminal, ejecute el comando `dotnet run` y debería ver la salida siguiente:</span><span class="sxs-lookup"><span data-stu-id="a97b7-131">In your terminal, run the `dotnet run` command and you should see the following output:</span></span>

```console
C:\working\templates\consoleasync> dotnet run
Hello World with C# 8.0!
```

<span data-ttu-id="a97b7-132">Puede eliminar las carpetas _obj_ y _bin_ creadas si usa `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="a97b7-132">You can delete the _obj_ and _bin_ folders created by using `dotnet run`.</span></span> <span data-ttu-id="a97b7-133">La eliminación de estos archivos garantizar que la plantilla solo incluya los archivos relacionados con la plantilla y no cualquier archivo que resulte de una acción de compilación.</span><span class="sxs-lookup"><span data-stu-id="a97b7-133">Deleting these files ensures your template only includes the files related to your template and not any files that result of a build action.</span></span>

<span data-ttu-id="a97b7-134">Ahora que creó el contenido de la plantilla, debe crear su configuración en la carpeta raíz de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="a97b7-134">Now that you have the content of the template created, you need to create the template config at the root folder of the template.</span></span>

## <a name="create-the-template-config"></a><span data-ttu-id="a97b7-135">Creación de la configuración de una plantilla</span><span class="sxs-lookup"><span data-stu-id="a97b7-135">Create the template config</span></span>

<span data-ttu-id="a97b7-136">En .NET Core, las plantillas se reconocen con una carpeta especial y un archivo de configuración que existen en la raíz de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="a97b7-136">Templates are recognized in .NET Core by a special folder and config file that exist at the root of your template.</span></span> <span data-ttu-id="a97b7-137">En este tutorial, la carpeta de la plantilla se encuentra en _working\templates\consoleasync_.</span><span class="sxs-lookup"><span data-stu-id="a97b7-137">In this tutorial, your template folder is located at _working\templates\consoleasync_.</span></span>

<span data-ttu-id="a97b7-138">Cuando se crea una plantilla, todos los archivos y las carpetas de la carpeta de la plantilla se incluyen como parte de la plantilla, a excepción de la carpeta de configuración especial.</span><span class="sxs-lookup"><span data-stu-id="a97b7-138">When you create a template, all files and folders in the template folder are included as part of the template except for the special config folder.</span></span> <span data-ttu-id="a97b7-139">Esta carpeta de configuración se denomina _.template.config_.</span><span class="sxs-lookup"><span data-stu-id="a97b7-139">This config folder is named _.template.config_.</span></span>

<span data-ttu-id="a97b7-140">En primer lugar, cree una subcarpeta con el nombre _.template.config_ y entre en ella.</span><span class="sxs-lookup"><span data-stu-id="a97b7-140">First, create a new subfolder named _.template.config_, enter it.</span></span> <span data-ttu-id="a97b7-141">Luego, cree un archivo denominado _template.json_.</span><span class="sxs-lookup"><span data-stu-id="a97b7-141">Then, create a new file named _template.json_.</span></span> <span data-ttu-id="a97b7-142">La estructura de la carpeta debe verse así:</span><span class="sxs-lookup"><span data-stu-id="a97b7-142">Your folder structure should look like this:</span></span>

```console
working
└───templates
    └───consoleasync
        └───.template.config
                template.json
```

<span data-ttu-id="a97b7-143">Abra _template.json_ con el editor de texto que prefiera, pegue el código JSON siguiente y guárdelo:</span><span class="sxs-lookup"><span data-stu-id="a97b7-143">Open the _template.json_ with your favorite text editor and paste in the following json code and save it:</span></span>

```json
{
  "$schema": "http://json.schemastore.org/template",
  "author": "Me",
  "classifications": [ "Common", "Console", "C#8" ],
  "identity": "ExampleTemplate.AsyncProject",
  "name": "Example templates: async project",
  "shortName": "consoleasync",
  "tags": {
    "language": "C#",
    "type": "project"
  }
}
```

<span data-ttu-id="a97b7-144">Este archivo de configuración contiene todos los valores de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="a97b7-144">This config file contains all of the settings for your template.</span></span> <span data-ttu-id="a97b7-145">Puede ver los valores básicos, como `name` y `shortName`, pero también hay un valor `tags/type` que está establecido en `project`.</span><span class="sxs-lookup"><span data-stu-id="a97b7-145">You can see the basic settings such as `name` and `shortName` but also there's a `tags/type` value that's set to `project`.</span></span> <span data-ttu-id="a97b7-146">Esto diseña la plantilla como una plantilla de proyecto.</span><span class="sxs-lookup"><span data-stu-id="a97b7-146">This designates your template as a project template.</span></span> <span data-ttu-id="a97b7-147">No hay ninguna restricción en el tipo de plantilla que crea.</span><span class="sxs-lookup"><span data-stu-id="a97b7-147">There's no restriction on the type of template you create.</span></span> <span data-ttu-id="a97b7-148">Los valores `item` y `project` son nombres comunes que .NET Core recomienda para que los usuarios puedan filtrar fácilmente el tipo de plantilla que buscan.</span><span class="sxs-lookup"><span data-stu-id="a97b7-148">The `item` and `project` values are common names that .NET Core recommends so that users can easily filter the type of template they're searching for.</span></span>

<span data-ttu-id="a97b7-149">El elemento `classifications` representa la columna **tags** que ve cuando ejecuta `dotnet new` y obtiene una lista de plantillas.</span><span class="sxs-lookup"><span data-stu-id="a97b7-149">The `classifications` item represents the **tags** column you see when you run `dotnet new` and get a list of templates.</span></span> <span data-ttu-id="a97b7-150">Los usuarios también pueden hacer una búsqueda según las etiquetas de clasificación.</span><span class="sxs-lookup"><span data-stu-id="a97b7-150">Users can also search based on classification tags.</span></span> <span data-ttu-id="a97b7-151">No confunda la propiedad `tags` del archivo .json con la lista de etiquetas `classifications`.</span><span class="sxs-lookup"><span data-stu-id="a97b7-151">Don't confuse the `tags` property in the json file with the `classifications` tags list.</span></span> <span data-ttu-id="a97b7-152">Lamentablemente, son dos elementos que tienen nombres similares.</span><span class="sxs-lookup"><span data-stu-id="a97b7-152">They're two different things unfortunately named similarly.</span></span> <span data-ttu-id="a97b7-153">El esquema completo del archivo *template.json* puede encontrarse en el [Almacenamiento del esquema JSON](http://json.schemastore.org/template).</span><span class="sxs-lookup"><span data-stu-id="a97b7-153">The full schema for the *template.json* file is found at the [JSON Schema Store](http://json.schemastore.org/template).</span></span> <span data-ttu-id="a97b7-154">Para más información sobre el archivo *template.json*, consulte la [wiki de plantillas dotnet](https://github.com/dotnet/templating/wiki).</span><span class="sxs-lookup"><span data-stu-id="a97b7-154">For more information about the *template.json* file, see the [dotnet templating wiki](https://github.com/dotnet/templating/wiki).</span></span>

<span data-ttu-id="a97b7-155">Ahora que tiene un archivo _.template.config/template.json_ válido, la plantilla está lista para instalarla.</span><span class="sxs-lookup"><span data-stu-id="a97b7-155">Now that you have a valid _.template.config/template.json_ file, your template is ready to be installed.</span></span> <span data-ttu-id="a97b7-156">Antes de instalar la plantilla, asegúrese de eliminar cualquier archivo o carpeta de archivos adicional que no quiere que se incluya en la plantilla, como las carpetas _bin_ o _obj_.</span><span class="sxs-lookup"><span data-stu-id="a97b7-156">Before you install the template, make sure that you delete any extra files folders and files you don't want included in your template, like the _bin_ or _obj_ folders.</span></span> <span data-ttu-id="a97b7-157">En el terminal, vaya a la carpeta _consoleasync_ y ejecute `dotnet new -i .\` para instalar la plantilla ubicada en la carpeta actual.</span><span class="sxs-lookup"><span data-stu-id="a97b7-157">In your terminal, navigate to the _consoleasync_ folder and run `dotnet new -i .\` to install the template located at the current folder.</span></span> <span data-ttu-id="a97b7-158">Si usa un sistema operativo Linux o MacOS, use una barra diagonal: `dotnet new -i ./`.</span><span class="sxs-lookup"><span data-stu-id="a97b7-158">If you're using a Linux or MacOS operating system, use a forward slash: `dotnet new -i ./`.</span></span>

<span data-ttu-id="a97b7-159">Este comando genera la lista de las plantillas instaladas, que debería incluir la suya.</span><span class="sxs-lookup"><span data-stu-id="a97b7-159">This command outputs the list of templates installed, which should include yours.</span></span>

```console
C:\working\templates\consoleasync> dotnet new -i .\
Usage: new [options]

Options:
  -h, --help          Displays help for this command.
  -l, --list          Lists templates containing the specified name. If no name is specified, lists all templates.

... cut to save space ...

Templates                                         Short Name            Language          Tags
-------------------------------------------------------------------------------------------------------------------------------
Console Application                               console               [C#], F#, VB      Common/Console
Example templates: async project                  consoleasync          [C#]              Common/Console/C#8
Class library                                     classlib              [C#], F#, VB      Common/Library
WPF Application                                   wpf                   [C#], VB          Common/WPF
Windows Forms (WinForms) Application              winforms              [C#], VB          Common/WinForms
Worker Service                                    worker                [C#]              Common/Worker/Web
```

### <a name="test-the-project-template"></a><span data-ttu-id="a97b7-160">Prueba de la plantilla de proyecto</span><span class="sxs-lookup"><span data-stu-id="a97b7-160">Test the project template</span></span>

<span data-ttu-id="a97b7-161">Ahora que tiene instalada una plantilla de elemento, pruébela.</span><span class="sxs-lookup"><span data-stu-id="a97b7-161">Now that you have an item template installed, test it.</span></span> <span data-ttu-id="a97b7-162">Vaya a la carpeta _test/_ y cree una aplicación de consola con `dotnet new consoleasync`.</span><span class="sxs-lookup"><span data-stu-id="a97b7-162">Navigate to the _test_ folder and create a new console application with `dotnet new consoleasync`.</span></span> <span data-ttu-id="a97b7-163">Esto genera un proyecto de trabajo que puede probar fácilmente con el comando `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="a97b7-163">This generates a working project you can easily test with the `dotnet run` command.</span></span>

```console
C:\test> dotnet new consoleasync
The template "Example templates: async project" was created successfully.
```

```console
C:\test> dotnet run
Hello World with C# 8.0!
```

<span data-ttu-id="a97b7-164">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="a97b7-164">Congratulations!</span></span> <span data-ttu-id="a97b7-165">Ha creado e implementado una plantilla de proyecto con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a97b7-165">You created and deployed a project template with .NET Core.</span></span> <span data-ttu-id="a97b7-166">Como preparación para la próxima parte de esta serie de tutoriales, debe desinstalar la plantilla que creó.</span><span class="sxs-lookup"><span data-stu-id="a97b7-166">In preparation for the next part of this tutorial series, you must uninstall the template you created.</span></span> <span data-ttu-id="a97b7-167">Asegúrese de eliminar también todos los archivos de la carpeta _test_.</span><span class="sxs-lookup"><span data-stu-id="a97b7-167">Make sure to delete all files from the _test_ folder too.</span></span> <span data-ttu-id="a97b7-168">Esto le permitirá volver a un estado limpio listo para la próxima sección importante de este tutorial.</span><span class="sxs-lookup"><span data-stu-id="a97b7-168">This will get you back to a clean state ready for the next major section of this tutorial.</span></span>

### <a name="uninstall-the-template"></a><span data-ttu-id="a97b7-169">Desinstalación de la plantilla</span><span class="sxs-lookup"><span data-stu-id="a97b7-169">Uninstall the template</span></span>

<span data-ttu-id="a97b7-170">Como instaló la plantilla a través de una ruta de acceso de archivo, debe desinstalarla con la ruta de acceso de archivo **absoluta**.</span><span class="sxs-lookup"><span data-stu-id="a97b7-170">Because you installed the template by using a file path, you must uninstall it with the **absolute** file path.</span></span> <span data-ttu-id="a97b7-171">Ejecute el comando `dotnet new -u` para ver una lista de las plantillas instaladas.</span><span class="sxs-lookup"><span data-stu-id="a97b7-171">You can see a list of templates installed by running the `dotnet new -u` command.</span></span> <span data-ttu-id="a97b7-172">Su plantilla debe aparecer en último lugar.</span><span class="sxs-lookup"><span data-stu-id="a97b7-172">Your template should be listed last.</span></span> <span data-ttu-id="a97b7-173">Use la ruta de acceso mostrada para desinstalar la plantilla con el comando `dotnet new -u <ABSOLUTE PATH TO TEMPLATE DIRECTORY>`.</span><span class="sxs-lookup"><span data-stu-id="a97b7-173">Use the path listed to uninstall your template with the `dotnet new -u <ABSOLUTE PATH TO TEMPLATE DIRECTORY>` command.</span></span>

```console
C:\working> dotnet new -u
Template Instantiation Commands for .NET Core CLI

Currently installed items:
  Microsoft.DotNet.Common.ItemTemplates
    Templates:
      dotnet gitignore file (gitignore)
      global.json file (globaljson)
      NuGet Config (nugetconfig)
      Solution File (sln)
      Dotnet local tool manifest file (tool-manifest)
      Web Config (webconfig)

... cut to save space ...

  NUnit3.DotNetNew.Template
    Templates:
      NUnit 3 Test Project (nunit) C#
      NUnit 3 Test Item (nunit-test) C#
      NUnit 3 Test Project (nunit) F#
      NUnit 3 Test Item (nunit-test) F#
      NUnit 3 Test Project (nunit) VB
      NUnit 3 Test Item (nunit-test) VB
  C:\working\templates\consoleasync
    Templates:
      Example templates: async project (consoleasync) C#
```

```console
C:\working> dotnet new -u C:\working\templates\consoleasync
```

## <a name="next-steps"></a><span data-ttu-id="a97b7-174">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="a97b7-174">Next steps</span></span>

<span data-ttu-id="a97b7-175">En este tutorial creó una plantilla de proyecto.</span><span class="sxs-lookup"><span data-stu-id="a97b7-175">In this tutorial, you created a project template.</span></span> <span data-ttu-id="a97b7-176">Para información sobre cómo empaquetar la plantilla de elemento y la de proyecto en un archivo fácil de usar, continúe con esta serie de tutoriales.</span><span class="sxs-lookup"><span data-stu-id="a97b7-176">To learn how to package both the item and project templates into an easy-to-use file, continue this tutorial series.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="a97b7-177">Creación de un paquete de plantillas</span><span class="sxs-lookup"><span data-stu-id="a97b7-177">Create a template pack</span></span>](cli-templates-create-template-pack.md)
