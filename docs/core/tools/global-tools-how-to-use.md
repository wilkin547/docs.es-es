---
title: 'Tutorial: Instalación y uso de una herramienta global de .NET'
description: Aprenda a instalar y usar una herramienta de .NET como una herramienta global.
ms.topic: tutorial
ms.date: 02/12/2020
ms.openlocfilehash: 01b773516da92fb16fb0f67fc6617e0c70d17c9d
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2020
ms.locfileid: "94633900"
---
# <a name="tutorial-install-and-use-a-net-global-tool-using-the-net-cli"></a>Tutorial: Instalación y uso de una herramienta global de .NET mediante la CLI de .NET

**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.1 y versiones posteriores

En este tutorial se enseña cómo instalar y usar una herramienta global. Usará una herramienta que ha creado en el [primer tutorial de esta serie](global-tools-how-to-create.md).

## <a name="prerequisites"></a>Requisitos previos

* Complete el [primer tutorial de esta serie](global-tools-how-to-create.md).

## <a name="use-the-tool-as-a-global-tool"></a>Uso de la herramienta como una herramienta global

1. Instale la herramienta desde el paquete; para ello, ejecute el comando [dotnet tool install](dotnet-tool-install.md) en la carpeta del proyecto *microsoft.botsay*:

   ```dotnetcli
   dotnet tool install --global --add-source ./nupkg microsoft.botsay
   ```

   El parámetro `--global` indica a la CLI de .NET que instale los archivos binarios de la herramienta en una ubicación predeterminada que se agrega de forma automática a la variable de entorno PATH.

   El parámetro `--add-source` indica a la CLI de .NET que use temporalmente el directorio *./nupkg* como una fuente de origen adicional para los paquetes NuGet. Ha asignado un nombre único al paquete para asegurarse de que solo se encontrará en el directorio *./nupkg*, no en el sitio de Nuget.org.

   En la salida se muestra el comando que se ha usado para llamar a la herramienta y la versión instalada:

   ```console
   You can invoke the tool using the following command: botsay
   Tool 'microsoft.botsay' (version '1.0.0') was successfully installed.
   ```

1. Invoque la herramienta:

   ```console
   botsay hello from the bot
   ```

   > [!NOTE]
   > Si se produce un error en este comando, es posible que tenga que abrir un nuevo terminal para actualizar el valor de PATH.

1. Ejecute el comando [dotnet tool uninstall](dotnet-tool-uninstall.md) para quitar la herramienta:

   ```dotnetcli
   dotnet tool uninstall -g microsoft.botsay
   ```

## <a name="use-the-tool-as-a-global-tool-installed-in-a-custom-location"></a>Uso de la herramienta como una herramienta global instalada en una ubicación personalizada

1. Instale la herramienta desde el paquete.

   En Windows:

   ```dotnetcli
   dotnet tool install --tool-path c:\dotnet-tools --add-source ./nupkg microsoft.botsay
   ```

   En Linux o macOS:

   ```dotnetcli
   dotnet tool install --tool-path ~/bin --add-source ./nupkg microsoft.botsay
   ```

   El parámetro `--tool-path` indica a la CLI de .NET que instale los archivos binarios de la herramienta en la ubicación especificada. Si el directorio no existe, se crea. Este directorio no se agrega automáticamente a la variable de entorno PATH.

   En la salida se muestra el comando que se ha usado para llamar a la herramienta y la versión instalada:

   ```console
   You can invoke the tool using the following command: botsay
   Tool 'microsoft.botsay' (version '1.0.0') was successfully installed.
   ```

1. Invoque la herramienta:

   En Windows:

   ```console
   c:\dotnet-tools\botsay hello from the bot
   ```

   En Linux o macOS:

   ```console
   ~/bin/botsay hello from the bot
   ```

1. Ejecute el comando [dotnet tool uninstall](dotnet-tool-uninstall.md) para quitar la herramienta:

   En Windows:

   ```dotnetcli
   dotnet tool uninstall --tool-path c:\dotnet-tools microsoft.botsay
   ```

   En Linux o macOS:

   ```dotnetcli
   dotnet tool uninstall --tool-path ~/bin microsoft.botsay
   ```

## <a name="troubleshoot"></a>Solucionar problemas

Si recibe un mensaje de error al seguir el tutorial, vea [Solución de problemas de uso de herramientas de .NET Core](troubleshoot-usage-issues.md).

## <a name="next-steps"></a>Pasos siguientes

En este tutorial, ha instalado y usado una herramienta como una herramienta global. Para instalar y usar la misma herramienta como una herramienta local, vaya al siguiente tutorial.

> [!div class="nextstepaction"]
> [Instalación y uso de herramientas locales](local-tools-how-to-use.md)
