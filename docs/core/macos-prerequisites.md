---
title: Requisitos previos para .NET Core en Mac
description: "Versiones de macOS admitidas y dependencias de .NET Core para desarrollar, implementar y ejecutar aplicaciones .NET Core en máquinas macOS."
keywords: .NET, .NET Core, macOS, Mac
author: guardrex
ms.author: mairaw
ms.date: 07/07/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: c33b1241-ab66-4583-9eba-52cf51146f5a
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 8feaee2cbfa55e23bd49c0ab76d995f15be343b4
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---

# <a name="prerequisites-for-net-core-on-mac"></a><span data-ttu-id="13101-104">Requisitos previos para .NET Core en Mac</span><span class="sxs-lookup"><span data-stu-id="13101-104">Prerequisites for .NET Core on Mac</span></span>

<span data-ttu-id="13101-105">En este artículo se muestran las versiones de macOS admitidas y las dependencias de .NET Core que necesita para desarrollar, implementar y ejecutar aplicaciones .NET Core en máquinas de macOS.</span><span class="sxs-lookup"><span data-stu-id="13101-105">This article shows you the supported macOS versions and .NET Core dependencies that you need to develop, deploy, and run .NET Core applications on macOS machines.</span></span> <span data-ttu-id="13101-106">Las versiones de SO admitidas y las dependencias que se indican a continuación se aplican a las tres formas de desarrollar aplicaciones .NET Core en un equipo Mac: mediante la [línea de comandos con su editor favorito](tutorials/using-with-xplat-cli.md), [Visual Studio Code](https://code.visualstudio.com/) y [Visual Studio para Mac](https://www.visualstudio.com/vs/visual-studio-mac/).</span><span class="sxs-lookup"><span data-stu-id="13101-106">The supported OS versions and dependencies that follow apply to the three ways of developing .NET Core apps on a Mac: via the [command-line with your favorite editor](tutorials/using-with-xplat-cli.md), [Visual Studio Code](https://code.visualstudio.com/), and [Visual Studio for Mac](https://www.visualstudio.com/vs/visual-studio-mac/).</span></span>

## <a name="supported-macos-versions"></a><span data-ttu-id="13101-107">Versiones de macOS compatibles</span><span class="sxs-lookup"><span data-stu-id="13101-107">Supported macOS versions</span></span>

<span data-ttu-id="13101-108">.NET Core es compatible con las siguientes versiones de macOS:</span><span class="sxs-lookup"><span data-stu-id="13101-108">.NET Core is supported on the following versions of macOS:</span></span>

* <span data-ttu-id="13101-109">macOS 10.12 "Sierra"</span><span class="sxs-lookup"><span data-stu-id="13101-109">macOS 10.12 "Sierra"</span></span>
* <span data-ttu-id="13101-110">macOS 10.11 "El Capitan" (solo .NET Core 1.x)</span><span class="sxs-lookup"><span data-stu-id="13101-110">macOS 10.11 "El Capitan" (.NET Core 1.x only)</span></span>

<span data-ttu-id="13101-111">Vea las [versiones de sistemas operativos compatibles](https://github.com/dotnet/core/blob/master/roadmap.md#supported-os-versions) para obtener una lista completa de sistemas operativos compatibles.</span><span class="sxs-lookup"><span data-stu-id="13101-111">See [Supported OS Versions](https://github.com/dotnet/core/blob/master/roadmap.md#supported-os-versions) for the complete list of supported operating systems.</span></span>

## <a name="net-core-dependencies"></a><span data-ttu-id="13101-112">Dependencias de .NET Core</span><span class="sxs-lookup"><span data-stu-id="13101-112">.NET Core dependencies</span></span>

<span data-ttu-id="13101-113">**.NET Core 1.x**</span><span class="sxs-lookup"><span data-stu-id="13101-113">**.NET Core 1.x**</span></span>

<span data-ttu-id="13101-114">.NET Core 1.x requiere OpenSSL cuando se ejecuta en macOS.</span><span class="sxs-lookup"><span data-stu-id="13101-114">.NET Core 1.x requires OpenSSL when running on macOS.</span></span> <span data-ttu-id="13101-115">Una manera fácil de obtener OpenSSL es usar el administrador de paquetes [Homebrew ("brew")](https://brew.sh/) para macOS.</span><span class="sxs-lookup"><span data-stu-id="13101-115">An easy way to obtain OpenSSL is by using the [Homebrew ("brew")](https://brew.sh/) package manager for macOS.</span></span> <span data-ttu-id="13101-116">Después de instalar *brew*, instale OpenSSL mediante la ejecución de los siguientes comandos en un símbolo del sistema de Terminal (comando):</span><span class="sxs-lookup"><span data-stu-id="13101-116">After installing *brew*, install OpenSSL by executing the following commands at a Terminal (command) prompt:</span></span>

```console
brew update
brew install openssl
mkdir -p /usr/local/lib
ln -s /usr/local/opt/openssl/lib/libcrypto.1.0.0.dylib /usr/local/lib/
ln -s /usr/local/opt/openssl/lib/libssl.1.0.0.dylib /usr/local/lib/
```

<span data-ttu-id="13101-117">Descargue e instale el SDK de .NET Core desde el portal de [descargas de .NET](https://www.microsoft.com/net/download/core).</span><span class="sxs-lookup"><span data-stu-id="13101-117">Download and install the .NET Core SDK from [.NET Downloads](https://www.microsoft.com/net/download/core).</span></span> <span data-ttu-id="13101-118">Si tiene problemas con la instalación en macOS, vea los temas sobre problemas conocidos [1.0.0 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) y [1.0.1 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md).</span><span class="sxs-lookup"><span data-stu-id="13101-118">If you have problems with the installation on macOS, consult the [1.0.0 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) and [1.0.1 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) topics.</span></span>

<span data-ttu-id="13101-119">**.NET Core 2.x**</span><span class="sxs-lookup"><span data-stu-id="13101-119">**.NET Core 2.x**</span></span>

<span data-ttu-id="13101-120">Descargue e instale el SDK de .NET Core desde el portal de [descargas de .NET](https://www.microsoft.com/net/download/core).</span><span class="sxs-lookup"><span data-stu-id="13101-120">Download and install the .NET Core SDK from [.NET Downloads](https://www.microsoft.com/net/download/core).</span></span> <span data-ttu-id="13101-121">Si tiene problemas con la instalación en macOS, vea el tema sobre [problemas conocidos](https://github.com/dotnet/core/tree/master/release-notes/2.0) para la versión instalada.</span><span class="sxs-lookup"><span data-stu-id="13101-121">If you have problems with the installation on macOS, consult the [Known issues](https://github.com/dotnet/core/tree/master/release-notes/2.0) topic for the version you have installed.</span></span>

## <a name="visual-studio-for-mac"></a><span data-ttu-id="13101-122">Visual Studio para Mac</span><span class="sxs-lookup"><span data-stu-id="13101-122">Visual Studio for Mac</span></span>

<span data-ttu-id="13101-123">Puede usar cualquier editor para desarrollar aplicaciones .NET Core con el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="13101-123">You can use any editor to develop .NET Core applications using the .NET Core SDK.</span></span> <span data-ttu-id="13101-124">En cambio, si quiere desarrollar aplicaciones .NET Core en Mac en un entorno de desarrollo integrado, puede usar [Visual Studio para Mac](https://www.visualstudio.com/vs/visual-studio-mac/).</span><span class="sxs-lookup"><span data-stu-id="13101-124">However, if you want to develop .NET Core applications on a Mac in an integrated development environment, you can use [Visual Studio for Mac](https://www.visualstudio.com/vs/visual-studio-mac/).</span></span> 

<span data-ttu-id="13101-125">El desarrollo de .NET Core en macOS con Visual Studio para Mac requiere:</span><span class="sxs-lookup"><span data-stu-id="13101-125">.NET Core development on macOS with Visual Studio for Mac requires:</span></span>

* <span data-ttu-id="13101-126">Una versión compatible del sistema operativo macOS</span><span class="sxs-lookup"><span data-stu-id="13101-126">A supported version of the macOS operating system</span></span>
* <span data-ttu-id="13101-127">OpenSSL (solo .NET Core 1.x; .NET Core 2.x usa los servicios de seguridad disponibles de forma nativa en macOS)</span><span class="sxs-lookup"><span data-stu-id="13101-127">OpenSSL (.NET Core 1.x only; .NET Core 2.x uses security services available natively in macOS)</span></span>
* <span data-ttu-id="13101-128">SDK de .NET Core para Mac</span><span class="sxs-lookup"><span data-stu-id="13101-128">.NET Core SDK for Mac</span></span>
* [<span data-ttu-id="13101-129">Visual Studio para Mac</span><span class="sxs-lookup"><span data-stu-id="13101-129">Visual Studio for Mac</span></span>](https://www.visualstudio.com/vs/visual-studio-mac/)

