---
title: Consumo de una biblioteca de .NET Standard en Visual Studio
description: Cree una aplicación de .NET Core que llame a los miembros de otra biblioteca de clases con Visual Studio 2019.
ms.date: 12/20/2019
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 4eb75f23359334ea483cba1498f1804c4b24c80c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "76920459"
---
# <a name="consume-a-net-standard-library-in-visual-studio"></a>Consumo de una biblioteca de .NET Standard en Visual Studio

Una vez que haya creado una biblioteca de clases de .NET Standard, la haya probado y haya creado una versión de lanzamiento de dicha biblioteca, el siguiente paso es ponerla a disposición de los autores de las llamadas. Existen dos maneras de hacerlo:

- Si una única solución va a usar la biblioteca (por ejemplo, si es un componente de una sola aplicación más grande), se puede incluir como proyecto en la solución.
- Si la biblioteca va a estar accesible públicamente, puede distribuirla como un paquete NuGet.

En este tutorial aprenderá a:
> [!div class="checklist"]
>
> - Agregue una aplicación de consola a la solución que haga referencia a un proyecto de biblioteca de .NET Standard.
> - Cree un paquete NuGet que contenga un proyecto de biblioteca de .NET Standard.

## <a name="add-a-console-app-to-your-solution"></a>Incorporación de una aplicación de consola a la solución

Así como incluyó pruebas unitarias en la misma solución que la biblioteca de clases en [Prueba de una biblioteca de .NET Standard con .NET Core en Visual Studio 2017](testing-library-with-visual-studio.md), puede incluir la aplicación como parte de esa solución. Por ejemplo, se puede usar la biblioteca de clases en una aplicación de consola que pide al usuario que inserte una cadena e informa de si su primer carácter está en mayúsculas:

1. Abra la solución `ClassLibraryProjects` que creó en el artículo [Creación de una biblioteca de .NET Standard con C# y el SDK de .NET Core en Visual Studio 2017](library-with-visual-studio.md).

1. Agregue una nueva aplicación de consola de .NET Core denominada "Showcase" a la solución.

   1. Haga clic con el botón derecho en la solución en el **Explorador de soluciones** y seleccione **Agregar** > **Nuevo proyecto**.

   1. En el cuadro de búsqueda de la página **Agregar un nuevo proyecto**, escriba **consola**. En la lista de lenguajes, elija **C#** o **Visual Basic** y, luego, en la lista de plataformas, elija **Todas las plataformas**. Elija la plantilla **Aplicación de consola (.NET Core)** y haga clic en **Siguiente**.

   1. En la página **Configure el nuevo proyecto**, escriba **ShowCase** en el cuadro **Nombre del proyecto**. Luego, elija **Crear**.

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **Presentación** y seleccione **Establecer como proyecto de inicio** en el menú contextual.

   ![Menú contextual del proyecto de Visual Studio para establecer el proyecto de inicio](./media/consuming-library-with-visual-studio/set-startup-project-context-menu.png)

1. Inicialmente, el proyecto no tiene acceso a la biblioteca de clases. Para permitir que se llame a métodos de la biblioteca de clases, puede crear una referencia a la biblioteca de clases. En el **Explorador de soluciones**, haga clic con el botón derecho en el nodo **Dependencias** del proyecto `ShowCase` y seleccione **Agregar referencia**.

   ![Menú contextual Agregar referencia de Visual Studio](./media/consuming-library-with-visual-studio/add-reference-context-menu.png)

1. En el cuadro de diálogo **Administrador de referencias**, seleccione **StringLibrary**, el proyecto de biblioteca de clases, y pulse el botón **Aceptar**.

   ![Cuadro de diálogo Administrador de referencias con StringLibrary seleccionado](./media/consuming-library-with-visual-studio/manage-project-references.png)

1. En la ventana de código del archivo *Program.vb* o *Program.vb*, reemplace todo el código con el código siguiente:

   [!code-csharp[UsingClassLib#1](~/samples/snippets/csharp/getting_started/with_visual_studio_2017/showcase.cs)]
   [!code-vb[UsingClassLib#1](~/samples/snippets/core/tutorials/vb-library-with-visual-studio/showcase.vb)]

   El código usa la variable `row` para mantener un recuento del número de filas de datos escritas en la ventana de consola. Siempre que sea mayor o igual a 25, el código borra la ventana de consola y muestra un mensaje al usuario.

   El programa le pide al usuario que escriba una cadena. Indica si la cadena comienza con un carácter en mayúsculas. Si el usuario presiona la tecla Entrar sin especificar una cadena, la aplicación finaliza y la ventana de la consola se cierra.

1. Si es necesario, cambie la barra de herramientas para compilar la versión de **depuración** del proyecto `ShowCase`. Compile y ejecute el programa haciendo clic en la flecha verde en el botón **Presentación**.

   ![Barra de herramientas del proyecto de Visual Studio en la que se muestra el botón Depurar](./media/consuming-library-with-visual-studio/visual-studio-project-toolbar.png)

La aplicación que usa esta biblioteca se puede depurar y publicar siguiendo los pasos indicados en [Depuración de la aplicación Hola mundo de .NET Core en C# o Visual Basic con Visual Studio 2017](debugging-with-visual-studio.md) y [Publicación de la aplicación Hola mundo de .NET Core con Visual Studio 2017](publishing-with-visual-studio.md).

## <a name="create-a-nuget-package"></a>Creación de un paquete NuGet

Puede hacer que la biblioteca de clases tenga una disponibilidad amplia si la publica como un paquete NuGet. Visual Studio no admite la creación de paquetes NuGet. Para crear uno, debe usar los comandos de la CLI de .NET Core:

1. Abra una ventana de la consola.

   Por ejemplo, escriba **Símbolo del sistema** en el cuadro de búsqueda de la barra de tareas de Windows. Seleccione la aplicación de escritorio **Símbolo del sistema** o presione **Entrar** si ya está seleccionado en los resultados de búsqueda.

1. Vaya al directorio del proyecto de la biblioteca. El directorio contiene el código fuente y un archivo de proyecto, *StringLibrary.csproj* o *StringLibrary.vbproj*.

1. Ejecute el comando [dotnet pack](../tools/dotnet-pack.md) para generar un paquete con una extensión *.nupkg*:

   ```dotnetcli
   dotnet pack --no-build
   ```

   > [!TIP]
   > Si el directorio que contiene *dotnet.exe* no está en la ruta de acceso, puede encontrar su ubicación escribiendo `where dotnet.exe` en la ventana de consola.

Para más información sobre la creación de paquetes NuGet, consulte [Creación de un paquete NuGet con la CLI de .NET Core](../deploying/creating-nuget-packages.md).
