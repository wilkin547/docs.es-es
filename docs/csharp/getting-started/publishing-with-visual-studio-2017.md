---
title: "Publicación de la aplicación Hola a todos con Visual Studio 2017"
description: "Publicación de la aplicación Hola a todos con Visual Studio 2017"
keywords: ".NET, .NET Core, aplicación de consola .NET Core, publicación (.NET Core), implementación (.NET Core)"
author: BillWagner
ms.author: wiwagn
ms.date: 10/24/2016
ms.topic: article
ms.prod: .net-core
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: a19545d3-24af-4a32-9778-cfb5ae938287
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: f4a30d19e111d395088e38c4543c9dacee6105fd
ms.lasthandoff: 03/13/2017

---

# <a name="publishing-your-hello-world-application-with-visual-studio-2017"></a>Publicación de la aplicación Hola a todos con Visual Studio 2017

En [Building a C# Hello World application with .NET Core in Visual Studio 2017](with-visual-studio-2017.md) (Compilación de una aplicación Hola a todos en C# con .NET Core en Visual Studio 2017), creó la aplicación de consola Hola a todos y en [Depuración de la aplicación Hola a todos en C# con Visual Studio 2017](debugging-with-visual-studio-2017.md), la probó usando el depurador de Visual Studio. Ahora que está seguro de que funciona como se esperaba, puede publicarla para que otros usuarios puedan ejecutarla. Al realizar la publicación, se crea el conjunto de archivos necesarios para ejecutar la aplicación; puede implementarlos mediante su copia en un equipo de destino.

Para publicar y ejecutar la aplicación: 

1. Asegúrese de que Visual Studio esté compilando la versión de lanzamiento de la aplicación. Si es necesario, cambie la configuración de compilación en la barra de herramientas de **Depurar** a **Versión**, como se muestra en la ilustración siguiente.

   ![Imagen](media/release.jpg)

1. Abra una ventana de consola. Por ejemplo, en el cuadro de texto **Pregúntame cualquier cosa** de la barra de tareas de Windows, escriba `Command Prompt` y, a continuación, elija la aplicación de escritorio **Símbolo del sistema** para abrir la ventana de consola.

1. Haga clic con el botón derecho en el proyecto Hola a todos (no en la solución Hola a todos) y seleccione **Publicar** en el menú. También puede seleccionar **Publicar Hola a todos** en el menú principal **Compilar** de Visual Studio.

1. Cuando aparezca el cuadro de diálogo **Publicar** que se muestra en la siguiente ilustración, cree un nuevo perfil de publicación, para ello, seleccione **Crear nuevo perfil**.

1. En el diálogo **Pick a publishing target** (Seleccionar un destino de publicación) que se muestra en la siguiente ilustración, seleccione el botón **Aceptar** para publicar la aplicación en el sistema de archivos local. Se encontrará en el subdirectorio bin\release\PublishOutput del directorio del proyecto de la aplicación.

1. Ahora que ha creado un perfil de publicación, seleccione el botón **Publicar** en el cuadro de diálogo **Publicar** que se muestra en la siguiente ilustración.

   ![Imagen](media/publish-2.jpg)

1. Como se muestra en la siguiente ilustración, el resultado publicado incluye los tres archivos siguientes que forman la aplicación y que puede implementar mediante su copia en un sistema de destino:

      - HelloWorld.dll
   
      - HelloWorld.deps.json

      - HelloWorld.runtimeconfig.json

   Un cuarto archivo, HelloWorld.pdb, contiene símbolos de depuración. No es necesario distribuir el archivo junto con su aplicación, aunque se debe guardar en caso de que necesite depurar la versión publicada de la aplicación.

   ![Imagen](media/pub-files.jpg)

El proceso de publicación crea una implementación dependiente del marco; la aplicación publicada se ejecutará en cualquier plataforma compatible con .NET Core, siempre que .NET Core esté instalado en el sistema. Los usuarios pueden ejecutar la aplicación mediante la emisión del comando `dotnet.exe HelloWorld.dll` desde una ventana de consola.

Para más información sobre cómo publicar e implementar aplicaciones de .NET Core, consulte [Implementación de aplicaciones .NET Core](../../core/deploying/index.md).
