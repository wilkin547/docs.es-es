---
title: 'Herramienta de diagnóstico dotnet-sos: CLI de .NET'
description: Aprenda a instalar y usar la herramienta de la CLI dotnet-sos para administrar la extensión del depurador de SOS, que se usa con depuradores nativos en Windows y Linux.
ms.date: 11/17/2020
ms.openlocfilehash: 09e8228c47bdc632bccf3c9ad2296d55fe420060
ms.sourcegitcommit: c0b803bffaf101e12f071faf94ca21b46d04ff30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/24/2020
ms.locfileid: "97765012"
---
# <a name="sos-installer-dotnet-sos"></a><span data-ttu-id="0fa2b-103">Instalador de SOS (dotnet-sos)</span><span class="sxs-lookup"><span data-stu-id="0fa2b-103">SOS installer (dotnet-sos)</span></span>

<span data-ttu-id="0fa2b-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.1 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="0fa2b-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="install"></a><span data-ttu-id="0fa2b-105">Instalar</span><span class="sxs-lookup"><span data-stu-id="0fa2b-105">Install</span></span>

<span data-ttu-id="0fa2b-106">Hay dos maneras de descargar e instalar `dotnet-sos`:</span><span class="sxs-lookup"><span data-stu-id="0fa2b-106">There are two ways to download and install `dotnet-sos`:</span></span>

- <span data-ttu-id="0fa2b-107">**Herramienta global dotnet:**</span><span class="sxs-lookup"><span data-stu-id="0fa2b-107">**dotnet global tool:**</span></span>

  <span data-ttu-id="0fa2b-108">Para instalar la versión de lanzamiento más reciente del [paquete NuGet](https://www.nuget.org/packages/dotnet-sos) de `dotnet-sos`, use el comando [dotnet tool install](../tools/dotnet-tool-install.md):</span><span class="sxs-lookup"><span data-stu-id="0fa2b-108">To install the latest release version of the `dotnet-sos` [NuGet package](https://www.nuget.org/packages/dotnet-sos), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

  ```dotnetcli
  dotnet tool install --global dotnet-sos
  ```

- <span data-ttu-id="0fa2b-109">**Descarga directa:**</span><span class="sxs-lookup"><span data-stu-id="0fa2b-109">**Direct download:**</span></span>

  <span data-ttu-id="0fa2b-110">descargue el archivo ejecutable de la herramienta que coincida con la plataforma:</span><span class="sxs-lookup"><span data-stu-id="0fa2b-110">Download the tool executable that matches your platform:</span></span>

  | <span data-ttu-id="0fa2b-111">SO</span><span class="sxs-lookup"><span data-stu-id="0fa2b-111">OS</span></span>  | <span data-ttu-id="0fa2b-112">Plataforma</span><span class="sxs-lookup"><span data-stu-id="0fa2b-112">Platform</span></span> |
  | --- | -------- |
  | <span data-ttu-id="0fa2b-113">Windows</span><span class="sxs-lookup"><span data-stu-id="0fa2b-113">Windows</span></span> | <span data-ttu-id="0fa2b-114">[x86](https://aka.ms/dotnet-sos/win-x86) \| [x64](https://aka.ms/dotnet-sos/win-x64) \| [arm](https://aka.ms/dotnet-sos/win-arm) \| [arm-x64](https://aka.ms/dotnet-sos/win-arm64)</span><span class="sxs-lookup"><span data-stu-id="0fa2b-114">[x86](https://aka.ms/dotnet-sos/win-x86) \| [x64](https://aka.ms/dotnet-sos/win-x64) \| [arm](https://aka.ms/dotnet-sos/win-arm) \| [arm-x64](https://aka.ms/dotnet-sos/win-arm64)</span></span> |
  | <span data-ttu-id="0fa2b-115">macOS</span><span class="sxs-lookup"><span data-stu-id="0fa2b-115">macOS</span></span>   | [<span data-ttu-id="0fa2b-116">x64</span><span class="sxs-lookup"><span data-stu-id="0fa2b-116">x64</span></span>](https://aka.ms/dotnet-sos/osx-x64) |
  | <span data-ttu-id="0fa2b-117">Linux</span><span class="sxs-lookup"><span data-stu-id="0fa2b-117">Linux</span></span>   | <span data-ttu-id="0fa2b-118">[x64](https://aka.ms/dotnet-sos/linux-x64) \| [arm](https://aka.ms/dotnet-sos/linux-arm) \| [arm64](https://aka.ms/dotnet-sos/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-sos/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-sos/linux-musl-arm64)</span><span class="sxs-lookup"><span data-stu-id="0fa2b-118">[x64](https://aka.ms/dotnet-sos/linux-x64) \| [arm](https://aka.ms/dotnet-sos/linux-arm) \| [arm64](https://aka.ms/dotnet-sos/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-sos/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-sos/linux-musl-arm64)</span></span> |

## <a name="synopsis"></a><span data-ttu-id="0fa2b-119">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="0fa2b-119">Synopsis</span></span>

```console
dotnet-sos [-h|--help] [options] [command]]
```

## <a name="description"></a><span data-ttu-id="0fa2b-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="0fa2b-120">Description</span></span>

<span data-ttu-id="0fa2b-121">La herramienta global `dotnet-sos` instala la [extensión del depurador de SOS](sos-debugging-extension.md).</span><span class="sxs-lookup"><span data-stu-id="0fa2b-121">The `dotnet-sos` global tool installs the [SOS debugger extension](sos-debugging-extension.md).</span></span> <span data-ttu-id="0fa2b-122">Esta extensión permite inspeccionar el estado de .NET Core administrado desde depuradores nativos, como lldb y WinDbg.</span><span class="sxs-lookup"><span data-stu-id="0fa2b-122">This extension lets you inspect managed .NET Core state from native debuggers like lldb and windbg.</span></span>

> [!NOTE]
> <span data-ttu-id="0fa2b-123">Solo es necesario instalar SOS a través de la herramienta de `dotnet-sos` en Linux o macOS.</span><span class="sxs-lookup"><span data-stu-id="0fa2b-123">Installing SOS via the `dotnet-sos` tool is only needed on Linux or macOS.</span></span>  <span data-ttu-id="0fa2b-124">También puede ser necesario en Windows si usa herramientas de depuración más antiguas.</span><span class="sxs-lookup"><span data-stu-id="0fa2b-124">It may also be needed on Windows if you're using older debugging tools.</span></span> <span data-ttu-id="0fa2b-125">Las versiones recientes del [depurador de Windows](/windows-hardware/drivers/debugger/debugger-download-tools) (a partir de la versión 10.0.18317.1001 de WinDbg o cdb) cargan SOS automáticamente desde la galería de extensiones de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0fa2b-125">Recent versions of the [Windows Debugger](/windows-hardware/drivers/debugger/debugger-download-tools) (>= version 10.0.18317.1001 of WinDbg or cdb) load SOS automatically from the Microsoft extension gallery.</span></span>  

## <a name="options"></a><span data-ttu-id="0fa2b-126">Opciones</span><span class="sxs-lookup"><span data-stu-id="0fa2b-126">Options</span></span>

- **`--version`**

  <span data-ttu-id="0fa2b-127">Muestra información de la versión.</span><span class="sxs-lookup"><span data-stu-id="0fa2b-127">Displays version information.</span></span>

- **`-h|--help`**

  <span data-ttu-id="0fa2b-128">Muestra la ayuda de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="0fa2b-128">Shows command-line help.</span></span>

## <a name="dotnet-sos-install"></a><span data-ttu-id="0fa2b-129">dotnet-sos install</span><span class="sxs-lookup"><span data-stu-id="0fa2b-129">dotnet-sos install</span></span>

<span data-ttu-id="0fa2b-130">Instala la [extensión SOS](sos-debugging-extension.md) localmente para depurar procesos de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="0fa2b-130">Installs the [SOS extension](sos-debugging-extension.md) locally for debugging .NET Core processes.</span></span> <span data-ttu-id="0fa2b-131">En macOS y Linux, el archivo *.lldbinit* se actualizará para que la extensión se cargue automáticamente al iniciar lldb.</span><span class="sxs-lookup"><span data-stu-id="0fa2b-131">On macOS and Linux, the *.lldbinit* file will be updated so that the extension automatically loads at lldb startup.</span></span> <span data-ttu-id="0fa2b-132">Si va a instalar SOS en Windows con herramientas de depuración más antiguas (anteriores a la versión 10.0.18317.1001), deberá cargar manualmente la extensión en WinDbg o cdb ejecutando `.load %USERPROFILE%\.dotnet\sos\sos.dll` en el depurador.</span><span class="sxs-lookup"><span data-stu-id="0fa2b-132">If you're installing SOS on Windows with older debugging tools (prior to version 10.0.18317.1001), you will need to manually load the extension in WinDbg or cdb by running `.load %USERPROFILE%\.dotnet\sos\sos.dll` in the debugger.</span></span>

### <a name="synopsis"></a><span data-ttu-id="0fa2b-133">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="0fa2b-133">Synopsis</span></span>

```console
dotnet-sos install [--architecture <arch>]
```

### <a name="options"></a><span data-ttu-id="0fa2b-134">Opciones</span><span class="sxs-lookup"><span data-stu-id="0fa2b-134">Options</span></span>

- **`--architecture <arch>`**

  <span data-ttu-id="0fa2b-135">Especifica la arquitectura del procesador de los archivos binarios de SOS que se van a instalar.</span><span class="sxs-lookup"><span data-stu-id="0fa2b-135">Specifies the processor architecture of the SOS binaries to install.</span></span> <span data-ttu-id="0fa2b-136">De forma predeterminada, `dotnet-sos` instala la arquitectura del equipo host.</span><span class="sxs-lookup"><span data-stu-id="0fa2b-136">By default, `dotnet-sos` installs the architecture of the host machine.</span></span> <span data-ttu-id="0fa2b-137">Use esta opción si quiere instalar SOS para una arquitectura diferente de la arquitectura de host de dotnet.</span><span class="sxs-lookup"><span data-stu-id="0fa2b-137">Use this option when you want to install SOS for an architecture that's different from the dotnet host architecture.</span></span> <span data-ttu-id="0fa2b-138">Por ejemplo, si está ejecutando archivos binarios de Arm32 desde un host de Arm64, tendrá que instalar SOS con `dotnet-sos install --architecture Arm`.</span><span class="sxs-lookup"><span data-stu-id="0fa2b-138">For example, if you're running Arm32 binaries from an Arm64 host, you will need to install SOS with `dotnet-sos install --architecture Arm`.</span></span>

  <span data-ttu-id="0fa2b-139">A continuación se enumeran las arquitecturas disponibles:</span><span class="sxs-lookup"><span data-stu-id="0fa2b-139">The following architectures are available:</span></span>

  - `Arm`
  - `Arm64`
  - `X86`
  - `X64`

## <a name="dotnet-sos-uninstall"></a><span data-ttu-id="0fa2b-140">dotnet-sos uninstall</span><span class="sxs-lookup"><span data-stu-id="0fa2b-140">dotnet-sos uninstall</span></span>

<span data-ttu-id="0fa2b-141">Desinstala la [extensión SOS](sos-debugging-extension.md) y, en Linux y macOS, la elimina de la configuración de lldb.</span><span class="sxs-lookup"><span data-stu-id="0fa2b-141">Uninstalls the [SOS extension](sos-debugging-extension.md) and, on Linux and macOS, removes it from lldb configuration.</span></span>

### <a name="synopsis"></a><span data-ttu-id="0fa2b-142">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="0fa2b-142">Synopsis</span></span>

```console
dotnet-sos uninstall
```
