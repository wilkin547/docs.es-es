---
title: Herramientas de .NET Core
description: Cómo instalar, usar, actualizar y quitar las herramientas de .NET Core. Abarca las herramientas globales, herramientas de ruta de acceso de herramientas y herramientas locales.
author: KathleenDollard
ms.date: 02/12/2020
ms.openlocfilehash: 75bdedcbc3ebe9c23477795415076d160ab9a642
ms.sourcegitcommit: 7499bdb428d63ed0e19e97f54d3d576c41598659
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/31/2020
ms.locfileid: "87455721"
---
# <a name="how-to-manage-net-core-tools"></a>Cómo administrar las herramientas de .NET Core

**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.1 y versiones posteriores

Una herramienta de .NET Core es un paquete especial de NuGet que contiene una aplicación de consola. Una herramienta se puede instalar en el equipo de las siguientes maneras:

* Como herramienta global.

  Los archivos binarios de la herramienta se instalan en un directorio predeterminado que se agrega a la variable de entorno PATH. Puede invocar la herramienta desde cualquier directorio del equipo sin especificar su ubicación. Una versión de una herramienta se usa para todos los directorios del equipo.

* Como herramienta global en una ubicación personalizada (también conocida como herramienta de ruta de acceso de herramientas).

  Los archivos binarios de la herramienta se instalan en la ubicación especificada. Puede invocar la herramienta desde el directorio de instalación o proporcionando el directorio con el nombre del comando o agregando el directorio a la variable de entorno PATH. Una versión de una herramienta se usa para todos los directorios del equipo.

* Como herramienta local (se aplica al SDK de .NET Core 3.0 y versiones posteriores).

  Los archivos binarios de la herramienta se instalan en un directorio predeterminado. Puede invocar la herramienta desde el directorio de instalación o con cualquiera de sus subdirectorios. Distintos directorios pueden usar versiones diferentes de la misma herramienta.
  
  La CLI de .NET usa archivos de manifiesto para realizar un seguimiento de las herramientas que se instalan como locales en un directorio. Cuando el archivo de manifiesto se guarda en el directorio raíz de un repositorio de código fuente, un colaborador puede clonar el repositorio e invocar un solo comando de CLI de .NET Core que instale todas las herramientas enumeradas en los archivos de manifiesto.

> [!IMPORTANT]
> Las herramientas de .NET Core se ejecutan con plena confianza. No instale una herramienta de .NET Core a menos que confíe en el autor.

## <a name="find-a-tool"></a>Búsqueda de una herramienta

Actualmente, .NET Core no tiene una característica de búsqueda de herramientas. Estas son algunas formas de encontrar herramientas:

* Busque en el sitio web de [NuGet](https://www.nuget.org) mediante el filtro de tipo de paquete "herramienta .NET". Para más información, vea [Búsqueda y selección de paquetes](/nuget/consume-packages/finding-and-choosing-packages).
* Consulte la lista de herramientas del repositorio GitHub [natemcmaster/dotnet-tools](https://github.com/natemcmaster/dotnet-tools).
* Use [ToolGet](https://www.toolget.net/) para buscar herramientas de .NET.
* Puede ver el código fuente de las herramientas creado por el equipo de ASP.NET Core en el [directorio de herramientas del repositorio de GitHub dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/tree/master/src/Tools).
* Obtenga más información sobre las herramientas de diagnóstico en [herramientas de diagnóstico de dotnet de .NET Core ](../diagnostics/index.md#net-core-dotnet-diagnostic-global-tools).

## <a name="check-the-author-and-statistics"></a>Comprobar el autor y las estadísticas

Dado que las herramientas de .NET Core se ejecutan con plena confianza y las herramientas globales se agregan a la variable de entorno PATH, pueden ser muy eficaces. No descargue herramientas de personas en las que no confíe.

Si la herramienta está hospedada en NuGet, busque la herramienta para comprobar el autor y las estadísticas.

## <a name="install-a-global-tool"></a>Instalación de una herramienta global

Para instalar una herramienta como una herramienta global, use la opción `-g` o `--global` del comando [dotnet tool install](dotnet-tool-install.md), tal como se muestra en el ejemplo siguiente:

```dotnetcli
dotnet tool install -g dotnetsay
```

La salida muestra el comando que se usa para invocar la herramienta y la versión instalada, de forma similar al ejemplo siguiente:

```output
You can invoke the tool using the following command: dotnetsay
Tool 'dotnetsay' (version '2.1.4') was successfully installed.
```

La ubicación predeterminada de los archivos binarios de una herramienta depende del sistema operativo:

| SO          | Ruta de acceso                          |
|-------------|-------------------------------|
| Linux/macOS | `$HOME/.dotnet/tools`         |
| Windows     | `%USERPROFILE%\.dotnet\tools` |

Esta ubicación se agrega a la ruta de acceso del usuario cuando se ejecuta el SDK por primera vez, por lo que las herramientas globales se pueden invocar desde cualquier directorio sin especificar la ubicación de la herramienta.

El acceso a las herramientas es específico del usuario, no de la máquina global. Una herramienta global solo está disponible para el usuario que ha instalado la herramienta.

### <a name="install-a-global-tool-in-a-custom-location"></a>Instalación de una herramienta global en una ubicación personalizada

Para instalar una herramienta como una herramienta global, use la opción `--tool-path` del comando [dotnet tool install](dotnet-tool-install.md), tal como se muestra en los ejemplos siguientes.

En Windows:

```dotnetcli
dotnet tool install dotnetsay --tool-path c:\dotnet-tools
```

En Linux o macOS:

```dotnetcli
dotnet tool install dotnetsay --tool-path ~/bin
```

El SDK de .NET Core no agrega esta ubicación automáticamente a la variable de entorno PATH. Para [invocar una herramienta de ruta de acceso de herramientas](#invoke-a-tool-path-tool), tiene que asegurarse de que el comando está disponible mediante uno de los métodos siguientes:

* Agregue el directorio de instalación a la variable de entorno PATH.
* Especifique la ruta de acceso completa a la herramienta al invocarla.
* Invoque la herramienta desde el directorio de instalación.

## <a name="install-a-local-tool"></a>Instalación de una herramienta local

**Se aplica al SDK de .NET Core 3.0 y versiones posteriores.**

Para instalar una herramienta solo para el acceso local (del directorio y los subdirectorios actuales), debe agregarse a un archivo de manifiesto de la herramienta. Para crear un archivo de manifiesto de herramienta, ejecute el comando `dotnet new tool-manifest`:

```dotnetcli
dotnet new tool-manifest
```

Este comando crea un archivo de manifiesto denominado *dotnet-tools.json* en el directorio *.config*. Para agregar una herramienta local al archivo de manifiesto, use el comando [dotnet tool install](dotnet-tool-install.md) y **omita** las opciones `--global` y `--tool-path`, tal como se muestra en el ejemplo siguiente:

```dotnetcli
dotnet tool install dotnetsay
```

En la salida del comando se muestra el archivo de manifiesto en el que se encuentra la herramienta que acaba de instalar, de manera similar al siguiente ejemplo:

```console
You can invoke the tool from this directory using the following command:
dotnet tool run dotnetsay
Tool 'dotnetsay' (version '2.1.4') was successfully installed.
Entry is added to the manifest file /home/name/botsay/.config/dotnet-tools.json.
```

En el ejemplo siguiente se muestra un archivo de manifiesto con dos herramientas locales instaladas:

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {
    "botsay": {
      "version": "1.0.0",
      "commands": [
        "botsay"
      ]
    },
    "dotnetsay": {
      "version": "2.1.3",
      "commands": [
        "dotnetsay"
      ]
    }
  }
}
```

Normalmente, una herramienta local se agrega al directorio raíz del repositorio. Después de insertar el archivo de manifiesto en el repositorio, los desarrolladores que extraen código del repositorio obtienen el archivo de manifiesto más reciente. Para instalar todas las herramientas enumeradas en el archivo de manifiesto, ejecutan el comando `dotnet tool restore`:

```dotnetcli
dotnet tool restore
```

La salida indica qué herramientas se han restaurado:

```console
Tool 'botsay' (version '1.0.0') was restored. Available commands: botsay
Tool 'dotnetsay' (version '2.1.3') was restored. Available commands: dotnetsay
Restore was successful.
```

## <a name="install-a-specific-tool-version"></a>Instalación de una versión específica de la herramienta

Para instalar una versión preliminar o una versión específica de la herramienta, especifique el número de versión con la opción `--version`, tal como se muestra en el ejemplo siguiente:

```dotnetcli
dotnet tool install dotnetsay --version 2.1.3
```

## <a name="use-a-tool"></a>Uso de una herramienta

El comando que se usa para invocar una herramienta puede ser diferente del nombre del paquete que se instala. Para mostrar todas las herramientas instaladas actualmente en el equipo para el usuario actual, use el comando [dotnet tool list](dotnet-tool-list.md):

```dotnetcli
dotnet tool list
```

La salida muestra la versión y el comando de cada herramienta, de forma similar al ejemplo siguiente:

```console
Package Id      Version      Commands       Manifest
-------------------------------------------------------------------------------------------
botsay          1.0.0        botsay         /home/name/repository/.config/dotnet-tools.json
dotnetsay       2.1.3        dotnetsay      /home/name/repository/.config/dotnet-tools.json
```

Tal como se muestra en este ejemplo, la lista muestra las herramientas locales. Para ver las herramientas globales, use la opción `--global` y, para ver herramientas de ruta de acceso de herramientas, use la opción `--tool-path`.

### <a name="invoke-a-global-tool"></a>Invocación de una herramienta global

En el caso de las herramientas globales, use el comando de la herramienta por sí solo. Por ejemplo, si el comando es `dotnetsay` o `dotnet-doc`, eso es lo que se usa para invocar el comando:

```console
dotnetsay
dotnet-doc
```

Si el comando comienza con el prefijo `dotnet-`, una manera alternativa de invocar la herramienta es usar el comando `dotnet` y omitir el prefijo del comando de la herramienta. Por ejemplo, si el comando es `dotnet-doc`, el siguiente comando invoca la herramienta:

```dotnetcli
dotnet doc
```

Sin embargo, en el siguiente escenario no se puede usar el comando `dotnet` para invocar una herramienta global:

* Una herramienta global y una herramienta local tienen el mismo comando con el prefijo `dotnet-`.
* Quiere invocar la herramienta global desde un directorio que está en el ámbito de la herramienta local.

En este escenario, `dotnet doc` y `dotnet dotnet-doc` invocan a la herramienta local. Para invocar la herramienta global, use el comando por sí solo:

```dotnetcli
dotnet-doc
```

### <a name="invoke-a-tool-path-tool"></a>Invocación de una herramienta de ruta de acceso de herramientas

Para invocar una herramienta global que se instala mediante la opción `tool-path`, asegúrese de que el comando está disponible, tal como se explicó [anteriormente en este artículo](#install-a-global-tool-in-a-custom-location).

### <a name="invoke-a-local-tool"></a>Invocación de una herramienta local

Para invocar una herramienta local, tiene que usar el comando `dotnet` desde el directorio de instalación. Puede usar el formato largo (`dotnet tool run <COMMAND_NAME>`) o el formato abreviado (`dotnet <COMMAND_NAME>`), tal como se muestra en los ejemplos siguientes:

```dotnetcli
dotnet tool run dotnetsay
dotnet dotnetsay
```

Si el comando tiene el prefijo `dotnet-`, puede incluir u omitir el prefijo al invocar la herramienta. Por ejemplo, si el comando es `dotnet-doc`, cualquiera de los siguientes ejemplos invoca la herramienta local:

```dotnetcli
dotnet tool run dotnet-doc
dotnet dotnet-doc
dotnet doc
```

## <a name="update-a-tool"></a>Actualización de una herramienta

La actualización de una herramienta implica desinstalarla y reinstalarla con la versión estable más reciente. Para actualizar una herramienta, use el comando [dotnet tool update](dotnet-tool-update.md) con la misma opción que usó para instalar la herramienta:

```dotnetcli
dotnet tool update --global <packagename>
dotnet tool update --tool-path <packagename>
dotnet tool update <packagename>
```

En el caso de una herramienta local, el SDK encuentra el primer archivo de manifiesto que contiene el identificador de paquete mediante la búsqueda en el directorio actual y en los directorios principales. Si no hay ningún identificador del paquete en ningún archivo de manifiesto, el SDK agrega una nueva entrada al archivo de manifiesto más cercano.

## <a name="uninstall-a-tool"></a>Desinstalación de una herramienta

Quite una herramienta mediante el comando [dotnet tool uninstall](dotnet-tool-uninstall.md) con la misma opción que usó para instalar la herramienta:

```dotnetcli
dotnet tool uninstall --global <packagename>
dotnet tool uninstall --tool-path <packagename>
dotnet tool uninstall <packagename>
```

En el caso de una herramienta local, el SDK encuentra el primer archivo de manifiesto que contiene el identificador de paquete mediante la búsqueda en el directorio actual y en los directorios principales.

## <a name="get-help-and-troubleshoot"></a>Ayuda y solución de problemas

Para obtener una lista de los comandos de `dotnet tool` disponibles, escriba el siguiente comando:

```dotnetcli
dotnet tool --help
```

Para obtener instrucciones sobre el uso de la herramienta, escriba uno de los siguientes comandos o vea el sitio web de la herramienta:

```dotnetcli
<command> --help
dotnet <command> --help
```

Si una herramienta no se puede instalar o ejecutar, consulte [Solución de problemas de uso de herramientas de .NET Core](troubleshoot-usage-issues.md).

## <a name="see-also"></a>Vea también

- [Tutorial: Creación de una herramienta de .NET Core mediante la CLI de .NET Core](global-tools-how-to-create.md)
- [Tutorial: Instalación y uso de una herramienta global de .NET Core mediante la CLI de .NET Core](global-tools-how-to-use.md)
- [Tutorial: Instalación y uso de una herramienta local de .NET Core mediante la CLI de .NET Core](local-tools-how-to-use.md)
