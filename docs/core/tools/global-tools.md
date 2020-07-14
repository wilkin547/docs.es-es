---
title: Herramientas de .NET Core
description: Cómo instalar, usar, actualizar y quitar las herramientas de .NET Core. Abarca las herramientas globales, herramientas de ruta de acceso de herramientas y herramientas locales.
author: KathleenDollard
ms.date: 02/12/2020
ms.openlocfilehash: 583dbb461543d1efb7328d55f6ecce4a99afcaca
ms.sourcegitcommit: 67cf756b033c6173a1bbd1cbd5aef1fccac99e34
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2020
ms.locfileid: "86226613"
---
# <a name="how-to-manage-net-core-tools"></a><span data-ttu-id="c186c-104">Cómo administrar las herramientas de .NET Core</span><span class="sxs-lookup"><span data-stu-id="c186c-104">How to manage .NET Core tools</span></span>

<span data-ttu-id="c186c-105">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.1 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="c186c-105">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

<span data-ttu-id="c186c-106">Una herramienta de .NET Core es un paquete especial de NuGet que contiene una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="c186c-106">A .NET Core tool is a special NuGet package that contains a console application.</span></span> <span data-ttu-id="c186c-107">Una herramienta se puede instalar en el equipo de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="c186c-107">A tool can be installed on your machine in the following ways:</span></span>

* <span data-ttu-id="c186c-108">Como herramienta global.</span><span class="sxs-lookup"><span data-stu-id="c186c-108">As a global tool.</span></span>

  <span data-ttu-id="c186c-109">Los archivos binarios de la herramienta se instalan en un directorio predeterminado que se agrega a la variable de entorno PATH.</span><span class="sxs-lookup"><span data-stu-id="c186c-109">The tool binaries are installed in a default directory that is added to the PATH environment variable.</span></span> <span data-ttu-id="c186c-110">Puede invocar la herramienta desde cualquier directorio del equipo sin especificar su ubicación.</span><span class="sxs-lookup"><span data-stu-id="c186c-110">You can invoke the tool from any directory on the machine without specifying its location.</span></span> <span data-ttu-id="c186c-111">Una versión de una herramienta se usa para todos los directorios del equipo.</span><span class="sxs-lookup"><span data-stu-id="c186c-111">One version of a tool is used for all directories on the machine.</span></span>

* <span data-ttu-id="c186c-112">Como herramienta global en una ubicación personalizada (también conocida como herramienta de ruta de acceso de herramientas).</span><span class="sxs-lookup"><span data-stu-id="c186c-112">As a global tool in a custom location (also known as a tool-path tool).</span></span>

  <span data-ttu-id="c186c-113">Los archivos binarios de la herramienta se instalan en la ubicación especificada.</span><span class="sxs-lookup"><span data-stu-id="c186c-113">The tool binaries are installed in a location that you specify.</span></span> <span data-ttu-id="c186c-114">Puede invocar la herramienta desde el directorio de instalación o proporcionando el directorio con el nombre del comando o agregando el directorio a la variable de entorno PATH.</span><span class="sxs-lookup"><span data-stu-id="c186c-114">You can invoke the tool from the installation directory or by providing the directory with the command name or by adding the directory to the PATH environment variable.</span></span> <span data-ttu-id="c186c-115">Una versión de una herramienta se usa para todos los directorios del equipo.</span><span class="sxs-lookup"><span data-stu-id="c186c-115">One version of a tool is used for all directories on the machine.</span></span>

* <span data-ttu-id="c186c-116">Como herramienta local (se aplica al SDK de .NET Core 3.0 y versiones posteriores).</span><span class="sxs-lookup"><span data-stu-id="c186c-116">As a local tool (applies to .NET Core SDK 3.0 and later).</span></span>

  <span data-ttu-id="c186c-117">Los archivos binarios de la herramienta se instalan en un directorio predeterminado.</span><span class="sxs-lookup"><span data-stu-id="c186c-117">The tool binaries are installed in a default directory.</span></span> <span data-ttu-id="c186c-118">Puede invocar la herramienta desde el directorio de instalación o con cualquiera de sus subdirectorios.</span><span class="sxs-lookup"><span data-stu-id="c186c-118">You invoke the tool from the installation directory or any of its subdirectories.</span></span> <span data-ttu-id="c186c-119">Distintos directorios pueden usar versiones diferentes de la misma herramienta.</span><span class="sxs-lookup"><span data-stu-id="c186c-119">Different directories can use different versions of the same tool.</span></span>
  
  <span data-ttu-id="c186c-120">La CLI de .NET usa archivos de manifiesto para realizar un seguimiento de las herramientas que se instalan como locales en un directorio.</span><span class="sxs-lookup"><span data-stu-id="c186c-120">The .NET CLI uses manifest files to keep track of which tools are installed as local to a directory.</span></span> <span data-ttu-id="c186c-121">Cuando el archivo de manifiesto se guarda en el directorio raíz de un repositorio de código fuente, un colaborador puede clonar el repositorio e invocar un solo comando de CLI de .NET Core que instale todas las herramientas enumeradas en los archivos de manifiesto.</span><span class="sxs-lookup"><span data-stu-id="c186c-121">When the manifest file is saved in the root directory of a source code repository, a contributor can clone the repository and invoke a single .NET Core CLI command that installs all of the tools listed in the manifest files.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c186c-122">Las herramientas de .NET Core se ejecutan con plena confianza.</span><span class="sxs-lookup"><span data-stu-id="c186c-122">.NET Core tools run in full trust.</span></span> <span data-ttu-id="c186c-123">No instale una herramienta de .NET Core a menos que confíe en el autor.</span><span class="sxs-lookup"><span data-stu-id="c186c-123">Do not install a .NET Core tool unless you trust the author.</span></span>

## <a name="find-a-tool"></a><span data-ttu-id="c186c-124">Búsqueda de una herramienta</span><span class="sxs-lookup"><span data-stu-id="c186c-124">Find a tool</span></span>

<span data-ttu-id="c186c-125">Actualmente, .NET Core no tiene una característica de búsqueda de herramientas.</span><span class="sxs-lookup"><span data-stu-id="c186c-125">Currently, .NET Core doesn't have a tool search feature.</span></span> <span data-ttu-id="c186c-126">Estas son algunas formas de encontrar herramientas:</span><span class="sxs-lookup"><span data-stu-id="c186c-126">Here are some ways to find tools:</span></span>

* <span data-ttu-id="c186c-127">Consulte la lista de herramientas del repositorio GitHub [natemcmaster/dotnet-tools](https://github.com/natemcmaster/dotnet-tools).</span><span class="sxs-lookup"><span data-stu-id="c186c-127">See the list of tools in the [natemcmaster/dotnet-tools](https://github.com/natemcmaster/dotnet-tools) GitHub repository.</span></span>
* <span data-ttu-id="c186c-128">Use [ToolGet](https://www.toolget.net/) para buscar herramientas de .NET.</span><span class="sxs-lookup"><span data-stu-id="c186c-128">Use [ToolGet](https://www.toolget.net/) to search for .NET tools.</span></span>
* <span data-ttu-id="c186c-129">Puede ver el código fuente de las herramientas creado por el equipo de ASP.NET Core en el [directorio de herramientas del repositorio de GitHub dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/tree/master/src/Tools).</span><span class="sxs-lookup"><span data-stu-id="c186c-129">See the source code for the tools created by the ASP.NET Core team in the [Tools directory of the dotnet/aspnetcore GitHub repository](https://github.com/dotnet/aspnetcore/tree/master/src/Tools).</span></span>
* <span data-ttu-id="c186c-130">Obtenga más información sobre las herramientas de diagnóstico en [herramientas de diagnóstico de dotnet de .NET Core ](../diagnostics/index.md#net-core-dotnet-diagnostic-global-tools).</span><span class="sxs-lookup"><span data-stu-id="c186c-130">Learn about diagnostic tools at [.NET Core dotnet diagnostic tools](../diagnostics/index.md#net-core-dotnet-diagnostic-global-tools).</span></span>
* <span data-ttu-id="c186c-131">Busque en el sitio web de [NuGet](https://www.nuget.org).</span><span class="sxs-lookup"><span data-stu-id="c186c-131">Search the [NuGet](https://www.nuget.org) website.</span></span> <span data-ttu-id="c186c-132">Sin embargo, el sitio de NuGet todavía no tiene una característica que le permita buscar solo paquetes de herramientas.</span><span class="sxs-lookup"><span data-stu-id="c186c-132">However, the NuGet site doesn't yet have a feature that lets you search only for tool packages.</span></span>

## <a name="check-the-author-and-statistics"></a><span data-ttu-id="c186c-133">Comprobar el autor y las estadísticas</span><span class="sxs-lookup"><span data-stu-id="c186c-133">Check the author and statistics</span></span>

<span data-ttu-id="c186c-134">Dado que las herramientas de .NET Core se ejecutan con plena confianza y las herramientas globales se agregan a la variable de entorno PATH, pueden ser muy eficaces.</span><span class="sxs-lookup"><span data-stu-id="c186c-134">Since .NET Core tools run in full trust, and global tools are added to the PATH environment variable, they can be very powerful.</span></span> <span data-ttu-id="c186c-135">No descargue herramientas de personas en las que no confíe.</span><span class="sxs-lookup"><span data-stu-id="c186c-135">Don't download tools from people you don't trust.</span></span>

<span data-ttu-id="c186c-136">Si la herramienta está hospedada en NuGet, busque la herramienta para comprobar el autor y las estadísticas.</span><span class="sxs-lookup"><span data-stu-id="c186c-136">If the tool is hosted on NuGet, you can check the author and statistics by searching for the tool.</span></span>

## <a name="install-a-global-tool"></a><span data-ttu-id="c186c-137">Instalación de una herramienta global</span><span class="sxs-lookup"><span data-stu-id="c186c-137">Install a global tool</span></span>

<span data-ttu-id="c186c-138">Para instalar una herramienta como una herramienta global, use la opción `-g` o `--global` del comando [dotnet tool install](dotnet-tool-install.md), tal como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c186c-138">To install a tool as a global tool, use the `-g` or `--global` option of [dotnet tool install](dotnet-tool-install.md), as shown in the following example:</span></span>

```dotnetcli
dotnet tool install -g dotnetsay
```

<span data-ttu-id="c186c-139">La salida muestra el comando que se usa para invocar la herramienta y la versión instalada, de forma similar al ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c186c-139">The output shows the command used to invoke the tool and the version installed, similar to the following example:</span></span>

```output
You can invoke the tool using the following command: dotnetsay
Tool 'dotnetsay' (version '2.1.4') was successfully installed.
```

<span data-ttu-id="c186c-140">La ubicación predeterminada de los archivos binarios de una herramienta depende del sistema operativo:</span><span class="sxs-lookup"><span data-stu-id="c186c-140">The default location for a tool's binaries depends on the operating system:</span></span>

| <span data-ttu-id="c186c-141">SO</span><span class="sxs-lookup"><span data-stu-id="c186c-141">OS</span></span>          | <span data-ttu-id="c186c-142">Ruta de acceso</span><span class="sxs-lookup"><span data-stu-id="c186c-142">Path</span></span>                          |
|-------------|-------------------------------|
| <span data-ttu-id="c186c-143">Linux/macOS</span><span class="sxs-lookup"><span data-stu-id="c186c-143">Linux/macOS</span></span> | `$HOME/.dotnet/tools`         |
| <span data-ttu-id="c186c-144">Windows</span><span class="sxs-lookup"><span data-stu-id="c186c-144">Windows</span></span>     | `%USERPROFILE%\.dotnet\tools` |

<span data-ttu-id="c186c-145">Esta ubicación se agrega a la ruta de acceso del usuario cuando se ejecuta el SDK por primera vez, por lo que las herramientas globales se pueden invocar desde cualquier directorio sin especificar la ubicación de la herramienta.</span><span class="sxs-lookup"><span data-stu-id="c186c-145">This location is added to the user's path when the SDK is first run, so global tools can be invoked from any directory without specifying the tool location.</span></span>

<span data-ttu-id="c186c-146">El acceso a las herramientas es específico del usuario, no de la máquina global.</span><span class="sxs-lookup"><span data-stu-id="c186c-146">Tool access is user-specific, not machine global.</span></span> <span data-ttu-id="c186c-147">Una herramienta global solo está disponible para el usuario que ha instalado la herramienta.</span><span class="sxs-lookup"><span data-stu-id="c186c-147">A global tool is only available to the user that installed the tool.</span></span>

### <a name="install-a-global-tool-in-a-custom-location"></a><span data-ttu-id="c186c-148">Instalación de una herramienta global en una ubicación personalizada</span><span class="sxs-lookup"><span data-stu-id="c186c-148">Install a global tool in a custom location</span></span>

<span data-ttu-id="c186c-149">Para instalar una herramienta como una herramienta global, use la opción `--tool-path` del comando [dotnet tool install](dotnet-tool-install.md), tal como se muestra en los ejemplos siguientes.</span><span class="sxs-lookup"><span data-stu-id="c186c-149">To install a tool as a global tool in a custom location, use the `--tool-path` option of [dotnet tool install](dotnet-tool-install.md), as shown in the following examples.</span></span>

<span data-ttu-id="c186c-150">En Windows:</span><span class="sxs-lookup"><span data-stu-id="c186c-150">On Windows:</span></span>

```dotnetcli
dotnet tool install dotnetsay --tool-path c:\dotnet-tools
```

<span data-ttu-id="c186c-151">En Linux o macOS:</span><span class="sxs-lookup"><span data-stu-id="c186c-151">On Linux or macOS:</span></span>

```dotnetcli
dotnet tool install dotnetsay --tool-path ~/bin
```

<span data-ttu-id="c186c-152">El SDK de .NET Core no agrega esta ubicación automáticamente a la variable de entorno PATH.</span><span class="sxs-lookup"><span data-stu-id="c186c-152">The .NET Core SDK doesn't add this location automatically to the PATH environment variable.</span></span> <span data-ttu-id="c186c-153">Para [invocar una herramienta de ruta de acceso de herramientas](#invoke-a-tool-path-tool), tiene que asegurarse de que el comando está disponible mediante uno de los métodos siguientes:</span><span class="sxs-lookup"><span data-stu-id="c186c-153">To [invoke a tool-path tool](#invoke-a-tool-path-tool), you have to make sure the command is available by using one of the following methods:</span></span>

* <span data-ttu-id="c186c-154">Agregue el directorio de instalación a la variable de entorno PATH.</span><span class="sxs-lookup"><span data-stu-id="c186c-154">Add the installation directory to the PATH environment variable.</span></span>
* <span data-ttu-id="c186c-155">Especifique la ruta de acceso completa a la herramienta al invocarla.</span><span class="sxs-lookup"><span data-stu-id="c186c-155">Specify the full path to the tool when you invoke it.</span></span>
* <span data-ttu-id="c186c-156">Invoque la herramienta desde el directorio de instalación.</span><span class="sxs-lookup"><span data-stu-id="c186c-156">Invoke the tool from within the installation directory.</span></span>

## <a name="install-a-local-tool"></a><span data-ttu-id="c186c-157">Instalación de una herramienta local</span><span class="sxs-lookup"><span data-stu-id="c186c-157">Install a local tool</span></span>

<span data-ttu-id="c186c-158">**Se aplica al SDK de .NET Core 3.0 y versiones posteriores.**</span><span class="sxs-lookup"><span data-stu-id="c186c-158">**Applies to .NET Core 3.0 SDK and later.**</span></span>

<span data-ttu-id="c186c-159">Para instalar una herramienta solo para el acceso local (del directorio y los subdirectorios actuales), debe agregarse a un archivo de manifiesto de la herramienta.</span><span class="sxs-lookup"><span data-stu-id="c186c-159">To install a tool for local access only (for the current directory and subdirectories), it has to be added to a tool manifest file.</span></span> <span data-ttu-id="c186c-160">Para crear un archivo de manifiesto de herramienta, ejecute el comando `dotnet new tool-manifest`:</span><span class="sxs-lookup"><span data-stu-id="c186c-160">To create a tool manifest file, run the `dotnet new tool-manifest` command:</span></span>

```dotnetcli
dotnet new tool-manifest
```

<span data-ttu-id="c186c-161">Este comando crea un archivo de manifiesto denominado *dotnet-tools.json* en el directorio *.config*.</span><span class="sxs-lookup"><span data-stu-id="c186c-161">This command creates a manifest file named *dotnet-tools.json* under the *.config* directory.</span></span> <span data-ttu-id="c186c-162">Para agregar una herramienta local al archivo de manifiesto, use el comando [dotnet tool install](dotnet-tool-install.md) y **omita** las opciones `--global` y `--tool-path`, tal como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c186c-162">To add a local tool to the manifest file, use the [dotnet tool install](dotnet-tool-install.md) command and **omit** the `--global` and `--tool-path` options, as shown in the following example:</span></span>

```dotnetcli
dotnet tool install dotnetsay
```

<span data-ttu-id="c186c-163">En la salida del comando se muestra el archivo de manifiesto en el que se encuentra la herramienta que acaba de instalar, de manera similar al siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c186c-163">The command output shows which manifest file the newly installed tool is in, similar to the following example:</span></span>

```console
You can invoke the tool from this directory using the following command:
dotnet tool run dotnetsay
Tool 'dotnetsay' (version '2.1.4') was successfully installed.
Entry is added to the manifest file /home/name/botsay/.config/dotnet-tools.json.
```

<span data-ttu-id="c186c-164">En el ejemplo siguiente se muestra un archivo de manifiesto con dos herramientas locales instaladas:</span><span class="sxs-lookup"><span data-stu-id="c186c-164">The following example shows a manifest file with two local tools installed:</span></span>

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {
    "botsay": {
      "version": "1.0.0",
      "commands": [
        "botsay"
      ]
    },
    "dotnetsay": {
      "version": "2.1.3",
      "commands": [
        "dotnetsay"
      ]
    }
  }
}
```

<span data-ttu-id="c186c-165">Normalmente, una herramienta local se agrega al directorio raíz del repositorio.</span><span class="sxs-lookup"><span data-stu-id="c186c-165">You typically add a local tool to the root directory of the repository.</span></span> <span data-ttu-id="c186c-166">Después de insertar el archivo de manifiesto en el repositorio, los desarrolladores que extraen código del repositorio obtienen el archivo de manifiesto más reciente.</span><span class="sxs-lookup"><span data-stu-id="c186c-166">After you check in the manifest file to the repository, developers who check out code from the repository get the latest manifest file.</span></span> <span data-ttu-id="c186c-167">Para instalar todas las herramientas enumeradas en el archivo de manifiesto, ejecutan el comando `dotnet tool restore`:</span><span class="sxs-lookup"><span data-stu-id="c186c-167">To install all of the tools listed in the manifest file, they run the `dotnet tool restore` command:</span></span>

```dotnetcli
dotnet tool restore
```

<span data-ttu-id="c186c-168">La salida indica qué herramientas se han restaurado:</span><span class="sxs-lookup"><span data-stu-id="c186c-168">The output indicates which tools were restored:</span></span>

```console
Tool 'botsay' (version '1.0.0') was restored. Available commands: botsay
Tool 'dotnetsay' (version '2.1.3') was restored. Available commands: dotnetsay
Restore was successful.
```

## <a name="install-a-specific-tool-version"></a><span data-ttu-id="c186c-169">Instalación de una versión específica de la herramienta</span><span class="sxs-lookup"><span data-stu-id="c186c-169">Install a specific tool version</span></span>

<span data-ttu-id="c186c-170">Para instalar una versión preliminar o una versión específica de la herramienta, especifique el número de versión con la opción `--version`, tal como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c186c-170">To install a pre-release version or a specific version of a tool, specify the version number by using the `--version` option, as shown in the following example:</span></span>

```dotnetcli
dotnet tool install dotnetsay --version 2.1.3
```

## <a name="use-a-tool"></a><span data-ttu-id="c186c-171">Uso de una herramienta</span><span class="sxs-lookup"><span data-stu-id="c186c-171">Use a tool</span></span>

<span data-ttu-id="c186c-172">El comando que se usa para invocar una herramienta puede ser diferente del nombre del paquete que se instala.</span><span class="sxs-lookup"><span data-stu-id="c186c-172">The command that you use to invoke a tool may be different from the name of the package that you install.</span></span> <span data-ttu-id="c186c-173">Para mostrar todas las herramientas instaladas actualmente en el equipo para el usuario actual, use el comando [dotnet tool list](dotnet-tool-list.md):</span><span class="sxs-lookup"><span data-stu-id="c186c-173">To display all of the tools currently installed on the machine for the current user, use the [dotnet tool list](dotnet-tool-list.md) command:</span></span>

```dotnetcli
dotnet tool list
```

<span data-ttu-id="c186c-174">La salida muestra la versión y el comando de cada herramienta, de forma similar al ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c186c-174">The output shows each tool's version and command, similar to the following example:</span></span>

```console
Package Id      Version      Commands       Manifest
-------------------------------------------------------------------------------------------
botsay          1.0.0        botsay         /home/name/repository/.config/dotnet-tools.json
dotnetsay       2.1.3        dotnetsay      /home/name/repository/.config/dotnet-tools.json
```

<span data-ttu-id="c186c-175">Tal como se muestra en este ejemplo, la lista muestra las herramientas locales.</span><span class="sxs-lookup"><span data-stu-id="c186c-175">As shown in this example, the list shows local tools.</span></span> <span data-ttu-id="c186c-176">Para ver las herramientas globales, use la opción `--global` y, para ver herramientas de ruta de acceso de herramientas, use la opción `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="c186c-176">To see global tools, use the `--global` option, and to see tool-path tools, use the `--tool-path` option.</span></span>

### <a name="invoke-a-global-tool"></a><span data-ttu-id="c186c-177">Invocación de una herramienta global</span><span class="sxs-lookup"><span data-stu-id="c186c-177">Invoke a global tool</span></span>

<span data-ttu-id="c186c-178">En el caso de las herramientas globales, use el comando de la herramienta por sí solo.</span><span class="sxs-lookup"><span data-stu-id="c186c-178">For global tools, use the tool command by itself.</span></span> <span data-ttu-id="c186c-179">Por ejemplo, si el comando es `dotnetsay` o `dotnet-doc`, eso es lo que se usa para invocar el comando:</span><span class="sxs-lookup"><span data-stu-id="c186c-179">For example, if the command is `dotnetsay` or `dotnet-doc`, that's what you use to invoke the command:</span></span>

```console
dotnetsay
dotnet-doc
```

<span data-ttu-id="c186c-180">Si el comando comienza con el prefijo `dotnet-`, una manera alternativa de invocar la herramienta es usar el comando `dotnet` y omitir el prefijo del comando de la herramienta.</span><span class="sxs-lookup"><span data-stu-id="c186c-180">If the command begins with the prefix `dotnet-`, an alternative way to invoke the tool is to use the `dotnet` command and omit the tool command prefix.</span></span> <span data-ttu-id="c186c-181">Por ejemplo, si el comando es `dotnet-doc`, el siguiente comando invoca la herramienta:</span><span class="sxs-lookup"><span data-stu-id="c186c-181">For example, if the command is `dotnet-doc`, the following command invokes the tool:</span></span>

```dotnetcli
dotnet doc
```

<span data-ttu-id="c186c-182">Sin embargo, en el siguiente escenario no se puede usar el comando `dotnet` para invocar una herramienta global:</span><span class="sxs-lookup"><span data-stu-id="c186c-182">However, in the following scenario you can't use the `dotnet` command to invoke a global tool:</span></span>

* <span data-ttu-id="c186c-183">Una herramienta global y una herramienta local tienen el mismo comando con el prefijo `dotnet-`.</span><span class="sxs-lookup"><span data-stu-id="c186c-183">A global tool and a local tool have the same command prefixed by `dotnet-`.</span></span>
* <span data-ttu-id="c186c-184">Quiere invocar la herramienta global desde un directorio que está en el ámbito de la herramienta local.</span><span class="sxs-lookup"><span data-stu-id="c186c-184">You want to invoke the global tool from a directory that is in scope for the local tool.</span></span>

<span data-ttu-id="c186c-185">En este escenario, `dotnet doc` y `dotnet dotnet-doc` invocan a la herramienta local.</span><span class="sxs-lookup"><span data-stu-id="c186c-185">In this scenario, `dotnet doc` and `dotnet dotnet-doc` invoke the local tool.</span></span> <span data-ttu-id="c186c-186">Para invocar la herramienta global, use el comando por sí solo:</span><span class="sxs-lookup"><span data-stu-id="c186c-186">To invoke the global tool, use the command by itself:</span></span>

```dotnetcli
dotnet-doc
```

### <a name="invoke-a-tool-path-tool"></a><span data-ttu-id="c186c-187">Invocación de una herramienta de ruta de acceso de herramientas</span><span class="sxs-lookup"><span data-stu-id="c186c-187">Invoke a tool-path tool</span></span>

<span data-ttu-id="c186c-188">Para invocar una herramienta global que se instala mediante la opción `tool-path`, asegúrese de que el comando está disponible, tal como se explicó [anteriormente en este artículo](#install-a-global-tool-in-a-custom-location).</span><span class="sxs-lookup"><span data-stu-id="c186c-188">To invoke a global tool that is installed by using the `tool-path` option, make sure the command is available, as explained [earlier in this article](#install-a-global-tool-in-a-custom-location).</span></span>

### <a name="invoke-a-local-tool"></a><span data-ttu-id="c186c-189">Invocación de una herramienta local</span><span class="sxs-lookup"><span data-stu-id="c186c-189">Invoke a local tool</span></span>

<span data-ttu-id="c186c-190">Para invocar una herramienta local, tiene que usar el comando `dotnet` desde el directorio de instalación.</span><span class="sxs-lookup"><span data-stu-id="c186c-190">To invoke a local tool, you have to use the `dotnet` command from within the installation directory.</span></span> <span data-ttu-id="c186c-191">Puede usar el formato largo (`dotnet tool run <COMMAND_NAME>`) o el formato abreviado (`dotnet <COMMAND_NAME>`), tal como se muestra en los ejemplos siguientes:</span><span class="sxs-lookup"><span data-stu-id="c186c-191">You can use the long form (`dotnet tool run <COMMAND_NAME>`) or the short form (`dotnet <COMMAND_NAME>`), as shown in the following examples:</span></span>

```dotnetcli
dotnet tool run dotnetsay
dotnet dotnetsay
```

<span data-ttu-id="c186c-192">Si el comando tiene el prefijo `dotnet-`, puede incluir u omitir el prefijo al invocar la herramienta.</span><span class="sxs-lookup"><span data-stu-id="c186c-192">If the command is prefixed by `dotnet-`, you can include or omit the prefix when you invoke the tool.</span></span> <span data-ttu-id="c186c-193">Por ejemplo, si el comando es `dotnet-doc`, cualquiera de los siguientes ejemplos invoca la herramienta local:</span><span class="sxs-lookup"><span data-stu-id="c186c-193">For example, if the command is `dotnet-doc`, any of the following examples invokes the local tool:</span></span>

```dotnetcli
dotnet tool run dotnet-doc
dotnet dotnet-doc
dotnet doc
```

## <a name="update-a-tool"></a><span data-ttu-id="c186c-194">Actualización de una herramienta</span><span class="sxs-lookup"><span data-stu-id="c186c-194">Update a tool</span></span>

<span data-ttu-id="c186c-195">La actualización de una herramienta implica desinstalarla y reinstalarla con la versión estable más reciente.</span><span class="sxs-lookup"><span data-stu-id="c186c-195">Updating a tool involves uninstalling and reinstalling it with the latest stable version.</span></span> <span data-ttu-id="c186c-196">Para actualizar una herramienta, use el comando [dotnet tool update](dotnet-tool-update.md) con la misma opción que usó para instalar la herramienta:</span><span class="sxs-lookup"><span data-stu-id="c186c-196">To update a tool, use the [dotnet tool update](dotnet-tool-update.md) command with the same option that you used to install the tool:</span></span>

```dotnetcli
dotnet tool update --global <packagename>
dotnet tool update --tool-path <packagename>
dotnet tool update <packagename>
```

<span data-ttu-id="c186c-197">En el caso de una herramienta local, el SDK encuentra el primer archivo de manifiesto que contiene el identificador de paquete mediante la búsqueda en el directorio actual y en los directorios principales.</span><span class="sxs-lookup"><span data-stu-id="c186c-197">For a local tool, the SDK finds the first manifest file that contains the package ID by looking in the current directory and parent directories.</span></span> <span data-ttu-id="c186c-198">Si no hay ningún identificador del paquete en ningún archivo de manifiesto, el SDK agrega una nueva entrada al archivo de manifiesto más cercano.</span><span class="sxs-lookup"><span data-stu-id="c186c-198">If there is no such package ID in any manifest file, the SDK adds a new entry to the closest manifest file.</span></span>

## <a name="uninstall-a-tool"></a><span data-ttu-id="c186c-199">Desinstalación de una herramienta</span><span class="sxs-lookup"><span data-stu-id="c186c-199">Uninstall a tool</span></span>

<span data-ttu-id="c186c-200">Quite una herramienta mediante el comando [dotnet tool uninstall](dotnet-tool-uninstall.md) con la misma opción que usó para instalar la herramienta:</span><span class="sxs-lookup"><span data-stu-id="c186c-200">Remove a tool by using the [dotnet tool uninstall](dotnet-tool-uninstall.md) command with the same option that you used to install the tool:</span></span>

```dotnetcli
dotnet tool uninstall --global <packagename>
dotnet tool uninstall --tool-path <packagename>
dotnet tool uninstall <packagename>
```

<span data-ttu-id="c186c-201">En el caso de una herramienta local, el SDK encuentra el primer archivo de manifiesto que contiene el identificador de paquete mediante la búsqueda en el directorio actual y en los directorios principales.</span><span class="sxs-lookup"><span data-stu-id="c186c-201">For a local tool, the SDK finds the first manifest file that contains the package ID by looking in the current directory and parent directories.</span></span>

## <a name="get-help-and-troubleshoot"></a><span data-ttu-id="c186c-202">Ayuda y solución de problemas</span><span class="sxs-lookup"><span data-stu-id="c186c-202">Get help and troubleshoot</span></span>

<span data-ttu-id="c186c-203">Para obtener una lista de los comandos de `dotnet tool` disponibles, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="c186c-203">To get a list of available `dotnet tool` commands, enter the following command:</span></span>

```dotnetcli
dotnet tool --help
```

<span data-ttu-id="c186c-204">Para obtener instrucciones sobre el uso de la herramienta, escriba uno de los siguientes comandos o vea el sitio web de la herramienta:</span><span class="sxs-lookup"><span data-stu-id="c186c-204">To get tool usage instructions, enter one of the following commands or see the tool's website:</span></span>

```dotnetcli
<command> --help
dotnet <command> --help
```

<span data-ttu-id="c186c-205">Si una herramienta no se puede instalar o ejecutar, consulte [Solución de problemas de uso de herramientas de .NET Core](troubleshoot-usage-issues.md).</span><span class="sxs-lookup"><span data-stu-id="c186c-205">If a tool fails to install or run, see [Troubleshoot .NET Core tool usage issues](troubleshoot-usage-issues.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c186c-206">Vea también</span><span class="sxs-lookup"><span data-stu-id="c186c-206">See also</span></span>

- [<span data-ttu-id="c186c-207">Tutorial: Creación de una herramienta de .NET Core mediante la CLI de .NET Core</span><span class="sxs-lookup"><span data-stu-id="c186c-207">Tutorial: Create a .NET Core tool using the .NET Core CLI</span></span>](global-tools-how-to-create.md)
- [<span data-ttu-id="c186c-208">Tutorial: Instalación y uso de una herramienta global de .NET Core mediante la CLI de .NET Core</span><span class="sxs-lookup"><span data-stu-id="c186c-208">Tutorial: Install and use a .NET Core global tool using the .NET Core CLI</span></span>](global-tools-how-to-use.md)
- [<span data-ttu-id="c186c-209">Tutorial: Instalación y uso de una herramienta local de .NET Core mediante la CLI de .NET Core</span><span class="sxs-lookup"><span data-stu-id="c186c-209">Tutorial: Install and use a .NET Core local tool using the .NET Core CLI</span></span>](local-tools-how-to-use.md)
