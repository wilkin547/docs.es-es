---
title: 'Instalación del entorno de ejecución de .NET Core en Windows, Linux y macOS: .NET Core'
description: Obtenga información sobre cómo instalar .NET Core en Windows, Linux y macOS. Descubra las dependencias necesarias para ejecutar aplicaciones de .NET Core.
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: d36909e06bd9a3de0940c4c1b2b9eacbf9cafe7f
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740595"
---
# <a name="install-the-net-core-runtime"></a><span data-ttu-id="27dc1-104">Instalación del entorno de ejecución de .NET Core</span><span class="sxs-lookup"><span data-stu-id="27dc1-104">Install the .NET Core Runtime</span></span>

<span data-ttu-id="27dc1-105">En este artículo, obtendrá información sobre cómo descargar e instalar el entorno de ejecución de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="27dc1-105">In this article, you'll learn how to download and install the .NET Core runtime.</span></span> <span data-ttu-id="27dc1-106">El entorno de ejecución de .NET Core se usa para ejecutar aplicaciones creadas con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="27dc1-106">The .NET Core runtime is used to run apps created with .NET Core.</span></span>

::: zone pivot="os-windows"

## <a name="install-with-an-installer"></a><span data-ttu-id="27dc1-107">Instalación mediante un instalador</span><span class="sxs-lookup"><span data-stu-id="27dc1-107">Install with an installer</span></span>

<span data-ttu-id="27dc1-108">Windows tiene instaladores independientes que se pueden usar para instalar el entorno de ejecución de .NET Core 3.1:</span><span class="sxs-lookup"><span data-stu-id="27dc1-108">Windows has standalone installers that can be used to install the .NET Core 3.1 runtime:</span></span>

- [<span data-ttu-id="27dc1-109">CPU de x64 (64 bits)</span><span class="sxs-lookup"><span data-stu-id="27dc1-109">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="27dc1-110">CPU de x86 (32 bits)</span><span class="sxs-lookup"><span data-stu-id="27dc1-110">x86 (32-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-an-installer"></a><span data-ttu-id="27dc1-111">Instalación mediante un instalador</span><span class="sxs-lookup"><span data-stu-id="27dc1-111">Install with an installer</span></span>

<span data-ttu-id="27dc1-112">macOS tiene instaladores independientes que se pueden usar para instalar el entorno de ejecución de .NET Core 3.1:</span><span class="sxs-lookup"><span data-stu-id="27dc1-112">macOS has standalone installers that can be used to install the .NET Core 3.1 runtime:</span></span>

- [<span data-ttu-id="27dc1-113">CPU de x64 (64 bits)</span><span class="sxs-lookup"><span data-stu-id="27dc1-113">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-linux"

## <a name="install-with-a-package-manager"></a><span data-ttu-id="27dc1-114">Instalación con un administrador de paquetes</span><span class="sxs-lookup"><span data-stu-id="27dc1-114">Install with a package manager</span></span>

<span data-ttu-id="27dc1-115">Se puede instalar el entorno de ejecución de .NET Core con muchos de los administradores de paquetes comunes de Linux.</span><span class="sxs-lookup"><span data-stu-id="27dc1-115">You can install the .NET Core Runtime with many of the common Linux package managers.</span></span> <span data-ttu-id="27dc1-116">Para obtener más información, vea [Administrador de paquetes de Linux: instalación de .NET Core](linux-package-managers.md).</span><span class="sxs-lookup"><span data-stu-id="27dc1-116">For more information, see [Linux Package Manager - Install .NET Core](linux-package-managers.md).</span></span>

<span data-ttu-id="27dc1-117">Su instalación con un administrador de paquetes solo se admite en la arquitectura x64.</span><span class="sxs-lookup"><span data-stu-id="27dc1-117">Installing it with a package manager is only supported on the x64 architecture.</span></span> <span data-ttu-id="27dc1-118">Si va a instalar el runtime de .NET Core con otra arquitectura, como ARM, siga las instrucciones de la sección [Descarga e instalación de forma manual](#download-and-manually-install).</span><span class="sxs-lookup"><span data-stu-id="27dc1-118">If you're installing the .NET Core Runtime with a different architecture, such as ARM, follow the instructions on the [Download and manually install](#download-and-manually-install) section.</span></span> <span data-ttu-id="27dc1-119">Para obtener más información sobre qué arquitecturas se admiten, consulte [Dependencias y requisitos de .NET Core](dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="27dc1-119">For more information about what architectures are supported, see [.NET Core dependencies and requirements](dependencies.md).</span></span>

## <a name="download-and-manually-install"></a><span data-ttu-id="27dc1-120">Descarga e instalación de forma manual</span><span class="sxs-lookup"><span data-stu-id="27dc1-120">Download and manually install</span></span>

<span data-ttu-id="27dc1-121">Para extraer el runtime y hacer que los comandos de la CLI de .NET Core estén disponibles en el terminal, en primer lugar [descargue](#all-net-core-downloads) una versión binaria de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="27dc1-121">To extract the runtime and make the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="27dc1-122">Después, abra un terminal y ejecute los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="27dc1-122">Then, open a terminal and run the following commands.</span></span>

```bash
mkdir -p $HOME/dotnet && tar zxf aspnetcore-runtime-3.1.0-linux-x64.tar.gz -C $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> <span data-ttu-id="27dc1-123">Los comandos `export` anteriores solo hacen que los comandos de la CLI de .NET Core estén disponibles para la sesión de terminal en la que se ha ejecutado.</span><span class="sxs-lookup"><span data-stu-id="27dc1-123">The preceding `export` commands only make the .NET Core CLI commands available for the terminal session in which it was run.</span></span>
>
> <span data-ttu-id="27dc1-124">Puede editar el perfil del shell para agregar los comandos de forma permanente.</span><span class="sxs-lookup"><span data-stu-id="27dc1-124">You can edit your shell profile to permanently add the commands.</span></span> <span data-ttu-id="27dc1-125">Hay una serie de shells distintos disponibles para Linux, y cada uno de ellos tiene un perfil diferente.</span><span class="sxs-lookup"><span data-stu-id="27dc1-125">There are a number of different shells available for Linux and each has a different profile.</span></span> <span data-ttu-id="27dc1-126">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="27dc1-126">For example:</span></span>
>
> - <span data-ttu-id="27dc1-127">**Shell de Bash**: *~/.bash_profile*, *~/.bashrc*</span><span class="sxs-lookup"><span data-stu-id="27dc1-127">**Bash Shell**: *~/.bash_profile*, *~/.bashrc*</span></span>
> - <span data-ttu-id="27dc1-128">**Shell de Korn**: *~/.kshrc* or *.profile*</span><span class="sxs-lookup"><span data-stu-id="27dc1-128">**Korn Shell**: *~/.kshrc* or *.profile*</span></span>
> - <span data-ttu-id="27dc1-129">**Shell de Z**: *~/.zshrc* or *.zprofile*</span><span class="sxs-lookup"><span data-stu-id="27dc1-129">**Z Shell**: *~/.zshrc* or *.zprofile*</span></span>
> 
> <span data-ttu-id="27dc1-130">Edite el archivo de origen adecuado para el shell y agregue `:$HOME/dotnet` al final de la instrucción `PATH` existente.</span><span class="sxs-lookup"><span data-stu-id="27dc1-130">Edit the appropriate source file for your shell and add `:$HOME/dotnet` to the end of the existing `PATH` statement.</span></span> <span data-ttu-id="27dc1-131">Si no se incluye ninguna instrucción `PATH`, agregue una nueva línea con `export PATH=$PATH:$HOME/dotnet`.</span><span class="sxs-lookup"><span data-stu-id="27dc1-131">If no `PATH` statement is included, add a new line with `export PATH=$PATH:$HOME/dotnet`.</span></span>
>
> <span data-ttu-id="27dc1-132">Además, agregue `export DOTNET_ROOT=$HOME/dotnet` al final del archivo.</span><span class="sxs-lookup"><span data-stu-id="27dc1-132">Also, add `export DOTNET_ROOT=$HOME/dotnet` to the end of the file.</span></span>

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a><span data-ttu-id="27dc1-133">Instalación mediante la automatización de PowerShell</span><span class="sxs-lookup"><span data-stu-id="27dc1-133">Install with PowerShell automation</span></span>

<span data-ttu-id="27dc1-134">Los [scripts de dotnet-install](../tools/dotnet-install-script.md) se usan para la automatización y las instalaciones que no son de administrador del entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="27dc1-134">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="27dc1-135">Se puede descargar el script desde la [página de referencia del script dotnet-install](../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="27dc1-135">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="27dc1-136">El valor predeterminado del script es instalar la versión más reciente de [soporte técnico a largo plazo (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), que actualmente es .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="27dc1-136">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="27dc1-137">Puede elegir una versión concreta especificando el modificador `Channel`.</span><span class="sxs-lookup"><span data-stu-id="27dc1-137">You can choose a specific release by specifying the `Channel` switch.</span></span> <span data-ttu-id="27dc1-138">Incluya el modificador `Runtime` para instalar un entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="27dc1-138">Include the `Runtime` switch to install a runtime.</span></span> <span data-ttu-id="27dc1-139">De lo contrario, el script instala el [SDK](sdk.md).</span><span class="sxs-lookup"><span data-stu-id="27dc1-139">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```powershell
dotnet-install.ps1 -Channel 3.1 -Runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="27dc1-140">El comando anterior instala el entorno de ejecución de ASP.NET Core para obtener la máxima compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="27dc1-140">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="27dc1-141">El entorno de ejecución de ASP.NET Core también incluye el estándar de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="27dc1-141">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

::: zone-end

::: zone pivot="os-linux,os-macos"

## <a name="install-with-bash-automation"></a><span data-ttu-id="27dc1-142">Instalación mediante la automatización de Bash</span><span class="sxs-lookup"><span data-stu-id="27dc1-142">Install with bash automation</span></span>

<span data-ttu-id="27dc1-143">Los [scripts de dotnet-install](../tools/dotnet-install-script.md) se usan para la automatización y las instalaciones que no son de administrador del entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="27dc1-143">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="27dc1-144">Se puede descargar el script desde la [página de referencia del script dotnet-install](../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="27dc1-144">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="27dc1-145">El valor predeterminado del script es instalar la versión más reciente de [soporte técnico a largo plazo (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), que actualmente es .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="27dc1-145">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="27dc1-146">Puede elegir una versión concreta especificando el modificador `current`.</span><span class="sxs-lookup"><span data-stu-id="27dc1-146">You can choose a specific release by specifying the `current` switch.</span></span> <span data-ttu-id="27dc1-147">Incluya el modificador `runtime` para instalar un entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="27dc1-147">Include the `runtime` switch to install a runtime.</span></span> <span data-ttu-id="27dc1-148">De lo contrario, el script instala el [SDK](sdk.md).</span><span class="sxs-lookup"><span data-stu-id="27dc1-148">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```bash
./dotnet-install.sh --channel 3.1 --runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="27dc1-149">El comando anterior instala el entorno de ejecución de ASP.NET Core para obtener la máxima compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="27dc1-149">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="27dc1-150">El entorno de ejecución de ASP.NET Core también incluye el estándar de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="27dc1-150">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

::: zone-end

## <a name="all-net-core-downloads"></a><span data-ttu-id="27dc1-151">Todas las descargas de .NET Core</span><span class="sxs-lookup"><span data-stu-id="27dc1-151">All .NET Core downloads</span></span>

<span data-ttu-id="27dc1-152">Puede descargar e instalar .NET Core directamente con uno de los vínculos siguientes:</span><span class="sxs-lookup"><span data-stu-id="27dc1-152">You can download and install .NET Core directly with one of the following links:</span></span>

- [<span data-ttu-id="27dc1-153">Descargas de .NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="27dc1-153">.NET Core 3.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="27dc1-154">Descargas de .NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="27dc1-154">.NET Core 3.0 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.0)
- [<span data-ttu-id="27dc1-155">Descargas de .NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="27dc1-155">.NET Core 2.2 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.2)
- [<span data-ttu-id="27dc1-156">Descargas de .NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="27dc1-156">.NET Core 2.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.1)

## <a name="docker"></a><span data-ttu-id="27dc1-157">Docker</span><span class="sxs-lookup"><span data-stu-id="27dc1-157">Docker</span></span>

<span data-ttu-id="27dc1-158">Los contenedores proporcionan una manera ligera de aislar la aplicación del resto del sistema host.</span><span class="sxs-lookup"><span data-stu-id="27dc1-158">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="27dc1-159">Los contenedores de la misma máquina comparten solo el kernel y usan los recursos proporcionados a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="27dc1-159">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="27dc1-160">.NET Core puede ejecutarse en un contenedor de Docker.</span><span class="sxs-lookup"><span data-stu-id="27dc1-160">.NET Core can run in a Docker container.</span></span> <span data-ttu-id="27dc1-161">Las imágenes oficiales de Docker en .NET Core se publican en el registro de contenedor de Microsoft (MCR) y se pueden encontrar en el [repositorio de Docker Hub para Microsoft .NET Core](https://hub.docker.com/_/microsoft-dotnet-core/).</span><span class="sxs-lookup"><span data-stu-id="27dc1-161">Official .NET Core Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span> <span data-ttu-id="27dc1-162">Cada repositorio contiene imágenes para diferentes combinaciones de .NET (SDK o Runtime) y del sistema operativo que puede usar.</span><span class="sxs-lookup"><span data-stu-id="27dc1-162">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="27dc1-163">Microsoft ofrece imágenes que se adaptan a escenarios específicos.</span><span class="sxs-lookup"><span data-stu-id="27dc1-163">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="27dc1-164">Por ejemplo, el [repositorio de ASP.NET Core](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) proporciona imágenes que se compilan para ejecutar aplicaciones de ASP.NET Core en producción.</span><span class="sxs-lookup"><span data-stu-id="27dc1-164">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="27dc1-165">Para obtener más información sobre el uso de .NET Core en un contenedor de Docker, vea [Introducción a .NET y Docker](../docker/introduction.md) y [Ejemplos](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span><span class="sxs-lookup"><span data-stu-id="27dc1-165">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="27dc1-166">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="27dc1-166">Next steps</span></span>

- <span data-ttu-id="27dc1-167">[Cómo comprobar que .NET Core ya está instalado](how-to-detect-installed-versions.md).</span><span class="sxs-lookup"><span data-stu-id="27dc1-167">[How to check if .NET Core is already installed](how-to-detect-installed-versions.md).</span></span>
