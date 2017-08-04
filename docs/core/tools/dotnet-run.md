---
title: 'Comando dotnet-run: CLI de .NET Core'
description: "El comando dotnet-run proporciona una opción conveniente para ejecutar la aplicación desde el código fuente."
keywords: dotnet-run, CLI, comando de la CLI, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 03/22/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 40d4e60f-9900-4a48-b03c-0bae06792d91
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: f0a6fce4f83808076b7cbcabdaa948badde2cf80
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-run"></a>dotnet-run

## <a name="name"></a>Name 

`dotnet-run`: ejecuta el código fuente sin comandos explícitos de compilación o inicio.

## <a name="synopsis"></a>Sinopsis

`dotnet run [-c|--configuration] [-f|--framework] [-p|--project] [[--] [application arguments]] [-h|--help]`

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

`--`

Delimita los argumentos a `dotnet run` a partir de argumentos de la aplicación que se va a ejecutar. Todos los argumentos después de este se pasan a la aplicación que se ejecuta. 

`-h|--help`

Imprime una corta ayuda para el comando.

`-c|--configuration <CONFIGURATION>`

Configuración que se va a usar para compilar el proyecto. El valor predeterminado es `Debug`.

`-f|--framework <FRAMEWORK>`

Compila y ejecuta la aplicación con el [marco](../../standard/frameworks.md) especificado. El marco debe especificarse en el archivo de proyecto.

`-p|--project <PATH/PROJECT.csproj>`

Especifica la ruta de acceso y el nombre del archivo de proyecto. (Consulte la NOTA). Si no se especifica, se toma como predeterminado el directorio actual.

> [!NOTE]
> Use la ruta de acceso y el nombre del archivo del proyecto con la opción `-p|--project`. Una regresión en la CLI impide proporcionar una ruta de carpeta en este momento. Para más información y para realizar un seguimiento de este problema, consulte [dotnet run -p, can not start a project (dotnet/cli #5992)](https://github.com/dotnet/cli/issues/5992) (dotnet run -p, no puede iniciar un proyecto [dotnet/cli #5992]).

## <a name="examples"></a>Ejemplos

Ejecución del proyecto en el directorio actual:

`dotnet run` 

Ejecución del proyecto especificado:

`dotnet run --project /projects/proj1/proj1.csproj`

Ejecute el proyecto en el directorio actual (el argumento `--help` en este ejemplo se pasa a la aplicación, dado que se usó el argumento `--`):

`dotnet run --configuration Release -- --help`

