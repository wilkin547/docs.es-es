---
title: Publicación de la aplicación Hola mundo de .NET Core con Visual Studio
description: La publicación crea el conjunto de archivos que se necesitan para ejecutar la aplicación de .NET Core.
author: BillWagner
ms.author: wiwagn
ms.date: 05/20/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: e4ef8c12f3e52faa7cf09058a98abae65b0dcfce
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84005126"
---
# <a name="tutorial-publish-a-net-core-console-application-with-visual-studio"></a>Tutorial: Publicación de una aplicación de consola de .NET Core con Visual Studio

En este tutorial se muestra cómo publicar una aplicación de consola para que otros usuarios puedan ejecutarla. La publicación crea el conjunto de archivos que se necesitan para ejecutar la aplicación. Para implementar los archivos, cópielos en el equipo de destino.

## <a name="prerequisites"></a>Requisitos previos

- Este tutorial funciona con la aplicación de consola que se crea en [Creación de una aplicación de consola de .NET Core en Visual Studio 2019](with-visual-studio.md).

## <a name="publish-the-app"></a>Publicar la aplicación

1. Asegúrese de que Visual Studio esté compilando la versión de lanzamiento de la aplicación. Si es necesario, cambie la configuración de compilación en la barra de herramientas de **Depurar** a **Versión**.

   ![Barra de herramientas de Visual Studio con compilación de versión seleccionado](media/publishing-with-visual-studio/visual-studio-toolbar-release.png)

1. Haga clic con el botón derecho en el proyecto **HelloWorld** (no en la solución HelloWorld) y seleccione **Publicar** en el menú.

   ![Menú contextual de Publicar de Visual Studio](media/publishing-with-visual-studio/publish-context-menu.png)

1. En la pestaña **Destino** de la página **Publicar**, seleccione **Carpeta** y luego **Siguiente**.

   ![Elegir un destino de publicación en Visual Studio](media/publishing-with-visual-studio/pick-publish-target.png)

1. En la pestaña **Ubicación** de la página **Publicar**, seleccione **Finalizar**.

   ![Pestaña Ubicación de la página Publicar de Visual Studio](media/publishing-with-visual-studio/publish-page-loc-tab.png)

1. En la pestaña **Publicar** de la ventana **Publicar**, seleccione **Publicar**.

   ![Ventana Publicar de Visual Studio](media/publishing-with-visual-studio/publish-page.png)

## <a name="inspect-the-files"></a>Inspección de los archivos

El proceso de publicación crea una implementación dependiente del marco, que es un tipo de implementación donde la aplicación publicada se ejecuta en cualquier máquina que tenga instalado .NET Core Runtime. Los usuarios pueden ejecutar la aplicación publicada haciendo doble clic en el archivo ejecutable o emitiendo el comando `dotnet HelloWorld.dll` desde un símbolo del sistema.

En los pasos siguientes, examinará los archivos creados por el proceso de publicación.

1. En el **Explorador de soluciones**, elija **Mostrar todos los archivos**.

1. En la carpeta del proyecto, expanda *bin/Release/netcoreapp3.1/publish*.

   :::image type="content" source="media/publishing-with-visual-studio/published-files-output.png" alt-text="Explorador de soluciones donde se muestran los archivos publicados":::

   Como se muestra en la imagen, el resultado publicado incluye los siguientes archivos:

      * *HelloWorld.deps.json*

         Este es el archivo de dependencias en tiempo de ejecución de la aplicación. Define los componentes y las bibliotecas de .NET Core (incluida la biblioteca de vínculos dinámicos que contiene la aplicación) necesarios para ejecutar la aplicación. Para obtener más información, consulte [Archivos de configuración en tiempo de ejecución](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).

      * *HelloWorld.dll*

         Esta es la versión de [implementación dependiente del marco](../deploying/deploy-with-cli.md#framework-dependent-deployment) de la aplicación. Para ejecutar esta biblioteca de vínculos dinámicos, escriba `dotnet HelloWorld.dll` en un símbolo del sistema.

      * *HelloWorld.exe*

         Esta es la versión del [ejecutable dependiente del marco](../deploying/deploy-with-cli.md#framework-dependent-executable) de la aplicación. Para ejecutarlo, escriba `HelloWorld.exe` en un símbolo del sistema.

      * *HelloWorld.pdb* (opcional para la implementación)

         Este es el archivo de símbolos de depuración. No necesita implementar este archivo junto con su aplicación, aunque se debe guardar en caso de que necesite depurar la versión publicada de la aplicación.

      * *HelloWorld.runtimeconfig.json*

         Este es el archivo de configuración en tiempo de ejecución de la aplicación. Identifica la versión de .NET Core en la que se ha compilado la aplicación para ejecutarse. También puede agregarle opciones de configuración. Para obtener más información, vea [Opciones de configuración en tiempo de ejecución de .NET Core](../run-time-config/index.md#runtimeconfigjson).

## <a name="run-the-published-app"></a>Ejecutar la aplicación publicada

1. En el **Explorador de soluciones**, haga clic con el botón derecho en la carpeta *Publicar* y seleccione **Copiar ruta de acceso completa**.

1. Abra un símbolo del sistema y vaya a la carpeta *Publicar*. Escriba `cd` y pegue la ruta de acceso completa. Por ejemplo:

   ```
   cd C:\Projects\HelloWorld\bin\Release\netcoreapp3.1\publish\
   ```

1. Ejecute la aplicación con el archivo ejecutable:

   1. Escriba `HelloWorld.exe` y presione Entrar.

   1. Escriba un nombre cuando se le pida y presione cualquier tecla para salir.

1. Ejecute la aplicación mediante el comando `dotnet`:

   1. Escriba `dotnet HelloWorld.dll` y presione Entrar.

   1. Escriba un nombre cuando se le pida y presione cualquier tecla para salir.

## <a name="additional-resources"></a>Recursos adicionales

- [Implementación de aplicaciones .NET Core](../deploying/index.md)

## <a name="next-steps"></a>Pasos siguientes

En este tutorial, ha publicado una aplicación de consola. En el siguiente tutorial, creará una biblioteca de clases.

> [!div class="nextstepaction"]
> [Creación de una biblioteca de .NET Standard en Visual Studio](library-with-visual-studio.md)
