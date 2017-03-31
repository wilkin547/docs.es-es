---
title: "Creación de una biblioteca de clases con C# y .NET Core en Visual Studio 2017"
description: Aprenda a crear una biblioteca de clases escrita en C# con Visual Studio de 2017.
keywords: .NET Core, biblioteca de clases de .NET Standard, Visual Studio 2017
author: stevehoag
ms.author: shoag
ms.date: 11/16/2016
ms.topic: article
ms.prod: .net-core
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: c849ca26-6a25-4d35-9544-f343af88e0e7
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 28fa60cdcf8e0056314af271208759eadd8503a5
ms.lasthandoff: 03/13/2017

---

# <a name="building-a-class-library-with-c-and-net-core-in-visual-studio-2017"></a>Creación de una biblioteca de clases con C# y .NET Core en Visual Studio 2017 #

Una biblioteca de clases define los tipos y los métodos a los que se puede llamar desde cualquier aplicación. Una biblioteca de clases desarrollada con .NET Core es compatible con la biblioteca de .NET Standard, lo que permite que cualquier plataforma .NET que admita esa versión de la biblioteca de .NET Standard pueda llamar a su biblioteca. Cuando termine la biblioteca de clases, puede decidir si quiera distribuirla como un componente de terceros o si la va a incluir como un componente empaquetado con una o varias aplicaciones.

> [!NOTE]
> Para ver una lista de las versiones de .NET Standard y las plataformas que admiten, consulte [Biblioteca estándar de .NET](../../standard/library.md).

En este tema, vamos a crear una sencilla biblioteca de utilidades que contiene un único método de control de cadenas. La implementaremos como un [método de extensión](../../csharp/programming-guide/classes-and-structs/extension-methods.md) de modo que se le pueda llamar como si fuera un miembro de la clase @System.String.

## <a name="creating-a-class-library-solution"></a>Creación de una solución de biblioteca de clases ##

Vamos a comenzar creando una solución para su proyecto de biblioteca de clases y sus proyectos relacionados. Una solución de Visual Studio solo sirve como contenedor de uno o varios proyectos. Para crear la solución:

1. En la barra de menús de Visual Studio, elija **Archivo**, **Nuevo**, **Proyecto**.

1. En el diálogo **Nuevos proyectos**, expanda el nodo **Otros tipos de proyectos** y elija **Soluciones de Visual Studio**, como se muestra en la siguiente ilustración.

   ![Imagen](./media/solution.jpg)

1. Asigne a la solución el nombre "ClassLibraryProjects" y elija el botón **Aceptar**. En la siguiente ilustración se muestra el resultado.

   ![Imagen](./media/vs_with_solution.jpg)

## <a name="creating-the-class-library-project"></a>Creación del proyecto de biblioteca de clases ##

Ahora podemos crear nuestro proyecto de biblioteca de clases:

1. En el **Explorador de soluciones**, abra el menú contextual del nodo **ClassLibraryProjects** y elija **Agregar**, **Nuevo proyecto**.

1. En el diálogo **Agregar nuevo proyecto**, elija el nodo **.NET Core** y luego la plantilla de proyecto **Biblioteca de clases (.NET Standard)**.

1. En el cuadro de texto **Nombre**, escriba "StringLibrary" como nombre del proyecto, como se muestra en la siguiente ilustración.

   ![Imagen](./media/lib_project.jpg)

1. Elija **Aceptar** para crear el proyecto de biblioteca de clases. En la siguiente ilustración se muestra el resultado.

   ![Imagen](./media/class_library.jpg)

1. Reemplace el código de la ventana de código por el código siguiente:

   [!CODE-csharp[ClassLib#1](../../../samples/snippets/csharp/getting_started/with_visual_studio_2017/classlib.cs#1)]

   la biblioteca de clases, `UtilityLibraries.StringLibrary`, contiene un método llamado `StartsWithUpper`, que devuelve un valor @System.Boolean que indica si la instancia de cadena actual comienza con un carácter en mayúscula. El estándar Unicode define qué caracteres están en mayúsculas. En .NET Core, el método [Char.IsUpper](xref:System.Char.IsUpper(System.Char)) devuelve `true` si un carácter está en mayúscula.

1. En la barra de menús, elija **Compilar**, **Compilar solución**. El proyecto se debería compilar sin errores.

## <a name="the-next-step"></a>Siguiente paso ##

Hasta el momento, hemos creado correctamente la biblioteca. Sin embargo, como no hemos llamado a ninguno de sus métodos, no sabemos si funciona como estaba previsto. El siguiente paso en el desarrollo de nuestra biblioteca consiste en probarla mediante un [proyecto de prueba unitaria en C#](testing-library-with-visual-studio.md).



