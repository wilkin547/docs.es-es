---
title: Requisitos previos para .NET Core en Mac
description: Versiones de macOS admitidas y dependencias de .NET Core para desarrollar, implementar y ejecutar aplicaciones .NET Core en máquinas macOS.
author: guardrex
ms.author: adegeo
ms.date: 12/14/2018
ms.openlocfilehash: bc6e0b20c61c474c7069b757528dbc1ea38354e3
ms.sourcegitcommit: 3d0c29b878f00caec288dfecb3a5c959de5aa629
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2018
ms.locfileid: "53656315"
---
# <a name="prerequisites-for-net-core-on-macos"></a><span data-ttu-id="fafe2-103">Requisitos previos para .NET Core en macOS</span><span class="sxs-lookup"><span data-stu-id="fafe2-103">Prerequisites for .NET Core on macOS</span></span>

<span data-ttu-id="fafe2-104">En este artículo se muestran las versiones de macOS admitidas y las dependencias de .NET Core que necesita para desarrollar, implementar y ejecutar aplicaciones .NET Core en máquinas de macOS.</span><span class="sxs-lookup"><span data-stu-id="fafe2-104">This article shows you the supported macOS versions and .NET Core dependencies that you need to develop, deploy, and run .NET Core applications on macOS machines.</span></span> <span data-ttu-id="fafe2-105">Las versiones de SO admitidas y las dependencias que se indican a continuación se aplican a las tres formas de desarrollar aplicaciones .NET Core en un equipo Mac: mediante la [línea de comandos con su editor favorito](tutorials/using-with-xplat-cli.md), [Visual Studio Code](https://code.visualstudio.com/) y [Visual Studio para Mac](https://visualstudio.microsoft.com/vs/visual-studio-mac/).</span><span class="sxs-lookup"><span data-stu-id="fafe2-105">The supported OS versions and dependencies that follow apply to the three ways of developing .NET Core apps on a Mac: via the [command-line with your favorite editor](tutorials/using-with-xplat-cli.md), [Visual Studio Code](https://code.visualstudio.com/), and [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/visual-studio-mac/).</span></span>

## <a name="supported-macos-versions"></a><span data-ttu-id="fafe2-106">Versiones de macOS compatibles</span><span class="sxs-lookup"><span data-stu-id="fafe2-106">Supported macOS versions</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="fafe2-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="fafe2-107">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="fafe2-108">.NET Core 2.x es compatible con las siguientes versiones de macOS:</span><span class="sxs-lookup"><span data-stu-id="fafe2-108">.NET Core 2.x is supported on the following versions of macOS:</span></span>

* <span data-ttu-id="fafe2-109">macOS 10.12 "Sierra" y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="fafe2-109">macOS 10.12 "Sierra" and later versions</span></span>

<span data-ttu-id="fafe2-110">Vea [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) (.NET Core 2.1: versiones de SO compatibles) y [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) (.NET Core 2.2: versiones de SO compatibles) para obtener la lista completa de sistemas operativos, distribuciones y versiones compatibles con .NET Core 2.1 y .NET Core 2.2, versiones del sistema operativo no compatibles y vínculos de la directiva de ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="fafe2-110">See [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) and [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) for the complete list of .NET Core 2.1 and .NET Core 2.2 supported operating systems, distributions and versions, out of support OS versions, and lifecycle policy links.</span></span>

<span data-ttu-id="fafe2-111">Para los vínculos de descarga y más información, consulte [.NET Core 2.2 downloads](https://www.microsoft.com/net/download/dotnet-core/2.2) (Descargas de .NET Core 2.2) o [.NET Core 2.1 downloads](https://www.microsoft.com/net/download/dotnet-core/2.1) (Descargas de .NET Core 2.1).</span><span class="sxs-lookup"><span data-stu-id="fafe2-111">For download links and more information, see [.NET Core 2.2 downloads](https://www.microsoft.com/net/download/dotnet-core/2.2) or [.NET Core 2.1 downloads](https://www.microsoft.com/net/download/dotnet-core/2.1).</span></span>


# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="fafe2-112">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="fafe2-112">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="fafe2-113">.NET Core 1.x es compatible con las siguientes versiones de macOS:</span><span class="sxs-lookup"><span data-stu-id="fafe2-113">.NET Core 1.x is supported on the following versions of macOS:</span></span>

* <span data-ttu-id="fafe2-114">macOS 10.12 "Sierra"</span><span class="sxs-lookup"><span data-stu-id="fafe2-114">macOS 10.12 "Sierra"</span></span>
* <span data-ttu-id="fafe2-115">macOS 10.11 "El Capitan"</span><span class="sxs-lookup"><span data-stu-id="fafe2-115">macOS 10.11 "El Capitan"</span></span>

<span data-ttu-id="fafe2-116">Vea [.NET Core 1.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.1/1.1.md) (.NET Core 1.1: versiones de SO compatibles) y [.NET Core 1.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) (.NET Core 1.0: versiones de SO compatibles) para obtener la lista completa de sistemas operativos, distribuciones y versiones compatibles con .NET Core 1.1 y .NET Core 1.0, versiones del sistema operativo no compatibles y vínculos de la directiva de ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="fafe2-116">See [.NET Core 1.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.1/1.1.md) and [.NET Core 1.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) for the complete list of .NET Core 1.1 and .NET Core 1.0 supported operating systems, distributions and versions, out of support OS versions, and lifecycle policy links.</span></span>

<span data-ttu-id="fafe2-117">Para los vínculos de descarga y más información, consulte [.NET Core 1.1 downloads](https://www.microsoft.com/net/download/dotnet-core/1.1) (Descargas de .NET Core 1.1) o [.NET Core 1.0 downloads](https://www.microsoft.com/net/download/dotnet-core/1.0) (Descargas de .NET Core 1.0).</span><span class="sxs-lookup"><span data-stu-id="fafe2-117">For download links and more information, see [.NET Core 1.1 downloads](https://www.microsoft.com/net/download/dotnet-core/1.1) or [.NET Core 1.0 downloads](https://www.microsoft.com/net/download/dotnet-core/1.0).</span></span>

# <a name="net-core-30-preview-1tabnetcore30"></a>[<span data-ttu-id="fafe2-118">.NET Core 3.0 (versión preliminar 1)</span><span class="sxs-lookup"><span data-stu-id="fafe2-118">.NET Core 3.0 Preview 1</span></span>](#tab/netcore30)

<span data-ttu-id="fafe2-119">.NET Core 3.0 (versión preliminar 1) es compatible con las versiones siguientes de macOS:</span><span class="sxs-lookup"><span data-stu-id="fafe2-119">.NET Core 3.0 Preview 1 is supported on the following versions of macOS:</span></span>

* <span data-ttu-id="fafe2-120">macOS 10.12 "Sierra" y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="fafe2-120">macOS 10.12 "Sierra" and later versions</span></span>

<span data-ttu-id="fafe2-121">Vea [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) (.NET Core 3.0: versiones de SO compatibles) para obtener la lista completa de sistemas operativos, distribuciones y versiones compatibles con .NET Core 3.0, las versiones de sistema operativo no compatibles y vínculos de la directiva de ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="fafe2-121">See [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) for the complete list of .NET Core 3.0 supported operating systems, distributions and versions, out of support OS versions, and lifecycle policy links.</span></span>

<span data-ttu-id="fafe2-122">Para obtener vínculos de descarga y más información, vea [.NET Core 3.0 downloads](https://www.microsoft.com/net/download/dotnet-core/3.0) (Descargas de .NET Core 3.0).</span><span class="sxs-lookup"><span data-stu-id="fafe2-122">For download links and more information, see [.NET Core 3.0 downloads](https://www.microsoft.com/net/download/dotnet-core/3.0).</span></span>

---

## <a name="net-core-dependencies"></a><span data-ttu-id="fafe2-123">Dependencias de .NET Core</span><span class="sxs-lookup"><span data-stu-id="fafe2-123">.NET Core dependencies</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="fafe2-124">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="fafe2-124">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="fafe2-125">Descargue e instale el SDK de .NET Core desde el portal de [descargas de .NET](https://www.microsoft.com/net/download/core).</span><span class="sxs-lookup"><span data-stu-id="fafe2-125">Download and install the .NET Core SDK from [.NET Downloads](https://www.microsoft.com/net/download/core).</span></span> <span data-ttu-id="fafe2-126">Si tiene problemas con la instalación en macOS, vea el tema sobre [problemas conocidos](https://github.com/dotnet/core/tree/master/release-notes/2.1) para la versión instalada.</span><span class="sxs-lookup"><span data-stu-id="fafe2-126">If you have problems with the installation on macOS, consult the [Known issues](https://github.com/dotnet/core/tree/master/release-notes/2.1) topic for the version you have installed.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="fafe2-127">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="fafe2-127">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="fafe2-128">.NET Core 1.x requiere OpenSSL cuando se ejecuta en macOS.</span><span class="sxs-lookup"><span data-stu-id="fafe2-128">.NET Core 1.x requires OpenSSL when running on macOS.</span></span> <span data-ttu-id="fafe2-129">Una manera fácil de obtener OpenSSL es usar el administrador de paquetes [Homebrew ("brew")](https://brew.sh/) para macOS.</span><span class="sxs-lookup"><span data-stu-id="fafe2-129">An easy way to obtain OpenSSL is by using the [Homebrew ("brew")](https://brew.sh/) package manager for macOS.</span></span> <span data-ttu-id="fafe2-130">Después de instalar *brew*, instale OpenSSL mediante la ejecución de los siguientes comandos en un símbolo del sistema de Terminal (comando):</span><span class="sxs-lookup"><span data-stu-id="fafe2-130">After installing *brew*, install OpenSSL by executing the following commands at a Terminal (command) prompt:</span></span>

```console
brew update
brew install openssl
mkdir -p /usr/local/lib
ln -s /usr/local/opt/openssl/lib/libcrypto.1.0.0.dylib /usr/local/lib/
ln -s /usr/local/opt/openssl/lib/libssl.1.0.0.dylib /usr/local/lib/
```

<span data-ttu-id="fafe2-131">Descargue e instale el SDK de .NET Core desde el portal de [descargas de .NET](https://www.microsoft.com/net/download/core).</span><span class="sxs-lookup"><span data-stu-id="fafe2-131">Download and install the .NET Core SDK from [.NET Downloads](https://www.microsoft.com/net/download/core).</span></span> <span data-ttu-id="fafe2-132">Si tiene problemas con la instalación en macOS, vea los temas sobre problemas conocidos [1.0.0 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) y [1.0.1 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md).</span><span class="sxs-lookup"><span data-stu-id="fafe2-132">If you have problems with the installation on macOS, consult the [1.0.0 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) and [1.0.1 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) topics.</span></span>

# <a name="net-core-30-preview-1tabnetcore30"></a>[<span data-ttu-id="fafe2-133">.NET Core 3.0 (versión preliminar 1)</span><span class="sxs-lookup"><span data-stu-id="fafe2-133">.NET Core 3.0 Preview 1</span></span>](#tab/netcore30)

<span data-ttu-id="fafe2-134">Descargue e instale el SDK de .NET Core desde el portal de [descargas de .NET](https://www.microsoft.com/net/download/core).</span><span class="sxs-lookup"><span data-stu-id="fafe2-134">Download and install the .NET Core SDK from [.NET Downloads](https://www.microsoft.com/net/download/core).</span></span> <span data-ttu-id="fafe2-135">Si tiene problemas con la instalación en macOS, vea el tema sobre [notas de la versión](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) para la versión instalada.</span><span class="sxs-lookup"><span data-stu-id="fafe2-135">If you have problems with the installation on macOS, consult the [Release notes](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) topic for the version you have installed.</span></span>

---

## <a name="increase-the-maximum-open-file-limit-net-core-versions-before-net-core-sdk-202"></a><span data-ttu-id="fafe2-136">Aumentar el límite máximo de archivos abiertos (versiones de .NET Core antes del SDK de .NET Core 2.0.2)</span><span class="sxs-lookup"><span data-stu-id="fafe2-136">Increase the maximum open file limit (.NET Core versions before .NET Core SDK 2.0.2)</span></span> 

<span data-ttu-id="fafe2-137">En versiones anteriores de .NET Core (antes del SDK de .NET Core 2.0.2), el límite predeterminado de archivos abiertos en macOS puede no ser suficiente para algunas cargas de trabajo de .NET Core, como la restauración de proyectos o la ejecución de pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="fafe2-137">In older .NET Core versions (before .NET Core SDK 2.0.2), the default open file limit on macOS may not be sufficient for some .NET Core workloads, such as restoring projects or running unit tests.</span></span>

<span data-ttu-id="fafe2-138">Puede aumentar este límite si sigue estos pasos:</span><span class="sxs-lookup"><span data-stu-id="fafe2-138">You can increase this limit by following these steps:</span></span>

1. <span data-ttu-id="fafe2-139">Con un editor de texto, cree un nuevo archivo _/Library/LaunchDaemons/limit.maxfiles.plist_ y guárdelo con este contenido:</span><span class="sxs-lookup"><span data-stu-id="fafe2-139">Using a text editor, create a new file _/Library/LaunchDaemons/limit.maxfiles.plist_, and save the file with this content:</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN"
        "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
  <dict>
    <key>Label</key>
    <string>limit.maxfiles</string>
    <key>ProgramArguments</key>
    <array>
      <string>launchctl</string>
      <string>limit</string>
      <string>maxfiles</string>
      <string>2048</string>
      <string>4096</string>
    </array>
    <key>RunAtLoad</key>
    <true/>
    <key>ServiceIPC</key>
    <false/>
  </dict>
</plist>
```

2. <span data-ttu-id="fafe2-140">En una ventana de terminal, ejecute el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="fafe2-140">In a terminal window, run the following command:</span></span>

   ```console
   echo 'ulimit -n 2048' | sudo tee -a /etc/profile
   ```

3. <span data-ttu-id="fafe2-141">Reinicie el equipo Mac para aplicar esta configuración.</span><span class="sxs-lookup"><span data-stu-id="fafe2-141">Reboot your Mac to apply these settings.</span></span>

## <a name="visual-studio-for-mac"></a><span data-ttu-id="fafe2-142">Visual Studio para Mac</span><span class="sxs-lookup"><span data-stu-id="fafe2-142">Visual Studio for Mac</span></span>

<span data-ttu-id="fafe2-143">Puede usar cualquier editor para desarrollar aplicaciones .NET Core con el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="fafe2-143">You can use any editor to develop .NET Core applications using the .NET Core SDK.</span></span> <span data-ttu-id="fafe2-144">En cambio, si quiere desarrollar aplicaciones .NET Core en Mac en un entorno de desarrollo integrado, puede usar [Visual Studio para Mac](https://visualstudio.microsoft.com/vs/visual-studio-mac/).</span><span class="sxs-lookup"><span data-stu-id="fafe2-144">However, if you want to develop .NET Core applications on a Mac in an integrated development environment, you can use [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/visual-studio-mac/).</span></span> 

<span data-ttu-id="fafe2-145">El desarrollo de .NET Core en macOS con Visual Studio para Mac requiere:</span><span class="sxs-lookup"><span data-stu-id="fafe2-145">.NET Core development on macOS with Visual Studio for Mac requires:</span></span>

* <span data-ttu-id="fafe2-146">Una versión compatible del sistema operativo macOS</span><span class="sxs-lookup"><span data-stu-id="fafe2-146">A supported version of the macOS operating system</span></span>
* <span data-ttu-id="fafe2-147">OpenSSL (solo .NET Core 1.x; .NET Core 2.x usa los servicios de seguridad disponibles de forma nativa en macOS)</span><span class="sxs-lookup"><span data-stu-id="fafe2-147">OpenSSL (.NET Core 1.x only; .NET Core 2.x uses security services available natively in macOS)</span></span>
* <span data-ttu-id="fafe2-148">SDK de .NET Core para Mac</span><span class="sxs-lookup"><span data-stu-id="fafe2-148">.NET Core SDK for Mac</span></span>
* [<span data-ttu-id="fafe2-149">Visual Studio para Mac</span><span class="sxs-lookup"><span data-stu-id="fafe2-149">Visual Studio for Mac</span></span>](https://visualstudio.microsoft.com/vs/visual-studio-mac/)
