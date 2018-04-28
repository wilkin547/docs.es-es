---
title: Creación de una plantilla personalizada para dotnet new
description: Obtenga información sobre cómo crear una plantilla personalizada para el comando dotnet new en este ameno tutorial.
author: guardrex
ms.author: mairaw
ms.date: 08/12/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.devlang: dotnet
ms.workload:
- dotnetcore
ms.openlocfilehash: 9ff58634daa6d51c10df9a3c9a1af0fd6420c69c
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="create-a-custom-template-for-dotnet-new"></a><span data-ttu-id="8fc1e-103">Creación de una plantilla personalizada para dotnet new</span><span class="sxs-lookup"><span data-stu-id="8fc1e-103">Create a custom template for dotnet new</span></span>

<span data-ttu-id="8fc1e-104">En este tutorial se le enseñará a hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8fc1e-104">This tutorial shows you how to:</span></span>

- <span data-ttu-id="8fc1e-105">Crear una plantilla básica a partir de un proyecto existente o un nuevo proyecto de aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="8fc1e-105">Create a basic template from an existing project or a new console app project.</span></span>
- <span data-ttu-id="8fc1e-106">Empaquetar la plantilla para su distribución en nuget.org o a partir de un archivo *nupkg* local.</span><span class="sxs-lookup"><span data-stu-id="8fc1e-106">Pack the template for distribution at nuget.org or from a local *nupkg* file.</span></span>
- <span data-ttu-id="8fc1e-107">Instalar la plantilla desde nuget.org, un archivo *nupkg* local o el sistema de archivos local.</span><span class="sxs-lookup"><span data-stu-id="8fc1e-107">Install the template from nuget.org, a local *nupkg* file, or the local file system.</span></span>
- <span data-ttu-id="8fc1e-108">Desinstalar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="8fc1e-108">Uninstall the template.</span></span>

<span data-ttu-id="8fc1e-109">Si prefiere hacer uso del tutorial con una muestra completa, descargue la [plantilla de proyecto de muestra](https://github.com/dotnet/dotnet-template-samples/tree/master/16-nuget-package).</span><span class="sxs-lookup"><span data-stu-id="8fc1e-109">If you prefer to proceed through the tutorial with a complete sample, download the [sample project template](https://github.com/dotnet/dotnet-template-samples/tree/master/16-nuget-package).</span></span> <span data-ttu-id="8fc1e-110">La plantilla de muestra está configurada para la distribución de NuGet.</span><span class="sxs-lookup"><span data-stu-id="8fc1e-110">The sample template is configured for NuGet distribution.</span></span>

<span data-ttu-id="8fc1e-111">Si quiere usar el ejemplo descargado con la distribución del sistema de archivos, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8fc1e-111">If you wish to use the downloaded sample with file system distribution, do the following:</span></span>

- <span data-ttu-id="8fc1e-112">Suba un nivel el contenido de la carpeta *content* de la muestra a la carpeta *GarciaSoftware.ConsoleTemplate.CSharp*.</span><span class="sxs-lookup"><span data-stu-id="8fc1e-112">Move the contents of the *content* folder of the sample up one level into the *GarciaSoftware.ConsoleTemplate.CSharp* folder.</span></span>
- <span data-ttu-id="8fc1e-113">Elimine la carpeta *content* vacía.</span><span class="sxs-lookup"><span data-stu-id="8fc1e-113">Delete the empty *content* folder.</span></span>
- <span data-ttu-id="8fc1e-114">Elimine el archivo *nuspec*.</span><span class="sxs-lookup"><span data-stu-id="8fc1e-114">Delete the *nuspec* file.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8fc1e-115">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="8fc1e-115">Prerequisites</span></span>

- <span data-ttu-id="8fc1e-116">Instalar el [SDK de .NET Core 2.0](https://www.microsoft.com/net/core) o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="8fc1e-116">Install the [.NET Core 2.0 SDK](https://www.microsoft.com/net/core) or later versions.</span></span>
- <span data-ttu-id="8fc1e-117">Leer el tema de referencia [Custom templates for dotnet new](../tools/custom-templates.md) (Plantillas personalizadas para dotnet new).</span><span class="sxs-lookup"><span data-stu-id="8fc1e-117">Read the reference topic [Custom templates for dotnet new](../tools/custom-templates.md).</span></span>

## <a name="create-a-template-from-a-project"></a><span data-ttu-id="8fc1e-118">Creación de una plantilla a partir de un proyecto</span><span class="sxs-lookup"><span data-stu-id="8fc1e-118">Create a template from a project</span></span>

<span data-ttu-id="8fc1e-119">Use un proyecto existente que se haya confirmado que se compila y se ejecuta, o cree un nuevo proyecto de aplicación de consola en una carpeta del disco duro.</span><span class="sxs-lookup"><span data-stu-id="8fc1e-119">Use an existing project that you've confirmed compiles and runs, or create a new console app project in a folder on your hard drive.</span></span> <span data-ttu-id="8fc1e-120">En este tutorial se da por hecho que el nombre de la carpeta de proyecto es *GarciaSoftware.ConsoleTemplate.CSharp* y que está almacenada en *Documentos\Plantillas* en el perfil del usuario.</span><span class="sxs-lookup"><span data-stu-id="8fc1e-120">This tutorial assumes that the name of the project folder is *GarciaSoftware.ConsoleTemplate.CSharp* stored at *Documents\Templates* in the user's profile.</span></span> <span data-ttu-id="8fc1e-121">El nombre de la plantilla de proyecto del tutorial tiene el formato *\<nombre de la compañía>.\<tipo de plantilla>.\<lenguaje de programación>*, pero puede asignar el nombre que quiera al proyecto y a la plantilla.</span><span class="sxs-lookup"><span data-stu-id="8fc1e-121">The tutorial project template name is in the format *\<Company Name>.\<Template Type>.\<Programming Language>*, but you're free to name your project and template anything you wish.</span></span>

1. <span data-ttu-id="8fc1e-122">Agregue una carpeta a la raíz del proyecto denominada *.template.config*.</span><span class="sxs-lookup"><span data-stu-id="8fc1e-122">Add a folder to the root of the project named *.template.config*.</span></span>
1. <span data-ttu-id="8fc1e-123">Dentro de la carpeta *.template.config*, cree un archivo *template.json* para configurar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="8fc1e-123">Inside the *.template.config* folder, create a *template.json* file to configure your template.</span></span> <span data-ttu-id="8fc1e-124">Para obtener más información y definiciones de miembros para el archivo *template.json*, vea el tema [Custom templates for dotnet new](../tools/custom-templates.md#templatejson) (Plantillas personalizadas para dotnet new) y el esquema [*template.json* en el almacenamiento del esquema JSON](http://json.schemastore.org/template).</span><span class="sxs-lookup"><span data-stu-id="8fc1e-124">For more information and member definitions for the *template.json* file, see the [Custom templates for dotnet new](../tools/custom-templates.md#templatejson) topic and the [*template.json* schema at the JSON Schema Store](http://json.schemastore.org/template).</span></span>

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

<span data-ttu-id="8fc1e-125">Ha terminado la plantilla.</span><span class="sxs-lookup"><span data-stu-id="8fc1e-125">The template is finished.</span></span> <span data-ttu-id="8fc1e-126">Una vez hecho esto, tiene dos opciones para la distribución de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="8fc1e-126">At this point, you have two options for template distribution.</span></span> <span data-ttu-id="8fc1e-127">Para continuar con este tutorial, elija uno de los dos pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="8fc1e-127">To continue this tutorial, choose one path or the other:</span></span>

1. <span data-ttu-id="8fc1e-128">[Distribución de NuGet](#use-nuget-distribution): instalación de la plantilla de NuGet o del paquete *nupkg* local y uso de la plantilla instalada.</span><span class="sxs-lookup"><span data-stu-id="8fc1e-128">[NuGet distribution](#use-nuget-distribution): install the template from NuGet or from the local *nupkg* file, and use the installed template.</span></span>
2. <span data-ttu-id="8fc1e-129">[Distribución del sistema de archivos](#use-file-system-distribution).</span><span class="sxs-lookup"><span data-stu-id="8fc1e-129">[File system distribution](#use-file-system-distribution).</span></span>

## <a name="use-nuget-distribution"></a><span data-ttu-id="8fc1e-130">Uso de la distribución de NuGet</span><span class="sxs-lookup"><span data-stu-id="8fc1e-130">Use NuGet Distribution</span></span>

### <a name="pack-the-template-into-a-nuget-package"></a><span data-ttu-id="8fc1e-131">Empaquetar la plantilla en un paquete de NuGet</span><span class="sxs-lookup"><span data-stu-id="8fc1e-131">Pack the template into a NuGet package</span></span>

1. <span data-ttu-id="8fc1e-132">Cree una carpeta para el paquete de NuGet.</span><span class="sxs-lookup"><span data-stu-id="8fc1e-132">Create a folder for the NuGet package.</span></span> <span data-ttu-id="8fc1e-133">Para el tutorial, se usa el nombre de carpeta *GarciaSoftware.ConsoleTemplate.CSharp*, y esta se crea dentro de una carpeta *Documentos\NuGetTemplates* del perfil del usuario.</span><span class="sxs-lookup"><span data-stu-id="8fc1e-133">For the tutorial, the folder name *GarciaSoftware.ConsoleTemplate.CSharp* is used, and the folder is created inside a *Documents\NuGetTemplates* folder in the user's profile.</span></span> <span data-ttu-id="8fc1e-134">Cree una carpeta denominada *content* dentro de la nueva carpeta de plantillas que contendrá los archivos del proyecto.</span><span class="sxs-lookup"><span data-stu-id="8fc1e-134">Create a folder named *content* inside of the new template folder to hold the project files.</span></span>
1. <span data-ttu-id="8fc1e-135">Copie el contenido de la carpeta del proyecto, junto con el archivo *.template.config/template.json*, en la carpeta *content* que ha creado.</span><span class="sxs-lookup"><span data-stu-id="8fc1e-135">Copy the contents of your project folder, together with its *.template.config/template.json* file, into the *content* folder you created.</span></span>
1. <span data-ttu-id="8fc1e-136">Junto a la carpeta *content*, agregue un [archivo *nuspec*](/nuget/create-packages/creating-a-package).</span><span class="sxs-lookup"><span data-stu-id="8fc1e-136">Next to the *content* folder, add a [*nuspec* file](/nuget/create-packages/creating-a-package).</span></span> <span data-ttu-id="8fc1e-137">El archivo nuspec es un archivo de manifiesto XML en el que se describe el contenido de un paquete y que controla el proceso de creación del paquete de NuGet.</span><span class="sxs-lookup"><span data-stu-id="8fc1e-137">The nuspec file is an XML manifest file that describes a package's contents and drives the process of creating the NuGet package.</span></span>
   
   ![Estructura de directorios en la que se muestra el diseño del paquete de NuGet](./media/create-custom-template/nugetdirectorylayout.png)

1. <span data-ttu-id="8fc1e-139">Dentro de un elemento **\<packageTypes>** en el archivo *nuspec*, incluya un elemento **\<packageType>** con un valor de atributo `name` de `Template`.</span><span class="sxs-lookup"><span data-stu-id="8fc1e-139">Inside of a **\<packageTypes>** element in the *nuspec* file, include a **\<packageType>** element with a `name` attribute value of `Template`.</span></span> <span data-ttu-id="8fc1e-140">Tanto la carpeta *content* como el archivo *nuspec* deben estar en el mismo directorio.</span><span class="sxs-lookup"><span data-stu-id="8fc1e-140">Both the *content* folder and the *nuspec* file should reside in the same directory.</span></span> <span data-ttu-id="8fc1e-141">En la tabla se muestran los elementos de archivo *nuspec* mínimos necesarios para generar una plantilla como un paquete NuGet.</span><span class="sxs-lookup"><span data-stu-id="8fc1e-141">The table shows the minimum *nuspec* file elements required to produce a template as a NuGet package.</span></span>

   | <span data-ttu-id="8fc1e-142">Elemento</span><span class="sxs-lookup"><span data-stu-id="8fc1e-142">Element</span></span>            | <span data-ttu-id="8fc1e-143">Tipo</span><span class="sxs-lookup"><span data-stu-id="8fc1e-143">Type</span></span>   | <span data-ttu-id="8fc1e-144">Description</span><span class="sxs-lookup"><span data-stu-id="8fc1e-144">Description</span></span> |
   | ------------------ | ------ | ----------- |
   | <span data-ttu-id="8fc1e-145">**\<authors>**</span><span class="sxs-lookup"><span data-stu-id="8fc1e-145">**\<authors>**</span></span>     | <span data-ttu-id="8fc1e-146">cadena</span><span class="sxs-lookup"><span data-stu-id="8fc1e-146">string</span></span> | <span data-ttu-id="8fc1e-147">Una lista separada por comas de los autores de los paquetes, que coinciden con los nombres de perfil de nuget.org. Estos se muestran en la galería de NuGet, en nuget.org, y se usan para hacer referencias cruzadas a paquetes de los mismos autores.</span><span class="sxs-lookup"><span data-stu-id="8fc1e-147">A comma-separated list of packages authors, matching the profile names on nuget.org. Authors are displayed in the NuGet Gallery on nuget.org and are used to cross-reference packages by the same authors.</span></span> |
   | <span data-ttu-id="8fc1e-148">**\<description>**</span><span class="sxs-lookup"><span data-stu-id="8fc1e-148">**\<description>**</span></span> | <span data-ttu-id="8fc1e-149">cadena</span><span class="sxs-lookup"><span data-stu-id="8fc1e-149">string</span></span> | <span data-ttu-id="8fc1e-150">Una descripción larga del paquete para su visualización en la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="8fc1e-150">A long description of the package for UI display.</span></span> |
   | <span data-ttu-id="8fc1e-151">**\<id>**</span><span class="sxs-lookup"><span data-stu-id="8fc1e-151">**\<id>**</span></span>          | <span data-ttu-id="8fc1e-152">cadena</span><span class="sxs-lookup"><span data-stu-id="8fc1e-152">string</span></span> | <span data-ttu-id="8fc1e-153">El identificador del paquete que no distingue entre mayúsculas y minúsculas, que debe ser único en nuget.org o en la galería en la que se mantendrá el paquete.</span><span class="sxs-lookup"><span data-stu-id="8fc1e-153">The case-insensitive package identifier, which must be unique across nuget.org or whatever gallery the package will reside in.</span></span> <span data-ttu-id="8fc1e-154">Los id. no pueden contener espacios ni caracteres no válidos para una URL y normalmente seguirán las reglas de espacios de nombres de .NET.</span><span class="sxs-lookup"><span data-stu-id="8fc1e-154">IDs may not contain spaces or characters that are not valid for a URL and generally follow .NET namespace rules.</span></span> <span data-ttu-id="8fc1e-155">Vea [Choosing a unique package identifier and setting the version number](/nuget/create-packages/creating-a-package#choosing-a-unique-package-identifier-and-setting-the-version-number) (Elección de un identificador de paquete único y establecimiento del número de versión) para obtener instrucciones.</span><span class="sxs-lookup"><span data-stu-id="8fc1e-155">See [Choosing a unique package identifier and setting the version number](/nuget/create-packages/creating-a-package#choosing-a-unique-package-identifier-and-setting-the-version-number) for guidance.</span></span> |
   | <span data-ttu-id="8fc1e-156">**\<packageType>**</span><span class="sxs-lookup"><span data-stu-id="8fc1e-156">**\<packageType>**</span></span> | <span data-ttu-id="8fc1e-157">cadena</span><span class="sxs-lookup"><span data-stu-id="8fc1e-157">string</span></span> | <span data-ttu-id="8fc1e-158">Coloque este elemento dentro de un elemento **\<packageTypes>** entre los elementos **\<metadata>**.</span><span class="sxs-lookup"><span data-stu-id="8fc1e-158">Place this element inside a **\<packageTypes>** element among the **\<metadata>** elements.</span></span> <span data-ttu-id="8fc1e-159">Establezca el atributo `name` del elemento **\<packageType>** en `Template`.</span><span class="sxs-lookup"><span data-stu-id="8fc1e-159">Set the `name` attribute of the **\<packageType>** element to `Template`.</span></span> |
   | <span data-ttu-id="8fc1e-160">**\<version>**</span><span class="sxs-lookup"><span data-stu-id="8fc1e-160">**\<version>**</span></span>     | <span data-ttu-id="8fc1e-161">cadena</span><span class="sxs-lookup"><span data-stu-id="8fc1e-161">string</span></span> | <span data-ttu-id="8fc1e-162">La versión del paquete, siguiendo el patrón de mayor.menor.revisión.</span><span class="sxs-lookup"><span data-stu-id="8fc1e-162">The version of the package, following the major.minor.patch pattern.</span></span> <span data-ttu-id="8fc1e-163">Los números de versión pueden incluir un sufijo de versión preliminar, tal y como se describe en [Versiones preliminares](/nuget/create-packages/prerelease-packages#semantic-versioning).</span><span class="sxs-lookup"><span data-stu-id="8fc1e-163">Version numbers may include a pre-release suffix as described in [Pre-release versions](/nuget/create-packages/prerelease-packages#semantic-versioning).</span></span> |

   <span data-ttu-id="8fc1e-164">Consulte [.nuspec reference](/nuget/schema/nuspec) (Referencia de .nuspec) para ver el esquema de archivo de *nuspec* completo.</span><span class="sxs-lookup"><span data-stu-id="8fc1e-164">See the [.nuspec reference](/nuget/schema/nuspec) for the complete *nuspec* file schema.</span></span>

   <span data-ttu-id="8fc1e-165">El archivo *nuspec* para el tutorial se denomina *GarciaSoftware.ConsoleTemplate.CSharp.nuspec* e incluye el siguiente contenido:</span><span class="sxs-lookup"><span data-stu-id="8fc1e-165">The *nuspec* file for the tutorial is named *GarciaSoftware.ConsoleTemplate.CSharp.nuspec* and contains the following content:</span></span>

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

1. <span data-ttu-id="8fc1e-166">[Cree el paquete](/nuget/create-packages/creating-a-package#creating-the-package) mediante el comando `nuget pack <PATH_TO_NUSPEC_FILE>`.</span><span class="sxs-lookup"><span data-stu-id="8fc1e-166">[Create the package](/nuget/create-packages/creating-a-package#creating-the-package) using the `nuget pack <PATH_TO_NUSPEC_FILE>` command.</span></span> <span data-ttu-id="8fc1e-167">En el comando siguiente se da por supuesto que la carpeta que contiene los recursos de NuGet está en *C:\Users\\\<USUARIO>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp*.</span><span class="sxs-lookup"><span data-stu-id="8fc1e-167">The following command assumes that the folder that holds the NuGet assets is at *C:\Users\\\<USER>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp*.</span></span> <span data-ttu-id="8fc1e-168">En cambio, no importa dónde ponga la carpeta en el sistema, el comando `nuget pack` acepta la ruta de acceso al archivo *nuspec*:</span><span class="sxs-lookup"><span data-stu-id="8fc1e-168">But wherever you place the folder on your system, the `nuget pack` command accepts the path to the *nuspec* file:</span></span>

   ```console
   nuget pack C:\Users\<USER>\Documents\NuGetTemplates\GarciaSoftware.ConsoleTemplate.CSharp\GarciaSoftware.ConsoleTemplate.CSharp.nuspec
   ```

### <a name="publishing-the-package-to-nugetorg"></a><span data-ttu-id="8fc1e-169">Publicación del paquete en nuget.org</span><span class="sxs-lookup"><span data-stu-id="8fc1e-169">Publishing the package to nuget.org</span></span>

<span data-ttu-id="8fc1e-170">Para publicar un paquete de NuGet, siga las instrucciones del tema [Create and publish a package](/nuget/quickstart/create-and-publish-a-package#publish-the-package) (Crear y publicar un paquete).</span><span class="sxs-lookup"><span data-stu-id="8fc1e-170">To publish a NuGet package, follow the instructions in the [Create and publish a package](/nuget/quickstart/create-and-publish-a-package#publish-the-package) topic.</span></span> <span data-ttu-id="8fc1e-171">En cambio, se recomienda que no publique la plantilla de tutorial en NuGet, ya que no se puede eliminar una vez publicada, solo se puede eliminar de la lista.</span><span class="sxs-lookup"><span data-stu-id="8fc1e-171">However, we recommend that you don't publish the tutorial template to NuGet as it can never be deleted once published, only delisted.</span></span> <span data-ttu-id="8fc1e-172">Ahora que tiene el paquete de NuGet en forma de un archivo *nupkg*, le recomendamos que siga estas instrucciones para instalar la plantilla directamente a partir del archivo *nupkg* local.</span><span class="sxs-lookup"><span data-stu-id="8fc1e-172">Now that you have the NuGet package in the form of a *nupkg* file, we suggest that you follow the instructions below to install the template directly from the local *nupkg* file.</span></span>

### <a name="install-the-template-from-a-nuget-package"></a><span data-ttu-id="8fc1e-173">Instalación de la plantilla a partir de un paquete de NuGet</span><span class="sxs-lookup"><span data-stu-id="8fc1e-173">Install the template from a NuGet package</span></span>

#### <a name="install-the-template-from-the-local-nupkg-file"></a><span data-ttu-id="8fc1e-174">Instalación de la plantilla a partir del archivo *nupkg* local</span><span class="sxs-lookup"><span data-stu-id="8fc1e-174">Install the template from the local *nupkg* file</span></span>

<span data-ttu-id="8fc1e-175">Para instalar la plantilla a partir del archivo *nupkg* que ha creado, use el comando `dotnet new` con la opción `-i|--install` y proporcione la ruta de acceso al archivo *nupkg*:</span><span class="sxs-lookup"><span data-stu-id="8fc1e-175">To install the template from the *nupkg* file that you produced, use the `dotnet new` command with the `-i|--install` option and provide the path to the *nupkg* file:</span></span>

```console
dotnet new -i C:\Users\<USER>\GarciaSoftware.ConsoleTemplate.CSharp.1.0.0.nupkg
```

#### <a name="install-the-template-from-a-nuget-package-stored-at-nugetorg"></a><span data-ttu-id="8fc1e-176">Instalación de la plantilla a partir de un paquete de NuGet almacenado en nuget.org</span><span class="sxs-lookup"><span data-stu-id="8fc1e-176">Install the template from a NuGet package stored at nuget.org</span></span>

<span data-ttu-id="8fc1e-177">Si quiere volver a instalar una plantilla a partir de un paquete de NuGet almacenado en nuget.org, use el comando `dotnet new` con la opción `-i|--install` y proporcione el nombre del paquete de NuGet:</span><span class="sxs-lookup"><span data-stu-id="8fc1e-177">If you wish to install a template from a NuGet package stored at nuget.org, use the `dotnet new` command with the `-i|--install` option and supply the name of the NuGet package:</span></span>

```console
dotnet new -i GarciaSoftware.ConsoleTemplate.CSharp
```

> [!NOTE]
> <span data-ttu-id="8fc1e-178">El ejemplo solamente sirve de demostración.</span><span class="sxs-lookup"><span data-stu-id="8fc1e-178">The example is for demonstration purposes only.</span></span> <span data-ttu-id="8fc1e-179">No hay ningún paquete de NuGet denominado `GarciaSoftware.ConsoleTemplate.CSharp` en nuget.org y no se recomienda que publique y consuma las plantillas de prueba de NuGet.</span><span class="sxs-lookup"><span data-stu-id="8fc1e-179">There isn't a `GarciaSoftware.ConsoleTemplate.CSharp` NuGet package at nuget.org, and we don't recommend that you publish and consume test templates from NuGet.</span></span> <span data-ttu-id="8fc1e-180">Si ejecuta el comando, no se instala ninguna plantilla.</span><span class="sxs-lookup"><span data-stu-id="8fc1e-180">If you run the command, no template is installed.</span></span> <span data-ttu-id="8fc1e-181">En cambio, puede instalar una plantilla que no se haya publicado en nuget.org si hace referencia al archivo *nupkg* directamente en el sistema de archivos local, tal y como se muestra en la sección anterior [Instalación de la plantilla a partir de un archivo nupkg local](#install-the-template-from-the-local-nupkg-file).</span><span class="sxs-lookup"><span data-stu-id="8fc1e-181">However, you can install a template that hasn't been published to nuget.org by referencing the *nupkg* file directly on your local file system as shown in the previous section [Install the template from the local nupkg file](#install-the-template-from-the-local-nupkg-file).</span></span>

<span data-ttu-id="8fc1e-182">Si quiere ver un ejemplo de cómo instalar una plantilla de un paquete en nuget.org, puede usar la [plantilla de NUnit 3 para dotnet-new](https://www.nuget.org/packages/NUnit3.DotNetNew.Template/).</span><span class="sxs-lookup"><span data-stu-id="8fc1e-182">If you'd like a live example of how to install a template from a package at nuget.org, you can use the [NUnit 3 template for dotnet-new](https://www.nuget.org/packages/NUnit3.DotNetNew.Template/).</span></span> <span data-ttu-id="8fc1e-183">Esta plantilla configura un proyecto para usar las pruebas unitarias de NUnit.</span><span class="sxs-lookup"><span data-stu-id="8fc1e-183">This template sets up a project to use NUnit unit testing.</span></span> <span data-ttu-id="8fc1e-184">Use el comando siguiente para instalarla:</span><span class="sxs-lookup"><span data-stu-id="8fc1e-184">Use the following command to install it:</span></span>

```console
dotnet new -i NUnit3.DotNetNew.Template
```

<span data-ttu-id="8fc1e-185">Al enumerar las plantillas con `dotnet new -l`, verá el *proyecto de prueba de NUnit 3* con el breve nombre de *nunit* en la lista de plantillas.</span><span class="sxs-lookup"><span data-stu-id="8fc1e-185">When you list the templates with `dotnet new -l`, you see the *NUnit 3 Test Project* with a short name of *nunit* in the template list.</span></span> <span data-ttu-id="8fc1e-186">Está listo para usar la plantilla en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="8fc1e-186">You're ready to use the template in the next section.</span></span>

![Ventana de consola en la que muestra la plantilla de NUnit junto a otras plantillas instaladas](./media/create-custom-template/nunit1.png)

### <a name="create-a-project-from-the-template"></a><span data-ttu-id="8fc1e-188">Creación de un proyecto a partir de la plantilla</span><span class="sxs-lookup"><span data-stu-id="8fc1e-188">Create a project from the template</span></span>

<span data-ttu-id="8fc1e-189">Después de instalar la plantilla desde NuGet, ejecute el comando `dotnet new <TEMPLATE>` desde el directorio donde quiera que se coloque la salida del motor de plantillas (a menos que esté usando la opción `-o|--output` para especificar un directorio específico) para usarla.</span><span class="sxs-lookup"><span data-stu-id="8fc1e-189">After the template is installed from NuGet, use the template by executing the `dotnet new <TEMPLATE>` command from the directory where you want to the template engine's output placed (unless you're using the `-o|--output` option to specify a specific directory).</span></span> <span data-ttu-id="8fc1e-190">Para obtener más información, consulte las [Opciones de `dotnet new`](~/docs/core/tools/dotnet-new.md#options).</span><span class="sxs-lookup"><span data-stu-id="8fc1e-190">For more information, see [`dotnet new` Options](~/docs/core/tools/dotnet-new.md#options).</span></span> <span data-ttu-id="8fc1e-191">Proporcione el nombre breve de la plantilla directamente junto al comando `dotnet new`.</span><span class="sxs-lookup"><span data-stu-id="8fc1e-191">Supply the template's short name directly to the `dotnet new` command.</span></span> <span data-ttu-id="8fc1e-192">Para crear un proyecto a partir de la plantilla de NUnit, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="8fc1e-192">To create a project from the NUnit template, run the following command:</span></span>

```console
dotnet new nunit
```

<span data-ttu-id="8fc1e-193">En la consola se muestra que se crea el proyecto y que se restauran los paquetes de este.</span><span class="sxs-lookup"><span data-stu-id="8fc1e-193">The console shows that the project is created and that the project's packages are restored.</span></span> <span data-ttu-id="8fc1e-194">Después de ejecutar el comando, el proyecto estará listo para usarse.</span><span class="sxs-lookup"><span data-stu-id="8fc1e-194">After the command is run, the project is ready for use.</span></span>

![Ventana de consola en la que se muestra la salida del comando dotnet new en el proceso de creación del proyecto de NUnit y de restauración de las dependencias del proyecto](./media/create-custom-template/nunit2.png)

### <a name="to-uninstall-a-template-from-a-nuget-package-stored-at-nugetorg"></a><span data-ttu-id="8fc1e-196">Desinstalación de una plantilla de un paquete de NuGet almacenado en nuget.org</span><span class="sxs-lookup"><span data-stu-id="8fc1e-196">To uninstall a template from a NuGet package stored at nuget.org</span></span>

```console
dotnet new -u GarciaSoftware.ConsoleTemplate.CSharp
```

> [!NOTE]
> <span data-ttu-id="8fc1e-197">El ejemplo solamente sirve de demostración.</span><span class="sxs-lookup"><span data-stu-id="8fc1e-197">The example is for demonstration purposes only.</span></span> <span data-ttu-id="8fc1e-198">No hay ningún paquete de NuGet denominado `GarciaSoftware.ConsoleTemplate.CSharp` en nuget.org ni instalado con el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="8fc1e-198">There isn't a `GarciaSoftware.ConsoleTemplate.CSharp` NuGet package at nuget.org or installed with the .NET Core SDK.</span></span> <span data-ttu-id="8fc1e-199">Si ejecuta el comando, no se desinstalará ninguna plantilla ni paquete y se mostrará la siguiente excepción:</span><span class="sxs-lookup"><span data-stu-id="8fc1e-199">If you run the command, no package/template is uninstalled and you receive the following exception:</span></span>
> 
> > <span data-ttu-id="8fc1e-200">Could not find something to uninstall called 'GarciaSoftware.ConsoleTemplate.CSharp' (No se ha encontrado nada denominado “GarciaSoftware.ConsoleTemplate.CSharp” para desinstalarlo).</span><span class="sxs-lookup"><span data-stu-id="8fc1e-200">Could not find something to uninstall called 'GarciaSoftware.ConsoleTemplate.CSharp'.</span></span>

<span data-ttu-id="8fc1e-201">Si ha instalado la [plantilla de NUnit 3 para dotnet-new](https://www.nuget.org/packages/NUnit3.DotNetNew.Template/) y quiere desinstalarla, use el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="8fc1e-201">If you installed the [NUnit 3 template for dotnet-new](https://www.nuget.org/packages/NUnit3.DotNetNew.Template/) and wish to uninstall it, use the following command:</span></span>

```console
dotnet new -u NUnit3.DotNetNew.Template
```

### <a name="uninstall-the-template-from-a-local-nupkg-file"></a><span data-ttu-id="8fc1e-202">Desinstalación de la plantilla de un paquete de nupkg local</span><span class="sxs-lookup"><span data-stu-id="8fc1e-202">Uninstall the template from a local nupkg file</span></span>

<span data-ttu-id="8fc1e-203">Si quiere desinstalar la plantilla, no intente usar la ruta de acceso al archivo *nupkg*.</span><span class="sxs-lookup"><span data-stu-id="8fc1e-203">When you wish to uninstall the template, don't attempt to use the path to the *nupkg* file.</span></span> <span data-ttu-id="8fc1e-204">*Si intenta desinstalar una plantilla mediante `dotnet new -u <PATH_TO_NUPKG_FILE>`, se produce un error.*</span><span class="sxs-lookup"><span data-stu-id="8fc1e-204">*Attempting to uninstall a template using `dotnet new -u <PATH_TO_NUPKG_FILE>` fails.*</span></span> <span data-ttu-id="8fc1e-205">Haga referencia al paquete por su `id`:</span><span class="sxs-lookup"><span data-stu-id="8fc1e-205">Reference the package by its `id`:</span></span>

```console
dotnet new -u GarciaSoftware.ConsoleTemplate.CSharp.1.0.0
```

## <a name="use-file-system-distribution"></a><span data-ttu-id="8fc1e-206">Uso de la distribución del sistema de archivos</span><span class="sxs-lookup"><span data-stu-id="8fc1e-206">Use file system distribution</span></span>

<span data-ttu-id="8fc1e-207">Para distribuir la plantilla, coloque la carpeta de plantillas de proyecto en una ubicación accesible para los usuarios de la red.</span><span class="sxs-lookup"><span data-stu-id="8fc1e-207">To distribute the template, place the project template folder in a location accessible to users on your network.</span></span> <span data-ttu-id="8fc1e-208">Use el comando `dotnet new` con la opción `-i|--install` y especifique la ruta de acceso a la carpeta de plantillas (la carpeta del proyecto que contiene el proyecto y la carpeta *.template.config*).</span><span class="sxs-lookup"><span data-stu-id="8fc1e-208">Use the `dotnet new` command with the `-i|--install` option and specify the path to the template folder (the project folder containing the project and the *.template.config* folder).</span></span>

<span data-ttu-id="8fc1e-209">En este tutorial se da por supuesto que la plantilla de proyecto se almacena en la carpeta *Documents/Templates* del perfil de usuario.</span><span class="sxs-lookup"><span data-stu-id="8fc1e-209">The tutorial assumes the project template is stored in the *Documents/Templates* folder of the user's profile.</span></span> <span data-ttu-id="8fc1e-210">Desde esa ubicación, instale la plantilla con el comando siguiente, pero reemplazando \<USER> con el nombre del perfil de usuario:</span><span class="sxs-lookup"><span data-stu-id="8fc1e-210">From that location, install the template with the following command replacing \<USER> with the user's profile name:</span></span>

```console
dotnet new -i C:\Users\<USER>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp
```

### <a name="create-a-project-from-the-template"></a><span data-ttu-id="8fc1e-211">Creación de un proyecto a partir de la plantilla</span><span class="sxs-lookup"><span data-stu-id="8fc1e-211">Create a project from the template</span></span>

<span data-ttu-id="8fc1e-212">Después de instalar la plantilla a partir del sistema de archivos, ejecute el comando `dotnet new <TEMPLATE>` desde el directorio donde quiera que se coloque la salida del motor de plantillas (a menos que esté usando la opción `-o|--output` para especificar un directorio específico) para usarla.</span><span class="sxs-lookup"><span data-stu-id="8fc1e-212">After the template is installed from the file system, use the template by executing the `dotnet new <TEMPLATE>` command from the directory where you want to the template engine's output placed (unless you're using the `-o|--output` option to specify a specific directory).</span></span> <span data-ttu-id="8fc1e-213">Para obtener más información, consulte las [Opciones de `dotnet new`](~/docs/core/tools/dotnet-new.md#options).</span><span class="sxs-lookup"><span data-stu-id="8fc1e-213">For more information, see [`dotnet new` Options](~/docs/core/tools/dotnet-new.md#options).</span></span> <span data-ttu-id="8fc1e-214">Proporcione el nombre breve de la plantilla directamente junto al comando `dotnet new`.</span><span class="sxs-lookup"><span data-stu-id="8fc1e-214">Supply the template's short name directly to the `dotnet new` command.</span></span>

<span data-ttu-id="8fc1e-215">Desde una nueva carpeta de proyecto creada en *C:\Users\\\<USUARIO>\Documentos\Proyectos\MyConsoleApp*, cree un proyecto a partir de la plantilla `garciaconsole`:</span><span class="sxs-lookup"><span data-stu-id="8fc1e-215">From a new project folder created at *C:\Users\\\<USER>\Documents\Projects\MyConsoleApp*, create a project from the `garciaconsole` template:</span></span>

```console
dotnet new garciaconsole
```

### <a name="uninstall-the-template"></a><span data-ttu-id="8fc1e-216">Desinstalación de la plantilla</span><span class="sxs-lookup"><span data-stu-id="8fc1e-216">Uninstall the template</span></span>

<span data-ttu-id="8fc1e-217">Si ha creado la plantilla en el sistema de archivos local en*C:\Users\\\<USUARIO>\Documentos\Plantillas\GarciaSoftware.ConsoleTemplate.CSharp*, desinstálela con el modificador `-u|--uninstall` e indicando la ruta de acceso a la carpeta de la plantilla:</span><span class="sxs-lookup"><span data-stu-id="8fc1e-217">If you created the template on your local file system at *C:\Users\\\<USER>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp*, uninstall it with the `-u|--uninstall` switch and the path to the template folder:</span></span>

```console
dotnet new -u C:\Users\<USER>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp
```

> [!NOTE]
> <span data-ttu-id="8fc1e-218">Para desinstalar la plantilla del sistema de archivos local, debe usar el nombre completo de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="8fc1e-218">To uninstall the template from your local file system, you need to fully qualify the path.</span></span> <span data-ttu-id="8fc1e-219">Por ejemplo, *C:\Users\\\<USUARIO>\Documentos\Plantillas\GarciaSoftware.ConsoleTemplate.CSharp* funcionará, pero *./GarciaSoftware.ConsoleTemplate.CSharp* desde la carpeta contenedora no lo hará.</span><span class="sxs-lookup"><span data-stu-id="8fc1e-219">For example, *C:\Users\\\<USER>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="8fc1e-220">Además, no debe incluir una barra diagonal para finalizar el directorio en la ruta de acceso a la plantilla.</span><span class="sxs-lookup"><span data-stu-id="8fc1e-220">Additionally, do not include a final terminating directory slash on your template path.</span></span>

## <a name="see-also"></a><span data-ttu-id="8fc1e-221">Vea también</span><span class="sxs-lookup"><span data-stu-id="8fc1e-221">See also</span></span>

[<span data-ttu-id="8fc1e-222">Wiki del repositorio de GitHub dotnet/templating</span><span class="sxs-lookup"><span data-stu-id="8fc1e-222">dotnet/templating GitHub repo Wiki</span></span>](https://github.com/dotnet/templating/wiki)  
[<span data-ttu-id="8fc1e-223">Repositorio de GitHub dotnet/dotnet-template-samples</span><span class="sxs-lookup"><span data-stu-id="8fc1e-223">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)  
<span data-ttu-id="8fc1e-224">[How to create your own templates for dotnet new](https://blogs.msdn.microsoft.com/dotnet/2017/04/02/how-to-create-your-own-templates-for-dotnet-new/) (Cómo crear sus propias plantillas para dotnet new)</span><span class="sxs-lookup"><span data-stu-id="8fc1e-224">[How to create your own templates for dotnet new](https://blogs.msdn.microsoft.com/dotnet/2017/04/02/how-to-create-your-own-templates-for-dotnet-new/)</span></span>  
[<span data-ttu-id="8fc1e-225">Esquema *template.json* en el Almacenamiento del esquema JSON</span><span class="sxs-lookup"><span data-stu-id="8fc1e-225">*template.json* schema at the JSON Schema Store</span></span>](http://json.schemastore.org/template)  
