---
title: 'dotnet-sos: .NET Core'
description: Obtenga información sobre cómo instalar y usar la herramienta de línea de comandos dotnet-sos.
ms.date: 08/26/2020
ms.openlocfilehash: ba83105718909038ca56129ed8a5063aeff12e89
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065089"
---
# <a name="sos-installer-dotnet-sos"></a><span data-ttu-id="d6c0b-103">Instalador de SOS (dotnet-sos)</span><span class="sxs-lookup"><span data-stu-id="d6c0b-103">SOS installer (dotnet-sos)</span></span>

<span data-ttu-id="d6c0b-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.1 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="d6c0b-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="install-dotnet-sos"></a><span data-ttu-id="d6c0b-105">Instalación de dotnet-sos</span><span class="sxs-lookup"><span data-stu-id="d6c0b-105">Install dotnet-sos</span></span>

<span data-ttu-id="d6c0b-106">Para instalar la versión de lanzamiento más reciente del [paquete NuGet](https://www.nuget.org/packages/dotnet-sos) de `dotnet-sos`, use el comando [dotnet tool install](../tools/dotnet-tool-install.md):</span><span class="sxs-lookup"><span data-stu-id="d6c0b-106">To install the latest release version of the `dotnet-sos` [NuGet package](https://www.nuget.org/packages/dotnet-sos), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

```dotnetcli
dotnet tool install -g dotnet-sos
```

## <a name="synopsis"></a><span data-ttu-id="d6c0b-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="d6c0b-107">Synopsis</span></span>

```console
dotnet-sos [-h|--help] [options] [command]]
```

## <a name="description"></a><span data-ttu-id="d6c0b-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="d6c0b-108">Description</span></span>

<span data-ttu-id="d6c0b-109">La herramienta global `dotnet-sos` instala la [extensión de depuración de SOS](../../framework/tools/sos-dll-sos-debugging-extension.md) para permitir la [inspección de estado de .NET Core administrado](https://github.com/dotnet/diagnostics/blob/master/documentation/sos-debugging-extension.md) desde depuradores nativos, como WinDbg/cdb en Windows y lldb en Linux y macOS.</span><span class="sxs-lookup"><span data-stu-id="d6c0b-109">The `dotnet-sos` global tool installs the [SOS debugger extension](../../framework/tools/sos-dll-sos-debugging-extension.md) allowing [inspection of managed .NET Core state](https://github.com/dotnet/diagnostics/blob/master/documentation/sos-debugging-extension.md) from native debuggers like WinDbg/cdb on Windows and lldb on Linux and macOS.</span></span> <span data-ttu-id="d6c0b-110">Las versiones recientes del depurador de Windows (posteriores o iguales a la versión 10.0.18317.1001 de WinDbg o cdb) cargarán SOS automáticamente desde la galería de extensiones de Microsoft, por lo que la instalación de SOS mediante la herramienta `dotnet-sos` solo es necesaria en Linux y macOS, o también en Windows si se usan herramientas de depuración anteriores.</span><span class="sxs-lookup"><span data-stu-id="d6c0b-110">Recent versions of the Windows Debugger (>= version 10.0.18317.1001 of WinDbg or cdb) will load SOS automatically from the Microsoft extension gallery, so installing SOS via the `dotnet-sos` tool is only needed on Linux and macOS or on Windows if using older debugging tools.</span></span>

## <a name="options"></a><span data-ttu-id="d6c0b-111">Opciones</span><span class="sxs-lookup"><span data-stu-id="d6c0b-111">Options</span></span>

- **`--version`**

  <span data-ttu-id="d6c0b-112">Muestra información de la versión.</span><span class="sxs-lookup"><span data-stu-id="d6c0b-112">Displays version information.</span></span>

- **`-h|--help`**

  <span data-ttu-id="d6c0b-113">Muestra la ayuda de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="d6c0b-113">Shows command-line help.</span></span>

## <a name="dotnet-sos-install"></a><span data-ttu-id="d6c0b-114">dotnet-sos install</span><span class="sxs-lookup"><span data-stu-id="d6c0b-114">dotnet-sos install</span></span>

<span data-ttu-id="d6c0b-115">Instala la [extensión SOS](../../framework/tools/sos-dll-sos-debugging-extension.md) localmente para depurar procesos de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d6c0b-115">Installs the [SOS extension](../../framework/tools/sos-dll-sos-debugging-extension.md) locally for debugging .NET Core processes.</span></span> <span data-ttu-id="d6c0b-116">En macOS y Linux, el archivo .lldbinit se actualizará para que la extensión se cargue automáticamente al iniciar lldb.</span><span class="sxs-lookup"><span data-stu-id="d6c0b-116">On macOS and Linux, the .lldbinit file will be updated so that the extension automatically loads at lldb startup.</span></span> <span data-ttu-id="d6c0b-117">Si va a instalar SOS en Windows con herramientas de depuración más antiguas (anteriores a la versión 10.0.18317.1001), deberá cargar manualmente la extensión en WinDbg o cdb ejecutando `.load %USERPROFILE%\.dotnet\sos\sos.dll` en el depurador.</span><span class="sxs-lookup"><span data-stu-id="d6c0b-117">If installing SOS on Windows with older debugging tools (< version 10.0.18317.1001), you will need to manually load the extension in WinDbg or cdb by running `.load %USERPROFILE%\.dotnet\sos\sos.dll` in the debugger.</span></span>

### <a name="synopsis"></a><span data-ttu-id="d6c0b-118">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="d6c0b-118">Synopsis</span></span>

```console
dotnet-sos install
```

## <a name="dotnet-sos-uninstall"></a><span data-ttu-id="d6c0b-119">dotnet-sos uninstall</span><span class="sxs-lookup"><span data-stu-id="d6c0b-119">dotnet-sos uninstall</span></span>

<span data-ttu-id="d6c0b-120">Desinstala la [extensión SOS](../../framework/tools/sos-dll-sos-debugging-extension.md) y, en Linux o macOS, la elimina de la configuración de lldb.</span><span class="sxs-lookup"><span data-stu-id="d6c0b-120">Uninstalls the [SOS extension](../../framework/tools/sos-dll-sos-debugging-extension.md) and, if on Linux or macOS, removes it from lldb configuration.</span></span>

### <a name="synopsis"></a><span data-ttu-id="d6c0b-121">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="d6c0b-121">Synopsis</span></span>

```console
dotnet-sos uninstall
```
