---
title: Scripts de dotnet-install | Microsoft Docs
description: "Aprenda sobre los scripts de dotnet-install para instalar las herramientas de la CLI de .NET Core y el entorno de tiempo de ejecución compartido."
keywords: dotnet-install, scripts de dotnet-install, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: b64e7e6f-ffb4-4fc8-b43b-5731c89479c2
translationtype: Human Translation
ms.sourcegitcommit: 4a1f0c88fb1ccd6694f8d4f5687431646adbe000
ms.openlocfilehash: fbc1ce8d864a5c2150c61f4b8bf7cb8544921634
ms.lasthandoff: 03/22/2017

---

# <a name="dotnet-install-scripts-reference"></a>referencia de scripts de dotnet-install

## <a name="name"></a>Name

`dotnet-install.ps1` | `dotnet-install.sh`: script usado para instalar las herramientas de la interfaz de la línea de comandos (CLI) de .NET Core y el entorno de tiempo de ejecución compartido.

## <a name="synopsis"></a>Sinopsis

Windows:

`dotnet-install.ps1 [-Channel] [-Version] [-InstallDir] [-Architecture] [-SharedRuntime] [-DebugSymbols] [-DryRun] [-NoPath] [-AzureFeed] [-ProxyAddress]`

macOS y Linux:

`dotnet-install.sh [--channel] [--version] [--install-dir] [--architecture] [--shared-runtime] [--debug-symbols] [--dry-run] [--no-path] [--verbose] [--azure-feed] [--help]`

## <a name="description"></a>Descripción

Los scripts de `dotnet-install` se usan para realizar una instalación sin derechos administrativos de la cadena de herramientas de CLI y del entorno de tiempo de ejecución compartido. Puede descargar los scripts del [repositorio de GitHub de CLI](https://github.com/dotnet/cli/tree/rel/1.0.0/scripts/obtain). 

La utilidad principal de estos scripts está en los escenarios de automatización y las instalaciones sin derechos administrativos. Hay dos scripts: uno es un script de PowerShell que funciona en Windows. El otro es un script de bash que funciona en Linux y OS X. Ambos scripts tienen el mismo comportamiento. El script de bash también lee modificadores de PowerShell, por lo que puede usar modificadores de PowerShell con el script en sistemas Linux y OS X. 

Los scripts de instalación descargan el archivo ZIP o tarball desde las entregas de compilación de la CLI y proceden a instalarlo en la ubicación predeterminada o en una ubicación especificada por `-InstallDir|--install-dir`. De forma predeterminada, los scripts de instalación descargan el SDK y lo instalan. Si desea obtener solo el tiempo de ejecución compartido, especifique el argumento `--shared-runtime`. 

De forma predeterminada, el script agrega la ubicación de instalación a $PATH para la sesión actual. Para invalidar este comportamiento, especifique el argumento `--no-path`. 

Antes de ejecutar el script, instale las [dependencias](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md) necesarias.

Puede instalar una versión específica mediante el argumento `--version`. La versión debe especificarse como una versión de 3 partes (por ejemplo, 1.0.0-13232). Si se omite, se tomará como predeterminado el primer archivo [global.json](global-json.md) que se encuentra en la jerarquía encima de la carpeta donde se invoca el script que contiene la propiedad `version`. Si no está presente, se usará la versión más reciente.

También puede usar este script para obtener el SDK o los archivos binarios de depuración del entorno de tiempo de ejecución compartido con símbolos de depuración mediante el argumento `--debug`. Si no puede hacerlo en la primera instalación y más adelante se da cuenta que necesita los símbolos de depuración, puede volver a ejecutar el script con el argumento `--debug` y la versión del SDK que instaló para obtener los símbolos de depuración. 

## <a name="options"></a>Opciones

Nota: Las opciones son diferentes entre implementaciones de scripts. 

### <a name="powershell-windows"></a>PowerShell (Windows)

`-Channel <CHANNEL>`

Especifica el canal de origen para la instalación. Los valores son `future`, `preview` y `production`. El valor predeterminado es `production`.

`-Version <VERSION>`

Especifica la versión de CLI para instalar. Debe especificar la versión como una versión formada por tres partes (por ejemplo, 1.0.0-13232). Si se omite, se toma como predeterminado el primer archivo [global.json](global-json.md) que contiene la propiedad `version`. Si no está presente, se usará la versión más reciente.

`-InstallDir <DIRECTORY>`

Especifica la ruta de instalación. Si no existe el directorio, se crea. El valor predeterminado es *% LocalAppData %\.dotnet*.

`-Architecture <ARCHITECTURE>`

Arquitectura de los archivos binarios de .NET Core para instalar. Los valores posibles son `auto`, `x64`, y `x86`. El valor predeterminado es `auto`, que representa la arquitectura de SO que se ejecuta en ese momento.

`-SharedRuntime`

Si se establece, este modificador limita la instalación al entorno de tiempo de ejecución compartido. No está instalado el SDK completo.

`-DebugSymbols` (consulte la NOTA)

Si se establece, el instalador incluye símbolos de depuración en la instalación.

> [!NOTE]
> El modificador `-DebugSymbols` no está actualmente disponible pero se prevé que lo esté en una futura versión.

`-DryRun`

Si se establece, el script no realizará la instalación pero, en su lugar, mostrará qué línea de comandos se va a usar para instalar de manera coherente la versión solicitada en estos momentos de la CLI de .NET. Por ejemplo, si especifica la versión `latest`, se muestra un vínculo con la versión específica, de manera que este comando puede usarse de manera determinista en un script de compilación. También se muestra la ubicación de los archivos binarios si prefiere instalarla o descargarla por su cuenta.

`-NoPath`

Si se establece, el prefijo/installdir no se exportan a la ruta de acceso para la sesión actual. De manera predeterminada, el script modificará la ruta de acceso, que hace que las herramientas de la CLI estén disponibles inmediatamente después de la instalación.

`-AzureFeed`

Especifica la dirección URL de la fuente de Azure al instalador. No se recomienda cambiar este valor. De manera predeterminada, es `https://dotnetcli.azureedge.net/dotnet`.

`-ProxyAddress`

Si se establece, el instalador usa el proxy al realizar solicitudes web.

### <a name="bash-macoslinux"></a>Bash (macOS y Linux)

`dotnet-install.sh [--channel] [--version] [--install-dir] [--architecture] [--shared-runtime] [--debug-symbols] [--dry-run] [--no-path] [--verbose] [--azure-feed] [--help]`

`--channel <CHANNEL>`

Especifica el canal de origen para la instalación. Los valores son `future`, `dev` y `production`. El valor predeterminado es `production`.

`--version <VERSION>`

Especifica la versión de CLI para instalar. Debe especificar la versión como una versión formada por tres partes (por ejemplo, 1.0.0-13232). Si se omite, se toma como predeterminado el primer archivo [global.json](global-json.md) que contiene la propiedad `version`. Si no está presente, se usará la versión más reciente.

`--install-dir <DIRECTORY>`

Especifica la ruta de instalación. Si no existe el directorio, se crea. El valor predeterminado es `$HOME/.dotnet`.

`--architecture <ARCHITECTURE>`

Arquitectura de los archivos binarios de .NET Core para instalar. Los valores posibles son `auto`, `x64`, `amd64`. El valor predeterminado es `auto`, que representa la arquitectura de SO que se ejecuta en ese momento.

`--shared-runtime`

Si se establece, este modificador limita la instalación al entorno de tiempo de ejecución compartido. No está instalado el SDK completo.

`--debug-symbols`

Si se establece, el instalador incluye símbolos de depuración en la instalación.

> [!NOTE]
> Este modificador no está actualmente disponible pero se prevé que lo esté en una futura versión.

`--dry-run`

Si se establece, el script no realizará la instalación pero, en su lugar, mostrará qué línea de comandos se va a usar para instalar de manera coherente la versión solicitada en estos momentos de la CLI de .NET. Por ejemplo, si especifica la versión `latest`, se muestra un vínculo con la versión específica, de manera que este comando puede usarse de manera determinista en un script de compilación. También se muestra la ubicación de los archivos binarios si prefiere instalarla o descargarla por su cuenta.

`--no-path`

Si se establece, el prefijo/installdir no se exportan a la ruta de acceso para la sesión actual. De manera predeterminada, el script modificará la ruta de acceso, que hace que las herramientas de la CLI estén disponibles inmediatamente después de la instalación.

`--verbose`

Muestra la información de diagnóstico.

`--azure-feed`

Especifica la dirección URL de la fuente de Azure al instalador. No se recomienda cambiar este valor. De manera predeterminada, es `https://dotnetcli.azureedge.net/dotnet`.

`--help`

Imprime la ayuda para el script.

## <a name="examples"></a>Ejemplos

Instalar la versión de desarrollo más reciente en la ubicación predeterminada:

Windows:

`./dotnet-install.ps1 -Channel Future`

macOS y Linux:

`./dotnet-install.sh --channel Future`

Instale la versión preliminar más reciente en la ubicación especificada:

Windows:

`./dotnet-install.ps1 -Channel preview -InstallDir C:\cli`

macOS y Linux:

`./dotnet-install.sh --channel preview --install-dir ~/cli`
