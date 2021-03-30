---
title: comando dotnet
description: Obtenga información sobre el comando dotnet (el controlador genérico para la CLI de .NET) y su uso.
ms.date: 11/11/2020
ms.openlocfilehash: 33c5f9d22166b818f5c860c4f4632d359f686919
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104874542"
---
# <a name="dotnet-command"></a>comando dotnet

**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.1 y versiones posteriores

## <a name="name"></a>NOMBRE

`dotnet`: controlador genérico de la CLI de .NET.

## <a name="synopsis"></a>Sinopsis

Para obtener información sobre los comandos disponibles y el entorno:

```dotnetcli
dotnet [--version] [--info] [--list-runtimes] [--list-sdks]

dotnet -h|--help
```

Para ejecutar un comando (se requiere la instalación de un SDK):

```dotnetcli
dotnet <COMMAND> [-d|--diagnostics] [-h|--help] [--verbosity <LEVEL>]
    [command-options] [arguments]
```

Para ejecutar una aplicación:

```dotnetcli
dotnet [--additionalprobingpath <PATH>] [--additional-deps <PATH>]
    [--fx-version <VERSION>]  [--roll-forward <SETTING>]
    <PATH_TO_APPLICATION> [arguments]

dotnet exec [--additionalprobingpath] [--additional-deps <PATH>]
    [--fx-version <VERSION>]  [--roll-forward <SETTING>]
    <PATH_TO_APPLICATION> [arguments]
```

`--roll-forward` está disponible a partir de .NET Core 3.x. En .NET Core 2.x, use `--roll-forward-on-no-candidate-fx`.

## <a name="description"></a>Descripción

El comando `dotnet` tiene dos funciones:

- Proporciona comandos para trabajar con proyectos de .NET.

  Por ejemplo, [`dotnet build`](dotnet-build.md) compila un proyecto. Cada comando define sus propias opciones y argumentos. Todos los comandos admiten la opción `--help` para ver una breve documentación sobre cómo usar el comando.

- Ejecuta aplicaciones de .NET.

  Hay que especificar la ruta de acceso al archivo `.dll` de una aplicación para poder ejecutarla.  Ejecutar la aplicación significa buscar y ejecutar el punto de entrada, que en el caso de las aplicaciones de consola es el método `Main`. Por ejemplo, `dotnet myapp.dll` ejecuta la aplicación `myapp`. Vea [Implementación de aplicaciones de .NET](../deploying/index.md) para obtener información sobre las opciones de implementación.

## <a name="options"></a>Opciones

Existen distintas opciones disponibles para usar `dotnet` por sí mismo, para ejecutar un comando y para ejecutar una aplicación.

### <a name="options-for-dotnet-by-itself"></a>Opciones de dotnet por sí mismo

Las siguientes opciones son para usar `dotnet` por sí mismo. Por ejemplo: `dotnet --info`. Muestran información sobre el entorno.

- **`--info`**

  Imprime información detallada sobre una instalación de .NET y el entorno del equipo, por ejemplo, el sistema operativo actual y el SHA de confirmación de la versión de .NET.

- **`--version`**

  Imprime la versión del SDK de .NET en uso.

- **`--list-runtimes`**

  Imprime una lista de los entornos de ejecución de .NET instalados. Una versión x86 del SDK muestra solo los runtime x86 y una versión x64 solo los runtime x64.

- **`--list-sdks`**

  Imprime una lista de los SDK de .NET instalados.

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

Las siguientes opciones están disponibles cuando `dotnet` ejecuta una aplicación. Por ejemplo: `dotnet myapp.dll --roll-forward Major`.

- **`--additionalprobingpath <PATH>`**

  Ruta de acceso que contiene directivas de sondeo y ensamblados para sondear.

- **`--additional-deps <PATH>`**

  Ruta de acceso a un archivo *.deps.json* adicional. Un archivo *deps.json* contiene una lista de dependencias, dependencias de compilación e información de versión que se usa para resolver conflictos de ensamblado. Para más información, vea [Runtime Configuration Files (Archivos de configuración en tiempo de ejecución)](https://github.com/dotnet/sdk/blob/main/documentation/specs/runtime-configuration-file.md) en GitHub.

- **`--depsfile <PATH_TO_DEPSFILE>`**

  Ruta de acceso al archivo *deps.json*. Un archivo *deps.json* es un archivo de configuración que contiene información sobre las dependencias necesarias para ejecutar la aplicación. El SDK de .NET genera este archivo.

- **`--runtimeconfig`**

  Ruta de acceso a un archivo *runtimeconfig.json*. Un archivo *runtimeconfig.json* es un archivo de configuración que contiene opciones de configuración en tiempo de ejecución. Para obtener más información, vea [Opciones de configuración en tiempo de ejecución de .NET Core](../run-time-config/index.md#runtimeconfigjson).

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

- **`--roll-forward-on-no-candidate-fx <N>`** **Disponible en el SDK de .NET Core 2.x.**

  Define el comportamiento cuando el marco de trabajo compartido necesario no está disponible. `N` puede ser:

  - `0`: se deshabilita la puesta al día incluso de las versiones secundarias.
  - `1`: puesta al día de la versión secundaria, pero no de la versión principal. Éste es el comportamiento predeterminado.
  - `2`: puesta al día de las versiones principales y secundarias.

  Para obtener más información, vea [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward) (Puesta al día).

  A partir de .NET Core 3.0, esta opción se sustituye por `--roll-forward` y es la que debe usarse.

- **`--fx-version <VERSION>`**

  Versión del entorno de ejecución de .NET que se va a usar para ejecutar la aplicación.

  Esta opción reemplaza la versión de la primera referencia de marco en el archivo `.runtimeconfig.json` de la aplicación. Esto significa que solo funciona según lo esperado si solo hay una referencia de marco. Si la aplicación tiene más de una referencia de marco, el uso de esta opción puede hacer que se produzcan errores.

## <a name="dotnet-commands"></a>comandos de dotnet

### <a name="general"></a>General

| Comando                                       | Función                                                            |
| --------------------------------------------- | ------------------------------------------------------------------- |
| [dotnet build](dotnet-build.md)               | Compila una aplicación de .NET.                                     |
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

Las herramientas son aplicaciones de consola que se instalan mediante paquetes NuGet y se invocan desde el símbolo del sistema. Puede encargarse de escribir las herramientas o instalar las escritas por terceros. Las herramientas también se denominan herramientas globales, herramientas de ruta de acceso de herramientas y herramientas locales. Para obtener más información, vea la [información general sobre las herramientas de .NET](global-tools.md). Las herramientas globales y de ruta de acceso de herramientas están disponibles a partir del SDK de .NET Core 2.1. Las herramientas locales están disponibles a partir del SDK de .NET Core 3.0.

Comando | Función
--- | ---
[dotnet tool install](dotnet-tool-install.md) | Instala una herramienta en el equipo.
[dotnet tool list](dotnet-tool-list.md) | Muestra todas las herramientas globales, de ruta de acceso de herramientas o locales instaladas actualmente en el equipo.
[dotnet tool search](dotnet-tool-list.md) | Busca en NuGet.org herramientas que tengan el término de búsqueda especificado en el nombre o los metadatos.
[dotnet tool uninstall](dotnet-tool-uninstall.md) | Desinstala una herramienta del equipo.
[dotnet tool update](dotnet-tool-update.md) | Actualiza una herramienta que está instalada en el equipo.

### <a name="additional-tools"></a>Herramientas adicionales

A partir del SDK de .NET Core 2.1.300, una serie de herramientas que estaban disponibles solo en función del proyecto mediante `DotnetCliToolReference` ahora están disponibles como parte del SDK de .NET. Estas herramientas se muestran en la tabla siguiente:

| Herramienta                                              | Función                                                     |
| ------------------------------------------------- | ------------------------------------------------------------ |
| dev-certs                                         | Crea y administra certificados de desarrollo.                |
| [ef](/ef/core/miscellaneous/cli/dotnet)           | Herramientas de línea de comandos de Entity Framework Core.                    |
| sql-cache                                         | Herramientas de línea de comandos de la caché de SQL Server.                         |
| [user-secrets](/aspnet/core/security/app-secrets) | Administra los secretos del usuario de desarrollo.                            |
| [watch](/aspnet/core/tutorials/dotnet-watch)      | Inicia un monitor de archivos que ejecuta un comando cuando cambian los archivos. |

Para obtener más información sobre cada herramienta, escriba `dotnet <tool-name> --help`.

## <a name="examples"></a>Ejemplos

Creación de una aplicación de consola de .NET:

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

  Especifica la ubicación de los entornos de ejecución de .NET, si no están instalados en la ubicación predeterminada. La ubicación predeterminada en Windows es `C:\Program Files\dotnet`. La ubicación predeterminada en Linux y macOS es `/usr/share/dotnet`. Esta variable de entorno solo se usa cuando se ejecutan aplicaciones a través de archivos ejecutables generados (hosts de aplicaciones). `DOTNET_ROOT(x86)` se usa en su lugar cuando se ejecuta un archivo ejecutable de 32 bits en un sistema operativo de 64 bits.

- `NUGET_PACKAGES`

  La carpeta de paquetes globales. Si no se establece, el valor predeterminado es `~/.nuget/packages` en Unix o `%userprofile%\.nuget\packages` en Windows.

- `DOTNET_SERVICING`

  Especifica la ubicación del índice de mantenimiento que usará el host compartido al cargar el entorno de tiempo de ejecución.

- `DOTNET_NOLOGO`

  Especifica si los mensajes de bienvenida y telemetría de .NET se muestran en la primera ejecución. Establézcala en `true` para silenciar estos mensajes (valores `true`, `1` o `yes` aceptados) o en `false` para permitirlos (valores `false`, `0` o `no` aceptados). Si no se establece, el valor predeterminado es `false` y los mensajes se mostrarán en la primera ejecución. Esta marca no tiene ningún efecto en la telemetría (consulte `DOTNET_CLI_TELEMETRY_OPTOUT` para excluirse del envío de telemetría).

- `DOTNET_CLI_TELEMETRY_OPTOUT`

  Especifica si se recopilan datos sobre el uso de herramientas de .NET y se envían a Microsoft. Establézcalo en `true` para no participar de la característica de la telemetría (se aceptan los valores `true`, `1` o `yes`). De lo contrario, establézcalo en `false` para participar de la característica de la telemetría (se aceptan los valores `false`, `0` o `no`). Si no se establece, el valor predeterminado es `false`, y la característica de telemetría está activa.

- `DOTNET_MULTILEVEL_LOOKUP`

  Especifica si desde la ubicación global se resuelve el entorno de ejecución de .NET, el marco compartido o el SDK. Si no se define, establece el valor predeterminado de 1 (`true` lógico). Establézcalo en 0 (`false` lógico) para no resolver desde la ubicación global y tener instalaciones de .NET aisladas. Para más información sobre las búsquedas de varios niveles, vea [Multi-level SharedFX Lookup](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/multilevel-sharedfx-lookup.md) (Búsqueda SharedFX de varios niveles).

- `DOTNET_ROLL_FORWARD` **Disponible a partir de .NET Core 3.x.**

  Determina el comportamiento de puesta al día. Para obtener más información, vea la opción `--roll-forward` más arriba en este mismo artículo.

- `DOTNET_ROLL_FORWARD_TO_PRERELEASE` **Disponible a partir de .NET Core 3.x.**

  Si se establece en `1` (habilitado), permite la puesta al día a una versión preliminar desde una versión de lanzamiento. De forma predeterminada (`0`: deshabilitado), cuando se solicita una versión de lanzamiento del entorno de ejecución de .NET, la puesta al día solo tendrá en cuenta las versiones de lanzamiento instaladas.

  Para obtener más información, vea [Roll forward](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward) (Puesta al día).

- `DOTNET_ROLL_FORWARD_ON_NO_CANDIDATE_FX` **Disponible en .NET Core 2.x.**

  Deshabilita la puesta al día de versiones secundarias, si está establecido en `0`. Para obtener más información, vea [Roll forward](../whats-new/dotnet-core-2-1.md#roll-forward) (Puesta al día).

  Este valor se ha sustituido en .NET Core 3.0 por `DOTNET_ROLL_FORWARD`, y esta es la configuración que debe usarse.

- `DOTNET_CLI_UI_LANGUAGE`

  Establece el idioma de la interfaz de usuario de la CLI mediante un valor de configuración regional como `en-us`. Los valores admitidos son los mismos que en Visual Studio. Para obtener más información, vea la sección sobre cómo cambiar el idioma del instalador en la [documentación de instalación de Visual Studio](/visualstudio/install/install-visual-studio). Se aplican las reglas del administrador de recursos de .NET, por lo que no hay que elegir una coincidencia exacta&mdash;(también se pueden elegir descendientes en el árbol `CultureInfo`). Por ejemplo, si se establece en `fr-CA`, la CLI buscará y usará las traducciones de `fr`. Si se establece en un idioma que no se admite, la CLI revertirá al inglés.

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

- `DOTNET_BUNDLE_EXTRACT_BASE_DIR` **Disponible a partir de .NET Core 3.x.**

  Especifica un directorio en el que se extrae una aplicación de un solo archivo antes de ejecutarse.

  Para más información, consulte [Archivos ejecutables de único archivo](../whats-new/dotnet-core-3-0.md#single-file-executables).

- `COREHOST_TRACE`, `COREHOST_TRACEFILE`, `COREHOST_TRACE_VERBOSITY`

  Controla el seguimiento de diagnósticos de los componentes de hospedaje, como `dotnet.exe`, `hostfxr` y `hostpolicy`.

  * `COREHOST_TRACE=[0/1]`: el valor predeterminado es `0` (el seguimiento está deshabilitado). Si se establece en `1`, se habilita el seguimiento de diagnósticos.
  * `COREHOST_TRACEFILE=<file path>`: solo tiene efecto si el seguimiento se habilita a través de `COREHOST_TRACE=1`. Cuando se establece, la información de seguimiento se escribe en el archivo especificado; en caso contrario, la información de seguimiento se escribe en `stderr`. **Disponible a partir de .NET Core 3.x.**
  * `COREHOST_TRACE_VERBOSITY=[1/2/3/4]`: el valor predeterminado es `4`. La configuración solo se usa cuando el seguimiento está habilitado a través de `COREHOST_TRACE=1`. **Disponible a partir de .NET Core 3.x.**
    * `4`: se escribe toda la información de seguimiento.
    * `3`: solo se escriben mensajes informativos, de advertencia y de error.
    * `2`: solo se escriben mensajes de advertencia y de error.
    * `1`: solo se escriben mensajes de error.

  La forma habitual de obtener información de seguimiento detallada sobre el inicio de la aplicación es establecer `COREHOST_TRACE=1` y `COREHOST_TRACEFILE=host_trace.txt` y, luego, ejecutar la aplicación. Se creará un nuevo archivo `host_trace.txt` en el directorio actual con la información detallada.

## <a name="see-also"></a>Vea también

- [Runtime Configuration Files (Archivos de configuración en tiempo de ejecución)](https://github.com/dotnet/sdk/blob/main/documentation/specs/runtime-configuration-file.md)
- [Opciones de configuración en tiempo de ejecución de .NET Core](../run-time-config/index.md)
