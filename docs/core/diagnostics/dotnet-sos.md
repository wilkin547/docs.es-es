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
# <a name="sos-installer-dotnet-sos"></a>Instalador de SOS (dotnet-sos)

**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.1 y versiones posteriores

## <a name="install-dotnet-sos"></a>Instalación de dotnet-sos

Para instalar la versión de lanzamiento más reciente del [paquete NuGet](https://www.nuget.org/packages/dotnet-sos) de `dotnet-sos`, use el comando [dotnet tool install](../tools/dotnet-tool-install.md):

```dotnetcli
dotnet tool install -g dotnet-sos
```

## <a name="synopsis"></a>Sinopsis

```console
dotnet-sos [-h|--help] [options] [command]]
```

## <a name="description"></a>Descripción

La herramienta global `dotnet-sos` instala la [extensión de depuración de SOS](../../framework/tools/sos-dll-sos-debugging-extension.md) para permitir la [inspección de estado de .NET Core administrado](https://github.com/dotnet/diagnostics/blob/master/documentation/sos-debugging-extension.md) desde depuradores nativos, como WinDbg/cdb en Windows y lldb en Linux y macOS. Las versiones recientes del depurador de Windows (posteriores o iguales a la versión 10.0.18317.1001 de WinDbg o cdb) cargarán SOS automáticamente desde la galería de extensiones de Microsoft, por lo que la instalación de SOS mediante la herramienta `dotnet-sos` solo es necesaria en Linux y macOS, o también en Windows si se usan herramientas de depuración anteriores.

## <a name="options"></a>Opciones

- **`--version`**

  Muestra información de la versión.

- **`-h|--help`**

  Muestra la ayuda de la línea de comandos.

## <a name="dotnet-sos-install"></a>dotnet-sos install

Instala la [extensión SOS](../../framework/tools/sos-dll-sos-debugging-extension.md) localmente para depurar procesos de .NET Core. En macOS y Linux, el archivo .lldbinit se actualizará para que la extensión se cargue automáticamente al iniciar lldb. Si va a instalar SOS en Windows con herramientas de depuración más antiguas (anteriores a la versión 10.0.18317.1001), deberá cargar manualmente la extensión en WinDbg o cdb ejecutando `.load %USERPROFILE%\.dotnet\sos\sos.dll` en el depurador.

### <a name="synopsis"></a>Sinopsis

```console
dotnet-sos install
```

## <a name="dotnet-sos-uninstall"></a>dotnet-sos uninstall

Desinstala la [extensión SOS](../../framework/tools/sos-dll-sos-debugging-extension.md) y, en Linux o macOS, la elimina de la configuración de lldb.

### <a name="synopsis"></a>Sinopsis

```console
dotnet-sos uninstall
```
