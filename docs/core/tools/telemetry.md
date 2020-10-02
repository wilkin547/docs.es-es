---
title: Telemetría del SDK de .NET Core
description: Descubra las características de telemetría del SDK de .NET Core que recopilan información de uso para el análisis, qué datos se recopilan y cómo deshabilitarlas.
author: KathleenDollard
ms.date: 08/27/2019
ms.openlocfilehash: bad6de138b9c35bcd8c5556df82103f959508b52
ms.sourcegitcommit: d04388f94dbcd756ffd608536c869aee3242cdb0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91206359"
---
# <a name="net-core-sdk-telemetry"></a>Telemetría del SDK de .NET Core

El [SDK de .NET Core](index.md) incluye una característica de telemetría que recopila datos de uso e información de excepción cuando se bloquea el CLI de .NET Core. El CLI de .NET Core incluye el SDK de .NET Core y es el conjunto de verbos que permiten compilar, probar y publicar las aplicaciones de .NET Core. Es importante que el equipo de .NET entienda cómo se usan las herramientas con el fin de mejorarlas. Con la información sobre los errores, el equipo consigue resolver problemas y corregir errores.

Los datos recopilados se publican de forma agregada bajo la [licencia de atribución de Creative Commons](https://creativecommons.org/licenses/by/4.0/).

## <a name="scope"></a>Ámbito

`dotnet` tiene dos funciones: ejecutar aplicaciones y ejecutar comandos de la CLI. La telemetría *no se recopila* cuando se usa `dotnet` para iniciar una aplicación con el siguiente formato:

- `dotnet [path-to-app].dll`

La telemetría *se recopila* cuando se usa cualquiera de los [comandos de la CLI de .NET Core](index.md), como:

- `dotnet build`
- `dotnet pack`
- `dotnet run`

## <a name="how-to-opt-out"></a>Cómo desactivar la característica

La característica de telemetría del SDK de .NET Core está habilitada de manera predeterminada. Para desactivar la característica de telemetría, establezca la variable de entorno `DOTNET_CLI_TELEMETRY_OPTOUT` en `1` o `true`.

El instalador del SDK de .NET Core también envía una única entrada de telemetría cuando se produce una instalación correcta. Para desactivarla, establezca la variable de entorno de `DOTNET_CLI_TELEMETRY_OPTOUT` antes de instalar el SDK de .NET Core.

## <a name="disclosure"></a>Divulgación

El SDK de .NET Core muestra texto similar al siguiente cuando se ejecuta por primera vez uno de los [comandos de la CLI de .NET Core](index.md) (por ejemplo, `dotnet build`). El texto puede variar ligeramente según la versión del SDK que ejecute. Esta experiencia de "primera vista" es la forma en que Microsoft le notifica sobre la recopilación de datos.

```console
Telemetry
---------
The .NET Core tools collect usage data in order to help us improve your experience. The data is collected by Microsoft and shared with the community. You can opt-out of telemetry by setting the DOTNET_CLI_TELEMETRY_OPTOUT environment variable to '1' or 'true' using your favorite shell.

Read more about .NET Core CLI Tools telemetry: https://aka.ms/dotnet-cli-telemetry
```

Para deshabilitar este mensaje y el mensaje de bienvenida de .NET Core, establezca la variable de entorno `DOTNET_NOLOGO` en `true`. Tenga en cuenta que esta variable no tiene ningún efecto sobre la exclusión de la telemetría.

## <a name="data-points"></a>Puntos de datos

La característica de telemetría no recopila datos personales, como direcciones de correo electrónico o nombres de usuario. No examina el código ni extrae datos de nivel de proyecto, como el nombre, el repositorio o el autor. Los datos se envían de forma segura a los servidores de Microsoft con tecnología de [Azure Monitor](https://azure.microsoft.com/services/monitor/), se conservan bajo acceso restringido y se publican bajo controles de seguridad estrictos de sistemas seguros de [Azure Storage](https://azure.microsoft.com/services/storage/).

La protección de su privacidad es importante para nosotros. Si sospecha que la telemetría está recopilando datos confidenciales o que los datos se están tratando de forma no segura o inapropiada, informe de un problema en el repositorio de [dotnet/cli](https://github.com/dotnet/sdk/issues) o envíenos un correo electrónico a [dotnet@microsoft.com](mailto:dotnet@microsoft.com) para que lo investiguemos.

La característica de telemetría recopila los siguientes datos:

| Versiones del SDK | Datos |
|--------------|------|
| Todas          | Marca de tiempo de la invocación. |
| Todas          | Comando invocado (por ejemplo, "build"), con hash a partir de 2.1. |
| Todas          | Dirección IP de tres octetos usada para determinar la ubicación geográfica. |
| Todas          | Sistema operativo y versión. |
| Todas          | Identificador de tiempo de ejecución (RID) en el que se ejecuta el SDK. |
| Todas          | Versión del SDK de .NET Core. |
| Todas          | Perfil de telemetría: valor opcional usado internamente en Microsoft y que solo se usa con la participación explícita del usuario. |
| >=2.0        | Opciones y argumentos del comando: se recopilan varias opciones y argumentos (no cadenas arbitrarias). Vea [opciones recopiladas](#collected-options). Con hash a partir de la versión 2.1.300. |
| >=2.0         | Si el SDK se ejecuta en un contenedor. |
| >=2.0         | Plataformas de destino (desde el evento `TargetFramework`), con hash a partir de 2.1. |
| >=2.0         | Dirección de Media Access Control (MAC) con hash (SHA256). |
| >=2.0         | Directorio de trabajo actual con hash. |
| >=2.0         | Informe de instalación correcta, con el nombre de archivo exe del instalador con hash. |
| >=2.1.300     | Versión de kernel. |
| >=2.1.300     | Versión/versión de libc. |
| >=3.0.100     | Indica si la salida se redirigió (true o false). |
| >=3.0.100     | En un bloqueo de CLI/SDK, el tipo de excepción y su seguimiento de pila (solo el código de CLI/SDK se incluye en el seguimiento de la pila enviado). Para más información, vea [Telemetría de la excepción de bloqueo de SDK/CLI de .NET Core recopilada](#net-core-clisdk-crash-exception-telemetry-collected). |

### <a name="collected-options"></a>Opciones recopiladas

Determinados comandos envían datos adicionales. Un subconjunto de comandos envía el primer argumento:

| Comando               | Datos del primer argumento enviados                |
|-----------------------|-----------------------------------------|
| `dotnet help <arg>`   | Se está consultando la ayuda del comando.  |
| `dotnet new <arg>`    | Nombre de la plantilla (con hash).             |
| `dotnet add <arg>`    | La palabra `package` o `reference`.      |
| `dotnet remove <arg>` | La palabra `package` o `reference`.      |
| `dotnet list <arg>`   | La palabra `package` o `reference`.      |
| `dotnet sln <arg>`    | La palabra `add`, `list` o `remove`.    |
| `dotnet nuget <arg>`  | La palabra `delete`, `locals` o `push`. |

Un subconjunto de comandos envía las opciones seleccionadas, si se usan, junto con sus valores:

| Opción                  | Comandos                                                                                       |
|-------------------------|------------------------------------------------------------------------------------------------|
| `--verbosity`           | Todos los comandos                                                                                   |
| `--language`            | `dotnet new`                                                                                   |
| `--configuration`       | `dotnet build`, `dotnet clean`, `dotnet publish`, `dotnet run`, `dotnet test`                  |
| `--framework`           | `dotnet build`, `dotnet clean`, `dotnet publish`, `dotnet run`, `dotnet test`, `dotnet vstest` |
| `--runtime`             | `dotnet build`,  `dotnet publish`                                                              |
| `--platform`            | `dotnet vstest`                                                                                |
| `--logger`              | `dotnet vstest`                                                                                |
| `--sdk-package-version` | `dotnet migrate`                                                                               |

A excepción de `--verbosity` y `--sdk-package-version`, se aplica un algoritmo hash a los demás valores a partir del SDK de .NET Core 2.1.100.

## <a name="net-core-clisdk-crash-exception-telemetry-collected"></a>Telemetría de la excepción de bloqueo de SDK/CLI de .NET Core recopilada

Si el SDK/CLI de .NET Core se bloquea, se recopila el nombre de la excepción y el seguimiento de la pila del código de CLI/SDK. Esta información se recopila para evaluar los problemas y mejorar la calidad del SDK de .NET Core y la CLI. En este artículo se proporciona información sobre los datos que se recopilan. También se ofrecen sugerencias para que los usuarios que compilan su propia versión del SDK de .NET Core eviten la divulgación involuntaria de información personal o confidencial.

### <a name="types-of-collected-data"></a>Tipos de datos recopilados

El CLI de .NET Core recopila información solo de las excepciones de CLI/SDK, pero no de las excepciones de la aplicación. Los datos recopilados contienen el nombre de la excepción y el seguimiento de la pila. Este seguimiento de la pila es del código de CLI/SDK.

En este ejemplo se muestra el tipo de datos que se recopilan:

```console
System.IO.IOException
at System.ConsolePal.WindowsConsoleStream.Write(Byte[] buffer, Int32 offset, Int32 count)
at System.IO.StreamWriter.Flush(Boolean flushStream, Boolean flushEncoder)
at System.IO.StreamWriter.Write(Char[] buffer)
at System.IO.TextWriter.WriteLine()
at System.IO.TextWriter.SyncTextWriter.WriteLine()
at Microsoft.DotNet.Cli.Utils.Reporter.WriteLine()
at Microsoft.DotNet.Tools.Run.RunCommand.EnsureProjectIsBuilt()
at Microsoft.DotNet.Tools.Run.RunCommand.Execute()
at Microsoft.DotNet.Tools.Run.RunCommand.Run(String[] args)
at Microsoft.DotNet.Cli.Program.ProcessArgs(String[] args, ITelemetry telemetryClient)
at Microsoft.DotNet.Cli.Program.Main(String[] args)
```

### <a name="avoid-inadvertent-disclosure-of-information"></a>Evasión de la divulgación involuntaria de información

Los colaboradores de .NET Core y cualquier otro usuario que ejecute una versión del SDK de .NET Core compilada por ellos mismos deben tener en cuenta la ruta de acceso al código fuente del SDK. Si se produce un bloqueo mientras se usa un SDK de .NET Core que es una compilación de depuración personalizada o está configurado con archivos de símbolos de compilación personalizados, la ruta de acceso del archivo de origen del SDK desde el equipo de compilación se recopila como parte del seguimiento de la pila y no tiene un algoritmo hash.

Por este motivo, las compilaciones personalizadas del SDK de .NET Core no deben almacenarse en directorios cuyos nombres de ruta de acceso expongan información personal o confidencial.

## <a name="see-also"></a>Vea también

- [Datos de telemetría de la CLI de .NET Core](https://dotnet.microsoft.com/platform/telemetry)
- [Fuente de referencia de telemetría (repositorio dotnet/sdk)](https://github.com/dotnet/sdk/tree/master/src/Cli/dotnet/Telemetry)
