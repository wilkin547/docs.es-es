---
title: 'Comando dotnet-restore: CLI de .NET Core | Microsoft Docs'
description: "Aprenda a restaurar dependencias y herramientas específicas del proyecto con el comando dotnet restore."
keywords: dotnet-restore, CLI, comando de la CLI, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 03/24/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: fd7a5769-afbe-4838-bbaf-3ae0cfcbb914
ms.translationtype: Human Translation
ms.sourcegitcommit: 602c173ff8d114a76c5598cd0826485ac32a2e72
ms.openlocfilehash: fd4fd6ef2e8482a2b961ccbca1f5227d80c8be53
ms.contentlocale: es-es
ms.lasthandoff: 03/29/2017

---

# <a name="dotnet-restore"></a>dotnet-restore

## <a name="name"></a>Name

`dotnet-restore`: restaura las dependencias y las herramientas de un proyecto.

## <a name="synopsis"></a>Sinopsis

`dotnet restore [<ROOT>] [-s|--source] [-r|--runtime] [--packages] [--disable-parallel] [--configfile] [--no-cache] [--ignore-failed-sources] [--no-dependencies] [-v|--verbosity] [-h|--help]`

## <a name="description"></a>Descripción

El comando `dotnet restore` usa NuGet para restaurar las dependencias, así como las herramientas específicas del proyecto que se especifican en el archivo project.json. De forma predeterminada, la restauración de dependencias y herramientas se realiza en paralelo.

Para restaurar las dependencias, NuGet necesita las fuentes donde se encuentran los paquetes. Las fuente se proporcionan normalmente mediante el archivo de configuración *NuGet.config*. Cuando se instalan las herramientas de la CLI, se proporciona un archivo de configuración predeterminado. Puede especificar más fuentes creando su propio archivo *NuGet.config* en el directorio del proyecto. También puede especificar fuentes adicionales por invocación en un símbolo del sistema. 

Para las dependencias, puede especificar dónde se colocan los paquetes restaurados durante la operación de restauración mediante el argumento `--packages`. Si no se especifica, se usa la caché de paquetes NuGet predeterminada, que se encuentra en el directorio `.nuget/packages` en el directorio de inicio del usuario en todos los sistemas operativos (por ejemplo, */home/user1* en Linux o *C:\Users\user1* en Windows).

Para herramientas específicas del proyecto, `dotnet restore` restaura primero el paquete en el que se empaqueta la herramienta y, a continuación, continúa con la restauración de las dependencias de la herramienta especificadas en su project.json.

El comportamiento del comando `dotnet restore` depende de algunas de las opciones de configuración del archivo *Nuget.Config*, si están presentes. Por ejemplo, establecer `globalPackagesFolder` en *NuGet.Config* coloca los paquetes NuGet restaurados en la carpeta especificada. Esta es una alternativa para especificar la opción `--packages` en el comando `dotnet restore`. Para obtener más información, vea la [referencia de NuGet.Config](https://docs.microsoft.com/nuget/schema/nuget-config-file).

## <a name="arguments"></a>Argumentos

`ROOT` 
    
Ruta de acceso opcional del archivo de proyecto para restaurar.

## <a name="options"></a>Opciones

`-h|--help`

Imprime una corta ayuda para el comando.

`-s|--source <SOURCE>`

Especifica un origen de paquetes de NuGet que se usará durante la operación de restauración. Esto invalida todos los orígenes especificados en los archivos *NuGet.config*. Al especificar esta opción varias veces, se pueden proporcionar varios orígenes.

`-r|--runtime <RUNTIME_IDENTIFIER>`

Especifica un tiempo de ejecución para la restauración del paquete. Se usa para restaurar los paquetes con tiempos de ejecución que no se enumeran explícitamente en la etiqueta `<RuntimeIdentifiers>` del archivo *.csproj*. Para obtener una lista de identificadores de tiempo de ejecución (RID), consulte el [catálogo de RID](../rid-catalog.md). Para proporcionar varios RID; especifique esta opción varias veces.

`--packages <PACKAGES_DIRECTORY>`

Especifica el directorio de los paquetes restaurados. 

`--disable-parallel`

Deshabilita la restauración de varios proyectos en paralelo. 

`--configfile <FILE>`

El archivo de configuración (*NuGet.config*) que se usa para la operación de restauración.

`--no-cache`

Especifica que no se almacenen en caché los paquetes y las solicitudes HTTP.

`--ignore-failed-sources`

Solo se advierte sobre los orígenes con error si hay paquetes que satisfagan el requisito de versión.

`--no-dependencies`

Al restaurar un proyecto con referencias de proyecto a proyecto (P2P), se restaura el proyecto raíz y no las referencias.

`--verbosity <LEVEL>`

Establece el nivel de detalle del comando. Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.

## <a name="examples"></a>Ejemplos

Restauración de dependencias y herramientas para el proyecto en el directorio actual:

`dotnet restore` 

Restauración de dependencias y herramientas para el proyecto `app1` encontrado en la ruta de acceso dada:

`dotnet restore ~/projects/app1/app1.csproj`
    
Restaurar las dependencias y las herramientas para el proyecto en el directorio actual con la ruta de acceso de archivo proporcionada como origen:

`dotnet restore -s c:\packages\mypackages` 

Restaurar las dependencias y las herramientas para el proyecto en el directorio actual mediante las dos rutas de acceso de archivo proporcionadas como orígenes:

`dotnet restore -s c:\packages\mypackages -s c:\packages\myotherpackages` 

Restaurar las dependencias y herramientas para el proyecto en el directorio actual y mostrar únicamente la salida mínima:

`dotnet restore --verbosity minimal`

