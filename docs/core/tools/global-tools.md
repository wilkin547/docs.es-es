---
title: Herramientas globales de .NET Core
description: Información general sobre las herramientas globales de .NET Core y los comandos de CLI de .NET Core que hay disponibles para ellas.
author: KathleenDollard
ms.date: 05/29/2018
ms.custom: seodec18
ms.openlocfilehash: 40a0aabcf523e8dac9a3ad226064bbb3c1b3ce5b
ms.sourcegitcommit: 8b8dd14dde727026fd0b6ead1ec1df2e9d747a48
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "71332018"
---
# <a name="net-core-global-tools-overview"></a><span data-ttu-id="6c303-103">Información general sobre las herramientas globales de .NET Core</span><span class="sxs-lookup"><span data-stu-id="6c303-103">.NET Core Global Tools overview</span></span>

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

<span data-ttu-id="6c303-104">Una herramienta global de .NET Core es un paquete especial de NuGet que contiene una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="6c303-104">A .NET Core Global Tool is a special NuGet package that contains a console application.</span></span> <span data-ttu-id="6c303-105">Las herramientas globales se pueden instalar en una ubicación predeterminada del equipo incluida en la variable de entorno PATH, o bien en una ubicación personalizada.</span><span class="sxs-lookup"><span data-stu-id="6c303-105">A Global Tool can be installed on your machine on a default location that is included in the PATH environment variable or on a custom location.</span></span>

<span data-ttu-id="6c303-106">Si quiere usar una herramienta global de .NET Core:</span><span class="sxs-lookup"><span data-stu-id="6c303-106">If you want to use a .NET Core Global Tool:</span></span>

* <span data-ttu-id="6c303-107">Busque información sobre la herramienta (normalmente un sitio web o página de GitHub).</span><span class="sxs-lookup"><span data-stu-id="6c303-107">Find information about the tool (usually a website or GitHub page).</span></span>
* <span data-ttu-id="6c303-108">Compruebe el autor y las estadísticas en la página principal de la fuente (normalmente NuGet.org).</span><span class="sxs-lookup"><span data-stu-id="6c303-108">Check the author and statistics in the home for the feed (usually NuGet.org).</span></span>
* <span data-ttu-id="6c303-109">Instale la herramienta.</span><span class="sxs-lookup"><span data-stu-id="6c303-109">Install the tool.</span></span>
* <span data-ttu-id="6c303-110">Llame a la herramienta.</span><span class="sxs-lookup"><span data-stu-id="6c303-110">Call the tool.</span></span>
* <span data-ttu-id="6c303-111">Actualice la herramienta.</span><span class="sxs-lookup"><span data-stu-id="6c303-111">Update the tool.</span></span>
* <span data-ttu-id="6c303-112">Desinstale la herramienta.</span><span class="sxs-lookup"><span data-stu-id="6c303-112">Uninstall the tool.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6c303-113">Las herramientas globales de .NET Core aparecen en su ruta de acceso y se ejecutan con plena confianza.</span><span class="sxs-lookup"><span data-stu-id="6c303-113">.NET Core Global Tools appear on your path and run in full trust.</span></span> <span data-ttu-id="6c303-114">No instale herramientas globales de .NET Core a menos que confíe en el autor.</span><span class="sxs-lookup"><span data-stu-id="6c303-114">Do not install .NET Core Global Tools unless you trust the author.</span></span>

## <a name="find-a-net-core-global-tool"></a><span data-ttu-id="6c303-115">Buscar una herramienta global de .NET Core</span><span class="sxs-lookup"><span data-stu-id="6c303-115">Find a .NET Core Global Tool</span></span>

<span data-ttu-id="6c303-116">Actualmente, no hay una característica que permita buscar herramientas globales en la interfaz de línea de comandos (CLI) de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6c303-116">Currently, there isn't a Global Tool search feature in the .NET Core Command-line Interface (CLI).</span></span>

<span data-ttu-id="6c303-117">Aunque estas herramientas se pueden encontrar en [NuGet](https://www.nuget.org),</span><span class="sxs-lookup"><span data-stu-id="6c303-117">You can find .NET Core Global Tools on [NuGet](https://www.nuget.org).</span></span> <span data-ttu-id="6c303-118">NuGet todavía no permite buscar de manera específica herramientas globales de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6c303-118">However, NuGet doesn't yet allow you to search specifically for .NET Core Global Tools.</span></span>

<span data-ttu-id="6c303-119">Es posible que encuentre recomendaciones sobre herramientas en entradas de blog o en el repositorio de GitHub [natemcmaster/dotnet-tools](https://github.com/natemcmaster/dotnet-tools).</span><span class="sxs-lookup"><span data-stu-id="6c303-119">You may also find tool recommendations in blog posts or in the [natemcmaster/dotnet-tools](https://github.com/natemcmaster/dotnet-tools) GitHub repository.</span></span>

<span data-ttu-id="6c303-120">Asimismo, puede ver el código fuente de las herramientas globales creado por el equipo de ASP.NET en el repositorio de GitHub [aspnet/DotNetTools](https://github.com/aspnet/DotNetTools/).</span><span class="sxs-lookup"><span data-stu-id="6c303-120">You can also see the source code for the Global Tools created by the ASP.NET team at the [aspnet/DotNetTools](https://github.com/aspnet/DotNetTools/) GitHub repository.</span></span>

## <a name="check-the-author-and-statistics"></a><span data-ttu-id="6c303-121">Comprobar el autor y las estadísticas</span><span class="sxs-lookup"><span data-stu-id="6c303-121">Check the author and statistics</span></span>

<span data-ttu-id="6c303-122">Dado que herramientas globales de .NET Core se ejecutan con plena confianza y generalmente se instalan en su ruta de acceso, pueden ser muy eficaces.</span><span class="sxs-lookup"><span data-stu-id="6c303-122">Since .NET Core Global Tools run in full trust and are generally installed on your path, they can be very powerful.</span></span> <span data-ttu-id="6c303-123">No descargue herramientas de personas en las que no confíe.</span><span class="sxs-lookup"><span data-stu-id="6c303-123">Don't download tools from people you don't trust.</span></span>

<span data-ttu-id="6c303-124">Si la herramienta está hospedada en NuGet, busque la herramienta para comprobar el autor y las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="6c303-124">If the tool is hosted on NuGet, you can check the author and statistics by searching for the tool.</span></span>

## <a name="install-a-global-tool"></a><span data-ttu-id="6c303-125">Instalar una herramienta global</span><span class="sxs-lookup"><span data-stu-id="6c303-125">Install a Global Tool</span></span>

<span data-ttu-id="6c303-126">Para instalar una herramienta global, use el comando de CLI de .NET Core [dotnet tool install](dotnet-tool-install.md).</span><span class="sxs-lookup"><span data-stu-id="6c303-126">To install a Global Tool, you use the [dotnet tool install](dotnet-tool-install.md) .NET Core CLI command.</span></span> <span data-ttu-id="6c303-127">En el ejemplo siguiente se muestra cómo instalar una herramienta global en la ubicación predeterminada:</span><span class="sxs-lookup"><span data-stu-id="6c303-127">The following example shows how to install a Global Tool in the default location:</span></span>

```dotnetcli
dotnet tool install -g dotnetsay
```

<span data-ttu-id="6c303-128">Si no se puede instalar la herramienta, se muestran mensajes de error.</span><span class="sxs-lookup"><span data-stu-id="6c303-128">If the tool can't be installed, error messages are displayed.</span></span> <span data-ttu-id="6c303-129">Verifique que se comprueban las fuentes que esperaba.</span><span class="sxs-lookup"><span data-stu-id="6c303-129">Check that the feeds you expected are being checked.</span></span>

<span data-ttu-id="6c303-130">Si está intentando instalar una versión preliminar o una versión específica de la herramienta, puede especificar el número de versión con el formato siguiente:</span><span class="sxs-lookup"><span data-stu-id="6c303-130">If you're trying to install a pre-release version or a specific version of the tool, you can specify the version number using the following format:</span></span>

```dotnetcli
dotnet tool install -g <package-name> --version <version-number>
```

<span data-ttu-id="6c303-131">Si la instalación es correcta, se muestra un mensaje similar al siguiente con el comando que se usa para llamar a la herramienta y la versión instalada:</span><span class="sxs-lookup"><span data-stu-id="6c303-131">If installation is successful, a message is displayed showing the command used to call the tool and the version installed, similar to the following example:</span></span>

```output
You can invoke the tool using the following command: dotnetsay
Tool 'dotnetsay' (version '2.0.0') was successfully installed.
```

<span data-ttu-id="6c303-132">Las herramientas globales pueden instalarse en el directorio predeterminado o en una ubicación específica.</span><span class="sxs-lookup"><span data-stu-id="6c303-132">Global Tools can be installed in the default directory or in a specific location.</span></span> <span data-ttu-id="6c303-133">Los directorios predeterminados son:</span><span class="sxs-lookup"><span data-stu-id="6c303-133">The default directories are:</span></span>

| <span data-ttu-id="6c303-134">SO</span><span class="sxs-lookup"><span data-stu-id="6c303-134">OS</span></span>          | <span data-ttu-id="6c303-135">Ruta de acceso</span><span class="sxs-lookup"><span data-stu-id="6c303-135">Path</span></span>                          |
|-------------|-------------------------------|
| <span data-ttu-id="6c303-136">Linux/macOS</span><span class="sxs-lookup"><span data-stu-id="6c303-136">Linux/macOS</span></span> | `$HOME/.dotnet/tools`         |
| <span data-ttu-id="6c303-137">Windows</span><span class="sxs-lookup"><span data-stu-id="6c303-137">Windows</span></span>     | `%USERPROFILE%\.dotnet\tools` |

<span data-ttu-id="6c303-138">Estas ubicaciones se agregan a la ruta de acceso del usuario cuando se ejecuta el SDK por primera vez, permitiendo así llamar directamente a las herramientas globales allí instaladas.</span><span class="sxs-lookup"><span data-stu-id="6c303-138">These locations are added to the user's path when the SDK is first run, so Global Tools installed there can be called directly.</span></span>

<span data-ttu-id="6c303-139">Tenga en cuenta que las herramientas globales son específicas del usuario, no de la máquina.</span><span class="sxs-lookup"><span data-stu-id="6c303-139">Note that the Global Tools are user-specific, not machine global.</span></span> <span data-ttu-id="6c303-140">Específica del usuario significa que no se puede instalar una herramienta global que está disponible para todos los usuarios de la máquina.</span><span class="sxs-lookup"><span data-stu-id="6c303-140">Being user-specific means you cannot install a Global Tool that is available to all users of the machine.</span></span> <span data-ttu-id="6c303-141">La herramienta solo está disponible para cada perfil de usuario en el que se instaló la herramienta.</span><span class="sxs-lookup"><span data-stu-id="6c303-141">The tool is only available for each user profile where the tool was installed.</span></span>

<span data-ttu-id="6c303-142">Las herramientas globales también pueden instalarse en un directorio específico.</span><span class="sxs-lookup"><span data-stu-id="6c303-142">Global Tools can also be installed in a specific directory.</span></span> <span data-ttu-id="6c303-143">Cuando se instalan en un directorio específico, el usuario debe incluir el directorio en la ruta de acceso a fin de asegurarse de que el comando está disponible. Hay dos maneras de hacerlo: llamar al comando con el directorio especificado, o llamar a la herramienta desde el directorio especificado.</span><span class="sxs-lookup"><span data-stu-id="6c303-143">When installed in a specific directory, the user must ensure the command is available, by including that directory in the path, by calling the command with the directory specified, or calling the tool from within the specified directory.</span></span>
<span data-ttu-id="6c303-144">En este caso, la CLI de .NET Core no agrega esta ubicación automáticamente a la variable de entorno PATH.</span><span class="sxs-lookup"><span data-stu-id="6c303-144">In this case, the .NET Core CLI doesn't add this location automatically to the PATH environment variable.</span></span>

## <a name="use-the-tool"></a><span data-ttu-id="6c303-145">Usar la herramienta</span><span class="sxs-lookup"><span data-stu-id="6c303-145">Use the tool</span></span>

<span data-ttu-id="6c303-146">Una vez que la herramienta se ha instalado, puede llamarla mediante su comando.</span><span class="sxs-lookup"><span data-stu-id="6c303-146">Once the tool is installed, you can call it by using its command.</span></span> <span data-ttu-id="6c303-147">Tenga en cuenta que el comando podría no ser el mismo que el nombre del paquete.</span><span class="sxs-lookup"><span data-stu-id="6c303-147">Note that the command may not be the same as the package name.</span></span>

<span data-ttu-id="6c303-148">Si el comando es `dotnetsay`, llame a la herramienta con:</span><span class="sxs-lookup"><span data-stu-id="6c303-148">If the command is `dotnetsay`, you call it with:</span></span>

```console
dotnetsay
```

<span data-ttu-id="6c303-149">Si la intención del autor era mostrar la herramienta ante una petición de `dotnet`, puede haberla escrito de manera que se llame como `dotnet <command>`, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6c303-149">If the tool author wanted the tool to appear in the context of the `dotnet` prompt, they may have written it in a way that you call it as `dotnet <command>`, such as:</span></span>

```dotnetcli
dotnet doc
```

<span data-ttu-id="6c303-150">Para ver las herramientas que están incluidas en un paquete de herramienta global instalado, enumere los paquetes instalados con el comando [dotnet tool list](dotnet-tool-list.md).</span><span class="sxs-lookup"><span data-stu-id="6c303-150">You can find which tools are included in an installed Global Tool package by listing the installed packages using the [dotnet tool list](dotnet-tool-list.md) command.</span></span>

<span data-ttu-id="6c303-151">También puede buscar las instrucciones de uso en el sitio web de la herramienta o escribir uno de los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="6c303-151">You can also look for usage instructions at the tool's website or by typing one of the following commands:</span></span>

```console
<command> --help
dotnet <command> --help
```

## <a name="other-cli-commands"></a><span data-ttu-id="6c303-152">Otros comandos de la CLI</span><span class="sxs-lookup"><span data-stu-id="6c303-152">Other CLI commands</span></span>

<span data-ttu-id="6c303-153">El SDK de .NET Core contiene otros comandos que pueden usarse con las herramientas globales de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6c303-153">The .NET Core SDK contains other commands that support .NET Core Global Tools.</span></span> <span data-ttu-id="6c303-154">Utilice cualquiera de los comandos de `dotnet tool` combinado con las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="6c303-154">Use any of the `dotnet tool` commands with one of the following options:</span></span>

* <span data-ttu-id="6c303-155">`--global` o `-g` especifica que el comando es aplicable a las herramientas globales de todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="6c303-155">`--global` or `-g` specifies that the command is applicable to user-wide Global Tools.</span></span>
* <span data-ttu-id="6c303-156">`--tool-path` especifica una ubicación personalizada para las herramientas globales.</span><span class="sxs-lookup"><span data-stu-id="6c303-156">`--tool-path` specifies a custom location for Global Tools.</span></span>

<span data-ttu-id="6c303-157">Para saber qué comandos están disponibles con las herramientas globales:</span><span class="sxs-lookup"><span data-stu-id="6c303-157">To find out which commands are available for Global Tools:</span></span>

```dotnetcli
dotnet tool --help
```

<span data-ttu-id="6c303-158">La actualización de una herramienta global implica desinstalarla y reinstalarla con la versión estable más reciente.</span><span class="sxs-lookup"><span data-stu-id="6c303-158">Updating a Global Tool involves uninstalling and reinstalling it with the latest stable version.</span></span> <span data-ttu-id="6c303-159">Para actualizar una herramienta global, utilice el comando [dotnet tool update](dotnet-tool-update.md):</span><span class="sxs-lookup"><span data-stu-id="6c303-159">To update a Global Tool, use the [dotnet tool update](dotnet-tool-update.md) command:</span></span>

```dotnetcli
dotnet tool update -g <packagename>
```

<span data-ttu-id="6c303-160">Para quitar una herramienta global con [dotnet tool uninstall](dotnet-tool-uninstall.md):</span><span class="sxs-lookup"><span data-stu-id="6c303-160">Remove a Global Tool using the [dotnet tool uninstall](dotnet-tool-uninstall.md):</span></span>

```dotnetcli
dotnet tool uninstall -g <packagename>
```

<span data-ttu-id="6c303-161">Para mostrar todas las herramientas globales instaladas actualmente en el equipo, junto con su versión y los comandos, use el comando [dotnet tool list](dotnet-tool-list.md):</span><span class="sxs-lookup"><span data-stu-id="6c303-161">To display all of the Global Tools currently installed on the machine, along with their version and commands, use the [dotnet tool list](dotnet-tool-list.md) command:</span></span>

```dotnetcli
dotnet tool list -g
```

## <a name="see-also"></a><span data-ttu-id="6c303-162">Vea también</span><span class="sxs-lookup"><span data-stu-id="6c303-162">See also</span></span>

* [<span data-ttu-id="6c303-163">Solución de problemas de uso de herramientas de .NET Core</span><span class="sxs-lookup"><span data-stu-id="6c303-163">Troubleshoot .NET Core tool usage issues</span></span>](troubleshoot-usage-issues.md)
