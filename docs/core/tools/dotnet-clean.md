---
title: 'Comando dotnet clean: CLI de .NET Core'
description: El comando dotnet clean limpia el directorio actual.
author: mairaw
ms.author: mairaw
ms.date: 05/25/2018
ms.openlocfilehash: 5553e4b4423a2d824c05caf7114c47b5f1c20477
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "45988340"
---
# <a name="dotnet-clean"></a>dotnet clean

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>nombre

`dotnet clean`: limpia la salida de un proyecto.

## <a name="synopsis"></a>Sinopsis

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)
```
dotnet clean [<PROJECT>] [-c|--configuration] [-f|--framework] [-o|--output] [-r|--runtime] [-v|--verbosity]
dotnet clean [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)
```
dotnet clean [<PROJECT>] [-c|--configuration] [-f|--framework] [-o|--output] [-v|--verbosity]
dotnet clean [-h|--help]
```
---

## <a name="description"></a>Descripción

El comando `dotnet clean` limpia la salida de la compilación anterior. Se implementa como un [destino MSBuild](/visualstudio/msbuild/msbuild-targets), por lo que el proyecto se evalúa cuando se ejecuta el comando. Solo se limpian las salidas que se crearon durante la compilación. Se limpian las carpetas intermedias (*obj*) y de la salida final (*bin*).

## <a name="arguments"></a>Argumentos

`PROJECT`

El proyecto de MSBuild para limpiar. Si no se especifica un archivo de proyecto, MSBuild busca en el directorio de trabajo actual un archivo que tenga una extensión de archivo que termine en *proj* y usa ese archivo.

## <a name="options"></a>Opciones

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

`-c|--configuration {Debug|Release}`

Define la configuración de compilación. El valor predeterminado es `Debug`. Esta opción solo es necesaria al realizar la limpieza si la especificó durante el tiempo de compilación.

`-f|--framework <FRAMEWORK>`

El [marco](../../standard/frameworks.md) que se especificó en tiempo de compilación. El marco se debe definir en el [archivo de proyecto](csproj.md). Si especificó el marco en tiempo de compilación, debe especificar el marco al realizar la limpieza.

`-h|--help`

Imprime una corta ayuda para el comando.

`-o|--output <OUTPUT_DIRECTORY>`

Directorio en el que se colocan las salidas de compilación. Especifique el modificador `-f|--framework <FRAMEWORK>` con el modificador del directorio de salida si especificó el marco cuando se compiló el proyecto.

`-r|--runtime <RUNTIME_IDENTIFIER>`

Limpia la carpeta de salida del tiempo de ejecución especificado. Esto se usa si se ha creado una [implementación autocontenida](../deploying/index.md#self-contained-deployments-scd).

`-v|--verbosity <LEVEL>`

Establece el nivel de detalle del comando. Niveles permitidos son q[uiet], m[inimal], n[ormal], d[etailed] y diag[nostic].

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

`-c|--configuration {Debug|Release}`

Define la configuración de compilación. El valor predeterminado es `Debug`. Esta opción solo es necesaria al realizar la limpieza si la especificó durante el tiempo de compilación.

`-f|--framework <FRAMEWORK>`

El [marco](../../standard/frameworks.md) que se especificó en tiempo de compilación. El marco se debe definir en el [archivo de proyecto](csproj.md). Si especificó el marco en tiempo de compilación, debe especificar el marco al realizar la limpieza.

`-h|--help`

Imprime una corta ayuda para el comando.

`-o|--output <OUTPUT_DIRECTORY>`

Directorio en el que se colocan las salidas de compilación. Especifique el modificador `-f|--framework <FRAMEWORK>` con el modificador del directorio de salida si especificó el marco cuando se compiló el proyecto.

`-v|--verbosity <LEVEL>`

Establece el nivel de detalle del comando. Niveles permitidos son q[uiet], m[inimal], n[ormal], d[etailed] y diag[nostic].

---

## <a name="examples"></a>Ejemplos

Limpie una compilación predeterminada del proyecto:

`dotnet clean`

Limpie un proyecto creado con la configuración de lanzamiento:

`dotnet clean --configuration Release`
