---
title: Comando dotnet-run | Microsoft Docs
description: "El comando dotnet-run proporciona una opción conveniente para ejecutar la aplicación desde el código fuente."
keywords: dotnet-run, CLI, comando de la CLI, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 40d4e60f-9900-4a48-b03c-0bae06792d91
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: 60bb9160e43788539b0dc6bcf1372bb925e9ba22
ms.lasthandoff: 03/07/2017

---

#<a name="dotnet-run"></a>dotnet-run

## <a name="name"></a>Name 

`dotnet-run`: ejecuta el código fuente disponible sin comandos explícitos de compilación o lanzamiento.

## <a name="synopsis"></a>Sinopsis

```
dotnet run [-c|--configuration] [-f|--framework] [-p|--project] [[--] [application arguments]]
dotnet run [-h|--help]
```

## <a name="description"></a>Descripción

El comando `dotnet run` proporciona una opción conveniente para ejecutar la aplicación desde el código fuente con un comando. Es útil para un desarrollo iterativo rápido en la línea de comandos. El comando depende del comando [`dotnet build`](dotnet-build.md) para compilar el código, por lo que cualquier requisito de la compilación, como que el proyecto tiene que restaurarse primero, se aplica a `dotnet run` también. 

Los archivos de salida se escriben en la ubicación predeterminada que es `bin/<configuration>/<target>`. Por ejemplo, si tiene una aplicación `netcoreapp1.0` y ejecuta `dotnet run`, el resultado se colocará en `bin/Debug/netcoreapp1.0`. Los archivos se sobrescriben según sea necesario. Los archivos temporales se colocan en el directorio `obj`. 

En el caso de un proyecto con varios marcos especificados, `dotnet run` mostrará un error a no ser que se use la opción `--framework` para especificar para qué marco se va a ejecutar la aplicación.

El comando `dotnet run` debe usarse en el contexto de proyectos, no de ensamblados compilados. Si, por el contrario, lo que intenta es ejecutar una DLL de aplicación portátil, debe usar [dotnet](dotnet.md) sin ningún comando, como en el ejemplo siguiente:
 
`dotnet myapp.dll`

Para más información sobre el controlador `dotnet`, consulte el tema [Herramientas de la interfaz de línea de comandos (CLI) de .NET Core](index.md).

Para ejecutar la aplicación, el comando `dotnet run` resuelve las dependencias de la aplicación que se encuentran fuera del entorno de tiempo de ejecución compartido desde la caché de NuGet. Por tanto, no se recomienda usar este comando para ejecutar aplicaciones en producción. En su lugar, debe [crear una implementación](../deploying/index.md) con el comando [`dotnet publish`](dotnet-publish.md) y usarlo en producción. 

## <a name="options"></a>Opciones

`--`

Delimita los argumentos a `dotnet run` a partir de argumentos de la aplicación que se va a ejecutar. Todos los argumentos después de este se pasarán a la aplicación que se ejecuta. 

`-h|--help`

Imprime una corta ayuda para el comando.

`-c|--configuration {Debug|Release}`

Configuración que se va a usar para compilar el proyecto. El valor predeterminado es `Debug`.

`-f|--framework <FRAMEWORK_IDENTIFIER>`

Compila y ejecuta la aplicación con el marco especificado. El marco tiene que especificarse en el archivo del proyecto.

`-p|--project <PATH>`

Especifica la ruta de acceso al archivo del proyecto que se va a ejecutar. Puede ser una ruta de acceso a un archivo [csproj](csproj.md) o a un directorio que contiene un archivo [csproj](csproj.md). Si no se especifica, se toma como predeterminado el directorio actual. 

## <a name="examples"></a>Ejemplos

Ejecución del proyecto en el directorio actual:

`dotnet run` 

Ejecución del proyecto especificado:

`dotnet run --project /projects/proj1/proj1.csproj`

Ejecución del proyecto en el directorio actual (el argumento `--help` en este ejemplo se pasa a la aplicación que se ejecuta, dado que se usó el argumento `--`):

`dotnet run --configuration Release -- --help`
