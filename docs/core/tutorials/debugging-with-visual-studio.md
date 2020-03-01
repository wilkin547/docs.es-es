---
title: Depuración de la aplicación Hola mundo de .NET Core con Visual Studio
description: Obtenga información sobre cómo depurar una aplicación Hola mundo, escrita en C# o Visual Basic, con Visual Studio.
ms.date: 12/05/2019
ms.custom: vs-dotnet
ms.openlocfilehash: b2ee1401fc89f990c5f930d80d1a510a117e63a0
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156678"
---
# <a name="debug-your-c-or-visual-basic-net-core-hello-world-application-using-visual-studio"></a>Depuración de la aplicación Hola mundo de .NET Core en C# o Visual Basic con Visual Studio

Hasta ahora, ha seguido los pasos descritos en [Creación de su primera aplicación de consola con .NET Core en Visual Studio 2019](with-visual-studio.md) para crear y ejecutar una aplicación de consola sencilla. Cuando haya escrito y compilado la aplicación, puede comenzar a probarla. Visual Studio incluye un conjunto completo de herramientas de depuración que puede usar para solucionar problemas de la aplicación.

## <a name="debug-build-configuration"></a>Depuración de la configuración de compilación

El modo de *depuración* y *versión* son dos de las configuraciones de compilación predeterminadas de Visual Studio. La configuración de compilación actual se muestra en la barra de herramientas. En la siguiente imagen de la barra de herramientas se muestra que Visual Studio está configurado para compilar la versión de depuración de la aplicación:

![Barra de herramientas de Visual Studio con Depuración resaltado](./media/debugging-with-visual-studio/visual-studio-toolbar-debug.png)

Empiece por ejecutar la versión de depuración de la aplicación. La configuración de compilación de depuración desactiva la mayoría de las optimizaciones del compilador y proporciona información más completa durante el proceso de compilación.

## <a name="set-a-breakpoint"></a>Establecer un punto de interrupción

Ejecute su programa y pruebe algunas características de depuración:

<!-- markdownlint-disable MD025 -->

# <a name="c"></a>[C#](#tab/csharp)

1. Establezca un *punto de interrupción* en la línea que dice `Console.WriteLine($"\nHello, {name}, on {date:d} at {date:t}!");`; para ello, haga clic en el margen izquierdo de la ventana de código de esa línea. También puede establecer un punto de interrupción colocando el símbolo de intercalación en la línea de código y presionando después **F9** o seleccionando **Depurar** > **Alternar punto de interrupción** en la barra de menús.

   Un punto de interrupción interrumpe temporalmente la ejecución de la aplicación *antes* de que se ejecute la línea con el punto de interrupción.

   Como se muestra en la siguiente imagen, para indicar la línea en la que se establece el punto de interrupción, Visual Studio lo resalta y muestra un círculo rojo en el margen izquierdo.

   ![Ventana del programa Visual Studio con el punto de interrupción establecido](./media/debugging-with-visual-studio/set-breakpoint-in-editor.png)

1. Ejecute el programa en el modo de depuración seleccionando el botón **HelloWorld** con la flecha verde en la barra de herramientas, presionando **F5** o seleccionando **Depurar** > **Iniciar depuración**.

1. Cuando el sistema le pida un nombre, escriba una cadena en la ventana de consola y luego presione **Entrar**.

1. La ejecución del programa se detiene cuando llega al punto de interrupción y antes de que se ejecute el método `Console.WriteLine`. La ventana **Variables locales** muestra los valores de las variables definidas en el método que se ejecuta actualmente.

   ![Captura de pantalla de un punto de interrupción en Visual Studio](./media/debugging-with-visual-studio/breakpoint-hit.png)

1. La ventana **Inmediato** le permite interactuar con la aplicación que está depurando. Puede cambiar el valor de las variables de forma interactiva para ver cómo afecta esto al programa.

   1. Si la ventana **Inmediato** no está visible, muéstrela; para ello, elija **Depurar** > **Ventanas** > **Inmediato**.

   1. Escriba `name = "Gracie"` en la ventana **Inmediato** y presione la tecla **Entrar**.

   1. Escriba `date = DateTime.Parse("11/16/2019 5:25 PM")` en la ventana **Inmediato** y presione la tecla **Entrar**.

   La ventana **Inmediato** muestra el valor de la variable de cadena y las propiedades del valor <xref:System.DateTime>. Además, los valores de las variables se actualizan en la ventana **Variables locales**.

   ![Ventanas Variables locales e Inmediato en Visual Studio 2019](./media/debugging-with-visual-studio/locals-immediate-window.png)

1. Seleccione el botón **Continuar** en la barra de herramientas para continuar con la ejecución del programa, o seleccione **Depurar** > **Continuar**. Los valores mostrados en la ventana de la consola corresponden a los cambios realizados en la ventana **Inmediato**.

   ![Ventana de consola que muestra los valores especificados](./media/debugging-with-visual-studio/console-window.png)

1. Presione cualquier tecla para salir de la aplicación y detenga la depuración.

# <a name="visual-basic"></a>[Visual Basic](#tab/vb)

1. Establezca un *punto de interrupción* en la línea que dice `Console.WriteLine($"{vbCrLf}Hello, {name}, on {currentDate:d} at {currentDate:t}!")`; para ello, haga clic en el margen izquierdo de la ventana de código de esa línea. También puede establecer un punto de interrupción colocando el símbolo de intercalación en la línea y eligiendo después **Depurar** > **Alternar punto de interrupción** en la barra de menús.

   Un punto de interrupción interrumpe temporalmente la ejecución de la aplicación *antes* de que se ejecute la línea con el punto de interrupción.

   Como se muestra en la siguiente ilustración, para indicar la línea en la que se establece el punto de interrupción, Visual Studio lo resalta y muestra un círculo rojo en el margen izquierdo.

   ![Ventana del programa Visual Studio con el punto de interrupción establecido](./media/debugging-with-visual-studio/vb/set-breakpoint-in-editor.png)

1. Ejecute el programa en el modo de depuración seleccionando el botón **HelloWorld** con la flecha verde en la barra de herramientas, presionando **F5** o seleccionando **Depurar** > **Iniciar depuración**.

1. Cuando el sistema le pida un nombre, escriba una cadena en la ventana de consola y presione **Entrar**.

1. La ejecución del programa se detiene cuando llega al punto de interrupción y antes de que se ejecute el método `Console.WriteLine`. La ventana **Variables locales** muestra los valores de las variables definidas en el método que se ejecuta actualmente.

1. La ventana **Inmediato** le permite interactuar con la aplicación que está depurando. Puede cambiar el valor de las variables de forma interactiva para ver cómo afecta esto al programa.

   1. Si la ventana **Inmediato** no está visible, muéstrela; para ello, elija **Depurar** > **Ventanas** > **Inmediato**.

   1. Escriba `name = "Gracie"` en la ventana **Inmediato** y presione la tecla **Entrar**.

   1. Escriba `date = DateTime.Parse("11/16/2019 5:25 PM")` en la ventana **Inmediato** y presione la tecla **Entrar**.

   Los valores de las variables se actualizan en la ventana **Variables locales**.

1. Seleccione el botón **Continuar** en la barra de herramientas para continuar con la ejecución del programa, o seleccione el elemento de menú **Depurar** > **Continuar**. Los valores mostrados en la ventana de la consola corresponden a los cambios realizados en la ventana **Inmediato**.

   ![Ventana de consola que muestra los valores especificados](./media/debugging-with-visual-studio/console-window.png)

1. Presione cualquier tecla para salir de la aplicación y detenga la depuración.

---

## <a name="set-a-conditional-breakpoint"></a>Establecimiento de un punto de interrupción condicional

Su programa muestra la cadena que escribe el usuario. ¿Qué sucede si el usuario no escribe nada? Puede probar esto con una característica de depuración útil que se denomina *punto de interrupción condicional*, que interrumpe la ejecución del programa cuando se cumplen una o más condiciones.

Para establecer un punto de interrupción condicional y probar lo que sucede cuando el usuario no especifica una cadena, haga lo siguiente:

# <a name="c"></a>[C#](#tab/csharp)

1. Haga clic con el botón derecho en el punto rojo que representa al punto de interrupción. En el menú contextual, seleccione **Condiciones** para abrir el cuadro diálogo **Configuración del punto de interrupción**. Active la casilla **Condiciones** si aún no está seleccionada.

   ![Editor con el panel de configuración de puntos de interrupción: C#](./media/debugging-with-visual-studio/breakpoint-settings.png)

1. Para la **Expresión condicional**, reemplace "por ejemplo, x == 5" por lo siguiente:

   ```csharp
   String.IsNullOrEmpty(name)
   ```

   Se está probando una condición de código, en la que la llamada al método `String.IsNullOrEmpty(name)` es `true` porque `name` no tiene asignado un valor o porque su valor es una cadena vacía (""). En lugar de una expresión condicional, también puede especificar un *número de llamadas*, que es lo que interrumpe la ejecución antes de que una instrucción se ejecute un número especificado de veces; o una *condición de filtro*, que es lo que interrumpe la ejecución del programa en función de atributos como un identificador de subproceso, nombre de proceso o nombre de subproceso.

1. Seleccione **Cerrar** para cerrar el cuadro de diálogo.

1. Inicie el programa con la depuración presionando **F5**.

1. En la ventana de consola, cuando se le pida que escriba su nombre, presione la tecla **Entrar**.

1. Como la condición que especificó (`name` es `null` o <xref:System.String.Empty?displayProperty=nameWithType>) se ha cumplido, la ejecución del programa se detiene cuando se alcanza el punto de interrupción y antes de que se ejecute el método `Console.WriteLine`.

1. Seleccione la ventana **Variables locales**, que muestra los valores de las variables que son locales para el método que se ejecuta actualmente. En este caso, `Main` es el método que se está ejecutando actualmente. Observe que el valor de la variable `name` es `""` o <xref:System.String.Empty?displayProperty=nameWithType>.

1. Confirme que el valor es una cadena vacía escribiendo la siguiente instrucción en la ventana **Inmediato** y presionando **Entrar**. El resultado es `true`.

   ```csharp
   ? name == String.Empty
   ```

   ![Ventana Inmediato en la que se devuelve un valor de True después de que se ejecute la instrucción: C#](./media/debugging-with-visual-studio/immediate-window-output.png)

1. Seleccione el botón **Continuar** en la barra de herramientas para continuar la ejecución del programa.

1. Presione cualquier tecla para cerrar la ventana de consola y detener la depuración.

1. Para borrar el punto de interrupción, haga clic en el punto en el margen izquierdo de la ventana de código, o seleccione **Depurar > Alternar punto de interrupción** mientras la línea de código está seleccionada.

# <a name="visual-basic"></a>[Visual Basic](#tab/vb)

1. Haga clic con el botón derecho en el punto rojo que representa al punto de interrupción. En el menú contextual, seleccione **Condiciones** para abrir el cuadro diálogo **Configuración del punto de interrupción**. Marque la casilla **Condiciones**.

   ![Editor con el panel de configuración de puntos de interrupción: Visual Basic](./media/debugging-with-visual-studio/vb-breakpointsettings.png)

1. Para la **expresión condicional**, reemplace "por ejemplo, x = 5" por lo siguiente:

   ```vb
   String.IsNullOrEmpty(name)
   ```

   Se está probando una condición de código, en la que la llamada al método `String.IsNullOrEmpty(name)` es `true` porque `name` no tiene asignado un valor o porque su valor es una cadena vacía (""). En lugar de una expresión condicional, también puede especificar un *número de llamadas*, que es lo que interrumpe la ejecución antes de que una instrucción se ejecute un número especificado de veces; o una *condición de filtro*, que es lo que interrumpe la ejecución del programa en función de atributos como un identificador de subproceso, nombre de proceso o nombre de subproceso.

1. Seleccione **Cerrar** para cerrar el cuadro de diálogo.

1. Inicie el programa con la depuración presionando **F5**.

1. En la ventana de consola, cuando se le pida que escriba su nombre, presione la tecla **Entrar**.

1. Como la condición que especificó (`name` es `null` o <xref:System.String.Empty?displayProperty=nameWithType>) se ha cumplido, la ejecución del programa se detiene cuando se alcanza el punto de interrupción y antes de que se ejecute el método `Console.WriteLine`.

1. Seleccione la ventana **Variables locales**, que muestra los valores de las variables que son locales para el método que se ejecuta actualmente. En este caso, `Main` es el método que se está ejecutando actualmente. Observe que el valor de la variable `name` es `""` o <xref:System.String.Empty?displayProperty=nameWithType>.

1. Confirme que el valor es una cadena vacía escribiendo la siguiente instrucción en la ventana **Inmediato** y presionando **Entrar**. El resultado es `true`.

   ```vb
   ? String.IsNullOrEmpty(name)
   ```

   ![Ventana Inmediato en la que se devuelve un valor de True después de que se ejecute la instrucción: Visual Basic](./media/debugging-with-visual-studio/vb/immediate-window-output.png)

1. Seleccione el botón **Continuar** en la barra de herramientas para continuar la ejecución del programa.

1. Presione cualquier tecla para cerrar la ventana de consola y detener la depuración.

1. Para borrar el punto de interrupción, haga clic en el punto en el margen izquierdo de la ventana de código, o seleccione el elemento de menú **Depurar > Alternar punto de interrupción** con la fila seleccionada.

---
## <a name="step-through-a-program"></a>Ejecución paso a paso de un programa

Visual Studio también le permite recorrer línea a línea un programa y supervisar su ejecución. Normalmente, establecería un punto de interrupción y usaría esta característica para seguir el flujo del programa mediante una pequeña parte de su código de programa. Como nuestro programa es pequeño, puede ejecutar paso a paso el programa entero:

# <a name="c"></a>[C#](#tab/csharp)

1. En la barra de menús, seleccione **Depurar** > **Paso a paso por instrucciones** o presione la tecla **F11**. Visual Studio resalta y muestra una flecha junto a la siguiente línea de ejecución.

   ![Método Paso a paso por instrucciones de Visual Studio: C#](./media/debugging-with-visual-studio/step-into-method.png)

   En este punto, la ventana **Variables locales** muestra que su programa ha definido solo una variable, `args`. Dado que no ha pasado ningún argumento de línea de comandos al programa, su valor es una matriz de cadena vacía. Además, Visual Studio ha abierto una ventana de consola en blanco.

1. Seleccione **Depurar** > **Paso a paso por instrucciones** o presione **F11**. Visual Studio ahora resalta la siguiente línea de ejecución. Como se muestra en la imagen, el código tarda en ejecutarse menos de una milésima de segundo entre la última instrucción y esta. `args` sigue siendo la única variable declarada y la ventana de consola sigue estando en blanco.

   ![Origen del método Paso a paso por instrucciones de Visual Studio: C#](./media/debugging-with-visual-studio/step-into-source-method.png)

1. Seleccione **Depurar** > **Paso a paso por instrucciones** o presione **F11**. Visual Studio resalta la instrucción que incluye la asignación de variables `name`. La ventana **Variables locales** muestra que `name` es `null`, y la ventana de consola muestra la cadena "What is your name?".

1. Para responder a la solicitud, escriba una cadena en la ventana de consola y presione **Entrar**. La consola no responde y la cadena que especificó no se muestra en la ventana de la consola, pero el método <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> capturará en cambio la entrada.

1. Seleccione **Depurar** > **Paso a paso por instrucciones** o presione **F11**. Visual Studio resalta la instrucción que incluye la asignación de variables `date`. La ventana **Variables locales** muestra el valor devuelto por la llamada al método <xref:System.Console.ReadLine%2A?displayProperty=nameWithType>. La ventana de la consola también muestra la cadena que escribió en la solicitud.

1. Seleccione **Depurar** > **Paso a paso por instrucciones** o presione **F11**. La ventana **Variables locales** muestra el valor de la variable `date` tras la asignación desde la propiedad <xref:System.DateTime.Now?displayProperty=nameWithType>. La ventana de consola permanece sin cambios.

1. Seleccione **Depurar** > **Paso a paso por instrucciones** o presione **F11**. Visual Studio llama al método <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType>. La ventana de la consola muestra la cadena con formato.

1. Seleccione **Depurar** > **Paso a paso para salir** o presione **Mayús**+**F11**. Esta acción detiene la ejecución paso a paso. La ventana de la consola muestra un mensaje y espera a que presione una tecla.

1. Presione cualquier tecla para cerrar la ventana de consola y detener la depuración.

# <a name="visual-basic"></a>[Visual Basic](#tab/vb)

1. En la barra de menús, seleccione **Depurar** > **Paso a paso por instrucciones** o presione la tecla **F11**. Visual Studio resalta y muestra una flecha junto a la siguiente línea de ejecución.

   ![Método Paso a paso por instrucciones de Visual Studio: Visual Basic](./media/debugging-with-visual-studio/vb-step-into-method.png)

   En este punto, la ventana **Variables locales** muestra que su programa ha definido solo una variable, `args`. Dado que no ha pasado ningún argumento de línea de comandos al programa, su valor es una matriz de cadena vacía. Además, Visual Studio ha abierto una ventana de consola en blanco.

1. Seleccione **Depurar** > **Paso a paso por instrucciones** o presione **F11**. Visual Studio ahora resalta la siguiente línea de ejecución. Como se muestra en la ilustración, el código tarda en ejecutarse menos de una milésima de segundo entre la última instrucción y esta. `args` sigue siendo la única variable declarada y la ventana de consola sigue estando en blanco.

   ![Origen del método Paso a paso por instrucciones de Visual Studio: Visual Basic](./media/debugging-with-visual-studio/vb-step-into-source-method.png)

1. Seleccione **Depurar** > **Paso a paso por instrucciones** o presione **F11**. Visual Studio resalta la instrucción que incluye la asignación de variables `name`. La ventana **Variables locales** muestra que `name` es `Nothing`, y la ventana de consola muestra la cadena "What is your name?".

1. Para responder a la solicitud, escriba una cadena en la ventana de consola y presione **Entrar**. La consola no responde y la cadena que especifique no se muestra en la ventana de la consola, pero el método <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> capturará en cambio la entrada.

1. Seleccione **Depurar** > **Paso a paso por instrucciones** o presione **F11**. Visual Studio resalta la instrucción que incluye la asignación de variables `currentDate`. La ventana **Variables locales** muestra el valor devuelto por la llamada al método <xref:System.Console.ReadLine%2A?displayProperty=nameWithType>. La ventana de la consola también muestra la cadena especificada cuando se solicitó la entrada.

1. Seleccione **Depurar** > **Paso a paso por instrucciones** o presione **F11**. La ventana de consola permanece sin cambios.

1. Seleccione **Depurar** > **Paso a paso por instrucciones** o presione **F11**. Visual Studio llama al método <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType>. La ventana de la consola muestra la cadena con formato.

1. Seleccione **Depurar** > **Paso a paso para salir** o presione **Mayús**+**F11**. Esta acción detiene la ejecución paso a paso. La ventana de la consola muestra un mensaje y espera a que presione una tecla.

1. Presione cualquier tecla para cerrar la ventana de consola y detener la depuración.

---

## <a name="build-a-release-version"></a>Creación de una versión de lanzamiento

Una vez que ha probado la versión de depuración de la aplicación, también debe compilar y probar la versión de lanzamiento. La versión de lanzamiento incorpora optimizaciones del compilador que en ocasiones afectan negativamente al comportamiento de una aplicación. Por ejemplo, las optimizaciones del compilador que están diseñadas para mejorar el rendimiento pueden crear condiciones de carrera en aplicaciones multiproceso.

Para compilar y probar la versión de lanzamiento de la aplicación de la consola, cambie la configuración de compilación en la barra de herramientas de **Depurar** a **Versión**.

![Barra de herramientas predeterminada de Visual Studio con Depuración resaltado](./media/debugging-with-visual-studio/visual-studio-toolbar-release.png)

Cuando presiona **F5** o elije **Compilar solución** en el menú **Compilar**, Visual Studio compila la versión de lanzamiento de la aplicación. Puede probarla como hizo con la versión de depuración.

## <a name="next-steps"></a>Pasos siguientes

Cuando haya depurado la aplicación, el siguiente paso es publicar una versión implementable de la misma. Para más información sobre cómo hacerlo, vea [Publicación de la aplicación Hola mundo de .NET Core con Visual Studio 2017](publishing-with-visual-studio.md).
