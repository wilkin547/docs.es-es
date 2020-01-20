---
title: Creación de una biblioteca de clases de .NET Standard en Visual Studio
description: Obtenga información sobre cómo crear una biblioteca de clases de .NET Standard escrita en C# o Visual Basic con Visual Studio
ms.date: 12/09/2019
ms.custom: vs-dotnet
ms.openlocfilehash: 748a1499e0c3a4a41613a69b715dbcfbd585bfe3
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714019"
---
# <a name="build-a-net-standard-library-in-visual-studio"></a>Creación de una de .NET Standard en Visual Studio

Una *biblioteca de clases* define los tipos y los métodos que se llaman desde una aplicación. Una biblioteca de clases que tiene como destino .NET Standard 2.0, lo que permite que cualquier implementación .NET que admita esa versión de .NET Standard pueda llamar a su biblioteca. Cuando termine la biblioteca de clases, puede decidir si quiere distribuirla como un componente de terceros o si la quiere incluir como un componente empaquetado con una o varias aplicaciones.

> [!NOTE]
> Para ver una lista de las versiones de .NET Standard y las plataformas que admiten, vea [.NET Standard](../../standard/net-standard.md).

En este tema, se creará una sencilla biblioteca de utilidades que contiene un único método de control de cadenas. Se implementará como un [método de extensión](../../csharp/programming-guide/classes-and-structs/extension-methods.md) de modo que se pueda llamar como si fuera un miembro de la clase <xref:System.String>.

## <a name="create-a-visual-studio-solution"></a>Creación de una solución de Visual Studio

Empiece por crear una solución en blanco para colocar el proyecto de biblioteca de clases en ella. Una solución de Visual Studio sirve como contenedor de uno o varios proyectos. Agregará proyectos adicionales relacionados a la misma solución si continúa con la serie de tutoriales.

Para crear la solución en blanco:

1. Abra Visual Studio.

2. En la ventana de inicio, elija **Crear un proyecto nuevo**.

3. En el cuadro de búsqueda de la página **Crear un nuevo proyecto**, escriba **solución**. Elija la plantilla **Solución en blanco** y luego seleccione **Siguiente**.

   ![Plantilla Solución en blanco en Visual Studio](media/library-with-visual-studio/blank-solution.png)

4. En la página **Configure el nuevo proyecto**, escriba **ClassLibraryProjects** en el cuadro **Nombre del proyecto**. Luego, elija **Crear**.

> [!TIP]
> También puede omitir este paso y dejar que Visual Studio cree la solución automáticamente al crear el proyecto en el paso siguiente. Busque las opciones de la solución en la página **Configure el nuevo proyecto**.

## <a name="create-a-class-library-project"></a>Crear un proyecto de biblioteca de clases

<!-- markdownlint-disable MD025 -->

# <a name="ctabcsharp"></a>[C#](#tab/csharp)

1. Agregue un nuevo proyecto de biblioteca de clases de .NET Standard para C# denominado "StringLibrary" a la solución.

   1. Haga clic con el botón derecho en la solución en el **Explorador de soluciones** y seleccione **Agregar** > **Nuevo proyecto**.

   1. En el cuadro de búsqueda de la página **Agregar un nuevo proyecto**, escriba **biblioteca**. Elija **C#** en la lista de lenguajes y, luego, **Todas las plataformas** en la lista de plataformas. Elija la plantilla **Biblioteca de clases (.NET Standard)** y, luego, **siguiente**.

   1. En la página **Configure el nuevo proyecto**, escriba **StringLibrary** en el cuadro **Nombre del proyecto**. Luego, elija **Crear**.

1. Asegúrese de que la biblioteca tiene como destino la versión correcta de .NET Standard. Haga clic con el botón derecho en el proyecto de biblioteca en el **Explorador de soluciones** y, luego, seleccione **Propiedades**. El cuadro de texto **Plataforma de destino** muestra que el proyecto tiene como destino .NET Standard 2.0.

   ![Propiedades del proyecto para la biblioteca de clases](./media/library-with-visual-studio/library-project-properties.png)

1. Reemplace el código de la ventana de código por el código siguiente y guarde el archivo:

   [!CODE-csharp[ClassLib#1](../../../samples/snippets/csharp/getting_started/with_visual_studio_2017/classlib.cs)]

   La biblioteca de clases, `UtilityLibraries.StringLibrary`, contiene un método denominado `StartsWithUpper`. Este método devuelve un valor <xref:System.Boolean> que indica si la instancia de cadena actual comienza con un carácter en mayúscula. El estándar Unicode distingue caracteres en mayúsculas de caracteres en minúsculas. El método <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> devuelve `true` si un carácter está en mayúsculas.

1. En la barra de menús, seleccione **Compilar** > **Compilar solución**.

# <a name="visual-basictabvb"></a>[Visual Basic](#tab/vb)

1. Agregue un nuevo proyecto de biblioteca de clases de .NET Standard para Visual Basic denominado "StringLibrary" a la solución.

   1. Haga clic con el botón derecho en la solución en el **Explorador de soluciones** y seleccione **Agregar** > **Nuevo proyecto**.

   1. En el cuadro de búsqueda de la página **Agregar un nuevo proyecto**, escriba **biblioteca**. Elija **Visual Basic** en la lista de lenguajes y luego, **Todas las plataformas** en la lista de plataformas. Elija la plantilla **Biblioteca de clases (.NET Standard)** y, luego, **siguiente**.

   1. En la página **Configure el nuevo proyecto**, escriba **StringLibrary** en el cuadro **Nombre del proyecto**. Luego, elija **Crear**.

1. Asegúrese de que la biblioteca tiene como destino la versión correcta de .NET Standard. Haga clic con el botón derecho en el proyecto de biblioteca en el **Explorador de soluciones** y, luego, seleccione **Propiedades**. El cuadro de texto **Plataforma de destino** muestra que el proyecto tiene como destino .NET Standard 2.0.

   ![Propiedades del proyecto para la biblioteca de clases](./media/library-with-visual-studio/vb/library-project-properties.png)

1. En el cuadro de diálogo **Propiedades**, borre el texto del cuadro de texto **Espacio de nombres raíz**. En cada proyecto, Visual Basic crea automáticamente un espacio de nombres que corresponde al nombre del proyecto. En este tutorial, definirá un espacio de nombres de nivel superior mediante la palabra clave [`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md) en el archivo de código.

1. Reemplace el código de la ventana de código por el código siguiente y guarde el archivo:

   [!CODE-vb[ClassLib#1](../../../samples/snippets/core/tutorials/vb-library-with-visual-studio/stringlibrary.vb)]

   La biblioteca de clases, `UtilityLibraries.StringLibrary`, contiene un método denominado `StartsWithUpper`. Este método devuelve un valor <xref:System.Boolean> que indica si la instancia de cadena actual comienza con un carácter en mayúscula. El estándar Unicode distingue caracteres en mayúsculas de caracteres en minúsculas. El método <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> devuelve `true` si un carácter está en mayúsculas.

1. En la barra de menús, seleccione **Compilar** > **Compilar solución**.

---

   El proyecto se debería compilar sin errores.

## <a name="next-steps"></a>Pasos siguientes

La biblioteca se ha creado correctamente. Como no se ha llamado a ninguno de los métodos, no se sabe si funciona como estaba previsto. El siguiente paso en el desarrollo de la biblioteca consiste en probarla.

> [!div class="nextstepaction"]
> [Crear un proyecto de prueba unitaria](testing-library-with-visual-studio.md)
