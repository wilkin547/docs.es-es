---
title: Comando dotnet-migrate | Microsoft Docs
description: El comando dotnet-migrate migra un proyecto y todas sus dependencias.
keywords: dotnet-migrate, CLI, comando de la CLI, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 11/13/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 0da07253-5ae1-42e9-9455-bffee9950952
translationtype: Human Translation
ms.sourcegitcommit: 796df1549a7553aa93158598d62338c02d4df73e
ms.openlocfilehash: 57ae01419c6f7a75970816e1245094c38c5247fa

---

#<a name="dotnet-migrate"></a>dotnet-migrate

[!INCLUDE[preview-warning](../../../includes/warning.md)]

## <a name="name"></a>Nombre 
dotnet-migrate: migra un proyecto .NET Core Preview 2 a un proyecto .NET Core RC4

## <a name="synopsis"></a>Sinopsis

`dotnet migrate [--help] [--template-file]  
    [--sdk-package-version] [--xproj-file]  
    [--skip-project-references]  [--report-file] [--format-report-file-json]
    [--skip-backup]
    [<arguments>]`

## <a name="description"></a>Descripción
El comando `dotnet migrate` migra un proyecto `project.json` válido basado en Preview 2 a un proyecto `csproj` de RC4 válido. De forma predeterminada, el comando migrará el proyecto raíz y todas las referencias de proyecto que contiene el proyecto raíz. Este comportamiento se puede deshabilitar mediante la opción `--skip-project-references` en tiempo de ejecución. 

La migración se puede realizar en:

* Un único proyecto especificando el archivo `project.json` que quiere migrar
* Todos los directorios especificados en el archivo `global.json` pasando una ruta de acceso al archivo `global.json`
* En todos los subdirectorios del directorio dado de manera recursiva 

El comando migrate mantendrá el archivo `project.json` migrado dentro de un directorio `backup` que se creará si no existe. Esta acción se puede invalidar mediante la opción `--skip-backup`. 

De forma predeterminada, la operación de migración generará el estado del proceso de migración a la salida estándar (STDOUT). Si usa la opción `--report-file`, esa salida también se guardará en un archivo que especifique. 

A partir de RC4, el comando `dotnet migrate` solo admite archivos `project.json` de Preview 2 válidos. Esto significa que no puede usarlo para migrar archivos `project.json` antiguos de DNX o Preview 1 directamente a csproj; primero deberá migrarlos a archivos project.json de Preview 2 y luego a archivos csproj. En el futuro, agregaremos compatibilidad con proyectos de Preview 1. 

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

`dotnet migrate -s -v 1.0.0-preview4`


<!--HONumber=Feb17_HO2-->


