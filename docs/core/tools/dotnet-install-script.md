---
title: Scripts de dotnet-install | Microsoft Docs
description: "Aprenda sobre los scripts de dotnet-install para instalar las herramientas de la CLI de .NET Core y el entorno de tiempo de ejecución compartido."
keywords: dotnet-install, scripts de dotnet-install, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: b64e7e6f-ffb4-4fc8-b43b-5731c89479c2
translationtype: Human Translation
ms.sourcegitcommit: 99254f84873003496ee00214d55ff908f9fd47d3
ms.openlocfilehash: 6301fb61be27d7dac6ead57159c0d9461b3eacb5
ms.lasthandoff: 03/07/2017

---

#<a name="dotnet-install-scripts-reference"></a>referencia de scripts de dotnet-install

## <a name="name"></a>Name

`dotnet-install.ps1` | `dotnet-install.sh`: script usado para instalar las herramientas de la interfaz de línea de comandos (CLI) de .NET Core y el entorno de tiempo de ejecución compartido.

## <a name="synopsis"></a>Sinopsis
Windows:

```
dotnet-install.ps1 [-Channel] [-Version] [-InstallDir] [-Architecture]
    [-SharedRuntime] [-DebugSymbols] [-DryRun] [-NoPath] [-AzureFeed] [-ProxyAddress]
```

macOS y Linux:

```
dotnet-install.sh [--channel] [--version] [--install-dir] [--architecture]
    [--shared-runtime] [--debug-symbols] [--dry-run] [--no-path] [--verbose] [--azure-feed] [--help]
```

## <a name="description"></a>Descripción
Los scripts de `dotnet-install` se usan para realizar una instalación sin derechos administrativos de la cadena de herramientas de CLI y del entorno de tiempo de ejecución compartido. Puede descargar los scripts de nuestro [repositorio de GitHub de CLI](https://github.com/dotnet/cli/tree/rel/1.0.0/scripts/obtain). 

Sus casos de uso principal es ayudar con los escenarios de automatización y las instalaciones sin derechos administrativos. Existen dos scripts, uno para PowerShell que funciona en Windows y un script de Bash que funciona en Linux y OS X. Ambos tienen el mismo comportamiento. El script de Bash también "comprende" los modificadores de PowerShell, de modo que puede usarlos en todos los ámbitos. 

Lo scripts de instalación descargarán el archivo ZIP o tarball desde las entregas de compilación de la CLI y procederán a instalarlo en la ubicación predeterminada o en una ubicación especificada por `--install-dir`. De forma predeterminada, el script de instalación descargará el SDK y lo instalará; si solo desea obtener el entorno de tiempo de ejecución compartido, puede especificar el argumento `--shared-runtime`. 

De forma predeterminada, el script agrega la ubicación de instalación a $PATH para la sesión actual. Esto se puede invalidar si se usa el argumento `--no-path`. 

Antes de ejecutar el script, instale todas las [dependencias](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md) necesarias.

Puede instalar una versión específica mediante el argumento `--version`. La versión debe especificarse como formada por tres partes (por ejemplo, 1.0.0-13232). Si se omite, se tomará como predeterminado el primer archivo [global.json](global-json.md) que se encuentra en la jerarquía encima de la carpeta donde se invocó el script que contiene la propiedad `version`. Si no está presente, se usará Latest.

También puede usar este script para obtener el SDK o los archivos binarios de depuración del entorno de tiempo de ejecución compartido con símbolos de depuración mediante el argumento `--debug`. Si esto no lo hace en la primera instalación y se da cuenta de que no necesita símbolos de depuración más adelante, puede volver a ejecutar el script con este argumento y la versión de los bits que ha instalado. 

## <a name="options"></a>Opciones
Las opciones son diferentes entre implementaciones de scripts. 

### <a name="powershell-windows"></a>PowerShell (Windows)
`-Channel [CHANNEL]`

El canal (por ejemplo, `future`, `preview`, `production`) desde el que instalarlo. El valor predeterminado es `production`.

`-Version [VERSION]`

Qué versión de la CLI se va a instalar. Necesita especificar la versión como una versión formada por tres partes (por ejemplo, 1.0.0-13232). Si se omite, se tomará como predeterminado el primer archivo [global.json](global-json.md) que contiene la propiedad `version`. Si no está presente, se usará Latest.

`-InstallDir [DIR]`

Ruta de acceso de instalación. Si no existe el directorio, se crea. El valor predeterminado es *% LocalAppData %\.dotnet*.

`-Architecture [ARCH]`

Arquitectura de los archivos binarios de .NET Core que se van a instalar. Los valores posibles son &lt;auto&gt;, x64 y x86. El valor predeterminado es &lt;auto&gt;, que representa la arquitectura de SO que está ejecutando en estos momentos.

`-SharedRuntime`

Si se establece, se instalan simplemente los bits del entorno de tiempo de ejecución compartido, no el SDK completo.

`-DebugSymbols`

Si se establece, el instalador incluirá símbolos de depuración en la instalación.

> [!NOTE]
> Este modificador no funciona todavía.

`-DryRun`

Si se establece, el script no realizará la instalación pero, en su lugar, mostrará qué línea de comandos se va a usar para instalar de manera coherente la versión solicitada en estos momentos de la CLI de .NET. Por ejemplo, si especifica la versión `latest`, mostrará un vínculo con la versión específica, de manera que este comando pueda usarse de manera determinista en un script de compilación.
También muestra la ubicación de los archivos binarios si prefiere instalarla o descargarla usted mismo.

`-NoPath`

Si se establece, el prefijo/installdir no se exportan a la ruta de acceso para la sesión actual. De manera predeterminada, el script modificará la ruta de acceso, que hace que las herramientas de la CLI estén disponibles inmediatamente después de la instalación.

`-AzureFeed`

La dirección URL de la fuente de Azure que va a usar este instalador. No se recomienda su modificación. De manera predeterminada, es `https://dotnetcli.azureedge.net/dotnet`.

`-ProxyAddress`

Si se establece, el instalador usará el proxy al realizar solicitudes web.

### <a name="bash-macoslinux"></a>Bash (macOS y Linux)

`dotnet-install.sh [--channel] [--version] [--install-dir] [--architecture]
    [--shared-runtime] [--debug-symbols] [--dry-run] [--no-path] [--verbose] [--azure-feed] [--help]
`

`--channel [CHANNEL]`

El canal (por ejemplo "futuro", "desarrollo", "producción") desde el que se instalará. El valor predeterminado es "Producción".

`--version [VERSION]`

Qué versión de la CLI se va a instalar. Necesita especificar la versión como una versión formada por tres partes (por ejemplo, 1.0.0-13232). Si se omite, se tomará como predeterminado el primer archivo [global.json](global-json.md) que contiene la propiedad `version`. Si no está presente, se usará Latest.

`--install-dir [DIR]`

Ruta de acceso a la ubicación de instalación. Si no existe el directorio, se crea. El valor predeterminado es `$HOME/.dotnet`.

`--architecture [ARCH]`

Arquitectura de los archivos binarios de .NET que se van a instalar. Los valores posibles son &lt;auto&gt;, x64 y amd64. El valor predeterminado es &lt;auto&gt;, que representa la arquitectura de SO que está ejecutando en estos momentos.

`--shared-runtime`

Si se establece, se instalan simplemente los bits del entorno de tiempo de ejecución compartido, no el SDK completo.

`--debug-symbols`

Si se establece, el instalador incluirá símbolos de depuración en la instalación.

> [!NOTE]
> Este modificador no funciona todavía.

`--dry-run`

Si se establece, el script no realizará la instalación pero, en su lugar, mostrará qué línea de comandos se va a usar para instalar de manera coherente la versión solicitada en estos momentos de la CLI de .NET. Por ejemplo, si especifica la versión `latest`, mostrará un vínculo con la versión específica, de manera que este comando pueda usarse de manera determinista en un script de compilación.
También muestra la ubicación de los archivos binarios si prefiere instalarla o descargarla usted mismo.

`--no-path`

Si se establece, el prefijo/installdir no se exportan a la ruta de acceso para la sesión actual. De manera predeterminada, el script modificará la ruta de acceso, que hace que las herramientas de la CLI estén disponibles inmediatamente después de la instalación.

`--verbose`

Muestra la información de diagnóstico.

`--azure-feed`

La dirección URL de la fuente de Azure que va a usar este instalador. No se recomienda su modificación. De manera predeterminada, es `https://dotnetcli.azureedge.net/dotnet`.

`--help`

Imprime la ayuda para el script.

## <a name="examples"></a>Ejemplos

Instale la versión más reciente de desarrollo en la ubicación predeterminada:

Windows:

`./dotnet-install.ps1 -Channel Future`

macOS y Linux:

`./dotnet-install.sh --channel Future`

Instale la versión preliminar más reciente en la ubicación especificada:

Windows:

`./dotnet-install.ps1 -Channel preview -InstallDir C:\cli`

macOS y Linux:

`./dotnet-install.sh --channel preview --install-dir ~/cli`
