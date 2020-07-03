---
title: 'Instalación y administración de plantillas de SDK: .NET Core'
description: Obtenga información sobre cómo instalar plantillas de .NET Core en Windows, Linux y macOS.
author: adegeo
ms.author: adegeo
ms.date: 04/24/2020
zone_pivot_groups: operating-systems-set-one
no-loc:
- dotnet new
- dotnet nuget add source
ms.openlocfilehash: 09acae1409eb0492be10bd3a61b14da5be57c6c7
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324490"
---
# <a name="manage-net-project-and-item-templates"></a><span data-ttu-id="2b488-103">Administración de plantillas de proyectos y elementos de .NET</span><span class="sxs-lookup"><span data-stu-id="2b488-103">Manage .NET project and item templates</span></span>

<span data-ttu-id="2b488-104">.NET Core proporciona un sistema de plantillas que permite a los usuarios instalar o desinstalar plantillas de NuGet, un archivo de paquete NuGet o un directorio del sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="2b488-104">.NET Core provides a template system that enables users to install or uninstall templates from NuGet, a NuGet package file, or a file system directory.</span></span> <span data-ttu-id="2b488-105">En este artículo se describe cómo administrar plantillas de .NET Core a través de la CLI del SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2b488-105">This article describes how to manage .NET Core templates through the .NET Core SDK CLI.</span></span>

<span data-ttu-id="2b488-106">Para obtener más información sobre la creación de plantillas, consulte [Tutorial: Creación de plantillas](../tutorials/cli-templates-create-item-template.md).</span><span class="sxs-lookup"><span data-stu-id="2b488-106">For more information about creating templates, see [Tutorial: Create templates](../tutorials/cli-templates-create-item-template.md).</span></span>

## <a name="install-template"></a><span data-ttu-id="2b488-107">Instalación de plantillas</span><span class="sxs-lookup"><span data-stu-id="2b488-107">Install template</span></span>

<span data-ttu-id="2b488-108">Las plantillas se instalan mediante el comando [dotnet new](../tools/dotnet-new.md) del SDK con el parámetro `-i`.</span><span class="sxs-lookup"><span data-stu-id="2b488-108">Templates are installed through the [dotnet new](../tools/dotnet-new.md) SDK command with the `-i` parameter.</span></span> <span data-ttu-id="2b488-109">Puede proporcionar el identificador de paquete NuGet de una plantilla o una carpeta que contenga los archivos de plantilla.</span><span class="sxs-lookup"><span data-stu-id="2b488-109">You can either provide the NuGet package identifier of a template, or a folder that contains the template files.</span></span>

### <a name="nuget-hosted-package"></a><span data-ttu-id="2b488-110">Paquete hospedado en NuGet</span><span class="sxs-lookup"><span data-stu-id="2b488-110">NuGet hosted package</span></span>

<span data-ttu-id="2b488-111">Las plantillas de la CLI de .NET se cargan en [NuGet](https://www.nuget.org/) para una distribución amplia.</span><span class="sxs-lookup"><span data-stu-id="2b488-111">.NET CLI templates are uploaded to [NuGet](https://www.nuget.org/) for wide distribution.</span></span> <span data-ttu-id="2b488-112">Las plantillas también se pueden instalar desde una fuente privada.</span><span class="sxs-lookup"><span data-stu-id="2b488-112">Templates can also be installed from a private feed.</span></span> <span data-ttu-id="2b488-113">En lugar de cargar una plantilla en una fuente de NuGet, los archivos de plantilla de *nupkg* se pueden distribuir e instalar manualmente, tal como se describe en la sección [Paquete NuGet local](#local-nuget-package).</span><span class="sxs-lookup"><span data-stu-id="2b488-113">Instead of uploading a template to a NuGet feed, *nupkg* template files can be distributed and manually installed, as described in the [Local NuGet package](#local-nuget-package) section.</span></span>

<span data-ttu-id="2b488-114">Para obtener más información sobre cómo configurar las fuentes de NuGet, vea [dotnet nuget add source](../tools/dotnet-nuget-add-source.md).</span><span class="sxs-lookup"><span data-stu-id="2b488-114">For more information about configuring NuGet feeds, see [dotnet nuget add source](../tools/dotnet-nuget-add-source.md).</span></span>

<span data-ttu-id="2b488-115">Para instalar un paquete de plantillas desde la fuente de NuGet predeterminada, use el comando `dotnet new -i {package-id}`:</span><span class="sxs-lookup"><span data-stu-id="2b488-115">To install a template pack from the default NuGet feed, use the `dotnet new -i {package-id}` command:</span></span>

```dotnetcli
dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates
```

<span data-ttu-id="2b488-116">Para instalar un paquete de plantillas desde la fuente de NuGet predeterminada con una versión específica, use el comando `dotnet new -i {package-id}::{version}`:</span><span class="sxs-lookup"><span data-stu-id="2b488-116">To install a template pack from the default NuGet feed with a specific version, use the `dotnet new -i {package-id}::{version}` command:</span></span>

```dotnetcli
dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.2.6
```

### <a name="local-nuget-package"></a><span data-ttu-id="2b488-117">Paquete NuGet local</span><span class="sxs-lookup"><span data-stu-id="2b488-117">Local NuGet package</span></span>

<span data-ttu-id="2b488-118">Cuando se crea un paquete de plantillas, se genera un archivo *nupkg*.</span><span class="sxs-lookup"><span data-stu-id="2b488-118">When a template pack is created, a *nupkg* file is generated.</span></span> <span data-ttu-id="2b488-119">Si tiene un archivo *nupkg* que contiene plantillas, puede instalarlo con el comando `dotnet new -i {path-to-package}`:</span><span class="sxs-lookup"><span data-stu-id="2b488-119">If you have a *nupkg* file containing templates, you can install it with the `dotnet new -i {path-to-package}` command:</span></span>

::: zone pivot="os-windows"

```dotnetcli
dotnet new -i c:\code\nuget-packages\Some.Templates.1.0.0.nupkg
```

::: zone-end

::: zone pivot="os-linux,os-macos"

```dotnetcli
dotnet new -i ~/code/nuget-packages/Some.Templates.1.0.0.nupkg
```

::: zone-end

### <a name="folder"></a><span data-ttu-id="2b488-120">Carpeta</span><span class="sxs-lookup"><span data-stu-id="2b488-120">Folder</span></span>

<span data-ttu-id="2b488-121">Como alternativa a la instalación de una plantilla desde un archivo *nupkg*, también puede instalar plantillas desde una carpeta directamente con el comando `dotnet new -i {folder-path}`.</span><span class="sxs-lookup"><span data-stu-id="2b488-121">As an alternative to installing template from a *nupkg* file, you can also install templates from a folder directly with the `dotnet new -i {folder-path}` command.</span></span> <span data-ttu-id="2b488-122">La carpeta especificada se trata como el identificador del paquete de plantillas para cualquier plantilla que se encuentre.</span><span class="sxs-lookup"><span data-stu-id="2b488-122">The folder specified is treated as the template pack identifier for any template found.</span></span> <span data-ttu-id="2b488-123">Se instalarán todas las plantillas que estén en la jerarquía de la carpeta especificada.</span><span class="sxs-lookup"><span data-stu-id="2b488-123">Any template found in the specified folder's hierarchy is installed.</span></span>

::: zone pivot="os-windows"

```dotnetcli
dotnet new -i c:\code\nuget-packages\some-folder\
```

::: zone-end

::: zone pivot="os-linux,os-macos"

```dotnetcli
dotnet new -i ~/code/nuget-packages/some-folder/
```

::: zone-end

<span data-ttu-id="2b488-124">La ruta `{folder-path}` especificada en el comando se convierte en el identificador del paquete de plantillas para todas las plantillas que se encuentren.</span><span class="sxs-lookup"><span data-stu-id="2b488-124">The `{folder-path}` specified on the command becomes the template pack identifier for all templates found.</span></span> <span data-ttu-id="2b488-125">Tal como se especifica en la sección [Enumeración de las plantillas](#list-templates), puede obtener una lista de las plantillas instaladas con el comando `dotnet new -u`.</span><span class="sxs-lookup"><span data-stu-id="2b488-125">As specified in the [List templates](#list-templates) section, you can get a list of templates installed with the `dotnet new -u` command.</span></span> <span data-ttu-id="2b488-126">En este ejemplo, el identificador del paquete de plantillas se muestra como la carpeta que se ha usado para la instalación:</span><span class="sxs-lookup"><span data-stu-id="2b488-126">In this example, the template pack identifier is shown as the folder used for install:</span></span>

::: zone pivot="os-windows"

```console
dotnet new -u
Template Instantiation Commands for .NET Core CLI

Currently installed items:

... cut to save space ...

  c:\code\nuget-packages\some-folder
    Templates:
      A Template Console Class (templateconsole) C#
      Project for some technology (contosoproject) C#
    Uninstall Command:
      dotnet new -u c:\code\nuget-packages\some-folder
```

::: zone-end

::: zone pivot="os-linux,os-macos"

```console
dotnet new -u
Template Instantiation Commands for .NET Core CLI

Currently installed items:

... cut to save space ...

  /home/username/code/templates
    Templates:
      A Template Console Class (templateconsole) C#
      Project for some technology (contosoproject) C#
    Uninstall Command:
      dotnet new -u /home/username/code/templates
```

::: zone-end

## <a name="uninstall-template"></a><span data-ttu-id="2b488-127">Desinstalación de plantillas</span><span class="sxs-lookup"><span data-stu-id="2b488-127">Uninstall template</span></span>

<span data-ttu-id="2b488-128">Las plantillas se desinstalan mediante el comando [dotnet new](../tools/dotnet-new.md) del SDK con el parámetro `-u`.</span><span class="sxs-lookup"><span data-stu-id="2b488-128">Templates are uninstalled through the [dotnet new](../tools/dotnet-new.md) SDK command with the `-u` parameter.</span></span> <span data-ttu-id="2b488-129">Puede proporcionar el identificador de paquete NuGet de una plantilla o una carpeta que contenga los archivos de plantilla.</span><span class="sxs-lookup"><span data-stu-id="2b488-129">You can either provide the NuGet package identifier of a template, or a folder that contains the template files.</span></span>

### <a name="nuget-package"></a><span data-ttu-id="2b488-130">Detección de</span><span class="sxs-lookup"><span data-stu-id="2b488-130">NuGet package</span></span>

<span data-ttu-id="2b488-131">Una vez instalado el paquete de plantillas de NuGet, ya sea desde una fuente de NuGet o un archivo *nupkg*, puede desinstalarlo mediante una referencia al identificador de paquete NuGet.</span><span class="sxs-lookup"><span data-stu-id="2b488-131">After a NuGet template pack is installed, either from a NuGet feed or a *nupkg* file, you can uninstall it by referencing the NuGet package identifier.</span></span>

<span data-ttu-id="2b488-132">Para desinstalar un paquete de plantillas, use el comando `dotnet new -u {package-id}`:</span><span class="sxs-lookup"><span data-stu-id="2b488-132">To uninstall a template pack, use the `dotnet new -u {package-id}` command:</span></span>

```dotnetcli
dotnet new -u Microsoft.DotNet.Web.Spa.ProjectTemplates
```

### <a name="folder"></a><span data-ttu-id="2b488-133">Carpeta</span><span class="sxs-lookup"><span data-stu-id="2b488-133">Folder</span></span>

<span data-ttu-id="2b488-134">Cuando las plantillas se instalan a través de una [ruta de acceso de carpeta](#folder), dicha ruta se convierte en el identificador del paquete de plantillas.</span><span class="sxs-lookup"><span data-stu-id="2b488-134">When templates are installed through a [folder path](#folder), the folder path becomes the template pack identifier.</span></span>

<span data-ttu-id="2b488-135">Para desinstalar un paquete de plantillas, use el comando `dotnet new -u {package-folder-path}`:</span><span class="sxs-lookup"><span data-stu-id="2b488-135">To uninstall a template pack, use the `dotnet new -u {package-folder-path}` command:</span></span>

::: zone pivot="os-windows"

```dotnetcli
dotnet new -u c:\code\nuget-packages\some-folder
```

::: zone-end

::: zone pivot="os-linux,os-macos"

```dotnetcli
dotnet new -u /home/username/code/templates
```

::: zone-end

## <a name="list-templates"></a><span data-ttu-id="2b488-136">Enumeración de plantillas</span><span class="sxs-lookup"><span data-stu-id="2b488-136">List templates</span></span>

<span data-ttu-id="2b488-137">Al usar el comando de desinstalación estándar sin un identificador de paquete, puede ver una lista de las plantillas instaladas, junto con el comando que desinstala cada plantilla.</span><span class="sxs-lookup"><span data-stu-id="2b488-137">By using the standard uninstall command without a package identifier, you can see a list of installed templates along with the command that uninstalls each template.</span></span>

```console
dotnet new -u
Template Instantiation Commands for .NET Core CLI

Currently installed items:

... cut to save space ...

  c:\code\nuget-packages\some-folder
    Templates:
      A Template Console Class (templateconsole) C#
      Project for some technology (contosoproject) C#
    Uninstall Command:
      dotnet new -u c:\code\nuget-packages\some-folder
```

## <a name="install-templates-from-other-sdks"></a><span data-ttu-id="2b488-138">Instalación de plantillas desde otros SDK</span><span class="sxs-lookup"><span data-stu-id="2b488-138">Install templates from other SDKs</span></span>

<span data-ttu-id="2b488-139">Si ha instalado cada versión del SDK secuencialmente (por ejemplo, si ha instalado el SDK 2.0, después el SDK 2.1, etc.), tendrá instaladas todas las plantillas del SDK.</span><span class="sxs-lookup"><span data-stu-id="2b488-139">If you've installed each version of the SDK sequentially, for example you installed SDK 2.0, then SDK 2.1, and so on, you'll have every SDK's templates installed.</span></span> <span data-ttu-id="2b488-140">Pero si comienza con una versión posterior del SDK, como la 3.1, solo se incluyen las plantillas para las [versiones LTS (compatibilidad a largo plazo)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), que en el momento de la versión 3.1 del SDK son SDK 2.1 y el SDK 3.1.</span><span class="sxs-lookup"><span data-stu-id="2b488-140">However, if you start with a later SDK version, like 3.1, only the templates for [LTS (long term support) releases](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) are included, which at the time of the SDK 3.1 release is SDK 2.1 and SDK 3.1.</span></span> <span data-ttu-id="2b488-141">No se incluyen las plantillas para ninguna otra versión.</span><span class="sxs-lookup"><span data-stu-id="2b488-141">Templates for any other release aren't included.</span></span>

<span data-ttu-id="2b488-142">Las plantillas de .NET Core están disponibles en NuGet y se pueden instalar como cualquier otra plantilla.</span><span class="sxs-lookup"><span data-stu-id="2b488-142">The .NET Core templates are available on NuGet, and you can install them like any other template.</span></span> <span data-ttu-id="2b488-143">Para obtener más información, consulte [Instalación del paquete hospedado en NuGet](#nuget-hosted-package).</span><span class="sxs-lookup"><span data-stu-id="2b488-143">For more information, see [Install NuGet hosted package](#nuget-hosted-package).</span></span>

| <span data-ttu-id="2b488-144">SDK</span><span class="sxs-lookup"><span data-stu-id="2b488-144">SDK</span></span>              | <span data-ttu-id="2b488-145">Identificador del paquete NuGet</span><span class="sxs-lookup"><span data-stu-id="2b488-145">NuGet Package Identifier</span></span>                                                                                                      |
|------------------|-------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="2b488-146">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="2b488-146">.NET Core 2.1</span></span>    | [`Microsoft.DotNet.Common.ProjectTemplates.2.1`](https://www.nuget.org/packages/Microsoft.DotNet.Common.ProjectTemplates.2.1) |
| <span data-ttu-id="2b488-147">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="2b488-147">.NET Core 2.2</span></span>    | [`Microsoft.DotNet.Common.ProjectTemplates.2.2`](https://www.nuget.org/packages/Microsoft.DotNet.Common.ProjectTemplates.2.2) |
| <span data-ttu-id="2b488-148">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="2b488-148">.NET Core 3.0</span></span>    | [`Microsoft.DotNet.Common.ProjectTemplates.3.0`](https://www.nuget.org/packages/Microsoft.DotNet.Common.ProjectTemplates.3.0) |
| <span data-ttu-id="2b488-149">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="2b488-149">.NET Core 3.1</span></span>    | [`Microsoft.DotNet.Common.ProjectTemplates.3.1`](https://www.nuget.org/packages/Microsoft.DotNet.Common.ProjectTemplates.3.1) |
| <span data-ttu-id="2b488-150">ASP.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="2b488-150">ASP.NET Core 2.1</span></span> | [`Microsoft.DotNet.Web.ProjectTemplates.2.1`](https://www.nuget.org/packages/Microsoft.DotNet.Web.ProjectTemplates.2.1)       |
| <span data-ttu-id="2b488-151">ASP.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="2b488-151">ASP.NET Core 2.2</span></span> | [`Microsoft.DotNet.Web.ProjectTemplates.2.2`](https://www.nuget.org/packages/Microsoft.DotNet.Web.ProjectTemplates.2.2)       |
| <span data-ttu-id="2b488-152">ASP.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="2b488-152">ASP.NET Core 3.0</span></span> | [`Microsoft.DotNet.Web.ProjectTemplates.3.0`](https://www.nuget.org/packages/Microsoft.DotNet.Web.ProjectTemplates.3.0)       |
| <span data-ttu-id="2b488-153">ASP.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="2b488-153">ASP.NET Core 3.1</span></span> | [`Microsoft.DotNet.Web.ProjectTemplates.3.1`](https://www.nuget.org/packages/Microsoft.DotNet.Web.ProjectTemplates.3.1)       |

<span data-ttu-id="2b488-154">Por ejemplo, el SDK de .NET Core incluye plantillas para una aplicación de consola que tiene como destino .NET Core 2.1 y .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="2b488-154">For example, the .NET Core SDK includes templates for a console app targeting .NET Core 2.1 and .NET Core 3.1.</span></span> <span data-ttu-id="2b488-155">Si quiere que el destino sea .NET Core 3.0, deberá instalar las plantillas de 3.0.</span><span class="sxs-lookup"><span data-stu-id="2b488-155">If you wanted to target .NET Core 3.0, you would need to install the 3.0 templates.</span></span>

01. <span data-ttu-id="2b488-156">Pruebe a crear una aplicación destinada a .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="2b488-156">Try creating an app that targets .NET Core 3.0.</span></span>

    ```dotnetcli
    dotnet new console --framework netcoreapp3.0
    ```

    <span data-ttu-id="2b488-157">Si ve un mensaje de error, debe instalar las plantillas.</span><span class="sxs-lookup"><span data-stu-id="2b488-157">If you see an error message, you need to install the templates.</span></span>

    > <span data-ttu-id="2b488-158">No se pudo encontrar una plantilla instalada que coincida con la entrada. Buscando en línea una que coincida…</span><span class="sxs-lookup"><span data-stu-id="2b488-158">Couldn't find an installed template that matches the input, searching online for one that does...</span></span>

01. <span data-ttu-id="2b488-159">Instale las plantillas de proyecto de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="2b488-159">Install the .NET Core 3.0 project templates.</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.DotNet.Common.ProjectTemplates.3.0
    ```

01. <span data-ttu-id="2b488-160">Pruebe a crear la aplicación otra vez.</span><span class="sxs-lookup"><span data-stu-id="2b488-160">Try creating the app a second time.</span></span>

    ```dotnetcli
    dotnet new console --framework netcoreapp3.0
    ```

    <span data-ttu-id="2b488-161">Debería ver un mensaje que indica que se ha creado el proyecto.</span><span class="sxs-lookup"><span data-stu-id="2b488-161">And you should see a message indicating the project was created.</span></span>

    > <span data-ttu-id="2b488-162">La plantilla "Console Application" se creó correctamente.</span><span class="sxs-lookup"><span data-stu-id="2b488-162">The template "Console Application" was created successfully.</span></span>
    >
    > <span data-ttu-id="2b488-163">Procesando acciones posteriores a la creación… Ejecutando "dotnet restore" en path-to-project-file.csproj… Determinando los proyectos que se van a restaurar… Restauración completada en 1,05 s para path-to-project-file.csproj.</span><span class="sxs-lookup"><span data-stu-id="2b488-163">Processing post-creation actions... Running 'dotnet restore' on path-to-project-file.csproj... Determining projects to restore... Restore completed in 1.05 sec for path-to-project-file.csproj.</span></span>
    >
    > <span data-ttu-id="2b488-164">Restauración correcta.</span><span class="sxs-lookup"><span data-stu-id="2b488-164">Restore succeeded.</span></span>

## <a name="see-also"></a><span data-ttu-id="2b488-165">Vea también</span><span class="sxs-lookup"><span data-stu-id="2b488-165">See also</span></span>

- <span data-ttu-id="2b488-166">[Tutorial: Creación de una plantilla de elemento](../tutorials/cli-templates-create-item-template.md).</span><span class="sxs-lookup"><span data-stu-id="2b488-166">[Tutorial: Create an item template](../tutorials/cli-templates-create-item-template.md)</span></span>
- [dotnet new](../tools/dotnet-new.md)
- [dotnet nuget add source](../tools/dotnet-nuget-add-source.md)
