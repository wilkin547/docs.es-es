---
title: 'Comando dotnet-pack: CLI de .NET Core | Microsoft Docs'
description: El comando dotnet-pack crea paquetes de NuGet para el proyecto .NET Core.
keywords: dotnet-pack, CLI, comando de la CLI, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 8dbbb3f7-b817-4161-a6c8-a3489d05e051
ms.translationtype: Human Translation
ms.sourcegitcommit: 14c2e01ab0c30c9f1cbfdcc53ea85fe51a4d8c2e
ms.openlocfilehash: 5a2ea69825fa336b1d8ce2283e214d02c16347e3
ms.contentlocale: es-es
ms.lasthandoff: 05/01/2017

---

# <a name="dotnet-pack"></a>dotnet-pack

## <a name="name"></a>Name

`dotnet-pack`: empaqueta el código en un paquete de NuGet.

## <a name="synopsis"></a>Sinopsis

`dotnet pack [<PROJECT>] [-o|--output] [--no-build] [--include-symbols] [--include-source] [-c|--configuration] [--version-suffix <VERSION_SUFFIX>] [-s|--serviceable] [-v|--verbosity] [-h|--help]`

## <a name="description"></a>Descripción

El comando `dotnet pack` compila el proyecto y crea paquetes de NuGet. El resultado de este comando es un paquete de NuGet. Si la opción `--include-symbols` está presente, se crea otro paquete que contiene los símbolos de depuración. 

Las dependencias de NuGet del proyecto empaquetado se agregan al archivo *.nuspec*, por lo que se pueden resolver adecuadamente cuando se instala el paquete. Las referencias de proyecto a proyecto no se empaquetan dentro del proyecto. Actualmente, debe disponer de un paquete por proyecto si tiene dependencias de proyecto a proyecto.

De forma predeterminada, `dotnet pack` compila primero el proyecto. Si desea evitar este comportamiento, pase la opción `--no-build`. A menudo resulta útil en escenarios de compilación de integración continua (CI) donde se conoce el código que se compiló anteriormente.

Puede proporcionar propiedades de MSBuild en el comando `dotnet pack` para el proceso de empaquetado. Para obtener más información, vea [Propiedades de metadatos de NuGet](csproj.md#nuget-metadata-properties) y la [Referencia de la línea de comandos de MSBuild](/visualstudio/msbuild/msbuild-command-line-reference).

## <a name="arguments"></a>Argumentos

`PROJECT` 
    
El proyecto para empaquetar. O bien una ruta de acceso a un [archivo csproj](csproj.md) o a un directorio. Si se omite, se toma como predeterminado el directorio actual. 

## <a name="options"></a>Opciones

`-h|--help`

Imprime una corta ayuda para el comando.  

`-o|--output <OUTPUT_DIRECTORY>`

Coloca los paquetes compilados en el directorio especificado. 

`--no-build`

No compila el proyecto antes de empaquetarlo. 

`--include-symbols`

Genera símbolos `nupkg`. 

`--include-source`

Incluye los archivos de origen en el paquete de NuGet. Los archivos de origen se incluyen en la carpeta `src` dentro de `nupkg`. 

`-c|--configuration <CONFIGURATION>`

Configuración para usar al compilar el proyecto. Si no se especifica, la configuración que se toma como predeterminada es `Debug`.

`--version-suffix <VERSION_SUFFIX>`

Define el valor de la propiedad de `$(VersionSuffix)` en el proyecto.

`-s|--serviceable`

Establece la marca de servicio en el paquete. Para más información, consulte [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing) (Blog de .NET: .NET 4.5.1 admite actualizaciones de seguridad de Microsoft para bibliotecas NuGet de .NET).

`--verbosity <LEVEL>`

Establece el nivel de detalle del comando. Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.

## <a name="examples"></a>Ejemplos

Empaquetado del proyecto en el directorio actual:

`dotnet pack`

Empaquetar el proyecto `app1`:

`dotnet pack ~/projects/app1/project.csproj`
    
Empaquetar el proyecto en el directorio actual y colocar los paquetes resultantes en la carpeta `nupkgs`:

`dotnet pack --output nupkgs`

Empaquetar el proyecto en el directorio actual en la carpeta `nupkgs` y omitir del paso de compilación:

`dotnet pack --no-build --output nupkgs`

Con el sufijo de la versión del proyecto configurado como `<VersionSuffix>$(VersionSuffix)</VersionSuffix>` en el archivo *.csproj*, empaquetar el proyecto actual y actualizar la versión del paquete resultante con el sufijo dado:

`dotnet pack --version-suffix "ci-1234"`

Establecer la versión del paquete en `2.1.0` con la propiedad de MSBuild `PackageVersion`:

`dotnet pack /p:PackageVersion=2.1.0`

