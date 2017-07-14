---
title: Requisitos previos para .NET Core en Mac | Microsoft Docs
description: "Versiones de macOS admitidas y dependencias de .NET Core para desarrollar, implementar y ejecutar aplicaciones .NET Core en máquinas macOS."
keywords: .NET, .NET Core, macOS, Mac
author: guardrex
ms.author: mairaw
ms.date: 06/12/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: c33b1241-ab66-4583-9eba-52cf51146f5a
ms.translationtype: Human Translation
ms.sourcegitcommit: 83200e452bccc20bfa82d94899514019e9d05a23
ms.openlocfilehash: 2aa685751fae9fa9771fa1cd86d211f742e06932
ms.contentlocale: es-es
ms.lasthandoff: 07/05/2017

---

# Requisitos previos para .NET Core en Mac
<a id="prerequisites-for-net-core-on-mac" class="xliff"></a>

En este artículo se muestran las versiones de macOS admitidas y las dependencias de .NET Core que necesita para desarrollar, implementar y ejecutar aplicaciones .NET Core en máquinas de macOS. Las versiones de SO admitidas y las dependencias que se indican a continuación se aplican a las tres formas de desarrollar aplicaciones .NET Core en un equipo Mac: mediante la [línea de comandos con su editor favorito](tutorials/using-with-xplat-cli.md), [Visual Studio Code](https://code.visualstudio.com/) y [Visual Studio para Mac](https://www.visualstudio.com/vs/visual-studio-mac/).

## Versiones de macOS compatibles
<a id="supported-macos-versions" class="xliff"></a>

.NET Core es compatible con las siguientes versiones de macOS:

* macOS 10.12 "Sierra"
* macOS 10.11 "El Capitan"

Consulte la [notas de la versión de .NET Core](https://github.com/dotnet/core/blob/master/release-notes/1.1/1.1.md) para obtener una lista completa de sistemas operativos compatibles.

## Dependencias de .NET Core
<a id="net-core-dependencies" class="xliff"></a>

**.NET Core 1.x**

.NET Core 1.x requiere OpenSSL cuando se ejecuta en macOS. Una manera fácil de obtener OpenSSL es usar el administrador de paquetes [Homebrew ("brew")](https://brew.sh/) para macOS. Después de instalar *brew*, instale OpenSSL mediante la ejecución de los siguientes comandos en un símbolo del sistema de Terminal (comando):

```console
brew update
brew install openssl
mkdir -p /usr/local/lib
ln -s /usr/local/opt/openssl/lib/libcrypto.1.0.0.dylib /usr/local/lib/
ln -s /usr/local/opt/openssl/lib/libssl.1.0.0.dylib /usr/local/lib/
```

Descargue e instale el SDK de .NET Core desde el portal de [descargas de .NET](https://www.microsoft.com/net/download/core). Si tiene problemas con la instalación en macOS, consulte el tema [Known issues & workarounds](https://github.com/dotnet/core/blob/master/cli/known-issues.md) (Problemas conocidos y soluciones alternativas).

**.NET Core 2.x**

Descargue e instale el SDK de .NET Core desde el portal de [descargas de .NET](https://www.microsoft.com/net/download/core). Si tiene problemas con la instalación en macOS, consulte el tema [Known issues & workarounds](https://github.com/dotnet/core/blob/master/cli/known-issues.md) (Problemas conocidos y soluciones alternativas).

## Visual Studio para Mac
<a id="visual-studio-for-mac" class="xliff"></a>

El desarrollo de .NET Core en macOS con Visual Studio para Mac requiere:

* Una versión compatible del sistema operativo macOS
* OpenSSL (solo .NET Core 1.x; .NET Core 2.x usa los servicios de seguridad disponibles de forma nativa en macOS)
* SDK de .NET Core para Mac
* [Visual Studio para Mac](https://www.visualstudio.com/vs/visual-studio-mac/)

