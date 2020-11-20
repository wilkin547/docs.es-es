---
title: 'Tutorial: Instalación y uso de herramientas locales de .NET'
description: Aprenda a instalar y usar una herramienta de .NET como una herramienta local.
ms.topic: tutorial
ms.date: 02/12/2020
ms.openlocfilehash: 2cb25443706293b66325d43136afcd3fd886294d
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2020
ms.locfileid: "94633886"
---
# <a name="tutorial-install-and-use-a-net-local-tool-using-the-net-cli"></a>Tutorial: Instalación y uso de una herramienta local de .NET mediante la CLI de .NET

**Este artículo se aplica a:** ✔️ SDK de .NET Core 3.0 y versiones posteriores

En este tutorial se enseña cómo instalar y usar una herramienta local. Usará una herramienta que ha creado en el [primer tutorial de esta serie](global-tools-how-to-create.md).

## <a name="prerequisites"></a>Requisitos previos

* Complete el [primer tutorial de esta serie](global-tools-how-to-create.md).
* Instale el entorno de ejecución de .NET Core 2.1.

  En este tutorial, instalará y usará una herramienta que tiene como destino .NET Core 2.1, por lo que debe tener ese entorno de ejecución instalado en el equipo. Para instalar la versión 2.1 del entorno de ejecución, vaya a la [página de descarga de .NET Core 2.1](https://dotnet.microsoft.com/download/dotnet-core/2.1) y busque el vínculo de instalación del entorno de ejecución en la columna **Ejecutar aplicaciones: entorno de ejecución**.

## <a name="create-a-manifest-file"></a>Crear un archivo de manifiesto

Para instalar una herramienta solo para el acceso local (del directorio y los subdirectorios actuales), debe agregarse a un archivo de manifiesto.

Desde la carpeta *microsoft.botsay*, suba un nivel hasta la carpeta *repository*:

```console
cd ..
```

Cree un archivo de manifiesto; para ello, ejecute el comando [dotnet new](dotnet-new.md):

```dotnetcli
dotnet new tool-manifest
```

En la salida se indica que el archivo se ha creado correctamente.

```console
The template "Dotnet local tool manifest file" was created successfully.
```

El archivo *.config/dotnet-tools.json* aún no contiene ninguna herramienta:

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {}
}
```

Las herramientas enumeradas en un archivo de manifiesto están disponibles en el directorio y los subdirectorios actuales. El directorio actual es el que contiene el directorio *.config* con el archivo de manifiesto.

Si se usa un comando de la CLI que hace referencia a una herramienta local, el SDK busca un archivo de manifiesto en el directorio actual y los directorios principales. Si encuentra un archivo de manifiesto, pero el archivo no incluye la herramienta a la que se hace referencia, continúa con la búsqueda en los directorios principales. La búsqueda finaliza cuando encuentra la herramienta a la que se hace referencia o un archivo de manifiesto con `isRoot` establecido en `true`.

## <a name="install-botsay-as-a-local-tool"></a>Instalación de botsay como una herramienta local

Instale la herramienta desde el paquete que ha creado en el primer tutorial:

```dotnetcli
dotnet tool install --add-source ./microsoft.botsay/nupkg microsoft.botsay
```

Este comando agrega la herramienta al archivo de manifiesto que ha creado en el paso anterior. En la salida del comando se muestra el archivo de manifiesto en el que se encuentra la herramienta que acaba de instalar:

 ```console
 You can invoke the tool from this directory using the following command:
 'dotnet tool run botsay' or 'dotnet botsay'
 Tool 'microsoft.botsay' (version '1.0.0') was successfully installed.
 Entry is added to the manifest file /home/name/repository/.config/dotnet-tools.json
 ```

Ahora, el archivo *.config/dotnet-tools.json* tiene una herramienta:

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {
    "microsoft.botsay": {
      "version": "1.0.0",
      "commands": [
        "botsay"
      ]
    }
  }
}
```

## <a name="use-the-tool"></a>Usar la herramienta

Para invocar la herramienta, ejecute el comando `dotnet tool run` desde la carpeta *repository*:

```dotnetcli
dotnet tool run botsay hello from the bot
```

## <a name="restore-a-local-tool-installed-by-others"></a>Restauración de una herramienta local instalada por otros usuarios

Normalmente, una herramienta local se instala en el directorio raíz del repositorio. Después de insertar el archivo de manifiesto en el repositorio, otros desarrolladores pueden obtener el archivo de manifiesto más reciente. Para instalar todas las herramientas enumeradas en el archivo de manifiesto, pueden ejecutar un único comando `dotnet tool restore`.

1. Abra el archivo *.config/dotnet-tools.json* y reemplace el contenido con el siguiente código JSON:

   ```json
   {
     "version": 1,
     "isRoot": true,
     "tools": {
       "microsoft.botsay": {
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

1. Reemplace `<name>` con el nombre que ha usado para crear el proyecto.

1. Guarde los cambios.

   Cambiar esto tiene el mismo resultado que obtener la versión más reciente del repositorio después de que otra persona haya instalado el paquete `dotnetsay` en el directorio del proyecto.

1. Ejecute el comando `dotnet tool restore`.

   ```dotnetcli
   dotnet tool restore
   ```

   El comando genera una salida como la del siguiente ejemplo:

   ```console
   Tool 'microsoft.botsay' (version '1.0.0') was restored. Available commands: botsay
   Tool 'dotnetsay' (version '2.1.3') was restored. Available commands: dotnetsay
   Restore was successful.
   ```

1. Compruebe que las herramientas están disponibles:

   ```dotnetcli
   dotnet tool list
   ```

   La salida es una lista de paquetes y comandos, similar al ejemplo siguiente:

   ```console
   Package Id      Version      Commands       Manifest
   --------------------------------------------------------------------------------------------
   microsoft.botsay 1.0.0        botsay         /home/name/repository/.config/dotnet-tools.json
   dotnetsay        2.1.3        dotnetsay      /home/name/repository/.config/dotnet-tools.json
   ```

1. Pruebe las herramientas:

   ```dotnetcli
   dotnet tool run dotnetsay hello from dotnetsay
   dotnet tool run botsay hello from botsay
   ```

## <a name="update-a-local-tool"></a>Actualización de una herramienta local

La versión instalada de la herramienta local `dotnetsay` es 2.1.3.  La versión más reciente es 2.1.4. Use el comando [dotnet tool update](dotnet-tool-update.md) para actualizar la herramienta a la versión más reciente.

```dotnetcli
dotnet tool update dotnetsay
```

En la salida se indica el nuevo número de versión:

```console
Tool 'dotnetsay' was successfully updated from version '2.1.3' to version '2.1.4'
(manifest file /home/name/repository/.config/dotnet-tools.json).
```

El comando update busca el primer archivo de manifiesto que contiene el identificador del paquete y lo actualiza. Si no hay ningún identificador del paquete en ningún archivo de manifiesto que esté en el ámbito de la búsqueda, el SDK agrega una nueva entrada al archivo de manifiesto más cercano. El ámbito de búsqueda va hacia los directorios principales hasta que se encuentra un archivo de manifiesto con `isRoot = true`.

## <a name="remove-local-tools"></a>Eliminación de las herramientas locales

Ejecute el comando [dotnet tool uninstall](dotnet-tool-uninstall.md) para quitar las herramientas instaladas:

```dotnetcli
dotnet tool uninstall microsoft.botsay
```

```dotnetcli
dotnet tool uninstall dotnetsay
```

## <a name="troubleshoot"></a>Solucionar problemas

Si recibe un mensaje de error al seguir el tutorial, vea [Solución de problemas de uso de herramientas de .NET Core](troubleshoot-usage-issues.md).

## <a name="see-also"></a>Vea también

Para obtener más información, vea [Herramientas de .NET Core](global-tools.md).
