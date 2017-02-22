---
title: Comando dotnet-test | Microsoft Docs
description: El comando `dotnet test` se usa para ejecutar pruebas unitarias en un proyecto determinado.
keywords: dotnet-test, CLI, comando de la CLI, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 02/08/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 4bf0aef4-148a-41c6-bb95-0a9e1af8762e
translationtype: Human Translation
ms.sourcegitcommit: 02f39bc959a56ab0fc2cfa57ce13f300a8a46107
ms.openlocfilehash: 204ebdb5a945dcd0c9277f1d95c113e829303b32

---

#<a name="dotnet-test-net-core-tools-rc4"></a>dotnet-test (.NET Core Tools RC4)

> [!WARNING]
> Este tema se aplica a .NET Core Tools RC4. Para la versión .NET Core Tools Preview 2, consulte el tema [dotnet-test](../../tools/dotnet-test.md).

## <a name="name"></a>Nombre

`dotnet-test`: controlador de prueba de .NET

## <a name="synopsis"></a>Sinopsis

`dotnet test [project] [--help] 
    [--settings] [--list-tests] [--filter] 
    [--test-adapter-path] [--logger] 
    [--configuration] [--framework] [--output] [--diag]
    [--no-build] [--verbosity]`

## <a name="description"></a>Descripción

El comando `dotnet test` se usa para ejecutar pruebas unitarias en un proyecto determinado. Las pruebas unitarias son proyectos de biblioteca de clases que tienen dependencias en el marco de pruebas unitarias (por ejemplo, NUnit o xUnit) y en el ejecutor dotnet test de ese marco de pruebas unitarias. Estas se empaquetan como paquetes de NuGet y se restauran como dependencias ordinarias para el proyecto.

Los proyectos de prueba también necesitan especificar el ejecutor de la prueba. Para ello se utiliza un elemento `<PackageReference>` ordinario, como se puede ver en el siguiente archivo de proyecto de ejemplo:

[!code-xml[Plantilla de XUnit Basic](../../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="options"></a>Opciones

`[project]`
    
Especifica una ruta de acceso al proyecto de prueba. Si se omite, se toma como predeterminado el directorio actual.

`-h|--help`

Imprime una corta ayuda para el comando.

`-s|--settings <SETTINGS_FILE>`

Configuración que se usará al ejecutar las pruebas. 

`-t|--list-tests`

Enumera todas las pruebas detectadas en el proyecto actual. 

`--filter <EXPRESSION>`

Filtra las pruebas del proyecto actual con la expresión dada. Para más información sobre la compatibilidad de filtrado, consulte [Running selective unit tests in Visual Studio using TestCaseFilter](https://aka.ms/vstest-filtering) (Ejecutar pruebas unitarias selectivas en Visual Studio mediante TestCaseFilter).

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

Use los adaptadores de prueba personalizados en la ruta especificada de esta ejecución de pruebas. 

`-l|--logger <LoggerUri/FriendlyName>`

Especifica un registrador para los resultados de pruebas. 

`-c|--configuration <Debug|Release>`

Configuración con la que se va a realizar la compilación. El valor predeterminado es `Debug`, pero la configuración del proyecto podría invalidar esta configuración del SDK predeterminada.

`-f|--framework <FRAMEWORK>`

Busca archivos binarios de prueba para un marco específico.

`-o|--output <OUTPUT_DIRECTORY>`

Directorio donde se encuentran los archivos binarios que se ejecutarán.

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

Habilita el modo de diagnóstico para la plataforma de prueba y escribe mensajes de diagnóstico en el archivo especificado. 

`--no-build` 

No compila el proyecto de prueba antes de ejecutarlo.

`-v|--verbosity [quiet|minimal|normal|diagnostic]`

Establece el nivel de detalle del comando. Puede especificar los siguientes niveles de detalle: q[uiet], m[inimal], n[ormal], d[etailed] y diag[nostic]. 

## <a name="examples"></a>Ejemplos

Ejecución de las pruebas en el proyecto en el directorio actual:

`dotnet test` 

Ejecución de las pruebas en el proyecto test1:

`dotnet test ~/projects/test1/test1.csproj` 

## <a name="see-also"></a>Vea también

[Marcos](../../../standard/frameworks.md)

[Catálogo de identificadores de tiempo de ejecución (RID)](../../rid-catalog.md)



<!--HONumber=Feb17_HO2-->


