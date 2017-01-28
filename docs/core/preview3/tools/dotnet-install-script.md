---
title: Scripts de dotnet-install | .NET Core SDK
description: "Aprenda sobre los scripts de dotnet-install para instalar las herramientas de la CLI de .NET Core y el entorno de tiempo de ejecución compartido."
keywords: dotnet-install, scripts de dotnet-install, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 10/12/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 59b9c456-2bfd-4adc-8202-a1c6a0a6c787
translationtype: Human Translation
ms.sourcegitcommit: 1a84c694945fe0c77468eb77274ab46618bccae6
ms.openlocfilehash: 08a401abed36e68caa7172e05184d18469fef48f

---

#<a name="dotnet-install-scripts-reference"></a>referencia de scripts de dotnet-install

## <a name="name"></a>Nombre
dotnet-install.ps1 | dotnet-install.sh: script usado para instalar las herramientas de la interfaz de línea de comandos (CLI) y el entorno de tiempo de ejecución compartido

## <a name="synopsis"></a>Sinopsis
Windows:

`dotnet-install.ps1 [-Channel] [-Version]
    [-InstallDir] [-Debug] [-NoPath] 
    [-SharedRuntime]`

macOS y Linux:

`dotnet-install.sh [--channel] [--version]
    [--install-dir] [--debug] [--no-path] 
    [--shared-runtime]`

## <a name="description"></a>Descripción
Los scripts de `dotnet-install` se usan para realizar una instalación sin derechos administrativos de la cadena de herramientas de CLI y del entorno de tiempo de ejecución compartido. Puede descargar los scripts de nuestro [repositorio de GitHub de CLI](https://github.com/dotnet/cli/tree/rel/1.0.0-preview2/scripts/obtain). 

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

La versión de CLI que se instalará; debe especificar la versión como formada por tres partes (por ejemplo, 1.0.0-13232). Si se omite, se tomará como predeterminado el primer archivo [global.json](global-json.md) que contiene la propiedad `version`; si no está presente, se usará Latest.     

`-InstallDir [DIR]`

Ruta de acceso de instalación. Si no existe el directorio, se crea. El valor predeterminado es *% LocalAppData %\.dotnet*.

`-Debug`

`true` para indicar que se deben usar paquetes más grandes que contengan símbolos de depuración; de lo contrario, `false`. El valor predeterminado es `false`.

`-NoPath`

`true` para indicar que el prefijo/installdir no se exportan a la ruta de acceso para la sesión actual; de lo contrario, `false`. El valor predeterminado es `false`, es decir, se modifica el valor de PATH. Esto hace que las herramientas de la CLI estén disponibles inmediatamente tras la instalación. 

`-SharedRuntime`

`true` para instalar los bits del entorno de tiempo de ejecución compartido; `false` para instalar el SDK completo. El valor predeterminado es `false`.

### <a name="bash-macoslinux"></a>Bash (macOS y Linux)
`--channel [CHANNEL]`

El canal (por ejemplo "futuro", "vista previa", "producción") desde el que se instalará. El valor predeterminado es "Producción".

`--version [VERSION]`

La versión de CLI que se instalará; debe especificar la versión como formada por tres partes (por ejemplo, 1.0.0-13232). Si se omite, se tomará como predeterminado el primer archivo [global.json](global-json.md) que contiene la propiedad `version`; si no está presente, se usará Latest.     

`--install-dir [DIR]`

Ruta de acceso a la ubicación de instalación. Si no existe el directorio, se crea. El valor predeterminado es `$HOME/.dotnet`.

`--debug`

`true` para indicar que se deben usar paquetes más grandes que contengan símbolos de depuración; de lo contrario, `false`. El valor predeterminado es `false`.

`--no-path`

`true` para indicar que el prefijo/installdir no se exportan a la ruta de acceso para la sesión actual; de lo contrario, `false`. El valor predeterminado es `false`, es decir, se modifica el valor de PATH. Esto hace que las herramientas de la CLI estén disponibles inmediatamente tras la instalación.  

`--shared-runtime`

`true` para instalar los bits del entorno de tiempo de ejecución compartido; `false` para instalar el SDK completo. El valor predeterminado es `false`.

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



<!--HONumber=Nov16_HO3-->


