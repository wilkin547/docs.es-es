---
title: "Creación de una biblioteca de clases con C# y .NET Core en Visual Studio 2017 | Microsoft Docs"
description: Aprenda a crear una biblioteca de clases escrita en C# con Visual Studio de 2017.
keywords: .NET Core, biblioteca de clases de .NET Standard, Visual Studio 2017
author: BillWagner
ms.author: wiwagn
ms.date: 04/17/2017
ms.topic: article
ms.prod: .net-core
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: c849ca26-6a25-4d35-9544-f343af88e0e7
ms.translationtype: Human Translation
ms.sourcegitcommit: 9cd469dfd4f38605f1455c008388ad04c366e484
ms.openlocfilehash: c29c4d2d1332fbf9e9e162e671200384a930aff1
ms.contentlocale: es-es
ms.lasthandoff: 06/20/2017

---

<a id="building-a-class-library-with-c-and-net-core-in-visual-studio-2017" class="xliff"></a>

# Creación de una biblioteca de clases con C# y .NET Core en Visual Studio 2017

Una *biblioteca de clases* define los tipos y los métodos que se llaman desde una aplicación. Una biblioteca de clases desarrollada con .NET Core es compatible con la biblioteca de .NET Standard, lo que permite que cualquier plataforma .NET que admita esa versión de la biblioteca de .NET Standard pueda llamar a su biblioteca. Cuando termine la biblioteca de clases, puede decidir si quiere distribuirla como un componente de terceros o si la quiere incluir como un componente empaquetado con una o varias aplicaciones.

> [!NOTE]
> Para ver una lista de las versiones de .NET Standard y las plataformas que admiten, vea [.NET Standard](../../standard/net-standard.md).

En este tema, se creará una sencilla biblioteca de utilidades que contiene un único método de control de cadenas. Se implementará como un [método de extensión](../../csharp/programming-guide/classes-and-structs/extension-methods.md) de modo que se pueda llamar como si fuera un miembro de la clase @System.String.

<a id="creating-a-class-library-solution" class="xliff"></a>

## Creación de una solución de biblioteca de clases

Para empezar, se crea una solución para el proyecto de biblioteca de clases y sus proyectos relacionados. Una solución de Visual Studio solo sirve como contenedor de uno o varios proyectos. Para crear la solución:

1. En la barra de menús de Visual Studio, elija **Archivo** > **Nuevo** > **Proyecto**.

1. En el cuadro de diálogo **Nuevo proyecto**, expanda el nodo **Otros tipos de proyectos** y seleccione **Soluciones de Visual Studio**. Asigne a la solución el nombre "ClassLibraryProjects" y pulse el botón **Aceptar**.

   ![Cuadro de diálogo Nuevo proyecto](./media/library-with-visual-studio/newproject.png)

<a id="creating-the-class-library-project" class="xliff"></a>

## Creación del proyecto de biblioteca de clases

Crear el proyecto de biblioteca de clases:

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el archivo de solución **ClassLibraryProjects** y seleccione **Agregar** > **Nuevo proyecto** en el menú contextual.

1. En el cuadro de diálogo **Agregar nuevo proyecto**, seleccione el nodo **.NET Core** seguido por la plantilla del proyecto **Biblioteca de clases (.NET Core)**. En el cuadro de texto **Nombre**, escriba "StringLibrary" como nombre del proyecto. Pulse **Aceptar** para crear el proyecto de biblioteca de clases.

   ![Cuadro de diálogo Agregar nuevo proyecto](./media/library-with-visual-studio/libproject.png)

   ![Ventana de aplicación de Visual Studio que muestra el código de plantilla de biblioteca de clases predeterminado](./media/library-with-visual-studio/stringlibrary.png)

1. Reemplace el código de la ventana de código por el código siguiente y guarde el archivo:

   [!CODE-csharp[ClassLib#1](../../../samples/snippets/csharp/getting_started/with_visual_studio_2017/classlib.cs#1)]

   la biblioteca de clases, `UtilityLibraries.StringLibrary`, contiene un método llamado `StartsWithUpper`, que devuelve un valor @System.Boolean que indica si la instancia de cadena actual comienza con un carácter en mayúscula. El estándar Unicode distingue caracteres en mayúsculas de caracteres en minúsculas. En .NET Core, el método [`Char.IsUpper`](xref:System.Char.IsUpper(System.Char)) devuelve `true` si un carácter está en mayúsculas.

1. En la barra de menús, seleccione **Compilar** > **Compilar solución**. El proyecto se debería compilar sin errores.

   ![Panel de salida que muestra que la compilación se ha realizado correctamente](./media/library-with-visual-studio/buildsucceeds.png)

<a id="next-step" class="xliff"></a>

## Paso siguiente

La biblioteca se ha creado correctamente. Como no se ha llamado a ninguno de los métodos, no se sabe si funciona como estaba previsto. El siguiente paso en el desarrollo de la biblioteca consiste en probarla mediante un [proyecto de prueba unitaria en C#](testing-library-with-visual-studio.md).

