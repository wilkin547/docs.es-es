---
title: Requisitos previos para .NET Core en Mac | Microsoft Docs
description: "Versiones de macOS admitidas y dependencias de .NET Core para desarrollar, implementar y ejecutar aplicaciones .NET Core en máquinas macOS."
keywords: .NET, .NET Core, macOS, Mac
author: guardrex
ms.author: mairaw
ms.date: 03/16/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: c33b1241-ab66-4583-9eba-52cf51146f5a
translationtype: Human Translation
ms.sourcegitcommit: ff143583ba62fc1d82561e739a75107e50ebee88
ms.openlocfilehash: da75f5fd56b7ce66b2c46ef488e6e26c55a63ee2
ms.lasthandoff: 03/20/2017

---

# <a name="prerequisites-for-net-core-on-mac"></a>Requisitos previos para .NET Core en Mac

En este artículo se muestran las versiones de macOS admitidas y las dependencias de .NET Core que necesita para desarrollar, implementar y ejecutar aplicaciones .NET Core en máquinas de macOS. Las versiones de SO admitidas y las dependencias que se indican a continuación se aplican a las tres formas de desarrollar aplicaciones .NET Core en un equipo Mac: mediante la [línea de comandos con su editor favorito](tutorials/using-with-xplat-cli.md), [Visual Studio Code (VS Code)](https://code.visualstudio.com/) y [Visual Studio para Mac](https://www.visualstudio.com/vs/visual-studio-mac/).

## <a name="supported-macos-versions"></a>Versiones de macOS compatibles

.NET Core es compatible con las siguientes versiones de macOS:

* macOS 10.12 "Sierra"
* macOS 10.11 "El Capitan"

Consulte la [notas de la versión de .NET Core](https://github.com/dotnet/core/blob/master/release-notes/1.1/1.1.md) para obtener una lista completa de sistemas operativos compatibles.

## <a name="net-core-dependencies"></a>Dependencias de .NET Core

.NET Core requiere OpenSSL cuando se ejecuta en macOS. Una manera fácil de obtener OpenSSL es usar el administrador de paquetes [Homebrew ("brew")](http://brew.sh/) para macOS. Después de instalar *brew*, instale OpenSSL mediante la ejecución de los siguientes comandos en un símbolo del sistema de Terminal (comando):

```Terminal
brew update
brew install openssl
mkdir -p /usr/local/lib
ln -s /usr/local/opt/openssl/lib/libcrypto.1.0.0.dylib /usr/local/lib/
ln -s /usr/local/opt/openssl/lib/libssl.1.0.0.dylib /usr/local/lib/
```

Después de instalar OpenSSL, obtenga el [instalador oficial del SDK de .NET Core para Mac](https://go.microsoft.com/fwlink/?linkid=843444). .NET Core 1.1.1 es la última versión. Para conocer las versiones compatibles a largo plazo y descargas adicionales, visite [.NET Downloads: All downloads](https://www.microsoft.com/net/download/core). (Descargas .NET: todas las descargas). Si tiene problemas con la instalación en macOS, consulte [Known issues & workarounds](https://github.com/dotnet/core/blob/master/cli/known-issues.md) (Problemas conocidos y soluciones temporales).

## <a name="visual-studio-for-mac"></a>Visual Studio para Mac

El desarrollo de .NET Core en macOS con Visual Studio para Mac requiere:

* Una versión compatible del sistema operativo macOS
* OpenSSL
* SDK de .NET Core para Mac
* [Visual Studio para Mac](https://www.visualstudio.com/vs/visual-studio-mac/)

