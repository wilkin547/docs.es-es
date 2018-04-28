---
title: 'Comando dotnet build: CLI de .NET Core'
description: El comando dotnet build compila un proyecto y todas sus dependencias.
author: mairaw
ms.author: mairaw
ms.date: 03/10/2018
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: 2c258f2906be43436b57b9795b5851af88804443
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="dotnet-build"></a>dotnet-build

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>nombre

`dotnet build`: compila un proyecto y todas sus dependencias.

## <a name="synopsis"></a>Sinopsis

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)
```
dotnet build [<PROJECT>] [-c|--configuration] [-f|--framework] [--force] [--no-dependencies] [--no-incremental]
    [--no-restore] [-o|--output] [-r|--runtime] [-v|--verbosity] [--version-suffix]
dotnet build [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)
```
dotnet build [<PROJECT>] [-c|--configuration] [-f|--framework] [--no-dependencies] [--no-incremental] [-o|--output]
    [-r|--runtime] [-v|--verbosity] [--version-suffix]
dotnet build [-h|--help]
```
---

## <a name="description"></a>Description

El comando `dotnet build` crea el proyecto y sus dependencias en un conjunto de archivos binarios. Los archivos binarios incluyen el código del proyecto en archivos de lenguaje intermedio (IL) con una extensión *.dll* y los archivos de símbolos usados para la depuración con una extensión *.pdb*. Se genera un archivo JSON de dependencias (*\*. deps.json*) que incluye las dependencias de la aplicación. Se genera un archivo *\*.runtimeconfig.json*, que especifica el tiempo de ejecución compartido y su versión de la aplicación.

Si el proyecto tiene dependencias de terceros, como bibliotecas de NuGet, estas se resuelven desde la caché de NuGet y no están disponibles en la salida compilada del proyecto. Teniendo eso en cuenta, el producto de `dotnet build` no está listo para transferirse a otra máquina para ejecutarse. Esto contrasta con el comportamiento de .NET Framework en el que al compilar un proyecto ejecutable (una aplicación) se genera ese ejecutable en cualquier máquina donde esté instalado .NET. Para tener una experiencia similar con .NET Core, es necesario usar el comando [dotnet publish](dotnet-publish.md). Para obtener más información, consulte el tema [Implementación de aplicaciones .NET Core](../deploying/index.md).

La compilación requiere el archivo *project.assets.json*, que muestra las dependencias de la aplicación. El archivo se crea cuando se ejecuta [`dotnet restore`](dotnet-restore.md). Sin el archivo de recursos, las herramientas no pueden resolver los ensamblados de referencia, lo que dará lugar a errores. Con el SDK de .NET Core 1.x, era necesario ejecutar de forma explícita `dotnet restore` antes de ejecutar `dotnet build`. A partir del SDK de .NET Core 2.0, `dotnet restore` se ejecuta implícitamente al ejecutar `dotnet build`. Si quiere deshabilitar la restauración implícita cuando se ejecuta el comando de compilación, puede usar la opción `--no-restore`.

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

`dotnet build` usa MSBuild para compilar el proyecto; por lo tanto, admite las compilaciones en paralelo e incrementales. Para más información, consulte [Compilaciones incrementales](/visualstudio/msbuild/incremental-builds).

Además de sus opciones, el comando `dotnet build` acepta opciones de MSBuild, como `/p` para establecer propiedades o `/l` para definir un registrador. Aprenda más sobre de estas opciones en la [referencia de línea de comandos de MSBuild](/visualstudio/msbuild/msbuild-command-line-reference). 

Si el proyecto es ejecutable o no viene determinado por la propiedad `<OutputType>` en el archivo del proyecto. En el siguiente ejemplo se muestra un proyecto que generará un código ejecutable:

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

Para generar una biblioteca, omita la propiedad `<OutputType>`. La principal diferencia en la salida compilada es que la DLL de IL para una biblioteca no contiene puntos de entrada y no se puede ejecutar. 

## <a name="arguments"></a>Argumentos

`PROJECT`

El archivo del proyecto que se va a compilar. Si no se especifica un archivo de proyecto, MSBuild busca en el directorio de trabajo actual un archivo que tenga una extensión de archivo que termine en *proj* y usa ese archivo.

## <a name="options"></a>Opciones

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

`-c|--configuration {Debug|Release}`

Define la configuración de compilación. El valor predeterminado es `Debug`.

`-f|--framework <FRAMEWORK>`

Compila para un [marco de trabajo](../../standard/frameworks.md) específico. El marco se debe definir en el [archivo de proyecto](csproj.md).

`--force`

 Fuerza la resolución de todas las dependencias, incluso si la última restauración se realizó correctamente. Esto es equivalente a eliminar el archivo *project.assets.json*.

`-h|--help`

Imprime una corta ayuda para el comando.

`--no-dependencies`

Omite las referencias de proyecto a proyecto (P2P) y solo compila el proyecto raíz especificado para compilar.

`--no-incremental`

Marca la compilación como no segura para la compilación incremental. Esto desactiva la compilación incremental y fuerza una recompilación limpia del gráfico de dependencias del proyecto.

`--no-restore`

No se realiza una restauración implícita durante la compilación.

`-o|--output <OUTPUT_DIRECTORY>`

Directorio donde se colocan los archivos binarios compilados. También debe definir `--framework` cuando se especifica esta opción.

`-r|--runtime <RUNTIME_IDENTIFIER>`

Especifica el tiempo de ejecución de destino. Para obtener una lista de identificadores de tiempo de ejecución (RID), consulte el [catálogo de RID](../rid-catalog.md).

`-v|--verbosity <LEVEL>`

Establece el nivel de detalle del comando. Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.

`--version-suffix <VERSION_SUFFIX>`

Define el sufijo de la versión de un asterisco (`*`) en el campo de versión del archivo del proyecto. El formato sigue las instrucciones de versión de NuGet.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

`-c|--configuration {Debug|Release}`

Define la configuración de compilación. El valor predeterminado es `Debug`.

`-f|--framework <FRAMEWORK>`

Compila para un [marco de trabajo](../../standard/frameworks.md) específico. El marco se debe definir en el [archivo de proyecto](csproj.md).

`-h|--help`

Imprime una corta ayuda para el comando.

`--no-dependencies`

Omite las referencias de proyecto a proyecto (P2P) y solo compila el proyecto raíz especificado para compilar.

`--no-incremental`

Marca la compilación como no segura para la compilación incremental. Esto desactiva la compilación incremental y fuerza una recompilación limpia del gráfico de dependencias del proyecto.

`-o|--output <OUTPUT_DIRECTORY>`

Directorio donde se colocan los archivos binarios compilados. También debe definir `--framework` cuando se especifica esta opción.

`-r|--runtime <RUNTIME_IDENTIFIER>`

Especifica el tiempo de ejecución de destino. Para obtener una lista de identificadores de tiempo de ejecución (RID), consulte el [catálogo de RID](../rid-catalog.md).

`-v|--verbosity <LEVEL>`

Establece el nivel de detalle del comando. Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.

`--version-suffix <VERSION_SUFFIX>`

Define el sufijo de la versión de un asterisco (`*`) en el campo de versión del archivo del proyecto. El formato sigue las instrucciones de versión de NuGet.

---

## <a name="examples"></a>Ejemplos

Creación de un proyecto y sus dependencias:

`dotnet build`

Creación de un proyecto y sus dependencias mediante la configuración de lanzamiento:

`dotnet build --configuration Release`

Compilación de un proyecto y sus dependencias para un tiempo de ejecución específico (en este ejemplo, Ubuntu 16.04):

`dotnet build --runtime ubuntu.16.04-x64`

Compile el proyecto y use origen del paquete NuGet especificado durante la operación de restauración (SDK de .NET Core 2.0 y versiones posteriores):

`dotnet build --source c:\packages\mypackages`