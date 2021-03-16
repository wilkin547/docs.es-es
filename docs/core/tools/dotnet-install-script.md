---
title: Scripts de dotnet-install
description: Obtenga información sobre los scripts de dotnet-install para instalar el SDK de .NET y el entorno de ejecución compartido.
ms.date: 09/22/2020
ms.openlocfilehash: 51482ca70d08d86e02a493f1da49b056fed8d11c
ms.sourcegitcommit: bdbf6472de867a0a11aaa5b9384a2506c24f27d2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2021
ms.locfileid: "102206692"
---
# <a name="dotnet-install-scripts-reference"></a>referencia de scripts de dotnet-install

## <a name="name"></a>NOMBRE

`dotnet-install.ps1` | `dotnet-install.sh`: script usado para instalar el SDK de .NET y el entorno de ejecución compartido.

## <a name="synopsis"></a>Sinopsis

Windows:

```powershell
dotnet-install.ps1 [-Architecture <ARCHITECTURE>] [-AzureFeed]
    [-Channel <CHANNEL>] [-DryRun] [-FeedCredential]
    [-InstallDir <DIRECTORY>] [-JSonFile <JSONFILE>]
    [-NoCdn] [-NoPath] [-ProxyAddress] [-ProxyBypassList <LIST_OF_URLS>]
    [-ProxyUseDefaultCredentials] [-Runtime <RUNTIME>]
    [-SkipNonVersionedFiles] [-UncachedFeed] [-Verbose]
    [-Version <VERSION>]

Get-Help ./dotnet-install.ps1
```

Linux/macOS:

```bash
dotnet-install.sh  [--architecture <ARCHITECTURE>] [--azure-feed]
    [--channel <CHANNEL>] [--dry-run] [--feed-credential]
    [--install-dir <DIRECTORY>] [--jsonfile <JSONFILE>]
    [--no-cdn] [--no-path] [--runtime <RUNTIME>] [--runtime-id <RID>]
    [--skip-non-versioned-files] [--uncached-feed] [--verbose]
    [--version <VERSION>]

dotnet-install.sh --help
```

El script de bash también lee modificadores de PowerShell, por lo que puede usar modificadores de PowerShell con el script en sistemas Linux y macOS.

## <a name="description"></a>Descripción

Los scripts `dotnet-install` realizan una instalación sin derechos administrativos del SDK de .NET, que incluye la CLI de .NET y el entorno de ejecución compartido. Hay dos scripts:

* un script de PowerShell que funciona en Windows;
* un script de Bash que funciona en Linux y macOS.

> [!NOTE]
> .NET recopila datos de telemetría. Para obtener más información y saber cómo no participar, consulte [Telemetría del SDK de .NET](telemetry.md).

### <a name="purpose"></a>Propósito

 El uso previsto de los scripts es en escenarios de integración continua (CI), donde:

* el SDK debe instalarse sin interacción del usuario y sin derechos de administrador;
* no es necesario que la instalación del SDK se mantenga en varias ejecuciones de CI.

  Esta es la secuencia típica de eventos:
  * Se desencadena la CI.
  * CI instala el SDK mediante uno de estos scripts.
  * CI finaliza su trabajo y borra los datos temporales, incluida la instalación del SDK.

Para configurar un entorno de desarrollo o ejecutar aplicaciones, use los instaladores en lugar de estos scripts.

### <a name="recommended-version"></a>Versión recomendada

Se recomienda usar la versión estable de los scripts:

- Bash (Linux/macOS): <https://dot.net/v1/dotnet-install.sh>
- PowerShell (Windows): <https://dot.net/v1/dotnet-install.ps1>

### <a name="script-behavior"></a>Comportamiento de los scripts

Ambos scripts tienen el mismo comportamiento. Descargan el archivo ZIP o tarball desde las entregas de compilación de la CLI y proceden a instalarlo en la ubicación predeterminada o en una ubicación especificada por `-InstallDir|--install-dir`.

De forma predeterminada, los scripts de instalación descargan el SDK y lo instalan. Si desea obtener solo el tiempo de ejecución compartido, especifique el argumento `-Runtime|--runtime`.

De forma predeterminada, el script agrega la ubicación de instalación a $PATH para la sesión actual. Para invalidar este comportamiento, especifique el argumento `-NoPath|--no-path`. El script no establece la variable de entorno `DOTNET_ROOT`.

Antes de ejecutar el script, instale las [dependencias](../install/windows.md#dependencies) necesarias.

Puede instalar una versión específica mediante el argumento `-Version|--version`. La versión debe especificarse como un número de versión de tres partes, por ejemplo, `2.1.0`. Si no se especifica la versión, el script instala la versión `latest`.

Los scripts de instalación no actualizan el Registro en Windows. Solo descargan los archivos binarios comprimidos y los copian en una carpeta. Si quiere que se actualicen los valores de las claves del Registro, use los instaladores de .NET.

## <a name="options"></a>Opciones

- **`-Architecture|--architecture <ARCHITECTURE>`**

  Arquitectura de los archivos binarios de .NET para instalar. Los valores posibles son `<auto>`, `amd64`, `x64`, `x86`, `arm64` y `arm`. El valor predeterminado es `<auto>`, que representa la arquitectura de SO que se ejecuta en ese momento.

- **`-AzureFeed|--azure-feed`**

  Especifica la dirección URL de la fuente de Azure al instalador. Le recomendamos que no cambie este valor. El valor predeterminado es `https://dotnetcli.azureedge.net/dotnet`.

- **`-Channel|--channel <CHANNEL>`**

  Especifica el canal de origen para la instalación. Los valores posibles son:

  - `Current`: versión más actual.
  - `LTS`: canal de soporte técnico a largo plazo (versión compatible más actual).
  - Versión de dos partes en formato X.Y que representa una versión específica (por ejemplo, `2.1` o `3.0`).
  - Nombre de rama: por ejemplo, `release/3.1.1xx` o `master` (para versiones nocturnas). Use esta opción para instalar una versión de un canal de versión preliminar. Use el nombre del canal como aparece en [Instaladores y binarios](https://github.com/dotnet/core-sdk#installers-and-binaries).

  El valor predeterminado es `LTS`. Para más información sobre los canales de soporte técnico de .NET, vea la página [.NET Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) (Directiva de soporte técnico de .NET Core).

- **`-DryRun|--dry-run`**

  Si se establece, el script no realizará la instalación. En su lugar, muestra qué línea de comandos se va a usar para instalar de manera coherente la versión solicitada actualmente de la CLI de .NET. Por ejemplo, si especifica la versión `latest`, se muestra un vínculo con la versión específica, de manera que este comando puede usarse de manera determinista en un script de compilación. También se muestra la ubicación de los archivos binarios si prefiere instalarla o descargarla por su cuenta.

- **`-FeedCredential|--feed-credential`**

  Se utiliza como una cadena de consulta para anexar a la fuente de Azure. Permite cambiar la dirección URL para usar cuentas de almacenamiento de blobs no público.

- **`--help`**

  Imprime la ayuda para el script. Solo se aplica al script de Bash. Para PowerShell, use `Get-Help ./dotnet-install.ps1`.

- **`-InstallDir|--install-dir <DIRECTORY>`**

  Especifica la ruta de instalación. Si no existe el directorio, se crea. El valor predeterminado es *%LocalAppData%\Microsoft\dotnet* en Windows y */usr/share/dotnet* en Linux/macOS. Los archivos binarios se colocan directamente en el directorio.

- **`-JSonFile|--jsonfile <JSONFILE>`**

  Especifica una ruta de acceso a un archivo [global.json](global-json.md) que se va a usar para determinar la versión del SDK. El archivo *global.json* debe tener un valor para `sdk:version`.

- **`-NoCdn|--no-cdn`**

  Deshabilita la descarga desde [Azure Content Delivery Network (CDN)](/azure/cdn/cdn-overview) y usa la fuente no almacenada en caché directamente.

- **`-NoPath|--no-path`**

  Si se establece, la carpeta de instalación no se exporta a la ruta de acceso para la sesión actual. De manera predeterminada, el script modifica la variable de entorno PATH, que hace que la CLI de .NET esté disponible inmediatamente después de la instalación.

- **`-ProxyAddress`**

  Si se establece, el instalador usa el proxy al realizar solicitudes web. (Solo es válido para Windows).

- **`-ProxyBypassList <LIST_OF_URLS>`**

  Si se establece con `ProxyAddress`, proporciona una lista de direcciones URL separadas por comas que omiten el proxy. (Solo es válido para Windows).

- **`ProxyUseDefaultCredentials`**

  Si se establece, el instalador usa las credenciales del usuario actual cuando se usa la dirección del proxy. (Solo es válido para Windows).

- **`-Runtime|--runtime <RUNTIME>`**

  Se instala simplemente el entorno de tiempo de ejecución compartido, no el SDK completo. Los valores posibles son:

  - `dotnet`: el entorno de tiempo de ejecución compartido `Microsoft.NETCore.App`.
  - `aspnetcore`: el entorno de tiempo de ejecución compartido `Microsoft.AspNetCore.App`.
  - `windowsdesktop`: el entorno de tiempo de ejecución compartido `Microsoft.WindowsDesktop.App`.

- **`--runtime-id <RID>` [En desuso]**

  Especifica el [identificador de entorno de ejecución](../rid-catalog.md) para el que se van a instalar las herramientas. Use `linux-x64` para Linux portátil. (Solo es válido para Linux/macOS y versiones anteriores a .NET Core 2.1).

  **`--os <OPERATING_SYSTEM>`**

  Especifica el sistema operativo para el que se instalan las herramientas. Los valores posibles son `osx`, `linux`, `linux-musl`, `freebsd` y `rhel.6`. (Es válido para .NET Core 2.1 y versiones posteriores).

  El parámetro es opcional y solo se debe usar cuando sea necesario invalidar el sistema operativo detectado por el script.

- **`-SharedRuntime|--shared-runtime`**

  > [!NOTE]
  > Este parámetro está obsoleto y puede quitarse en una versión futura del script. La alternativa recomendada es la opción `-Runtime|--runtime`.

  Se instalan simplemente los bits del entorno de tiempo de ejecución compartido, no el SDK completo. Esta opción equivale a especificar `-Runtime|--runtime dotnet`.

- **`-SkipNonVersionedFiles|--skip-non-versioned-files`**

  Omite la instalación de archivos sin control de versiones, como *dotnet.exe*, si ya existen.

- **`-UncachedFeed|--uncached-feed`**

  Permite cambiar la dirección URL de la fuente no almacenada en caché que este instalador utiliza. Le recomendamos que no cambie este valor.

- **`-Verbose|--verbose`**

  Muestra la información de diagnóstico.

- **`-Version|--version <VERSION>`**

  Representa una versión de compilación concreta. Los valores posibles son:

  - `latest`: compilación más reciente en el canal (utilizado con la opción `-Channel`).
  - Versión de tres partes en formato X.Y.Z que representa una determinada versión de compilación; reemplaza a la opción `-Channel`. Por ejemplo: `2.0.0-preview2-006120`.

  Si no se especifica, el valor predeterminado de `-Version` es `latest`.

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

- Obtenga el script e instale ejemplos de una línea para la CLI de .NET:

  Windows:

  ```powershell
  # Run a separate PowerShell process because the script calls exit, so it will end the current PowerShell session.
  &powershell -NoProfile -ExecutionPolicy unrestricted -Command "[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; &([scriptblock]::Create((Invoke-WebRequest -UseBasicParsing 'https://dot.net/v1/dotnet-install.ps1'))) <additional install-script args>"
  ```

  macOS y Linux:

  ```bash
  curl -sSL https://dot.net/v1/dotnet-install.sh | bash /dev/stdin <additional install-script args>
  ```

## <a name="see-also"></a>Vea también

- [Versiones de .NET](https://github.com/dotnet/core/releases)
- [Archivo de descarga del SDK y el entorno de ejecución de .NET](https://github.com/dotnet/core/blob/master/release-notes/download-archive.md)
