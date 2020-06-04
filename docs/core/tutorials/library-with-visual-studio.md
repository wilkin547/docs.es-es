---
title: Creación de una biblioteca de clases de .NET Standard en Visual Studio
description: Obtenga información sobre cómo crear una biblioteca de clases de .NET Standard mediante Visual Studio.
ms.date: 05/21/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 2afe11ad75fc36a67efed48d56dbafb11bceaf2a
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84005290"
---
# <a name="tutorial-create-a-net-standard-library-in-visual-studio"></a>Tutorial: Creación de una biblioteca de .NET Standard en Visual Studio

Una *biblioteca de clases* define los tipos y los métodos que se llaman desde una aplicación. Una biblioteca de clases que tiene como destino .NET Standard 2.0, lo que permite que cualquier implementación .NET que admita esa versión de .NET Standard pueda llamar a su biblioteca. Cuando termine la biblioteca de clases, puede decidir si quiere distribuirla como un componente de terceros o si la quiere incluir como un componente empaquetado con una o varias aplicaciones.

> [!NOTE]
> Para ver una lista de las versiones de .NET Standard y las plataformas que admiten, vea [.NET Standard](../../standard/net-standard.md).

En este tutorial, creará una sencilla biblioteca de utilidades que contiene un único método de control de cadenas. Lo implementará como un [método de extensión](../../csharp/programming-guide/classes-and-structs/extension-methods.md) de modo que se pueda llamar como si fuera un miembro de la clase <xref:System.String>.

## <a name="prerequisites"></a>Requisitos previos

- [Visual Studio 2019, versión 16.6 o posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) con la carga de trabajo **Desarrollo multiplataforma de .NET Core** instalada. El SDK de .NET Core 3.1 se instala automáticamente al seleccionar esta carga de trabajo.

  Para más información, consulte la sección [Instalación con Visual Studio](../install/sdk.md?pivots=os-windows#install-with-visual-studio) del artículo [Instalación del SDK de .NET Core](../install/sdk.md?pivots=os-windows).

## <a name="create-a-visual-studio-solution"></a>Creación de una solución de Visual Studio

Empiece por crear una solución en blanco para colocar el proyecto de biblioteca de clases en ella. Una solución de Visual Studio sirve como contenedor de uno o varios proyectos. Agregará otros proyectos relacionados a la misma solución.

Para crear la solución en blanco:

1. Abra Visual Studio.

2. En la ventana de inicio, elija **Crear un proyecto nuevo**.

3. En el cuadro de búsqueda de la página **Crear un nuevo proyecto**, escriba **solución**. Elija la plantilla **Solución en blanco** y luego seleccione **Siguiente**.

   ![Plantilla Solución en blanco en Visual Studio](media/library-with-visual-studio/blank-solution.png)

4. En la página **Configure el nuevo proyecto**, escriba **ClassLibraryProjects** en el cuadro **Nombre del proyecto**. Luego, elija **Crear**.

## <a name="create-a-class-library-project"></a>Crear un proyecto de biblioteca de clases

1. Agregue un nuevo proyecto de biblioteca de clases de .NET Standard denominado "StringLibrary" a la solución.

   1. Haga clic con el botón derecho en la solución en el **Explorador de soluciones** y seleccione **Agregar** > **Nuevo proyecto**.

   1. En el cuadro de búsqueda de la página **Agregar un nuevo proyecto**, escriba **biblioteca**. En la lista de lenguajes, elija **C#** o **Visual Basic** y, luego, en la lista de plataformas, elija **Todas las plataformas**. Elija la plantilla **Biblioteca de clases (.NET Standard)** y, luego, **siguiente**.

   1. En la página **Configure el nuevo proyecto**, escriba **StringLibrary** en el cuadro **Nombre del proyecto**. Luego, elija **Crear**.

1. Asegúrese de que la biblioteca tiene como destino la versión correcta de .NET Standard. Haga clic con el botón derecho en el proyecto de biblioteca en el **Explorador de soluciones** y, luego, seleccione **Propiedades**. El cuadro de texto **Plataforma de destino** muestra que el proyecto tiene como destino .NET Standard 2.0.

   ![Propiedades del proyecto para la biblioteca de clases](./media/library-with-visual-studio/library-project-properties.png)

1. Si usa Visual Basic, borre el texto del cuadro de texto **Espacio de nombres raíz**.

   ![Propiedades del proyecto para la biblioteca de clases](./media/library-with-visual-studio/vb/library-project-properties.png)

   En cada proyecto, Visual Basic crea automáticamente un espacio de nombres que corresponde al nombre del proyecto. En este tutorial, definirá un espacio de nombres de nivel superior mediante la palabra clave [`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md) en el archivo de código.

1. Reemplace el código de la ventana de código por *Class1.cs* o *Class1.vb* y guarde el archivo. Si no se muestra el idioma que quiere usar, cambie el selector de idioma en la parte superior de la página.

   [!code-csharp[](../../../samples/snippets/csharp/getting_started/with_visual_studio_2017/classlib.cs)]
   [!code-vb[](../../../samples/snippets/core/tutorials/vb-library-with-visual-studio/stringlibrary.vb)]

   La biblioteca de clases, `UtilityLibraries.StringLibrary`, contiene un método denominado `StartsWithUpper`. Este método devuelve un valor <xref:System.Boolean> que indica si la instancia de cadena actual comienza con un carácter en mayúscula. El estándar Unicode distingue caracteres en mayúsculas de caracteres en minúsculas. El método <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> devuelve `true` si un carácter está en mayúsculas.

1. En la barra de menús, seleccione **Compilar** > **Compilar solución** para comprobar que el proyecto se compila sin errores.

## <a name="add-a-console-app-to-the-solution"></a>Incorporación de una aplicación de consola a la solución

Use la biblioteca de clases en una aplicación de consola que pida al usuario que escriba una cadena e indique si la cadena comienza con un carácter en mayúsculas.

1. Agregue una nueva aplicación de consola de .NET Core denominada "Showcase" a la solución.

   1. Haga clic con el botón derecho en la solución en el **Explorador de soluciones** y seleccione **Agregar** > **Nuevo proyecto**.

   1. En el cuadro de búsqueda de la página **Agregar un nuevo proyecto**, escriba **consola**. Elija **C#** o **Visual Basic** en la lista de lenguajes y luego, **Todas las plataformas** en la lista de plataformas.

   1. Elija la plantilla **Aplicación de consola (.NET Core)** y haga clic en **Siguiente**.

   1. En la página **Configure el nuevo proyecto**, escriba **ShowCase** en el cuadro **Nombre del proyecto**. Luego, elija **Crear**.

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **Presentación** y seleccione **Establecer como proyecto de inicio** en el menú contextual.

   ![Menú contextual del proyecto de Visual Studio para establecer el proyecto de inicio](media/library-with-visual-studio/set-startup-project-context-menu.png)

1. En un principio, el nuevo proyecto de aplicación de consola no tiene acceso a la biblioteca de clases. Para que pueda llamar a los métodos de la biblioteca de clases, cree una referencia de proyecto al proyecto de biblioteca de clases. En el **Explorador de soluciones**, haga clic con el botón derecho en el nodo **Dependencias** del proyecto `ShowCase` y seleccione **Agregar referencia de proyecto**.

   ![Menú contextual Agregar referencia de Visual Studio](media/library-with-visual-studio/add-reference-context-menu.png)

1. En el cuadro de diálogo **Administrador de referencias**, seleccione el proyecto **StringLibrary** y después **Aceptar**.

   ![Cuadro de diálogo Administrador de referencias con StringLibrary seleccionado](media/library-with-visual-studio/manage-project-references.png)

1. En la ventana de código del archivo *Program.cs* o *Program.vb*, reemplace todo el código con el siguiente código.

   [!code-csharp[UsingClassLib#1](~/samples/snippets/csharp/getting_started/with_visual_studio_2017/showcase.cs)]
   [!code-vb[UsingClassLib#1](~/samples/snippets/core/tutorials/vb-library-with-visual-studio/showcase.vb)]

   El código usa la variable `row` para mantener un recuento del número de filas de datos escritas en la ventana de consola. Siempre que sea mayor o igual a 25, el código borra la ventana de consola y muestra un mensaje al usuario.

   El programa le pide al usuario que escriba una cadena. Indica si la cadena comienza con un carácter en mayúsculas. Si el usuario presiona la tecla Entrar sin especificar una cadena, la aplicación finaliza y la ventana de la consola se cierra.

1. Si es necesario, cambie la barra de herramientas para compilar la versión de **depuración** del proyecto `ShowCase`. Compile y ejecute el programa haciendo clic en la flecha verde en el botón **Presentación**.

   ![Barra de herramientas del proyecto de Visual Studio en la que se muestra el botón Depurar](media/library-with-visual-studio/visual-studio-project-toolbar.png)

1. Para probar el programa, escriba cadenas y presione **Entrar** y, después, presione **Entrar** para salir.

   :::image type="content" source="media/library-with-visual-studio/run-showcase.png" alt-text="Ventana de la consola con ShowCase en ejecución":::

## <a name="next-steps"></a>Pasos siguientes

En este tutorial, ha creado una solución, ha agregado un proyecto de biblioteca y ha agregado un proyecto de aplicación de consola que usa la biblioteca. En el siguiente tutorial, agregará un proyecto de prueba unitaria a la solución.

> [!div class="nextstepaction"]
> [Prueba de una biblioteca .NET Standard con .NET Core en Visual Studio](testing-library-with-visual-studio.md)
