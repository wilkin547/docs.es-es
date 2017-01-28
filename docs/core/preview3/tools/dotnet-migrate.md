---
title: Comando dotnet-migrate | SDK de .NET Core
description: El comando dotnet-migrate migra un proyecto y todas sus dependencias.
keywords: dotnet-migrate, CLI, comando de la CLI, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 11/13/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 70285a83-4103-4617-be8b-d0e1e9a4a91d
translationtype: Human Translation
ms.sourcegitcommit: 1a84c694945fe0c77468eb77274ab46618bccae6
ms.openlocfilehash: 150d70e3f0a80f7f6e733abee3691a0fe420919f

---

#<a name="dotnet-migrate"></a>dotnet-migrate

## <a name="name"></a>Nombre 
dotnet-migrate: migra un proyecto .NET Core de Preview 2 a un proyecto .NET Core de Preview 3

## <a name="synopsis"></a>Sinopsis

`dotnet migrate [--help] [--template-file]  
    [--sdk-package-version] [--xproj-file]  
    [--skip-project-references]  [--report-file] [--format-report-file-json]
    [--skip-backup]
    [<arguments>]`

## <a name="description"></a>Descripción
El comando `dotnet migrate` migra un proyecto `project.json` válido de Preview 2 a un proyecto `csproj` válido de Preview 3. De forma predeterminada, el comando migrará el proyecto raíz y todas las referencias de proyecto que contiene el proyecto raíz. Este comportamiento se puede deshabilitar mediante la opción `--skip-project-references` en tiempo de ejecución. 

La migración se puede realizar en:

* Un único proyecto especificando el archivo `project.json` que quiere migrar
* Todos los directorios especificados en el archivo `global.json` pasando una ruta de acceso al archivo `global.json`
* En todos los subdirectorios del directorio dado de manera recursiva 

El comando migrate mantendrá el archivo `project.json` migrado dentro de un directorio `backup` que se creará si no existe. Esta acción se puede invalidar mediante la opción `--skip-backup`. 

De forma predeterminada, la operación de migración generará el estado del proceso de migración a la salida estándar (STDOUT). Si usa la opción `--report-file`, esa salida también se guardará en un archivo que especifique. 

A partir de Preview 3, el comando `dotnet migrate` solo admite archivos `project.json` válidos de Preview 2. Esto significa que no puede usarlo para migrar archivos `project.json` antiguos de DNX o Preview 1 directamente a csproj; primero deberá migrarlos a archivos project.json de Preview 2 y luego a archivos csproj. En el futuro, agregaremos compatibilidad con proyectos de Preview 1. 

## <a name="options"></a>Opciones

`-h|--help`

Imprime una corta ayuda para el comando.  

`-t|--template-file <TEMPLATE_FILE>`

Archivo csproj de plantilla que se utilizará para la migración. De forma predeterminada, se usará la misma plantilla que la descartada por `dotnet new`. 

`-v|--sdk-package-version <VERSION>`

La versión del paquete de sdk a la que se hará referencia en la aplicación migrada. El valor predeterminado es la versión del sdk en dotnet-new.

`-x|--xproj-file <FILE>`

La ruta de acceso al archivo xproj que se usará. Necesario cuando hay más de un archivo xproj en un directorio de proyecto.

`-s|--skip-project-references [Debug|Release]`

Omite la migración de referencias de proyecto. De forma predeterminada, las referencias de proyecto se migran de manera recursiva.

`-r|--report-file <REPORT_FILE>`

Salida del informe de migración a un archivo además de a la consola.

`--format-report-file-json <REPORT_FILE>`

Salida del archivo de informe de migración como json en lugar de mensajes de usuario.

`--skip-backup`

Omite el traslado de project.json, global.json y \*.xproj a un directorio `backup` tras la realización correcta de la migración.

## <a name="examples"></a>Ejemplos

Migra un proyecto del directorio actual y todas sus dependencias de proyecto a proyecto:

`dotnet migrate`

Migra todos los proyectos a los que apunta el archivo `global.json`:

`dotnet migrate path/to/global.json`

Migra solo el proyecto actual y ninguna dependencia de proyecto a proyecto y usa una versión especifica del SDK:

`dotnet migrate -s -v 1.0.0-preview3`




<!--HONumber=Nov16_HO3-->


