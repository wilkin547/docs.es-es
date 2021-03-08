---
title: Solución de problemas de uso de herramientas de .NET Core
description: Descubra los problemas comunes que se producen al ejecutar herramientas de .NET y sus posibles soluciones.
author: kdollard
ms.topic: troubleshooting
ms.date: 02/14/2020
ms.openlocfilehash: 9cf0320ec5b5d6f317a4ef7f9052c0068b3ad8e5
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102104094"
---
# <a name="troubleshoot-net-tool-usage-issues"></a><span data-ttu-id="5d839-103">Solución de problemas de uso de herramientas de .NET Core</span><span class="sxs-lookup"><span data-stu-id="5d839-103">Troubleshoot .NET tool usage issues</span></span>

<span data-ttu-id="5d839-104">Es posible que surjan problemas al intentar instalar o ejecutar una herramienta de .NET, que puede ser global o local.</span><span class="sxs-lookup"><span data-stu-id="5d839-104">You might come across issues when trying to install or run a .NET tool, which can be a global tool or a local tool.</span></span> <span data-ttu-id="5d839-105">En este artículo se describen las causas principales más comunes y algunas posibles soluciones.</span><span class="sxs-lookup"><span data-stu-id="5d839-105">This article describes the common root causes and some possible solutions.</span></span>

## <a name="installed-net-tool-fails-to-run"></a><span data-ttu-id="5d839-106">No se puede ejecutar la herramienta de .NET instalada</span><span class="sxs-lookup"><span data-stu-id="5d839-106">Installed .NET tool fails to run</span></span>

<span data-ttu-id="5d839-107">Cuando una herramienta de .NET no se ejecuta, lo más probable es que se haya producido uno de los problemas siguientes:</span><span class="sxs-lookup"><span data-stu-id="5d839-107">When a .NET tool fails to run, most likely you ran into one of the following issues:</span></span>

* <span data-ttu-id="5d839-108">No se encontró el archivo ejecutable de la herramienta.</span><span class="sxs-lookup"><span data-stu-id="5d839-108">The executable file for the tool wasn't found.</span></span>
* <span data-ttu-id="5d839-109">No se encuentra la versión correcta del entorno de ejecución de .NET.</span><span class="sxs-lookup"><span data-stu-id="5d839-109">The correct version of the .NET runtime wasn't found.</span></span>

### <a name="executable-file-not-found"></a><span data-ttu-id="5d839-110">No se encontró el archivo ejecutable</span><span class="sxs-lookup"><span data-stu-id="5d839-110">Executable file not found</span></span>

<span data-ttu-id="5d839-111">Si no se encuentra el archivo ejecutable, verá un mensaje similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="5d839-111">If the executable file isn't found, you'll see a message similar to the following:</span></span>

```console
Could not execute because the specified command or file was not found.
Possible reasons for this include:
  * You misspelled a built-in dotnet command.
  * You intended to execute a .NET program, but dotnet-xyz does not exist.
  * You intended to run a global tool, but a dotnet-prefixed executable with this name could not be found on the PATH.
```

<span data-ttu-id="5d839-112">El nombre del archivo ejecutable determina cómo se invoca la herramienta.</span><span class="sxs-lookup"><span data-stu-id="5d839-112">The name of the executable determines how you invoke the tool.</span></span> <span data-ttu-id="5d839-113">En la siguiente tabla se describe el formato:</span><span class="sxs-lookup"><span data-stu-id="5d839-113">The following table describes the format:</span></span>

| <span data-ttu-id="5d839-114">Formato del nombre del archivo ejecutable</span><span class="sxs-lookup"><span data-stu-id="5d839-114">Executable name format</span></span>  | <span data-ttu-id="5d839-115">Formato de invocación</span><span class="sxs-lookup"><span data-stu-id="5d839-115">Invocation format</span></span>   |
|-------------------------|---------------------|
| `dotnet-<toolName>.exe` | `dotnet <toolName>` |
| `<toolName>.exe`        | `<toolName>`        |

* <span data-ttu-id="5d839-116">Herramientas globales</span><span class="sxs-lookup"><span data-stu-id="5d839-116">Global tools</span></span>

  <span data-ttu-id="5d839-117">Las herramientas globales pueden instalarse en el directorio predeterminado o en una ubicación específica.</span><span class="sxs-lookup"><span data-stu-id="5d839-117">Global tools can be installed in the default directory or in a specific location.</span></span> <span data-ttu-id="5d839-118">Los directorios predeterminados son:</span><span class="sxs-lookup"><span data-stu-id="5d839-118">The default directories are:</span></span>

  | <span data-ttu-id="5d839-119">SO</span><span class="sxs-lookup"><span data-stu-id="5d839-119">OS</span></span>          | <span data-ttu-id="5d839-120">Ruta de acceso</span><span class="sxs-lookup"><span data-stu-id="5d839-120">Path</span></span>                          |
  |-------------|-------------------------------|
  | <span data-ttu-id="5d839-121">Linux/macOS</span><span class="sxs-lookup"><span data-stu-id="5d839-121">Linux/macOS</span></span> | `$HOME/.dotnet/tools`         |
  | <span data-ttu-id="5d839-122">Windows</span><span class="sxs-lookup"><span data-stu-id="5d839-122">Windows</span></span>     | `%USERPROFILE%\.dotnet\tools` |

  <span data-ttu-id="5d839-123">Si intenta ejecutar una herramienta global, compruebe que la variable del entorno `PATH` de su máquina contiene la ruta de acceso donde instaló la herramienta global y que el archivo ejecutable está en esa ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="5d839-123">If you're trying to run a global tool, check that the `PATH` environment variable on your machine contains the path where you installed the global tool and that the executable is in that path.</span></span>

  <span data-ttu-id="5d839-124">La primera vez que se usa, la CLI de .NET intenta agregar la ubicación predeterminada a la variable de entorno PATH.</span><span class="sxs-lookup"><span data-stu-id="5d839-124">The .NET CLI tries to add the default location to the PATH environment variable on its first usage.</span></span> <span data-ttu-id="5d839-125">Pero hay algunos escenarios en los que la ubicación podría no agregarse a PATH automáticamente:</span><span class="sxs-lookup"><span data-stu-id="5d839-125">However, there are some scenarios where the location might not be added to PATH automatically:</span></span>

  * <span data-ttu-id="5d839-126">Si usa Linux y ha instalado el SDK de .NET mediante archivos *.tar.gz* en lugar de apt-get o rpm.</span><span class="sxs-lookup"><span data-stu-id="5d839-126">If you're using Linux and you've installed the .NET SDK using *.tar.gz* files and not apt-get or rpm.</span></span>
  * <span data-ttu-id="5d839-127">Si usa macOS 10.15 “Catalina” o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="5d839-127">If you're using macOS 10.15 "Catalina" or later versions.</span></span>
  * <span data-ttu-id="5d839-128">Si usa macOS 10.14 "Mojave" o versiones anteriores, y ha instalado el SDK de .NET mediante archivos *.tar.gz* en lugar de *.pkg*.</span><span class="sxs-lookup"><span data-stu-id="5d839-128">If you're using macOS 10.14 "Mojave" or earlier versions, and you've installed the .NET SDK using *.tar.gz* files and not *.pkg*.</span></span>
  * <span data-ttu-id="5d839-129">Si ha instalado el SDK de .NET Core 3.0 y ha establecido la variable de entorno `DOTNET_ADD_GLOBAL_TOOLS_TO_PATH` en `false`.</span><span class="sxs-lookup"><span data-stu-id="5d839-129">If you've installed the .NET Core 3.0 SDK and you've set the `DOTNET_ADD_GLOBAL_TOOLS_TO_PATH` environment variable to `false`.</span></span>
  * <span data-ttu-id="5d839-130">Si ha instalado el SDK de .NET Core 2.2 o versiones anteriores y ha establecido la variable de entorno `DOTNET_SKIP_FIRST_TIME_EXPERIENCE` en `true`.</span><span class="sxs-lookup"><span data-stu-id="5d839-130">If you've installed .NET Core 2.2 SDK or earlier versions, and you've set the `DOTNET_SKIP_FIRST_TIME_EXPERIENCE` environment variable to `true`.</span></span>

  <span data-ttu-id="5d839-131">En estos casos, o si especificó la opción `--tool-path`, la variable de entorno `PATH` del equipo no contiene automáticamente la ruta de acceso donde se instaló la herramienta global.</span><span class="sxs-lookup"><span data-stu-id="5d839-131">In these scenarios or if you specified the `--tool-path` option, the `PATH` environment variable on your machine doesn't automatically contain the path where you installed the global tool.</span></span> <span data-ttu-id="5d839-132">En tal caso, anexe la ubicación de la herramienta (por ejemplo, `$HOME/.dotnet/tools`) a la variable de entorno `PATH` usando el método que el shell proporcione para actualizar variables de entorno.</span><span class="sxs-lookup"><span data-stu-id="5d839-132">In that case, append the tool location (for example, `$HOME/.dotnet/tools`) to the `PATH` environment variable by using whatever method your shell provides for updating environment variables.</span></span> <span data-ttu-id="5d839-133">Para obtener más información, vea [Herramientas de .NET](global-tools.md).</span><span class="sxs-lookup"><span data-stu-id="5d839-133">For more information, see [.NET tools](global-tools.md).</span></span>

* <span data-ttu-id="5d839-134">Herramientas locales</span><span class="sxs-lookup"><span data-stu-id="5d839-134">Local tools</span></span>

  <span data-ttu-id="5d839-135">Si intenta ejecutar una herramienta local, compruebe que hay un archivo de manifiesto denominado *dotnet-tools.json* en el directorio actual o en cualquiera de sus directorios principales.</span><span class="sxs-lookup"><span data-stu-id="5d839-135">If you're trying to run a local tool, verify that there's a manifest file called *dotnet-tools.json* in the current directory or any of its parent directories.</span></span> <span data-ttu-id="5d839-136">Este archivo también puede encontrarse en una carpeta denominada *.config* en cualquier lugar de la jerarquía de carpetas del proyecto, en lugar de en la carpeta raíz.</span><span class="sxs-lookup"><span data-stu-id="5d839-136">This file can also live under a folder named *.config* anywhere in the project folder hierarchy, instead of the root folder.</span></span> <span data-ttu-id="5d839-137">Si *dotnet-tools.json* existe, ábralo y busque la herramienta que intenta ejecutar.</span><span class="sxs-lookup"><span data-stu-id="5d839-137">If *dotnet-tools.json* exists, open it and check for the tool you're trying to run.</span></span> <span data-ttu-id="5d839-138">Si el archivo no contiene una entrada para `"isRoot": true`, busque más arriba en la jerarquía de archivos otros archivos de manifiesto de la herramienta.</span><span class="sxs-lookup"><span data-stu-id="5d839-138">If the file doesn't contain an entry for `"isRoot": true`, then also check further up the file hierarchy for additional tool manifest files.</span></span>

  <span data-ttu-id="5d839-139">Si intenta ejecutar una herramienta de .NET que se ha instalado con una ruta de acceso especificada, debe incluir esa ruta de acceso al usar la herramienta.</span><span class="sxs-lookup"><span data-stu-id="5d839-139">If you're trying to run a .NET tool that was installed with a specified path, you need to include that path when using the tool.</span></span> <span data-ttu-id="5d839-140">Un ejemplo de uso de una herramienta instalada en una ruta de acceso de herramientas es:</span><span class="sxs-lookup"><span data-stu-id="5d839-140">An example of using a tool-path installed tool is:</span></span>

  ```console
  ..\<toolDirectory>\dotnet-<toolName>
  ```

### <a name="runtime-not-found"></a><span data-ttu-id="5d839-141">No se encontró el runtime</span><span class="sxs-lookup"><span data-stu-id="5d839-141">Runtime not found</span></span>

<span data-ttu-id="5d839-142">Las herramientas globales de .NET son [aplicaciones que dependen del marco](../deploying/index.md#publish-framework-dependent), lo que significa que se basan en un entorno de ejecución de .NET instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="5d839-142">.NET tools are [framework-dependent applications](../deploying/index.md#publish-framework-dependent), which means they rely on a .NET runtime installed on your machine.</span></span> <span data-ttu-id="5d839-143">Si no se encuentra el entorno de ejecución esperado, se siguen las reglas normales de puesta al día del de .NET:</span><span class="sxs-lookup"><span data-stu-id="5d839-143">If the expected runtime isn't found, they follow normal .NET runtime roll-forward rules such as:</span></span>

* <span data-ttu-id="5d839-144">Una aplicación avanza a la versión de revisión más alta de las versiones principal y secundaria especificadas.</span><span class="sxs-lookup"><span data-stu-id="5d839-144">An application rolls forward to the highest patch release of the specified major and minor version.</span></span>
* <span data-ttu-id="5d839-145">Si no hay ningún runtime que coincida con un número de versión principal y secundaria, se usa la siguiente versión secundaria más alta.</span><span class="sxs-lookup"><span data-stu-id="5d839-145">If there's no matching runtime with a matching major and minor version number, the next higher minor version is used.</span></span>
* <span data-ttu-id="5d839-146">Esta puesta al día no se produce entre versiones preliminares del runtime ni entre versiones preliminares y versiones de lanzamiento.</span><span class="sxs-lookup"><span data-stu-id="5d839-146">Roll forward doesn't occur between preview versions of the runtime or between preview versions and release versions.</span></span> <span data-ttu-id="5d839-147">Por tanto, las herramientas de .NET creadas con versiones preliminares deben ser recompiladas, publicadas nuevamente y reinstaladas por el autor.</span><span class="sxs-lookup"><span data-stu-id="5d839-147">So, .NET tools created using preview versions must be rebuilt and republished by the author and reinstalled.</span></span>

<span data-ttu-id="5d839-148">La puesta al día no se producirá de forma predeterminada en dos escenarios comunes:</span><span class="sxs-lookup"><span data-stu-id="5d839-148">Roll-forward won't occur by default in two common scenarios:</span></span>

* <span data-ttu-id="5d839-149">Solo están disponibles las versiones anteriores del runtime.</span><span class="sxs-lookup"><span data-stu-id="5d839-149">Only lower versions of the runtime are available.</span></span> <span data-ttu-id="5d839-150">La puesta al día solo selecciona versiones posteriores del runtime.</span><span class="sxs-lookup"><span data-stu-id="5d839-150">Roll-forward only selects later versions of the runtime.</span></span>
* <span data-ttu-id="5d839-151">Solo están disponibles las versiones posteriores principales del runtime.</span><span class="sxs-lookup"><span data-stu-id="5d839-151">Only higher major versions of the runtime are available.</span></span> <span data-ttu-id="5d839-152">La puesta al día no traspasa los límites de la versión principal.</span><span class="sxs-lookup"><span data-stu-id="5d839-152">Roll-forward doesn't cross major version boundaries.</span></span>

<span data-ttu-id="5d839-153">Si una aplicación no encuentra el runtime apropiado, no se puede ejecutar y notifica un error.</span><span class="sxs-lookup"><span data-stu-id="5d839-153">If an application can't find an appropriate runtime, it fails to run and reports an error.</span></span>

<span data-ttu-id="5d839-154">Puede averiguar qué entornos de ejecución de .NET están instalados en el equipo con uno de los comandos siguientes:</span><span class="sxs-lookup"><span data-stu-id="5d839-154">You can find out which .NET runtimes are installed on your machine using one of the following commands:</span></span>

```dotnetcli
dotnet --list-runtimes
dotnet --info
```

<span data-ttu-id="5d839-155">Si cree que la herramienta debería ser compatible con la versión de runtime que tiene instalada actualmente, puede ponerse en contacto con el autor de la herramienta para ver si puede actualizar el número de versión o la compatibilidad con varios destinos.</span><span class="sxs-lookup"><span data-stu-id="5d839-155">If you think the tool should support the runtime version you currently have installed, you can contact the tool author and see if they can update the version number or multi-target.</span></span> <span data-ttu-id="5d839-156">Una vez que se vuelva a compilar y a publicar el paquete de herramientas en NuGet con un número de versión actualizado, podrá actualizar su copia.</span><span class="sxs-lookup"><span data-stu-id="5d839-156">Once they've recompiled and republished their tool package to NuGet with an updated version number, you can update your copy.</span></span> <span data-ttu-id="5d839-157">Mientras tanto, la solución más rápida es instalar una versión del runtime que funcione con la herramienta que intenta ejecutar.</span><span class="sxs-lookup"><span data-stu-id="5d839-157">While that doesn't happen, the quickest solution for you is to install a version of the runtime that would work with the tool you're trying to run.</span></span> <span data-ttu-id="5d839-158">Para descargar una versión específica del entorno de ejecución de .NET, visite la [página de descarga de .NET](https://dotnet.microsoft.com/download/dotnet).</span><span class="sxs-lookup"><span data-stu-id="5d839-158">To download a specific .NET runtime version, visit the [.NET download page](https://dotnet.microsoft.com/download/dotnet).</span></span>

<span data-ttu-id="5d839-159">Si instala el SDK de .NET en una ubicación que no es la predeterminada, debe establecer la variable de entorno `DOTNET_ROOT` en el directorio que contiene el archivo ejecutable `dotnet`.</span><span class="sxs-lookup"><span data-stu-id="5d839-159">If you install the .NET SDK to a non-default location, you need to set the environment variable `DOTNET_ROOT` to the directory that contains the `dotnet` executable.</span></span>

## <a name="net-tool-installation-fails"></a><span data-ttu-id="5d839-160">Error en la instalación de una herramienta de .NET</span><span class="sxs-lookup"><span data-stu-id="5d839-160">.NET tool installation fails</span></span>

<span data-ttu-id="5d839-161">Hay varias razones por las que se puede producir un error en la instalación de una herramienta local o global de .NET.</span><span class="sxs-lookup"><span data-stu-id="5d839-161">There are a number of reasons the installation of a .NET global or local tool may fail.</span></span> <span data-ttu-id="5d839-162">Cuando se produzca un error en la instalación de la herramienta, verá un mensaje similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="5d839-162">When the tool installation fails, you'll see a message similar to the following one:</span></span>

```console
Tool '{0}' failed to install. This failure may have been caused by:

* You are attempting to install a preview release and did not use the --version option to specify the version.
* A package by this name was found, but it was not a .NET tool.
* The required NuGet feed cannot be accessed, perhaps because of an Internet connection problem.
* You mistyped the name of the tool.

For more reasons, including package naming enforcement, visit https://aka.ms/failure-installing-tool
```

<span data-ttu-id="5d839-163">Para ayudar a diagnosticar estos errores, los mensajes de NuGet se muestran directamente al usuario, junto con el mensaje anterior.</span><span class="sxs-lookup"><span data-stu-id="5d839-163">To help diagnose these failures, NuGet messages are shown directly to the user, along with the previous message.</span></span> <span data-ttu-id="5d839-164">El mensaje de NuGet puede ayudarle a identificar el problema.</span><span class="sxs-lookup"><span data-stu-id="5d839-164">The NuGet message may help you identify the problem.</span></span>

### <a name="package-naming-enforcement"></a><span data-ttu-id="5d839-165">Cumplimiento de la nomenclatura de los paquetes</span><span class="sxs-lookup"><span data-stu-id="5d839-165">Package naming enforcement</span></span>

<span data-ttu-id="5d839-166">Microsoft ha cambiado sus instrucciones sobre los identificadores de paquetes para las herramientas, lo que ha dado lugar a que no se encuentren diversas herramientas con el nombre previsto.</span><span class="sxs-lookup"><span data-stu-id="5d839-166">Microsoft has changed its guidance on the Package ID for tools, resulting in a number of tools not being found with the predicted name.</span></span> <span data-ttu-id="5d839-167">Según las nuevas instrucciones, todas las herramientas de Microsoft deben tener el prefijo “Microsoft”.</span><span class="sxs-lookup"><span data-stu-id="5d839-167">The new guidance is that all Microsoft tools be prefixed with "Microsoft."</span></span> <span data-ttu-id="5d839-168">Este prefijo está reservado y solo se puede usar para los paquetes firmados con un certificado autorizado de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5d839-168">This prefix is reserved and can only be used for packages signed with a Microsoft authorized certificate.</span></span>

<span data-ttu-id="5d839-169">Durante la transición, algunas herramientas de Microsoft tendrán el formato anterior del identificador de paquete, mientras que otras tendrán el nuevo formato:</span><span class="sxs-lookup"><span data-stu-id="5d839-169">During the transition, some Microsoft tools will have the old form of the package ID, while others will have the new form:</span></span>

```dotnetcli
dotnet tool install -g Microsoft.<toolName>
dotnet tool install -g <toolName>
```

<span data-ttu-id="5d839-170">A medida que se actualicen los identificadores de paquetes, deberá usar el nuevo identificador de paquete para obtener las actualizaciones más recientes.</span><span class="sxs-lookup"><span data-stu-id="5d839-170">As package IDs are updated, you'll need to change to the new package ID to get the latest updates.</span></span> <span data-ttu-id="5d839-171">Los paquetes con el nombre de herramienta simplificado estarán en desuso.</span><span class="sxs-lookup"><span data-stu-id="5d839-171">Packages with the simplified tool name will be deprecated.</span></span>

### <a name="preview-releases"></a><span data-ttu-id="5d839-172">Versiones preliminares</span><span class="sxs-lookup"><span data-stu-id="5d839-172">Preview releases</span></span>

* <span data-ttu-id="5d839-173">Intenta instalar una versión preliminar y no ha usado la opción `--version` para especificar la versión.</span><span class="sxs-lookup"><span data-stu-id="5d839-173">You're attempting to install a preview release and didn't use the `--version` option to specify the version.</span></span>

<span data-ttu-id="5d839-174">Las herramientas de .NET que se encuentran en versión preliminar se deben especificar con una parte del nombre para indicar que están en versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="5d839-174">.NET tools that are in preview must be specified with a portion of the name to indicate that they are in preview.</span></span> <span data-ttu-id="5d839-175">No es necesario incluir todo el nombre de la versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="5d839-175">You don't need to include the entire preview.</span></span> <span data-ttu-id="5d839-176">Si los números de versión tienen el formato esperado, puede usar algo parecido al ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5d839-176">Assuming the version numbers are in the expected format, you can use something like the following example:</span></span>

```dotnetcli
dotnet tool install -g --version 1.1.0-pre <toolName>
```

### <a name="package-isnt-a-net-tool"></a><span data-ttu-id="5d839-177">El paquete no es una herramienta de .NET</span><span class="sxs-lookup"><span data-stu-id="5d839-177">Package isn't a .NET tool</span></span>

* <span data-ttu-id="5d839-178">Se ha encontrado un paquete NuGet con este nombre, pero no era una herramienta de .NET.</span><span class="sxs-lookup"><span data-stu-id="5d839-178">A NuGet package by this name was found, but it wasn't a .NET tool.</span></span>

<span data-ttu-id="5d839-179">Si intenta instalar un paquete NuGet normal que no es una herramienta de .NET, verá un error similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="5d839-179">If you try to install a NuGet package that is a regular NuGet package and not a .NET tool, you'll see an error similar to the following:</span></span>

> <span data-ttu-id="5d839-180">NU1212: combinación de paquete de proyecto no válida para `<ToolName>`.</span><span class="sxs-lookup"><span data-stu-id="5d839-180">NU1212: Invalid project-package combination for `<ToolName>`.</span></span> <span data-ttu-id="5d839-181">El estilo de proyecto DotnetToolReference solo puede contener referencias de tipo DotnetTool.</span><span class="sxs-lookup"><span data-stu-id="5d839-181">DotnetToolReference project style can only contain references of the DotnetTool type.</span></span>

### <a name="nuget-feed-cant-be-accessed"></a><span data-ttu-id="5d839-182">No se puede acceder a la fuente NuGet</span><span class="sxs-lookup"><span data-stu-id="5d839-182">NuGet feed can't be accessed</span></span>

* <span data-ttu-id="5d839-183">No se puede acceder a la fuente NuGet necesaria, quizás debido a un problema con la conexión a Internet.</span><span class="sxs-lookup"><span data-stu-id="5d839-183">The required NuGet feed can't be accessed, perhaps because of an Internet connection problem.</span></span>

<span data-ttu-id="5d839-184">La instalación de la herramienta requiere acceso a la fuente NuGet que contiene el paquete de la herramienta.</span><span class="sxs-lookup"><span data-stu-id="5d839-184">Tool installation requires access to the NuGet feed that contains the tool package.</span></span> <span data-ttu-id="5d839-185">Se produce un error si la fuente no está disponible.</span><span class="sxs-lookup"><span data-stu-id="5d839-185">It fails if the feed isn't available.</span></span> <span data-ttu-id="5d839-186">Puede modificar las fuentes con `nuget.config`, solicitar un archivo `nuget.config` determinado o especificar fuentes adicionales con el modificador `--add-source`.</span><span class="sxs-lookup"><span data-stu-id="5d839-186">You can alter feeds with `nuget.config`, request a specific `nuget.config` file, or specify additional feeds with the `--add-source` switch.</span></span> <span data-ttu-id="5d839-187">De forma predeterminada, NuGet genera un error para cualquier fuente con la que no pueda conectar.</span><span class="sxs-lookup"><span data-stu-id="5d839-187">By default, NuGet throws an error for any feed that can't connect.</span></span> <span data-ttu-id="5d839-188">La marca `--ignore-failed-sources` puede omitir estos orígenes no accesibles.</span><span class="sxs-lookup"><span data-stu-id="5d839-188">The flag `--ignore-failed-sources` can skip these non-reachable sources.</span></span>

### <a name="package-id-incorrect"></a><span data-ttu-id="5d839-189">Identificador de paquete incorrecto</span><span class="sxs-lookup"><span data-stu-id="5d839-189">Package ID incorrect</span></span>

* <span data-ttu-id="5d839-190">No ha escrito correctamente el nombre de la herramienta.</span><span class="sxs-lookup"><span data-stu-id="5d839-190">You mistyped the name of the tool.</span></span>

<span data-ttu-id="5d839-191">Un motivo habitual de error es que el nombre de la herramienta no es correcto.</span><span class="sxs-lookup"><span data-stu-id="5d839-191">A common reason for failure is that the tool name isn't correct.</span></span> <span data-ttu-id="5d839-192">Esto puede ocurrir cuando se produce un error de escritura, o porque la herramienta se ha movido o está en desuso.</span><span class="sxs-lookup"><span data-stu-id="5d839-192">This can happen because of mistyping, or because the tool has moved or been deprecated.</span></span> <span data-ttu-id="5d839-193">En el caso de las herramientas de NuGet.org, una manera de asegurarse de que tiene el nombre correcto es buscar la herramienta en NuGet.org y copiar el comando de instalación.</span><span class="sxs-lookup"><span data-stu-id="5d839-193">For tools on NuGet.org, one way to ensure you have the name correct is to search for the tool at NuGet.org and copy the installation command.</span></span>

## <a name="see-also"></a><span data-ttu-id="5d839-194">Vea también</span><span class="sxs-lookup"><span data-stu-id="5d839-194">See also</span></span>

* [<span data-ttu-id="5d839-195">Herramientas de .NET</span><span class="sxs-lookup"><span data-stu-id="5d839-195">.NET tools</span></span>](global-tools.md)
