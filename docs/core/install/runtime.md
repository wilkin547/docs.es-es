---
title: 'Instalación del entorno de ejecución de .NET Core en Windows, Linux y macOS: .NET Core'
description: Obtenga información sobre cómo instalar .NET Core en Windows, Linux y macOS. Descubra las dependencias necesarias para ejecutar aplicaciones de .NET Core.
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: a41bbdf5419585f06773583dbe82ab0d84ebaa4c
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78157641"
---
# <a name="install-the-net-core-runtime"></a><span data-ttu-id="2c637-104">Instalación del entorno de ejecución de .NET Core</span><span class="sxs-lookup"><span data-stu-id="2c637-104">Install the .NET Core Runtime</span></span>

<span data-ttu-id="2c637-105">En este artículo, obtendrá información sobre cómo descargar e instalar el entorno de ejecución de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2c637-105">In this article, you'll learn how to download and install the .NET Core runtime.</span></span> <span data-ttu-id="2c637-106">El entorno de ejecución de .NET Core se usa para ejecutar aplicaciones creadas con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2c637-106">The .NET Core runtime is used to run apps created with .NET Core.</span></span>

::: zone pivot="os-windows"

## <a name="install-with-an-installer"></a><span data-ttu-id="2c637-107">Instalación mediante un instalador</span><span class="sxs-lookup"><span data-stu-id="2c637-107">Install with an installer</span></span>

<span data-ttu-id="2c637-108">Windows tiene instaladores independientes que se pueden usar para instalar el entorno de ejecución de .NET Core 3.1:</span><span class="sxs-lookup"><span data-stu-id="2c637-108">Windows has standalone installers that can be used to install the .NET Core 3.1 runtime:</span></span>

- [<span data-ttu-id="2c637-109">CPU de x64 (64 bits)</span><span class="sxs-lookup"><span data-stu-id="2c637-109">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="2c637-110">CPU de x86 (32 bits)</span><span class="sxs-lookup"><span data-stu-id="2c637-110">x86 (32-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-an-installer"></a><span data-ttu-id="2c637-111">Instalación mediante un instalador</span><span class="sxs-lookup"><span data-stu-id="2c637-111">Install with an installer</span></span>

<span data-ttu-id="2c637-112">macOS tiene instaladores independientes que se pueden usar para instalar el entorno de ejecución de .NET Core 3.1:</span><span class="sxs-lookup"><span data-stu-id="2c637-112">macOS has standalone installers that can be used to install the .NET Core 3.1 runtime:</span></span>

- [<span data-ttu-id="2c637-113">CPU de x64 (64 bits)</span><span class="sxs-lookup"><span data-stu-id="2c637-113">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

## <a name="download-and-manually-install"></a><span data-ttu-id="2c637-114">Descarga e instalación de forma manual</span><span class="sxs-lookup"><span data-stu-id="2c637-114">Download and manually install</span></span>

<span data-ttu-id="2c637-115">Como alternativa a los instaladores de macOS para .NET Core, puede descargar e instalar manualmente el entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="2c637-115">As an alternative to the macOS installers for .NET Core, you can download and manually install the runtime.</span></span>

<span data-ttu-id="2c637-116">Para instalar el entorno de ejecución y hacer que los comandos de la CLI de .NET Core estén disponibles en el terminal, en primer lugar [descargue](#all-net-core-downloads) una versión binaria de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2c637-116">To install the runtime and enable the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="2c637-117">Después, abra un terminal y ejecute los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="2c637-117">Then, open a terminal and run the following commands.</span></span> <span data-ttu-id="2c637-118">Se supone que el entorno de ejecución se ha descargado al archivo `~/Downloads/dotnet-runtime.pkg`.</span><span class="sxs-lookup"><span data-stu-id="2c637-118">It's assumed the runtime is downloaded to the `~/Downloads/dotnet-runtime.pkg` file.</span></span>

```bash
mkdir -p $HOME/dotnet
sudo installer -pkg ~/Downloads/dotnet-runtime.pkg -target $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

::: zone-end

::: zone pivot="os-linux"

## <a name="install-with-a-package-manager"></a><span data-ttu-id="2c637-119">Instalación con un administrador de paquetes</span><span class="sxs-lookup"><span data-stu-id="2c637-119">Install with a package manager</span></span>

<span data-ttu-id="2c637-120">Se puede instalar el entorno de ejecución de .NET Core con muchos de los administradores de paquetes comunes de Linux.</span><span class="sxs-lookup"><span data-stu-id="2c637-120">You can install the .NET Core Runtime with many of the common Linux package managers.</span></span> <span data-ttu-id="2c637-121">Para obtener más información, vea [Administrador de paquetes de Linux: instalación de .NET Core](linux-package-managers.md).</span><span class="sxs-lookup"><span data-stu-id="2c637-121">For more information, see [Linux Package Manager - Install .NET Core](linux-package-managers.md).</span></span>

<span data-ttu-id="2c637-122">Su instalación con un administrador de paquetes solo se admite en la arquitectura x64.</span><span class="sxs-lookup"><span data-stu-id="2c637-122">Installing it with a package manager is only supported on the x64 architecture.</span></span> <span data-ttu-id="2c637-123">Si va a instalar el runtime de .NET Core con otra arquitectura, como ARM, siga las instrucciones de la sección [Descarga e instalación de forma manual](#download-and-manually-install).</span><span class="sxs-lookup"><span data-stu-id="2c637-123">If you're installing the .NET Core Runtime with a different architecture, such as ARM, follow the instructions on the [Download and manually install](#download-and-manually-install) section.</span></span> <span data-ttu-id="2c637-124">Para obtener más información sobre qué arquitecturas se admiten, consulte [Dependencias y requisitos de .NET Core](dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="2c637-124">For more information about what architectures are supported, see [.NET Core dependencies and requirements](dependencies.md).</span></span>

## <a name="download-and-manually-install"></a><span data-ttu-id="2c637-125">Descarga e instalación de forma manual</span><span class="sxs-lookup"><span data-stu-id="2c637-125">Download and manually install</span></span>

<span data-ttu-id="2c637-126">Para extraer el runtime y hacer que los comandos de la CLI de .NET Core estén disponibles en el terminal, en primer lugar [descargue](#all-net-core-downloads) una versión binaria de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2c637-126">To extract the runtime and make the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="2c637-127">Después, abra un terminal y ejecute los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="2c637-127">Then, open a terminal and run the following commands.</span></span>

```bash
mkdir -p $HOME/dotnet && tar zxf aspnetcore-runtime-3.1.0-linux-x64.tar.gz -C $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> <span data-ttu-id="2c637-128">Los comandos `export` anteriores solo hacen que los comandos de la CLI de .NET Core estén disponibles para la sesión de terminal en la que se ha ejecutado.</span><span class="sxs-lookup"><span data-stu-id="2c637-128">The preceding `export` commands only make the .NET Core CLI commands available for the terminal session in which it was run.</span></span>
>
> <span data-ttu-id="2c637-129">Puede editar el perfil del shell para agregar los comandos de forma permanente.</span><span class="sxs-lookup"><span data-stu-id="2c637-129">You can edit your shell profile to permanently add the commands.</span></span> <span data-ttu-id="2c637-130">Hay una serie de shells distintos disponibles para Linux, y cada uno de ellos tiene un perfil diferente.</span><span class="sxs-lookup"><span data-stu-id="2c637-130">There are a number of different shells available for Linux and each has a different profile.</span></span> <span data-ttu-id="2c637-131">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2c637-131">For example:</span></span>
>
> - <span data-ttu-id="2c637-132">**Shell de Bash**: *~/.bash_profile*, *~/.bashrc*</span><span class="sxs-lookup"><span data-stu-id="2c637-132">**Bash Shell**: *~/.bash_profile*, *~/.bashrc*</span></span>
> - <span data-ttu-id="2c637-133">**Shell de Korn**: *~/.kshrc* or *.profile*</span><span class="sxs-lookup"><span data-stu-id="2c637-133">**Korn Shell**: *~/.kshrc* or *.profile*</span></span>
> - <span data-ttu-id="2c637-134">**Shell de Z**: *~/.zshrc* or *.zprofile*</span><span class="sxs-lookup"><span data-stu-id="2c637-134">**Z Shell**: *~/.zshrc* or *.zprofile*</span></span>
>
> <span data-ttu-id="2c637-135">Edite el archivo de origen adecuado para el shell y agregue `:$HOME/dotnet` al final de la instrucción `PATH` existente.</span><span class="sxs-lookup"><span data-stu-id="2c637-135">Edit the appropriate source file for your shell and add `:$HOME/dotnet` to the end of the existing `PATH` statement.</span></span> <span data-ttu-id="2c637-136">Si no se incluye ninguna instrucción `PATH`, agregue una nueva línea con `export PATH=$PATH:$HOME/dotnet`.</span><span class="sxs-lookup"><span data-stu-id="2c637-136">If no `PATH` statement is included, add a new line with `export PATH=$PATH:$HOME/dotnet`.</span></span>
>
> <span data-ttu-id="2c637-137">Además, agregue `export DOTNET_ROOT=$HOME/dotnet` al final del archivo.</span><span class="sxs-lookup"><span data-stu-id="2c637-137">Also, add `export DOTNET_ROOT=$HOME/dotnet` to the end of the file.</span></span>

<span data-ttu-id="2c637-138">Este enfoque le permite instalar diferentes versiones en ubicaciones independientes y elegir explícitamente cuál usará cada aplicación.</span><span class="sxs-lookup"><span data-stu-id="2c637-138">This approach lets you install different versions into separate locations and choose explicitly which one to use by which application.</span></span>

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a><span data-ttu-id="2c637-139">Instalación mediante la automatización de PowerShell</span><span class="sxs-lookup"><span data-stu-id="2c637-139">Install with PowerShell automation</span></span>

<span data-ttu-id="2c637-140">Los [scripts de dotnet-install](../tools/dotnet-install-script.md) se usan para la automatización y las instalaciones que no son de administrador del entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="2c637-140">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="2c637-141">Se puede descargar el script desde la [página de referencia del script dotnet-install](../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="2c637-141">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="2c637-142">El valor predeterminado del script es instalar la versión más reciente de [soporte técnico a largo plazo (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), que actualmente es .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="2c637-142">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="2c637-143">Puede elegir una versión concreta especificando el modificador `Channel`.</span><span class="sxs-lookup"><span data-stu-id="2c637-143">You can choose a specific release by specifying the `Channel` switch.</span></span> <span data-ttu-id="2c637-144">Incluya el modificador `Runtime` para instalar un entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="2c637-144">Include the `Runtime` switch to install a runtime.</span></span> <span data-ttu-id="2c637-145">De lo contrario, el script instala el [SDK](sdk.md).</span><span class="sxs-lookup"><span data-stu-id="2c637-145">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```powershell
dotnet-install.ps1 -Channel 3.1 -Runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="2c637-146">El comando anterior instala el entorno de ejecución de ASP.NET Core para obtener la máxima compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="2c637-146">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="2c637-147">El entorno de ejecución de ASP.NET Core también incluye el estándar de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2c637-147">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

## <a name="download-and-manually-install"></a><span data-ttu-id="2c637-148">Descarga e instalación de forma manual</span><span class="sxs-lookup"><span data-stu-id="2c637-148">Download and manually install</span></span>

<span data-ttu-id="2c637-149">Para extraer el runtime y hacer que los comandos de la CLI de .NET Core estén disponibles en el terminal, en primer lugar [descargue](#all-net-core-downloads) una versión binaria de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2c637-149">To extract the runtime and make the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="2c637-150">A continuación, cree un directorio para la instalación, por ejemplo `%USERPROFILE%\dotnet`.</span><span class="sxs-lookup"><span data-stu-id="2c637-150">Then, create a directory to install to, for example `%USERPROFILE%\dotnet`.</span></span> <span data-ttu-id="2c637-151">Por último, extraiga el archivo zip descargado en ese directorio.</span><span class="sxs-lookup"><span data-stu-id="2c637-151">Finally, extract the downloaded zip file into that directory.</span></span>

<span data-ttu-id="2c637-152">De forma predeterminada, los comandos y las aplicaciones de la CLI de .NET Core no usarán la versión de .NET Core instalada de esta manera.</span><span class="sxs-lookup"><span data-stu-id="2c637-152">By default, .NET Core CLI commands and apps will not use .NET Core installed in this way.</span></span> <span data-ttu-id="2c637-153">Debe optar explícitamente por usarla.</span><span class="sxs-lookup"><span data-stu-id="2c637-153">You have to explicitly choose to use it.</span></span> <span data-ttu-id="2c637-154">Para ello, cambie las variables de entorno con las que se inicia una aplicación:</span><span class="sxs-lookup"><span data-stu-id="2c637-154">To do so, change the environment variables with which an application is started:</span></span>

```console
set DOTNET_ROOT=%USERPROFILE%\dotnet
set PATH=%USERPROFILE%\dotnet;%PATH%
```

<span data-ttu-id="2c637-155">Este enfoque permite instalar varias versiones en ubicaciones independientes y elegir explícitamente qué ubicación de instalación debe usar una aplicación mediante la ejecución de la aplicación con variables de entorno que apuntan a esa ubicación.</span><span class="sxs-lookup"><span data-stu-id="2c637-155">This approach lets you install multiple versions into separate locations, then explicitly choose which install location an application should use by running the application with environment variables pointing at that location.</span></span>

<span data-ttu-id="2c637-156">Incluso cuando se establecen estas variables de entorno, .NET Core sigue teniendo en cuenta la ubicación de instalación global predeterminada al seleccionar el mejor marco para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2c637-156">Even when these environment variables are set, .NET Core still considers the default global install location when selecting the best framework for running the application.</span></span> <span data-ttu-id="2c637-157">Normalmente, el valor predeterminado es `C:\Program Files\dotnet`, que usan los instaladores.</span><span class="sxs-lookup"><span data-stu-id="2c637-157">The default is typically `C:\Program Files\dotnet`, which the installers use.</span></span> <span data-ttu-id="2c637-158">Puede indicar al motor en tiempo de ejecución que solo use la ubicación de instalación personalizada mediante la configuración de esta variable de entorno:</span><span class="sxs-lookup"><span data-stu-id="2c637-158">You can instruct the runtime to only use the custom install location by setting this environment variable as well:</span></span>

```console
set DOTNET_MULTILEVEL_LOOKUP=0
```

::: zone-end

::: zone pivot="os-linux,os-macos"

## <a name="install-with-bash-automation"></a><span data-ttu-id="2c637-159">Instalación mediante la automatización de Bash</span><span class="sxs-lookup"><span data-stu-id="2c637-159">Install with bash automation</span></span>

<span data-ttu-id="2c637-160">Los [scripts de dotnet-install](../tools/dotnet-install-script.md) se usan para la automatización y las instalaciones que no son de administrador del entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="2c637-160">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="2c637-161">Se puede descargar el script desde la [página de referencia del script dotnet-install](../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="2c637-161">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="2c637-162">El valor predeterminado del script es instalar la versión más reciente de [soporte técnico a largo plazo (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), que actualmente es .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="2c637-162">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="2c637-163">Puede elegir una versión concreta especificando el modificador `current`.</span><span class="sxs-lookup"><span data-stu-id="2c637-163">You can choose a specific release by specifying the `current` switch.</span></span> <span data-ttu-id="2c637-164">Incluya el modificador `runtime` para instalar un entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="2c637-164">Include the `runtime` switch to install a runtime.</span></span> <span data-ttu-id="2c637-165">De lo contrario, el script instala el [SDK](sdk.md).</span><span class="sxs-lookup"><span data-stu-id="2c637-165">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```bash
./dotnet-install.sh --channel 3.1 --runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="2c637-166">El comando anterior instala el entorno de ejecución de ASP.NET Core para obtener la máxima compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="2c637-166">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="2c637-167">El entorno de ejecución de ASP.NET Core también incluye el estándar de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2c637-167">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

::: zone-end

## <a name="all-net-core-downloads"></a><span data-ttu-id="2c637-168">Todas las descargas de .NET Core</span><span class="sxs-lookup"><span data-stu-id="2c637-168">All .NET Core downloads</span></span>

<span data-ttu-id="2c637-169">Puede descargar e instalar .NET Core directamente con uno de los vínculos siguientes:</span><span class="sxs-lookup"><span data-stu-id="2c637-169">You can download and install .NET Core directly with one of the following links:</span></span>

- [<span data-ttu-id="2c637-170">Descargas de .NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="2c637-170">.NET Core 3.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="2c637-171">Descargas de .NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="2c637-171">.NET Core 3.0 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.0)
- [<span data-ttu-id="2c637-172">Descargas de .NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="2c637-172">.NET Core 2.2 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.2)
- [<span data-ttu-id="2c637-173">Descargas de .NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="2c637-173">.NET Core 2.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.1)

## <a name="docker"></a><span data-ttu-id="2c637-174">Docker</span><span class="sxs-lookup"><span data-stu-id="2c637-174">Docker</span></span>

<span data-ttu-id="2c637-175">Los contenedores proporcionan una manera ligera de aislar la aplicación del resto del sistema host.</span><span class="sxs-lookup"><span data-stu-id="2c637-175">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="2c637-176">Los contenedores de la misma máquina comparten solo el kernel y usan los recursos proporcionados a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2c637-176">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="2c637-177">.NET Core puede ejecutarse en un contenedor de Docker.</span><span class="sxs-lookup"><span data-stu-id="2c637-177">.NET Core can run in a Docker container.</span></span> <span data-ttu-id="2c637-178">Las imágenes oficiales de Docker en .NET Core se publican en el registro de contenedor de Microsoft (MCR) y se pueden encontrar en el [repositorio de Docker Hub para Microsoft .NET Core](https://hub.docker.com/_/microsoft-dotnet-core/).</span><span class="sxs-lookup"><span data-stu-id="2c637-178">Official .NET Core Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span> <span data-ttu-id="2c637-179">Cada repositorio contiene imágenes para diferentes combinaciones de .NET (SDK o Runtime) y del sistema operativo que puede usar.</span><span class="sxs-lookup"><span data-stu-id="2c637-179">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="2c637-180">Microsoft ofrece imágenes que se adaptan a escenarios específicos.</span><span class="sxs-lookup"><span data-stu-id="2c637-180">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="2c637-181">Por ejemplo, el [repositorio de ASP.NET Core](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) proporciona imágenes que se compilan para ejecutar aplicaciones de ASP.NET Core en producción.</span><span class="sxs-lookup"><span data-stu-id="2c637-181">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="2c637-182">Para obtener más información sobre el uso de .NET Core en un contenedor de Docker, vea [Introducción a .NET y Docker](../docker/introduction.md) y [Ejemplos](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span><span class="sxs-lookup"><span data-stu-id="2c637-182">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="2c637-183">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="2c637-183">Next steps</span></span>

- <span data-ttu-id="2c637-184">[Cómo comprobar que .NET Core ya está instalado](how-to-detect-installed-versions.md).</span><span class="sxs-lookup"><span data-stu-id="2c637-184">[How to check if .NET Core is already installed](how-to-detect-installed-versions.md).</span></span>
