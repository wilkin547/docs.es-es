---
title: Requisitos previos para .NET Core en Mac
description: Versiones de macOS admitidas y dependencias de .NET Core para desarrollar, implementar y ejecutar aplicaciones .NET Core en máquinas macOS.
author: guardrex
ms.author: adegeo
ms.custom: updateeachvsrelease
ms.date: 12/14/2018
ms.openlocfilehash: 3f5dce25ed03061d690432684975909d15bbad57
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64752956"
---
# <a name="prerequisites-for-net-core-on-macos"></a>Requisitos previos para .NET Core en macOS

En este artículo se muestran las versiones de macOS admitidas y las dependencias de .NET Core que necesita para desarrollar, implementar y ejecutar aplicaciones .NET Core en máquinas de macOS. Las versiones de SO admitidas y las dependencias que se indican a continuación se aplican a las tres formas de desarrollar aplicaciones .NET Core en un equipo Mac: mediante la [línea de comandos con su editor favorito](tutorials/using-with-xplat-cli.md), [Visual Studio Code](https://code.visualstudio.com/) y [Visual Studio para Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).

## <a name="supported-macos-versions"></a>Versiones de macOS compatibles

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

.NET Core 2.x es compatible con las siguientes versiones de macOS:

* macOS 10.12 "Sierra" y versiones posteriores

Vea [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) (.NET Core 2.1: versiones de SO compatibles) y [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) (.NET Core 2.2: versiones de SO compatibles) para obtener la lista completa de sistemas operativos, distribuciones y versiones compatibles con .NET Core 2.1 y .NET Core 2.2, versiones del sistema operativo no compatibles y vínculos de la directiva de ciclo de vida.

Para los vínculos de descarga y más información, consulte [.NET Core 2.2 downloads](https://www.microsoft.com/net/download/dotnet-core/2.2) (Descargas de .NET Core 2.2) o [.NET Core 2.1 downloads](https://www.microsoft.com/net/download/dotnet-core/2.1) (Descargas de .NET Core 2.1).

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

.NET Core 1.x es compatible con las siguientes versiones de macOS:

* macOS 10.12 "Sierra"
* macOS 10.11 "El Capitan"

Vea [.NET Core 1.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.1/1.1.md) (.NET Core 1.1: versiones de SO compatibles) y [.NET Core 1.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) (.NET Core 1.0: versiones de SO compatibles) para obtener la lista completa de sistemas operativos, distribuciones y versiones compatibles con .NET Core 1.1 y .NET Core 1.0, versiones del sistema operativo no compatibles y vínculos de la directiva de ciclo de vida.

Para los vínculos de descarga y más información, consulte [.NET Core 1.1 downloads](https://www.microsoft.com/net/download/dotnet-core/1.1) (Descargas de .NET Core 1.1) o [.NET Core 1.0 downloads](https://www.microsoft.com/net/download/dotnet-core/1.0) (Descargas de .NET Core 1.0).

# <a name="net-core-30tabnetcore30"></a>[.NET Core 3.0](#tab/netcore30)

.NET Core 3.0 (versión preliminar 3) es compatible con las versiones siguientes de macOS:

* macOS 10.12 "Sierra" y versiones posteriores

Vea [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) (.NET Core 3.0: versiones de SO compatibles) para obtener la lista completa de sistemas operativos, distribuciones y versiones compatibles con .NET Core 3.0, las versiones de sistema operativo no compatibles y vínculos de la directiva de ciclo de vida.

Para obtener vínculos de descarga y más información, vea [.NET Core 3.0 downloads](https://www.microsoft.com/net/download/dotnet-core/3.0) (Descargas de .NET Core 3.0).

---

## <a name="net-core-dependencies"></a>Dependencias de .NET Core

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

Descargue e instale el SDK de .NET Core desde el portal de [descargas de .NET](https://www.microsoft.com/net/download/core). Si tiene problemas con la instalación en macOS, vea el tema sobre [problemas conocidos](https://github.com/dotnet/core/tree/master/release-notes/2.1) para la versión instalada.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

.NET Core 1.x requiere OpenSSL cuando se ejecuta en macOS. Una manera fácil de obtener OpenSSL es usar el administrador de paquetes [Homebrew ("brew")](https://brew.sh/) para macOS. Después de instalar *brew*, instale OpenSSL mediante la ejecución de los siguientes comandos en un símbolo del sistema de Terminal (comando):

```console
brew update
brew install openssl
mkdir -p /usr/local/lib
ln -s /usr/local/opt/openssl/lib/libcrypto.1.0.0.dylib /usr/local/lib/
ln -s /usr/local/opt/openssl/lib/libssl.1.0.0.dylib /usr/local/lib/
```

Descargue e instale el SDK de .NET Core desde el portal de [descargas de .NET](https://www.microsoft.com/net/download/core). Si tiene problemas con la instalación en macOS, vea los temas sobre problemas conocidos [1.0.0 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) y [1.0.1 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md).

# <a name="net-core-30tabnetcore30"></a>[.NET Core 3.0](#tab/netcore30)

Descargue e instale el SDK de .NET Core desde el portal de [descargas de .NET](https://www.microsoft.com/net/download/core). Si tiene problemas con la instalación en macOS, vea el tema sobre [notas de la versión](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) para la versión instalada.

---

## <a name="increase-the-maximum-open-file-limit-net-core-versions-before-net-core-sdk-202"></a>Aumentar el límite máximo de archivos abiertos (versiones de .NET Core antes del SDK de .NET Core 2.0.2)

En versiones anteriores de .NET Core (antes del SDK de .NET Core 2.0.2), el límite predeterminado de archivos abiertos en macOS puede no ser suficiente para algunas cargas de trabajo de .NET Core, como la restauración de proyectos o la ejecución de pruebas unitarias.

Puede aumentar este límite si sigue estos pasos:

1. Con un editor de texto, cree un nuevo archivo _/Library/LaunchDaemons/limit.maxfiles.plist_ y guárdelo con este contenido:

    ```xml
    <?xml version="1.0" encoding="UTF-8"?>
    <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
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

2. En una ventana de terminal, ejecute el comando siguiente:

   ```console
   echo 'ulimit -n 2048' | sudo tee -a /etc/profile
   ```

3. Reinicie el equipo Mac para aplicar esta configuración.

## <a name="visual-studio-for-mac"></a>Visual Studio para Mac

Puede usar cualquier editor para desarrollar aplicaciones .NET Core con el SDK de .NET Core. En cambio, si quiere desarrollar aplicaciones .NET Core en Mac en un entorno de desarrollo integrado, puede usar [Visual Studio para Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).

El desarrollo de .NET Core en macOS con Visual Studio para Mac requiere:

* Una versión compatible del sistema operativo macOS
* OpenSSL (solo .NET Core 1.x; .NET Core 2.x usa los servicios de seguridad disponibles de forma nativa en macOS)
* SDK de .NET Core para Mac
* [Visual Studio para Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)
