---
title: Plantillas personalizadas para dotnet new
description: Obtenga información sobre las plantillas personalizadas para cualquier tipo de proyecto o archivo de .NET.
author: adegeo
ms.date: 05/20/2020
ms.openlocfilehash: 1d2e5ffcb0b279f1686855834c2357827a4dc7d5
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90538100"
---
# <a name="custom-templates-for-dotnet-new"></a><span data-ttu-id="6f358-103">Plantillas personalizadas para dotnet new</span><span class="sxs-lookup"><span data-stu-id="6f358-103">Custom templates for dotnet new</span></span>

<span data-ttu-id="6f358-104">El [SDK de .NET Core](https://dotnet.microsoft.com/download) cuenta con muchas plantillas ya instaladas y listas para su uso.</span><span class="sxs-lookup"><span data-stu-id="6f358-104">The [.NET Core SDK](https://dotnet.microsoft.com/download) comes with many templates already installed and ready for you to use.</span></span> <span data-ttu-id="6f358-105">El [comando `dotnet new`](dotnet-new.md) no es solo la forma de usar una plantilla, sino también cómo instalarlas y desinstalarlas.</span><span class="sxs-lookup"><span data-stu-id="6f358-105">The [`dotnet new` command](dotnet-new.md) isn't only the way to use a template, but also how to install and uninstall templates.</span></span> <span data-ttu-id="6f358-106">A partir de .NET Core 2.0, puede crear sus propias plantillas personalizadas para cualquier tipo de proyecto, como una aplicación, un servicio, una herramienta o una biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="6f358-106">Starting with .NET Core 2.0, you can create your own custom templates for any type of project, such as an app, service, tool, or class library.</span></span> <span data-ttu-id="6f358-107">Incluso puede crear una plantilla que genere uno o más archivos independientes, como un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="6f358-107">You can even create a template that outputs one or more independent files, such as a configuration file.</span></span>

<span data-ttu-id="6f358-108">Puede instalar plantillas personalizadas desde un paquete NuGet en cualquier fuente NuGet, haciendo referencia a un archivo *.nupkg* de NuGet directamente o especificando un directorio del sistema de archivos que contenga la plantilla.</span><span class="sxs-lookup"><span data-stu-id="6f358-108">You can install custom templates from a NuGet package on any NuGet feed, by referencing a NuGet *.nupkg* file directly, or by specifying a file system directory that contains the template.</span></span> <span data-ttu-id="6f358-109">El motor de plantillas ofrece características que le permiten reemplazar valores, incluir y excluir archivos y ejecutar operaciones de procesamiento personalizadas cuando se usa la plantilla.</span><span class="sxs-lookup"><span data-stu-id="6f358-109">The template engine offers features that allow you to replace values, include and exclude files, and execute custom processing operations when your template is used.</span></span>

<span data-ttu-id="6f358-110">El motor de plantillas es de código abierto, y el repositorio de código en línea está en [dotnet/templating](https://github.com/dotnet/templating/) en GitHub.</span><span class="sxs-lookup"><span data-stu-id="6f358-110">The template engine is open source, and the online code repository is at [dotnet/templating](https://github.com/dotnet/templating/) on GitHub.</span></span> <span data-ttu-id="6f358-111">Puede encontrar más plantillas, incluidas las plantillas de terceros, en [Plantillas disponibles para dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new) en GitHub.</span><span class="sxs-lookup"><span data-stu-id="6f358-111">More templates, including templates from third parties, are found at [Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new) on GitHub.</span></span> <span data-ttu-id="6f358-112">Para obtener información sobre cómo crear y usar plantillas personalizadas, vea [Cómo crear sus propias plantillas para dotnet new](https://devblogs.microsoft.com/dotnet/how-to-create-your-own-templates-for-dotnet-new/) y la [Wiki del repositorio de GitHub dotnet/templating](https://github.com/dotnet/templating/wiki).</span><span class="sxs-lookup"><span data-stu-id="6f358-112">For more information about creating and using custom templates, see [How to create your own templates for dotnet new](https://devblogs.microsoft.com/dotnet/how-to-create-your-own-templates-for-dotnet-new/) and the [dotnet/templating GitHub repo Wiki](https://github.com/dotnet/templating/wiki).</span></span>

> [!NOTE]
> <span data-ttu-id="6f358-113">Los ejemplos de plantillas están disponibles en el repositorio de GitHub [dotnet/dotnet-template-samples](https://github.com/dotnet/dotnet-template-samples).</span><span class="sxs-lookup"><span data-stu-id="6f358-113">Template examples are available at the [dotnet/dotnet-template-samples](https://github.com/dotnet/dotnet-template-samples) GitHub repository.</span></span> <span data-ttu-id="6f358-114">Sin embargo, aunque estos ejemplos son un buen recurso para aprender cómo funcionan las plantillas, el repositorio está archivado y no recibe mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="6f358-114">However, while these examples are good resource for learning how the templates work, the repository is archived and no longer maintained.</span></span> <span data-ttu-id="6f358-115">Los ejemplos pueden no estar actualizados y ya no funcionan.</span><span class="sxs-lookup"><span data-stu-id="6f358-115">The examples may be out of date and no longer working.</span></span>

<span data-ttu-id="6f358-116">Para seguir un tutorial y crear una plantilla, vea el tutorial [Creación de una plantilla personalizada para dotnet new](../tutorials/cli-templates-create-item-template.md).</span><span class="sxs-lookup"><span data-stu-id="6f358-116">To follow a walkthrough and create a template, see the [Create a custom template for dotnet new](../tutorials/cli-templates-create-item-template.md) tutorial.</span></span>

### <a name="net-default-templates"></a><span data-ttu-id="6f358-117">Plantillas predeterminadas .NET</span><span class="sxs-lookup"><span data-stu-id="6f358-117">.NET default templates</span></span>

<span data-ttu-id="6f358-118">Cuando instala el [SDK de .NET Core](https://dotnet.microsoft.com/download), recibe más de una docena de plantillas integradas para crear proyectos y archivos, incluidas las aplicaciones de consola, bibliotecas de clases, proyectos de prueba unitaria, aplicaciones de ASP.NET Core (incluidos los proyectos [Angular](https://angular.io/) y [React](https://facebook.github.io/react/)), y archivos de configuración.</span><span class="sxs-lookup"><span data-stu-id="6f358-118">When you install the [.NET Core SDK](https://dotnet.microsoft.com/download), you receive over a dozen built-in templates for creating projects and files, including console apps, class libraries, unit test projects, ASP.NET Core apps (including [Angular](https://angular.io/) and [React](https://facebook.github.io/react/) projects), and configuration files.</span></span> <span data-ttu-id="6f358-119">Para enumerar las plantillas integradas, ejecute el comando `dotnet new` con la opción `-l|--list`:</span><span class="sxs-lookup"><span data-stu-id="6f358-119">To list the built-in templates, run the `dotnet new` command with the `-l|--list` option:</span></span>

```dotnetcli
dotnet new --list
```

## <a name="configuration"></a><span data-ttu-id="6f358-120">Configuración</span><span class="sxs-lookup"><span data-stu-id="6f358-120">Configuration</span></span>

<span data-ttu-id="6f358-121">Una plantilla consta de las siguientes partes:</span><span class="sxs-lookup"><span data-stu-id="6f358-121">A template is composed of the following parts:</span></span>

- <span data-ttu-id="6f358-122">Archivos de origen y carpetas.</span><span class="sxs-lookup"><span data-stu-id="6f358-122">Source files and folders.</span></span>
- <span data-ttu-id="6f358-123">Un archivo de configuración (*template.json*).</span><span class="sxs-lookup"><span data-stu-id="6f358-123">A configuration file (*template.json*).</span></span>

### <a name="source-files-and-folders"></a><span data-ttu-id="6f358-124">Archivos de origen y carpetas</span><span class="sxs-lookup"><span data-stu-id="6f358-124">Source files and folders</span></span>

<span data-ttu-id="6f358-125">Los archivos de origen y las carpetas incluyen todos los archivos y carpetas que quiera que el motor de plantilla use cuando se ejecuta el comando `dotnet new <TEMPLATE>`.</span><span class="sxs-lookup"><span data-stu-id="6f358-125">The source files and folders include whatever files and folders you want the template engine to use when the `dotnet new <TEMPLATE>` command is run.</span></span> <span data-ttu-id="6f358-126">El motor de plantillas está diseñado para usar *proyectos ejecutables* como código fuente para generar proyectos.</span><span class="sxs-lookup"><span data-stu-id="6f358-126">The template engine is designed to use *runnable projects* as source code to produce projects.</span></span> <span data-ttu-id="6f358-127">Esto presenta varias ventajas:</span><span class="sxs-lookup"><span data-stu-id="6f358-127">This has several benefits:</span></span>

- <span data-ttu-id="6f358-128">El motor de plantillas no necesita que inserte tokens especiales en su código de origen del proyecto.</span><span class="sxs-lookup"><span data-stu-id="6f358-128">The template engine doesn't require you to inject special tokens into your project's source code.</span></span>
- <span data-ttu-id="6f358-129">Los archivos de código no son archivos especiales ni se modifican de ninguna manera para que funcionen con el motor de plantillas.</span><span class="sxs-lookup"><span data-stu-id="6f358-129">The code files aren't special files or modified in any way to work with the template engine.</span></span> <span data-ttu-id="6f358-130">Por lo tanto, las herramientas que usa normalmente para trabajar con los proyectos también funcionan con el contenido de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="6f358-130">So, the tools you normally use when working with projects also work with template content.</span></span>
- <span data-ttu-id="6f358-131">Compile, ejecute y depure sus proyectos de plantilla de la forma en que lo hace para cualquiera de sus otros proyectos.</span><span class="sxs-lookup"><span data-stu-id="6f358-131">You build, run, and debug your template projects just like you do for any of your other projects.</span></span>
- <span data-ttu-id="6f358-132">Puede crear rápidamente una plantilla de un proyecto existente simplemente agregando un archivo de configuración *./.template.config/template.json* al proyecto.</span><span class="sxs-lookup"><span data-stu-id="6f358-132">You can quickly create a template from an existing project just by adding a *./.template.config/template.json* configuration file to the project.</span></span>

<span data-ttu-id="6f358-133">Los archivos y las carpetas que se almacenan en la plantilla no se limitan a tipos de proyectos .NET formales.</span><span class="sxs-lookup"><span data-stu-id="6f358-133">Files and folders stored in the template aren't limited to formal .NET project types.</span></span> <span data-ttu-id="6f358-134">Los archivos de origen y las carpetas pueden constar de cualquier contenido que quiera crear cuando se use la plantilla, incluso si el motor de plantillas genera solo un archivo como su salida.</span><span class="sxs-lookup"><span data-stu-id="6f358-134">Source files and folders may consist of any content that you wish to create when the template is used, even if the template engine produces just one file as its output.</span></span>

<span data-ttu-id="6f358-135">Los archivos que genera la plantilla se pueden modificar según la lógica y la configuración que ha proporcionado en el archivo de configuración *template.json*.</span><span class="sxs-lookup"><span data-stu-id="6f358-135">Files generated by the template can be modified based on logic and settings you've provided in the *template.json* configuration file.</span></span> <span data-ttu-id="6f358-136">El usuario puede invalidar esta configuración pasando las opciones al comando `dotnet new <TEMPLATE>`.</span><span class="sxs-lookup"><span data-stu-id="6f358-136">The user can override these settings by passing options to the `dotnet new <TEMPLATE>` command.</span></span> <span data-ttu-id="6f358-137">Un ejemplo común de una lógica personalizada es proporcionar un nombre para una clase o variable en el archivo de código que se implementa mediante una plantilla.</span><span class="sxs-lookup"><span data-stu-id="6f358-137">A common example of custom logic is providing a name for a class or variable in the code file that's deployed by a template.</span></span>

### <a name="templatejson"></a><span data-ttu-id="6f358-138">template.json</span><span class="sxs-lookup"><span data-stu-id="6f358-138">template.json</span></span>

<span data-ttu-id="6f358-139">El archivo *template.json* se coloca en una carpeta *.template.config* en el directorio raíz de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="6f358-139">The *template.json* file is placed in a *.template.config* folder in the root directory of the template.</span></span> <span data-ttu-id="6f358-140">El archivo proporciona información de configuración al motor de plantillas.</span><span class="sxs-lookup"><span data-stu-id="6f358-140">The file provides configuration information to the template engine.</span></span> <span data-ttu-id="6f358-141">La configuración mínima necesita los miembros que se muestran en la tabla siguiente, que es suficiente para crear una plantilla funcional.</span><span class="sxs-lookup"><span data-stu-id="6f358-141">The minimum configuration requires the members shown in the following table, which is sufficient to create a functional template.</span></span>

| <span data-ttu-id="6f358-142">Miembro</span><span class="sxs-lookup"><span data-stu-id="6f358-142">Member</span></span>            | <span data-ttu-id="6f358-143">Tipo</span><span class="sxs-lookup"><span data-stu-id="6f358-143">Type</span></span>          | <span data-ttu-id="6f358-144">Descripción</span><span class="sxs-lookup"><span data-stu-id="6f358-144">Description</span></span> |
| ----------------- | ------------- | ----------- |
| `$schema`         | <span data-ttu-id="6f358-145">Identificador URI</span><span class="sxs-lookup"><span data-stu-id="6f358-145">URI</span></span>           | <span data-ttu-id="6f358-146">El esquema JSON para el archivo *template.json*.</span><span class="sxs-lookup"><span data-stu-id="6f358-146">The JSON schema for the *template.json* file.</span></span> <span data-ttu-id="6f358-147">Los editores que admiten los esquemas JSON habilitan las características de edición JSON cuando se especifica el esquema.</span><span class="sxs-lookup"><span data-stu-id="6f358-147">Editors that support JSON schemas enable JSON-editing features when the schema is specified.</span></span> <span data-ttu-id="6f358-148">Por ejemplo, [Visual Studio Code](https://code.visualstudio.com/) necesita este miembro para habilitar IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="6f358-148">For example, [Visual Studio Code](https://code.visualstudio.com/) requires this member to enable IntelliSense.</span></span> <span data-ttu-id="6f358-149">Use un valor de `http://json.schemastore.org/template`.</span><span class="sxs-lookup"><span data-stu-id="6f358-149">Use a value of `http://json.schemastore.org/template`.</span></span> |
| `author`          | <span data-ttu-id="6f358-150">cadena</span><span class="sxs-lookup"><span data-stu-id="6f358-150">string</span></span>        | <span data-ttu-id="6f358-151">El autor de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="6f358-151">The author of the template.</span></span> |
| `classifications` | <span data-ttu-id="6f358-152">array(string)</span><span class="sxs-lookup"><span data-stu-id="6f358-152">array(string)</span></span> | <span data-ttu-id="6f358-153">Cero o más características de la plantilla que un usuario puede usar para buscar la plantilla al buscarla.</span><span class="sxs-lookup"><span data-stu-id="6f358-153">Zero or more characteristics of the template that a user might use to find the template when searching for it.</span></span> <span data-ttu-id="6f358-154">Las clasificaciones también aparecen en la columna *Etiquetas* cuando aparece en una lista de plantillas que se han generado mediante el comando `dotnet new -l|--list`.</span><span class="sxs-lookup"><span data-stu-id="6f358-154">The classifications also appear in the *Tags* column when it appears in a list of templates produced by using the `dotnet new -l|--list` command.</span></span> |
| `identity`        | <span data-ttu-id="6f358-155">cadena</span><span class="sxs-lookup"><span data-stu-id="6f358-155">string</span></span>        | <span data-ttu-id="6f358-156">Un nombre único para esta plantilla.</span><span class="sxs-lookup"><span data-stu-id="6f358-156">A unique name for this template.</span></span> |
| `name`            | <span data-ttu-id="6f358-157">cadena</span><span class="sxs-lookup"><span data-stu-id="6f358-157">string</span></span>        | <span data-ttu-id="6f358-158">El nombre de la plantilla que los usuarios deben ver.</span><span class="sxs-lookup"><span data-stu-id="6f358-158">The name for the template that users should see.</span></span> |
| `shortName`       | <span data-ttu-id="6f358-159">cadena</span><span class="sxs-lookup"><span data-stu-id="6f358-159">string</span></span>        | <span data-ttu-id="6f358-160">Un nombre abreviado predeterminado para seleccionar la plantilla que se aplica a entornos donde el usuario especifica el nombre de la plantilla; no se selecciona mediante una GUI.</span><span class="sxs-lookup"><span data-stu-id="6f358-160">A default shorthand name for selecting the template that applies to environments where the template name is specified by the user, not selected via a GUI.</span></span> <span data-ttu-id="6f358-161">Por ejemplo, un nombre abreviado es útil al usar plantillas desde un símbolo del sistema con comandos de la CLI.</span><span class="sxs-lookup"><span data-stu-id="6f358-161">For example, the short name is useful when using templates from a command prompt with CLI commands.</span></span> |

<span data-ttu-id="6f358-162">El esquema completo del archivo *template.json* puede encontrarse en el [Almacenamiento del esquema JSON](http://json.schemastore.org/template).</span><span class="sxs-lookup"><span data-stu-id="6f358-162">The full schema for the *template.json* file is found at the [JSON Schema Store](http://json.schemastore.org/template).</span></span> <span data-ttu-id="6f358-163">Para más información sobre el archivo *template.json*, consulte la [wiki de plantillas dotnet](https://github.com/dotnet/templating/wiki).</span><span class="sxs-lookup"><span data-stu-id="6f358-163">For more information about the *template.json* file, see the [dotnet templating wiki](https://github.com/dotnet/templating/wiki).</span></span>

#### <a name="example"></a><span data-ttu-id="6f358-164">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6f358-164">Example</span></span>

<span data-ttu-id="6f358-165">Por ejemplo, esta es una carpeta de plantillas que tiene dos archivos de contenido: *console.cs* y *readme.txt*.</span><span class="sxs-lookup"><span data-stu-id="6f358-165">For example, here is a template folder that contains two content files: *console.cs* and *readme.txt*.</span></span> <span data-ttu-id="6f358-166">Tenga en cuenta que existe la carpeta requerida denominada *.template.config* que contiene el archivo *template.json*.</span><span class="sxs-lookup"><span data-stu-id="6f358-166">Take notice that there is the required folder named *.template.config* that contains the *template.json* file.</span></span>

```text
└───mytemplate
    │   console.cs
    │   readme.txt
    │
    └───.template.config
            template.json
```

<span data-ttu-id="6f358-167">El archivo *template.json* tiene un aspecto parecido al siguiente:</span><span class="sxs-lookup"><span data-stu-id="6f358-167">The *template.json* file looks like the following:</span></span>

```json
{
  "$schema": "http://json.schemastore.org/template",
  "author": "Travis Chau",
  "classifications": [ "Common", "Console" ],
  "identity": "AdatumCorporation.ConsoleTemplate.CSharp",
  "name": "Adatum Corporation Console Application",
  "shortName": "adatumconsole"
}
```

<span data-ttu-id="6f358-168">La carpeta *mytemplate* es un paquete de plantilla instalable.</span><span class="sxs-lookup"><span data-stu-id="6f358-168">The *mytemplate* folder is an installable template pack.</span></span> <span data-ttu-id="6f358-169">Una vez instalado el paquete, `shortName` se puede utilizar con el comando `dotnet new`.</span><span class="sxs-lookup"><span data-stu-id="6f358-169">Once the pack is installed, the `shortName` can be used with the `dotnet new` command.</span></span> <span data-ttu-id="6f358-170">Por ejemplo, `dotnet new adatumconsole` generaría los archivos `console.cs` y `readme.txt` en la carpeta actual.</span><span class="sxs-lookup"><span data-stu-id="6f358-170">For example, `dotnet new adatumconsole` would output the `console.cs` and `readme.txt` files to the current folder.</span></span>

## <a name="packing-a-template-into-a-nuget-package-nupkg-file"></a><span data-ttu-id="6f358-171">Empaquetar una plantilla en un paquete NuGet (archivo nupkg)</span><span class="sxs-lookup"><span data-stu-id="6f358-171">Packing a template into a NuGet package (nupkg file)</span></span>

<span data-ttu-id="6f358-172">Una plantilla personalizada se empaqueta con el comando la [dotnet pack](dotnet-pack.md) y un archivo *.csproj*.</span><span class="sxs-lookup"><span data-stu-id="6f358-172">A custom template is packed with the [dotnet pack](dotnet-pack.md) command and a *.csproj* file.</span></span> <span data-ttu-id="6f358-173">Como alternativa, se puede usar [NuGet](/nuget/tools/nuget-exe-cli-reference) con el comando [nuget pack](/nuget/tools/cli-ref-pack) junto con un archivo *.nuspec*.</span><span class="sxs-lookup"><span data-stu-id="6f358-173">Alternatively, [NuGet](/nuget/tools/nuget-exe-cli-reference) can be used with the [nuget pack](/nuget/tools/cli-ref-pack) command along with a *.nuspec* file.</span></span> <span data-ttu-id="6f358-174">Pero NuGet necesita .NET Framework en Windows y [Mono](https://www.mono-project.com/) en Linux y macOS.</span><span class="sxs-lookup"><span data-stu-id="6f358-174">However, NuGet requires the .NET Framework on Windows and [Mono](https://www.mono-project.com/) on Linux and macOS.</span></span>

<span data-ttu-id="6f358-175">El archivo *.csproj* es ligeramente diferente al archivo *.csproj* de un proyecto de código tradicional.</span><span class="sxs-lookup"><span data-stu-id="6f358-175">The *.csproj* file is slightly different from a traditional code-project *.csproj* file.</span></span> <span data-ttu-id="6f358-176">Tenga en cuenta la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="6f358-176">Note the following settings:</span></span>

01. <span data-ttu-id="6f358-177">El valor `<PackageType>` se agrega y se establece en `Template`.</span><span class="sxs-lookup"><span data-stu-id="6f358-177">The `<PackageType>` setting is added and set to `Template`.</span></span>
01. <span data-ttu-id="6f358-178">El valor `<PackageVersion>` se agrega y establece en un [número de versión de NuGet](/nuget/reference/package-versioning).</span><span class="sxs-lookup"><span data-stu-id="6f358-178">The `<PackageVersion>` setting is added and set to a valid [NuGet version number](/nuget/reference/package-versioning).</span></span>
01. <span data-ttu-id="6f358-179">El valor `<PackageId>` se agrega y se establece en un identificador único.</span><span class="sxs-lookup"><span data-stu-id="6f358-179">The `<PackageId>` setting is added and set to a unique identifier.</span></span> <span data-ttu-id="6f358-180">Este identificador se usa para desinstalar el paquete de plantillas y lo usan las fuentes NuGet para registrar su paquete de plantillas.</span><span class="sxs-lookup"><span data-stu-id="6f358-180">This identifier is used to uninstall the template pack and is used by NuGet feeds to register your template pack.</span></span>
01. <span data-ttu-id="6f358-181">Se debe establecer la configuración de metadatos genérica: `<Title>`, `<Authors>`, `<Description>` y `<PackageTags>`.</span><span class="sxs-lookup"><span data-stu-id="6f358-181">Generic metadata settings should be set: `<Title>`, `<Authors>`, `<Description>`, and `<PackageTags>`.</span></span>
01. <span data-ttu-id="6f358-182">Debe establecerse la configuración `<TargetFramework>`, aunque no se usen los datos binarios generados por el proceso de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="6f358-182">The `<TargetFramework>` setting must be set, even though the binary produced by the template process isn't used.</span></span> <span data-ttu-id="6f358-183">En el ejemplo siguiente se establece en `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="6f358-183">In the example below it's set to `netstandard2.0`.</span></span>

<span data-ttu-id="6f358-184">Un paquete de plantillas, en forma de un paquete NuGet *.nupkg*, requiere que todas las plantillas se almacenan en la carpeta *content* dentro del paquete.</span><span class="sxs-lookup"><span data-stu-id="6f358-184">A template pack, in the form of a *.nupkg* NuGet package, requires that all templates be stored in the *content* folder within the package.</span></span> <span data-ttu-id="6f358-185">Hay algunas opciones de configuración más para agregar a un archivo *.csproj* para asegurarse de que el paquete *.nupkg* generado se puede instalar como un paquete de plantilla:</span><span class="sxs-lookup"><span data-stu-id="6f358-185">There are a few more settings to add to a *.csproj* file to ensure that the generated *.nupkg* can be installed as a template pack:</span></span>

01. <span data-ttu-id="6f358-186">El valor `<IncludeContentInPack>` se establece en `true` para incluir cualquier archivo que el proyecto establece como **content** en el paquete NuGet.</span><span class="sxs-lookup"><span data-stu-id="6f358-186">The `<IncludeContentInPack>` setting is set to `true` to include any file the project sets as **content** in the NuGet package.</span></span>
01. <span data-ttu-id="6f358-187">El valor `<IncludeBuildOutput>` se establece en `false` para excluir todos los archivos binarios generados por el compilador desde el paquete NuGet.</span><span class="sxs-lookup"><span data-stu-id="6f358-187">The `<IncludeBuildOutput>` setting is set to `false` to exclude all binaries generated by the compiler from the NuGet package.</span></span>
01. <span data-ttu-id="6f358-188">El valor `<ContentTargetFolders>` se establece en `content`.</span><span class="sxs-lookup"><span data-stu-id="6f358-188">The `<ContentTargetFolders>` setting is set to `content`.</span></span> <span data-ttu-id="6f358-189">Esto garantiza que los archivos establecidos como **content** se almacenan en la carpeta *content* carpeta en el paquete NuGet.</span><span class="sxs-lookup"><span data-stu-id="6f358-189">This makes sure that the files set as **content** are stored in the *content* folder in the NuGet package.</span></span> <span data-ttu-id="6f358-190">Esta carpeta del paquete NuGet la analiza el sistema de plantillas dotnet.</span><span class="sxs-lookup"><span data-stu-id="6f358-190">This folder in the NuGet package is parsed by the dotnet template system.</span></span>

<span data-ttu-id="6f358-191">Una manera sencilla de excluir todos los archivos de código para que el proyecto de su plantilla no los compile es usando el elemento `<Compile Remove="**\*" />` del archivo de proyecto, dentro de un elemento `<ItemGroup>`.</span><span class="sxs-lookup"><span data-stu-id="6f358-191">An easy way to exclude all code files from being compiled by your template project is by using the `<Compile Remove="**\*" />` item in your project file, inside an `<ItemGroup>` element.</span></span>

<span data-ttu-id="6f358-192">Una manera sencilla de estructurar su paquete de plantillas es colocar todas las plantillas en carpetas individuales y luego cada carpeta de plantillas dentro de una carpeta *templates* que se encuentra en el mismo directorio que el archivo *.csproj* .</span><span class="sxs-lookup"><span data-stu-id="6f358-192">An easy way to structure your template pack is to put all templates in individual folders, and then each template folder inside of a *templates* folder that is located in the same directory as your *.csproj* file.</span></span> <span data-ttu-id="6f358-193">De esta manera, puede usar un solo elemento del proyecto para incluir todos los archivos y carpetas en *templates* como **content**.</span><span class="sxs-lookup"><span data-stu-id="6f358-193">This way, you can use a single project item to include all files and folders in the *templates* as **content**.</span></span> <span data-ttu-id="6f358-194">Dentro de un elemento `<ItemGroup>`, cree un elemento `<Content Include="templates\**\*" Exclude="templates\**\bin\**;templates\**\obj\**" />`.</span><span class="sxs-lookup"><span data-stu-id="6f358-194">Inside of an `<ItemGroup>` element, create a `<Content Include="templates\**\*" Exclude="templates\**\bin\**;templates\**\obj\**" />` item.</span></span>

<span data-ttu-id="6f358-195">Este es un archivo *.csproj* de ejemplo que sigue todas las pautas anteriores.</span><span class="sxs-lookup"><span data-stu-id="6f358-195">Here is an example *.csproj* file that follows all of the guidelines above.</span></span> <span data-ttu-id="6f358-196">Empaqueta la carpeta secundaria *templates* en la carpeta del paquete *content* y excluye cualquier archivo de código de la compilación.</span><span class="sxs-lookup"><span data-stu-id="6f358-196">It packs the *templates* child folder to the *content* package folder and excludes any code file from being compiled.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <PackageType>Template</PackageType>
    <PackageVersion>1.0</PackageVersion>
    <PackageId>AdatumCorporation.Utility.Templates</PackageId>
    <Title>AdatumCorporation Templates</Title>
    <Authors>Me</Authors>
    <Description>Templates to use when creating an application for Adatum Corporation.</Description>
    <PackageTags>dotnet-new;templates;contoso</PackageTags>
    <TargetFramework>netstandard2.0</TargetFramework>

    <IncludeContentInPack>true</IncludeContentInPack>
    <IncludeBuildOutput>false</IncludeBuildOutput>
    <ContentTargetFolders>content</ContentTargetFolders>
  </PropertyGroup>

  <ItemGroup>
    <Content Include="templates\**\*" Exclude="templates\**\bin\**;templates\**\obj\**" />
    <Compile Remove="**\*" />
  </ItemGroup>

</Project>
```

<span data-ttu-id="6f358-197">En el siguiente ejemplo se muestra la estructura de archivos y carpetas de usar *.csproj*  para crear un paquete de plantillas.</span><span class="sxs-lookup"><span data-stu-id="6f358-197">The example below demonstrates the file and folder structure of using a *.csproj* to create a template pack.</span></span> <span data-ttu-id="6f358-198">El archivo *MyDotnetTemplates.csproj* y la carpeta *templates* se encuentran en la raíz de un directorio denominado *project_folder*.</span><span class="sxs-lookup"><span data-stu-id="6f358-198">The *MyDotnetTemplates.csproj* file and *templates* folder are both located at the root of a directory named *project_folder*.</span></span> <span data-ttu-id="6f358-199">La carpeta *templates* contiene dos plantillas: *mytemplate1* y *mytemplate2*.</span><span class="sxs-lookup"><span data-stu-id="6f358-199">The *templates* folder contains two templates, *mytemplate1* and *mytemplate2*.</span></span> <span data-ttu-id="6f358-200">Cada plantilla tiene archivos de contenido y una carpeta *.template.config* con un archivo de configuración *template.json*.</span><span class="sxs-lookup"><span data-stu-id="6f358-200">Each template has content files and a *.template.config* folder with a *template.json* config file.</span></span>

```text
project_folder
│   MyDotnetTemplates.csproj
│
└───templates
    ├───mytemplate1
    │   │   console.cs
    │   │   readme.txt
    │   │
    │   └───.template.config
    │           template.json
    │
    └───mytemplate2
        │   otherfile.cs
        │
        └───.template.config
                template.json
```

## <a name="installing-a-template"></a><span data-ttu-id="6f358-201">Instalar una plantilla</span><span class="sxs-lookup"><span data-stu-id="6f358-201">Installing a template</span></span>

<span data-ttu-id="6f358-202">Use el comando [dotnet new -i|--install](dotnet-new.md) para instalar un paquete.</span><span class="sxs-lookup"><span data-stu-id="6f358-202">Use the [dotnet new -i|--install](dotnet-new.md) command to install a package.</span></span>

### <a name="to-install-a-template-from-a-nuget-package-stored-at-nugetorg"></a><span data-ttu-id="6f358-203">Para instalar una plantilla de un paquete NuGet almacenado en nuget.org</span><span class="sxs-lookup"><span data-stu-id="6f358-203">To install a template from a NuGet package stored at nuget.org</span></span>

<span data-ttu-id="6f358-204">Use el identificador del paquete NuGet para instalar un paquete de plantillas.</span><span class="sxs-lookup"><span data-stu-id="6f358-204">Use the NuGet package identifier to install a template package.</span></span>

```dotnetcli
dotnet new -i <NUGET_PACKAGE_ID>
```

### <a name="to-install-a-template-from-a-local-nupkg-file"></a><span data-ttu-id="6f358-205">Para instalar una plantilla de un archivo nupkg local</span><span class="sxs-lookup"><span data-stu-id="6f358-205">To install a template from a local nupkg file</span></span>

<span data-ttu-id="6f358-206">Proporcione la ruta de acceso a un archivo de paquete NuGet *.nupkg*.</span><span class="sxs-lookup"><span data-stu-id="6f358-206">Provide the path to a *.nupkg* NuGet package file.</span></span>

```dotnetcli
dotnet new -i <PATH_TO_NUPKG_FILE>
```

### <a name="to-install-a-template-from-a-file-system-directory"></a><span data-ttu-id="6f358-207">Para instalar una plantilla desde un directorio de sistema de archivos</span><span class="sxs-lookup"><span data-stu-id="6f358-207">To install a template from a file system directory</span></span>

<span data-ttu-id="6f358-208">Las plantillas se pueden instalar desde una carpeta de plantillas, como la carpeta *mytemplate1* del ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="6f358-208">Templates can be installed from a template folder, such as the *mytemplate1* folder from the example above.</span></span> <span data-ttu-id="6f358-209">Especifique la ruta de acceso de la carpeta *.template.config*.</span><span class="sxs-lookup"><span data-stu-id="6f358-209">Specify the folder path of the *.template.config* folder.</span></span> <span data-ttu-id="6f358-210">La ruta de acceso al directorio de plantillas no es necesario que sea absoluto.</span><span class="sxs-lookup"><span data-stu-id="6f358-210">The path to the template directory does not need to be absolute.</span></span> <span data-ttu-id="6f358-211">Sin embargo, se requiere una ruta de acceso absoluta para desinstalar una plantilla que se instala desde una carpeta.</span><span class="sxs-lookup"><span data-stu-id="6f358-211">However, an absolute path is required to uninstall a template that is installed from a folder.</span></span>

```dotnetcli
dotnet new -i <FILE_SYSTEM_DIRECTORY>
```

## <a name="get-a-list-of-installed-templates"></a><span data-ttu-id="6f358-212">Obtención de una lista de plantillas instaladas</span><span class="sxs-lookup"><span data-stu-id="6f358-212">Get a list of installed templates</span></span>

<span data-ttu-id="6f358-213">El comando de desinstalación, sin ningún otro parámetro, enumerará todas las plantillas instaladas.</span><span class="sxs-lookup"><span data-stu-id="6f358-213">The uninstall command, without any other parameters, will list all installed templates.</span></span>

```dotnetcli
dotnet new -u
```

<span data-ttu-id="6f358-214">Ese comando devuelve algo similar a la salida siguiente:</span><span class="sxs-lookup"><span data-stu-id="6f358-214">That command returns something similar to the following output:</span></span>

```console
Template Instantiation Commands for .NET Core CLI

Currently installed items:
  Microsoft.DotNet.Common.ItemTemplates
    Templates:
      global.json file (globaljson)
      NuGet Config (nugetconfig)
      Solution File (sln)
      Dotnet local tool manifest file (tool-manifest)
      Web Config (webconfig)
  Microsoft.DotNet.Common.ProjectTemplates.3.0
    Templates:
      Class library (classlib) C#
      Class library (classlib) F#
      Class library (classlib) VB
      Console Application (console) C#
      Console Application (console) F#
      Console Application (console) VB
...
```

<span data-ttu-id="6f358-215">El primer nivel de los elementos situados después de `Currently installed items:` son los identificadores usados en la desinstalación de una plantilla.</span><span class="sxs-lookup"><span data-stu-id="6f358-215">The first level of items after `Currently installed items:` are the identifiers used in uninstalling a template.</span></span> <span data-ttu-id="6f358-216">Y en el ejemplo anterior, se enumeran `Microsoft.DotNet.Common.ItemTemplates` y `Microsoft.DotNet.Common.ProjectTemplates.3.0`.</span><span class="sxs-lookup"><span data-stu-id="6f358-216">And in the example above, `Microsoft.DotNet.Common.ItemTemplates` and `Microsoft.DotNet.Common.ProjectTemplates.3.0` are listed.</span></span> <span data-ttu-id="6f358-217">Si la plantilla se instaló mediante una ruta de acceso del sistema de archivos, este identificador será la ruta de acceso de la carpeta *.template.config*.</span><span class="sxs-lookup"><span data-stu-id="6f358-217">If the template was installed by using a file system path, this identifier will the folder path of the *.template.config* folder.</span></span>

## <a name="uninstalling-a-template"></a><span data-ttu-id="6f358-218">Desinstalación de una plantilla</span><span class="sxs-lookup"><span data-stu-id="6f358-218">Uninstalling a template</span></span>

<span data-ttu-id="6f358-219">Use el comando [dotnet new -u|--uninstall](dotnet-new.md) para desinstalar un paquete.</span><span class="sxs-lookup"><span data-stu-id="6f358-219">Use the [dotnet new -u|--uninstall](dotnet-new.md) command to uninstall a package.</span></span>

<span data-ttu-id="6f358-220">Si el paquete lo instaló una fuente de NuGet o un archivo *.nupkg* directamente, proporcione el identificador.</span><span class="sxs-lookup"><span data-stu-id="6f358-220">If the package was installed by either a NuGet feed or by a *.nupkg* file directly, provide the identifier.</span></span>

```dotnetcli
dotnet new -u <NUGET_PACKAGE_ID>
```

<span data-ttu-id="6f358-221">Si el paquete se instaló mediante la especificación de una ruta de acceso a la carpeta *.template.config*, use esa ruta de acceso **absoluta** para desinstalar el paquete.</span><span class="sxs-lookup"><span data-stu-id="6f358-221">If the package was installed by specifying a path to the *.template.config* folder, use that **absolute** path to uninstall the package.</span></span> <span data-ttu-id="6f358-222">Puede ver la ruta de acceso absoluta de la plantilla en el resultado proporcionado por el comando `dotnet new -u`.</span><span class="sxs-lookup"><span data-stu-id="6f358-222">You can see the absolute path of the template in the output provided by the `dotnet new -u` command.</span></span> <span data-ttu-id="6f358-223">Para obtener más información, consulte la sección [Obtención de una lista de plantillas instaladas](#get-a-list-of-installed-templates) anterior.</span><span class="sxs-lookup"><span data-stu-id="6f358-223">For more information, see the [Get a list of installed templates](#get-a-list-of-installed-templates) section above.</span></span>

```dotnetcli
dotnet new -u <ABSOLUTE_FILE_SYSTEM_DIRECTORY>
```

## <a name="create-a-project-using-a-custom-template"></a><span data-ttu-id="6f358-224">Crear un proyecto con una plantilla personalizada</span><span class="sxs-lookup"><span data-stu-id="6f358-224">Create a project using a custom template</span></span>

<span data-ttu-id="6f358-225">Después de que se instale una plantilla, use la plantilla ejecutando el comando `dotnet new <TEMPLATE>` como lo haría con cualquier otra plantilla preinstalada.</span><span class="sxs-lookup"><span data-stu-id="6f358-225">After a template is installed, use the template by executing the `dotnet new <TEMPLATE>` command as you would with any other pre-installed template.</span></span> <span data-ttu-id="6f358-226">También puede especificar [opciones](dotnet-new.md#options) en el comando `dotnet new`, incluidas las opciones específicas de plantilla que ha definido en la configuración de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="6f358-226">You can also specify [options](dotnet-new.md#options) to the `dotnet new` command, including template-specific options you configured in the template settings.</span></span> <span data-ttu-id="6f358-227">Proporcione el nombre breve de la plantilla directamente al comando:</span><span class="sxs-lookup"><span data-stu-id="6f358-227">Supply the template's short name directly to the command:</span></span>

```dotnetcli
dotnet new <TEMPLATE>
```

## <a name="see-also"></a><span data-ttu-id="6f358-228">Vea también</span><span class="sxs-lookup"><span data-stu-id="6f358-228">See also</span></span>

- [<span data-ttu-id="6f358-229">Creación de una plantilla personalizada para dotnet new (tutorial)</span><span class="sxs-lookup"><span data-stu-id="6f358-229">Create a custom template for dotnet new (tutorial)</span></span>](../tutorials/cli-templates-create-item-template.md)
- [<span data-ttu-id="6f358-230">Wiki del repositorio de GitHub dotnet/templating</span><span class="sxs-lookup"><span data-stu-id="6f358-230">dotnet/templating GitHub repo Wiki</span></span>](https://github.com/dotnet/templating/wiki)
- [<span data-ttu-id="6f358-231">Repositorio de GitHub dotnet/dotnet-template-samples</span><span class="sxs-lookup"><span data-stu-id="6f358-231">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- <span data-ttu-id="6f358-232">[How to create your own templates for dotnet new](https://devblogs.microsoft.com/dotnet/how-to-create-your-own-templates-for-dotnet-new/) (Cómo crear sus propias plantillas para dotnet new)</span><span class="sxs-lookup"><span data-stu-id="6f358-232">[How to create your own templates for dotnet new](https://devblogs.microsoft.com/dotnet/how-to-create-your-own-templates-for-dotnet-new/)</span></span>
- [<span data-ttu-id="6f358-233">Esquema *template.json* en el Almacenamiento del esquema JSON</span><span class="sxs-lookup"><span data-stu-id="6f358-233">*template.json* schema at the JSON Schema Store</span></span>](http://json.schemastore.org/template)
