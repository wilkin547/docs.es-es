---
title: Solución de problemas de uso de herramientas de .NET Core
description: Descubra los problemas comunes que se producen al ejecutar herramientas de .NET Core y sus posibles soluciones.
author: kdollard
ms.topic: troubleshooting
ms.date: 02/14/2020
ms.openlocfilehash: db88958e1605fef589c5dbcb12065a6318183705
ms.sourcegitcommit: cbb19e56d48cf88375d35d0c27554d4722761e0d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2020
ms.locfileid: "88608310"
---
# <a name="troubleshoot-net-core-tool-usage-issues"></a>Solución de problemas de uso de herramientas de .NET Core

Es posible que surjan problemas al intentar instalar o ejecutar una herramienta de .NET Core, la cual puede ser global o local. En este artículo se describen las causas principales más comunes y algunas posibles soluciones.

## <a name="installed-net-core-tool-fails-to-run"></a>No se puede ejecutar la herramienta de .NET Core instalada

Cuando una herramienta de .NET Core no se ejecuta, lo más probable es que se haya producido uno de los siguientes problemas:

* No se encontró el archivo ejecutable de la herramienta.
* No se encontró la versión correcta del runtime de .NET Core.

### <a name="executable-file-not-found"></a>No se encontró el archivo ejecutable

Si no se encuentra el archivo ejecutable, verá un mensaje similar al siguiente:

```console
Could not execute because the specified command or file was not found.
Possible reasons for this include:
  * You misspelled a built-in dotnet command.
  * You intended to execute a .NET Core program, but dotnet-xyz does not exist.
  * You intended to run a global tool, but a dotnet-prefixed executable with this name could not be found on the PATH.
```

El nombre del archivo ejecutable determina cómo se invoca la herramienta. En la siguiente tabla se describe el formato:

| Formato del nombre del archivo ejecutable  | Formato de invocación   |
|-------------------------|---------------------|
| `dotnet-<toolName>.exe` | `dotnet <toolName>` |
| `<toolName>.exe`        | `<toolName>`        |

* Herramientas globales

  Las herramientas globales pueden instalarse en el directorio predeterminado o en una ubicación específica. Los directorios predeterminados son:

  | SO          | Ruta de acceso                          |
  |-------------|-------------------------------|
  | Linux/macOS | `$HOME/.dotnet/tools`         |
  | Windows     | `%USERPROFILE%\.dotnet\tools` |

  Si intenta ejecutar una herramienta global, compruebe que la variable del entorno `PATH` de su máquina contiene la ruta de acceso donde instaló la herramienta global y que el archivo ejecutable está en esa ruta de acceso.

  La primera vez que se usa, la CLI de .NET Core intenta agregar la ubicación predeterminada a la variable de entorno PATH. Pero hay algunos escenarios en los que la ubicación podría no agregarse a PATH automáticamente:

  * Si usa Linux y ha instalado el SDK de .NET Core mediante el uso de archivos *.tar.gz* en lugar de “apt-get” o “rpm”.
  * Si usa macOS 10.15 “Catalina” o versiones posteriores.
  * Si usa macOS 10.14 “Mojave” o versiones anteriores y ha instalado el SDK de .NET Core mediante el uso de archivos *.tar.gz* en lugar de *.pkg*.
  * Si ha instalado el SDK de .NET Core 3.0 y ha establecido la variable de entorno `DOTNET_ADD_GLOBAL_TOOLS_TO_PATH` en `false`.
  * Si ha instalado el SDK de .NET Core 2.2 o versiones anteriores y ha establecido la variable de entorno `DOTNET_SKIP_FIRST_TIME_EXPERIENCE` en `true`.

  En estos casos, o si especificó la opción `--tool-path`, la variable de entorno `PATH` del equipo no contiene automáticamente la ruta de acceso donde se instaló la herramienta global. En tal caso, anexe la ubicación de la herramienta (por ejemplo, `$HOME/.dotnet/tools`) a la variable de entorno `PATH` usando el método que el shell proporcione para actualizar variables de entorno. Para obtener más información, vea [Herramientas de .NET Core](global-tools.md).

* Herramientas locales

  Si intenta ejecutar una herramienta local, compruebe que hay un archivo de manifiesto denominado *dotnet-tools.json* en el directorio actual o en cualquiera de sus directorios principales. Este archivo también puede encontrarse en una carpeta denominada *.config* en cualquier lugar de la jerarquía de carpetas del proyecto, en lugar de en la carpeta raíz. Si *dotnet-tools.json* existe, ábralo y busque la herramienta que intenta ejecutar. Si el archivo no contiene una entrada para `"isRoot": true`, busque más arriba en la jerarquía de archivos otros archivos de manifiesto de la herramienta.

  Si intenta ejecutar una herramienta de .NET Core que se instaló con una ruta de acceso especificada, debe incluir dicha ruta de acceso al usar la herramienta. Un ejemplo de uso de una herramienta instalada en una ruta de acceso de herramientas es:

  ```console
  ..\<toolDirectory>\dotnet-<toolName>
  ```

### <a name="runtime-not-found"></a>No se encontró el runtime

Las herramientas de .NET Core son [aplicaciones dependientes del marco](../deploying/index.md#publish-framework-dependent), lo que significa que se basan en un runtime de .NET Core instalado en el equipo. Si no se encuentra el runtime esperado, se siguen las reglas normales de puesta al día de runtime de .NET Core:

* Una aplicación avanza a la versión de revisión más alta de las versiones principal y secundaria especificadas.
* Si no hay ningún runtime que coincida con un número de versión principal y secundaria, se usa la siguiente versión secundaria más alta.
* Esta puesta al día no se produce entre versiones preliminares del runtime ni entre versiones preliminares y versiones de lanzamiento. Por lo tanto, las herramientas de .NET Core creadas con versiones preliminares deben ser recompiladas, publicadas nuevamente y reinstaladas por el autor.

La puesta al día no se producirá de forma predeterminada en dos escenarios comunes:

* Solo están disponibles las versiones anteriores del runtime. La puesta al día solo selecciona versiones posteriores del runtime.
* Solo están disponibles las versiones posteriores principales del runtime. La puesta al día no traspasa los límites de la versión principal.

Si una aplicación no encuentra el runtime apropiado, no se puede ejecutar y notifica un error.

Puede averiguar qué runtimes de .NET Core están instalados en su máquina con uno de los comandos siguientes:

```dotnetcli
dotnet --list-runtimes
dotnet --info
```

Si cree que la herramienta debería ser compatible con la versión de runtime que tiene instalada actualmente, puede ponerse en contacto con el autor de la herramienta para ver si puede actualizar el número de versión o la compatibilidad con varios destinos. Una vez que se vuelva a compilar y a publicar el paquete de herramientas en NuGet con un número de versión actualizado, podrá actualizar su copia. Mientras tanto, la solución más rápida es instalar una versión del runtime que funcione con la herramienta que intenta ejecutar. Para descargar una versión específica del runtime de .NET Core, visite la [página de descarga de .NET Core](https://dotnet.microsoft.com/download/dotnet-core).

Si instala el SDK de .NET Core en una ubicación que no es la predeterminada, debe establecer la variable de entorno `DOTNET_ROOT` en el directorio que contiene el archivo ejecutable `dotnet`.

## <a name="net-core-tool-installation-fails"></a>Error en la instalación de una herramienta de .NET Core

Hay varias razones por las que se puede producir un error en la instalación de una herramienta local o global de .NET Core. Cuando se produzca un error en la instalación de la herramienta, verá un mensaje similar al siguiente:

```console
Tool '{0}' failed to install. This failure may have been caused by:

* You are attempting to install a preview release and did not use the --version option to specify the version.
* A package by this name was found, but it was not a .NET Core tool.
* The required NuGet feed cannot be accessed, perhaps because of an Internet connection problem.
* You mistyped the name of the tool.

For more reasons, including package naming enforcement, visit https://aka.ms/failure-installing-tool
```

Para ayudar a diagnosticar estos errores, los mensajes de NuGet se muestran directamente al usuario, junto con el mensaje anterior. El mensaje de NuGet puede ayudarle a identificar el problema.

### <a name="package-naming-enforcement"></a>Cumplimiento de la nomenclatura de los paquetes

Microsoft ha cambiado sus instrucciones sobre los identificadores de paquetes para las herramientas, lo que ha dado lugar a que no se encuentren diversas herramientas con el nombre previsto. Según las nuevas instrucciones, todas las herramientas de Microsoft deben tener el prefijo “Microsoft”. Este prefijo está reservado y solo se puede usar para los paquetes firmados con un certificado autorizado de Microsoft.

Durante la transición, algunas herramientas de Microsoft tendrán el formato anterior del identificador de paquete, mientras que otras tendrán el nuevo formato:

```dotnetcli
dotnet tool install -g Microsoft.<toolName>
dotnet tool install -g <toolName>
```

A medida que se actualicen los identificadores de paquetes, deberá usar el nuevo identificador de paquete para obtener las actualizaciones más recientes. Los paquetes con el nombre de herramienta simplificado estarán en desuso.

### <a name="preview-releases"></a>Versiones preliminares

* Intenta instalar una versión preliminar y no ha usado la opción `--version` para especificar la versión.

Las herramientas de .NET Core que se encuentran en versión preliminar deben especificarse con una parte del nombre para indicar que están en versión preliminar. No es necesario incluir todo el nombre de la versión preliminar. Si los números de versión tienen el formato esperado, puede usar algo parecido al ejemplo siguiente:

```dotnetcli
dotnet tool install -g --version 1.1.0-pre <toolName>
```

### <a name="package-isnt-a-net-core-tool"></a>El paquete no es una herramienta de .NET Core

* Se encontró un paquete NuGet con este nombre, pero no era una herramienta .NET Core.

Si intenta instalar un paquete normal de NuGet que no es una herramienta de .NET Core, verá un error similar al siguiente:

> NU1212: combinación de paquete de proyecto no válida para `<ToolName>`. El estilo de proyecto DotnetToolReference solo puede contener referencias de tipo DotnetTool.

### <a name="nuget-feed-cant-be-accessed"></a>No se puede acceder a la fuente NuGet

* No se puede acceder a la fuente NuGet necesaria, quizás debido a un problema con la conexión a Internet.

La instalación de la herramienta requiere acceso a la fuente NuGet que contiene el paquete de la herramienta. Se produce un error si la fuente no está disponible. Puede modificar las fuentes con `nuget.config`, solicitar un archivo `nuget.config` determinado o especificar fuentes adicionales con el modificador `--add-source`. De forma predeterminada, NuGet genera un error para cualquier fuente con la que no pueda conectar. La marca `--ignore-failed-sources` puede omitir estos orígenes no accesibles.

### <a name="package-id-incorrect"></a>Identificador de paquete incorrecto

* No ha escrito correctamente el nombre de la herramienta.

Un motivo habitual de error es que el nombre de la herramienta no es correcto. Esto puede ocurrir cuando se produce un error de escritura, o porque la herramienta se ha movido o está en desuso. En el caso de las herramientas de NuGet.org, una manera de asegurarse de que tiene el nombre correcto es buscar la herramienta en NuGet.org y copiar el comando de instalación.

## <a name="see-also"></a>Vea también

* [Herramientas de .NET Core](global-tools.md)
