---
title: "Creación de una plantilla personalizada para dotnet new"
description: "Obtenga información sobre cómo crear una plantilla personalizada para el comando dotnet new en este ameno tutorial."
keywords: ".NET, .NET Core, plantilla, creación de plantillas, tutorial, dotnet new"
author: guardrex
ms.author: mairaw
ms.date: 08/12/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 519b910a-6efe-4394-9b81-0546aa3e7462
ms.translationtype: HT
ms.sourcegitcommit: c58ed1b3c09f1e358d0b66f6cf7186821601fd69
ms.openlocfilehash: e31977c511f18737aef673c78a3e295d7c24782f
ms.contentlocale: es-es
ms.lasthandoff: 08/12/2017

---

# <a name="create-a-custom-template-for-dotnet-new"></a><span data-ttu-id="fe245-104">Creación de una plantilla personalizada para dotnet new</span><span class="sxs-lookup"><span data-stu-id="fe245-104">Create a custom template for dotnet new</span></span>

<span data-ttu-id="fe245-105">En este tutorial se le enseñará a hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fe245-105">This tutorial shows you how to:</span></span>

- <span data-ttu-id="fe245-106">Crear una plantilla básica a partir de un proyecto existente o un nuevo proyecto de aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="fe245-106">Create a basic template from an existing project or a new console app project.</span></span>
- <span data-ttu-id="fe245-107">Empaquetar la plantilla para su distribución en nuget.org o a partir de un archivo *nupkg* local.</span><span class="sxs-lookup"><span data-stu-id="fe245-107">Pack the template for distribution at nuget.org or from a local *nupkg* file.</span></span>
- <span data-ttu-id="fe245-108">Instalar la plantilla desde nuget.org, un archivo *nupkg* local o el sistema de archivos local.</span><span class="sxs-lookup"><span data-stu-id="fe245-108">Install the template from nuget.org, a local *nupkg* file, or the local file system.</span></span>
- <span data-ttu-id="fe245-109">Desinstalar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="fe245-109">Uninstall the template.</span></span>

<span data-ttu-id="fe245-110">Si prefiere hacer uso del tutorial con una muestra completa, descargue la [plantilla de proyecto de muestra](https://github.com/dotnet/dotnet-template-samples/tree/master/16-nuget-package).</span><span class="sxs-lookup"><span data-stu-id="fe245-110">If you prefer to proceed through the tutorial with a complete sample, download the [sample project template](https://github.com/dotnet/dotnet-template-samples/tree/master/16-nuget-package).</span></span> <span data-ttu-id="fe245-111">La plantilla de muestra está configurada para la distribución de NuGet.</span><span class="sxs-lookup"><span data-stu-id="fe245-111">The sample template is configured for NuGet distribution.</span></span>

<span data-ttu-id="fe245-112">Si quiere usar el ejemplo descargado con la distribución del sistema de archivos, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fe245-112">If you wish to use the downloaded sample with file system distribution, do the following:</span></span>

- <span data-ttu-id="fe245-113">Suba un nivel el contenido de la carpeta *content* de la muestra a la carpeta *GarciaSoftware.ConsoleTemplate.CSharp*.</span><span class="sxs-lookup"><span data-stu-id="fe245-113">Move the contents of the *content* folder of the sample up one level into the *GarciaSoftware.ConsoleTemplate.CSharp* folder.</span></span>
- <span data-ttu-id="fe245-114">Elimine la carpeta *content* vacía.</span><span class="sxs-lookup"><span data-stu-id="fe245-114">Delete the empty *content* folder.</span></span>
- <span data-ttu-id="fe245-115">Elimine el archivo *nuspec*.</span><span class="sxs-lookup"><span data-stu-id="fe245-115">Delete the *nuspec* file.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fe245-116">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="fe245-116">Prerequisites</span></span>

- <span data-ttu-id="fe245-117">Instalar el [SDK de .NET Core 2.0](https://www.microsoft.com/net/core) o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="fe245-117">Install the [.NET Core 2.0 SDK](https://www.microsoft.com/net/core) or later versions.</span></span>
- <span data-ttu-id="fe245-118">Leer el tema de referencia [Custom templates for dotnet new](../tools/custom-templates.md) (Plantillas personalizadas para dotnet new).</span><span class="sxs-lookup"><span data-stu-id="fe245-118">Read the reference topic [Custom templates for dotnet new](../tools/custom-templates.md).</span></span>

## <a name="create-a-template-from-a-project"></a><span data-ttu-id="fe245-119">Creación de una plantilla a partir de un proyecto</span><span class="sxs-lookup"><span data-stu-id="fe245-119">Create a template from a project</span></span>

<span data-ttu-id="fe245-120">Use un proyecto existente que se haya confirmado que se compila y se ejecuta, o cree un proyecto de aplicación de consola en una carpeta del disco duro.</span><span class="sxs-lookup"><span data-stu-id="fe245-120">Use an existing project that you've confirmed it compiles and runs, or create a new console app project in a folder on your hard drive.</span></span> <span data-ttu-id="fe245-121">En este tutorial se da por hecho que el nombre de la carpeta de proyecto es *GarciaSoftware.ConsoleTemplate.CSharp* y que está almacenada en *Documentos/Plantillas* en el perfil del usuario.</span><span class="sxs-lookup"><span data-stu-id="fe245-121">This tutorial assumes that the name of the project folder is *GarciaSoftware.ConsoleTemplate.CSharp* stored at *Documents/Templates* in the user's profile.</span></span> <span data-ttu-id="fe245-122">El nombre de la plantilla de proyecto del tutorial tiene el formato *\<nombre de la compañía>.\<tipo de plantilla>.\<lenguaje de programación>*, pero puede asignar el nombre que quiera al proyecto y a la plantilla.</span><span class="sxs-lookup"><span data-stu-id="fe245-122">The tutorial project template name is in the format *\<Company Name>.\<Template Type>.\<Programming Language>*, but you're free to name your project and template anything you wish.</span></span>

1. <span data-ttu-id="fe245-123">Agregue una carpeta a la raíz del proyecto denominada *.template.config*.</span><span class="sxs-lookup"><span data-stu-id="fe245-123">Add a folder to the root of the project named *.template.config*.</span></span>
1. <span data-ttu-id="fe245-124">Dentro de la carpeta *.template.config*, cree un archivo *template.json* para configurar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="fe245-124">Inside the *.template.config* folder, create a *template.json* file to configure your template.</span></span> <span data-ttu-id="fe245-125">Para obtener más información y definiciones de miembros para el archivo *template.json*, vea el tema [Custom templates for dotnet new](../tools/custom-templates.md#templatejson) (Plantillas personalizadas para dotnet new) y el esquema [*template.json* en el almacenamiento del esquema JSON](http://json.schemastore.org/template).</span><span class="sxs-lookup"><span data-stu-id="fe245-125">For more information and member definitions for the *template.json* file, see the [Custom templates for dotnet new](../tools/custom-templates.md#templatejson) topic and the [*template.json* schema at the JSON Schema Store](http://json.schemastore.org/template).</span></span>

```json
{
    "$schema": "http://json.schemastore.org/template",
    "author": "Catalina Garcia",
    "classifications": [ "Common", "Console" ],
    "identity": "GarciaSoftware.ConsoleTemplate.CSharp",
    "name": "Garcia Software Console Application",
    "shortName": "garciaconsole"
}
```

<span data-ttu-id="fe245-126">Ha terminado la plantilla.</span><span class="sxs-lookup"><span data-stu-id="fe245-126">The template is finished.</span></span> <span data-ttu-id="fe245-127">Una vez hecho esto, tiene dos opciones para la distribución de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="fe245-127">At this point, you have two options for template distribution.</span></span> <span data-ttu-id="fe245-128">Para continuar con este tutorial, elija uno de los dos pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="fe245-128">To continue this tutorial, choose one path or the other:</span></span>

1. <span data-ttu-id="fe245-129">[Distribución de NuGet](#use-nuget-distribution): instalación de la plantilla de NuGet o del paquete *nupkg* local y uso de la plantilla instalada.</span><span class="sxs-lookup"><span data-stu-id="fe245-129">[NuGet distribution](#use-nuget-distribution): install the template from NuGet or from the local *nupkg* file, and use the installed template.</span></span>
2. <span data-ttu-id="fe245-130">[Distribución del sistema de archivos](#use-file-system-distribution).</span><span class="sxs-lookup"><span data-stu-id="fe245-130">[File system distribution](#use-file-system-distribution).</span></span>

## <a name="use-nuget-distribution"></a><span data-ttu-id="fe245-131">Uso de la distribución de NuGet</span><span class="sxs-lookup"><span data-stu-id="fe245-131">Use NuGet Distribution</span></span>

### <a name="pack-the-template-into-a-nuget-package"></a><span data-ttu-id="fe245-132">Empaquetar la plantilla en un paquete de NuGet</span><span class="sxs-lookup"><span data-stu-id="fe245-132">Pack the template into a NuGet package</span></span>

1. <span data-ttu-id="fe245-133">Cree una carpeta para el paquete de NuGet.</span><span class="sxs-lookup"><span data-stu-id="fe245-133">Create a folder for the NuGet package.</span></span> <span data-ttu-id="fe245-134">Para el tutorial, se usa el nombre de carpeta *GarciaSoftware.ConsoleTemplate.CSharp*, y esta se crea dentro de una carpeta *Documentos/NuGetTemplates* del perfil del usuario.</span><span class="sxs-lookup"><span data-stu-id="fe245-134">For the tutorial, the folder name *GarciaSoftware.ConsoleTemplate.CSharp* is used, and the folder is created inside a *Documents/NuGetTemplates* folder in the user's profile.</span></span> <span data-ttu-id="fe245-135">Cree una carpeta denominada *content* dentro de la nueva carpeta de plantillas que contendrá los archivos del proyecto.</span><span class="sxs-lookup"><span data-stu-id="fe245-135">Create a folder named *content* inside of the new template folder to hold the project files.</span></span>
1. <span data-ttu-id="fe245-136">Copie el contenido de la carpeta del proyecto, junto con el archivo *.template.config/template.json*, en la carpeta *content* que ha creado.</span><span class="sxs-lookup"><span data-stu-id="fe245-136">Copy the contents of your project folder, together with its *.template.config/template.json* file, into the *content* folder you created.</span></span>
1. <span data-ttu-id="fe245-137">Junto a la carpeta *content*, agregue un [archivo *nuspec*](/nuget/create-packages/creating-a-package).</span><span class="sxs-lookup"><span data-stu-id="fe245-137">Next to the *content* folder, add a [*nuspec* file](/nuget/create-packages/creating-a-package).</span></span> <span data-ttu-id="fe245-138">El archivo nuspec es un archivo de manifiesto XML en el que se describe el contenido de un paquete y que controla el proceso de creación del paquete de NuGet.</span><span class="sxs-lookup"><span data-stu-id="fe245-138">The nuspec file is an XML manifest file that describes a package's contents and drives the process of creating the NuGet package.</span></span>
   
   ![Estructura de directorios en la que se muestra el diseño del paquete de NuGet](./media/create-custom-template/nugetdirectorylayout.png)

1. <span data-ttu-id="fe245-140">Dentro de un elemento **\<packageTypes>** en el archivo *nuspec*, incluya un elemento **\<packageType>** con un valor de atributo `name` de `Template`.</span><span class="sxs-lookup"><span data-stu-id="fe245-140">Inside of a **\<packageTypes>** element in the *nuspec* file, include a **\<packageType>** element with a `name` attribute value of `Template`.</span></span> <span data-ttu-id="fe245-141">Tanto la carpeta *content* como el archivo *nuspec* deben estar en el mismo directorio.</span><span class="sxs-lookup"><span data-stu-id="fe245-141">Both the *content* folder and the *nuspec* file should reside in the same directory.</span></span> <span data-ttu-id="fe245-142">En la tabla se muestran los elementos de archivo *nuspec* mínimos necesarios para generar una plantilla como un paquete NuGet.</span><span class="sxs-lookup"><span data-stu-id="fe245-142">The table shows the minimum *nuspec* file elements required to produce a template as a NuGet package.</span></span>

   | <span data-ttu-id="fe245-143">Elemento</span><span class="sxs-lookup"><span data-stu-id="fe245-143">Element</span></span>            | <span data-ttu-id="fe245-144">Tipo</span><span class="sxs-lookup"><span data-stu-id="fe245-144">Type</span></span>   | <span data-ttu-id="fe245-145">Descripción</span><span class="sxs-lookup"><span data-stu-id="fe245-145">Description</span></span> |
   | ------------------ | ------ | ----------- |
   | <span data-ttu-id="fe245-146">**\<authors>**</span><span class="sxs-lookup"><span data-stu-id="fe245-146">**\<authors>**</span></span>     | <span data-ttu-id="fe245-147">string</span><span class="sxs-lookup"><span data-stu-id="fe245-147">string</span></span> | <span data-ttu-id="fe245-148">Una lista separada por comas de los autores de los paquetes, que coinciden con los nombres de perfil de nuget.org.</span><span class="sxs-lookup"><span data-stu-id="fe245-148">A comma-separated list of packages authors, matching the profile names on nuget.org.</span></span> <span data-ttu-id="fe245-149">Estos se muestran en la galería de NuGet, en nuget.org, y se usan para hacer referencias cruzadas a paquetes de los mismos autores.</span><span class="sxs-lookup"><span data-stu-id="fe245-149">Authors are displayed in the NuGet Gallery on nuget.org and are used to cross-reference packages by the same authors.</span></span> |
   | <span data-ttu-id="fe245-150">**\<description>**</span><span class="sxs-lookup"><span data-stu-id="fe245-150">**\<description>**</span></span> | <span data-ttu-id="fe245-151">string</span><span class="sxs-lookup"><span data-stu-id="fe245-151">string</span></span> | <span data-ttu-id="fe245-152">Una descripción larga del paquete para su visualización en la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="fe245-152">A long description of the package for UI display.</span></span> |
   | <span data-ttu-id="fe245-153">**\<id>**</span><span class="sxs-lookup"><span data-stu-id="fe245-153">**\<id>**</span></span>          | <span data-ttu-id="fe245-154">string</span><span class="sxs-lookup"><span data-stu-id="fe245-154">string</span></span> | <span data-ttu-id="fe245-155">El identificador del paquete que no distingue entre mayúsculas y minúsculas, que debe ser único en nuget.org o en la galería en la que se mantendrá el paquete.</span><span class="sxs-lookup"><span data-stu-id="fe245-155">The case-insensitive package identifier, which must be unique across nuget.org or whatever gallery the package will reside in.</span></span> <span data-ttu-id="fe245-156">Los id. no pueden contener espacios ni caracteres no válidos para una URL y normalmente seguirán las reglas de espacios de nombres de .NET.</span><span class="sxs-lookup"><span data-stu-id="fe245-156">IDs may not contain spaces or characters that are not valid for a URL and generally follow .NET namespace rules.</span></span> <span data-ttu-id="fe245-157">Vea [Choosing a unique package identifier and setting the version number](/nuget/create-packages/creating-a-package#choosing-a-unique-package-identifier-and-setting-the-version-number) (Elección de un identificador de paquete único y establecimiento del número de versión) para obtener instrucciones.</span><span class="sxs-lookup"><span data-stu-id="fe245-157">See [Choosing a unique package identifier and setting the version number](/nuget/create-packages/creating-a-package#choosing-a-unique-package-identifier-and-setting-the-version-number) for guidance.</span></span> |
   | <span data-ttu-id="fe245-158">**\<packageType>**</span><span class="sxs-lookup"><span data-stu-id="fe245-158">**\<packageType>**</span></span> | <span data-ttu-id="fe245-159">string</span><span class="sxs-lookup"><span data-stu-id="fe245-159">string</span></span> | <span data-ttu-id="fe245-160">Coloque este elemento dentro de un elemento **\<packageTypes>** entre los elementos **\<metadata>**.</span><span class="sxs-lookup"><span data-stu-id="fe245-160">Place this element inside a **\<packageTypes>** element among the **\<metadata>** elements.</span></span> <span data-ttu-id="fe245-161">Establezca el atributo `name` del elemento **\<packageType>** en `Template`.</span><span class="sxs-lookup"><span data-stu-id="fe245-161">Set the `name` attribute of the **\<packageType>** element to `Template`.</span></span> |
   | <span data-ttu-id="fe245-162">**\<version>**</span><span class="sxs-lookup"><span data-stu-id="fe245-162">**\<version>**</span></span>     | <span data-ttu-id="fe245-163">string</span><span class="sxs-lookup"><span data-stu-id="fe245-163">string</span></span> | <span data-ttu-id="fe245-164">La versión del paquete, siguiendo el patrón de mayor.menor.revisión.</span><span class="sxs-lookup"><span data-stu-id="fe245-164">The version of the package, following the major.minor.patch pattern.</span></span> <span data-ttu-id="fe245-165">Los números de versión pueden incluir un sufijo de versión preliminar, tal y como se describe en [Versiones preliminares](/nuget/create-packages/prerelease-packages#semantic-versioning).</span><span class="sxs-lookup"><span data-stu-id="fe245-165">Version numbers may include a pre-release suffix as described in [Pre-release versions](/nuget/create-packages/prerelease-packages#semantic-versioning).</span></span> |

   <span data-ttu-id="fe245-166">Consulte [.nuspec reference](/nuget/schema/nuspec) (Referencia de .nuspec) para ver el esquema de archivo de *nuspec* completo.</span><span class="sxs-lookup"><span data-stu-id="fe245-166">See the [.nuspec reference](/nuget/schema/nuspec) for the complete *nuspec* file schema.</span></span>

   <span data-ttu-id="fe245-167">El archivo *nuspec* para el tutorial se denomina *GarciaSoftware.ConsoleTemplate.CSharp.nuspec* e incluye el siguiente contenido:</span><span class="sxs-lookup"><span data-stu-id="fe245-167">The *nuspec* file for the tutorial is named *GarciaSoftware.ConsoleTemplate.CSharp.nuspec* and contains the following content:</span></span>

   ```xml
   <?xml version="1.0" encoding="utf-8"?>
   <package xmlns="http://schemas.microsoft.com/packaging/2012/06/nuspec.xsd">
     <metadata>
       <id>GarciaSoftware.ConsoleTemplate.CSharp</id>
       <version>1.0.0</version>
       <description>
         Creates the Garcia Software console app.
       </description>
       <authors>Catalina Garcia</authors>
       <packageTypes>
         <packageType name="Template" />
       </packageTypes>
     </metadata>
   </package>
   ```

1. <span data-ttu-id="fe245-168">[Cree el paquete](/nuget/create-packages/creating-a-package#creating-the-package) mediante el comando `nuget pack <PATH_TO_NUSPEC_FILE>`.</span><span class="sxs-lookup"><span data-stu-id="fe245-168">[Create the package](/nuget/create-packages/creating-a-package#creating-the-package) using the `nuget pack <PATH_TO_NUSPEC_FILE>` command.</span></span> <span data-ttu-id="fe245-169">En el comando siguiente se da por supuesto que la carpeta que contiene los recursos de NuGet está en *C:/Users/\<USUARIO>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp/*.</span><span class="sxs-lookup"><span data-stu-id="fe245-169">The following command assumes that the folder that holds the NuGet assets is at *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp/*.</span></span> <span data-ttu-id="fe245-170">En cambio, no importa dónde ponga la carpeta en el sistema, el comando `nuget pack` acepta la ruta de acceso al archivo *nuspec*:</span><span class="sxs-lookup"><span data-stu-id="fe245-170">But wherever you place the folder on your system, the `nuget pack` command accepts the path to the *nuspec* file:</span></span>

   ```console
   nuget pack C:/Users/<USER>/Documents/NuGetTemplates/GarciaSoftware.ConsoleTemplate.CSharp/GarciaSoftware.ConsoleTemplate.CSharp.nuspec
   ```

### <a name="publishing-the-package-to-nugetorg"></a><span data-ttu-id="fe245-171">Publicación del paquete en nuget.org</span><span class="sxs-lookup"><span data-stu-id="fe245-171">Publishing the package to nuget.org</span></span>

<span data-ttu-id="fe245-172">Para publicar un paquete de NuGet, siga las instrucciones del tema [Create and publish a package](/nuget/quickstart/create-and-publish-a-package#publish-the-package) (Crear y publicar un paquete).</span><span class="sxs-lookup"><span data-stu-id="fe245-172">To publish a NuGet package, follow the instructions in the [Create and publish a package](/nuget/quickstart/create-and-publish-a-package#publish-the-package) topic.</span></span> <span data-ttu-id="fe245-173">En cambio, se recomienda que no publique la plantilla de tutorial en NuGet, ya que no se puede eliminar una vez publicada, solo se puede eliminar de la lista.</span><span class="sxs-lookup"><span data-stu-id="fe245-173">However, we recommend that you don't publish the tutorial template to NuGet as it can never be deleted once published, only delisted.</span></span> <span data-ttu-id="fe245-174">Ahora que tiene el paquete de NuGet en forma de un archivo *nupkg*, le recomendamos que siga estas instrucciones para instalar la plantilla directamente a partir del archivo *nupkg* local.</span><span class="sxs-lookup"><span data-stu-id="fe245-174">Now that you have the NuGet package in the form of a *nupkg* file, we suggest that you follow the instructions below to install the template directly from the local *nupkg* file.</span></span>

### <a name="install-the-template-from-a-nuget-package"></a><span data-ttu-id="fe245-175">Instalación de la plantilla a partir de un paquete de NuGet</span><span class="sxs-lookup"><span data-stu-id="fe245-175">Install the template from a NuGet package</span></span>

#### <a name="install-the-template-from-the-local-nupkg-file"></a><span data-ttu-id="fe245-176">Instalación de la plantilla a partir del archivo *nupkg* local</span><span class="sxs-lookup"><span data-stu-id="fe245-176">Install the template from the local *nupkg* file</span></span>

<span data-ttu-id="fe245-177">Para instalar la plantilla a partir del archivo *nupkg* que ha creado, use el comando `dotnet new` con la opción `-i|--install` y proporcione la ruta de acceso al archivo *nupkg*:</span><span class="sxs-lookup"><span data-stu-id="fe245-177">To install the template from the *nupkg* file that you produced, use the `dotnet new` command with the `-i|--install` option and provide the path to the *nupkg* file:</span></span>

```console
dotnet new -i C:/Users/<USER>/GarciaSoftware.ConsoleTemplate.CSharp.1.0.0.nupkg
```

#### <a name="install-the-template-from-a-nuget-package-stored-at-nugetorg"></a><span data-ttu-id="fe245-178">Instalación de la plantilla a partir de un paquete de NuGet almacenado en nuget.org</span><span class="sxs-lookup"><span data-stu-id="fe245-178">Install the template from a NuGet package stored at nuget.org</span></span>

<span data-ttu-id="fe245-179">Si quiere volver a instalar una plantilla a partir de un paquete de NuGet almacenado en nuget.org, use el comando `dotnet new` con la opción `-i|--install` y proporcione el nombre del paquete de NuGet:</span><span class="sxs-lookup"><span data-stu-id="fe245-179">If you wish to install a template from a NuGet package stored at nuget.org, use the `dotnet new` command with the `-i|--install` option and supply the name of the NuGet package:</span></span>

```console
dotnet new -i GarciaSoftware.ConsoleTemplate.CSharp
```

> [!NOTE]
> <span data-ttu-id="fe245-180">El ejemplo solamente sirve de demostración.</span><span class="sxs-lookup"><span data-stu-id="fe245-180">The example is for demonstration purposes only.</span></span> <span data-ttu-id="fe245-181">No hay ningún paquete de NuGet denominado `GarciaSoftware.ConsoleTemplate.CSharp` en nuget.org y no se recomienda que publique y consuma las plantillas de prueba de NuGet.</span><span class="sxs-lookup"><span data-stu-id="fe245-181">There isn't a `GarciaSoftware.ConsoleTemplate.CSharp` NuGet package at nuget.org, and we don't recommend that you publish and consume test templates from NuGet.</span></span> <span data-ttu-id="fe245-182">Si ejecuta el comando, no se instala ninguna plantilla.</span><span class="sxs-lookup"><span data-stu-id="fe245-182">If you run the command, no template is installed.</span></span> <span data-ttu-id="fe245-183">En cambio, puede instalar una plantilla que no se haya publicado en nuget.org si hace referencia al archivo *nupkg* directamente en el sistema de archivos local, tal y como se muestra en la sección anterior [Instalación de la plantilla a partir de un archivo nupkg local](#install-the-template-from-the-local-nupkg-file).</span><span class="sxs-lookup"><span data-stu-id="fe245-183">However, you can install a template that hasn't been published to nuget.org by referencing the *nupkg* file directly on your local file system as shown in the previous section [Install the template from the local nupkg file](#install-the-template-from-the-local-nupkg-file).</span></span>

<span data-ttu-id="fe245-184">Si quiere ver un ejemplo de cómo instalar una plantilla de un paquete en nuget.org, puede usar la [plantilla de NUnit 3 para dotnet-new](https://www.nuget.org/packages/NUnit3.DotNetNew.Template/).</span><span class="sxs-lookup"><span data-stu-id="fe245-184">If you'd like a live example of how to install a template from a package at nuget.org, you can use the [NUnit 3 template for dotnet-new](https://www.nuget.org/packages/NUnit3.DotNetNew.Template/).</span></span> <span data-ttu-id="fe245-185">Esta plantilla configura un proyecto para usar las pruebas unitarias de NUnit.</span><span class="sxs-lookup"><span data-stu-id="fe245-185">This template sets up a project to use NUnit unit testing.</span></span> <span data-ttu-id="fe245-186">Use el comando siguiente para instalarla:</span><span class="sxs-lookup"><span data-stu-id="fe245-186">Use the following command to install it:</span></span>

```console
dotnet new -i NUnit3.DotNetNew.Template
```

<span data-ttu-id="fe245-187">Al enumerar las plantillas con `dotnet new -l`, verá el *proyecto de prueba de NUnit 3* con el breve nombre de *nunit* en la lista de plantillas.</span><span class="sxs-lookup"><span data-stu-id="fe245-187">When you list the templates with `dotnet new -l`, you see the *NUnit 3 Test Project* with a short name of *nunit* in the template list.</span></span> <span data-ttu-id="fe245-188">Está listo para usar la plantilla en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="fe245-188">You're ready to use the template in the next section.</span></span>

![Ventana de consola en la que muestra la plantilla de NUnit junto a otras plantillas instaladas](./media/create-custom-template/nunit1.png)

### <a name="create-a-project-from-the-template"></a><span data-ttu-id="fe245-190">Creación de un proyecto a partir de la plantilla</span><span class="sxs-lookup"><span data-stu-id="fe245-190">Create a project from the template</span></span>

<span data-ttu-id="fe245-191">Después de instalar la plantilla desde NuGet, ejecute el comando `dotnet new <TEMPLATE>` desde el directorio donde quiera que se coloque la salida del motor de plantillas (a menos que esté usando la opción `-o|--output` para especificar un directorio específico) para usarla.</span><span class="sxs-lookup"><span data-stu-id="fe245-191">After the template is installed from NuGet, use the template by executing the `dotnet new <TEMPLATE>` command from the directory where you want to the template engine's output placed (unless you're using the `-o|--output` option to specify a specific directory).</span></span> <span data-ttu-id="fe245-192">Para obtener más información, consulte las [Opciones de `dotnet new`](~/docs/core/tools/dotnet-new.md#options).</span><span class="sxs-lookup"><span data-stu-id="fe245-192">For more information, see [`dotnet new` Options](~/docs/core/tools/dotnet-new.md#options).</span></span> <span data-ttu-id="fe245-193">Proporcione el nombre breve de la plantilla directamente junto al comando `dotnet new`.</span><span class="sxs-lookup"><span data-stu-id="fe245-193">Supply the template's short name directly to the `dotnet new` command.</span></span> <span data-ttu-id="fe245-194">Para crear un proyecto a partir de la plantilla de NUnit, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="fe245-194">To create a project from the NUnit template, run the following command:</span></span>

```console
dotnet new nunit
```

<span data-ttu-id="fe245-195">En la consola se muestra que se crea el proyecto y que se restauran los paquetes de este.</span><span class="sxs-lookup"><span data-stu-id="fe245-195">The console shows that the project is created and that the project's packages are restored.</span></span> <span data-ttu-id="fe245-196">Después de ejecutar el comando, el proyecto estará listo para usarse.</span><span class="sxs-lookup"><span data-stu-id="fe245-196">After the command is run, the project is ready for use.</span></span>

![Ventana de consola en la que se muestra la salida del comando dotnet new en el proceso de creación del proyecto de NUnit y de restauración de las dependencias del proyecto](./media/create-custom-template/nunit2.png)

### <a name="to-uninstall-a-template-from-a-nuget-package-stored-at-nugetorg"></a><span data-ttu-id="fe245-198">Desinstalación de una plantilla de un paquete de NuGet almacenado en nuget.org</span><span class="sxs-lookup"><span data-stu-id="fe245-198">To uninstall a template from a NuGet package stored at nuget.org</span></span>

```console
dotnet new -u GarciaSoftware.ConsoleTemplate.CSharp
```

> [!NOTE]
> <span data-ttu-id="fe245-199">El ejemplo solamente sirve de demostración.</span><span class="sxs-lookup"><span data-stu-id="fe245-199">The example is for demonstration purposes only.</span></span> <span data-ttu-id="fe245-200">No hay ningún paquete de NuGet denominado `GarciaSoftware.ConsoleTemplate.CSharp` en nuget.org ni instalado con el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="fe245-200">There isn't a `GarciaSoftware.ConsoleTemplate.CSharp` NuGet package at nuget.org or installed with the .NET Core SDK.</span></span> <span data-ttu-id="fe245-201">Si ejecuta el comando, no se desinstalará ninguna plantilla ni paquete y se mostrará la siguiente excepción:</span><span class="sxs-lookup"><span data-stu-id="fe245-201">If you run the command, no package/template is uninstalled and you receive the following exception:</span></span>
> 
> > <span data-ttu-id="fe245-202">Could not find something to uninstall called 'GarciaSoftware.ConsoleTemplate.CSharp' (No se ha encontrado nada denominado “GarciaSoftware.ConsoleTemplate.CSharp” para desinstalarlo).</span><span class="sxs-lookup"><span data-stu-id="fe245-202">Could not find something to uninstall called 'GarciaSoftware.ConsoleTemplate.CSharp'.</span></span>

<span data-ttu-id="fe245-203">Si ha instalado la [plantilla de NUnit 3 para dotnet-new](https://www.nuget.org/packages/NUnit3.DotNetNew.Template/) y quiere desinstalarla, use el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="fe245-203">If you installed the [NUnit 3 template for dotnet-new](https://www.nuget.org/packages/NUnit3.DotNetNew.Template/) and wish to uninstall it, use the following command:</span></span>

```console
dotnet new -u NUnit3.DotNetNew.Template
```

### <a name="uninstall-the-template-from-a-local-nupkg-file"></a><span data-ttu-id="fe245-204">Desinstalación de la plantilla de un paquete de nupkg local</span><span class="sxs-lookup"><span data-stu-id="fe245-204">Uninstall the template from a local nupkg file</span></span>

<span data-ttu-id="fe245-205">Si quiere desinstalar la plantilla, no intente usar la ruta de acceso al archivo *nupkg*.</span><span class="sxs-lookup"><span data-stu-id="fe245-205">When you wish to uninstall the template, don't attempt to use the path to the *nupkg* file.</span></span> <span data-ttu-id="fe245-206">*Si intenta desinstalar una plantilla mediante `dotnet new -u <PATH_TO_NUPKG_FILE>`, se produce un error.*</span><span class="sxs-lookup"><span data-stu-id="fe245-206">*Attempting to uninstall a template using `dotnet new -u <PATH_TO_NUPKG_FILE>` fails.*</span></span> <span data-ttu-id="fe245-207">Haga referencia al paquete por su `id`:</span><span class="sxs-lookup"><span data-stu-id="fe245-207">Reference the package by its `id`:</span></span>

```console
dotnet new -u GarciaSoftware.ConsoleTemplate.CSharp.1.0.0
```

## <a name="use-file-system-distribution"></a><span data-ttu-id="fe245-208">Uso de la distribución del sistema de archivos</span><span class="sxs-lookup"><span data-stu-id="fe245-208">Use file system distribution</span></span>

<span data-ttu-id="fe245-209">Para distribuir la plantilla, coloque la carpeta de plantillas de proyecto en una ubicación accesible para los usuarios de la red.</span><span class="sxs-lookup"><span data-stu-id="fe245-209">To distribute the template, place the project template folder in a location accessible to users on your network.</span></span> <span data-ttu-id="fe245-210">Use el comando `dotnet new` con la opción `-i|--install` y especifique la ruta de acceso a la carpeta de plantillas (la carpeta del proyecto que contiene el proyecto y la carpeta *.template.config*).</span><span class="sxs-lookup"><span data-stu-id="fe245-210">Use the `dotnet new` command with the `-i|--install` option and specify the path to the template folder (the project folder containing the project and the *.template.config* folder).</span></span>

<span data-ttu-id="fe245-211">En este tutorial se da por supuesto que la plantilla de proyecto se almacena en la carpeta *Documents/Templates* del perfil de usuario.</span><span class="sxs-lookup"><span data-stu-id="fe245-211">The tutorial assumes the project template is stored in the *Documents/Templates* folder of the user's profile.</span></span> <span data-ttu-id="fe245-212">Desde esa ubicación, instale la plantilla con el comando siguiente, pero reemplazando \<USER> con el nombre del perfil de usuario:</span><span class="sxs-lookup"><span data-stu-id="fe245-212">From that location, install the template with the following command replacing \<USER> with the user's profile name:</span></span>

```console
dotnet new -i C:/Users/<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp
```

### <a name="create-a-project-from-the-template"></a><span data-ttu-id="fe245-213">Creación de un proyecto a partir de la plantilla</span><span class="sxs-lookup"><span data-stu-id="fe245-213">Create a project from the template</span></span>

<span data-ttu-id="fe245-214">Después de instalar la plantilla a partir del sistema de archivos, ejecute el comando `dotnet new <TEMPLATE>` desde el directorio donde quiera que se coloque la salida del motor de plantillas (a menos que esté usando la opción `-o|--output` para especificar un directorio específico) para usarla.</span><span class="sxs-lookup"><span data-stu-id="fe245-214">After the template is installed from the file system, use the template by executing the `dotnet new <TEMPLATE>` command from the directory where you want to the template engine's output placed (unless you're using the `-o|--output` option to specify a specific directory).</span></span> <span data-ttu-id="fe245-215">Para obtener más información, consulte las [Opciones de `dotnet new`](~/docs/core/tools/dotnet-new.md#options).</span><span class="sxs-lookup"><span data-stu-id="fe245-215">For more information, see [`dotnet new` Options](~/docs/core/tools/dotnet-new.md#options).</span></span> <span data-ttu-id="fe245-216">Proporcione el nombre breve de la plantilla directamente junto al comando `dotnet new`.</span><span class="sxs-lookup"><span data-stu-id="fe245-216">Supply the template's short name directly to the `dotnet new` command.</span></span>

<span data-ttu-id="fe245-217">Desde una nueva carpeta de proyecto creada en *C:/Users/\<USUARIO>/Documents/Projects/MyConsoleApp*, cree un proyecto a partir de la plantilla `garciaconsole`:</span><span class="sxs-lookup"><span data-stu-id="fe245-217">From a new project folder created at *C:/Users/\<USER>/Documents/Projects/MyConsoleApp*, create a project from the `garciaconsole` template:</span></span>

```console
dotnet new garciaconsole
```

### <a name="uninstall-the-template"></a><span data-ttu-id="fe245-218">Desinstalación de la plantilla</span><span class="sxs-lookup"><span data-stu-id="fe245-218">Uninstall the template</span></span>

<span data-ttu-id="fe245-219">Si ha creado la plantilla en el sistema de archivos local en *C:/Users/\<USUARIO>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp*, desinstálela con el modificador `-u|--uninstall` e indicando la ruta de acceso a la carpeta de la plantilla:</span><span class="sxs-lookup"><span data-stu-id="fe245-219">If you created the template on your local file system at *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp*, uninstall it with the `-u|--uninstall` switch and the path to the template folder:</span></span>

```console
dotnet new -u C:/Users/<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp
```

## <a name="see-also"></a><span data-ttu-id="fe245-220">Vea también</span><span class="sxs-lookup"><span data-stu-id="fe245-220">See also</span></span>

[<span data-ttu-id="fe245-221">Wiki del repositorio de GitHub dotnet/templating</span><span class="sxs-lookup"><span data-stu-id="fe245-221">dotnet/templating GitHub repo Wiki</span></span>](https://github.com/dotnet/templating/wiki)  
[<span data-ttu-id="fe245-222">Repositorio de GitHub dotnet/dotnet-template-samples</span><span class="sxs-lookup"><span data-stu-id="fe245-222">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)  
<span data-ttu-id="fe245-223">[How to create your own templates for dotnet new](https://blogs.msdn.microsoft.com/dotnet/2017/04/02/how-to-create-your-own-templates-for-dotnet-new/) (Cómo crear sus propias plantillas para dotnet new)</span><span class="sxs-lookup"><span data-stu-id="fe245-223">[How to create your own templates for dotnet new](https://blogs.msdn.microsoft.com/dotnet/2017/04/02/how-to-create-your-own-templates-for-dotnet-new/)</span></span>  
[<span data-ttu-id="fe245-224">Esquema *template.json* en el Almacenamiento del esquema JSON</span><span class="sxs-lookup"><span data-stu-id="fe245-224">*template.json* schema at the JSON Schema Store</span></span>](http://json.schemastore.org/template)  

