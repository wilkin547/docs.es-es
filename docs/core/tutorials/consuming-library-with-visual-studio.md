---
title: Consumo de una biblioteca de clases con .NET Core en Visual Studio 2017
description: Obtenga información sobre cómo llamar a los miembros de una biblioteca de clases con Visual Studio 2017.
author: BillWagner
ms.author: wiwagn
ms.date: 06/05/2018
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 52ec46c23bb928b49f034270ed1d510d1acf992e
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2018
ms.locfileid: "45518170"
---
# <a name="consuming-a-net-standard-library-in-visual-studio-2017"></a>Consumo de una biblioteca de clases con .NET Core en Visual Studio 2017

Una vez que haya creado una biblioteca de clases de .NET Standard siguiendo los pasos de [Building a C# class library with .NET Core in Visual Studio 2017](./library-with-visual-studio.md) (Creación de una biblioteca de clases de C# con .NET Core en Visual Studio 2017) o [Building a Visual Basic class library with .NET Core in Visual Studio 2017](vb-library-with-visual-studio.md) (Creación de una biblioteca de clases de Visual Basic con .NET Core en Visual Studio 2017), pruébela en [Testing a class library with .NET Core in Visual Studio 2017](testing-library-with-visual-studio.md) (Prueba de una biblioteca de clases con .NET Core en Visual Studio 2017), y compile una versión de lanzamiento de la biblioteca; el paso siguiente consiste en hacer que esté disponible para los autores de llamadas. Existen dos maneras de hacerlo:

* Si una única solución va a usar la biblioteca (por ejemplo, si es un componente de una sola aplicación más grande), se puede incluir como proyecto en la solución.

* Si la biblioteca va a ser accesible con carácter general, puede distribuirla como un paquete NuGet.

## <a name="including-a-library-as-a-project-in-a-solution"></a>Inclusión de una biblioteca como proyecto en una solución

Así como se incluyen pruebas unitarias en la misma solución que la biblioteca de clases, se puede incluir la aplicación como parte de esa solución. Por ejemplo, se puede usar la biblioteca de clases en una aplicación de consola que pide al usuario que inserte una cadena e informa de si su primer carácter está en mayúsculas:

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
1. Abra la solución `ClassLibraryProjects` creada en el tema [Building a C# Class Library with .NET Core in Visual Studio 2017](./library-with-visual-studio.md) (Creación de una biblioteca de clases de C# con .NET Core en Visual Studio 2017). En el **Explorador de soluciones**, haga clic con el botón derecho en la solución **ClassLibraryProject** y seleccione **Agregar** > **Nuevo proyecto** en el menú contextual.

1. En el cuadro de diálogo **Agregar nuevo proyecto**, expanda el nodo **Visual C#** y seleccione el nodo **.NET Core** seguido por la plantilla del proyecto **Aplicación de consola (.NET Core)**. En el cuadro de texto **Nombre**, escriba "Presentación" y pulse el botón **Aceptar**.

   ![Cuadro de diálogo Agregar nuevo proyecto](./media/consuming-library-with-visual-studio/addnewproject.png)

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **Presentación** y seleccione **Establecer como proyecto de inicio** en el menú contextual. 

   ![Menú contextual de Presentación](./media/consuming-library-with-visual-studio/setstartupproject.png)

1. Inicialmente, el proyecto no tiene acceso a la biblioteca de clases. Para permitir que se llame a métodos de la biblioteca de clases, puede crear una referencia a la biblioteca de clases. En el **Explorador de soluciones**, haga clic con el botón derecho en el nodo **Dependencias** del proyecto `ShowCase` y seleccione **Agregar referencia**.

   ![Menú contextual Dependencias de Presentación](./media/consuming-library-with-visual-studio/addreference.png)

1. En el cuadro de diálogo **Administrador de referencias**, seleccione **StringLibrary**, el proyecto de biblioteca de clases, y pulse el botón **Aceptar**.

   ![Administrador de referencias](./media/consuming-library-with-visual-studio/referencemanager.png)

1. En la ventana de código del archivo *Program.cs*, reemplace todo el código por el código siguiente:

   [!CODE-csharp[UsingClassLib#1](../../../samples/snippets/csharp/getting_started/with_visual_studio_2017/showcase.cs)]

   El código usa la variable `row` para mantener un recuento del número de filas de datos escritas en la ventana de consola. Siempre que sea mayor o igual a 25, el código borra la ventana de consola y muestra un mensaje al usuario.

   El programa le pide al usuario que escriba una cadena. Indica si la cadena comienza con un carácter en mayúsculas. Si el usuario presiona la tecla Entrar sin especificar una cadena, la aplicación finaliza y la ventana de consola se cierra.

1. Si es necesario, cambie la barra de herramientas para compilar la versión de **depuración** del proyecto `ShowCase`. Compile y ejecute el programa haciendo clic en la flecha verde en el botón **Presentación**.

   ![Imagen](./media/consuming-library-with-visual-studio/toolbar.png)
# <a name="visual-basictabvisual-basic"></a>[Visual Basic](#tab/visual-basic)
1. Abra la solución `ClassLibraryProjects` creada en el tema [Building a class Library with Visual Basic and .NET Core in Visual Studio 2017](vb-library-with-visual-studio.md) (Creación de una biblioteca de clases con Visual Basic y .NET Core en Visual Studio 2017). En el **Explorador de soluciones**, haga clic con el botón derecho en la solución **ClassLibraryProject** y seleccione **Agregar** > **Nuevo proyecto** en el menú contextual.

1. En el cuadro de diálogo **Agregar nuevo proyecto**, expanda el nodo **Visual Basic** y seleccione el nodo **.NET Core** seguido por la plantilla del proyecto **Aplicación de consola (.NET Core)**. En el cuadro de texto **Nombre**, escriba "Presentación" y pulse el botón **Aceptar**.

   ![Cuadro de diálogo Agregar nuevo proyecto](./media/consuming-library-with-visual-studio/vb-addnewproject.png)

1. En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **Presentación** y seleccione **Establecer como proyecto de inicio** en el menú contextual. 

   ![Menú contextual de Presentación](./media/consuming-library-with-visual-studio/setstartupproject.png)

1. Inicialmente, el proyecto no tiene acceso a la biblioteca de clases. Para permitir que se llame a métodos de la biblioteca de clases, puede crear una referencia a la biblioteca de clases. En el **Explorador de soluciones**, haga clic con el botón derecho en el nodo **Dependencias** del proyecto `ShowCase` y seleccione **Agregar referencia**.

   ![Menú contextual Dependencias de Presentación](./media/consuming-library-with-visual-studio/addreference.png)

1. En el cuadro de diálogo **Administrador de referencias**, seleccione **StringLibrary**, el proyecto de biblioteca de clases, y pulse el botón **Aceptar**.

   ![Administrador de referencias](./media/consuming-library-with-visual-studio/referencemanager.png)

1. En la ventana de código del archivo *Program.vb*, reemplace todo el código por el código siguiente:

    [!CODE-vb[UsingClassLib#1](../../../samples/snippets/core/tutorials/vb-library-with-visual-studio/showcase.vb)]

   El código usa la variable `row` para mantener un recuento del número de filas de datos escritas en la ventana de consola. Siempre que sea mayor o igual a 25, el código borra la ventana de consola y muestra un mensaje al usuario.

   El programa le pide al usuario que escriba una cadena. Indica si la cadena comienza con un carácter en mayúsculas. Si el usuario presiona la tecla Entrar sin especificar una cadena, la aplicación finaliza y la ventana de consola se cierra.

1. Si es necesario, cambie la barra de herramientas para compilar la versión de **depuración** del proyecto `ShowCase`. Compile y ejecute el programa haciendo clic en la flecha verde en el botón **Presentación**.

   ![Imagen](./media/consuming-library-with-visual-studio/toolbar.png)
---

La aplicación que usa esta biblioteca se puede depurar y publicar siguiendo los pasos indicados en [Debugging your Hello World Application with Visual Studio 2017](debugging-with-visual-studio.md) (Depuración de la aplicación Hola a todos con Visual Studio 2017) y [Publishing your Hello World Application with Visual Studio 2017](publishing-with-visual-studio.md) (Publicación de la aplicación Hola a todos con Visual Studio 2017).

## <a name="distributing-the-library-in-a-nuget-package"></a>Distribución de la biblioteca en un paquete NuGet

Puede hacer que la biblioteca de clases tenga una disponibilidad amplia si la publica como un paquete NuGet. Visual Studio no admite la creación de paquetes NuGet. Para crear uno, se usa la [utilidad de línea de comandos `dotnet`](../../core/tools/dotnet.md):

1. Abra una ventana de consola. Por ejemplo, en el cuadro de texto **Pregúntame cualquier cosa** de la barra de tareas de Windows, escriba `Command Prompt` (o `cmd` para abreviar) y abra una ventana de consola seleccionando la aplicación de escritorio **Símbolo del sistema** o presionando Entrar si está seleccionada en los resultados de búsqueda.

1. Vaya al directorio del proyecto de la biblioteca. A menos que haya reconfigurado la ubicación típica del archivo, se encuentra en el directorio *Documentos\Visual Studio 2017\Projects\ClassLibraryProjects\StringLibrary*. El directorio contiene el código fuente y un archivo de proyecto, *StringLibrary.csproj*.

1. Emita el comando `dotnet pack --no-build`: La utilidad `dotnet` genera un paquete con una extensión *.nupkg*.

   > [!TIP]
   > Si el directorio que contiene *dotnet.exe* no está en la ruta de acceso, puede encontrar su ubicación escribiendo `where dotnet.exe` en la ventana de consola.

Para más información sobre la creación de paquetes NuGet, consulte [Cómo crear un paquete NuGet con herramientas multiplataforma ](../../core/deploying/creating-nuget-packages.md).
