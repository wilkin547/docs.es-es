---
title: Creación de una biblioteca de clases de .NET Standard mediante Visual Studio para Mac
description: Obtenga información sobre cómo crear una biblioteca de clases de .NET Standard mediante Visual Studio para Mac.
ms.date: 06/08/2020
ms.openlocfilehash: 8e1e4ca3bc1b12d889b847d80318f3d6cd1bbe46
ms.sourcegitcommit: 3492dafceb5d4183b6b0d2f3bdf4a1abc4d5ed8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/16/2020
ms.locfileid: "86416007"
---
# <a name="tutorial-create-a-net-standard-library-using-visual-studio-for-mac"></a>Tutorial: Creación de una biblioteca de .NET Standard mediante Visual Studio para Mac

En este tutorial, creará una biblioteca de clases que contiene un único método de control de cadenas. Lo implementará como un [método de extensión](../../csharp/programming-guide/classes-and-structs/extension-methods.md) de modo que se pueda llamar como si fuera un miembro de la clase <xref:System.String>.

Una *biblioteca de clases* define los tipos y los métodos que se llaman desde una aplicación. Una biblioteca de clases que tenga como destino .NET Standard 2.1 puede usarse por una aplicación que tenga como destino cualquier implementación de .NET que admita la versión 2.1 de .NET Standard. Cuando termine la biblioteca de clases, puede distribuirla como un componente de terceros o como un componente empaquetado con una o varias aplicaciones.

> [!NOTE]
> Sus comentarios son muy importantes. Hay dos maneras de proporcionar comentarios al equipo de desarrollo de Visual Studio para Mac:
>
> - En Visual Studio para Mac, seleccione **Ayuda** > **Notificar un problema** en el menú o **Notificar un problema** desde la pantalla de bienvenida, que abre una ventana para presentar un informe de errores. Puede realizar un seguimiento de sus comentarios en el portal de la [Comunidad de desarrolladores](https://developercommunity.visualstudio.com/spaces/41/index.html).
> - Para hacer una sugerencia, seleccione **Ayuda** > **Aportar una sugerencia** en el menú o **Aportar una sugerencia** desde la pantalla de bienvenida, que le lleva a la [página web de la Comunidad de desarrolladores de Visual Studio para Mac](https://developercommunity.visualstudio.com/content/idea/post.html?space=41).

## <a name="prerequisites"></a>Requisitos previos

* [Instale Visual Studio para Mac, versión 8.6 o posterior](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link). Seleccione la opción para instalar .NET Core. La instalación de Xamarin es opcional para el desarrollo de .NET Core. Para obtener más información, vea los siguientes recursos:

  * [Tutorial: Instalación de Visual Studio para Mac](/visualstudio/mac/installation).
  * [Versiones de macOS compatibles](../install/dependencies.md?pivots=os-macos).
  * [Versiones de .NET Core compatibles con Visual Studio para Mac](/visualstudio/mac/net-core-support).

## <a name="create-a-solution-with-a-class-library-project"></a>Creación de una solución con un proyecto de biblioteca de clases

Una solución de Visual Studio sirve como contenedor de uno o varios proyectos. Creación de una solución y un proyecto de biblioteca de clases en la solución. Agregará otros proyectos relacionados a la misma solución más adelante.

1. Inicie Visual Studio para Mac:

1. En la ventana de inicio, seleccione **Nuevo proyecto**.

1. En el cuadro de diálogo **Nuevo proyecto**, en el nodo **Multiplataforma**, seleccione **Biblioteca** y luego seleccione la plantilla **Biblioteca de .NET Standard**. A continuación, seleccione **Siguiente**.

   :::image type="content" source="media/library-with-visual-studio-mac/visual-studio-mac-new-project.png" alt-text="Cuadro de diálogo Nuevo proyecto":::

1. En el cuadro de diálogo para **configurar la nueva biblioteca de .NET Standard**, elija ".NET Standard 2.1" y seleccione **Siguiente**.

   :::image type="content" source="media/library-with-visual-studio-mac/choose-net-std-21.png" alt-text="Selección de .NET Standard 2.1":::

1. Asigne al proyecto el nombre "StringLibrary" y a la solución "ClassLibraryProjects". Deje activada la opción **Crear un directorio de proyecto dentro del directorio de la solución**. Seleccione **Crear**.

   :::image type="content" source="media/library-with-visual-studio-mac/visual-studio-mac-new-project-options.png" alt-text="Opciones del cuadro de diálogo Nuevo proyecto de Visual Studio para Mac":::

1. En el menú principal, seleccione **Ver** > **Paneles** > **Solución** y seleccione el icono de acoplamiento para mantener el panel abierto.

   :::image type="content" source="media/library-with-visual-studio-mac/solution-dock-icon.png" alt-text="Icono de acoplamiento del panel de solución":::

1. En el panel **Solución**, expanda el nodo `StringLibrary` para mostrar el archivo de clase proporcionado por la plantilla *Class1.cs*. Haga clic presionando <kbd>control</kbd> en el archivo, seleccione **Cambiar nombre** en el menú contextual y denomínelo *StringLibrary.cs*. Abra el archivo y reemplace el contenido por el código siguiente:

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibrary/Class1.cs":::

1. Presione <kbd>⌘</kbd><kbd>S</kbd> (<kbd>command</kbd>+<kbd>S</kbd>) para guardar el archivo.

1. Seleccione **Errores** en el margen inferior de la ventana de IDE para abrir el panel **Errores**. Seleccione el botón **Salida de la compilación**.

   :::image type="content" source="media/library-with-visual-studio-mac/visual-studio-mac-error-button.png" alt-text="Margen inferior del IDE de Visual Studio para Mac con el botón Errores":::

1. Seleccione **Compilar** > **Compilar todo** en el menú.

   La solución se compila. El panel de salida de la compilación muestra que la compilación es correcta.

   :::image type="content" source="media/library-with-visual-studio-mac/visual-studio-mac-build-panel.png" alt-text="Panel de salida de la compilación de Visual Studio para Mac del panel Errores con el mensaje de compilación correcta":::

## <a name="add-a-console-app-to-the-solution"></a>Incorporación de una aplicación de consola a la solución

Agregue una aplicación de consola que use la biblioteca de clases. La aplicación solicitará al usuario que escriba una cadena y notificará si la cadena comienza con un carácter en mayúsculas.

1. En el panel **Solución**, haga clic pulsando <kbd>control</kbd> en la solución `ClassLibraryProjects`. Agregue un nuevo proyecto de **aplicación de consola**; para ello, seleccione la plantilla de las plantillas de **Web and Console** (Web y consola) > **Aplicación** y seleccione **Siguiente**.

1. Seleccione **.NET Core 3.1** como **Marco de destino** y, a continuación, seleccione **Siguiente**.

1. Asigne al proyecto el nombre **ShowCase**. Seleccione **Crear** para crear el proyecto en la solución.

   :::image type="content" source="media/library-with-visual-studio-mac/add-showcase-project.png" alt-text="Adición de Showcase":::

1. Abra el archivo *Program.cs*. Reemplace el código por el siguiente código:

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/ShowCase/Program.cs":::

   El programa le pide al usuario que escriba una cadena. Indica si la cadena comienza con un carácter en mayúsculas. Si el usuario presiona la tecla <kbd>Entrar</kbd> sin especificar una cadena, la aplicación finaliza y la ventana de la consola se cierra.

   El código usa la variable `row` para mantener un recuento del número de filas de datos escritas en la ventana de consola. Siempre que sea mayor o igual a 25, el código borra la ventana de consola y muestra un mensaje al usuario.

## <a name="add-a-project-reference"></a>Agregar una referencia de proyecto

En un principio, el nuevo proyecto de aplicación de consola no tiene acceso a la biblioteca de clases. Para que pueda llamar a los métodos de la biblioteca de clases, cree una referencia de proyecto al proyecto de biblioteca de clases.

1. En el panel **Soluciones**, haga clic presionando <kbd>control</kbd> en el nodo **Dependencias** del nuevo proyecto **ShowCase**. En el menú contextual, seleccione **Agregar referencia**.

1. En el cuadro de diálogo **Referencias**, seleccione **StringLibrary** y **Aceptar**.

## <a name="run-the-app"></a>Ejecutar la aplicación

1. Haga clic presionando <kbd>control</kbd> en el proyecto ShowCase y seleccione **Ejecutar el proyecto** en el menú contextual.

1. Para probar el programa, escriba cadenas y presione <kbd>Entrar</kbd> y, después, presione <kbd>Entrar</kbd> para salir.

   :::image type="content" source="media/library-with-visual-studio-mac/visual-studio-mac-console-window.png" alt-text="Ventana de la consola de Visual Studio para Mac en la que se muestra la aplicación en ejecución":::

## <a name="additional-resources"></a>Recursos adicionales

* [Desarrollo de bibliotecas con la CLI de .NET Core](libraries.md)
* [Versiones de .NET Standard y las plataformas que admiten](../../standard/net-standard.md).
* [Notas de la versión de Visual Studio 2019 para Mac](/visualstudio/releasenotes/vs2019-mac-relnotes)

## <a name="next-steps"></a>Pasos siguientes

En este tutorial, ha creado una solución, ha agregado un proyecto de biblioteca y ha agregado un proyecto de aplicación de consola que usa la biblioteca. En el siguiente tutorial, agregará un proyecto de prueba unitaria a la solución.

> [!div class="nextstepaction"]
> [Prueba de una biblioteca .NET Standard con .NET Core mediante Visual Studio para Mac](testing-library-with-visual-studio-mac.md)
