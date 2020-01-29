---
title: Scripts de dotnet-install
description: Obtenga información sobre los scripts de dotnet-install para instalar el SDK de .NET Core y el entorno de ejecución compartido.
ms.date: 01/23/2020
ms.openlocfilehash: 169991ac4cd24ccab90634ff265c3ae5b603f8e9
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734206"
---
# <a name="dotnet-install-scripts-reference"></a>referencia de scripts de dotnet-install

## <a name="name"></a>NOMBRE

`dotnet-install.ps1` | `dotnet-install.sh`: script usado para instalar el SDK de .NET Core y el entorno de ejecución compartido.

## <a name="synopsis"></a>Sinopsis

Windows:

```powershell
dotnet-install.ps1 [-Channel] [-Version] [-JSonFile] [-InstallDir] [-Architecture]
    [-Runtime] [-DryRun] [-NoPath] [-Verbose] [-AzureFeed] [-UncachedFeed] [-NoCdn] [-FeedCredential]
    [-ProxyAddress] [-ProxyUseDefaultCredentials] [-SkipNonVersionedFiles] [-Help]
```

Linux/macOs:

```bash
dotnet-install.sh [--channel] [--version] [--jsonfile] [--install-dir] [--architecture]
    [--runtime] [--dry-run] [--no-path] [--verbose] [--azure-feed] [--uncached-feed] [--no-cdn] [--feed-credential]
    [--runtime-id] [--skip-non-versioned-files] [--help]
```

## <a name="description"></a>Descripción

Los scripts `dotnet-install` se usan para realizar una instalación sin derechos administrativos del SDK de .NET Core, que incluye las herramientas de la CLI de .NET Core y el entorno de tiempo de ejecución compartido.

Se recomienda usar la versión estable de los scripts:

- Bash (Linux/macOS): <https://dot.net/v1/dotnet-install.sh>
- PowerShell (Windows): <https://dot.net/v1/dotnet-install.ps1>

La utilidad principal de estos scripts está en los escenarios de automatización y las instalaciones sin derechos administrativos. Existen dos scripts: uno es un script de PowerShell que funciona en Windows y el otro es un script de Bash que funciona en Linux y macOS. Ambos scripts tienen el mismo comportamiento. El script de bash también lee modificadores de PowerShell, por lo que puede usar modificadores de PowerShell con el script en sistemas Linux y macOS.

Los scripts de instalación descargan el archivo ZIP o tarball desde las entregas de compilación de la CLI y proceden a instalarlo en la ubicación predeterminada o en una ubicación especificada por `-InstallDir|--install-dir`. De forma predeterminada, los scripts de instalación descargan el SDK y lo instalan. Si desea obtener solo el tiempo de ejecución compartido, especifique el argumento `-Runtime|--runtime`.

De forma predeterminada, el script agrega la ubicación de instalación a $PATH para la sesión actual. Para invalidar este comportamiento, especifique el argumento `-NoPath|--no-path`.

Antes de ejecutar el script, instale las [dependencias](../install/dependencies.md) necesarias.

Puede instalar una versión específica mediante el argumento `-Version|--version`. La versión debe especificarse como una versión de tres partes (por ejemplo, `2.1.0`). Si no se proporciona, usa la versión `latest`.

## <a name="options"></a>Opciones

- **`-Channel|--channel <CHANNEL>`**

  Especifica el canal de origen para la instalación. Los valores posibles son:

  - `Current`: versión más actual.
  - `LTS`: canal de soporte técnico a largo plazo (versión compatible más actual).
  - Versión de dos partes en formato X.Y que representa una versión específica (por ejemplo, `2.1` o `3.0`).
  - Nombre de rama: por ejemplo, `release/3.1.1xx` o `master` (para versiones nocturnas). Use esta opción para instalar una versión de un canal de versión preliminar. Use el nombre del canal como aparece en [Instaladores y binarios](https://github.com/dotnet/core-sdk#installers-and-binaries).

  El valor predeterminado es `LTS`. Para más información sobre los canales de soporte técnico de .NET, vea la página [.NET Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) (Directiva de soporte técnico de .NET Core).

- **`-Version|--version <VERSION>`**

  Representa una versión de compilación concreta. Los valores posibles son:

  - `latest`: compilación más reciente en el canal (utilizado con la opción `-Channel`).
  - `coherent`: compilación coherente más reciente en el canal; usa la última combinación de paquetes estables (usados con las opciones `-Channel` del nombre de la rama).
  - Versión de tres partes en formato X.Y.Z que representa una determinada versión de compilación; reemplaza a la opción `-Channel`. Por ejemplo: `2.0.0-preview2-006120`.

  Si no se especifica, el valor predeterminado de `-Version` es `latest`.

- **`-JSonFile|--jsonfile <JSONFILE>`**

  Especifica una ruta de acceso a un archivo [global.json](global-json.md) que se va a usar para determinar la versión del SDK. El archivo *global.json* debe tener un valor para `sdk:version`.

- **`-InstallDir|--install-dir <DIRECTORY>`**

  Especifica la ruta de instalación. Si no existe el directorio, se crea. El valor predeterminado es *%LocalAppData%\Microsoft\dotnet*. Los archivos binarios se colocan directamente en el directorio.

- **`-Architecture|--architecture <ARCHITECTURE>`**

  Arquitectura de los archivos binarios de .NET Core para instalar. Los valores posibles son `<auto>`, `amd64`, `x64`, `x86`, `arm64` y `arm`. El valor predeterminado es `<auto>`, que representa la arquitectura de SO que se ejecuta en ese momento.

- **`-SharedRuntime|--shared-runtime`**

  > [!NOTE]
  > Este parámetro está obsoleto y puede quitarse en una versión futura del script. La alternativa recomendada es la opción `-Runtime|--runtime`.

  Se instalan simplemente los bits del entorno de tiempo de ejecución compartido, no el SDK completo. Esta opción equivale a especificar `-Runtime|--runtime dotnet`.

- **`-Runtime|--runtime <RUNTIME>`**

  Se instala simplemente el entorno de tiempo de ejecución compartido, no el SDK completo. Los valores posibles son:

  - `dotnet`: el entorno de tiempo de ejecución compartido `Microsoft.NETCore.App`.
  - `aspnetcore`: el entorno de tiempo de ejecución compartido `Microsoft.AspNetCore.App`.
  - `windowsdesktop`: el entorno de tiempo de ejecución compartido `Microsoft.WindowsDesktop.App`.

- **`-DryRun|--dry-run`**

  Si se establece, el script no realizará la instalación. En su lugar, mostrará qué línea de comandos se va a usar para instalar de manera coherente la versión solicitada actualmente de la CLI de .NET Core. Por ejemplo, si especifica la versión `latest`, se muestra un vínculo con la versión específica, de manera que este comando puede usarse de manera determinista en un script de compilación. También se muestra la ubicación de los archivos binarios si prefiere instalarla o descargarla por su cuenta.

- **`-NoPath|--no-path`**

  Si se establece, la carpeta de instalación no se exporta a la ruta de acceso para la sesión actual. De manera predeterminada, el script modifica la ruta de acceso, que hace que las herramientas de la CLI estén disponibles inmediatamente después de la instalación.

- **`-Verbose|--verbose`**

  Muestra la información de diagnóstico.

- **`-AzureFeed|--azure-feed`**

  Especifica la dirección URL de la fuente de Azure al instalador. Le recomendamos que no cambie este valor. El valor predeterminado es `https://dotnetcli.azureedge.net/dotnet`.

- **`-UncachedFeed|--uncached-feed`**

  Permite cambiar la dirección URL de la fuente no almacenada en caché que este instalador utiliza. Le recomendamos que no cambie este valor.

- **`-NoCdn|--no-cdn`**

  Deshabilita la descarga desde [Azure Content Delivery Network (CDN)](https://docs.microsoft.com/azure/cdn/cdn-overview) y usa la fuente no almacenada en caché directamente.

- **`-FeedCredential|--feed-credential`**

  Se utiliza como una cadena de consulta para anexar a la fuente de Azure. Permite cambiar la dirección URL para usar cuentas de almacenamiento de blobs no público.

- **`--runtime-id`**

  Especifica el [identificador de entorno de ejecución](../rid-catalog.md) para el que se van a instalar las herramientas. Use `linux-x64` para Linux portátil. (Solo válido para Linux/macOS)

- **`-ProxyAddress`**

  Si se establece, el instalador usa el proxy al realizar solicitudes web. (Solo es válido para Windows)

- **`ProxyUseDefaultCredentials`**

  Si se establece, el instalador usa las credenciales del usuario actual cuando se usa la dirección del proxy. (Solo es válido para Windows)

- **`-SkipNonVersionedFiles|--skip-non-versioned-files`**

  Omite la instalación de archivos sin control de versiones, como *dotnet.exe*, si ya existen.

- **`-Help|--help`**

  Imprime la ayuda para el script.

## <a name="examples"></a>Ejemplos

- Instale la versión compatible a largo plazo más reciente en la ubicación predeterminada:

  Windows:

  ```powershell
  ./dotnet-install.ps1 -Channel LTS
  ```

  macOS y Linux:

  ```bash
  ./dotnet-install.sh --channel LTS
  ```

- Instale la versión más reciente del canal 3.1 en la ubicación especificada:

  Windows:

  ```powershell
  ./dotnet-install.ps1 -Channel 3.1 -InstallDir C:\cli
  ```

  macOS y Linux:

  ```bash
  ./dotnet-install.sh --channel 3.1 --install-dir ~/cli
  ```

- Instale la versión 3.0.0 del entorno de ejecución compartido:

  Windows:

  ```powershell
  ./dotnet-install.ps1 -Runtime dotnet -Version 3.0.0
  ```

  macOS y Linux:

  ```bash
  ./dotnet-install.sh --runtime dotnet --version 3.0.0
  ```

- Obtenga el script e instale la versión 2.1.2 detrás de un proxy corporativo (solo Windows):

  ```powershell
  Invoke-WebRequest 'https://dot.net/v1/dotnet-install.ps1' -Proxy $env:HTTP_PROXY -ProxyUseDefaultCredentials -OutFile 'dotnet-install.ps1';
  ./dotnet-install.ps1 -InstallDir '~/.dotnet' -Version '2.1.2' -ProxyAddress $env:HTTP_PROXY -ProxyUseDefaultCredentials;
  ```

- Obtenga el script e instale ejemplos de una línea para la CLI de .NET Core:

  Windows:

  ```powershell
  # Run a separate PowerShell process because the script calls exit, so it will end the current PowerShell session.
  &powershell -NoProfile -ExecutionPolicy unrestricted -Command "[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; &([scriptblock]::Create((Invoke-WebRequest -UseBasicParsing 'https://dot.net/v1/dotnet-install.ps1'))) <additional install-script args>"
  ```

  macOS y Linux:

  ```bash
  curl -ssl https://dot.net/v1/dotnet-install.sh | bash /dev/stdin <additional install-script args>
  ```

## <a name="see-also"></a>Vea también

- [Versiones de .NET Core](https://github.com/dotnet/core/releases)
- [Archivo de descarga del SDK y .NET Core Runtime](https://github.com/dotnet/core/blob/master/release-notes/download-archive.md)
