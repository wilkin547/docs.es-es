---
title: Publicación de una aplicación de consola de .NET con Visual Studio para Mac
description: Aprenda a usar Visual Studio para Mac para crear el conjunto de archivos necesarios para ejecutar una aplicación de .NET.
ms.date: 11/30/2020
ms.openlocfilehash: 88f143011b19ca8eda6610803c894e619d06a635
ms.sourcegitcommit: 9d525bb8109216ca1dc9e39c149d4902f4b43da5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2020
ms.locfileid: "96599196"
---
# <a name="tutorial-publish-a-net-console-application-using-visual-studio-for-mac"></a>Tutorial: Publicación de una aplicación de consola de .NET con Visual Studio para Mac

En este tutorial se muestra cómo publicar una aplicación de consola para que otros usuarios puedan ejecutarla. La publicación crea el conjunto de archivos que se necesitan para ejecutar la aplicación. Para implementar los archivos, cópielos en el equipo de destino.

## <a name="prerequisites"></a>Requisitos previos

- Este tutorial funciona con la aplicación de consola que se crea en [Creación de una aplicación de consola de .NET con Visual Studio para Mac](with-visual-studio-mac.md).

## <a name="publish-the-app"></a>Publicar la aplicación

1. Inicie Visual Studio para Mac:

1. Abra el proyecto HelloWorld que creó en [Creación de una aplicación de consola de .NET con Visual Studio para Mac](with-visual-studio-mac.md).

1. Asegúrese de que Visual Studio esté compilando la versión de lanzamiento de la aplicación. Si es necesario, cambie la configuración de compilación en la barra de herramientas de **Depurar** a **Versión**.

   :::image type="content" source="media/publishing-with-visual-studio-mac/toolbar-release.png" alt-text="Barra de herramientas de Visual Studio con compilación de versión seleccionada":::

1. En el menú principal, elija **Compilación** > **Publicar en carpeta...** .

   :::image type="content" source="media/publishing-with-visual-studio-mac/publish-context-menu.png" alt-text="Menú contextual Publicar de Visual Studio":::

1. En el cuadro de diálogo **Publicar en carpeta**, seleccione **Publicar**.

   :::image type="content" source="media/publishing-with-visual-studio-mac/publish-to-folder-dialog.png" alt-text="Cuadro de diálogo Publicar en carpeta de Visual Studio":::

   Se abre la carpeta de publicación, que muestra los archivos que se crearon.

   :::image type="content" source="media/publishing-with-visual-studio-mac/publish-folder.png" alt-text="carpeta de publicación":::

1. Seleccione el icono de engranaje y elija **Copy "publish" as Pathname** (Copiar "publicar" como nombre de ruta) en el menú contextual.

   :::image type="content" source="media/publishing-with-visual-studio-mac/copy-path.png" alt-text="Copiar ruta de acceso en la carpeta de publicación":::

## <a name="inspect-the-files"></a>Inspección de los archivos

El proceso de publicación crea una implementación dependiente del marco, que es un tipo de implementación donde la aplicación publicada se ejecuta en cualquier máquina que tenga instalado el entorno de ejecución de .NET. Los usuarios pueden ejecutar la aplicación publicada mediante la ejecución del comando `dotnet HelloWorld.dll` desde un símbolo del sistema.

Como se muestra en la imagen anterior, la salida publicada incluye los siguientes archivos:

* *HelloWorld.deps.json*

  Este es el archivo de dependencias en tiempo de ejecución de la aplicación. Define los componentes y las bibliotecas de .NET (incluida la biblioteca de vínculos dinámicos que contiene la aplicación) necesarios para ejecutar la aplicación. Para obtener más información, consulte [Archivos de configuración en tiempo de ejecución](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).

* *HelloWorld.dll*

   Esta es la versión de [implementación dependiente del marco](../deploying/deploy-with-cli.md#framework-dependent-deployment) de la aplicación. Para ejecutar esta biblioteca de vínculos dinámicos, escriba `dotnet HelloWorld.dll` en un símbolo del sistema. Este método de ejecución de la aplicación funciona en cualquier plataforma que tenga instalado el entorno de ejecución de .NET.

* *HelloWorld.pdb* (opcional para la implementación)

   Este es el archivo de símbolos de depuración. No necesita implementar este archivo junto con su aplicación, aunque se debe guardar en caso de que necesite depurar la versión publicada de la aplicación.

* *HelloWorld.runtimeconfig.json*

   Este es el archivo de configuración en tiempo de ejecución de la aplicación. Identifica la versión de .NET en la que se ha compilado la aplicación para ejecutarse. También puede agregarle opciones de configuración. Para obtener más información, vea [Opciones de configuración en tiempo de ejecución de .NET Core](../run-time-config/index.md#runtimeconfigjson).

## <a name="run-the-published-app"></a>Ejecutar la aplicación publicada

1. Abra un terminal y vaya a la carpeta *publish*. Para ello, escriba `cd` y, luego, pegue la ruta de acceso que copió anteriormente. Por ejemplo:

   ```console
   cd ~/Projects/HelloWorld/HelloWorld/bin/Release/net5.0/publish/
   ```

1. Ejecute la aplicación mediante el comando `dotnet`:

   1. Escriba `dotnet HelloWorld.dll` y presione <kbd>Entrar</kbd>.

   1. Escriba un nombre cuando se le pida y presione cualquier tecla para salir.

## <a name="additional-resources"></a>Recursos adicionales

- [implementación de aplicaciones .NET](../deploying/index.md)

## <a name="next-steps"></a>Pasos siguientes

En este tutorial, ha publicado una aplicación de consola. En el siguiente tutorial, creará una biblioteca de clases.

> [!div class="nextstepaction"]
> [Creación de una biblioteca .NET mediante Visual Studio para Mac](library-with-visual-studio-mac.md)
