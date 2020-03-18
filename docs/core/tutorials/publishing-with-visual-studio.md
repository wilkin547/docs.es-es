---
title: Publicación de la aplicación Hola mundo de .NET Core con Visual Studio
description: La publicación crea el conjunto de archivos que se necesitan para ejecutar la aplicación de .NET Core.
author: BillWagner
ms.author: wiwagn
ms.date: 12/10/2019
ms.custom: vs-dotnet
ms.openlocfilehash: bdd6e28713bdece2bd144e6763bd84d719e91449
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "78156639"
---
# <a name="publish-your-net-core-hello-world-application-with-visual-studio"></a>Publicación de la aplicación Hola mundo de .NET Core con Visual Studio

En [Creación de una aplicación Hola mundo con .NET Core en Visual Studio](with-visual-studio.md), ha compilado una aplicación de consola Hola mundo. En [Depuración de la aplicación Hola mundo con Visual Studio](debugging-with-visual-studio.md), la ha probado con el depurador de Visual Studio. Ahora que está seguro de que funciona como se esperaba, puede publicarla para que otros usuarios puedan ejecutarla. La publicación crea el conjunto de archivos que se necesitan para ejecutar la aplicación. Para implementar los archivos, cópielos en el equipo de destino.

## <a name="publish-the-app"></a>Publicar la aplicación

1. Asegúrese de que Visual Studio esté compilando la versión de lanzamiento de la aplicación. Si es necesario, cambie la configuración de compilación en la barra de herramientas de **Depurar** a **Versión**.

   ![Barra de herramientas de Visual Studio con compilación de versión seleccionado](media/publishing-with-visual-studio/visual-studio-toolbar-release.png)

1. Haga clic con el botón derecho en el proyecto **HelloWorld** (no en la solución HelloWorld) y seleccione **Publicar** en el menú. (también puede seleccionar **Publicar Hola mundo** en el menú principal **Compilar**).

   ![Menú contextual de Publicar de Visual Studio](media/publishing-with-visual-studio/publish-context-menu.png)

1. En la página **Elegir un destino de publicación**, seleccione **Carpeta** y, a continuación, seleccione **Crear perfil**.

   ![Elegir un destino de publicación en Visual Studio](media/publishing-with-visual-studio/pick-publish-target.png)

1. En la página **Publicar**, seleccione **Publicar**.

   ![Ventana Publicar de Visual Studio](media/publishing-with-visual-studio/publish-page.png)

## <a name="inspect-the-files"></a>Inspección de los archivos

El proceso de publicación crea una implementación dependiente del marco, que es un tipo de implementación donde la aplicación publicada se ejecuta en cualquier plataforma compatible con .NET Core con .NET Core instalado en el sistema. Los usuarios pueden ejecutar la aplicación publicada haciendo doble clic en el archivo ejecutable o emitiendo el comando `dotnet HelloWorld.dll` desde un símbolo del sistema.

En los pasos siguientes, examinará los archivos creados por el proceso de publicación.

1. Abra un símbolo del sistema.

   Una forma de abrir un símbolo del sistema es escribir **Símbolo del sistema** (o **cmd**) en el cuadro de búsqueda de la barra de tareas de Windows. Seleccione la aplicación de escritorio **Símbolo del sistema** o presione **Entrar** si ya está seleccionado en los resultados de búsqueda.

1. Vaya a la aplicación publicada en el subdirectorio *bin\Release\netcoreapp3.1\publish* del directorio del proyecto de la aplicación.

   ![Ventana de la consola que muestra los archivos publicados](media/publishing-with-visual-studio/published-files-output.png)

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

## <a name="additional-resources"></a>Recursos adicionales

- [Implementación de aplicaciones .NET Core](../deploying/index.md)
