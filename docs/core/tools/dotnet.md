---
title: 'Comando dotnet: CLI de .NET Core'
description: Aprenda sobre el comando dotnet (el controlador genérico para las herramientas de la CLI de .NET Core) y su uso.
author: mairaw
ms.author: mairaw
ms.date: 06/04/2018
ms.openlocfilehash: 788dc746705f9328683019ab3ad9836204a1ea63
ms.sourcegitcommit: fc70fcb9c789b6a4aefcdace46f3643fd076450f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2018
ms.locfileid: "34805664"
---
# <a name="dotnet-command"></a>comando dotnet

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>nombre

`dotnet`: controlador general para ejecutar comandos de la línea de comandos.

## <a name="synopsis"></a>Sinopsis

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)
```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics] [--fx-version]
    [-h|--help] [--info] [--list-runtimes] [--list-sdks] [--roll-forward-on-no-candidate-fx] [-v|--verbosity] [--version]
```
# <a name="net-core-20tabnetcore20"></a>[.NET Core 2.0](#tab/netcore20)
```
dotnet [command] [arguments] [--additional-deps] [--additionalprobingpath] [-d|--diagnostics]
    [--fx-version] [-h|--help] [--info] [--roll-forward-on-no-candidate-fx] [-v|--verbosity] [--version]
```
# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)
```
dotnet [command] [arguments] [--additionalprobingpath] [-d|--diagnostics] [--fx-version]
    [-h|--help] [--info] [-v|--verbosity] [--version]
```
---

## <a name="description"></a>Description

`dotnet` es un controlador genérico para la cadena de herramientas de la interfaz de la línea de comandos (CLI). Se invoca por sí mismo y proporciona breves instrucciones de uso.

Cada característica específica se implementa como un comando. Para usar la característica, el comando se especifica después de `dotnet`, por ejemplo, [`dotnet build`](dotnet-build.md). Todos los argumentos que siguen al comando son sus propios argumentos.

La única vez que `dotnet` se usa como un comando por sí solo es para ejecutar [aplicaciones dependientes del marco](../deploying/index.md). Especifique una DLL de aplicación después del verbo `dotnet` para ejecutar la aplicación (por ejemplo, `dotnet myapp.dll`).

## <a name="options"></a>Opciones

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)

`--additional-deps <PATH>`

Ruta de acceso a archivo *deps.json* adicional.

`--additionalprobingpath <PATH>`

Ruta de acceso que contiene directivas de sondeo y ensamblados para sondear.

`-d|--diagnostics`

Habilita la salida de diagnóstico.

`--fx-version <VERSION>`

Versión del tiempo de ejecución de .NET Core instalado que se usará para ejecutar la aplicación.

`-h|--help`

Imprime una corta ayuda para el comando. Si se usa con `dotnet`, también imprime una lista de los comandos disponibles.

`--info`

Imprime información detallada sobre las herramientas de la CLI y el entorno, como el sistema operativo actual, el SHA de confirmación para la versión y otra información.

`--list-runtimes`

Muestra los tiempos de ejecución de .NET Core instalados.

`--list-sdks`

Muestra los SDK de .NET Core instalados.

`--roll-forward-on-no-candidate-fx`

 Se pone al día con ningún candidato de marco de trabajo compartido.

`-v|--verbosity <LEVEL>`

Establece el nivel de detalle del comando. Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`. Estos no se admiten en todos los comandos; consulte la página específica de cada comando para asegurarse de que la opción está disponible.

`--version`

Imprime la versión del SDK de .NET Core en uso.

# <a name="net-core-20tabnetcore20"></a>[.NET Core 2.0](#tab/netcore20)

`--additional-deps <PATH>`

Ruta de acceso a archivo *deps.json* adicional.

`--additionalprobingpath <PATH>`

Ruta de acceso que contiene directivas de sondeo y ensamblados para sondear.

`-d|--diagnostics`

Habilita la salida de diagnóstico.

`--fx-version <VERSION>`

Versión del tiempo de ejecución de .NET Core instalado que se usará para ejecutar la aplicación.

`-h|--help`

Imprime una corta ayuda para el comando. Si se usa con `dotnet`, también imprime una lista de los comandos disponibles.

`--info`

Imprime información detallada sobre las herramientas de la CLI y el entorno, como el sistema operativo actual, el SHA de confirmación para la versión y otra información.

`--roll-forward-on-no-candidate-fx`

 Se pone al día con ningún candidato de marco de trabajo compartido.

`-v|--verbosity <LEVEL>`

Establece el nivel de detalle del comando. Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`. Estos no se admiten en todos los comandos; consulte la página específica de cada comando para asegurarse de que la opción está disponible.

`--version`

Imprime la versión del SDK de .NET Core en uso.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

`--additionalprobingpath <PATH>`

Ruta de acceso que contiene directivas de sondeo y ensamblados para sondear.

`-d|--diagnostics`

Habilita la salida de diagnóstico.

`--fx-version <VERSION>`

Versión del tiempo de ejecución de .NET Core instalado que se usará para ejecutar la aplicación.

`-h|--help`

Imprime una corta ayuda para el comando. Si se usa con `dotnet`, también imprime una lista de los comandos disponibles.

`--info`

Imprime información detallada sobre las herramientas de la CLI y el entorno, como el sistema operativo actual, el SHA de confirmación para la versión y otra información.

`-v|--verbosity <LEVEL>`

Establece el nivel de detalle del comando. Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`. Estos no se admiten en todos los comandos; consulte la página específica de cada comando para asegurarse de que la opción está disponible.

`--version`

Imprime la versión del SDK de .NET Core en uso.

---

## <a name="dotnet-commands"></a>comandos de dotnet

### <a name="general"></a>General

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)

| Comando                                       | Función                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [dotnet build](dotnet-build.md)               | Compila una aplicación .NET Core.                                     |
| [dotnet build-server](dotnet-build-server.md) | Interactúa con servidores iniciados por una compilación.                          |
| [dotnet clean](dotnet-clean.md)               | Limpia las salidas de la compilación.                                                |
| [dotnet help](dotnet-help.md)                 | Muestra documentación más detallada en línea sobre el comando.           |
| [dotnet migrate](dotnet-migrate.md)           | Migra un proyecto de Preview 2 válido a un proyecto del SDK 1.0 de .NET Core.  |
| [dotnet msbuild](dotnet-msbuild.md)           | Proporciona acceso a la línea de comandos de MSBuild.                        |
| [dotnet new](dotnet-new.md)                   | Inicializa un proyecto de C# o F# para una plantilla determinada.                |
| [dotnet pack](dotnet-pack.md)                 | Crea un paquete de NuGet de su código.                               |
| [dotnet publish](dotnet-publish.md)           | Publica una aplicación dependiente del maco .NET o autocontenida. |
| [dotnet restore](dotnet-restore.md)           | Restaura las dependencias de una aplicación determinada.                  |
| [dotnet run](dotnet-run.md)                   | Ejecuta la aplicación desde el origen.                                   |
| [dotnet sln](dotnet-sln.md)                   | Opciones para agregar, quitar y mostrar proyectos en un archivo de solución.       |
| [dotnet store](dotnet-store.md)               | Almacena ensamblados en el almacenamiento de paquetes en tiempo de ejecución.                     |
| [dotnet test](dotnet-test.md)                 | Ejecuta pruebas usando un ejecutor de pruebas.                                     |

# <a name="net-core-20tabnetcore20"></a>[.NET Core 2.0](#tab/netcore20)

| Comando                             | Función                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [dotnet build](dotnet-build.md)     | Compila una aplicación .NET Core.                                     |
| [dotnet clean](dotnet-clean.md)     | Limpia las salidas de la compilación.                                              |
| [dotnet help](dotnet-help.md)       | Muestra documentación más detallada en línea sobre el comando.           |
| [dotnet migrate](dotnet-migrate.md) | Migra un proyecto de Preview 2 válido a un proyecto del SDK 1.0 de .NET Core.  |
| [dotnet msbuild](dotnet-msbuild.md) | Proporciona acceso a la línea de comandos de MSBuild.                        |
| [dotnet new](dotnet-new.md)         | Inicializa un proyecto de C# o F# para una plantilla determinada.                |
| [dotnet pack](dotnet-pack.md)       | Crea un paquete de NuGet de su código.                               |
| [dotnet publish](dotnet-publish.md) | Publica una aplicación dependiente del maco .NET o autocontenida. |
| [dotnet restore](dotnet-restore.md) | Restaura las dependencias de una aplicación determinada.                  |
| [dotnet run](dotnet-run.md)         | Ejecuta la aplicación desde el origen.                                   |
| [dotnet sln](dotnet-sln.md)         | Opciones para agregar, quitar y mostrar proyectos en un archivo de solución.       |
| [dotnet store](dotnet-store.md)     | Almacena ensamblados en el almacenamiento de paquetes en tiempo de ejecución.                     |
| [dotnet test](dotnet-test.md)       | Ejecuta pruebas usando un ejecutor de pruebas.                                     |

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

| Comando                             | Función                                                            |
| ----------------------------------- | ------------------------------------------------------------------- |
| [dotnet build](dotnet-build.md)     | Compila una aplicación .NET Core.                                     |
| [dotnet clean](dotnet-clean.md)     | Limpia las salidas de la compilación.                                              |
| [dotnet migrate](dotnet-migrate.md) | Migra un proyecto de Preview 2 válido a un proyecto del SDK 1.0 de .NET Core.  |
| [dotnet msbuild](dotnet-msbuild.md) | Proporciona acceso a la línea de comandos de MSBuild.                        |
| [dotnet new](dotnet-new.md)         | Inicializa un proyecto de C# o F# para una plantilla determinada.                |
| [dotnet pack](dotnet-pack.md)       | Crea un paquete de NuGet de su código.                               |
| [dotnet publish](dotnet-publish.md) | Publica una aplicación dependiente del maco .NET o autocontenida. |
| [dotnet restore](dotnet-restore.md) | Restaura las dependencias de una aplicación determinada.                  |
| [dotnet run](dotnet-run.md)         | Ejecuta la aplicación desde el origen.                                   |
| [dotnet sln](dotnet-sln.md)         | Opciones para agregar, quitar y mostrar proyectos en un archivo de solución.       |
| [dotnet test](dotnet-test.md)       | Ejecuta pruebas usando un ejecutor de pruebas.                                     |

---

### <a name="project-references"></a>Referencias de proyecto

Comando | Función
--- | ---
[dotnet add reference](dotnet-add-reference.md) | Agrega una referencia de proyecto.
[dotnet list reference](dotnet-list-reference.md) | Enumera referencias de proyecto.
[dotnet remove reference](dotnet-remove-reference.md) | Quita una referencia de proyecto.

### <a name="nuget-packages"></a>Paquetes NuGet

Comando | Función
--- | ---
[dotnet add package](dotnet-add-package.md) | Agrega un paquete NuGet.
[dotnet remove package](dotnet-remove-package.md) | Quita un paquete NuGet.

### <a name="nuget-commands"></a>Comandos NuGet

Comando | Función
--- | ---
[dotnet nuget delete](dotnet-nuget-delete.md) | Elimina o quita de la lista un paquete del servidor.
[dotnet nuget locals](dotnet-nuget-locals.md) | Borra o muestra los recursos de NuGet locales, como la caché de solicitudes http, la caché temporal o la carpeta de paquetes global de toda la máquina.
[dotnet nuget push](dotnet-nuget-push.md) | Inserta un paquete en el servidor y lo publica.

### <a name="global-tools-commands"></a>Comandos de herramientas globales

Las [herramientas globales de .NET Core](global-tools.md) están disponibles a partir del SDK de .NET Core 2.1.300:

Comando | Función
--- | ---
[dotnet tool install](dotnet-tool-install.md) | Instala una herramienta global en su equipo.
[dotnet tool list](dotnet-tool-list.md) | Enumera todas las herramientas globales instaladas actualmente en el directorio predeterminado de la máquina o en la ruta especificada.
[dotnet tool uninstall](dotnet-tool-uninstall.md) | Desinstala una herramienta global de su equipo.
[dotnet tool update](dotnet-tool-update.md) | Actualiza una herramienta global en su equipo.

### <a name="additional-tools"></a>Herramientas adicionales

A partir del SDK de .NET Core 2.1.300, una serie de herramientas que estaban disponibles solo en función del proyecto mediante `DotnetCliToolReference` ahora están disponibles como parte del SDK de .NET Core. Estas herramientas incluyen:

| Herramienta                                              | Función                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| dev-certs                                         | Crea y administra certificados de desarrollo.                |
| [ef](/ef/core/miscellaneous/cli/dotnet)           | Herramientas de línea de comandos de Entity Framework Core.                    |
| sql-cache                                         | Herramientas de línea de comandos de la caché de SQL Server.                         |
| [user-secrets](/aspnet/core/security/app-secrets) | Administra los secretos del usuario de desarrollo.                            |
| [watch](/aspnet/core/tutorials/dotnet-watch)      | Inicia un monitor de archivos que ejecuta un comando cuando cambian los archivos. |

Para obtener más información sobre cada herramienta, ejecute `dotnet <tool-name> --help`.

## <a name="examples"></a>Ejemplos

Crea una aplicación de consola de .NET Core:

`dotnet new console`

Restauración de dependencias de una aplicación determinada:

`dotnet restore`

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

Compilación de un proyecto y sus dependencias en un directorio determinado:

`dotnet build`

Ejecuta una aplicación dependiente del marco denominada `myapp.dll`:

`dotnet myapp.dll`

## <a name="environment-variables"></a>Variables de entorno

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)

`DOTNET_PACKAGES`

La caché del paquete principal. Si no se establece, el valor predeterminado es `$HOME/.nuget/packages` en Unix o `%HOME%\NuGet\Packages` en Windows.

`DOTNET_SERVICING`

Especifica la ubicación del índice de mantenimiento que usará el host compartido al cargar el entorno de tiempo de ejecución.

`DOTNET_CLI_TELEMETRY_OPTOUT`

Especifica si se recopilan datos sobre el uso de herramientas de .NET Core y se envían a Microsoft. Establézcalo en `true` para no participar de la característica de la telemetría (se aceptan los valores `true`, `1` o `yes`). De lo contrario, establézcalo en `false` para participar de la característica de la telemetría (se aceptan los valores `false`, `0` o `no`). Si no se establece, el valor predeterminado es `false`, y la característica de telemetría está activa.

`DOTNET_MULTILEVEL_LOOKUP`

Especifica si desde la ubicación global se resuelve .NET Core Runtime, el marco de trabajo compartido o el SDK. Si no se establece, el valor predeterminado es `true`. Se establece en `false` para no resolverse desde la ubicación global y tener instalaciones de .NET Core aisladas (se aceptan los valores `0` o `false`). Para más información sobre las búsquedas de varios niveles, vea [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md) (Búsqueda SharedFX de varios niveles).

`DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX`

Deshabilita la puesta al día de versiones secundarias. Para obtener más información, vea [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward) (Puesta al día).

# <a name="net-core-20tabnetcore20"></a>[.NET Core 2.0](#tab/netcore20)

`DOTNET_PACKAGES`

La caché del paquete principal. Si no se establece, el valor predeterminado es `$HOME/.nuget/packages` en Unix o `%HOME%\NuGet\Packages` en Windows.

`DOTNET_SERVICING`

Especifica la ubicación del índice de mantenimiento que usará el host compartido al cargar el entorno de tiempo de ejecución.

`DOTNET_CLI_TELEMETRY_OPTOUT`

Especifica si se recopilan datos sobre el uso de herramientas de .NET Core y se envían a Microsoft. Establézcalo en `true` para no participar de la característica de la telemetría (se aceptan los valores `true`, `1` o `yes`). De lo contrario, establézcalo en `false` para participar de la característica de la telemetría (se aceptan los valores `false`, `0` o `no`). Si no se establece, el valor predeterminado es `false`, y la característica de telemetría está activa.

`DOTNET_MULTILEVEL_LOOKUP`

Especifica si desde la ubicación global se resuelve .NET Core Runtime, el marco de trabajo compartido o el SDK. Si no se establece, el valor predeterminado es `true`. Se establece en `false` para no resolverse desde la ubicación global y tener instalaciones de .NET Core aisladas (se aceptan los valores `0` o `false`). Para más información sobre las búsquedas de varios niveles, vea [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md) (Búsqueda SharedFX de varios niveles).

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

`DOTNET_PACKAGES`

La caché del paquete principal. Si no se establece, el valor predeterminado es `$HOME/.nuget/packages` en Unix o `%HOME%\NuGet\Packages` en Windows.

`DOTNET_SERVICING`

Especifica la ubicación del índice de mantenimiento que usará el host compartido al cargar el entorno de tiempo de ejecución.

`DOTNET_CLI_TELEMETRY_OPTOUT`

Especifica si se recopilan datos sobre el uso de herramientas de .NET Core y se envían a Microsoft. Establézcalo en `true` para no participar de la característica de la telemetría (se aceptan los valores `true`, `1` o `yes`). De lo contrario, establézcalo en `false` para participar de la característica de la telemetría (se aceptan los valores `false`, `0` o `no`). Si no se establece, el valor predeterminado es `false`, y la característica de telemetría está activa.

---
