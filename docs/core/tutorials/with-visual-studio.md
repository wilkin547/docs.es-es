---
title: Creación de una aplicación Hola mundo de C# con .NET Core en Visual Studio
description: Obtenga información sobre cómo crear su primera aplicación de consola .NET Core con C# o Visual Basic mediante Visual Studio 2017.
author: BillWagner
ms.author: wiwagn
ms.date: 12/09/2019
ms.custom: vs-dotnet
ms.openlocfilehash: 738fc49a820c3c5d94fb35c1bf7a8b718ed75cb3
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83394825"
---
# <a name="tutorial-create-your-first-net-core-console-application-in-visual-studio-2019"></a>Tutorial: Creación de su primera aplicación de consola con .NET Core en Visual Studio 2019

En este artículo se proporciona una introducción paso a paso para crear y ejecutar una aplicación de consola Hola mundo con .NET Core en Visual Studio 2019. Tradicionalmente, se usa una aplicación Hola mundo para introducir a los principiantes en un nuevo lenguaje de programación. En este programa simplemente muestra la frase "Hola mundo" en la pantalla.

## <a name="prerequisites"></a>Requisitos previos

- [Visual Studio 2019, versión 16.4 o posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) con la carga de trabajo **Desarrollo multiplataforma de .NET Core** instalada El SDK de .NET Core 3.1 se instala automáticamente al seleccionar esta carga de trabajo.

Para más información, consulte la sección [Instalación con Visual Studio](../install/sdk.md?pivots=os-windows#install-with-visual-studio) del artículo [Instalación del SDK de .NET Core](../install/sdk.md?pivots=os-windows).

## <a name="create-the-app"></a>Creación de la aplicación

Las instrucciones siguientes crean una sencilla aplicación de consola de Hola mundo:

<!-- markdownlint-disable MD025 -->

# <a name="c"></a>[C#](#tab/csharp)

1. Abra Visual Studio 2019.

1. Cree un nuevo proyecto de aplicación de consola de .Net Core en C# denominado "HelloWorld".

   1. En la ventana de inicio, elija **Crear un proyecto nuevo**.

      ![Botón Crear un proyecto seleccionado en la ventana de inicio de Visual Studio](./media/with-visual-studio/start-window.png)

   1. En la página **Crear un proyecto**, escriba **consola** en el cuadro de búsqueda. Después, elija **C#** en la lista de lenguajes y, luego, **Todas las plataformas** en la lista de plataformas. Elija la plantilla **Aplicación de consola (.NET Core)** y haga clic en **Siguiente**.

      ![Creación de una nueva ventana de proyecto con filtros seleccionados](./media/with-visual-studio/create-new-project.png)

      > [!TIP]
      > Si no ve las plantillas de .NET Core, es probable que falte la carga de trabajo necesaria instalada. En el mensaje **¿No encuentra lo que busca?** , elija el vínculo **Instalar más herramientas y características**. Se abre el Instalador de Visual Studio. Asegúrese de que tiene instalada la carga de trabajo **Desarrollo multiplataforma de .NET Core**.

   1. En la página **Configurar el nuevo proyecto**, escriba **HelloWorld** en el cuadro **Nombre del proyecto**. Luego, elija **Crear**.

      ![Configuración de la ventana de nuevo proyecto con los campos de nombre de proyecto, ubicación y nombre de la solución](./media/with-visual-studio/configure-new-project.png)

   La plantilla de aplicación de consola de C# para .NET Core define automáticamente una clase, `Program`, con un único método, `Main`, que adopta una matriz <xref:System.String> como argumento. `Main` es el punto de entrada de la aplicación, el método que se llama automáticamente mediante el tiempo de ejecución cuando inicia la aplicación. Los argumentos de línea de comandos proporcionados cuando se inicia la aplicación están disponibles en la matriz *args*.

   ![Visual Studio y el nuevo proyecto Hola mundo](./media/with-visual-studio/visual-studio-main-window.png)

# <a name="visual-basic"></a>[Visual Basic](#tab/vb)

1. Abra Visual Studio 2019.

1. Cree un nuevo proyecto de aplicación de consola de .NET Core con Visual Basic denominado "HelloWorld".

   1. En la ventana de inicio, elija **Crear un proyecto nuevo**.

      ![Botón Crear un proyecto seleccionado en la ventana de inicio de Visual Studio](./media/with-visual-studio/start-window.png)

   1. En la página **Crear un proyecto**, escriba **consola** en el cuadro de búsqueda. Después, elija **Visual Basic** en la lista de lenguajes y luego, **Todas las plataformas** en la lista de plataformas. Elija la plantilla **Aplicación de consola (.NET Core)** y haga clic en **Siguiente**.

      ![Elija la plantilla Visual Basic para la Aplicación de consola (.NET Framework).](./media/with-visual-studio/vb/create-new-project.png)

      > [!TIP]
      > Si no ve las plantillas de .NET Core, es probable que falte la carga de trabajo necesaria instalada. En el mensaje **¿No encuentra lo que busca?** , elija el vínculo **Instalar más herramientas y características**. Se abre el Instalador de Visual Studio. Asegúrese de que tiene instalada la carga de trabajo **Desarrollo multiplataforma de .NET Core**.

   1. En la página **Configurar el nuevo proyecto**, escriba **HelloWorld** en el cuadro **Nombre del proyecto**. Luego, elija **Crear**.

   La plantilla de aplicación de consola para .NET Core define automáticamente una clase, `Program`, con un único método, `Main`, que adopta una matriz <xref:System.String> como argumento. `Main` es el punto de entrada de la aplicación, el método que se llama automáticamente mediante el tiempo de ejecución cuando inicia la aplicación. Los argumentos de línea de comandos proporcionados cuando se inicia la aplicación están disponibles en el parámetro `args`.

   ![Visual Studio y el nuevo proyecto Hola mundo](./media/with-visual-studio/vb/visual-studio-main-window.png)

---

   La plantilla crea una aplicación "Hola mundo" sencilla. Llama al método <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> para mostrar la cadena literal "Hola mundo" en la ventana de la consola.

## <a name="run-the-app"></a>Ejecutar la aplicación

1. Para ejecutar el programa, elija **HelloWorld** en la barra de herramientas o presione **F5**.

   ![Barra de herramientas de Visual Studio con el botón Ejecutar HelloWorld seleccionado](./media/with-visual-studio/run-program.png)

   Se abre la ventana de la consola con el texto "Hello World" impreso en la pantalla y parte de la información de depuración de Visual Studio.

   ![Ventana de la consola que muestra Hola mundo Presione cualquier tecla para continuar](./media/with-visual-studio/hello-world-console.png)

1. Presione cualquier tecla para cerrar la ventana de consola.

## <a name="enhance-the-app"></a>Mejora de la aplicación

Mejore su aplicación para pedir su nombre al usuario y mostrarlo junto con la fecha y la hora. Las instrucciones siguientes modifican y ejecutan de nuevo la aplicación:

# <a name="c"></a>[C#](#tab/csharp)

1. Reemplace el contenido del método `Main`, que actualmente es solo la línea que llama a `Console.WriteLine`, con el código siguiente:

   [!code-csharp[GettingStarted#1](~/samples/snippets/csharp/getting_started/with_visual_studio/HelloWorld.cs#1)]

   Este código muestra "What is your name?" en la ventana de la consola y espera a que el usuario escriba una cadena seguida de la tecla Entrar. Almacena esta cadena en una variable denominada `name`. También recupera el valor de la propiedad <xref:System.DateTime.Now?displayProperty=nameWithType>, que contiene la hora local actual, y lo asigna a una variable denominada `date`. Por último, usa una [cadena interpolada](../../csharp/language-reference/tokens/interpolated.md) para mostrar estos valores en la ventana de la consola.

1. Compile el programa; para ello, seleccione **Generar** > **Compilar solución**.

1. Para ejecutar el programa, elija **HelloWorld** en la barra de herramientas o presione **F5**.

1. Responda a la solicitud escribiendo un nombre y presionando la tecla **Entrar**.

   ![Ventana de la consola con el resultado del programa modificado](./media/with-visual-studio/hello-world-update.png)

1. Presione cualquier tecla para cerrar la ventana de consola.

# <a name="visual-basic"></a>[Visual Basic](#tab/vb)

1. Reemplace el contenido del método `Main`, que actualmente es solo la línea que llama a `Console.WriteLine`, con el código siguiente:

   [!code-vb[GettingStarted#1](~/samples/snippets/core/tutorials/vb-with-visual-studio/Program.vb#1)]

   Este código muestra "What is your name?" en la ventana de la consola y espera a que el usuario escriba una cadena seguida de la tecla Entrar. Almacena esta cadena en una variable denominada `name`. También recupera el valor de la propiedad <xref:System.DateTime.Now?displayProperty=nameWithType>, que contiene la hora local actual, y lo asigna a una variable denominada `date`. Por último, usa una [cadena interpolada](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md) para mostrar estos valores en la ventana de la consola.

1. Compile el programa; para ello, seleccione **Generar** > **Compilar solución**.

1. Para ejecutar el programa, elija **HelloWorld** en la barra de herramientas o presione **F5**.

1. Responda a la solicitud escribiendo un nombre y presionando la tecla **Entrar**.

   ![Ventana de la consola con el resultado del programa modificado](./media/with-visual-studio/hello-world-update.png)

1. Presione cualquier tecla para cerrar la ventana de consola.

---

## <a name="next-steps"></a>Pasos siguientes

En este artículo, ha creado y ejecutado su primera aplicación de .NET Core. En el paso siguiente, va a depurar la aplicación.

> [!div class="nextstepaction"]
> [Depuración de una aplicación "Hola mundo" con .NET Core en Visual Studio](debugging-with-visual-studio.md)
