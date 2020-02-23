---
title: Comando dotnet publish
description: El comando dotnet publish publica el proyecto de .NET Core en un directorio.
ms.date: 05/29/2018
ms.openlocfilehash: 0653a7b1e1abd6d7ffd3d21a0410279235b43a28
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77451297"
---
# <a name="dotnet-publish"></a>dotnet publish

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>NOMBRE

`dotnet publish`: empaqueta la aplicación y sus dependencias en una carpeta para su implementación en un sistema de hospedaje.

## <a name="synopsis"></a>Sinopsis

<!-- markdownlint-disable MD025 -->

# <a name="net-core-21"></a>[.NET Core 2.1](#tab/netcore21)

```dotnetcli
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [--force] [--manifest] [--no-build] [--no-dependencies]
    [--no-restore] [-o|--output] [-r|--runtime] [--self-contained] [-v|--verbosity] [--version-suffix]
dotnet publish [-h|--help]
```

# <a name="net-core-20"></a>[.NET Core 2.0](#tab/netcore20)

```dotnetcli
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [--force] [--manifest] [--no-dependencies]
    [--no-restore] [-o|--output] [-r|--runtime] [--self-contained] [-v|--verbosity] [--version-suffix]
dotnet publish [-h|--help]
```

# <a name="net-core-1x"></a>[.NET Core 1.x](#tab/netcore1x)

```dotnetcli
dotnet publish [<PROJECT>] [-c|--configuration] [-f|--framework] [-o|--output] [-r|--runtime] [-v|--verbosity]
    [--version-suffix]
dotnet publish [-h|--help]
```

---

## <a name="description"></a>Descripción

`dotnet publish`: compila la aplicación, lee sus dependencias especificadas en el archivo de proyecto y publica el conjunto resultante de archivos en un directorio. La salida incluye los recursos siguientes:

- Código de lenguaje intermedio (IL) en un ensamblado con una extensión *dll*.
- Archivo *.deps.json* que incluye todas las dependencias del proyecto.
- Archivo *.runtime.config.json* en el que se especifica el entorno de tiempo de ejecución compartido que espera la aplicación, así como otras opciones de configuración para el tiempo de ejecución (por ejemplo, el tipo de recolección de elementos no utilizados).
- Las dependencias de la aplicación, que se copian de la caché de NuGet a la carpeta de salida.

La salida del comando `dotnet publish` está lista para la implementación en un sistema de hospedaje (por ejemplo, un servidor, un equipo PC o Mac, un portátil) para la ejecución. Es la única manera admitida oficialmente para preparar la aplicación para la implementación. Dependiendo del tipo de implementación que especifique el proyecto, el sistema de hospedaje puede o no tener instalado el entorno de tiempo de ejecución compartido de .NET Core. Para obtener más información, consulte el tema [Implementación de aplicaciones .NET Core](../deploying/index.md). Para la estructura de directorios de una aplicación publicada, consulte [Directory structure](/aspnet/core/hosting/directory-structure) (Estructura de directorios).

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="arguments"></a>Argumentos

`PROJECT`

El proyecto que se va a publicar. Es la ruta de acceso y el nombre de archivo de un archivo de proyecto [C#](csproj.md), F# o Visual Basic, o la ruta de acceso a un directorio que contiene un archivo de proyecto C#, F# o Visual Basic. Si no se especifica, se toma como predeterminado el directorio actual.

## <a name="options"></a>Opciones

# <a name="net-core-21"></a>[.NET Core 2.1](#tab/netcore21)

`-c|--configuration {Debug|Release}`

Define la configuración de compilación. El valor predeterminado es `Debug`.

`-f|--framework <FRAMEWORK>`

Publica la aplicación para el [marco de trabajo de destino especificado](../../standard/frameworks.md). Debe especificar el marco de trabajo de destino en el archivo de proyecto.

`--force`

Fuerza la resolución de todas las dependencias, incluso si la última restauración se realizó correctamente. Especificar esta marca es lo mismo que eliminar el archivo *project.assets.json*.

`-h|--help`

Imprime una corta ayuda para el comando.

`--manifest <PATH_TO_MANIFEST_FILE>`

Especifica uno o varios [manifiestos de destino](../deploying/runtime-store.md) que se usarán para recortar el conjunto de paquetes publicados con la aplicación. El archivo de manifiesto es parte de la salida del [comando `dotnet store`](dotnet-store.md). Para especificar varios manifiestos, agregue la opción `--manifest` para cada manifiesto. Esta opción está disponible a partir del SDK de .NET Core 2.0.

`--no-build`

No compila el proyecto antes de publicarlo. También establece la marca `--no-restore` de forma implícita.

`--no-dependencies`

Omite las referencias de proyecto a proyecto y solo restaura el proyecto raíz.

`--no-restore`

No ejecuta una restauración implícita al ejecutar el comando.

`-o|--output <OUTPUT_DIRECTORY>`

Especifica la ruta de acceso del directorio de salida. Si no se especifica, el valor predeterminado es *./bin/[configuration]/[framework]/publish/* para una implementación dependiente del marco de trabajo o *./bin/[configuration]/[framework]/[runtime]/publish/* para una implementación independiente.
Si la ruta de acceso es relativa, el directorio de salida generado es relativo a la ubicación del archivo de proyecto, no al directorio de trabajo actual.

`--self-contained`

Publica el tiempo de ejecución de .NET Core con la aplicación para que no sea necesario tener instalado el tiempo de ejecución en la máquina de destino. Si se especifica un identificador de tiempo de ejecución, su valor predeterminado es `true`. Para más información sobre los diferentes tipos de implementación, vea [Implementación de aplicaciones .NET Core](../deploying/index.md).

`-r|--runtime <RUNTIME_IDENTIFIER>`

Publica la aplicación para un determinado entorno de tiempo de ejecución. Esto se usa al crear una [implementación autocontenida (SCD)](../deploying/index.md#publish-self-contained). Para obtener una lista de identificadores de tiempo de ejecución (RID), consulte el [catálogo de RID](../rid-catalog.md). El valor predeterminado es publicar una [aplicación dependiente del marco de trabajo (FDD)](../deploying/index.md#publish-runtime-dependent).

`-v|--verbosity <LEVEL>`

Establece el nivel de detalle del comando. Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.

`--version-suffix <VERSION_SUFFIX>`

Define el sufijo de versión para reemplazar el asterisco (`*`) en el campo de versión del archivo de proyecto.

# <a name="net-core-20"></a>[.NET Core 2.0](#tab/netcore20)

`-c|--configuration {Debug|Release}`

Define la configuración de compilación. El valor predeterminado es `Debug`.

`-f|--framework <FRAMEWORK>`

Publica la aplicación para el [marco de trabajo de destino especificado](../../standard/frameworks.md). Debe especificar el marco de trabajo de destino en el archivo de proyecto.

`--force`

Fuerza la resolución de todas las dependencias, incluso si la última restauración se realizó correctamente. Especificar esta marca es lo mismo que eliminar el archivo *project.assets.json*.

`-h|--help`

Imprime una corta ayuda para el comando.

`--manifest <PATH_TO_MANIFEST_FILE>`

Especifica uno o varios [manifiestos de destino](../deploying/runtime-store.md) que se usarán para recortar el conjunto de paquetes publicados con la aplicación. El archivo de manifiesto es parte de la salida del [comando `dotnet store`](dotnet-store.md). Para especificar varios manifiestos, agregue la opción `--manifest` para cada manifiesto. Esta opción está disponible a partir del SDK de .NET Core 2.0.

`--no-dependencies`

Omite las referencias de proyecto a proyecto y solo restaura el proyecto raíz.

`--no-restore`

No ejecuta una restauración implícita al ejecutar el comando.

`-o|--output <OUTPUT_DIRECTORY>`

Especifica la ruta de acceso del directorio de salida. Si no se especifica, el valor predeterminado es *./bin/[configuration]/[framework]/publish/* para una implementación dependiente del marco de trabajo o *./bin/[configuration]/[framework]/[runtime]/publish/* para una implementación independiente.
Si la ruta de acceso es relativa, el directorio de salida generado es relativo a la ubicación del archivo de proyecto, no al directorio de trabajo actual.

`--self-contained`

Publica el tiempo de ejecución de .NET Core con la aplicación para que no sea necesario tener instalado el tiempo de ejecución en la máquina de destino. Si se especifica un identificador de tiempo de ejecución, su valor predeterminado es `true`. Para más información sobre los diferentes tipos de implementación, vea [Implementación de aplicaciones .NET Core](../deploying/index.md).

`-r|--runtime <RUNTIME_IDENTIFIER>`

Publica la aplicación para un determinado entorno de tiempo de ejecución. Esto se usa al crear una [implementación autocontenida (SCD)](../deploying/index.md#publish-self-contained). Para obtener una lista de identificadores de tiempo de ejecución (RID), consulte el [catálogo de RID](../rid-catalog.md). El valor predeterminado es publicar una [aplicación dependiente del marco de trabajo (FDD)](../deploying/index.md#publish-runtime-dependent).

`-v|--verbosity <LEVEL>`

Establece el nivel de detalle del comando. Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.

`--version-suffix <VERSION_SUFFIX>`

Define el sufijo de versión para reemplazar el asterisco (`*`) en el campo de versión del archivo de proyecto.

# <a name="net-core-1x"></a>[.NET Core 1.x](#tab/netcore1x)

`-c|--configuration {Debug|Release}`

Define la configuración de compilación. El valor predeterminado es `Debug`.

`-f|--framework <FRAMEWORK>`

Publica la aplicación para el [marco de trabajo de destino especificado](../../standard/frameworks.md). Debe especificar el marco de trabajo de destino en el archivo de proyecto.

`-h|--help`

Imprime una corta ayuda para el comando.

`--manifest <PATH_TO_MANIFEST_FILE>`

Especifica uno o varios [manifiestos de destino](../deploying/runtime-store.md) que se usarán para recortar el conjunto de paquetes publicados con la aplicación. El archivo de manifiesto es parte de la salida del [comando `dotnet store`](dotnet-store.md). Para especificar varios manifiestos, agregue la opción `--manifest` para cada manifiesto. Esta opción está disponible a partir del SDK de .NET Core 2.0.

`-o|--output <OUTPUT_DIRECTORY>`

Especifica la ruta de acceso del directorio de salida. Si no se especifica, el valor predeterminado es *./bin/[configuration]/[framework]/publish/* para una implementación dependiente del marco de trabajo o *./bin/[configuration]/[framework]/[runtime]/publish/* para una implementación independiente.
Si la ruta de acceso es relativa, el directorio de salida generado es relativo a la ubicación del archivo de proyecto, no al directorio de trabajo actual.

`-r|--runtime <RUNTIME_IDENTIFIER>`

Publica la aplicación para un determinado entorno de tiempo de ejecución. Esto se usa al crear una [implementación autocontenida (SCD)](../deploying/index.md#publish-self-contained). Para obtener una lista de identificadores de tiempo de ejecución (RID), consulte el [catálogo de RID](../rid-catalog.md). El valor predeterminado es publicar una [aplicación dependiente del marco de trabajo (FDD)](../deploying/index.md#publish-runtime-dependent).

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

Publica la aplicación actual pero no restaura las referencias de proyecto a proyecto (P2P), solo el proyecto raíz, durante la operación de restauración (SDK de .NET Core 2.0 y versiones superiores):

`dotnet publish --no-dependencies`

## <a name="see-also"></a>Vea también

- [Marcos de trabajo de destino](../../standard/frameworks.md)
- [Catálogo de identificadores de tiempo de ejecución (RID)](../rid-catalog.md)
