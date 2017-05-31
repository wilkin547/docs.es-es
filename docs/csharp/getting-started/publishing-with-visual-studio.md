---
title: "Publicación de la aplicación Hola a todos con Visual Studio 2017"
description: "La publicación crea el conjunto de archivos que se necesitan para ejecutar la aplicación."
keywords: ".NET, .NET Core, aplicación de consola, publicación, implementación"
author: BillWagner
ms.author: wiwagn
ms.date: 04/17/2017
ms.topic: article
ms.prod: .net-core
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: a19545d3-24af-4a32-9778-cfb5ae938287
ms.translationtype: Human Translation
ms.sourcegitcommit: 39e8e757a446b30ab18914465853138e1c239e40
ms.openlocfilehash: 1c4fbefb23fc47cf035085f76ec1c10d5422a6f5
ms.contentlocale: es-es
ms.lasthandoff: 05/03/2017

---

# <a name="publishing-your-hello-world-application-with-visual-studio-2017"></a>Publicación de la aplicación Hola a todos con Visual Studio 2017

En [Compilación de una aplicación Hola mundo en C# con .NET Core en Visual Studio 2017](with-visual-studio.md), ha compilado una aplicación de consola Hola mundo. En [Depuración de la aplicación Hola a todos en C# con Visual Studio 2017](debugging-with-visual-studio.md), la ha probado con el depurador de Visual Studio. Ahora que está seguro de que funciona como se esperaba, puede publicarla para que otros usuarios puedan ejecutarla. Al realizar la publicación, se crea el conjunto de archivos necesarios para ejecutar la aplicación; y puede implementarlos mediante su copia en un equipo de destino.

Para publicar y ejecutar la aplicación: 

1. Asegúrese de que Visual Studio esté compilando la versión de lanzamiento de la aplicación. Si es necesario, cambie la configuración de compilación en la barra de herramientas de **Depurar** a **Versión**.

   ![Barra de herramientas de Visual Studio](media/publishing-with-visual-studio/toolbar.png)

1. Haga clic con el botón derecho en el proyecto **HelloWorld** (no en la solución HelloWorld) y seleccione **Publicar** en el menú. También puede seleccionar **Publicar Hola a todos** en el menú principal **Compilar** de Visual Studio.

   ![Barra de herramientas de Visual Studio](media/publishing-with-visual-studio/publish1.png)

1. En la ventana de publicación **HelloWorld**, la carpeta de salida de la publicación predeterminada se proporciona en el cuadro de texto **Elegir una carpeta**. Seleccione el botón **Publicar**.

   ![Barra de herramientas de Visual Studio](media/publishing-with-visual-studio/publishwindow.png)

1. Abra una ventana de consola. Por ejemplo, en el cuadro de texto **Pregúntame cualquier cosa** de la barra de tareas de Windows, escriba `Command Prompt` (o `cmd` para abreviar) y abra una ventana de consola seleccionando la aplicación de escritorio **Símbolo del sistema** o presionando Entrar si está seleccionada en los resultados de búsqueda.

1. Vaya a la aplicación publicada en el subdirectorio `bin\release\PublishOutput` del directorio del proyecto de la aplicación. Como se muestra en la ilustración siguiente, el resultado publicado incluye los siguientes cuatro archivos:

      * *HelloWorld.deps.json*
      * *HelloWorld.dll*
      * *HelloWorld.pdb* (opcional para la implementación)
      * *HelloWorld.runtimeconfig.json*

   El archivo *HelloWorld.pdb* contiene símbolos de depuración. No necesita implementar este archivo junto con su aplicación, aunque se debe guardar en caso de que necesite depurar la versión publicada de la aplicación.

   ![Ventana de la consola que muestra los archivos publicados](media/publishing-with-visual-studio/publishedfiles.png)

El proceso de publicación crea una implementación dependiente del marco, que es un tipo de implementación donde la aplicación publicada se ejecutará en cualquier plataforma compatible con .NET Core con .NET Core instalado en el sistema. Los usuarios pueden ejecutar la aplicación mediante la emisión del comando `dotnet HelloWorld.dll` desde una ventana de consola.

Para más información sobre cómo publicar e implementar aplicaciones de .NET Core, consulte [Implementación de aplicaciones .NET Core](../../core/deploying/index.md).
