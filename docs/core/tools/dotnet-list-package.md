---
title: Comando dotnet list package
description: El comando "dotnet list package" ofrece una opción práctica para mostrar las referencias de paquete de un proyecto o una solución.
ms.date: 11/11/2020
ms.openlocfilehash: b51ef5deb8b6418938787003b409803a3c814b08
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104873437"
---
# <a name="dotnet-list-package"></a>dotnet list package

**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.2 y versiones posteriores

## <a name="name"></a>NOMBRE

`dotnet list package`: muestra las referencias de paquete de un proyecto o una solución.

## <a name="synopsis"></a>Sinopsis

```dotnetcli
dotnet list [<PROJECT>|<SOLUTION>] package [--config <SOURCE>]
    [--deprecated]
    [--framework <FRAMEWORK>] [--highest-minor] [--highest-patch]
    [--include-prerelease] [--include-transitive] [--interactive]
    [--outdated] [--source <SOURCE>] [-v|--verbosity <LEVEL>]

dotnet list package -h|--help
```

## <a name="description"></a>Descripción

El comando `dotnet list package` ofrece una opción práctica para mostrar todas las referencias de paquete de NuGet de una solución o un proyecto específico. Primero deberá crear el proyecto para tener los recursos necesarios para que este comando se procese. En el ejemplo siguiente se muestra la salida del comando `dotnet list package` para el proyecto [SentimentAnalysis](https://github.com/dotnet/samples/tree/main/machine-learning/tutorials/SentimentAnalysis):

```output
Project 'SentimentAnalysis' has the following package references
   [netcoreapp2.1]:
   Top-level Package               Requested   Resolved
   > Microsoft.ML                  1.4.0       1.4.0
   > Microsoft.NETCore.App   (A)   [2.1.0, )   2.1.0

(A) : Auto-referenced package.
```

La columna **Requested** hace referencia a la versión de paquete especificada en el archivo del proyecto y puede ser un intervalo. La columna **Resolved** muestra la versión que el proyecto usa actualmente y siempre se trata de un valor único. Los paquetes que tienen `(A)` junto al nombre representan referencias implícitas de paquete que se deducen de la configuración del proyecto (tipo `Sdk`, propiedad `<TargetFramework>` o `<TargetFrameworks>`, etc.).

Use la opción `--outdated` para averiguar si hay disponibles más recientes de los paquetes que usa en los proyectos. De manera predeterminada, `--outdated` muestra los paquetes estables más recientes, a menos que la versión resuelta también sea una versión preliminar. Para incluir versiones preliminares cuando se muestren versiones más recientes, especifique también la opción `--include-prerelease`. En los ejemplos siguientes se muestra la salida del comando `dotnet list package --outdated --include-prerelease` para el mismo proyecto, tal como en el ejemplo anterior:

```output
The following sources were used:
   https://api.nuget.org/v3/index.json
   C:\Program Files (x86)\Microsoft SDKs\NuGetPackages\

Project `SentimentAnalysis` has the following updates to its packages
   [netcoreapp2.1]:
   Top-level Package      Requested   Resolved   Latest
   > Microsoft.ML         1.4.0       1.4.0      1.5.0-preview
```

Si tiene que averiguar si el proyecto tiene dependencias transitivas, use la opción `--include-transitive`. Las dependencias transitivas se producen cuando se agrega un paquete al proyecto que, a su vez, se basa en otro paquete. En el ejemplo siguiente se muestra la salida de la ejecución del comando `dotnet list package --include-transitive` en el proyecto [HelloPlugin](https://github.com/dotnet/samples/tree/main/core/extensions/AppWithPlugin/HelloPlugin), que muestra paquetes de nivel superior y los paquetes de los que dependen:

```output
Project 'HelloPlugin' has the following package references
   [netcoreapp3.0]:
   Transitive Package      Resolved
   > PluginBase            1.0.0
```

## <a name="arguments"></a>Argumentos

`PROJECT | SOLUTION`

El archivo de proyecto o solución donde se operará. Si no se especifica, el comando busca uno en el directorio actual. Si se encuentra más de una solución o proyecto, se genera un error.

## <a name="options"></a>Opciones

- **`--config <SOURCE>`**

  Los orígenes de NuGet que se usarán al buscar paquetes más recientes. Requiere la opción `--outdated`.

- **`--deprecated`**

  Muestra los paquetes que han quedado en desuso.

- **`--framework <FRAMEWORK>`**

  Muestra solo los paquetes aplicables al [marco de destino](../../standard/frameworks.md) especificado. Para especificar varios marcos, repita la opción varias veces. Por ejemplo: `--framework netcoreapp2.2 --framework netstandard2.0`.

- **`-h|--help`**

  Imprime una corta ayuda para el comando.

- **`--highest-minor`**

  Considere solo los paquetes con un número de versión principal coincidente al buscar paquetes más recientes. Requiere la opción `--outdated` o `--deprecated`.

- **`--highest-patch`**

  Considere solo los paquetes con número de versión principal y secundario coincidente al buscar paquetes más recientes. Requiere la opción `--outdated` o `--deprecated`.

- **`--include-prerelease`**

  Considere los paquetes con versiones preliminares al buscar paquetes más recientes. Requiere la opción `--outdated` o `--deprecated`.

- **`--include-transitive`**

  Enumera los paquetes transitivos, además de los paquetes de nivel superior. Al especificar esta opción, recibe una lista de paquetes de los que dependen los paquetes de nivel superior.

- **`--interactive`**

  Permite que el comando se detenga y espere una entrada o una acción del usuario. Por ejemplo, para completar la autenticación. Disponible desde el SDK de .NET Core 3.0.

- **`--outdated`**

  Enumera los paquetes con versiones más recientes disponibles.

- **`-s|--source <SOURCE>`**

  Los orígenes de NuGet que se usarán al buscar paquetes más recientes. Requiere la opción `--outdated` o `--deprecated`.

- **`-v|--verbosity <LEVEL>`**

  Establece el nivel de detalle de MSBuild. Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`. De manera predeterminada, es `minimal`.

## <a name="examples"></a>Ejemplos

- Muestre las referencias de paquete de un proyecto específico:

  ```dotnetcli
  dotnet list SentimentAnalysis.csproj package
  ```

- Muestre las referencias de paquete que tienen versiones más recientes disponibles, incluidas versiones preliminares:

  ```dotnetcli
  dotnet list package --outdated --include-prerelease
  ```

- Muestre las referencias de paquete para un marco de destino específico:

  ```dotnetcli
  dotnet list package --framework netcoreapp3.0
  ```
