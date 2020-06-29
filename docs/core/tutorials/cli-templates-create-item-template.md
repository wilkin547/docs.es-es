---
title: 'Creación de una plantilla de elemento para dotnet new: CLI de .NET Core'
description: Obtenga información sobre cómo crear una plantilla de elemento para el comando dotnet new. Las plantillas de elemento pueden contener cualquier número de archivos.
author: adegeo
ms.date: 06/25/2019
ms.topic: tutorial
ms.author: adegeo
ms.openlocfilehash: 0b804d26b2f33d4d600c17de2f7f71101a0f9c98
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324375"
---
# <a name="tutorial-create-an-item-template"></a><span data-ttu-id="c90d3-104">Tutorial: Creación de una plantilla de elemento</span><span class="sxs-lookup"><span data-stu-id="c90d3-104">Tutorial: Create an item template</span></span>

<span data-ttu-id="c90d3-105">Con .NET Core, puede crear e implementar plantillas que generan proyectos, archivos e inclusos recursos.</span><span class="sxs-lookup"><span data-stu-id="c90d3-105">With .NET Core, you can create and deploy templates that generate projects, files, even resources.</span></span> <span data-ttu-id="c90d3-106">Este tutorial es el primero de una serie que enseña a crear, instalar y desinstalar plantillas para usarlas con el comando `dotnet new`.</span><span class="sxs-lookup"><span data-stu-id="c90d3-106">This tutorial is part one of a series that teaches you how to create, install, and uninstall, templates for use with the `dotnet new` command.</span></span>

<span data-ttu-id="c90d3-107">En esta parte de la serie, aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="c90d3-107">In this part of the series, you'll learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="c90d3-108">Crear una clase para una plantilla de elemento.</span><span class="sxs-lookup"><span data-stu-id="c90d3-108">Create a class for an item template</span></span>
> * <span data-ttu-id="c90d3-109">Crear el archivo y la carpeta de configuración de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="c90d3-109">Create the template config folder and file</span></span>
> * <span data-ttu-id="c90d3-110">Instalar una plantilla desde una ruta de acceso de archivo.</span><span class="sxs-lookup"><span data-stu-id="c90d3-110">Install a template from a file path</span></span>
> * <span data-ttu-id="c90d3-111">Probar una plantilla de elemento.</span><span class="sxs-lookup"><span data-stu-id="c90d3-111">Test an item template</span></span>
> * <span data-ttu-id="c90d3-112">Desinstalar una plantilla de elemento.</span><span class="sxs-lookup"><span data-stu-id="c90d3-112">Uninstall an item template</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c90d3-113">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="c90d3-113">Prerequisites</span></span>

* <span data-ttu-id="c90d3-114">[SDK de .NET Core 2.2](https://dotnet.microsoft.com/download) o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="c90d3-114">[.NET Core 2.2 SDK](https://dotnet.microsoft.com/download) or later versions.</span></span>
* <span data-ttu-id="c90d3-115">Leer el artículo de referencia [Plantillas personalizadas para dotnet new](../tools/custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="c90d3-115">Read the reference article [Custom templates for dotnet new](../tools/custom-templates.md).</span></span>

  <span data-ttu-id="c90d3-116">En el artículo de referencia se explican los aspectos básicos de las plantillas y cómo se unen.</span><span class="sxs-lookup"><span data-stu-id="c90d3-116">The reference article explains the basics about templates and how they're put together.</span></span> <span data-ttu-id="c90d3-117">Parte de esta información se repetirá en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="c90d3-117">Some of this information will be reiterated here.</span></span>

* <span data-ttu-id="c90d3-118">Abra un terminal y vaya a la carpeta _working\templates_.</span><span class="sxs-lookup"><span data-stu-id="c90d3-118">Open a terminal and navigate to the _working\templates_ folder.</span></span>

## <a name="create-the-required-folders"></a><span data-ttu-id="c90d3-119">Creación de las carpetas necesarias</span><span class="sxs-lookup"><span data-stu-id="c90d3-119">Create the required folders</span></span>

<span data-ttu-id="c90d3-120">Esta serie usa una "carpeta de trabajo", donde se encuentra el origen de la plantilla, y una "carpeta de prueba" que se usa para probar las plantillas.</span><span class="sxs-lookup"><span data-stu-id="c90d3-120">This series uses a "working folder" where your template source is contained and a "testing folder" used to test your templates.</span></span> <span data-ttu-id="c90d3-121">La carpeta de trabajo y la carpeta de prueba deben estar en la misma carpeta.</span><span class="sxs-lookup"><span data-stu-id="c90d3-121">The working folder and testing folder should be under the same parent folder.</span></span>

<span data-ttu-id="c90d3-122">En primer lugar, cree la carpeta principal, no importa con qué nombre.</span><span class="sxs-lookup"><span data-stu-id="c90d3-122">First, create the parent folder, the name does not matter.</span></span> <span data-ttu-id="c90d3-123">Luego, cree una subcarpeta denominada _working_ (trabajo).</span><span class="sxs-lookup"><span data-stu-id="c90d3-123">Then, create a subfolder named _working_.</span></span> <span data-ttu-id="c90d3-124">Dentro de la carpeta _working_, cree una subcarpeta con el nombre _templates_ (plantillas).</span><span class="sxs-lookup"><span data-stu-id="c90d3-124">Inside of the _working_ folder, create a subfolder named _templates_.</span></span>

<span data-ttu-id="c90d3-125">A continuación, cree una carpeta dentro de la carpeta principal con el nombre _test_ (prueba).</span><span class="sxs-lookup"><span data-stu-id="c90d3-125">Next, create a folder under the parent folder named _test_.</span></span> <span data-ttu-id="c90d3-126">La estructura de carpetas debe tener el siguiente aspecto.</span><span class="sxs-lookup"><span data-stu-id="c90d3-126">The folder structure should look like the following.</span></span>

```console
parent_folder
├───test
└───working
    └───templates
```

## <a name="create-an-item-template"></a><span data-ttu-id="c90d3-127">Creación de una plantilla de elemento</span><span class="sxs-lookup"><span data-stu-id="c90d3-127">Create an item template</span></span>

<span data-ttu-id="c90d3-128">Una plantilla de elemento es un tipo de plantilla específico que contiene uno o varios archivos.</span><span class="sxs-lookup"><span data-stu-id="c90d3-128">An item template is a specific type of template that contains one or more files.</span></span> <span data-ttu-id="c90d3-129">Estos tipos de plantillas son útiles cuando se quiere generar algún contenido como un archivo de solución, código o configuración.</span><span class="sxs-lookup"><span data-stu-id="c90d3-129">These types of templates are useful when you want to generate something like a config, code, or solution file.</span></span> <span data-ttu-id="c90d3-130">En este ejemplo, creará una clase que agrega un método de extensión al tipo de cadena.</span><span class="sxs-lookup"><span data-stu-id="c90d3-130">In this example, you'll create a class that adds an extension method to the string type.</span></span>

<span data-ttu-id="c90d3-131">En el terminal, vaya a la carpeta _working\templates_ y cree una subcarpeta llamada _extensions_.</span><span class="sxs-lookup"><span data-stu-id="c90d3-131">In your terminal, navigate to the _working\templates_ folder and create a new subfolder named _extensions_.</span></span> <span data-ttu-id="c90d3-132">Entre a la carpeta.</span><span class="sxs-lookup"><span data-stu-id="c90d3-132">Enter the folder.</span></span>

```console
working
└───templates
    └───extensions
```

<span data-ttu-id="c90d3-133">Cree un archivo nuevo denominado _CommonExtensions.cs_ y ábralo con el editor de texto que prefiera.</span><span class="sxs-lookup"><span data-stu-id="c90d3-133">Create a new file named _CommonExtensions.cs_ and open it with your favorite text editor.</span></span> <span data-ttu-id="c90d3-134">Esta clase proporcionará un método de extensión denominado `Reverse` que invierte el contenido de una cadena.</span><span class="sxs-lookup"><span data-stu-id="c90d3-134">This class will provide an extension method named `Reverse` that reverses the contents of a string.</span></span> <span data-ttu-id="c90d3-135">Pegue el código siguiente y guarde el archivo:</span><span class="sxs-lookup"><span data-stu-id="c90d3-135">Paste in the following code and save the file:</span></span>

```csharp
using System;

namespace System
{
    public static class StringExtensions
    {
        public static string Reverse(this string value)
        {
            var tempArray = value.ToCharArray();
            Array.Reverse(tempArray);
            return new string(tempArray);
        }
    }
}
```

<span data-ttu-id="c90d3-136">Ahora que creó el contenido de la plantilla, debe crear su configuración en la carpeta raíz de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="c90d3-136">Now that you have the content of the template created, you need to create the template config at the root folder of the template.</span></span>

## <a name="create-the-template-config"></a><span data-ttu-id="c90d3-137">Creación de la configuración de una plantilla</span><span class="sxs-lookup"><span data-stu-id="c90d3-137">Create the template config</span></span>

<span data-ttu-id="c90d3-138">En .NET Core, las plantillas se reconocen con una carpeta especial y un archivo de configuración que existen en la raíz de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="c90d3-138">Templates are recognized in .NET Core by a special folder and config file that exist at the root of your template.</span></span> <span data-ttu-id="c90d3-139">En este tutorial, la carpeta de la plantilla se encuentra en _working\templates\extensions_.</span><span class="sxs-lookup"><span data-stu-id="c90d3-139">In this tutorial, your template folder is located at _working\templates\extensions_.</span></span>

<span data-ttu-id="c90d3-140">Cuando se crea una plantilla, todos los archivos y las carpetas de la carpeta de la plantilla se incluyen como parte de la plantilla, a excepción de la carpeta de configuración especial.</span><span class="sxs-lookup"><span data-stu-id="c90d3-140">When you create a template, all files and folders in the template folder are included as part of the template except for the special config folder.</span></span> <span data-ttu-id="c90d3-141">Esta carpeta de configuración se denomina _.template.config_.</span><span class="sxs-lookup"><span data-stu-id="c90d3-141">This config folder is named _.template.config_.</span></span>

<span data-ttu-id="c90d3-142">En primer lugar, cree una subcarpeta con el nombre _.template.config_ y entre en ella.</span><span class="sxs-lookup"><span data-stu-id="c90d3-142">First, create a new subfolder named _.template.config_, enter it.</span></span> <span data-ttu-id="c90d3-143">Luego, cree un archivo denominado _template.json_.</span><span class="sxs-lookup"><span data-stu-id="c90d3-143">Then, create a new file named _template.json_.</span></span> <span data-ttu-id="c90d3-144">La estructura de la carpeta debe verse así:</span><span class="sxs-lookup"><span data-stu-id="c90d3-144">Your folder structure should look like this:</span></span>

```console
working
└───templates
    └───extensions
        └───.template.config
                template.json
```

<span data-ttu-id="c90d3-145">Abra _template.json_ con el editor de texto que prefiera, pegue el código JSON siguiente y guárdelo.</span><span class="sxs-lookup"><span data-stu-id="c90d3-145">Open the _template.json_ with your favorite text editor and paste in the following JSON code and save it.</span></span>

```json
{
  "$schema": "http://json.schemastore.org/template",
  "author": "Me",
  "classifications": [ "Common", "Code" ],
  "identity": "ExampleTemplate.StringExtensions",
  "name": "Example templates: string extensions",
  "shortName": "stringext",
  "tags": {
    "language": "C#",
    "type": "item"
  }
}
```

<span data-ttu-id="c90d3-146">Este archivo de configuración contiene todos los valores de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="c90d3-146">This config file contains all the settings for your template.</span></span> <span data-ttu-id="c90d3-147">Puede ver los valores básicos, como `name` y `shortName`, pero también hay un valor `tags/type` que está establecido en `item`.</span><span class="sxs-lookup"><span data-stu-id="c90d3-147">You can see the basic settings, such as `name` and `shortName`, but there's also a `tags/type` value that is set to `item`.</span></span> <span data-ttu-id="c90d3-148">De este modo, la plantilla se clasifica como una plantilla de elemento.</span><span class="sxs-lookup"><span data-stu-id="c90d3-148">This categorizes your template as an item template.</span></span> <span data-ttu-id="c90d3-149">No hay ninguna restricción en el tipo de plantilla que crea.</span><span class="sxs-lookup"><span data-stu-id="c90d3-149">There's no restriction on the type of template you create.</span></span> <span data-ttu-id="c90d3-150">Los valores `item` y `project` son nombres comunes que .NET Core recomienda para que los usuarios puedan filtrar fácilmente el tipo de plantilla que buscan.</span><span class="sxs-lookup"><span data-stu-id="c90d3-150">The `item` and `project` values are common names that .NET Core recommends so that users can easily filter the type of template they're searching for.</span></span>

<span data-ttu-id="c90d3-151">El elemento `classifications` representa la columna **tags** que ve cuando ejecuta `dotnet new` y obtiene una lista de plantillas.</span><span class="sxs-lookup"><span data-stu-id="c90d3-151">The `classifications` item represents the **tags** column you see when you run `dotnet new` and get a list of templates.</span></span> <span data-ttu-id="c90d3-152">Los usuarios también pueden hacer una búsqueda según las etiquetas de clasificación.</span><span class="sxs-lookup"><span data-stu-id="c90d3-152">Users can also search based on classification tags.</span></span> <span data-ttu-id="c90d3-153">No confunda la propiedad `tags` del archivo \*.json con la lista de etiquetas `classifications`.</span><span class="sxs-lookup"><span data-stu-id="c90d3-153">Don't confuse the `tags` property in the \*.json file with the `classifications` tags list.</span></span> <span data-ttu-id="c90d3-154">Lamentablemente, son dos elementos que tienen nombres similares.</span><span class="sxs-lookup"><span data-stu-id="c90d3-154">They're two different things unfortunately named similarly.</span></span> <span data-ttu-id="c90d3-155">El esquema completo del archivo *template.json* puede encontrarse en el [Almacenamiento del esquema JSON](http://json.schemastore.org/template).</span><span class="sxs-lookup"><span data-stu-id="c90d3-155">The full schema for the *template.json* file is found at the [JSON Schema Store](http://json.schemastore.org/template).</span></span> <span data-ttu-id="c90d3-156">Para más información sobre el archivo *template.json*, consulte la [wiki de plantillas dotnet](https://github.com/dotnet/templating/wiki).</span><span class="sxs-lookup"><span data-stu-id="c90d3-156">For more information about the *template.json* file, see the [dotnet templating wiki](https://github.com/dotnet/templating/wiki).</span></span>

<span data-ttu-id="c90d3-157">Ahora que tiene un archivo _.template.config/template.json_ válido, la plantilla está lista para instalarla.</span><span class="sxs-lookup"><span data-stu-id="c90d3-157">Now that you have a valid _.template.config/template.json_ file, your template is ready to be installed.</span></span> <span data-ttu-id="c90d3-158">En el terminal, vaya a la carpeta _extensions_ y ejecute el comando siguiente para instalar la plantilla ubicada en la carpeta actual:</span><span class="sxs-lookup"><span data-stu-id="c90d3-158">In your terminal, navigate to the  _extensions_ folder and run the following command to install the template located at the current folder:</span></span>

* <span data-ttu-id="c90d3-159">**En Windows**: `dotnet new -i .\`</span><span class="sxs-lookup"><span data-stu-id="c90d3-159">**On Windows**: `dotnet new -i .\`</span></span>
* <span data-ttu-id="c90d3-160">**En Linux o macOS**: `dotnet new -i ./`</span><span class="sxs-lookup"><span data-stu-id="c90d3-160">**On Linux or macOS**: `dotnet new -i ./`</span></span>

<span data-ttu-id="c90d3-161">Este comando genera la lista de las plantillas instaladas, que debería incluir la suya.</span><span class="sxs-lookup"><span data-stu-id="c90d3-161">This command outputs the list of templates installed, which should include yours.</span></span>

```console
C:\working\templates\extensions> dotnet new -i .\
Usage: new [options]

Options:
  -h, --help          Displays help for this command.
  -l, --list          Lists templates containing the specified name. If no name is specified, lists all templates.

... cut to save space ...

Templates                                         Short Name            Language          Tags
-------------------------------------------------------------------------------------------------------------------------------
Example templates: string extensions              stringext             [C#]              Common/Code
Console Application                               console               [C#], F#, VB      Common/Console
Class library                                     classlib              [C#], F#, VB      Common/Library
WPF Application                                   wpf                   [C#], VB          Common/WPF
Windows Forms (WinForms) Application              winforms              [C#], VB          Common/WinForms
Worker Service                                    worker                [C#]              Common/Worker/Web
```

## <a name="test-the-item-template"></a><span data-ttu-id="c90d3-162">Prueba de la plantilla de elemento</span><span class="sxs-lookup"><span data-stu-id="c90d3-162">Test the item template</span></span>

<span data-ttu-id="c90d3-163">Ahora que tiene instalada una plantilla de elemento, pruébela.</span><span class="sxs-lookup"><span data-stu-id="c90d3-163">Now that you have an item template installed, test it.</span></span> <span data-ttu-id="c90d3-164">Vaya a la carpeta _test/_ y cree una aplicación de consola con `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="c90d3-164">Navigate to the _test/_ folder and create a new console application with `dotnet new console`.</span></span> <span data-ttu-id="c90d3-165">Esto genera un proyecto de trabajo que puede probar fácilmente con el comando `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="c90d3-165">This generates a working project you can easily test with the `dotnet run` command.</span></span>

```dotnetcli
dotnet new console
```

<span data-ttu-id="c90d3-166">Verá un resultado similar al siguiente.</span><span class="sxs-lookup"><span data-stu-id="c90d3-166">You get output similar to the following.</span></span>

```console
The template "Console Application" was created successfully.

Processing post-creation actions...
Running 'dotnet restore' on C:\test\test.csproj...
  Restore completed in 54.82 ms for C:\test\test.csproj.

Restore succeeded.
```

<span data-ttu-id="c90d3-167">Ejecute el proyecto.</span><span class="sxs-lookup"><span data-stu-id="c90d3-167">Run the project with.</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="c90d3-168">Obtendrá la siguiente salida.</span><span class="sxs-lookup"><span data-stu-id="c90d3-168">You get the following output.</span></span>

```console
Hello World!
```

<span data-ttu-id="c90d3-169">Luego, ejecute `dotnet new stringext` para generar _CommonExtensions.cs_ desde la plantilla.</span><span class="sxs-lookup"><span data-stu-id="c90d3-169">Next, run `dotnet new stringext` to generate the _CommonExtensions.cs_ from the template.</span></span>

```dotnetcli
dotnet new stringext
```

<span data-ttu-id="c90d3-170">Obtendrá la siguiente salida.</span><span class="sxs-lookup"><span data-stu-id="c90d3-170">You get the following output.</span></span>

```console
The template "Example templates: string extensions" was created successfully.
```

<span data-ttu-id="c90d3-171">Cambie el código en _Program.cs_ para invertir la cadena `"Hello World"` con el método de extensión que se proporciona en la plantilla.</span><span class="sxs-lookup"><span data-stu-id="c90d3-171">Change the code in _Program.cs_ to reverse the `"Hello World"` string with the extension method provided by the template.</span></span>

```csharp
Console.WriteLine("Hello World!".Reverse());
```

<span data-ttu-id="c90d3-172">Vuelva a ejecutar el programa y verá que el resultado se invirtió.</span><span class="sxs-lookup"><span data-stu-id="c90d3-172">Run the program again and you'll see that the result is reversed.</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="c90d3-173">Obtendrá la siguiente salida.</span><span class="sxs-lookup"><span data-stu-id="c90d3-173">You get the following output.</span></span>

```console
!dlroW olleH
```

<span data-ttu-id="c90d3-174">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="c90d3-174">Congratulations!</span></span> <span data-ttu-id="c90d3-175">Ha creado e implementado una plantilla de elemento con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c90d3-175">You created and deployed an item template with .NET Core.</span></span> <span data-ttu-id="c90d3-176">Como preparación para la próxima parte de esta serie de tutoriales, debe desinstalar la plantilla que creó.</span><span class="sxs-lookup"><span data-stu-id="c90d3-176">In preparation for the next part of this tutorial series, you must uninstall the template you created.</span></span> <span data-ttu-id="c90d3-177">Asegúrese de eliminar también todos los archivos de la carpeta _test_.</span><span class="sxs-lookup"><span data-stu-id="c90d3-177">Make sure to delete all files from the _test_ folder too.</span></span> <span data-ttu-id="c90d3-178">Esto le permitirá volver a un estado limpio listo para la próxima sección importante de este tutorial.</span><span class="sxs-lookup"><span data-stu-id="c90d3-178">This will get you back to a clean state ready for the next major section of this tutorial.</span></span>

## <a name="uninstall-the-template"></a><span data-ttu-id="c90d3-179">Desinstalación de la plantilla</span><span class="sxs-lookup"><span data-stu-id="c90d3-179">Uninstall the template</span></span>

<span data-ttu-id="c90d3-180">Como instaló la plantilla a través de la ruta de acceso de archivo, debe desinstalarla con la ruta de acceso de archivo **absoluta**.</span><span class="sxs-lookup"><span data-stu-id="c90d3-180">Because you installed the template by file path, you must uninstall it with the **absolute** file path.</span></span> <span data-ttu-id="c90d3-181">Ejecute el comando `dotnet new -u` para ver una lista de las plantillas instaladas.</span><span class="sxs-lookup"><span data-stu-id="c90d3-181">You can see a list of templates installed by running the `dotnet new -u` command.</span></span> <span data-ttu-id="c90d3-182">Su plantilla debe aparecer en último lugar.</span><span class="sxs-lookup"><span data-stu-id="c90d3-182">Your template should be listed last.</span></span> <span data-ttu-id="c90d3-183">Use la ruta de acceso mostrada para desinstalar la plantilla con el comando `dotnet new -u <ABSOLUTE PATH TO TEMPLATE DIRECTORY>`.</span><span class="sxs-lookup"><span data-stu-id="c90d3-183">Use the path listed to uninstall your template with the `dotnet new -u <ABSOLUTE PATH TO TEMPLATE DIRECTORY>` command.</span></span>

```dotnetcli
dotnet new -u
```

<span data-ttu-id="c90d3-184">Verá un resultado similar al siguiente.</span><span class="sxs-lookup"><span data-stu-id="c90d3-184">You get output similar to the following.</span></span>

```console
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
  C:\working\templates\extensions
    Templates:
      Example templates: string extensions (stringext) C#
```

<span data-ttu-id="c90d3-185">Para desinstalar una plantilla, ejecute el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="c90d3-185">To uninstall a template, run the following command.</span></span>

```dotnetcli
dotnet new -u C:\working\templates\extensions
```

## <a name="next-steps"></a><span data-ttu-id="c90d3-186">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="c90d3-186">Next steps</span></span>

<span data-ttu-id="c90d3-187">En este tutorial, creó una plantilla de elemento.</span><span class="sxs-lookup"><span data-stu-id="c90d3-187">In this tutorial, you created an item template.</span></span> <span data-ttu-id="c90d3-188">Para aprender a crear una plantilla de proyecto, siga con esta serie de tutoriales.</span><span class="sxs-lookup"><span data-stu-id="c90d3-188">To learn how to create a project template, continue this tutorial series.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="c90d3-189">Creación de una plantilla de proyecto</span><span class="sxs-lookup"><span data-stu-id="c90d3-189">Create a project template</span></span>](cli-templates-create-project-template.md)
