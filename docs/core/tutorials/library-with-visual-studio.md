---
title: Creación de una biblioteca de clases de .NET con Visual Studio
description: Obtenga información sobre cómo crear una biblioteca de clases de .NET mediante Visual Studio.
ms.date: 08/07/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet,contperf-fy21q1
ms.openlocfilehash: 2d9b02a155c950b77565a66417948568f5fa039f
ms.sourcegitcommit: d0990c1c1ab2f81908360f47eafa8db9aa165137
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2020
ms.locfileid: "97513125"
---
# <a name="tutorial-create-a-net-class-library-using-visual-studio"></a>Tutorial: Creación de una biblioteca de clases de .NET con Visual Studio

En este tutorial, creará una sencilla clases de utilidades que contiene un único método de control de cadenas.

Una *biblioteca de clases* define los tipos y los métodos que se llaman desde una aplicación. Si la biblioteca tiene como destino .NET Standard 2.0, se puede llamar mediante cualquier implementación de .NET (incluido .NET Framework) que admita .NET Standard 2.0. Si la biblioteca tiene como destino .NET 5, la puede llamar cualquier aplicación que tenga como destino .NET 5. En este tutorial se muestra cómo seleccionar .NET 5 como destino.

Al crear una biblioteca de clases, puede distribuirla como un paquete NuGet o un componente empaquetado con la aplicación en la que se usa.

## <a name="prerequisites"></a>Prerrequisitos

- [Visual Studio 2019, versión 16.8 o posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) con la carga de trabajo **Desarrollo multiplataforma de .NET Core** instalada. El SDK de .NET 5.0 se instala automáticamente al seleccionar esta carga de trabajo. En este tutorial se asume que ha habilitado **Mostrar todas las plantillas de .NET Core en el nuevo proyecto**, como se muestra en [Tutorial: Creación de una aplicación de consola de .NET con Visual Studio](with-visual-studio.md).

## <a name="create-a-solution"></a>Crear una solución

Empiece por crear una solución en blanco para colocar el proyecto de biblioteca de clases en ella. Una solución de Visual Studio sirve como contenedor de uno o varios proyectos. Agregará otros proyectos relacionados a la misma solución.

Para crear la solución en blanco:

1. Inicie Visual Studio.

2. En la ventana de inicio, elija **Crear un proyecto nuevo**.

3. En el cuadro de búsqueda de la página **Crear un nuevo proyecto**, escriba **solución**. Elija la plantilla **Solución en blanco** y luego seleccione **Siguiente**.

   :::image type="content" source="media/library-with-visual-studio/blank-solution.png" alt-text="Plantilla Solución en blanco en Visual Studio":::

4. En la página **Configure el nuevo proyecto**, escriba **ClassLibraryProjects** en el cuadro **Nombre del proyecto**. Luego, elija **Crear**.

## <a name="create-a-class-library-project"></a>Crear un proyecto de biblioteca de clases

1. Agregue un nuevo proyecto de biblioteca de clases de .NET denominado "StringLibrary" a la solución.

   1. Haga clic con el botón derecho en la solución en el **Explorador de soluciones** y seleccione **Agregar** > **Nuevo proyecto**.

   1. En el cuadro de búsqueda de la página **Agregar un nuevo proyecto**, escriba **biblioteca**. En la lista de lenguajes, elija **C#** o **Visual Basic** y, luego, en la lista de plataformas, elija **Todas las plataformas**. Elija la plantilla **Biblioteca de clases** y luego **Siguiente**.

   1. En la página **Configurar el nuevo proyecto**, escriba **StringLibrary** en el cuadro **Nombre del proyecto** y, después, seleccione **Siguiente**.

   1. En la página **Información adicional**, seleccione **.NET 5.0 (actual)** y después **Crear**.

1. Asegúrese de que la biblioteca tiene como destino la versión correcta de .NET. Haga clic con el botón derecho en el proyecto de biblioteca en el **Explorador de soluciones** y, luego, seleccione **Propiedades**. En el cuadro de texto **Plataforma de destino** se muestra que el proyecto tiene como destino .NET 5.0.

1. Si usa Visual Basic, borre el texto del cuadro de texto **Espacio de nombres raíz**.

   :::image type="content" source="./media/library-with-visual-studio/vb/library-project-properties.png" alt-text="Propiedades del proyecto para la biblioteca de clases":::

   En cada proyecto, Visual Basic crea automáticamente un espacio de nombres que corresponde al nombre del proyecto. En este tutorial, definirá un espacio de nombres de nivel superior mediante la palabra clave [`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md) en el archivo de código.

1. Reemplace el código de la ventana de código por *Class1.cs* o *Class1.vb* y guarde el archivo. Si no se muestra el idioma que quiere usar, cambie el selector de idioma en la parte superior de la página.

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibrary/Class1.cs":::
   :::code language="vb" source="./snippets/library-with-visual-studio/vb/StringLibrary/Class1.vb":::

   La biblioteca de clases, `UtilityLibraries.StringLibrary`, contiene un método denominado `StartsWithUpper`. Este método devuelve un valor <xref:System.Boolean> que indica si la instancia de cadena actual comienza con un carácter en mayúscula. El estándar Unicode distingue caracteres en mayúsculas de caracteres en minúsculas. El método <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> devuelve `true` si un carácter está en mayúsculas.

   `StartsWithUpper` se implementa como un [método de extensión](../../csharp/programming-guide/classes-and-structs/extension-methods.md), de modo que se pueda llamar como si fuera un miembro de la clase <xref:System.String>.

1. En la barra de menú, seleccione **Compilar** > **Compilar solución**, o bien presione <kbd>Ctrl</kbd>+<kbd>Mayús</kbd>+<kbd>B</kbd>, para comprobar que el proyecto se compila sin errores.

## <a name="add-a-console-app-to-the-solution"></a>Incorporación de una aplicación de consola a la solución

Agregue una aplicación de consola que use la biblioteca de clases. La aplicación solicitará al usuario que escriba una cadena y notificará si la cadena comienza con un carácter en mayúsculas.

1. Agregue una nueva aplicación de consola de .NET denominada "ShowCase" a la solución.

   1. Haga clic con el botón derecho en la solución en el **Explorador de soluciones** y seleccione **Agregar** > **Nuevo proyecto**.

   1. En el cuadro de búsqueda de la página **Agregar un nuevo proyecto**, escriba **consola**. Elija **C#** o **Visual Basic** en la lista de lenguajes y luego, **Todas las plataformas** en la lista de plataformas.

   1. Elija la plantilla **Aplicación de consola** y, después, seleccione **Siguiente**.

   1. En la página **Configure el nuevo proyecto**, escriba **ShowCase** en el cuadro **Nombre del proyecto**. Después, haga clic en **Siguiente**.

   1. En la página **Información adicional**, seleccione **.NET 5.0 (actual)** en el cuadro **Plataforma de destino**. Luego, elija **Crear**.

1. En la ventana de código del archivo *Program.cs* o *Program.vb*, reemplace todo el código con el siguiente código.

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/ShowCase/Program.cs":::
   :::code language="vb" source="./snippets/library-with-visual-studio/vb/ShowCase/Program.vb":::

   El código usa la variable `row` para mantener un recuento del número de filas de datos escritas en la ventana de consola. Siempre que sea mayor o igual a 25, el código borra la ventana de consola y muestra un mensaje al usuario.

   El programa le pide al usuario que escriba una cadena. Indica si la cadena comienza con un carácter en mayúsculas. Si el usuario presiona la tecla <kbd>Entrar</kbd> sin especificar una cadena, la aplicación finaliza y la ventana de la consola se cierra.

## <a name="add-a-project-reference"></a>Agregar una referencia de proyecto

En un principio, el nuevo proyecto de aplicación de consola no tiene acceso a la biblioteca de clases. Para que pueda llamar a los métodos de la biblioteca de clases, cree una referencia de proyecto al proyecto de biblioteca de clases.

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el nodo **Dependencias** del proyecto `ShowCase` y seleccione **Agregar referencia de proyecto**.

   :::image type="content" source="media/library-with-visual-studio/add-reference-context-menu.png" alt-text="Menú contextual Agregar referencia de Visual Studio":::

1. En el cuadro de diálogo **Administrador de referencias**, seleccione el proyecto **StringLibrary** y después **Aceptar**.

   :::image type="content" source="media/library-with-visual-studio/manage-project-references.png" alt-text="Cuadro de diálogo Administrador de referencias con StringLibrary seleccionado":::

## <a name="run-the-app"></a>Ejecutar la aplicación

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **Presentación** y seleccione **Establecer como proyecto de inicio** en el menú contextual.

   :::image type="content" source="media/library-with-visual-studio/set-startup-project-context-menu.png" alt-text="Menú contextual del proyecto de Visual Studio para establecer el proyecto de inicio":::

1. Presione <kbd>CTRL</kbd>+<kbd>F5</kbd> para compilar y ejecutar el programa sin depuración.

   :::image type="content" source="media/library-with-visual-studio/visual-studio-project-toolbar.png" alt-text="Barra de herramientas del proyecto de Visual Studio en la que se muestra el botón Depurar":::

1. Para probar el programa, escriba cadenas y presione <kbd>Entrar</kbd> y, después, presione <kbd>Entrar</kbd> para salir.

   :::image type="content" source="media/library-with-visual-studio/run-showcase.png" alt-text="Ventana de la consola con ShowCase en ejecución":::

## <a name="additional-resources"></a>Recursos adicionales

* [Desarrollo de bibliotecas con la CLI de .NET](libraries.md)
* [Versiones de .NET Standard y las plataformas que admiten](../../standard/net-standard.md).

## <a name="next-steps"></a>Pasos siguientes

En este tutorial, ha creado una prueba unitaria de una biblioteca de clases. En el siguiente tutorial, aprenderá a hacer una prueba unitaria de la biblioteca de clases.

> [!div class="nextstepaction"]
> [Prueba unitaria de una biblioteca de clases de .NET con Visual Studio](testing-library-with-visual-studio.md)

También puede omitir las pruebas unitarias automatizadas y aprender a compartir la biblioteca mediante la creación de un paquete NuGet:

> [!div class="nextstepaction"]
> [Crear y publicar un paquete con Visual Studio](/nuget/quickstart/create-and-publish-a-package-using-visual-studio)

También puede obtener más información sobre cómo publicar una aplicación de consola. Si publica la aplicación de consola a partir de la solución que ha creado en este tutorial, la biblioteca de clases lo incluirá como un archivo *.dll*.

> [!div class="nextstepaction"]
> [Publicación de una aplicación de consola de .NET con Visual Studio](publishing-with-visual-studio.md)
