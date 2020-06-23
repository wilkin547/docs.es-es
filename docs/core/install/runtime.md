---
title: 'Instalación del entorno de ejecución de .NET Core en Windows, Linux y macOS: .NET Core'
description: Obtenga información sobre cómo instalar .NET Core en Windows, Linux y macOS. Descubra las dependencias necesarias para ejecutar aplicaciones de .NET Core.
author: thraka
ms.author: adegeo
ms.date: 05/04/2020
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: d3f7083366e2019d01884b5dff6e60d05ed565dd
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2020
ms.locfileid: "84768292"
---
# <a name="install-the-net-core-runtime"></a><span data-ttu-id="747f7-104">Instalación del entorno de ejecución de .NET Core</span><span class="sxs-lookup"><span data-stu-id="747f7-104">Install the .NET Core Runtime</span></span>

<span data-ttu-id="747f7-105">En este artículo, obtendrá información sobre cómo descargar e instalar el entorno de ejecución de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="747f7-105">In this article, you'll learn how to download and install the .NET Core runtime.</span></span> <span data-ttu-id="747f7-106">El entorno de ejecución de .NET Core se usa para ejecutar aplicaciones creadas con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="747f7-106">The .NET Core runtime is used to run apps created with .NET Core.</span></span>

::: zone pivot="os-windows"

## <a name="install-with-an-installer"></a><span data-ttu-id="747f7-107">Instalación mediante un instalador</span><span class="sxs-lookup"><span data-stu-id="747f7-107">Install with an installer</span></span>

<span data-ttu-id="747f7-108">Windows tiene instaladores independientes que se pueden usar para instalar el entorno de ejecución de .NET Core 3.1:</span><span class="sxs-lookup"><span data-stu-id="747f7-108">Windows has standalone installers that can be used to install the .NET Core 3.1 runtime:</span></span>

- [<span data-ttu-id="747f7-109">CPU de x64 (64 bits)</span><span class="sxs-lookup"><span data-stu-id="747f7-109">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="747f7-110">CPU de x86 (32 bits)</span><span class="sxs-lookup"><span data-stu-id="747f7-110">x86 (32-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-an-installer"></a><span data-ttu-id="747f7-111">Instalación mediante un instalador</span><span class="sxs-lookup"><span data-stu-id="747f7-111">Install with an installer</span></span>

<span data-ttu-id="747f7-112">macOS tiene instaladores independientes que se pueden usar para instalar el entorno de ejecución de .NET Core 3.1:</span><span class="sxs-lookup"><span data-stu-id="747f7-112">macOS has standalone installers that can be used to install the .NET Core 3.1 runtime:</span></span>

- [<span data-ttu-id="747f7-113">CPU de x64 (64 bits)</span><span class="sxs-lookup"><span data-stu-id="747f7-113">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

## <a name="download-and-manually-install"></a><span data-ttu-id="747f7-114">Descarga e instalación de forma manual</span><span class="sxs-lookup"><span data-stu-id="747f7-114">Download and manually install</span></span>

<span data-ttu-id="747f7-115">Como alternativa a los instaladores de macOS para .NET Core, puede descargar e instalar manualmente el entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="747f7-115">As an alternative to the macOS installers for .NET Core, you can download and manually install the runtime.</span></span>

<span data-ttu-id="747f7-116">Para instalar el entorno de ejecución y hacer que los comandos de la CLI de .NET Core estén disponibles en el terminal, en primer lugar [descargue](#all-net-core-downloads) una versión binaria de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="747f7-116">To install the runtime and enable the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="747f7-117">Después, abra un terminal y ejecute los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="747f7-117">Then, open a terminal and run the following commands.</span></span> <span data-ttu-id="747f7-118">Se supone que el entorno de ejecución se ha descargado al archivo `~/Downloads/dotnet-runtime.pkg`.</span><span class="sxs-lookup"><span data-stu-id="747f7-118">It's assumed the runtime is downloaded to the `~/Downloads/dotnet-runtime.pkg` file.</span></span>

```bash
mkdir -p $HOME/dotnet
sudo installer -pkg ~/Downloads/dotnet-runtime.pkg -target $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

::: zone-end

::: zone pivot="os-linux"

## <a name="install-on-linux"></a><span data-ttu-id="747f7-119">Instalar en Linux</span><span class="sxs-lookup"><span data-stu-id="747f7-119">Install on Linux</span></span>

<span data-ttu-id="747f7-120">Este artículo se retirará pronto.</span><span class="sxs-lookup"><span data-stu-id="747f7-120">This article will be removed soon.</span></span> <span data-ttu-id="747f7-121">En este momento se reemplaza por [Instalación de .NET Core en Linux](linux.md).</span><span class="sxs-lookup"><span data-stu-id="747f7-121">It is currently replaced by [Install .NET Core on Linux](linux.md).</span></span>

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a><span data-ttu-id="747f7-122">Instalación mediante la automatización de PowerShell</span><span class="sxs-lookup"><span data-stu-id="747f7-122">Install with PowerShell automation</span></span>

<span data-ttu-id="747f7-123">Los [scripts de dotnet-install](../tools/dotnet-install-script.md) se usan para la automatización y las instalaciones que no son de administrador del entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="747f7-123">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="747f7-124">Se puede descargar el script desde la [página de referencia del script dotnet-install](../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="747f7-124">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="747f7-125">El valor predeterminado del script es instalar la versión más reciente de [soporte técnico a largo plazo (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), que actualmente es .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="747f7-125">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="747f7-126">Puede elegir una versión concreta especificando el modificador `Channel`.</span><span class="sxs-lookup"><span data-stu-id="747f7-126">You can choose a specific release by specifying the `Channel` switch.</span></span> <span data-ttu-id="747f7-127">Incluya el modificador `Runtime` para instalar un entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="747f7-127">Include the `Runtime` switch to install a runtime.</span></span> <span data-ttu-id="747f7-128">De lo contrario, el script instala el [SDK](sdk.md).</span><span class="sxs-lookup"><span data-stu-id="747f7-128">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```powershell
dotnet-install.ps1 -Channel 3.1 -Runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="747f7-129">El comando anterior instala el entorno de ejecución de ASP.NET Core para obtener la máxima compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="747f7-129">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="747f7-130">El entorno de ejecución de ASP.NET Core también incluye el estándar de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="747f7-130">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

## <a name="download-and-manually-install"></a><span data-ttu-id="747f7-131">Descarga e instalación de forma manual</span><span class="sxs-lookup"><span data-stu-id="747f7-131">Download and manually install</span></span>

<span data-ttu-id="747f7-132">Para extraer el runtime y hacer que los comandos de la CLI de .NET Core estén disponibles en el terminal, en primer lugar [descargue](#all-net-core-downloads) una versión binaria de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="747f7-132">To extract the runtime and make the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="747f7-133">A continuación, cree un directorio para la instalación, por ejemplo `%USERPROFILE%\dotnet`.</span><span class="sxs-lookup"><span data-stu-id="747f7-133">Then, create a directory to install to, for example `%USERPROFILE%\dotnet`.</span></span> <span data-ttu-id="747f7-134">Por último, extraiga el archivo zip descargado en ese directorio.</span><span class="sxs-lookup"><span data-stu-id="747f7-134">Finally, extract the downloaded zip file into that directory.</span></span>

<span data-ttu-id="747f7-135">De forma predeterminada, los comandos y las aplicaciones de la CLI de .NET Core no usarán la versión de .NET Core instalada de esta manera y debe elegir explícitamente usarla.</span><span class="sxs-lookup"><span data-stu-id="747f7-135">By default, .NET Core CLI commands and apps won't use .NET Core installed in this way and you must explicitly choose to use it.</span></span> <span data-ttu-id="747f7-136">Para ello, cambie las variables de entorno con las que se inicia una aplicación:</span><span class="sxs-lookup"><span data-stu-id="747f7-136">To do so, change the environment variables with which an application is started:</span></span>

```console
set DOTNET_ROOT=%USERPROFILE%\dotnet
set PATH=%USERPROFILE%\dotnet;%PATH%
```

<span data-ttu-id="747f7-137">Este enfoque permite instalar varias versiones en ubicaciones independientes y elegir explícitamente qué ubicación de instalación debe usar una aplicación mediante la ejecución de la aplicación con variables de entorno que apuntan a esa ubicación.</span><span class="sxs-lookup"><span data-stu-id="747f7-137">This approach lets you install multiple versions into separate locations, then explicitly choose which install location an application should use by running the application with environment variables pointing at that location.</span></span>

<span data-ttu-id="747f7-138">Incluso cuando se establecen estas variables de entorno, .NET Core sigue teniendo en cuenta la ubicación de instalación global predeterminada al seleccionar el mejor marco para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="747f7-138">Even when these environment variables are set, .NET Core still considers the default global install location when selecting the best framework for running the application.</span></span> <span data-ttu-id="747f7-139">Normalmente, el valor predeterminado es `C:\Program Files\dotnet`, que usan los instaladores.</span><span class="sxs-lookup"><span data-stu-id="747f7-139">The default is typically `C:\Program Files\dotnet`, which the installers use.</span></span> <span data-ttu-id="747f7-140">Puede indicar al motor en tiempo de ejecución que solo use la ubicación de instalación personalizada mediante la configuración de esta variable de entorno:</span><span class="sxs-lookup"><span data-stu-id="747f7-140">You can instruct the runtime to only use the custom install location by setting this environment variable as well:</span></span>

```console
set DOTNET_MULTILEVEL_LOOKUP=0
```

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-bash-automation"></a><span data-ttu-id="747f7-141">Instalación mediante la automatización de Bash</span><span class="sxs-lookup"><span data-stu-id="747f7-141">Install with bash automation</span></span>

<span data-ttu-id="747f7-142">Los [scripts de dotnet-install](../tools/dotnet-install-script.md) se usan para la automatización y las instalaciones que no son de administrador del entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="747f7-142">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="747f7-143">Se puede descargar el script desde la [página de referencia del script dotnet-install](../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="747f7-143">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="747f7-144">El valor predeterminado del script es instalar la versión más reciente de [soporte técnico a largo plazo (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), que actualmente es .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="747f7-144">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="747f7-145">Puede elegir una versión concreta especificando el modificador `current`.</span><span class="sxs-lookup"><span data-stu-id="747f7-145">You can choose a specific release by specifying the `current` switch.</span></span> <span data-ttu-id="747f7-146">Incluya el modificador `runtime` para instalar un entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="747f7-146">Include the `runtime` switch to install a runtime.</span></span> <span data-ttu-id="747f7-147">De lo contrario, el script instala el [SDK](sdk.md).</span><span class="sxs-lookup"><span data-stu-id="747f7-147">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```bash
./dotnet-install.sh --channel 3.1 --runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="747f7-148">El comando anterior instala el entorno de ejecución de ASP.NET Core para obtener la máxima compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="747f7-148">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="747f7-149">El entorno de ejecución de ASP.NET Core también incluye el estándar de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="747f7-149">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

::: zone-end

## <a name="all-net-core-downloads"></a><span data-ttu-id="747f7-150">Todas las descargas de .NET Core</span><span class="sxs-lookup"><span data-stu-id="747f7-150">All .NET Core downloads</span></span>

<span data-ttu-id="747f7-151">Puede descargar e instalar .NET Core directamente con uno de los vínculos siguientes:</span><span class="sxs-lookup"><span data-stu-id="747f7-151">You can download and install .NET Core directly with one of the following links:</span></span>

- [<span data-ttu-id="747f7-152">Descargas de .NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="747f7-152">.NET Core 3.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="747f7-153">Descargas de .NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="747f7-153">.NET Core 2.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.1)

## <a name="docker"></a><span data-ttu-id="747f7-154">Docker</span><span class="sxs-lookup"><span data-stu-id="747f7-154">Docker</span></span>

<span data-ttu-id="747f7-155">Los contenedores proporcionan una manera ligera de aislar la aplicación del resto del sistema host.</span><span class="sxs-lookup"><span data-stu-id="747f7-155">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="747f7-156">Los contenedores de la misma máquina comparten solo el kernel y usan los recursos proporcionados a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="747f7-156">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="747f7-157">.NET Core puede ejecutarse en un contenedor de Docker.</span><span class="sxs-lookup"><span data-stu-id="747f7-157">.NET Core can run in a Docker container.</span></span> <span data-ttu-id="747f7-158">Las imágenes oficiales de Docker en .NET Core se publican en el registro de contenedor de Microsoft (MCR) y se pueden encontrar en el [repositorio de Docker Hub para Microsoft .NET Core](https://hub.docker.com/_/microsoft-dotnet-core/).</span><span class="sxs-lookup"><span data-stu-id="747f7-158">Official .NET Core Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span> <span data-ttu-id="747f7-159">Cada repositorio contiene imágenes para diferentes combinaciones de .NET (SDK o Runtime) y del sistema operativo que puede usar.</span><span class="sxs-lookup"><span data-stu-id="747f7-159">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="747f7-160">Microsoft ofrece imágenes que se adaptan a escenarios específicos.</span><span class="sxs-lookup"><span data-stu-id="747f7-160">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="747f7-161">Por ejemplo, el [repositorio de ASP.NET Core](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) proporciona imágenes que se compilan para ejecutar aplicaciones de ASP.NET Core en producción.</span><span class="sxs-lookup"><span data-stu-id="747f7-161">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="747f7-162">Para obtener más información sobre el uso de .NET Core en un contenedor de Docker, vea [Introducción a .NET y Docker](../docker/introduction.md) y [Ejemplos](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span><span class="sxs-lookup"><span data-stu-id="747f7-162">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="747f7-163">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="747f7-163">Next steps</span></span>

- <span data-ttu-id="747f7-164">[Cómo comprobar que .NET Core ya está instalado](how-to-detect-installed-versions.md).</span><span class="sxs-lookup"><span data-stu-id="747f7-164">[How to check if .NET Core is already installed](how-to-detect-installed-versions.md).</span></span>
