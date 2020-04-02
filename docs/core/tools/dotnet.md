---
title: comando dotnet
description: Aprenda sobre el comando dotnet (el controlador genérico para la CLI de .NET Core) y su uso.
ms.date: 02/13/2020
ms.openlocfilehash: 8692d419afd528bf49e1dc7dc1a7a5fd698b363b
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2020
ms.locfileid: "80134070"
---
# <a name="dotnet-command"></a>comando dotnet

**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.1 y versiones posteriores

## <a name="name"></a>NOMBRE

`dotnet`: controlador genérico de la CLI de .NET Core.

## <a name="synopsis"></a>Sinopsis

Para obtener información sobre los comandos disponibles y el entorno:

```dotnetcli
dotnet [-h|--help] [--version] [--info]
    [--list-runtimes] [--list-sdks]
```

Para ejecutar un comando (se requiere la instalación de un SDK):

```dotnetcli
dotnet <COMMAND> [-d|--diagnostics] [-h|--help] [--verbosity]
    [command-options] [arguments]
```

Para ejecutar una aplicación:

```dotnetcli
dotnet [--additionalprobingpath] [--additional-deps]
    [--fx-version]  [--roll-forward]
    <PATH_TO_APPLICATION> [arguments]

dotnet exec [--additionalprobingpath] [--additional-deps]
    [--fx-version]  [--roll-forward]
    <PATH_TO_APPLICATION> [arguments]
```

`--roll-forward` está disponible a partir de .NET Core 3.x. En .NET Core 2.x, use `--roll-forward-on-no-candidate-fx`.

## <a name="description"></a>Descripción

El comando `dotnet` tiene dos funciones:

- Proporciona comandos para trabajar con proyectos de .NET Core.

  Por ejemplo, [`dotnet build`](dotnet-build.md) compila un proyecto. Cada comando define sus propias opciones y argumentos. Todos los comandos admiten la opción `--help` para ver una breve documentación sobre cómo usar el comando.

- Ejecuta aplicaciones de .NET Core.

  Hay que especificar la ruta de acceso al archivo `.dll` de una aplicación para poder ejecutarla. Por ejemplo, `dotnet myapp.dll` ejecuta la aplicación `myapp`. Vea [Implementación de aplicaciones .NET Core](../deploying/index.md) para obtener más información sobre las opciones de implementación.

## <a name="options"></a>Opciones

Existen distintas opciones disponibles para usar `dotnet` por sí mismo, para ejecutar un comando y para ejecutar una aplicación.

### <a name="options-for-dotnet-by-itself"></a>Opciones de dotnet por sí mismo

Las siguientes opciones son para usar `dotnet` por sí mismo. Por ejemplo: `dotnet --info`. Muestran información sobre el entorno.

- **`--info`**

  Imprime información detallada sobre una instalación de .NET Core y el entorno informático, por ejemplo, el sistema operativo actual y el SHA de confirmación de la versión de .NET Core.

- **`--version`**

  Imprime la versión del SDK de .NET Core en uso.

- **`--list-runtimes`**

  Muestra una lista de los runtime de .NET Core instalados.

- **`--list-sdks`**

  Muestra una lista de los SDK de .NET Core instalados.

- **`-h|--help`**

  Muestra una lista de los comandos disponibles.

### <a name="sdk-options-for-running-a-command"></a>Opciones de SDK para ejecutar un comando

Las siguientes opciones son para usar `dotnet` con un comando. Por ejemplo: `dotnet build --help`.

- **`-d|--diagnostics`**

  Habilita la salida de diagnóstico.

- **`-v|--verbosity <LEVEL>`**

  Establece el nivel de detalle del comando. Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`. Estos no se admiten en todos los comandos. Vea la página específica de cada comando para asegurarse de que la opción está disponible.

- **`-h|--help`**

  Imprime la documentación de un comando determinado, como `dotnet build --help`.

- **`command options`**

  Cada comando define opciones específicas de ese comando. Vea la página de comandos específica para obtener una lista de las opciones disponibles.

### <a name="runtime-options"></a>Definición de tiempo de ejecución

Las siguientes opciones están disponibles cuando `dotnet` ejecuta una aplicación. Por ejemplo: `dotnet myapp.dll --fx-version 3.1.1`.

- **`--additionalprobingpath <PATH>`**

  Ruta de acceso que contiene directivas de sondeo y ensamblados para sondear.

- **`--additional-deps <PATH>`**

  Ruta de acceso a un archivo *.deps.json* adicional. Un archivo *deps.json* contiene una lista de dependencias, dependencias de compilación e información de versión que se usa para resolver conflictos de ensamblado. Para más información, vea [Runtime Configuration Files (Archivos de configuración en tiempo de ejecución)](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md) en GitHub.

- **`--fx-version <VERSION>`**

  Versión del runtime de .NET Core que se va a usar para ejecutar la aplicación.

- **`--runtimeconfig`**

  Ruta de acceso a un archivo *runtimeconfig.json*. Un archivo *runtimeconfig.json* es un archivo de configuración que contiene opciones de configuración en tiempo de ejecución. Para obtener más información, vea [Opciones de configuración en tiempo de ejecución de .NET Core](../run-time-config/index.md#runtimeconfigjson).

- **`--roll-forward-on-no-candidate-fx <N>`** **Disponible en el SDK de .NET Core 2.x.**

  Define el comportamiento cuando el marco de trabajo compartido necesario no está disponible. `N` puede ser:

  - `0`: se deshabilita la puesta al día incluso de las versiones secundarias.
  - `1`: puesta al día de la versión secundaria, pero no de la versión principal. Éste es el comportamiento predeterminado.
  - `2`: puesta al día de las versiones principales y secundarias.

   Para obtener más información, vea [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward) (Puesta al día).

- **`--roll-forward <SETTING>`** **Disponible a partir del SDK de .NET Core 3.0.**

  Controla cómo se aplica la puesta al día en la aplicación. `SETTING` puede tener uno de los valores siguientes. Si no se especifica, el valor predeterminado es `Minor`.

  - `LatestPatch`: la aplicación se pone al día con la última versión de revisión. Se deshabilita la puesta al día de versiones secundarias.
  - `Minor`: la aplicación se pone al día con la versión secundaria mínima superior, si no se encuentra la versión secundaria solicitada. Si se encuentra la versión secundaria solicitada, se utiliza la directiva LatestPatch.
  - `Major`: la aplicación se pone al día con la versión secundaria mínima superior, y con la versión secundaria mínima si no se encuentra la versión secundaria solicitada. Si se encuentra la versión principal solicitada, se utiliza la directiva Minor.
  - `LatestMinor`: la aplicación e pone al día con la última versión secundaria, aunque la versión secundaria solicitada esté presente. Se destina a escenarios de hospedaje de componentes.
  - `LatestMajor`: la aplicación se pone al día con la última versión principal y la última versión secundaria, aunque la versión principal solicitada esté presente. Se destina a escenarios de hospedaje de componentes.
  - `Disable`: la aplicación no se pone al día. Solo se enlaza a la versión especificada. No se recomienda esta directiva para uso general, ya que deshabilita la capacidad de puesta al día con las revisiones más recientes. Este valor solo se recomienda a efectos de pruebas.

A excepción de `Disable`, todos los valores usarán la última versión de revisión disponible.

El comportamiento de puesta al día también se puede configurar en una propiedad de archivo de proyecto, en una propiedad de archivo de configuración de runtime y en una variable de entorno. Para obtener más información, vea [Puesta al día del runtime de versiones principales](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward).

## <a name="dotnet-commands"></a>comandos de dotnet

### <a name="general"></a>General

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
[dotnet nuget push](dotnet-nuget-push.md) | Inserta un paquete en el servidor y lo publica.
[dotnet nuget locals](dotnet-nuget-locals.md) | Borra o muestra los recursos de NuGet locales, como la caché de solicitudes http, la caché temporal o la carpeta de paquetes global de toda la máquina.
[dotnet nuget add source](dotnet-nuget-add-source.md) | Agrega un origen de NuGet.
[dotnet nuget disable source](dotnet-nuget-disable-source.md) | Deshabilita un origen de NuGet.
[dotnet nuget enable source](dotnet-nuget-enable-source.md) | Habilita un origen de NuGet.
[dotnet nuget list source](dotnet-nuget-list-source.md) | Enumera todos los orígenes de NuGet configurados.
[dotnet nuget remove source](dotnet-nuget-remove-source.md) | Quita un origen de NuGet.
[dotnet nuget update source](dotnet-nuget-update-source.md) | Actualiza un origen de NuGet.

### <a name="global-tool-path-and-local-tools-commands"></a>Comandos de herramientas locales, globales y de ruta de acceso de herramientas

Las herramientas son aplicaciones de consola que se instalan mediante paquetes NuGet y se invocan desde el símbolo del sistema. Puede encargarse de escribir las herramientas o instalar las escritas por terceros. Las herramientas también se denominan herramientas globales, herramientas de ruta de acceso de herramientas y herramientas locales. Para obtener más información, vea [Información general sobre las herramientas de .NET Core](global-tools.md). Las herramientas globales y de ruta de acceso de herramientas están disponibles a partir del SDK de .NET Core 2.1. Las herramientas locales están disponibles a partir del SDK de .NET Core 3.0.

Comando | Función
--- | ---
[dotnet tool install](dotnet-tool-install.md) | Instala una herramienta en el equipo.
[dotnet tool list](dotnet-tool-list.md) | Muestra todas las herramientas globales, de ruta de acceso de herramientas o locales instaladas actualmente en el equipo.
[dotnet tool uninstall](dotnet-tool-uninstall.md) | Desinstala una herramienta del equipo.
[dotnet tool update](dotnet-tool-update.md) | Actualiza una herramienta que está instalada en el equipo.

### <a name="additional-tools"></a>Herramientas adicionales

A partir del SDK de .NET Core 2.1.300, una serie de herramientas que estaban disponibles solo en función del proyecto mediante `DotnetCliToolReference` ahora están disponibles como parte del SDK de .NET Core. Estas herramientas se muestran en la tabla siguiente:

| Herramienta                                              | Función                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| dev-certs                                         | Crea y administra certificados de desarrollo.                |
| [ef](/ef/core/miscellaneous/cli/dotnet)           | Herramientas de línea de comandos de Entity Framework Core.                    |
| sql-cache                                         | Herramientas de línea de comandos de la caché de SQL Server.                         |
| [user-secrets](/aspnet/core/security/app-secrets) | Administra los secretos del usuario de desarrollo.                            |
| [watch](/aspnet/core/tutorials/dotnet-watch)      | Inicia un monitor de archivos que ejecuta un comando cuando cambian los archivos. |

Para obtener más información sobre cada herramienta, escriba `dotnet <tool-name> --help`.

## <a name="examples"></a>Ejemplos

Cree una aplicación de consola de .NET Core:

```dotnetcli
dotnet new console
```

Compilación de un proyecto y sus dependencias en un directorio determinado:

```dotnetcli
dotnet build
```

Ejecute una aplicación:

```dotnetcli
dotnet myapp.dll
```

## <a name="environment-variables"></a>Variables de entorno

- `DOTNET_ROOT`, `DOTNET_ROOT(x86)`

  Especifica la ubicación de los runtime de .NET Core, si no están instalados en la ubicación predeterminada. La ubicación predeterminada en Windows es `C:\Program Files\dotnet`. La ubicación predeterminada en Linux y macOS es `/usr/share/dotnet`. Esta variable de entorno solo se usa cuando se ejecutan aplicaciones a través de archivos ejecutables generados (hosts de aplicaciones). `DOTNET_ROOT(x86)` se usa en su lugar cuando se ejecuta un archivo ejecutable de 32 bits en un sistema operativo de 64 bits.

- `DOTNET_PACKAGES`

  La carpeta de paquetes globales. Si no se establece, el valor predeterminado es `~/.nuget/packages` en Unix o `%userprofile%\.nuget\packages` en Windows.

- `DOTNET_SERVICING`

  Especifica la ubicación del índice de mantenimiento que usará el host compartido al cargar el entorno de tiempo de ejecución.

- `DOTNET_NOLOGO`

  Especifica si los mensajes de bienvenida y de telemetría de .NET Core se muestran en la primera ejecución. Establézcala en `true` para silenciar estos mensajes (valores `true`, `1` o `yes` aceptados) o en `false` para permitirlos (valores `false`, `0` o `no` aceptados). Si no se establece, el valor predeterminado es `false` y los mensajes se mostrarán en la primera ejecución. Tenga en cuenta que esta marca no tiene ningún efecto en la telemetría (consulte `DOTNET_CLI_TELEMETRY_OPTOUT` para excluirse del envío de telemetría).

- `DOTNET_CLI_TELEMETRY_OPTOUT`

  Especifica si se recopilan datos sobre el uso de herramientas de .NET Core y se envían a Microsoft. Establézcalo en `true` para no participar de la característica de la telemetría (se aceptan los valores `true`, `1` o `yes`). De lo contrario, establézcalo en `false` para participar de la característica de la telemetría (se aceptan los valores `false`, `0` o `no`). Si no se establece, el valor predeterminado es `false`, y la característica de telemetría está activa.

- `DOTNET_MULTILEVEL_LOOKUP`

  Especifica si desde la ubicación global se resuelve .NET Core Runtime, el marco de trabajo compartido o el SDK. Si no se define, establece el valor predeterminado de 1 (`true` lógico). Establézcalo en 0 (`false` lógico) para no resolver desde la ubicación global y tener instalaciones de .NET Core aisladas. Para más información sobre las búsquedas de varios niveles, vea [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md) (Búsqueda SharedFX de varios niveles).

- `DOTNET_ROLL_FORWARD` **Disponible a partir del SDK de .NET Core 3.x.**

  Determina el comportamiento de puesta al día. Para obtener más información, vea la opción `--roll-forward` más arriba en este mismo artículo.

- `DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX` **Disponible en el SDK de .NET Core 2.x.**

  Deshabilita la puesta al día de versiones secundarias, si está establecido en `0`. Para obtener más información, vea [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward) (Puesta al día).

- `DOTNET_CLI_UI_LANGUAGE`

  Establece el idioma de la interfaz de usuario de la CLI mediante un valor de configuración regional como `en-us`. Los valores admitidos son los mismos que en Visual Studio. Para obtener más información, vea la sección sobre cómo cambiar el idioma del instalador en la [documentación de instalación de Visual Studio](https://docs.microsoft.com/visualstudio/install/install-visual-studio?view=vs-2019). Se aplican las reglas del administrador de recursos de .NET, por lo que no hay que elegir una coincidencia exacta&mdash;(también se pueden elegir descendientes en el árbol `CultureInfo`). Por ejemplo, si se establece en `fr-CA`, la CLI buscará y usará las traducciones de `fr`. Si se establece en un idioma que no se admite, la CLI revertirá al inglés.

- `DOTNET_DISABLE_GUI_ERRORS`

  En el caso de los archivos ejecutables generados habilitados para GUI, se deshabilita el cuadro de diálogo emergente que suele aparecer con ciertos tipos de errores. Solo escribe en `stderr` y se cierra en esos casos.
  
- `DOTNET_ADDITIONAL_DEPS`

  Equivale a la opción `--additional-deps` de la CLI.

- `DOTNET_RUNTIME_ID`

  Invalida el RID detectado.

- `DOTNET_SHARED_STORE`

  Ubicación del "almacén compartido" a la que la resolución de ensamblado revierte en algunos casos.

- `DOTNET_STARTUP_HOOKS`

  Lista de ensamblados de los que cargar y ejecutar enlaces de inicio.

- `COREHOST_TRACE`, `COREHOST_TRACEFILE`, `COREHOST_TRACE_VERBOSITY`

  Controla el seguimiento de diagnósticos de los componentes de hospedaje, como `dotnet.exe`, `hostfxr` y `hostpolicy`.

## <a name="see-also"></a>Vea también

- [Runtime Configuration Files (Archivos de configuración en tiempo de ejecución)](https://github.com/dotnet/cli/blob/master/Documentation/specs/runtime-configuration-file.md)
- [Opciones de configuración en tiempo de ejecución de .NET Core](../run-time-config/index.md)
