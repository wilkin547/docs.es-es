---
title: Comando dotnet | SDK de .NET Core
description: "Aprenda sobre el comando dotnet (el controlador genérico para las herramientas de la CLI de .NET Core) y su uso."
keywords: dotnet, CLI, comandos de la CLI, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 10/07/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 93015521-2127-4fe9-8fce-ca79bcc4ff49
translationtype: Human Translation
ms.sourcegitcommit: 1a84c694945fe0c77468eb77274ab46618bccae6
ms.openlocfilehash: bbc13c8cca82e660f0f8ccf7d88c0340d9c06e68

---

#<a name="dotnet-command"></a>comando dotnet

## <a name="name"></a>Nombre

dotnet: controlador general para ejecutar comandos de la línea de comandos

## <a name="synopsis"></a>Sinopsis

`dotnet [--version] [--verbose] [--info] [command] [arguments] [--help]`

## <a name="description"></a>Descripción
`dotnet` es un controlador genérico para la cadena de herramientas de la interfaz de la línea de comandos (CLI). Se invoca por sí mismo y proporciona breves instrucciones de uso. 

Cada característica específica se implementa como un comando. Para usar la característica, el comando se especifica después de `dotnet`, por ejemplo, [`dotnet build`](dotnet-build.md). Todos los argumentos que siguen al comando son sus propios argumentos. 

La única vez que `dotnet` se usa como comando por sí solo es para ejecutar aplicaciones portátiles. Basta con especificar una DLL de aplicación portátil después del verbo `dotnet` para ejecutar la aplicación.    

## <a name="options"></a>Opciones

`-v|--verbose`

Habilita la salda detallada.

`--version`

Imprime la versión de las herramientas de la CLI.

`--info`

Imprime información más detallada sobre las herramientas de la CLI, como el sistema operativo actual, la confirmación de SHA para la versión, etc. 

`-h|--help`

Imprime una corta ayuda para el comando. Si se usa con `dotnet` también imprime una lista de los comandos disponibles.  

## <a name="dotnet-commands"></a>comandos de dotnet

Existen los siguientes comandos para dotnet:

* [dotnet-new](dotnet-new.md)
   * Inicializa un proyecto de aplicación de consola de C# o F #.
* [dotnet-restore](dotnet-restore.md)
  * Restaura las dependencias de una aplicación determinada. 
* [dotnet-build](dotnet-build.md)
  * Compila una aplicación .NET Core.
* [dotnet-publish](dotnet-publish.md)
   * Publica una aplicación .NET portátil o autocontenida.
* [dotnet-run](dotnet-run.md)
   * Ejecuta la aplicación desde el origen.
* [dotnet-test](dotnet-test.md)
   * Ejecuta pruebas mediante un ejecutor de pruebas especificado en el archivo project.json.
* [dotnet-pack](dotnet-pack.md)
   * Crea un paquete de NuGet de su código.
* [dotnet-migrate](dotnet-migrate.md)
   * Migra un proyecto de Preview 2 válido a un proyecto de Preview 3.
* [dotnet-msbuild](dotnet-msbuild.md)
   * Proporciona acceso a la línea de comandos de MSBuild.

## <a name="examples"></a>Ejemplos

Inicialización de una aplicación de consola de .NET Core de ejemplo que se puede compilar y ejecutar:

`dotnet new`

Restauración de dependencias de una aplicación determinada:

`dotnet restore`

Compilación de un proyecto y sus dependencias en un directorio determinado: 

`dotnet build`

Ejecución de una aplicación portátil con nombre `myapp.dll`: `dotnet myapp.dll`

## <a name="environment"></a>Entorno 

`DOTNET_PACKAGES`

La caché del paquete principal. Si no se establece, el valor predeterminado es $HOME/.nuget/packages en Unix o %HOME%\NuGet\Packages en Windows.

`DOTNET_SERVICING`

Especifica la ubicación del índice de mantenimiento que usará el host compartido al cargar el entorno de tiempo de ejecución.

`DOTNET_CLI_TELEMETRY_OPTOUT`

Especifica si se recopilan datos sobre el uso de herramientas de .NET Core y se envían a Microsoft. `true` para desactivar la característica de telemetría (valores true, 1 o sí aceptado); de lo contrario, `false` (valores false, 0 o no aceptado). Si no se establece, se toma como predeterminado `false`, es decir, la característica de telemetría está activada.




<!--HONumber=Nov16_HO3-->


