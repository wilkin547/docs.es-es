---
title: CLI de .NET
titleSuffix: ''
description: Información general de la CLI de .NET y sus características.
ms.topic: overview
ms.date: 02/13/2020
ms.openlocfilehash: 6a12e2d16afe36092c10e14a7465fa3bdbb23f32
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2020
ms.locfileid: "94633861"
---
# <a name="net-cli-overview"></a>Información general sobre la CLI de .NET

**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.1 y versiones posteriores

La interfaz de la línea de comandos (CLI) de .NET es una cadena de herramientas multiplataforma que sirve para desarrollar, compilar, ejecutar y publicar aplicaciones .NET.

La CLI de .NET se incluye con el [SDK de .NET](../sdk.md). Para obtener más información sobre cómo instalar el SDK de .NET, vea [Instalación de .NET Core](../install/windows.md).

## <a name="cli-commands"></a>Comandos de la CLI

De forma predeterminada, se instalan los siguientes comandos:

### <a name="basic-commands"></a>Comandos básicos

- [`new`](dotnet-new.md)
- [`restore`](dotnet-restore.md)
- [`build`](dotnet-build.md)
- [`publish`](dotnet-publish.md)
- [`run`](dotnet-run.md)
- [`test`](dotnet-test.md)
- [`vstest`](dotnet-vstest.md)
- [`pack`](dotnet-pack.md)
- [`migrate`](dotnet-migrate.md)
- [`clean`](dotnet-clean.md)
- [`sln`](dotnet-sln.md)
- [`help`](dotnet-help.md)
- [`store`](dotnet-store.md)

### <a name="project-modification-commands"></a>Comandos de modificación del proyecto

- [`add package`](dotnet-add-package.md)
- [`add reference`](dotnet-add-reference.md)
- [`remove package`](dotnet-remove-package.md)
- [`remove reference`](dotnet-remove-reference.md)
- [`list reference`](dotnet-list-reference.md)

### <a name="advanced-commands"></a>Comandos avanzados

- [`nuget delete`](dotnet-nuget-delete.md)
- [`nuget locals`](dotnet-nuget-locals.md)
- [`nuget push`](dotnet-nuget-push.md)
- [`msbuild`](dotnet-msbuild.md)
- [`dotnet install script`](dotnet-install-script.md)

### <a name="tool-management-commands"></a>Comandos de administración de herramientas

- [`tool install`](dotnet-tool-install.md)
- [`tool list`](dotnet-tool-list.md)
- [`tool update`](dotnet-tool-update.md)
- [`tool restore`](global-tools.md#install-a-local-tool) Disponible a partir del SDK de .NET Core 3.0.
- [`tool run`](global-tools.md#invoke-a-local-tool) Disponible a partir del SDK de .NET Core 3.0.
- [`tool uninstall`](dotnet-tool-uninstall.md)

Las herramientas son aplicaciones de consola que se instalan mediante paquetes NuGet y se invocan desde el símbolo del sistema. Puede encargarse de escribir las herramientas o instalar las escritas por terceros. Las herramientas también se denominan herramientas globales, herramientas de ruta de acceso de herramientas y herramientas locales. Para obtener más información, vea la [información general sobre las herramientas de .NET](global-tools.md).

## <a name="command-structure"></a>Estructura de comandos

La estructura de comandos de la CLI consta del [controlador ("dotnet")](#driver), [el comando](#command) y posiblemente de los [argumentos de comandos](#arguments) y otras [opciones](#options). Este patrón se puede ver en la mayoría de las operaciones de la CLI, como la creación de una nueva aplicación de consola y su ejecución desde la línea de comandos, como muestran los siguientes comandos cuando se ejecutan desde un directorio denominado *my_app*:

```dotnetcli
dotnet new console
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

### <a name="driver"></a>Controlador

El controlador se denomina [dotnet](dotnet.md) y tiene dos responsabilidades, ejecutar una [aplicación dependiente del marco](../deploying/index.md) o ejecutar un comando.

Para ejecutar una aplicación dependiente del marco, especifique la aplicación después del controlador, por ejemplo, `dotnet /path/to/my_app.dll`. Cuando ejecute el comando desde la carpeta donde reside la DLL de la aplicación, simplemente ejecute `dotnet my_app.dll`. Si quiere usar una versión específica del entorno de ejecución .NET, use la opción `--fx-version <VERSION>` (consulte la referencia del [comando dotnet](dotnet.md)).

Cuando se proporciona un comando para el controlador, `dotnet.exe` inicia el proceso de ejecución del comando de la CLI. Por ejemplo:

```dotnetcli
dotnet build
```

En primer lugar, el controlador determina la versión de SDK que se debe usar. Si no hay ningún archivo [global.json](global-json.md), se usa la última versión del SDK disponible. Podría tratarse de una versión preliminar o de una versión estable, en función de lo último que esté disponible en el equipo.  Una vez determinada la versión del SDK, se ejecutará el comando.

### <a name="command"></a>Comando

El comando realiza una acción. Por ejemplo, `dotnet build` compila código. `dotnet publish` publica el código. Los comandos se implementan como una aplicación de consola usando una convención `dotnet {command}`.

### <a name="arguments"></a>Argumentos

Los argumentos que se pasan en la línea de comandos son los argumentos para el comando invocado. Por ejemplo, cuando ejecuta `dotnet publish my_app.csproj`, el argumento `my_app.csproj` indica el proyecto que se publicará y se pasa al comando `publish`.

### <a name="options"></a>Opciones

Las opciones que se pasan en la línea de comandos son las opciones para el comando que se invoca. Por ejemplo, cuando ejecuta `dotnet publish --output /build_output`, la opción `--output` y su valor se pasan al comando `publish`.

## <a name="see-also"></a>Vea también

- [Repositorio de GitHub dotnet/sdk](https://github.com/dotnet/sdk/)
- [Guía de instalación de .NET](../install/windows.md)
