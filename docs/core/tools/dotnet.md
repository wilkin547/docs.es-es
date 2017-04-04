---
title: 'Comando dotnet: CLI de .NET Core |Microsoft Docs'
description: "Aprenda sobre el comando dotnet (el controlador genérico para las herramientas de la CLI de .NET Core) y su uso."
keywords: dotnet, CLI, comandos de la CLI, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 03/20/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 256e468e-eaaa-4715-b5fb-8cbddcf80e69
translationtype: Human Translation
ms.sourcegitcommit: dff752a9d31ec92b113dae9eed20cd72faf57c84
ms.openlocfilehash: a470403e703ffb55de3d91cd5334c09bf11be06d
ms.lasthandoff: 03/22/2017

---

# <a name="dotnet-command"></a>comando dotnet

## <a name="name"></a>Name

`dotnet`: controlador general para ejecutar comandos de la línea de comandos.

## <a name="synopsis"></a>Sinopsis

`dotnet [command] [arguments] [--version] [--info] [-d|--diagnostics] [-v|--verbose] [--fx-version] [--additionalprobingpath] [-h|--help]`

## <a name="description"></a>Descripción

`dotnet` es un controlador genérico para la cadena de herramientas de la interfaz de la línea de comandos (CLI). Se invoca por sí mismo y proporciona breves instrucciones de uso.

Cada característica específica se implementa como un comando. Para usar la característica, el comando se especifica después de `dotnet`, por ejemplo, [`dotnet build`](dotnet-build.md). Todos los argumentos que siguen al comando son sus propios argumentos.

La única vez que `dotnet` se usa como un comando por sí solo es para ejecutar [aplicaciones dependientes del marco](../app-types.md). Especifique una DLL de aplicación después del verbo `dotnet` para ejecutar la aplicación (por ejemplo, `dotnet myapp.dll`).

## <a name="options"></a>Opciones

`-v|--verbose`

Habilita la salda detallada.

`-d|--diagnostics`

Habilita la salida de diagnóstico.

`--fx-version <VERSION>`

Versión instalada de Shared Framework que se usa para ejecutar la aplicación.

`--additionalprobingpath <PATH>`

Ruta de acceso que contiene directivas de sondeo y ensamblados para sondear.

`--version`

Imprime la versión de las herramientas de la CLI.

`--info`

Imprime información detallada sobre las herramientas de la CLI y el entorno, como el sistema operativo actual, el SHA de confirmación para la versión y otra información.

`-h|--help`

Imprime una corta ayuda para el comando. Si se usa con `dotnet`, también imprime una lista de los comandos disponibles.

## <a name="dotnet-commands"></a>comandos de dotnet

### <a name="general"></a>General

Comando | Función
--- | ---
[dotnet-build](dotnet-build.md) | Compila una aplicación .NET Core.
[dotnet-clean](dotnet-clean.md) | Limpia las salidas de la compilación.
[dotnet-migrate](dotnet-migrate.md) | Migra un proyecto de Preview 2 válido a un proyecto del SDK 1.0 de .NET Core.
[dotnet-msbuild](dotnet-msbuild.md) | Proporciona acceso a la línea de comandos de MSBuild.
[dotnet-new](dotnet-new.md) | Inicializa un proyecto de C# o F# para una plantilla determinada.
[dotnet-pack](dotnet-pack.md) | Crea un paquete de NuGet de su código.
[dotnet-publish](dotnet-publish.md) | Publica una aplicación dependiente del maco .NET o autocontenida.
[dotnet-restore](dotnet-restore.md) | Restaura las dependencias de una aplicación determinada.
[dotnet-run](dotnet-run.md) | Ejecuta la aplicación desde el origen.
[dotnet-sln](dotnet-sln.md) | Opciones para agregar, quitar y mostrar proyectos en un archivo de solución.
[dotnet-test](dotnet-test.md) | Ejecuta pruebas usando un ejecutor de pruebas.

### <a name="project-references"></a>Referencias de proyecto

Comando | Función
--- | ---
[dotnet-add reference](dotnet-add-reference.md) | Agrega una referencia de proyecto.
[dotnet-list reference](dotnet-list-reference.md) | Enumera referencias de proyecto.
[dotnet-remove reference](dotnet-remove-reference.md) | Quita una referencia de proyecto.

### <a name="nuget-packages"></a>Paquetes NuGet

Comando | Función
--- | ---
[dotnet-add package](dotnet-add-package.md) | Agrega un paquete NuGet.
[dotnet-remove package](dotnet-remove-package.md) | Quita un paquete NuGet.

### <a name="nuget-commands"></a>Comandos NuGet

Comando | Función
--- | ---
[dotnet-nuget delete](dotnet-nuget-delete.md) | Elimina o quita de la lista un paquete del servidor.
[dotnet-nuget locals](dotnet-nuget-locals.md) | Borra o muestra los recursos de NuGet locales, como la caché de solicitudes http, la caché temporal o la carpeta de paquetes global de toda la máquina.
[dotnet-nuget push](dotnet-nuget-push.md) | Inserta un paquete en el servidor y lo publica.

## <a name="examples"></a>Ejemplos

Inicialización de una aplicación de consola de .NET Core de ejemplo que se puede compilar y ejecutar:

`dotnet new console`

Restauración de dependencias de una aplicación determinada:

`dotnet restore`

Compilación de un proyecto y sus dependencias en un directorio determinado:

`dotnet build`

Ejecuta una aplicación dependiente del marco denominada `myapp.dll`:

`dotnet myapp.dll`

## <a name="environment-variables"></a>Variables de entorno

`DOTNET_PACKAGES`

La caché del paquete principal. Si no se establece, el valor predeterminado es `$HOME/.nuget/packages` en Unix o `%HOME%\NuGet\Packages` en Windows.

`DOTNET_SERVICING`

Especifica la ubicación del índice de mantenimiento que usará el host compartido al cargar el entorno de tiempo de ejecución.

`DOTNET_CLI_TELEMETRY_OPTOUT`

Especifica si se recopilan datos sobre el uso de herramientas de .NET Core y se envían a Microsoft. Establezca `true` para excluir la característica de telemetría (valores aceptados `true`, `1` o `yes`); en caso contrario, establezca `false` para incluir las características de telemetría (valores aceptados `false`, `0` o `no`). Si no se establece, el valor predeterminado es `false`, y se activa la característica de telemetría.

