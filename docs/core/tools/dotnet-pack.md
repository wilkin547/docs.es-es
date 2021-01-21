---
title: Comando dotnet
description: El comando dotnet pack crea paquetes NuGet para el proyecto de .NET.
ms.date: 04/28/2020
ms.openlocfilehash: a9a634c358f5de4f28c3de06edc9a2b4d2eb8d57
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2021
ms.locfileid: "98190083"
---
# <a name="dotnet-pack"></a>dotnet pack

**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.x y versiones posteriores

## <a name="name"></a>NOMBRE

`dotnet pack`: empaqueta el código en un paquete de NuGet.

## <a name="synopsis"></a>Sinopsis

```dotnetcli
dotnet pack [<PROJECT>|<SOLUTION>] [-c|--configuration <CONFIGURATION>]
    [--force] [--include-source] [--include-symbols] [--interactive]
    [--no-build] [--no-dependencies] [--no-restore] [--nologo]
    [-o|--output <OUTPUT_DIRECTORY>] [--runtime <RUNTIME_IDENTIFIER>]
    [-s|--serviceable] [-v|--verbosity <LEVEL>]
    [--version-suffix <VERSION_SUFFIX>]

dotnet pack -h|--help
```

## <a name="description"></a>Descripción

El comando `dotnet pack` compila el proyecto y crea paquetes de NuGet. El resultado de este comando es un paquete de NuGet (es decir, un archivo *.nupkg*).

Si quiere generar un paquete que contenga los símbolos de depuración, tiene dos opciones a su disposición:

- `--include-symbols`: crea el paquete de símbolos.
- `--include-source`: crea el paquete de símbolos con una carpeta `src` dentro que contiene los archivos de origen.

Las dependencias de NuGet del proyecto empaquetado se agregan al archivo *.nuspec*, por lo que se pueden resolver adecuadamente cuando se instala el paquete. Las referencias de proyecto a proyecto no se empaquetan dentro del proyecto. Actualmente, debe disponer de un paquete por proyecto si tiene dependencias de proyecto a proyecto.

De forma predeterminada, `dotnet pack` compila primero el proyecto. Si desea evitar este comportamiento, pase la opción `--no-build`. Esta opción a menudo resulta útil en escenarios de compilación de integración continua (CI) donde se conoce el código que se compiló anteriormente.

> [!NOTE]
> En algunos casos, no se puede realizar la compilación implícita. Esto puede ocurrir cuando se establece `GeneratePackageOnBuild`, para evitar una dependencia cíclica entre los destinos de compilación y de paquete. La compilación también puede producir un error si hay un archivo bloqueado u otro problema.

Puede proporcionar propiedades de MSBuild en el comando `dotnet pack` para el proceso de empaquetado. Para obtener más información, vea [pack y restore de NuGet como destinos de MSBuild](/nuget/reference/msbuild-targets#pack-target) y [Referencia de la línea de comandos de MSBuild](/visualstudio/msbuild/msbuild-command-line-reference). La sección [Ejemplos](#examples) muestra cómo utilizar el modificador `-p` de MSBuild en un par de escenarios diferentes.

Los proyectos web no están empaquetados de forma predeterminada. Para invalidar el comportamiento predeterminado, agregue la siguiente propiedad a su archivo *.csproj*:

```xml
<PropertyGroup>
   <IsPackable>true</IsPackable>
</PropertyGroup>
```

### <a name="implicit-restore"></a>Restauración implícita

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="arguments"></a>Argumentos

`PROJECT | SOLUTION`

  El archivo de proyecto o solución para empaquetar. Se trata de una ruta a un archivo .csproj, .vbproj o .fsproj, o a un archivo de solución o un directorio. Si no se especifica, el comando busca un archivo del proyecto o de la solución en el directorio actual.

## <a name="options"></a>Opciones

- **`-c|--configuration <CONFIGURATION>`**

  Define la configuración de compilación. El valor predeterminado para la mayoría de los proyectos es `Debug`, pero puede invalidar los valores de configuración de compilación en el proyecto.

- **`--force`**

  Fuerza la resolución de todas las dependencias, incluso si la última restauración se realizó correctamente. Especificar esta marca es lo mismo que eliminar el archivo *project.assets.json*.

- **`-h|--help`**

  Imprime una corta ayuda para el comando.

- **`--include-source`**

  Incluye los paquetes NuGet de símbolos de depuración, además de los paquetes NuGet normales en el directorio de salida. Los archivos de origen se incluyen en la carpeta `src` dentro del paquete de símbolos.

- **`--include-symbols`**

  Incluye los paquetes NuGet de símbolos de depuración, además de los paquetes NuGet normales en el directorio de salida.

- **`--interactive`**

  Permite que el comando se detenga y espere la entrada o acción del usuario (por ejemplo, completar la autenticación). Disponible desde el SDK de .NET Core 3.0.

- **`--no-build`**

  No compila el proyecto antes de empaquetarlo. También establece la marca `--no-restore` de forma implícita.

- **`--no-dependencies`**

  Omite las referencias de proyecto a proyecto y solo restaura el proyecto raíz.

- **`--no-restore`**

  No ejecuta una restauración implícita al ejecutar el comando.

- **`--nologo`**

  No se muestra la pancarta de inicio ni el mensaje de copyright. Disponible desde el SDK de .NET Core 3.0.

- **`-o|--output <OUTPUT_DIRECTORY>`**

  Coloca los paquetes compilados en el directorio especificado.

- **`--runtime <RUNTIME_IDENTIFIER>`**

  Especifica el tiempo de ejecución de destino para el que restaurar los paquetes. Para obtener una lista de identificadores de tiempo de ejecución (RID), consulte el [catálogo de RID](../rid-catalog.md).

- **`-s|--serviceable`**

  Establece la marca de servicio en el paquete. Para obtener más información, vea [.NET Blog: .NET Framework 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing) (Blog de .NET: .NET Framework 4.5.1 admite actualizaciones de seguridad de Microsoft para bibliotecas NuGet de .NET).

- **`--version-suffix <VERSION_SUFFIX>`**

  Define el valor de la propiedad de `$(VersionSuffix)` en el proyecto.

- **`-v|--verbosity <LEVEL>`**

  Establece el nivel de detalle del comando. Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.

## <a name="examples"></a>Ejemplos

- Empaquetado del proyecto en el directorio actual:

  ```dotnetcli
  dotnet pack
  ```

- Empaquetar el proyecto `app1`:

  ```dotnetcli
  dotnet pack ~/projects/app1/project.csproj
  ```

- Empaquetar el proyecto en el directorio actual y colocar los paquetes resultantes en la carpeta `nupkgs`:

  ```dotnetcli
  dotnet pack --output nupkgs
  ```

- Empaquetar el proyecto en el directorio actual en la carpeta `nupkgs` y omitir del paso de compilación:

  ```dotnetcli
  dotnet pack --no-build --output nupkgs
  ```

- Con el sufijo de la versión del proyecto configurado como `<VersionSuffix>$(VersionSuffix)</VersionSuffix>` en el archivo *.csproj*, empaquetar el proyecto actual y actualizar la versión del paquete resultante con el sufijo dado:

  ```dotnetcli
  dotnet pack --version-suffix "ci-1234"
  ```

- Establecer la versión del paquete en `2.1.0` con la propiedad de MSBuild `PackageVersion`:

  ```dotnetcli
  dotnet pack -p:PackageVersion=2.1.0
  ```

- Empaquete el proyecto para un determinado [marco de destino](../../standard/frameworks.md):

  ```dotnetcli
  dotnet pack -p:TargetFrameworks=net45
  ```

- Empaquete el proyecto y use un entorno de ejecución específico (Windows 10) para la operación de restauración:

  ```dotnetcli
  dotnet pack --runtime win10-x64
  ```

- Empaquete el proyecto mediante un archivo *.nuspec*:

  ```dotnetcli
  dotnet pack ~/projects/app1/project.csproj -p:NuspecFile=~/projects/app1/project.nuspec -p:NuspecBasePath=~/projects/app1/nuget
  ```

  Para obtener información sobre cómo usar `NuspecFile`, `NuspecBasePath` y `NuspecProperties`, vea los siguientes recursos:

  - [Empaquetado mediante un archivo .nuspec](/nuget/reference/msbuild-targets#packing-using-a-nuspec)
  - [Puntos de extensión avanzados para crear un paquete personalizado](/nuget/reference/msbuild-targets#advanced-extension-points-to-create-customized-package)
  - [Propiedades globales](/visualstudio/msbuild/msbuild-properties#global-properties)
