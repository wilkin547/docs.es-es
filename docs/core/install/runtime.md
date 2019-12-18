---
title: 'Instalación del entorno de ejecución de .NET Core en Windows, Linux y macOS: .NET Core'
description: Obtenga información sobre cómo instalar .NET Core en Windows, Linux y macOS. Descubra las dependencias necesarias para ejecutar aplicaciones de .NET Core.
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 8f4a895ad66dea3063a32f785e4c521196266978
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2019
ms.locfileid: "74998892"
---
# <a name="install-the-net-core-runtime"></a><span data-ttu-id="4baea-104">Instalación del entorno de ejecución de .NET Core</span><span class="sxs-lookup"><span data-stu-id="4baea-104">Install the .NET Core Runtime</span></span>

<span data-ttu-id="4baea-105">En este artículo, obtendrá información sobre cómo descargar e instalar el entorno de ejecución de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4baea-105">In this article, you'll learn how to download and install the .NET Core runtime.</span></span> <span data-ttu-id="4baea-106">El entorno de ejecución de .NET Core se usa para ejecutar aplicaciones creadas con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4baea-106">The .NET Core runtime is used to run apps created with .NET Core.</span></span>

::: zone pivot="os-windows"

## <a name="install-with-an-installer"></a><span data-ttu-id="4baea-107">Instalación mediante un instalador</span><span class="sxs-lookup"><span data-stu-id="4baea-107">Install with an installer</span></span>

<span data-ttu-id="4baea-108">Windows tiene instaladores independientes que se pueden usar para instalar el entorno de ejecución de .NET Core 3.1:</span><span class="sxs-lookup"><span data-stu-id="4baea-108">Windows has standalone installers that can be used to install the .NET Core 3.1 runtime:</span></span>

- [<span data-ttu-id="4baea-109">CPU de x64 (64 bits)</span><span class="sxs-lookup"><span data-stu-id="4baea-109">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="4baea-110">CPU de x86 (32 bits)</span><span class="sxs-lookup"><span data-stu-id="4baea-110">x86 (32-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-an-installer"></a><span data-ttu-id="4baea-111">Instalación mediante un instalador</span><span class="sxs-lookup"><span data-stu-id="4baea-111">Install with an installer</span></span>

<span data-ttu-id="4baea-112">macOS tiene instaladores independientes que se pueden usar para instalar el entorno de ejecución de .NET Core 3.1:</span><span class="sxs-lookup"><span data-stu-id="4baea-112">macOS has standalone installers that can be used to install the .NET Core 3.1 runtime:</span></span>

- [<span data-ttu-id="4baea-113">CPU de x64 (64 bits)</span><span class="sxs-lookup"><span data-stu-id="4baea-113">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-linux"

## <a name="install-with-a-package-manager"></a><span data-ttu-id="4baea-114">Instalación con un administrador de paquetes</span><span class="sxs-lookup"><span data-stu-id="4baea-114">Install with a package manager</span></span>

<span data-ttu-id="4baea-115">Se puede instalar el entorno de ejecución de .NET Core con muchos de los administradores de paquetes comunes de Linux.</span><span class="sxs-lookup"><span data-stu-id="4baea-115">You can install the .NET Core Runtime with many of the common Linux package managers.</span></span> <span data-ttu-id="4baea-116">Para obtener más información, vea [Administrador de paquetes de Linux: instalación de .NET Core](linux-package-manager-rhel7.md).</span><span class="sxs-lookup"><span data-stu-id="4baea-116">For more information, see [Linux Package Manager - Install .NET Core](linux-package-manager-rhel7.md).</span></span>

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a><span data-ttu-id="4baea-117">Instalación mediante la automatización de PowerShell</span><span class="sxs-lookup"><span data-stu-id="4baea-117">Install with PowerShell automation</span></span>

<span data-ttu-id="4baea-118">Los [scripts de dotnet-install](../tools/dotnet-install-script.md) se usan para la automatización y las instalaciones que no son de administrador del entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4baea-118">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="4baea-119">Se puede descargar el script desde la [página de referencia del script dotnet-install](../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="4baea-119">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="4baea-120">El valor predeterminado del script es instalar la versión más reciente de [soporte técnico a largo plazo (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), que actualmente es .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="4baea-120">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="4baea-121">Puede elegir una versión concreta especificando el modificador `Channel`.</span><span class="sxs-lookup"><span data-stu-id="4baea-121">You can choose a specific release by specifying the `Channel` switch.</span></span> <span data-ttu-id="4baea-122">Incluya el modificador `Runtime` para instalar un entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4baea-122">Include the `Runtime` switch to install a runtime.</span></span> <span data-ttu-id="4baea-123">De lo contrario, el script instala el [SDK](sdk.md).</span><span class="sxs-lookup"><span data-stu-id="4baea-123">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```powershell
dotnet-install.ps1 -Channel 3.1 -Runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="4baea-124">El comando anterior instala el entorno de ejecución de ASP.NET Core para obtener la máxima compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="4baea-124">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="4baea-125">El entorno de ejecución de ASP.NET Core también incluye el estándar de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4baea-125">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

::: zone-end

::: zone pivot="os-linux,os-macos"

## <a name="install-with-bash-automation"></a><span data-ttu-id="4baea-126">Instalación mediante la automatización de Bash</span><span class="sxs-lookup"><span data-stu-id="4baea-126">Install with bash automation</span></span>

<span data-ttu-id="4baea-127">Los [scripts de dotnet-install](../tools/dotnet-install-script.md) se usan para la automatización y las instalaciones que no son de administrador del entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4baea-127">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="4baea-128">Se puede descargar el script desde la [página de referencia del script dotnet-install](../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="4baea-128">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="4baea-129">El valor predeterminado del script es instalar la versión más reciente de [soporte técnico a largo plazo (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), que actualmente es .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="4baea-129">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="4baea-130">Puede elegir una versión concreta especificando el modificador `current`.</span><span class="sxs-lookup"><span data-stu-id="4baea-130">You can choose a specific release by specifying the `current` switch.</span></span> <span data-ttu-id="4baea-131">Incluya el modificador `runtime` para instalar un entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4baea-131">Include the `runtime` switch to install a runtime.</span></span> <span data-ttu-id="4baea-132">De lo contrario, el script instala el [SDK](sdk.md).</span><span class="sxs-lookup"><span data-stu-id="4baea-132">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```bash
./dotnet-install.sh --current 3.1 --runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="4baea-133">El comando anterior instala el entorno de ejecución de ASP.NET Core para obtener la máxima compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="4baea-133">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="4baea-134">El entorno de ejecución de ASP.NET Core también incluye el estándar de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4baea-134">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

::: zone-end

## <a name="all-net-core-downloads"></a><span data-ttu-id="4baea-135">Todas las descargas de .NET Core</span><span class="sxs-lookup"><span data-stu-id="4baea-135">All .NET Core downloads</span></span>

<span data-ttu-id="4baea-136">Puede descargar e instalar .NET Core directamente con uno de los vínculos siguientes:</span><span class="sxs-lookup"><span data-stu-id="4baea-136">You can download and install .NET Core directly with one of the following links:</span></span>

- [<span data-ttu-id="4baea-137">Descargas de .NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="4baea-137">.NET Core 3.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="4baea-138">Descargas de .NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="4baea-138">.NET Core 3.0 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.0)
- [<span data-ttu-id="4baea-139">Descargas de .NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="4baea-139">.NET Core 2.2 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.2)
- [<span data-ttu-id="4baea-140">Descargas de .NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="4baea-140">.NET Core 2.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.1)

## <a name="docker"></a><span data-ttu-id="4baea-141">Docker</span><span class="sxs-lookup"><span data-stu-id="4baea-141">Docker</span></span>

<span data-ttu-id="4baea-142">Los contenedores proporcionan una manera ligera de aislar la aplicación del resto del sistema host.</span><span class="sxs-lookup"><span data-stu-id="4baea-142">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="4baea-143">Los contenedores de la misma máquina comparten solo el kernel y usan los recursos proporcionados a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4baea-143">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="4baea-144">.NET Core puede ejecutarse en un contenedor de Docker.</span><span class="sxs-lookup"><span data-stu-id="4baea-144">.NET Core can run in a Docker container.</span></span> <span data-ttu-id="4baea-145">Las imágenes oficiales de Docker en .NET Core se publican en el registro de contenedor de Microsoft (MCR) y se pueden encontrar en el [repositorio de Docker Hub para Microsoft .NET Core](https://hub.docker.com/_/microsoft-dotnet-core/).</span><span class="sxs-lookup"><span data-stu-id="4baea-145">Official .NET Core Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span> <span data-ttu-id="4baea-146">Cada repositorio contiene imágenes para diferentes combinaciones de .NET (SDK o Runtime) y del sistema operativo que puede usar.</span><span class="sxs-lookup"><span data-stu-id="4baea-146">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="4baea-147">Microsoft ofrece imágenes que se adaptan a escenarios específicos.</span><span class="sxs-lookup"><span data-stu-id="4baea-147">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="4baea-148">Por ejemplo, el [repositorio de ASP.NET Core](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) proporciona imágenes que se compilan para ejecutar aplicaciones de ASP.NET Core en producción.</span><span class="sxs-lookup"><span data-stu-id="4baea-148">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="4baea-149">Para obtener más información sobre el uso de .NET Core en un contenedor de Docker, vea [Introducción a .NET y Docker](../docker/introduction.md) y [Ejemplos](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span><span class="sxs-lookup"><span data-stu-id="4baea-149">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="4baea-150">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="4baea-150">Next steps</span></span>

- <span data-ttu-id="4baea-151">[Cómo comprobar que .NET Core ya está instalado](how-to-detect-installed-versions.md).</span><span class="sxs-lookup"><span data-stu-id="4baea-151">[How to check if .NET Core is already installed](how-to-detect-installed-versions.md).</span></span>
