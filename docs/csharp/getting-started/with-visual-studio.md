---
title: "Compilación de una aplicación Hola mundo en C# con .NET Core en Visual Studio 2017"
description: "Obtenga información sobre cómo crear una sencilla aplicación de consola .NET Core con Visual Studio 2017."
keywords: ".NET Core, aplicación de consola .NET Core, Visual Studio 2017"
author: stevehoag
ms.author: shoag
ms.date: 03/07/2017
ms.topic: article
ms.prod: .net-core
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 97aa50bf-bdf8-416d-a56c-ac77504c14ea
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: f1a20f399b4ab34986d700622ff3bf3859b001bd
ms.lasthandoff: 03/13/2017

---

# <a name="building-a-c-hello-world-application-with-net-core-in-visual-studio-2017"></a>Compilación de una aplicación Hola mundo en C# con .NET Core en Visual Studio 2017 #

En este tema se proporciona una introducción detallada para compilar, depurar y publicar una sencilla aplicación de consola .NET Core con Visual Studio 2017. Visual Studio 2017 proporciona un entorno de desarrollo completo para la compilación de aplicaciones .NET Core. Siempre que la aplicación no tenga dependencias específicas de la plataforma, la propia aplicación puede ejecutarse en cualquier plataforma que tenga como destino .NET Core y en cualquier sistema que tenga instalado .NET Core.

## <a name="prerequisites"></a>Requisitos previos ##

- [Visual Studio de 2017](https://www.visualstudio.com/downloads/) con la carga de trabajo "Desarrollo multiplataforma de .NET Core" instalada. 

Para más información, vea la sección [Visual Studio 2017](../../core/windows-prerequisites.md) en el tema de los requisitos previos de Windows.

## <a name="a-simple-hello-world-application"></a>Una aplicación "Hola mundo" sencilla ##

Para empezar, se va a crear una aplicación de consola "Hola mundo" sencilla. Estos son los pasos:

1. Abra Visual Studio y, en el menú **Archivo**, elija **Nuevo** > **Proyecto**. En el cuadro de diálogo **Nuevo proyecto**, expanda el nodo **Visual C#** en el panel de la izquierda y después elija el nodo **.NET Core**.

2. En el panel derecho, elija **Aplicación de consola (.NET Core)**. Escriba el nombre del proyecto, `HelloWorld`, y asegúrese de que el cuadro **Crear directorio para la solución** está activado, como se muestra en la figura siguiente.

   ![Captura de pantalla que muestra el cuadro de diálogo Nuevo proyecto con la aplicación de consola seleccionada](./media/with-visual-studio/vs_newproject.jpg)
   
3. Elija el botón **Aceptar** . Visual Studio muestra su entorno de desarrollo con su ventana de código, como se muestra en la figura siguiente. La plantilla de aplicación de consola de C# para .NET Core define automáticamente una clase, `Program`, con un único método, `Main`, que adopta una matriz @System.String como argumento. `Main` es el punto de entrada de la aplicación, el método al que llama automáticamente el tiempo de ejecución cuando inicia la aplicación. Los argumentos de línea de comandos proporcionados cuando se inicia la aplicación están disponibles en la matriz *args*.

   ![Visual Studio y el nuevo proyecto Hola mundo](./media/with-visual-studio/vs_devenv.jpg)

   La plantilla crea una aplicación muy sencilla "Hola mundo"; llama al método @System.Console.WriteLine(System.String) para mostrar la cadena literal "¡Hola mundo!" en la ventana de consola. Al seleccionar el botón "Hola a todos" con la flecha verde en la barra de herramientas, ahora puede ejecutar el programa en modo de depuración. No obstante, si lo hace, la ventana de consola se mostrará durante muy poco tiempo antes de cerrarse. Esto ocurre porque `Main` finaliza y la aplicación termina en cuanto se ejecuta la única instrucción en el método `Main`.

4. Se va a detener la aplicación existente antes de que cierre la ventana de consola. Agregue el código siguiente inmediatamente después de llamar al método @System.Console.WriteLine(System.String):

   ```csharp
   Console.Write("Press any key to continue...");
   Console.ReadKey(true);
   ```
   Este código pide al usuario que presione cualquier tecla y, a continuación, detiene el programa hasta que se presiona una tecla.

5. En la barra de menús, elija **Compilar**, **Compilar solución**. De esta forma, el programa se compila en IL, un lenguaje intermedio que después se convierte en código binario mediante un compilador Just-In-Time (JIT).

6. Seleccione el botón "Hola a todos" con la flecha verde en la barra de herramientas para ejecutar el programa. El resultado se muestra en la ilustración siguiente.

   ![Imagen](./media/with-visual-studio/simple_hello.jpg)

7. Presione cualquier tecla para cerrar la ventana.

## <a name="enhancing-the-hello-world-application"></a>Mejora de la aplicación "Hola mundo" ##

Se va a mejorar la aplicación para pedir al usuario su nombre, que luego se mostrará junto con la fecha y hora en la ventana de consola. Para modificar y probar el programa, haga lo siguiente:

1. Escriba el siguiente código de C# en la ventana de código inmediatamente después del corchete de apertura que sigue a la línea `public static void Main(string[] args)` y antes del primer corchete de cierre.

   [!CODE [GettingStarted#1](../../../samples/snippets/csharp/getting_started/with_visual_studio/helloworld.cs#1)]

   En la siguiente ilustración se muestra la ventana de código resultante.

   ![Ejecución del programa modificado](./media/with-visual-studio/codewindow.jpg)

   Este código muestra "What is your name?" en la consola y espera a que el usuario escriba una cadena seguida de la tecla ENTRAR. Almacena esta cadena a una variable denominada `name`. También recupera el valor de la propiedad @System.DateTime.Now, que contiene la hora local actual, y lo asigna a una variable denominada `date`. A continuación, utiliza una [cadena de formato compuesto](../../standard/base-types/composite-format.md) para mostrar estos valores en la consola.

2. Compile el programa; para ello, seleccione **Generar** > **Compilar solución**. De esta forma, el programa se compila en IL, un lenguaje intermedio que después se convierte en código binario mediante un compilador Just-In-Time (JIT).

3. Ejecute el programa en modo de depuración en Visual Studio; para ello, seleccione la flecha verde en la barra de herramientas, presione F5 o elija el elemento de menú **Depurar** > **Iniciar depuración**. Después de responder a las preguntas, para lo que debe escribir el nombre y presionar la tecla ENTRAR, la ventana de consola debe tener un aspecto similar al siguiente:

   ![Ejecución del programa modificado](./media/with-visual-studio/console.jpg)

4. Presione cualquier tecla para cerrar la ventana de consola. Esto finaliza el modo de depuración.

Ahora ha creado y ejecutado esta sencilla aplicación. Para desarrollar una aplicación profesional, todavía hay algunos pasos adicionales que puede realizar para preparar el lanzamiento de la aplicación:

- Para obtener información sobre la depuración de la aplicación, vea [Depuración de la aplicación Hola mundo](debugging-with-visual-studio-2017.md).

- Para obtener información sobre el desarrollo de una publicación de una versión de distribución de la aplicación, vea [Publicación de la aplicación Hola mundo](publishing-with-visual-studio-2017.md).

## <a name="related-topics"></a>Temas relacionados ##

En lugar de una aplicación de consola, también puede crear una biblioteca de clases con .NET Core y Visual Studio 2017. Para consultar una introducción detallada, vea [Building a class library with C# and .NET Core in Visual Studio 2017](library-with-visual-studio-2017.md) (Creación de una biblioteca de clases con C# y .NET Core en Visual Studio 2017).

También puede desarrollar una aplicación de consola .NET Core en Mac, Linux y Windows mediante Visual Studio Code, un editor de código cuya descarga es gratuita. Para obtener un tutorial detallado, vea [Introducción a Visual Studio Code](with-visual-studio-code.md).

