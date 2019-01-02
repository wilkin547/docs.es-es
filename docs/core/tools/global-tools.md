---
title: Herramientas globales de .NET Core
description: Información general sobre las herramientas globales de .NET Core y los comandos de CLI de .NET Core que hay disponibles para ellas.
author: KathleenDollard
ms.date: 05/29/2018
ms.custom: seodec18
ms.openlocfilehash: 3bbf1e7953482dc07f05570443cf640a9fab6258
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53170861"
---
# <a name="net-core-global-tools-overview"></a>Información general sobre las herramientas globales de .NET Core

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

Una herramienta global de .NET Core es un paquete especial de NuGet que contiene una aplicación de consola. Las herramientas globales se pueden instalar en una ubicación predeterminada del equipo incluida en la variable de entorno PATH, o bien en una ubicación personalizada.

Si quiere usar una herramienta global de .NET Core:

* Busque información sobre la herramienta (normalmente un sitio web o página de GitHub).
* Compruebe el autor y las estadísticas en la página principal de la fuente (normalmente NuGet.org).
* Instale la herramienta.
* Llame a la herramienta.
* Actualice la herramienta.
* Desinstale la herramienta.

> [!IMPORTANT]
> Las herramientas globales de .NET Core aparecen en su ruta de acceso y se ejecutan con plena confianza. No instale herramientas globales de .NET Core a menos que confíe en el autor.

## <a name="find-a-net-core-global-tool"></a>Buscar una herramienta global de .NET Core

Actualmente, no hay una característica que permita buscar herramientas globales en la interfaz de línea de comandos (CLI) de .NET Core.

Aunque estas herramientas se pueden encontrar en [NuGet](https://www.nuget.org), NuGet todavía no permite buscar de manera específica herramientas globales de .NET Core.

Es posible que encuentre recomendaciones sobre herramientas en entradas de blog o en el repositorio de GitHub [natemcmaster/dotnet-tools](https://github.com/natemcmaster/dotnet-tools).

Asimismo, puede ver el código fuente de las herramientas globales creado por el equipo de ASP.NET en el repositorio de GitHub [aspnet/DotNetTools](https://github.com/aspnet/DotNetTools/).

## <a name="check-the-author-and-statistics"></a>Comprobar el autor y las estadísticas

Dado que herramientas globales de .NET Core se ejecutan con plena confianza y generalmente se instalan en su ruta de acceso, pueden ser muy eficaces. No descargue herramientas de personas en las que no confíe.

Si la herramienta está hospedada en NuGet, busque la herramienta para comprobar el autor y las estadísticas.

## <a name="install-a-global-tool"></a>Instalar una herramienta global

Para instalar una herramienta global, use el comando de CLI de .NET Core [dotnet tool install](dotnet-tool-install.md). En el ejemplo siguiente se muestra cómo instalar una herramienta global en la ubicación predeterminada:

```console
dotnet tool install -g dotnetsay
```

Si no se puede instalar la herramienta, se muestran mensajes de error. Verifique que se comprueban las fuentes que esperaba.

Si está intentando instalar una versión preliminar o una versión específica de la herramienta, puede especificar el número de versión con el formato siguiente:

```console
dotnet tool install -g <package-name> --version <version-number>
```

Si la instalación es correcta, se muestra un mensaje similar al siguiente con el comando que se usa para llamar a la herramienta y la versión instalada:

```
You can invoke the tool using the following command: dotnetsay
Tool 'dotnetsay' (version '2.0.0') was successfully installed.
```

Las herramientas globales pueden instalarse en el directorio predeterminado o en una ubicación específica. Los directorios predeterminados son:

| SO          | Ruta de acceso                          |
|-------------|-------------------------------|
| Linux/macOS | `$HOME/.dotnet/tools`         |
| Windows     | `%USERPROFILE%\.dotnet\tools` |

Estas ubicaciones se agregan a la ruta de acceso del usuario cuando se ejecuta el SDK por primera vez, permitiendo así llamar directamente a las herramientas globales allí instaladas.

Tenga en cuenta que las herramientas globales son específicas del usuario, no de la máquina. Específica del usuario significa que no se puede instalar una herramienta global que está disponible para todos los usuarios de la máquina. La herramienta solo está disponible para cada perfil de usuario en el que se instaló la herramienta.

Las herramientas globales también pueden instalarse en un directorio específico. Cuando se instalan en un directorio específico, el usuario debe incluir el directorio en la ruta de acceso a fin de asegurarse de que el comando está disponible. Hay dos maneras de hacerlo: llamar al comando con el directorio especificado, o llamar a la herramienta desde el directorio especificado.
En este caso, la CLI de .NET Core no agrega esta ubicación automáticamente a la variable de entorno PATH.

## <a name="use-the-tool"></a>Usar la herramienta

Una vez que la herramienta se ha instalado, puede llamarla mediante su comando. Tenga en cuenta que el comando podría no ser el mismo que el nombre del paquete.

Si el comando es `dotnetsay`, llame a la herramienta con:

```console
dotnetsay
```

Si la intención del autor era mostrar la herramienta ante una petición de `dotnet`, puede haberla escrito de manera que se llame como `dotnet <command>`, por ejemplo:

```console
dotnet doc
```

Para ver las herramientas que están incluidas en un paquete de herramienta global instalado, enumere los paquetes instalados con el comando [dotnet tool list](dotnet-tool-list.md).

También puede buscar las instrucciones de uso en el sitio web de la herramienta o escribir uno de los siguientes comandos:

```console
<command> --help
dotnet <command> --help
```

### <a name="what-could-go-wrong"></a>Cosas que pueden fallar

Las herramientas globales son [aplicaciones que dependen del marco](../deploying/index.md#framework-dependent-deployments-fdd), lo que significa que se basan en un runtime de .NET Core instalado en el equipo. Si no se encuentra el runtime esperado, se siguen las reglas normales de puesta al día de runtime de .NET Core:

* Una aplicación avanza a la versión de revisión más alta de las versiones principal y secundaria especificadas.
* Si no hay ningún runtime que coincida con un número de versión principal y secundaria, se usa la siguiente versión secundaria más alta.
* Esta puesta al día no se produce entre versiones preliminares del runtime ni entre versiones preliminares y versiones de lanzamiento. En consecuencia, las herramientas globales creadas con versiones preliminares deben ser recompiladas por el autor y posteriormente reinstaladas.
* Pueden producirse otros problemas con las herramientas globales creadas en .NET Core 2.1, versión preliminar 1. Para obtener más información, consulte [.NET Core 2.1 Preview 2 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/2.1/Preview/2.1.0-preview2-known-issues.md) (Problemas conocidos de .NET Core 2.1, versión preliminar 2).

Si una aplicación no encuentra el runtime apropiado, no se puede ejecutar y notifica un error.

Otro problema que puede ocurrir es que una herramienta global que se creó durante una versión preliminar anterior no funcione con los runtime de .NET Core instalados actualmente. Puede usar el comando siguiente para ver los runtime que están instalados en su equipo:

```console
dotnet --list-runtimes
```

Póngase en contacto con el autor de la herramienta global y vea si puede volver a compilar y publicar en NuGet el paquete de la herramienta con un número de versión actualizada. Una vez que hayan actualizado el paquete en NuGet, puede actualizar su copia.

La primera vez que se usa, la CLI de .NET Core intenta agregar las ubicaciones predeterminadas a la variable de entorno PATH. Pero hay un par de escenarios en los que la ubicación podría no agregarse automáticamente a PATH:

* Si ha establecido la variable de entorno `DOTNET_SKIP_FIRST_TIME_EXPERIENCE`.
* En macOS, si ha instalado el SDK de .NET Core usando archivos *.tar.gz* en lugar de *.pkg*.
* En Linux, debe editar el archivo de entorno de shell para configurar PATH.

## <a name="other-cli-commands"></a>Otros comandos de la CLI

El SDK de .NET Core contiene otros comandos que pueden usarse con las herramientas globales de .NET Core. Utilice cualquiera de los comandos de `dotnet tool` combinado con las opciones siguientes:

* `--global` o `-g` especifica que el comando es aplicable a las herramientas globales de todos los usuarios.
* `--tool-path` especifica una ubicación personalizada para las herramientas globales.

Para saber qué comandos están disponibles con las herramientas globales:

```console
dotnet tool --help
```

La actualización de una herramienta global implica desinstalarla y reinstalarla con la versión estable más reciente. Para actualizar una herramienta global, utilice el comando [dotnet tool update](dotnet-tool-update.md):

```console
dotnet tool update -g <packagename>
```

Para quitar una herramienta global con [dotnet tool uninstall](dotnet-tool-uninstall.md):

```console
dotnet tool uninstall -g <packagename>
```

Para mostrar todas las herramientas globales instaladas actualmente en el equipo, junto con su versión y los comandos, use el comando [dotnet tool list](dotnet-tool-list.md):

```console
dotnet tool list -g
```