---
title: Comando dotnet-migrate | Microsoft Docs
description: El comando dotnet-migrate migra un proyecto y todas sus dependencias.
keywords: dotnet-migrate, CLI, comando de la CLI, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 0da07253-5ae1-42e9-9455-bffee9950952
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: b7da4df5319e7c17900b9c093347e8a17045a6a3
ms.lasthandoff: 03/07/2017

---
#<a name="dotnet-migrate"></a>dotnet-migrate

## <a name="name"></a>Name 
dotnet-migrate: migra un proyecto .NET Core Preview 2 a un proyecto del SDK 1.0 de .NET Core.

## <a name="synopsis"></a>Sinopsis

```
dotnet migrate [-t|--template-file] [-v|--sdk-package-version] [-x|--xproj-file] [-s|--skip-project-references] [-r|--report-file] [--format-report-file-json] [--skip-backup] [<arguments>]
dotnet migrate [-h|--help]
```

## <a name="description"></a>Descripción

El comando `dotnet migrate` migrará un proyecto válido basado en *project.json* de Preview 2 a un proyecto válido *csproj* del SDK 1.0 de .NET Core. 

De forma predeterminada, el comando migrará el proyecto raíz y todas las referencias de proyecto que contiene el proyecto raíz. Este comportamiento se puede deshabilitar mediante la opción `--skip-project-references` en tiempo de ejecución. 

La migración se puede realizar en:

* Un único proyecto especificando el archivo *project.json* que quiere migrar
* Todos los directorios especificados en el archivo *global.json* pasando una ruta al archivo *global.json*
* En todos los subdirectorios del directorio dado de manera recursiva 

El comando de migración mantendrá el archivo *project.json* migrado dentro de un directorio `backup` que se creará si no existe. Esta acción se puede invalidar mediante la opción `--skip-backup`. 

De forma predeterminada, la operación de migración generará el estado del proceso de migración a la salida estándar (STDOUT). Si usa la opción `--report-file`, esa salida también se guardará en un archivo que especifique. 

El comando `dotnet migrate` solo admite archivos válidos *project.json* de Preview 2. Esto significa que no puede usarlo para migrar archivos *project.json* antiguos de DNX o Preview 1 directamente a csproj; primero deberá migrarlos a archivos project.json de Preview 2 y luego a archivos csproj. En el futuro, agregaremos compatibilidad con proyectos de Preview 1. 

## <a name="options"></a>Opciones

`-h|--help`

Imprime una corta ayuda para el comando.  

`-t|--template-file <TEMPLATE_FILE>`

Archivo csproj de plantilla que se utilizará para la migración. De forma predeterminada, se usará la misma plantilla que la descartada por `dotnet new console`. 

`-v|--sdk-package-version <VERSION>`

La versión del paquete de sdk a la que se hará referencia en la aplicación migrada. El valor predeterminado es la versión del sdk en dotnet-new.

`-x|--xproj-file <FILE>`

La ruta de acceso al archivo xproj que se usará. Necesario cuando hay más de un archivo xproj en un directorio de proyecto.

`-s|--skip-project-references [Debug|Release]`

Omite la migración de referencias de proyecto. De forma predeterminada, las referencias de proyecto se migran de forma recursiva.

`-r|--report-file <REPORT_FILE>`

Salida del informe de migración a un archivo además de a la consola.

`--format-report-file-json <REPORT_FILE>`

Salida del archivo de informe de migración como json en lugar de mensajes de usuario.

`--skip-backup`

Omite el traslado de project.json, global.json y \*.xproj a un directorio `backup` tras la realización correcta de la migración.

## <a name="examples"></a>Ejemplos

Migra un proyecto del directorio actual y todas sus dependencias de proyecto a proyecto:

`dotnet migrate`

Migrar todos los proyectos a los que apunta el archivo *global.json*:

`dotnet migrate path/to/global.json`

Migra solo el proyecto actual y ninguna dependencia de proyecto a proyecto y usa una versión especifica del SDK:

`dotnet migrate -s -v 1.0.0-preview4`
