---
title: 'Comando dotnet run: CLI de .NET Core'
description: "El comando dotnet run proporciona una opción conveniente para ejecutar la aplicación desde el código fuente."
author: mairaw
ms.author: mairaw
ms.date: 09/24/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.openlocfilehash: 7670934199d7d4b8a7c5e598142366ef1eb3ef1c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="dotnet-run"></a>dotnet run

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>Name

`dotnet run`: ejecuta el código fuente sin comandos explícitos de compilación o inicio.

## <a name="synopsis"></a>Sinopsis

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

```
dotnet run [-c|--configuration] [-f|--framework] [--force] [--launch-profile] [--no-build] [--no-dependencies] [--no-launch-profile] [--no-restore] [-p|--project] [--runtime] [[--] [application arguments]]
dotnet run [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

```
dotnet run [-c|--configuration] [-f|--framework] [-p|--project] [[--] [application arguments]]
dotnet run [-h|--help]
```

---

## <a name="description"></a>Descripción

El comando `dotnet run` proporciona una opción conveniente para ejecutar la aplicación desde el código fuente con un comando. Es útil para un desarrollo iterativo rápido desde la línea de comandos. El comando depende del comando [`dotnet build`](dotnet-build.md) para compilar el código. Los requisitos para la compilación, como que el cliente se deba restaurar primero, también se aplican a `dotnet run`. 

Los archivos de salida se escriben en la ubicación predeterminada, que es `bin/<configuration>/<target>`. Por ejemplo, si tiene una aplicación `netcoreapp1.0` y ejecuta `dotnet run`, la salida se colocará en `bin/Debug/netcoreapp1.0`. Los archivos se sobrescriben según sea necesario. Los archivos temporales se colocan en el directorio `obj`. 

Si el proyecto especifica varios marcos, al ejecutar `dotnet run` se produce un error a menos que se use la opción `-f|--framework <FRAMEWORK>` para especificar el marco.

El comando `dotnet run` debe usarse en el contexto de proyectos, no de ensamblados compilados. Si, por el contrario, está intentando ejecutar una DLL de aplicación dependiente del marco de trabajo, debe usar [dotnet](dotnet.md) sin un comando. Por ejemplo, para ejecutar `myapp.dll`, use:

```
dotnet myapp.dll
```

Para más información sobre el controlador `dotnet`, consulte el tema [Herramientas de la interfaz de la línea de comandos (CLI) de .NET Core ](index.md).

Para ejecutar la aplicación, el comando `dotnet run` resuelve las dependencias de la aplicación que se encuentran fuera del entorno de tiempo de ejecución compartido desde la caché de NuGet. Dado que se usan dependencias almacenadas en caché, no se recomienda utilizar `dotnet run` para ejecutar aplicaciones en producción. En su lugar, [cree una implementación](../deploying/index.md) mediante el comando [`dotnet publish`](dotnet-publish.md) e implemente la salida publicada.

## <a name="options"></a>Opciones

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

`--`

Delimita los argumentos a `dotnet run` a partir de argumentos de la aplicación que se va a ejecutar. Todos los argumentos después de este se pasan a la aplicación que se ejecuta.

`-c|--configuration {Debug|Release}`

Define la configuración de compilación. El valor predeterminado es `Debug`.

`-f|--framework <FRAMEWORK>`

Compila y ejecuta la aplicación con el [marco](../../standard/frameworks.md) especificado. El marco debe especificarse en el archivo de proyecto.

`--force`

Fuerza la resolución de todas las dependencias, incluso si la última restauración se realizó correctamente. Esto es equivalente a eliminar *project.assets.json*.

`-h|--help`

Imprime una corta ayuda para el comando.

`--launch-profile <NAME>`

El nombre del perfil de inicio (si lo hay) que se usará al iniciar la aplicación. Los perfiles de inicio se definen en el archivo *launchSettings.json* y se suelen denominar simplemente `Development`, `Staging` y `Production`. Para obtener más información, consulte [Working with multiple environments](/aspnet/core/fundamentals/environments) (Trabajo con varios entornos).

`--no-build`

No compila el proyecto antes de ejecutarlo.

`--no-dependencies`

Al restaurar un proyecto con referencias de proyecto a proyecto (P2P), se restaura el proyecto raíz y no las referencias.

`--no-launch-profile`

No intenta usar *launchSettings.json* para configurar la aplicación.

`--no-restore`

No realiza una restauración implícita al ejecutar el comando.

`-p|--project <PATH>`

Especifica la ruta de acceso del archivo del proyecto que se va a ejecutar (nombre de la carpeta o ruta de acceso completa). Si no se especifica, se toma como predeterminado el directorio actual.

`--runtime <RUNTIME_IDENTIFIER>`

Especifica el tiempo de ejecución de destino para el que restaurar los paquetes. Para obtener una lista de identificadores de tiempo de ejecución (RID), consulte el [catálogo de RID](../rid-catalog.md).

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

`--`

Delimita los argumentos a `dotnet run` a partir de argumentos de la aplicación que se va a ejecutar. Todos los argumentos después de este se pasan a la aplicación que se ejecuta.

`-c|--configuration {Debug|Release}`

Define la configuración de compilación. El valor predeterminado es `Debug`.

`-f|--framework <FRAMEWORK>`

Compila y ejecuta la aplicación con el [marco](../../standard/frameworks.md) especificado. El marco debe especificarse en el archivo de proyecto.

`-h|--help`

Imprime una corta ayuda para el comando.

`-p|--project <PATH/PROJECT.csproj>`

Especifica la ruta de acceso y el nombre del archivo de proyecto. (Consulte la NOTA). Si no se especifica, se toma como predeterminado el directorio actual.

> [!NOTE]
> Use la ruta de acceso y el nombre del archivo del proyecto con la opción `-p|--project`. Una regresión en la CLI impide proporcionar una ruta de carpeta con el SDK de .NET Core 1.x. Para obtener más información sobre este problema, consulte [dotnet run -p, can not start a project (dotnet/cli #5992)](https://github.com/dotnet/cli/issues/5992) (dotnet run -p, no puede iniciar un proyecto [dotnet/cli #5992]).

---

## <a name="examples"></a>Ejemplos

Ejecución del proyecto en el directorio actual:

`dotnet run`

Ejecución del proyecto especificado:

`dotnet run --project /projects/proj1/proj1.csproj`

Ejecute el proyecto en el directorio actual (el argumento `--help` en este ejemplo se pasa a la aplicación, dado que se usó el argumento `--`):

`dotnet run --configuration Release -- --help`
