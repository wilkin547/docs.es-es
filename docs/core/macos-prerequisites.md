---
title: Requisitos previos para .NET Core en Mac
description: Versiones de macOS admitidas y dependencias de .NET Core para desarrollar, implementar y ejecutar aplicaciones .NET Core en máquinas macOS.
author: thraka
ms.author: adegeo
ms.custom: updateeachvsrelease
ms.date: 10/11/2019
ms.openlocfilehash: 2d4fc0b37be08988440325db8b507124c36bf053
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2019
ms.locfileid: "72318316"
---
# <a name="prerequisites-for-net-core-on-macos"></a>Requisitos previos para .NET Core en macOS

En este artículo se muestran las versiones de macOS admitidas y las dependencias de .NET Core que necesita para desarrollar, implementar y ejecutar aplicaciones .NET Core en máquinas de macOS. Las versiones de SO admitidas y las dependencias que se indican a continuación se aplican a las tres formas de desarrollar aplicaciones .NET Core en un equipo Mac: mediante la [línea de comandos con su editor favorito](tutorials/using-with-xplat-cli.md), [Visual Studio Code](https://code.visualstudio.com/) y [Visual Studio para Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).

## <a name="downloads-and-dependencies"></a>Descargas y dependencias

<!-- markdownlint-disable MD025 -->

# <a name="net-core-30tabnetcore30"></a>[.NET Core 3.0](#tab/netcore30)

.NET Core 3.0 es compatible con **macOS High Sierra (versión 10.13)**  y versiones posteriores. Se necesita una arquitectura de CPU **x64**.

Descargue e instale el SDK de .NET Core desde el la página [Descargas de .NET Core 3.0](https://dotnet.microsoft.com/download/dotnet-core/3.0). Vea [.NET Core 3.0: versiones de SO compatibles](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) para obtener la lista completa de sistemas operativos, distribuciones y versiones compatibles con .NET Core 3.0, las versiones de sistema operativo no compatibles y vínculos de la directiva de ciclo de vida.

Para obtener una lista de los problemas conocidos, vea [Problemas conocidos de .NET Core](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-known-issues.md).

# <a name="net-core-22tabnetcore22"></a>[.NET Core 2.2](#tab/netcore22)

.NET Core 2.2 es compatible con **macOS Sierra (versión 10.12)** y versiones posteriores. Se necesita una arquitectura de CPU **x64**.

Descargue e instale el SDK de .NET Core desde el la página [Descargas de .NET Core 2.2](https://dotnet.microsoft.com/download/dotnet-core/2.2). Vea [.NET Core 2.2: versiones de SO compatibles](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) para obtener la lista completa de sistemas operativos, distribuciones y versiones compatibles con .NET Core 2.2, las versiones de sistema operativo no compatibles y vínculos de la directiva de ciclo de vida.

Para obtener una lista de los problemas conocidos, vea [Problemas conocidos de .NET Core](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-known-issues.md).

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)

.NET Core 2.1 es compatible con **macOS Sierra (versión 10.12)** y versiones posteriores. Se necesita una arquitectura de CPU **x64**.

Descargue e instale el SDK de .NET Core desde la página [Descargas de .NET Core 2.1](https://dotnet.microsoft.com/download/dotnet-core/2.1). Vea [.NET Core 2.1: versiones de SO compatibles](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) para obtener la lista completa de sistemas operativos, distribuciones y versiones compatibles con .NET Core 2.1, las versiones de sistema operativo no compatibles y vínculos de la directiva de ciclo de vida.

Para obtener una lista de los problemas conocidos, vea [Problemas conocidos de .NET Core](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-known-issues.md).

---

## <a name="libgdiplus"></a>libgdiplus

Las aplicaciones .NET Core que usan el ensamblado *System.Drawing.Common* requieren la instalación de libgdiplus.

Una manera fácil de obtener libgdiplus es usar el administrador de paquetes [Homebrew ("brew")](https://brew.sh/) para macOS. Después de instalar *brew*, instale libgdiplus mediante la ejecución de los comandos siguientes en un símbolo del sistema de Terminal (comando):

```console
brew update
brew install libgdiplus
```

## <a name="visual-studio-for-mac"></a>Visual Studio para Mac

Puede usar cualquier editor para desarrollar aplicaciones .NET Core con el SDK de .NET Core. En cambio, si quiere desarrollar aplicaciones .NET Core en Mac en un entorno de desarrollo integrado, puede usar [Visual Studio para Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).
