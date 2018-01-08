---
title: Scripts de dotnet-install
description: "Aprenda sobre los scripts de dotnet-install para instalar las herramientas de la CLI de .NET Core y el entorno de tiempo de ejecución compartido."
keywords: dotnet-install, scripts de dotnet-install, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 09/11/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: b64e7e6f-ffb4-4fc8-b43b-5731c89479c2
ms.workload: dotnetcore
ms.openlocfilehash: bc38ca7b9f00c6c252ff4963c42519a64c456b43
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="dotnet-install-scripts-reference"></a>referencia de scripts de dotnet-install

## <a name="name"></a>nombre

`dotnet-install.ps1` | `dotnet-install.sh`: script usado para instalar las herramientas de la CLI de .NET Core y el entorno de tiempo de ejecución compartido.

## <a name="synopsis"></a>Sinopsis

Windows:

`dotnet-install.ps1 [-Channel] [-Version] [-InstallDir] [-Architecture] [-SharedRuntime] [-DryRun] [-NoPath] [-AzureFeed] [-ProxyAddress] [--Verbose] [--Help]`

macOS y Linux:

`dotnet-install.sh [--channel] [--version] [--install-dir] [--architecture] [--shared-runtime] [--dry-run] [--no-path] [--azure-feed] [--verbose] [--help]`

## <a name="description"></a>Description

Los scripts `dotnet-install` se usan para realizar una instalación sin derechos administrativos del SDK de .NET Core, que incluye las herramientas de la CLI de .NET Core y el entorno de tiempo de ejecución compartido.

Le recomendamos que use la versión estable que se hospeda en el [sitio web principal de .NET Core](https://dot.net). Las rutas de acceso directas a los scripts son las siguientes:

* https://dot.net/v1/dotnet-install.sh (bash, UNIX)
* https://dot.net/v1/dotnet-install.ps1 (Powershell, Windows)

La utilidad principal de estos scripts está en los escenarios de automatización y las instalaciones sin derechos administrativos. Hay dos scripts: uno es un script de PowerShell que funciona en Windows. El otro script es un script de bash que funciona en Linux y macOS. Ambos scripts tienen el mismo comportamiento. El script de bash también lee modificadores de PowerShell, por lo que puede usar modificadores de PowerShell con el script en sistemas Linux y macOS. 

Los scripts de instalación descargan el archivo ZIP o tarball desde las entregas de compilación de la CLI y proceden a instalarlo en la ubicación predeterminada o en una ubicación especificada por `-InstallDir|--install-dir`. De forma predeterminada, los scripts de instalación descargan el SDK y lo instalan. Si desea obtener solo el tiempo de ejecución compartido, especifique el argumento `--shared-runtime`. 

De forma predeterminada, el script agrega la ubicación de instalación a $PATH para la sesión actual. Para invalidar este comportamiento, especifique el argumento `--no-path`. 

Antes de ejecutar el script, instale las [dependencias](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md) necesarias.

Puede instalar una versión específica mediante el argumento `--version`. La versión debe especificarse como una versión de 3 partes (por ejemplo, 1.0.0-13232). Si se omite, usa la versión `latest`.

## <a name="options"></a>Opciones

`-Channel <CHANNEL>`

Especifica el canal de origen para la instalación. Los valores posibles son:

- `Current`: versión actual
- `LTS`: canal de soporte técnico a largo plazo (versión actual compatible)
- Versión de dos partes en formato X.Y que representa una versión específica (por ejemplo, `2.0` o `1.0`)
- Nombre de rama [por ejemplo, `release/2.0.0`, `release/2.0.0-preview2` o `master` para la última versión de la rama `master` (versiones nocturna "experimentales")]

El valor predeterminado es `LTS`. Para más información sobre los canales de soporte técnico de .NET, vea el tema [.NET Core Support Lifecycle](https://www.microsoft.com/net/core/support) (Ciclo de vida de soporte técnico de .NET Core).

`-Version <VERSION>`

Representa una versión de compilación concreta. Los valores posibles son:

- `latest`: compilación más reciente en el canal (utilizado con la opción `-Channel`)
- `coherent`: compilación coherente más reciente en el canal; usa la última combinación de paquetes estables (usados con las opciones `-Channel` del nombre de la rama)
- Versión de tres partes en formato X.Y.Z que representa una determinada versión de compilación; reemplaza a la opción `-Channel`. Por ejemplo: `2.0.0-preview2-006120`.

Si se omite, el valor predeterminado de `-Version` es `latest`.

`-InstallDir <DIRECTORY>`

Especifica la ruta de instalación. Si no existe el directorio, se crea. El valor predeterminado es *% LocalAppData %\.dotnet*. Tenga en cuenta que los archivos binarios se colocan directamente en el directorio.

`-Architecture <ARCHITECTURE>`

Arquitectura de los archivos binarios de .NET Core para instalar. Los valores posibles son `auto`, `x64`, y `x86`. El valor predeterminado es `auto`, que representa la arquitectura de SO que se ejecuta en ese momento.

`-SharedRuntime`

Si se establece, este modificador limita la instalación al entorno de tiempo de ejecución compartido. No está instalado el SDK completo.

`-DryRun`

Si se establece, el script no realizará la instalación pero, en su lugar, mostrará qué línea de comandos se va a usar para instalar de manera coherente la versión solicitada actualmente de la CLI de .NET Core. Por ejemplo, si especifica la versión `latest`, se muestra un vínculo con la versión específica, de manera que este comando puede usarse de manera determinista en un script de compilación. También se muestra la ubicación de los archivos binarios si prefiere instalarla o descargarla por su cuenta.

`-NoPath`

Si se establece, el prefijo/installdir no se exportan a la ruta de acceso para la sesión actual. De manera predeterminada, el script modificará la ruta de acceso, que hace que las herramientas de la CLI estén disponibles inmediatamente después de la instalación.

`-AzureFeed`

Especifica la dirección URL de la fuente de Azure al instalador. No se recomienda cambiar este valor. El valor predeterminado es `https://dotnetcli.azureedge.net/dotnet`.

`-ProxyAddress`

Si se establece, el instalador usa el proxy al realizar solicitudes web. (Solo es válido para Windows)

`--verbose`

Muestra la información de diagnóstico.

`--help`

Imprime la ayuda para el script.

## <a name="examples"></a>Ejemplos

Instale la versión compatible a largo plazo más reciente en la ubicación predeterminada:

Windows:

`./dotnet-install.ps1 -Channel LTS`

macOS y Linux:

`./dotnet-install.sh --channel LTS`

Instale la versión más reciente del canal 2.0 en la ubicación especificada:

Windows:

`./dotnet-install.ps1 -Channel 2.0 -InstallDir C:\cli`

macOS y Linux:

`./dotnet-install.sh --channel 2.0 --install-dir ~/cli`

Instale la versión 1.1.0 del entorno de tiempo de ejecución compartido:

Windows:

`./dotnet-install.ps1 -SharedRuntime -Version 1.1.0`

macOS y Linux:

`./dotnet-install.sh --shared-runtime --version 1.1.0`

Obtenga el script e instale ejemplos de una línea para la CLI de .NET Core:

Windows:

`@powershell -NoProfile -ExecutionPolicy unrestricted -Command "&([scriptblock]::Create((Invoke-WebRequest -useb 'https://dot.net/v1/dotnet-install.ps1'))) <additional install-script args>"`

macOS y Linux:

`curl -sSL https://dot.net/v1/dotnet-install.sh | bash /dev/stdin <additional install-script args>`

## <a name="see-also"></a>Vea también

[Versiones de .NET Core](https://github.com/dotnet/core/releases)   
[Archivo de descarga del SDK y .NET Core Runtime](https://github.com/dotnet/core/blob/master/release-notes/download-archive.md)
