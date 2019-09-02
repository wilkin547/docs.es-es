---
title: Comando dotnet migrate
description: El comando dotnet migrate migra un proyecto y todas sus dependencias.
ms.date: 06/26/2019
ms.openlocfilehash: 86f11592e774da12b010886aaa1e30cee063fea6
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2019
ms.locfileid: "70202541"
---
# <a name="dotnet-migrate"></a>dotnet migrate

**Este tema se aplica a: ✓** SDK de .NET Core 1.x y versiones posteriores

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a>nombre

`dotnet migrate`: migra un proyecto .NET Core de la versión preliminar 2 a un proyecto del estilo de SDK de .NET Core.

> [!NOTE]
> `dotnet migrate` se quitará del SDK de .NET Core 3.0 en la próxima publicación de versión preliminar.

## <a name="synopsis"></a>Sinopsis

```console
dotnet migrate [<SOLUTION_FILE|PROJECT_DIR>] [--format-report-file-json] [-r|--report-file] [-s|--skip-project-references] [--skip-backup] [-t|--template-file] [-v|--sdk-package-version] [-x|--xproj-file]
dotnet migrate [-h|--help]
```

## <a name="description"></a>DESCRIPCIÓN

Con el comando `dotnet migrate` se migra un proyecto válido basado en *project.json* de la versión preliminar 2 a un proyecto válido *csproj* del estilo de SDK de .NET Core.

De forma predeterminada, el comando migra el proyecto raíz y todas las referencias de proyecto que contiene. Este comportamiento se deshabilita mediante la opción `--skip-project-references` en tiempo de ejecución.

La migración se puede realizar en los recursos siguientes:

* Un único proyecto mediante la especificación del archivo *project.json* que quiere migrar.
* Todos los directorios especificados en el archivo *global.json* pasando una ruta al archivo *global.json*.
* Un archivo *solution.sln*, donde se migran los proyectos a los que se hace referencia en la solución.
* Todos los subdirectorios del directorio dado de manera recursiva.

El comando `dotnet migrate` mantiene el archivo *project.json* migrado dentro de un directorio `backup`, que se crea en caso de que no exista. Este comportamiento se invalida con la opción `--skip-backup`.

De forma predeterminada, la operación de migración genera el estado del proceso de migración a la salida estándar (STDOUT). Si usa la opción `--report-file <REPORT_FILE>`, la salida se guarda en el archivo especificado.

El comando `dotnet migrate` solo admite proyectos válidos basados en *project.json* de la versión preliminar 2. Esto significa que no se puede usar para migrar DNX o los proyectos basados en *project.json* de la versión preliminar 1 directamente a proyectos de MSBuild/csproj. Primero debe migrar manualmente el proyecto a un proyecto basado en *project.json* de la versión preliminar 2 y luego usar el comando `dotnet migrate` para migrar el proyecto.

## <a name="arguments"></a>Argumentos

`PROJECT_JSON/GLOBAL_JSON/SOLUTION_FILE/PROJECT_DIR`

La ruta de acceso a uno de los siguientes elementos:

* Un archivo *project.json* para migrar.
* Un archivo *global.json*: se migran las carpetas especificadas en *global.json*.
* Un archivo *solution.sln*: se migran los proyectos a los que se hace referencia en la solución.
* Un directorio para migrar: se buscan de forma recursiva los archivos *project.json* que se van a migrar dentro del directorio especificado.

Si no se especifica nada, se toma como valor predeterminado el directorio actual.

## <a name="options"></a>Opciones

`--format-report-file-json <REPORT_FILE>`

Salida del archivo de informe de migración como JSON en lugar de mensajes de usuario.

`-h|--help`

Imprime una corta ayuda para el comando.

`-r|--report-file <REPORT_FILE>`

Salida del informe de migración a un archivo además de a la consola.

`-s|--skip-project-references [Debug|Release]`

Omite la migración de referencias de proyecto. De forma predeterminada, las referencias de proyecto se migran de forma recursiva.

`--skip-backup`

Omite el traslado de *project.json*, *global.json* y *\*.xproj* a un directorio `backup` tras la realización correcta de la migración.

`-t|--template-file <TEMPLATE_FILE>`

Archivo csproj de plantilla que se utilizará para la migración. De forma predeterminada, se usa la misma plantilla que la descartada por `dotnet new console`.

`-v|--sdk-package-version <VERSION>`

La versión del paquete sdk a la que se hace referencia en la aplicación migrada. El valor predeterminado es la versión del SDK en `dotnet new`.

`-x|--xproj-file <FILE>`

La ruta de acceso al archivo xproj que se usará. Necesario cuando hay más de un archivo xproj en un directorio de proyecto.

## <a name="examples"></a>Ejemplos

Migrar un proyecto del directorio actual y todas sus dependencias de proyecto a proyecto:

`dotnet migrate`

Migrar todos los proyectos que incluyen el archivo *global.json*:

`dotnet migrate path/to/global.json`

Migrar solo el proyecto actual y ninguna dependencia de proyecto a proyecto (P2P). Además, usar una versión específica de SDK:

`dotnet migrate -s -v 1.0.0-preview4`
