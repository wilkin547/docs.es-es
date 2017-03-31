---
title: Consumo de una biblioteca de clases con .NET Core en Visual Studio 2017
description: "Conozca más sobre cómo llamar a los miembros de una biblioteca de clases con Visual Studio 2017"
keywords: ".NET Core, biblioteca de clases de .NET Core, .NET Standard, distribución de biblioteca de clases de .NET Standard"
author: stevehoag
ms.author: shoag
ms.date: 11/16/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: d7b94076-1108-4174-94e7-a18f00072bb7
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 0b42eeb0149feec09ddacba98383da3abd53bb5e
ms.lasthandoff: 03/13/2017

---

# <a name="consuming-a-class-library-with-net-core-in-visual-studio-2017"></a>Consumo de una biblioteca de clases con .NET Core en Visual Studio 2017 #

Una vez que ha seguido los pasos indicados en [Building a C# class library with .NET Core in Visual Studio 2017](./library-with-visual-studio-2017.md) (Creación de una biblioteca de clases de C# con .NET Core en Visual Studio 2017) y en [Testing a class library with .NET Core in Visual Studio 2017](testing-library-with-visual-studio.md) (Prueba de una biblioteca de clases con .NET Core en Visual Studio de 2017) para compilar y probar su biblioteca de clases, y ha creado una versión de lanzamiento de la biblioteca, el paso siguiente consiste en hacer que esté disponible para los llamadores. Existen dos maneras de hacerlo:

- Si la biblioteca la va a usar una única solución (por ejemplo, si es un componente de una sola aplicación más grande), simplemente puede incluirla como proyecto en su solución.

- Si la biblioteca va a ser accesible con carácter general, puede distribuirla como un paquete NuGet.

## <a name="including-a-library-as-a-project-in-a-solution"></a>Inclusión de una biblioteca como proyecto en una solución ##

Así como incluimos pruebas unitarias en la misma solución que nuestra biblioteca de clases, podemos incluir nuestra aplicación como parte de esa solución. Por ejemplo, vamos a usar nuestra biblioteca de clases en una aplicación de consola que solicita al usuario que inserte una cadena e informa de si su primer carácter está en mayúsculas:

1. Abra la solución creada `ClassLibraryProjects` en el tema [Building a C# Class Library with .NET Core in Visual Studio 2017](./library-with-visual-studio-2017.md) (Creación de una biblioteca de clases de C# con .NET Core en Visual Studio 2017) y, en el Explorador de soluciones, abra el menú contextual del nodo **ClassLibraryProjects** y elija **Agregar**, **Nuevo proyecto**.

1. En el cuadro de diálogo **Agregar nuevo proyecto**, expanda los nodos **Visual C#** y **.NET Core** y elija la plantilla de proyecto **Aplicación de consola (.NET Core)**, como se muestra en la ilustración siguiente.

   ![Imagen](./media/use-library.jpg)

1. En el cuadro de diálogo **Nombre**, escriba `ShowCase` y elija el botón **Aceptar**.

1. En el Explorador de soluciones, abra el menú contextual para el nodo de proyecto **ShowCase** y elija **Establecer como proyecto de inicio**.

1. Inicialmente nuestro proyecto no tiene acceso a nuestra biblioteca de clases. Para que pueda llamar a métodos de nuestra biblioteca de clases, en el **Explorador de soluciones**, abra el menú contextual del nodo **Dependencias** en el proyecto **ShowCase** y elija **Agregar referencia**.

1. En el cuadro de diálogo **Administrador de referencias**, elija **StringLibrary**, nuestro proyecto de biblioteca de clases, tal como se muestra en la ilustración siguiente y, a continuación, elija el botón **Aceptar**.

   ![Imagen](./media/add-lib-ref.jpg)

1. En la ventana de código del archivo "program.cs", reemplace todo el código por el código siguiente:

 [!CODE-csharp[UsingClassLib#1](../../../samples/snippets/csharp/getting_started/with_visual_studio_2017/showcase.cs#1)]

   El código usa la propiedad [Console.WindowHeight](xref:System.Console.WindowHeight) para determinar cuántas filas tiene la ventana de consola. Siempre que la propiedad [Console.CursorTop](xref:System.Console.CursorTop) sea mayor o igual que el número total de filas de la ventana de consola, el código borra la ventana de consola y vuelve a mostrar un mensaje al usuario.

   El programa en sí solo le pide al usuario que inserte una cadena. Luego indica si la cadena comienza con un carácter en mayúsculas. Si el usuario presiona la tecla **Entrar** sin especificar una cadena, la ventana de consola se cierra y la aplicación finaliza.

1. Si lo cree necesario, cambie la barra de herramientas para compilar la versión de **depuración** del proyecto`ShowCase`, como se muestra en la siguiente ilustración.

   ![Imagen](./media/showcase-toolbar.jpg)

1. Compile y ejecute el programa haciendo clic en la flecha verde en el botón **ShowCase**.

La aplicación que usa esta biblioteca se puede depurar y finalmente publicar siguiendo los pasos indicados en [Debugging your C# Hello World Application with Visual Studio 2017](debugging-with-visual-studio-2017.md) (Depuración de la aplicación Hola a todos en C# con Visual Studio 2017) y [Publicación de la aplicación Hola a todos con Visual Studio 2017](publishing-with-visual-studio-2017.md).

## <a name="distributing-the-library-in-a-nuget-package"></a>Distribución de la biblioteca en un paquete NuGet ##

Puede hacer que su biblioteca de clases tenga una disponibilidad más amplia si la publica como un paquete NuGet. Visual Studio no admite la creación de paquetes NuGet. Para crear uno, debe usar la [`dotnet.exe`utilidad de línea de comandos](../../core/tools/dotnet.md) de la siguiente manera:

1. Abra una ventana de consola. Por ejemplo, en el cuadro de texto **Pregúntame cualquier cosa** de la barra de tareas de Windows, escriba `Command Prompt` y, a continuación, elija la aplicación de escritorio **Símbolo del sistema** para abrir la ventana de consola.

1. Vaya al directorio del proyecto de la biblioteca. Normalmente, a menos que haya reconfigurado la ubicación del archivo, está en el directorio `Documents\Visual Studio 2017\Projects\ClassLibraryProjects\StringLibrary`. El directorio contiene el código fuente y un archivo de proyecto `StringLibrary.csproj`.

1. Emita el comando `dotnet.exe pack --no-build`: La utilidad `dotnet.exe` genera un paquete con una extensión .nupkg.

   > [!TIP]
   > Si el directorio que contiene `dotnet.exe` no está en la ruta de acceso, puede encontrar su ubicación escribiendo `where dotnet.exe` en la ventana de consola.

Para más información sobre la creación de paquetes NuGet, consulte [Cómo crear un paquete NuGet con herramientas multiplataforma ](../../core/deploying/creating-nuget-packages.md).
