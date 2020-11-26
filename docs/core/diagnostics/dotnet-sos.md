---
title: 'Herramienta de diagnóstico dotnet-sos: CLI de .NET'
description: Aprenda a instalar y usar la herramienta de la CLI dotnet-sos para administrar la extensión del depurador de SOS, que se usa con depuradores nativos en Windows y Linux.
ms.date: 11/17/2020
ms.openlocfilehash: 59512c42a778f68bb3cd092dc854dcc727fd2881
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94825447"
---
# <a name="sos-installer-dotnet-sos"></a><span data-ttu-id="89560-103">Instalador de SOS (dotnet-sos)</span><span class="sxs-lookup"><span data-stu-id="89560-103">SOS installer (dotnet-sos)</span></span>

<span data-ttu-id="89560-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.1 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="89560-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="install"></a><span data-ttu-id="89560-105">Instalar</span><span class="sxs-lookup"><span data-stu-id="89560-105">Install</span></span>

<span data-ttu-id="89560-106">Hay dos maneras de descargar e instalar `dotnet-sos`:</span><span class="sxs-lookup"><span data-stu-id="89560-106">There are two ways to download and install `dotnet-sos`:</span></span>

- <span data-ttu-id="89560-107">**Herramienta global dotnet:**</span><span class="sxs-lookup"><span data-stu-id="89560-107">**dotnet global tool:**</span></span>

  <span data-ttu-id="89560-108">Para instalar la versión de lanzamiento más reciente del [paquete NuGet](https://www.nuget.org/packages/dotnet-sos) de `dotnet-sos`, use el comando [dotnet tool install](../tools/dotnet-tool-install.md):</span><span class="sxs-lookup"><span data-stu-id="89560-108">To install the latest release version of the `dotnet-sos` [NuGet package](https://www.nuget.org/packages/dotnet-sos), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

  ```dotnetcli
  dotnet tool install --global dotnet-sos
  ```

- <span data-ttu-id="89560-109">**Descarga directa:**</span><span class="sxs-lookup"><span data-stu-id="89560-109">**Direct download:**</span></span>

  <span data-ttu-id="89560-110">Descargue el archivo ejecutable de la herramienta que coincida con la plataforma:</span><span class="sxs-lookup"><span data-stu-id="89560-110">Download the tool executable that matches your platform:</span></span>

  | <span data-ttu-id="89560-111">SO</span><span class="sxs-lookup"><span data-stu-id="89560-111">OS</span></span>  | <span data-ttu-id="89560-112">Plataforma</span><span class="sxs-lookup"><span data-stu-id="89560-112">Platform</span></span> |
  | --- | -------- |
  | <span data-ttu-id="89560-113">Windows</span><span class="sxs-lookup"><span data-stu-id="89560-113">Windows</span></span> | <span data-ttu-id="89560-114">[x86](https://aka.ms/dotnet-sos/win-x86) \| [x64](https://aka.ms/dotnet-sos/win-x64) \| [arm](https://aka.ms/dotnet-sos/win-arm) \| [arm-x64](https://aka.ms/dotnet-sos/win-arm64)</span><span class="sxs-lookup"><span data-stu-id="89560-114">[x86](https://aka.ms/dotnet-sos/win-x86) \| [x64](https://aka.ms/dotnet-sos/win-x64) \| [arm](https://aka.ms/dotnet-sos/win-arm) \| [arm-x64](https://aka.ms/dotnet-sos/win-arm64)</span></span> |
  | <span data-ttu-id="89560-115">macOS</span><span class="sxs-lookup"><span data-stu-id="89560-115">macOS</span></span>   | [<span data-ttu-id="89560-116">x64</span><span class="sxs-lookup"><span data-stu-id="89560-116">x64</span></span>](https://aka.ms/dotnet-sos/osx-x64) |
  | <span data-ttu-id="89560-117">Linux</span><span class="sxs-lookup"><span data-stu-id="89560-117">Linux</span></span>   | <span data-ttu-id="89560-118">[x64](https://aka.ms/dotnet-sos/linux-x64) \| [arm](https://aka.ms/dotnet-sos/linux-arm) \| [arm64](https://aka.ms/dotnet-sos/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-sos/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-sos/linux-musl-arm64)</span><span class="sxs-lookup"><span data-stu-id="89560-118">[x64](https://aka.ms/dotnet-sos/linux-x64) \| [arm](https://aka.ms/dotnet-sos/linux-arm) \| [arm64](https://aka.ms/dotnet-sos/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-sos/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-sos/linux-musl-arm64)</span></span> |

## <a name="synopsis"></a><span data-ttu-id="89560-119">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="89560-119">Synopsis</span></span>

```console
dotnet-sos [-h|--help] [options] [command]]
```

## <a name="description"></a><span data-ttu-id="89560-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="89560-120">Description</span></span>

<span data-ttu-id="89560-121">La herramienta global `dotnet-sos` instala la [extensión de depuración de SOS](../../framework/tools/sos-dll-sos-debugging-extension.md) para permitir la [inspección de estado de .NET Core administrado](https://github.com/dotnet/diagnostics/blob/master/documentation/sos-debugging-extension.md) desde depuradores nativos, como WinDbg/cdb en Windows y lldb en Linux y macOS.</span><span class="sxs-lookup"><span data-stu-id="89560-121">The `dotnet-sos` global tool installs the [SOS debugger extension](../../framework/tools/sos-dll-sos-debugging-extension.md) allowing [inspection of managed .NET Core state](https://github.com/dotnet/diagnostics/blob/master/documentation/sos-debugging-extension.md) from native debuggers like WinDbg/cdb on Windows and lldb on Linux and macOS.</span></span> <span data-ttu-id="89560-122">Las versiones recientes del depurador de Windows (posteriores o iguales a la versión 10.0.18317.1001 de WinDbg o cdb) cargarán SOS automáticamente desde la galería de extensiones de Microsoft, por lo que la instalación de SOS mediante la herramienta `dotnet-sos` solo es necesaria en Linux y macOS, o también en Windows si se usan herramientas de depuración anteriores.</span><span class="sxs-lookup"><span data-stu-id="89560-122">Recent versions of the Windows Debugger (>= version 10.0.18317.1001 of WinDbg or cdb) will load SOS automatically from the Microsoft extension gallery, so installing SOS via the `dotnet-sos` tool is only needed on Linux and macOS or on Windows if using older debugging tools.</span></span>

## <a name="options"></a><span data-ttu-id="89560-123">Opciones</span><span class="sxs-lookup"><span data-stu-id="89560-123">Options</span></span>

- **`--version`**

  <span data-ttu-id="89560-124">Muestra información de la versión.</span><span class="sxs-lookup"><span data-stu-id="89560-124">Displays version information.</span></span>

- **`-h|--help`**

  <span data-ttu-id="89560-125">Muestra la ayuda de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="89560-125">Shows command-line help.</span></span>

## <a name="dotnet-sos-install"></a><span data-ttu-id="89560-126">dotnet-sos install</span><span class="sxs-lookup"><span data-stu-id="89560-126">dotnet-sos install</span></span>

<span data-ttu-id="89560-127">Instala la [extensión SOS](../../framework/tools/sos-dll-sos-debugging-extension.md) localmente para depurar procesos de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="89560-127">Installs the [SOS extension](../../framework/tools/sos-dll-sos-debugging-extension.md) locally for debugging .NET Core processes.</span></span> <span data-ttu-id="89560-128">En macOS y Linux, el archivo .lldbinit se actualizará para que la extensión se cargue automáticamente al iniciar lldb.</span><span class="sxs-lookup"><span data-stu-id="89560-128">On macOS and Linux, the .lldbinit file will be updated so that the extension automatically loads at lldb startup.</span></span> <span data-ttu-id="89560-129">Si va a instalar SOS en Windows con herramientas de depuración más antiguas (anteriores a la versión 10.0.18317.1001), deberá cargar manualmente la extensión en WinDbg o cdb ejecutando `.load %USERPROFILE%\.dotnet\sos\sos.dll` en el depurador.</span><span class="sxs-lookup"><span data-stu-id="89560-129">If installing SOS on Windows with older debugging tools (< version 10.0.18317.1001), you will need to manually load the extension in WinDbg or cdb by running `.load %USERPROFILE%\.dotnet\sos\sos.dll` in the debugger.</span></span>

### <a name="synopsis"></a><span data-ttu-id="89560-130">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="89560-130">Synopsis</span></span>

```console
dotnet-sos install
```

## <a name="dotnet-sos-uninstall"></a><span data-ttu-id="89560-131">dotnet-sos uninstall</span><span class="sxs-lookup"><span data-stu-id="89560-131">dotnet-sos uninstall</span></span>

<span data-ttu-id="89560-132">Desinstala la [extensión SOS](../../framework/tools/sos-dll-sos-debugging-extension.md) y, en Linux o macOS, la elimina de la configuración de lldb.</span><span class="sxs-lookup"><span data-stu-id="89560-132">Uninstalls the [SOS extension](../../framework/tools/sos-dll-sos-debugging-extension.md) and, if on Linux or macOS, removes it from lldb configuration.</span></span>

### <a name="synopsis"></a><span data-ttu-id="89560-133">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="89560-133">Synopsis</span></span>

```console
dotnet-sos uninstall
```
