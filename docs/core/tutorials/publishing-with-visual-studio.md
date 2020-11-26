---
title: Publicación de una aplicación de consola de .NET con Visual Studio
description: Obtenga información sobre cómo usar Visual Studio para crear el conjunto de archivos necesarios para ejecutar una aplicación de .NET.
ms.date: 06/08/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: b0c6bd85ddf86f0eb11c56f01abb74a7e9786363
ms.sourcegitcommit: 5114e7847e0ff8ddb8c266802d47af78567949cf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/19/2020
ms.locfileid: "94916034"
---
# <a name="tutorial-publish-a-net-console-application-using-visual-studio"></a>Tutorial: Publicación de una aplicación de consola de .NET con Visual Studio

En este tutorial se muestra cómo publicar una aplicación de consola para que otros usuarios puedan ejecutarla. La publicación crea el conjunto de archivos que se necesitan para ejecutar la aplicación. Para implementar los archivos, cópielos en el equipo de destino.

## <a name="prerequisites"></a>Requisitos previos

- Este tutorial funciona con la aplicación de consola que se crea en [Creación de una aplicación de consola de .NET con Visual Studio](with-visual-studio.md).

## <a name="publish-the-app"></a>Publicar la aplicación

1. Inicie Visual Studio.

1. Abra el proyecto *HelloWorld* que ha creado en [Creación de una aplicación de consola de .NET con Visual Studio](with-visual-studio.md).

1. Asegúrese de que Visual Studio usa la configuración de compilación de versión. Si es necesario, cambie la configuración de compilación en la barra de herramientas de **Depurar** a **Versión**.

   :::image type="content" source="media/publishing-with-visual-studio/visual-studio-toolbar-release.png" alt-text="Barra de herramientas de Visual Studio con compilación de versión seleccionada":::

1. Haga clic con el botón derecho en el proyecto **HelloWorld** (no en la solución HelloWorld) y seleccione **Publicar** en el menú.

   :::image type="content" source="media/publishing-with-visual-studio/publish-context-menu.png" alt-text="Menú contextual Publicar de Visual Studio":::

1. En la pestaña **Destino** de la página **Publicar**, seleccione **Carpeta** y luego **Siguiente**.

   :::image type="content" source="media/publishing-with-visual-studio/pick-publish-target.png" alt-text="Elegir un destino de publicación en Visual Studio":::

1. En la pestaña **Destino específico** de la página **Publicar**, seleccione **Carpeta** y luego **Siguiente**.

   :::image type="content" source="media/publishing-with-visual-studio/pick-specific-publish-target.png" alt-text="Elección del destino de publicación específico en Visual Studio":::

1. En la pestaña **Ubicación** de la página **Publicar**, seleccione **Finalizar**.

   :::image type="content" source="media/publishing-with-visual-studio/publish-page-loc-tab.png" alt-text="Pestaña Ubicación de la página Publicar de Visual Studio":::

1. En la pestaña **Publicar** de la ventana **Publicar**, seleccione **Publicar**.

   :::image type="content" source="media/publishing-with-visual-studio/publish-page.png" alt-text="Ventana Publicar de Visual Studio":::

## <a name="inspect-the-files"></a>Inspección de los archivos

De forma predeterminada, el proceso de publicación crea una implementación dependiente del marco, que es un tipo de implementación donde la aplicación publicada se ejecuta en un equipo con el entorno de ejecución de .NET instalado. Los usuarios pueden ejecutar la aplicación publicada haciendo doble clic en el archivo ejecutable o emitiendo el comando `dotnet HelloWorld.dll` desde un símbolo del sistema.

En los pasos siguientes, examinará los archivos creados por el proceso de publicación.

1. En el **Explorador de soluciones**, elija **Mostrar todos los archivos**.

1. En la carpeta del proyecto, expanda *bin/Release/net5.0/publish*.

   :::image type="content" source="media/publishing-with-visual-studio/published-files-output.png" alt-text="Explorador de soluciones donde se muestran los archivos publicados":::

   Como se muestra en la imagen, el resultado publicado incluye los siguientes archivos:

   * *HelloWorld.deps.json*

      Este es el archivo de dependencias en tiempo de ejecución de la aplicación. Define los componentes y las bibliotecas de .NET (incluida la biblioteca de vínculos dinámicos que contiene la aplicación) necesarios para ejecutar la aplicación. Para obtener más información, consulte [Archivos de configuración en tiempo de ejecución](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).

   * *HelloWorld.dll*

      Esta es la versión de [implementación dependiente del marco](../deploying/deploy-with-cli.md#framework-dependent-deployment) de la aplicación. Para ejecutar esta biblioteca de vínculos dinámicos, escriba `dotnet HelloWorld.dll` en un símbolo del sistema. Este método de ejecución de la aplicación funciona en cualquier plataforma que tenga instalado el entorno de ejecución de .NET.

   * *HelloWorld.exe*

      Esta es la versión del [ejecutable dependiente del marco](../deploying/deploy-with-cli.md#framework-dependent-executable) de la aplicación. Para ejecutarlo, escriba `HelloWorld.exe` en un símbolo del sistema. El archivo es específico del sistema operativo.

   * *HelloWorld.pdb* (opcional para la implementación)

      Este es el archivo de símbolos de depuración. No necesita implementar este archivo junto con su aplicación, aunque se debe guardar en caso de que necesite depurar la versión publicada de la aplicación.

   * *HelloWorld.runtimeconfig.json*

      Este es el archivo de configuración en tiempo de ejecución de la aplicación. Identifica la versión de .NET en la que se ha compilado la aplicación para ejecutarse. También puede agregarle opciones de configuración. Para obtener más información, vea [Opciones de configuración en tiempo de ejecución de .NET Core](../run-time-config/index.md#runtimeconfigjson).

## <a name="run-the-published-app"></a>Ejecutar la aplicación publicada

1. En el **Explorador de soluciones**, haga clic con el botón derecho en la carpeta *Publicar* y seleccione **Copiar ruta de acceso completa**.

1. Abra un símbolo del sistema y vaya a la carpeta *Publicar*. Para ello, escriba `cd` y pegue la ruta de acceso completa. Por ejemplo:

   ```console
   cd C:\Projects\HelloWorld\bin\Release\netcoreapp3.1\publish\
   ```

1. Ejecute la aplicación con el archivo ejecutable:

   1. Escriba `HelloWorld.exe` y presione <kbd>ENTRAR</kbd>.

   1. Escriba un nombre cuando se le pida y presione cualquier tecla para salir.

1. Ejecute la aplicación mediante el comando `dotnet`:

   1. Escriba `dotnet HelloWorld.dll` y presione <kbd>ENTRAR</kbd>.

   1. Escriba un nombre cuando se le pida y presione cualquier tecla para salir.

## <a name="additional-resources"></a>Recursos adicionales

- [implementación de aplicaciones .NET](../deploying/index.md)

## <a name="next-steps"></a>Pasos siguientes

En este tutorial, ha publicado una aplicación de consola. En el siguiente tutorial, creará una biblioteca de clases.

> [!div class="nextstepaction"]
> [Creación de una biblioteca de clases de .NET con Visual Studio](library-with-visual-studio.md)
