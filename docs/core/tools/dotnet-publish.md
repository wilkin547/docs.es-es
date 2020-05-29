---
title: Comando dotnet publish
description: El comando dotnet publish publica el proyecto o la solución de .NET Core en un directorio.
ms.date: 02/24/2020
ms.openlocfilehash: 697746291a8b34a856433049fe7264ad0ea4af7a
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83761907"
---
# <a name="dotnet-publish"></a>dotnet publish

**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.1 y versiones posteriores

## <a name="name"></a>NOMBRE

`dotnet publish`: publica la aplicación y sus dependencias en una carpeta para la implementación en un sistema de hospedaje.

## <a name="synopsis"></a>Sinopsis

```dotnetcli
dotnet publish [<PROJECT>|<SOLUTION>] [-c|--configuration <CONFIGURATION>]
    [-f|--framework <FRAMEWORK>] [--force] [--interactive]
    [--manifest <PATH_TO_MANIFEST_FILE>] [--no-build] [--no-dependencies]
    [--no-restore] [--nologo] [-o|--output <OUTPUT_DIRECTORY>]
    [-p:PublishReadyToRun=true] [-p:PublishSingleFile=true] [-p:PublishTrimmed=true]
    [-r|--runtime <RUNTIME_IDENTIFIER>] [--self-contained [true|false]]
    [--no-self-contained] [-v|--verbosity <LEVEL>]
    [--version-suffix <VERSION_SUFFIX>]

dotnet publish -h|--help
```

## <a name="description"></a>Descripción

`dotnet publish`: compila la aplicación, lee sus dependencias especificadas en el archivo de proyecto y publica el conjunto resultante de archivos en un directorio. La salida incluye los recursos siguientes:

- Código de lenguaje intermedio (IL) en un ensamblado con una extensión *dll*.
- Un archivo *.deps.json* que incluye todas las dependencias del proyecto.
- Un archivo *.runtime.config.json* en el que se especifica el tiempo de ejecución compartido que espera la aplicación, así como otras opciones de configuración para el tiempo de ejecución (por ejemplo, el tipo de recolección de elementos no utilizados).
- Las dependencias de la aplicación, que se copian de la caché de NuGet a la carpeta de salida.

La salida del comando `dotnet publish` está lista para la implementación en un sistema de hospedaje (por ejemplo, un servidor, un equipo PC o Mac, un portátil) para la ejecución. Es la única manera admitida oficialmente para preparar la aplicación para la implementación. Dependiendo del tipo de implementación que especifique el proyecto, el sistema de hospedaje puede o no tener instalado el entorno de tiempo de ejecución compartido de .NET Core. Para obtener más información, vea [Publicación de aplicaciones .NET Core con la CLI de .NET Core](../deploying/deploy-with-cli.md).

### <a name="implicit-restore"></a>Restauración implícita

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

### <a name="msbuild"></a>MSBuild

Con el comando `dotnet publish` se llama a MSBuild, lo que invoca el destino `Publish`. Todos los parámetros pasados a `dotnet publish` se pasan a MSBuild. Los parámetros `-c` y `-o` se asignan respectivamente a las propiedades `Configuration` y `OutputPath` de MSBuild.

El comando `dotnet publish` acepta opciones de MSBuild, como `-p` para establecer propiedades y `-l` para definir un registrador. Por ejemplo, se puede establecer una propiedad de MSBuild mediante el uso del formato: `-p:<NAME>=<VALUE>`. También se pueden establecer las propiedades relacionadas con la publicación si se hace referencia a un archivo *.pubxml*, por ejemplo:

```dotnetcli
dotnet publish -p:PublishProfile=Properties\PublishProfiles\FolderProfile.pubxml
```

Para obtener más información, vea los siguientes recursos:

- [Referencia de la línea de comandos de MSBuild](/visualstudio/msbuild/msbuild-command-line-reference)
- [Perfiles de publicación (.pubxml) de Visual Studio para la implementación de aplicaciones ASP.NET Core](/aspnet/core/host-and-deploy/visual-studio-publish-profiles)
- [dotnet msbuild](dotnet-msbuild.md)

## <a name="arguments"></a>Argumentos

- **`PROJECT|SOLUTION`**

  El archivo de proyecto o solución que se va a publicar.
  
  * `PROJECT` es la ruta de acceso y el nombre de archivo de un archivo de proyecto de [C#](csproj.md), F# o Visual Basic, o bien la ruta de acceso a un directorio que contiene un archivo de proyecto de C#, F# o Visual Basic. Si no se especifica el directorio, se toma como predeterminado el actual.

  * `SOLUTION` es la ruta de acceso y el nombre de archivo de un archivo de solución (extensión *.sln*), o bien la ruta de acceso a un directorio que contiene un archivo de solución. Si no se especifica el directorio, se toma como predeterminado el actual. Disponible desde el SDK de .NET Core 3.0.

## <a name="options"></a>Opciones

- **`-c|--configuration <CONFIGURATION>`**

  Define la configuración de compilación. El valor predeterminado para la mayoría de los proyectos es `Debug`, pero puede invalidar los valores de configuración de compilación en el proyecto.

- **`-f|--framework <FRAMEWORK>`**

  Publica la aplicación para el [marco de trabajo de destino especificado](../../standard/frameworks.md). Debe especificar el marco de trabajo de destino en el archivo de proyecto.

- **`--force`**

  Fuerza la resolución de todas las dependencias, incluso si la última restauración se realizó correctamente. Especificar esta marca es lo mismo que eliminar el archivo *project.assets.json*.

- **`-h|--help`**

  Imprime una corta ayuda para el comando.

- **`--interactive`**

  Permite que el comando se detenga y espere una entrada o una acción del usuario. Por ejemplo, para completar la autenticación. Disponible desde el SDK de .NET Core 3.0.

- **`--manifest <PATH_TO_MANIFEST_FILE>`**

  Especifica uno o varios [manifiestos de destino](../deploying/runtime-store.md) que se usarán para recortar el conjunto de paquetes publicados con la aplicación. El archivo de manifiesto es parte de la salida del [comando `dotnet store`](dotnet-store.md). Para especificar varios manifiestos, agregue la opción `--manifest` para cada manifiesto.

- **`--no-build`**

  No compila el proyecto antes de publicarlo. También establece la marca `--no-restore` de forma implícita.

- **`--no-dependencies`**

  Omite las referencias de proyecto a proyecto y solo restaura el proyecto raíz.

- **`--nologo`**

  No se muestra la pancarta de inicio ni el mensaje de copyright. Disponible desde el SDK de .NET Core 3.0.

- **`--no-restore`**

  No ejecuta una restauración implícita al ejecutar el comando.

- **`-o|--output <OUTPUT_DIRECTORY>`**

  Especifica la ruta de acceso del directorio de salida.
  
  Si no se especifica, el valor predeterminado es *[project_file_folder]./bin/[configuration]/[framework]/publish/* para un archivo ejecutable dependiente del tiempo de ejecución y archivos binarios multiplataforma. El valor predeterminado es *[project_file_folder]/bin/[configuration]/[framework]/[runtime]/publish/* para un archivo ejecutable autocontenido.

  En un proyecto web, si la carpeta de salida se encuentra en la carpeta del proyecto, los comandos `dotnet publish` posteriores dan como resultado carpetas de salida anidadas. Por ejemplo, si la carpeta del proyecto es *myproject* y la carpeta de salida de la publicación es *myproject/publish*, y ejecuta `dotnet publish` dos veces, la segunda ejecución coloca los archivos de contenido, como *.config* y *.json*, en *myproject/publish/publish*. Para evitar el anidamiento de carpetas de publicación, especifique una que no esté **directamente** en la carpeta del proyecto, o bien excluya la carpeta de publicación del proyecto. Para excluir una carpeta de publicación denominada *publishoutput*, agregue el elemento siguiente a un elemento `PropertyGroup` en el archivo *.csproj*:

  ```xml
  <DefaultItemExcludes>$(DefaultItemExcludes);publishoutput**</DefaultItemExcludes>
  ```

  - SDK de .NET Core 3.x y versiones posteriores
  
    Si se especifica una ruta de acceso relativa al publicar un proyecto, el directorio de salida generado es relativo al directorio de trabajo actual, no a la ubicación del archivo del proyecto.

    Si se especifica una ruta de acceso relativa al publicar una solución, todas las salidas de todos los proyectos van en la carpeta especificada relativa al directorio de trabajo actual. A fin de que la salida de la publicación vaya a carpetas independientes para cada proyecto, especifique una ruta de acceso relativa mediante el uso de la propiedad `PublishDir` de MSBuild en lugar de la opción `--output`. Por ejemplo, `dotnet publish -p:PublishDir=.\publish` envía la salida de publicación de cada proyecto a una carpeta `publish` en la carpeta que contiene el archivo del proyecto.

  - SDK de .NET Core 2.x
  
    Si se especifica una ruta de acceso relativa al publicar un proyecto, el directorio de salida generado es relativo a la ubicación del archivo del proyecto, no al directorio de trabajo actual.

    Si se especifica una ruta de acceso relativa al publicar una solución, la salida de cada proyecto va a una carpeta independiente relativa a la ubicación del archivo del proyecto. Si se especifica una ruta de acceso absoluta al publicar una solución, la salida de las publicaciones de todos los proyectos van a la carpeta especificada.

- **`-p:PublishReadyToRun=true`**

  Compila los ensamblados de aplicación con el formato ReadyToRun (R2R). R2R es una forma de compilación Ahead Of Time (AOT). Para obtener más información, vea [Imágenes ReadyToRun](../whats-new/dotnet-core-3-0.md#readytorun-images). Disponible desde el SDK de .NET Core 3.0.

  Se recomienda especificar esta opción en un perfil de publicación en lugar de hacerlo en la línea de comandos. Para obtener más información, vea [MSBuild](#msbuild).

- **`-p:PublishSingleFile=true`**

  Empaqueta la aplicación en un ejecutable de archivo único específico de la plataforma. El archivo ejecutable es autoextraíble y contiene todas las dependencias (incluidas las nativas) necesarias para ejecutar la aplicación. Cuando la aplicación se ejecuta por primera vez, se extrae en un directorio que se basa en el nombre de la aplicación y el identificador de compilación. El inicio es más rápido cuando se vuelve a ejecutar la aplicación. No es necesario extraer la aplicación por segunda vez a menos que se haya usado una versión nueva. Disponible desde el SDK de .NET Core 3.0.

  Para obtener más información sobre la publicación de archivos únicos, vea el [documento de diseño del programa de instalación de conjunto de archivos únicos](https://github.com/dotnet/designs/blob/master/accepted/2020/single-file/design.md).

  Se recomienda especificar esta opción en un perfil de publicación en lugar de hacerlo en la línea de comandos. Para obtener más información, vea [MSBuild](#msbuild).

- **`-p:PublishTrimmed=true`**

  Recorta las bibliotecas no utilizadas para reducir el tamaño de implementación de una aplicación cuando se publica un ejecutable independiente. Para obtener más información, vea [Recorte de implementaciones autocontenidas y ejecutables](../deploying/trim-self-contained.md). Disponible desde el SDK de .NET Core 3.0.

  Se recomienda especificar esta opción en un perfil de publicación en lugar de hacerlo en la línea de comandos. Para obtener más información, vea [MSBuild](#msbuild).

- **`--self-contained [true|false]`**

  Publica el tiempo de ejecución de .NET Core con la aplicación para que no sea necesario tener instalado el tiempo de ejecución en la máquina de destino. El valor predeterminado es `true` si se especifica un identificador en tiempo de ejecución y el proyecto es de tipo ejecutable (no un proyecto de biblioteca). Para obtener más información, vea [Publicación de aplicaciones .NET Core](../deploying/index.md) y [Publicación de aplicaciones .NET Core con la CLI de .NET Core](../deploying/deploy-with-cli.md).

  Si se usa esta opción sin especificar `true` o `false`, el valor predeterminado es `true`. En ese caso, no coloque el argumento de la solución o el proyecto inmediatamente después de `--self-contained`, porque se espera que `true` o `false` estén en esa posición.

- **`--no-self-contained`**

  Equivalente a `--self-contained false`. Disponible desde el SDK de .NET Core 3.0.

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  Publica la aplicación para un determinado entorno de tiempo de ejecución. Para obtener una lista de identificadores de tiempo de ejecución (RID), consulte el [catálogo de RID](../rid-catalog.md). Para obtener más información, vea [Publicación de aplicaciones .NET Core](../deploying/index.md) y [Publicación de aplicaciones .NET Core con la CLI de .NET Core](../deploying/deploy-with-cli.md).

- **`-v|--verbosity <LEVEL>`**

  Establece el nivel de detalle del comando. Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`. El valor predeterminado es `minimal`.

- **`--version-suffix <VERSION_SUFFIX>`**

  Define el sufijo de versión para reemplazar el asterisco (`*`) en el campo de versión del archivo de proyecto.

## <a name="examples"></a>Ejemplos

- Cree un [archivo binario multiplataforma dependiente del tiempo de ejecución ](../deploying/index.md#produce-a-cross-platform-binary) para el proyecto en el directorio actual:

  ```dotnetcli
  dotnet publish
  ```

  A partir del SDK de .NET Core 3.0, en este ejemplo también se crea un [ ejecutable dependiente del tiempo de ejecución](../deploying/index.md#publish-runtime-dependent) para la plataforma actual.

- Cree un [ejecutable independiente](../deploying/index.md#publish-self-contained) para el proyecto en el directorio actual, para un tiempo de ejecución específico:

  ```dotnetcli
  dotnet publish --runtime osx.10.11-x64
  ```

  El RID debe estar en el archivo del proyecto.

- Cree un [ejecutable dependiente del tiempo de ejecución](../deploying/index.md#publish-runtime-dependent) para el proyecto en el directorio actual, para una plataforma específica:

  ```dotnetcli
  dotnet publish --runtime osx.10.11-x64 --self-contained false
  ```

  El RID debe estar en el archivo del proyecto. Este ejemplo se aplica al SDK de .NET Core 3.0 y versiones posteriores.

- Publique el proyecto en el directorio actual, para un tiempo de ejecución específico y una plataforma de destino:

  ```dotnetcli
  dotnet publish --framework netcoreapp3.1 --runtime osx.10.11-x64
  ```

- Publique el archivo del proyecto especificado:

  ```dotnetcli
  dotnet publish ~/projects/app1/app1.csproj
  ```

- Publique la aplicación actual pero sin restaurar las referencias de proyecto a proyecto (P2P), solo el proyecto raíz, durante la operación de restauración:

  ```dotnetcli
  dotnet publish --no-dependencies
  ```

## <a name="see-also"></a>Vea también

- [Información general sobre la publicación de aplicaciones de .NET Core](../deploying/index.md)
- [Publicación de aplicaciones .NET Core con la CLI de .NET Core](../deploying/deploy-with-cli.md)
- [Marcos de trabajo de destino](../../standard/frameworks.md)
- [Catálogo de identificadores de tiempo de ejecución (RID)](../rid-catalog.md)
- [Trabajo con la certificación de macOS Catalina](../install/macos-notarization-issues.md)
- [Estructura de directorios de una aplicación publicada](/aspnet/core/hosting/directory-structure)
- [Referencia de la línea de comandos de MSBuild](/visualstudio/msbuild/msbuild-command-line-reference)
- [Perfiles de publicación (.pubxml) de Visual Studio para la implementación de aplicaciones ASP.NET Core](/aspnet/core/host-and-deploy/visual-studio-publish-profiles)
- [dotnet msbuild](dotnet-msbuild.md)
- [ILLInk.Tasks](https://aka.ms/dotnet-illink)
