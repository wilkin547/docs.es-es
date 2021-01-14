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
# <a name="sos-installer-dotnet-sos"></a>Instalador de SOS (dotnet-sos)

**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.1 y versiones posteriores

## <a name="install"></a>Instalar

Hay dos maneras de descargar e instalar `dotnet-sos`:

- **Herramienta global dotnet:**

  Para instalar la versión de lanzamiento más reciente del [paquete NuGet](https://www.nuget.org/packages/dotnet-sos) de `dotnet-sos`, use el comando [dotnet tool install](../tools/dotnet-tool-install.md):

  ```dotnetcli
  dotnet tool install --global dotnet-sos
  ```

- **Descarga directa:**

  descargue el archivo ejecutable de la herramienta que coincida con la plataforma:

  | SO  | Plataforma |
  | --- | -------- |
  | Windows | [x86](https://aka.ms/dotnet-sos/win-x86) \| [x64](https://aka.ms/dotnet-sos/win-x64) \| [arm](https://aka.ms/dotnet-sos/win-arm) \| [arm-x64](https://aka.ms/dotnet-sos/win-arm64) |
  | macOS   | [x64](https://aka.ms/dotnet-sos/osx-x64) |
  | Linux   | [x64](https://aka.ms/dotnet-sos/linux-x64) \| [arm](https://aka.ms/dotnet-sos/linux-arm) \| [arm64](https://aka.ms/dotnet-sos/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-sos/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-sos/linux-musl-arm64) |

## <a name="synopsis"></a>Sinopsis

```console
dotnet-sos [-h|--help] [options] [command]]
```

## <a name="description"></a>Descripción

La herramienta global `dotnet-sos` instala la [extensión del depurador de SOS](sos-debugging-extension.md). Esta extensión permite inspeccionar el estado de .NET Core administrado desde depuradores nativos, como lldb y WinDbg.

> [!NOTE]
> Solo es necesario instalar SOS a través de la herramienta de `dotnet-sos` en Linux o macOS.  También puede ser necesario en Windows si usa herramientas de depuración más antiguas. Las versiones recientes del [depurador de Windows](/windows-hardware/drivers/debugger/debugger-download-tools) (a partir de la versión 10.0.18317.1001 de WinDbg o cdb) cargan SOS automáticamente desde la galería de extensiones de Microsoft.  

## <a name="options"></a>Opciones

- **`--version`**

  Muestra información de la versión.

- **`-h|--help`**

  Muestra la ayuda de la línea de comandos.

## <a name="dotnet-sos-install"></a>dotnet-sos install

Instala la [extensión SOS](sos-debugging-extension.md) localmente para depurar procesos de .NET Core. En macOS y Linux, el archivo *.lldbinit* se actualizará para que la extensión se cargue automáticamente al iniciar lldb. Si va a instalar SOS en Windows con herramientas de depuración más antiguas (anteriores a la versión 10.0.18317.1001), deberá cargar manualmente la extensión en WinDbg o cdb ejecutando `.load %USERPROFILE%\.dotnet\sos\sos.dll` en el depurador.

### <a name="synopsis"></a>Sinopsis

```console
dotnet-sos install [--architecture <arch>]
```

### <a name="options"></a>Opciones

- **`--architecture <arch>`**

  Especifica la arquitectura del procesador de los archivos binarios de SOS que se van a instalar. De forma predeterminada, `dotnet-sos` instala la arquitectura del equipo host. Use esta opción si quiere instalar SOS para una arquitectura diferente de la arquitectura de host de dotnet. Por ejemplo, si está ejecutando archivos binarios de Arm32 desde un host de Arm64, tendrá que instalar SOS con `dotnet-sos install --architecture Arm`.

  A continuación se enumeran las arquitecturas disponibles:

  - `Arm`
  - `Arm64`
  - `X86`
  - `X64`

## <a name="dotnet-sos-uninstall"></a>dotnet-sos uninstall

Desinstala la [extensión SOS](sos-debugging-extension.md) y, en Linux y macOS, la elimina de la configuración de lldb.

### <a name="synopsis"></a>Sinopsis

```console
dotnet-sos uninstall
```
