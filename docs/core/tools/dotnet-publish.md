---
title: 'Comando dotnet publish: CLI de .NET Core'
description: El comando dotnet publish publica el proyecto de .NET Core en un directorio.
keywords: dotnet-publish, CLI, comando de la CLI, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 08/12/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: f2ef275a-7c5e-430a-8c30-65f52af62771
ms.translationtype: HT
ms.sourcegitcommit: a19ab54a6cc44bd7acd1e40a4ca94da52bf14297
ms.openlocfilehash: db6e527a6132be0b6362c68945bb68884f5ad619
ms.contentlocale: es-es
ms.lasthandoff: 08/14/2017

---
# <a name="dotnet-publish"></a>dotnet publish

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>Nombre

`dotnet publish`: empaqueta la aplicación y sus dependencias en una carpeta para su implementación en un sistema de hospedaje.

## <a name="synopsis"></a>Sinopsis

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

```
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [--force] [--manifest] [no-dependencies] [--no-restore] [-o|--output] [-r|--runtime] [--self-contained] [-v|--verbosity] [--version-suffix]
dotnet publish [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

```
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [-o|--output] [-r|--runtime] [-v|--verbosity] [--version-suffix]
dotnet publish [-h|--help]
```

---

## <a name="description"></a>Descripción

`dotnet publish`: compila la aplicación, lee sus dependencias especificadas en el archivo de proyecto y publica el conjunto resultante de archivos en un directorio. La salida contendrá lo siguiente:

* Código de lenguaje intermedio (IL) en un ensamblado con una extensión *dll*.
* Archivo *.deps.json* que contiene todas las dependencias del proyecto.
* Archivo *.runtime.config.json* en el que se especifica el entorno de tiempo de ejecución compartido que espera la aplicación, así como otras opciones de configuración para el tiempo de ejecución (por ejemplo, el tipo de recolección de elementos no utilizados).
* Todas las dependencias de la aplicación. Estas se copian de la caché de NuGet a la carpeta de salida.

La salida del comando `dotnet publish` está preparada para la implementación de un sistema de hospedaje (por ejemplo, un servidor, un equipo PC o Mac o un equipo portátil) para la ejecución y es la única manera admitida oficialmente de preparar la aplicación para la implementación. Dependiendo del tipo de implementación que especifique el proyecto, el sistema de hospedaje puede o no tener instalado el entorno de tiempo de ejecución compartido de .NET Core. Para más información, consulte el tema [Implementación de aplicaciones .NET Core](../deploying/index.md). Para la estructura de directorios de una aplicación publicada, consulte [Directory structure](/aspnet/core/hosting/directory-structure) (Estructura de directorios).

## <a name="arguments"></a>Argumentos

`PROJECT`

El proyecto para publicar, cuyo valor predeterminado es el directorio actual si no se especifica.

## <a name="options"></a>Opciones

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

`-c|--configuration {Debug|Release}`

Define la configuración de compilación. El valor predeterminado es `Debug`.

`-f|--framework <FRAMEWORK>`

Publica la aplicación para el [marco de trabajo de destino especificado](../../standard/frameworks.md). Debe especificar el marco de trabajo de destino en el archivo de proyecto.

`--force`

Fuerza la resolución de todas las dependencias, incluso si la última restauración se realizó correctamente. Esto es equivalente a eliminar el archivo *project.assets.json*.

`-h|--help`

Imprime una corta ayuda para el comando.

`--manifest <PATH_TO_MANIFEST_FILE>`

Especifica uno o varios [manifiestos de destino](../deploying/runtime-store.md) que se usarán para recortar el conjunto de paquetes publicados con la aplicación. El archivo de manifiesto es parte de la salida del [comando `dotnet store`](dotnet-store.md). Para especificar varios manifiestos, agregue la opción `--manifest` para cada manifiesto. Esta opción está disponible a partir del SDK de .NET Core 2.0.

`--no-dependencies`

Omite las referencias de proyecto a proyecto y solo restaura el proyecto raíz.

`--no-restore`

No realiza una restauración implícita al ejecutar el comando.

`-o|--output <OUTPUT_DIRECTORY>`

Especifica la ruta de acceso del directorio de salida. Si no se especifica, el valor predeterminado es *./bin/[configuration]/[framework]/* para una implementación dependiente del marco de trabajo o *./bin/[configuration]/[framework]/[runtime]* para una implementación independiente.

`--self-contained`

Publica el tiempo de ejecución de .NET Core con la aplicación para que no sea necesario tener instalado el tiempo de ejecución en la máquina de destino. Si se especifica un identificador de tiempo de ejecución, su valor predeterminado es `true`. Para obtener más información sobre los diferentes tipos de implementación, consulte [Implementación de aplicaciones .NET Core](../deploying/index.md).

`-r|--runtime <RUNTIME_IDENTIFIER>`

Publica la aplicación para un determinado entorno de tiempo de ejecución. Esto se usa al crear una [implementación autocontenida (SCD)](../deploying/index.md#self-contained-deployments-scd). Para obtener una lista de identificadores de tiempo de ejecución (RID), consulte el [catálogo de RID](../rid-catalog.md). El valor predeterminado es publicar una [aplicación dependiente del marco de trabajo (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).

`-v|--verbosity <LEVEL>`

Establece el nivel de detalle del comando. Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.

`--version-suffix <VERSION_SUFFIX>`

Define el sufijo de versión para reemplazar el asterisco (`*`) en el campo de versión del archivo de proyecto.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

`-c|--configuration {Debug|Release}`

Define la configuración de compilación. El valor predeterminado es `Debug`.

`-f|--framework <FRAMEWORK>`

Publica la aplicación para el [marco de trabajo de destino especificado](../../standard/frameworks.md). Debe especificar el marco de trabajo de destino en el archivo de proyecto.

`-h|--help`

Imprime una corta ayuda para el comando.

`--manifest <PATH_TO_MANIFEST_FILE>`

Especifica uno o varios [manifiestos de destino](../deploying/runtime-store.md) que se usarán para recortar el conjunto de paquetes publicados con la aplicación. El archivo de manifiesto es parte de la salida del [comando `dotnet store`](dotnet-store.md). Para especificar varios manifiestos, agregue la opción `--manifest` para cada manifiesto. Esta opción está disponible a partir del SDK de .NET Core 2.0.

`-o|--output <OUTPUT_DIRECTORY>`

Especifica la ruta de acceso del directorio de salida. Si no se especifica, el valor predeterminado es *./bin/[configuration]/[framework]/* para una implementación dependiente del marco de trabajo o *./bin/[configuration]/[framework]/[runtime]* para una implementación independiente.

`-r|--runtime <RUNTIME_IDENTIFIER>`

Publica la aplicación para un determinado entorno de tiempo de ejecución. Esto se usa al crear una [implementación autocontenida (SCD)](../deploying/index.md#self-contained-deployments-scd). Para obtener una lista de identificadores de tiempo de ejecución (RID), consulte el [catálogo de RID](../rid-catalog.md). El valor predeterminado es publicar una [aplicación dependiente del marco de trabajo (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).

`-v|--verbosity <LEVEL>`

Establece el nivel de detalle del comando. Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.

`--version-suffix <VERSION_SUFFIX>`

Define el sufijo de versión para reemplazar el asterisco (`*`) en el campo de versión del archivo de proyecto.

---

## <a name="examples"></a>Ejemplos

Publica el proyecto en el directorio actual:

`dotnet publish`

Publicar la aplicación con el archivo del proyecto especificado:

`dotnet publish ~/projects/app1/app1.csproj`
    
Publica el proyecto en el directorio actual mediante el marco de trabajo `netcoreapp1.1`:

`dotnet publish --framework netcoreapp1.1`
    
Publica la aplicación actual mediante el marco de trabajo `netcoreapp1.1` y el entorno de tiempo de ejecución para `OS X 10.10` (este RID tiene que existir en el archivo de proyecto):

`dotnet publish --framework netcoreapp1.1 --runtime osx.10.11-x64`

## <a name="see-also"></a>Vea también

* [Marcos de trabajo de destino](../../standard/frameworks.md)
* [Catálogo de identificadores de tiempo de ejecución (RID)](../rid-catalog.md)

