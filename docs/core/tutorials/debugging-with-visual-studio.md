---
title: "Depuración de una aplicación Hola mundo de .NET Core en C# o Visual Basic con Visual Studio 2017"
description: "Obtenga información sobre cómo depurar una aplicación Hola mundo, escrita en C# o Visual Basic, con Visual Studio 2017."
keywords: ".NET Core, aplicación de consola de .NET Core, depuración de .NET Core"
author: BillWagner
ms.author: wiwagn
ms.date: 12/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: cb213625-cc60-438b-9b9e-49aed0e4a974
ms.workload: dotnetcore
ms.openlocfilehash: 6c8e1de4e0053ae6f74dc6c74fe37b6d7661932e
ms.sourcegitcommit: 91691981897cf8451033cb01071d8f5d94017f97
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2018
---
# <a name="debug-your-hello-world-application-with-visual-studio-2017"></a>Depuración de la aplicación Hola a todos con Visual Studio 2017

Hasta ahora, ha seguido los pasos descritos en [Compilación de una aplicación Hola a todos en C# con .NET Core en Visual Studio 2017](.\with-visual-studio.md) o [Compilación de una aplicación Hola a todos en Visual Basic con .NET Core en Visual Studio 2017](vb-with-visual-studio.md) para crear y ejecutar una aplicación de consola sencilla. Cuando haya escrito y compilado la aplicación, puede comenzar a probarla. Visual Studio incluye un conjunto completo de herramientas de depuración que puede usar para probar y solucionar problemas de la aplicación.

## <a name="debugging-in-debug-mode"></a>Depuración en modo de depuración

El modo de *depuración* y *versión* son dos de las configuraciones de compilación predeterminadas de Visual Studio. La configuración de compilación actual se muestra en la barra de herramientas. En la siguiente imagen de la barra de herramientas se muestra que Visual Studio está configurado para compilar la aplicación en el modo de **depuración**.

   ![Barra de herramientas de Visual Studio](./media/debugging-with-visual-studio/toolbar1.png)

Siempre debe empezar probando el programa en modo de depuración. El modo de depuración desactiva la mayoría de las optimizaciones del compilador y proporciona información más completa durante el proceso de compilación.

## <a name="setting-a-breakpoint"></a>Establecer un punto de interrupción

Ejecute su programa en el modo de depuración y pruebe algunas características de depuración:

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
1. Un *punto de interrupción* interrumpe temporalmente la ejecución de la aplicación *antes* de que se ejecute la línea con el punto de interrupción. 

   Establezca un punto de interrupción en la línea que dice `Console.WriteLine($"\nHello, {name}, on {date:d} at {date:t}!");` haciendo clic en el margen izquierdo de la ventana de código en esa línea o seleccione el elemento de menú **Depurar** > **Alternar punto de interrupción** con la línea seleccionada. Como se muestra en la siguiente ilustración, para indicar la línea en la que se establece el punto de interrupción, Visual Studio lo resalta y muestra un círculo rojo en el margen izquierdo.

   ![Ventana del programa Visual Studio con el punto de interrupción establecido](./media/debugging-with-visual-studio/setbreakpoint.png)

1. Ejecute el programa en el modo de depuración seleccionando el botón **HelloWorld** con la flecha verde en la barra de herramientas, presionando F5 o seleccionando **Depurar** > **Iniciar depuración**.

1. Cuando el sistema le pida un nombre, escriba una cadena en la ventana de consola y presione Entrar.

1. La ejecución del programa se detiene cuando llega al punto de interrupción y antes de que se ejecute el método `Console.WriteLine`. La ventana **Automático** muestra los valores de variables que se usan en torno a la línea actual. La ventana **Variables locales** (que puede ver haciendo clic en la pestaña **Variables locales**) muestra los valores de las variables definidas en el método que se ejecuta actualmente.

   ![Ventana de la aplicación de Visual Studio](./media/debugging-with-visual-studio/break.png)

1. Puede cambiar el valor de las variables para ver cómo afecta esto a su programa. Si la **ventana Inmediato** no está visible, muéstrela, para ello, seleccione el elemento de menú **Depurar** > **Ventanas** > **Inmediato**. La **ventana Inmediato** le permite interactuar con la aplicación que está depurando.

1. Puede cambiar los valores de las variables de manera interactiva. Escriba `name = "Gracie"` en la **ventana Inmediato** y presione la tecla Entrar.

1. Escriba `date = new DateTime(2016,11,01,11,59,00)` en la **ventana Inmediato** y presione la tecla Entrar.

   La **ventana Inmediato** muestra el valor de la variable de cadena y las propiedades del valor <xref:System.DateTime>. Además, el valor de las variables se actualiza en las ventanas **Automático** y **Variables locales**.

   ![Ventana Automático y ventana Inmediato](./media/debugging-with-visual-studio/autosimmediate.png)

1. Seleccione el botón **Continuar** en la barra de herramientas para continuar con la ejecución del programa, o seleccione el elemento de menú **Depurar** > **Continuar**. Los valores mostrados en la ventana de la consola corresponden a los cambios realizados en la **ventana Inmediato**.

   ![Ventana de la consola que muestra el valor de tipo Jack en el mensaje What is your name? seguido de Hello Gracie el 1/11/2016 a las 11:59](./media/debugging-with-visual-studio/changed.png)

1. Presione cualquier tecla para salir de la aplicación y finalice el modo de depuración.
# <a name="visual-basictabvb"></a>[Visual Basic](#tab/vb)
1. Un *punto de interrupción* interrumpe temporalmente la ejecución de la aplicación *antes* de que se ejecute la línea con el punto de interrupción. 

   Establezca un punto de interrupción en la línea que dice `Console.WriteLine(vbCrLf + $"Hello, {name}, on {currentDate:d} at {currentDate:t}!")` haciendo clic en el margen izquierdo de la ventana de código en esa línea o seleccione el elemento de menú **Depurar** > **Alternar punto de interrupción** con la línea seleccionada. Como se muestra en la siguiente ilustración, para indicar la línea en la que se establece el punto de interrupción, Visual Studio lo resalta y muestra un círculo rojo en el margen izquierdo.

   ![Ventana del programa Visual Studio con el punto de interrupción establecido](./media/debugging-with-visual-studio/vb-setbreakpoint.png)

1. Ejecute el programa en el modo de depuración seleccionando el botón **HelloWorld** con la flecha verde en la barra de herramientas, presionando F5 o seleccionando **Depurar** > **Iniciar depuración**.

1. Cuando el sistema le pida un nombre, escriba una cadena en la ventana de consola y presione Entrar.

1. La ejecución del programa se detiene cuando llega al punto de interrupción y antes de que se ejecute el método `Console.WriteLine`. La ventana **Automático** muestra los valores de variables que se usan en torno a la línea actual. La ventana **Variables locales** (que puede ver haciendo clic en la pestaña **Variables locales**) muestra los valores de las variables definidas en el método que se ejecuta actualmente.

   ![Ventana de la aplicación de Visual Studio](./media/debugging-with-visual-studio/vb-break.png)

1. Puede cambiar el valor de las variables para ver cómo afecta esto a su programa. Si la **ventana Inmediato** no está visible, muéstrela, para ello, seleccione el elemento de menú **Depurar** > **Ventanas** > **Inmediato**. La **ventana Inmediato** le permite interactuar con la aplicación que está depurando.

1. Puede cambiar los valores de las variables de manera interactiva. Escriba `name = "Gracie"` en la **ventana Inmediato** y presione la tecla Entrar.

1. Escriba `currentDate = new DateTime(2016,11,01,11,59,00)` en la **ventana Inmediato** y presione la tecla Entrar.

1. Seleccione el botón **Continuar** en la barra de herramientas para continuar con la ejecución del programa, o seleccione el elemento de menú **Depurar** > **Continuar**. Los valores mostrados en la ventana de la consola corresponden a los cambios realizados en la **ventana Inmediato**.

   ![Ventana de consola que muestra los valores cambiados especificados en la ventana Inmediato](./media/debugging-with-visual-studio/changed.png)

1. Presione cualquier tecla para salir de la aplicación y finalice el modo de depuración.
---

## <a name="setting-a-conditional-breakpoint"></a>Establecimiento de un punto de interrupción condicional

Su programa muestra la cadena que escribe el usuario. ¿Qué sucede si el usuario no escribe nada? Puede probar esto con una característica de depuración útil, el *punto de interrupción condicional*, que interrumpe la ejecución del programa cuando se cumplen una o más condiciones.

Para establecer un punto de interrupción condicional y probar lo que sucede cuando el usuario no especifica una cadena, haga lo siguiente:

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
1. Haga clic con el botón derecho en el punto rojo que representa al punto de interrupción. En el menú contextual, seleccione **Condiciones** para abrir el cuadro diálogo **Configuración del punto de interrupción**. Marque la casilla **Condiciones**.

   ![Panel de configuración de punto de interrupción](./media/debugging-with-visual-studio/breakpointsettings.png)

1. Para la **expresión condicional**, reemplace "por ejemplo, x == 5" por lo siguiente:

   ```csharp
   String.IsNullOrEmpty(name)
   ```

   Se está probando una condición de código, en la que la llamada al método `String.IsNullOrEmpty(name)` es `true` porque *name* no tiene asignado un valor o porque su valor es una cadena vacía (""). También puede especificar un *número de llamadas*, que es lo que interrumpe la ejecución antes de que una instrucción se ejecute un número especificado de veces; o una *condición de filtro*, que es lo que interrumpe la ejecución del programa en función de atributos como un identificador de subproceso, nombre de proceso o nombre de subproceso.

1. Seleccione el botón **Cerrar** para cerrar el cuadro de diálogo.

1. Ejecute el programa en modo de depuración.

1. En la ventana de consola, cuando se le pida que escriba su nombre, presione la tecla Entrar.

1. Como la condición que hemos especificado, `name` es `null` o <xref:System.String.Empty?displayProperty=nameWithType>, se ha cumplido, la ejecución del programa se detiene cuando se alcanza el punto de interrupción y antes de que se ejecute el método `Console.WriteLine`.

1. Seleccione la ventana **Variables locales**, que muestra los valores de las variables que son locales para el método que se ejecuta actualmente, que es el método `Main` en su programa. Observe que el valor de la variable `name` es `""` o <xref:System.String.Empty?displayProperty=nameWithType>.

1. Confirme que el valor es una cadena vacía escribiendo la siguiente instrucción en la **ventana Inmediato**. El resultado es `true`.

   ```csharp
   ? name == String.Empty
   ```

   ![La ventana Inmediato devolviendo un valor de True después de que se ejecute la instrucción](./media/debugging-with-visual-studio/emptystring.png)

1. Seleccione el botón **Continuar** en la barra de herramientas para continuar la ejecución del programa.

1. Presione cualquier tecla para cerrar la ventana de consola y salir del modo de depuración.

1. Para borrar el punto de interrupción, haga clic en el punto en el margen izquierdo de la ventana de código, o seleccione el elemento de menú **Depurar > Alternar punto de interrupción** con la fila seleccionada.
# <a name="visual-basictabvb"></a>[Visual Basic](#tab/vb)
1. Haga clic con el botón derecho en el punto rojo que representa al punto de interrupción. En el menú contextual, seleccione **Condiciones** para abrir el cuadro diálogo **Configuración del punto de interrupción**. Marque la casilla **Condiciones**.

   ![Panel de configuración de punto de interrupción](./media/debugging-with-visual-studio/vb-breakpointsettings.png)

1. Para la **expresión condicional**, reemplace "por ejemplo, x = 5" por lo siguiente:

   ```vb
   String.IsNullOrEmpty(name)
   ```

   Se está probando una condición de código, en la que la llamada al método `String.IsNullOrEmpty(name)` es `True` porque *name* no tiene asignado un valor o porque su valor es una cadena vacía (""). También puede especificar un *número de llamadas*, que es lo que interrumpe la ejecución antes de que una instrucción se ejecute un número especificado de veces; o una *condición de filtro*, que es lo que interrumpe la ejecución del programa en función de atributos como un identificador de subproceso, nombre de proceso o nombre de subproceso.

1. Seleccione el botón **Cerrar** para cerrar el cuadro de diálogo.

1. Ejecute el programa en modo de depuración.

1. En la ventana de consola, cuando se le pida que escriba su nombre, presione la tecla Entrar.

1. Como la condición que hemos especificado, `name` es `null` o <xref:System.String.Empty?displayProperty=nameWithType>, se ha cumplido, la ejecución del programa se detiene cuando se alcanza el punto de interrupción y antes de que se ejecute el método `Console.WriteLine`.

1. Seleccione la ventana **Variables locales**, que muestra los valores de las variables que son locales para el método que se ejecuta actualmente, que es el método `Main` en su programa. Observe que el valor de la variable `name` es `""` o <xref:System.String.Empty?displayProperty=nameWithType>.

1. Confirme que el valor es una cadena vacía escribiendo la siguiente instrucción en la **ventana Inmediato**. El resultado es `true`.

   ```vb
   ? String.IsNullOrEmpty(name)
   ```
  ![La ventana Inmediato devolviendo un valor de True después de que se ejecute la instrucción](./media/debugging-with-visual-studio/vb-emptystring.png)

1. Seleccione el botón **Continuar** en la barra de herramientas para continuar la ejecución del programa.

1. Presione cualquier tecla para cerrar la ventana de consola y salir del modo de depuración.

1. Para borrar el punto de interrupción, haga clic en el punto en el margen izquierdo de la ventana de código, o seleccione el elemento de menú **Depurar > Alternar punto de interrupción** con la fila seleccionada.
---
## <a name="stepping-through-a-program"></a>Ejecución paso a paso de un programa

Visual Studio también le permite recorrer línea a línea un programa y supervisar su ejecución. Normalmente, establecería un punto de interrupción y usaría esta característica para seguir el flujo del programa mediante una pequeña parte de su código de programa. Como nuestro programa es pequeño, puede ejecutar paso a paso el programa entero realizando lo siguiente:

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
1. En la barra de menús, seleccione **Depurar** > **Paso a paso por instrucciones** o presione la tecla F11. Visual Studio resalta y muestra una flecha junto a la siguiente línea de ejecución.

   ![Ventana de Visual Studio](./media/debugging-with-visual-studio/stepinto1.png)

   En este punto, la ventana **Automático** muestra que su programa ha definido solo una variable, `args`. Dado que no ha pasado ningún argumento de línea de comandos al programa, su valor es una matriz de cadena vacía. Además, Visual Studio ha abierto una ventana de consola en blanco.

1. Seleccione **Depurar** > **Paso a paso por instrucciones** o presione la tecla F11. Visual Studio ahora resalta la siguiente línea de ejecución. Como se muestra en la ilustración, el código tarda en ejecutarse menos de una milésima de segundo entre la última instrucción y esta. `args` sigue siendo la única variable declarada y la ventana de consola sigue estando en blanco.

   ![Ventana de Visual Studio](./media/debugging-with-visual-studio/stepinto2.png)

1. Seleccione **Depurar** > **Paso a paso por instrucciones** o presione la tecla F11. Visual Studio resalta la instrucción que incluye la asignación de variables `name`. La ventana **Automático** muestra que `name` es `null`, y la ventana de consola muestra la cadena "What is your name?".

1. Para responder a la solicitud, escriba una cadena en la ventana de consola y presione Entrar. La consola no responde y la cadena que especifique no se muestra en la ventana de la consola, pero el método <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> capturará en cambio la entrada.

1. Seleccione **Depurar** > **Paso a paso por instrucciones** o presione la tecla F11. Visual Studio resalta la instrucción que incluye la asignación de variables `date` (en C#) o `currentDate` (en Visual Basic). La ventana **Automático** muestra el valor de propiedad <xref:System.DateTime.Now?displayProperty=nameWithType> y el valor devuelto por la llamada al método <xref:System.Console.ReadLine%2A?displayProperty=nameWithType>. La ventana de la consola también muestra la cadena especificada cuando se solicitó la entrada.

1. Seleccione **Depurar** > **Paso a paso por instrucciones** o presione la tecla F11. La ventana **Automático** muestra el valor de la variable `date` tras la asignación desde la propiedad <xref:System.DateTime.Now?displayProperty=nameWithType>. La ventana de consola permanece sin cambios.

1. Seleccione **Depurar** > **Paso a paso por instrucciones** o presione la tecla F11. Visual Studio llama al método <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType>. Los valores de las variables `date` (o `currentDate`) y `name` aparecen en la ventana **Automático** y la ventana de consola muestra la cadena con formato.

1. Seleccione **Depurar** > **Paso a paso para salir** o presione la tecla Mayús y la tecla F11. Esta acción detiene la ejecución paso a paso. La ventana de la consola muestra un mensaje y espera a que presione una tecla.

1. Presione cualquier tecla para cerrar la ventana de consola y salir del modo de depuración.
# <a name="visual-basictabvb"></a>[Visual Basic](#tab/vb)
1. En la barra de menús, seleccione **Depurar** > **Paso a paso por instrucciones** o presione la tecla F11. Visual Studio resalta y muestra una flecha junto a la siguiente línea de ejecución.

   ![Ventana de Visual Studio](./media/debugging-with-visual-studio/vb-stepinto1.png)

   En este punto, como no ha pasado ningún argumento de línea de comandos al programa, la ventana **Automático** muestra que el valor de la variable `args` es una matriz de cadena vacía. Además, Visual Studio ha abierto una ventana de consola en blanco.

1. Seleccione **Depurar** > **Paso a paso por instrucciones** o presione la tecla F11. Visual Studio ahora resalta la siguiente línea de ejecución. Como se muestra en la ilustración, el código tarda en ejecutarse menos de una milésima de segundo entre la última instrucción y esta. `args` sigue siendo la única variable declarada y la ventana de consola sigue estando en blanco.

   ![Ventana de Visual Studio](./media/debugging-with-visual-studio/vb-stepinto2.png)

1. Seleccione **Depurar** > **Paso a paso por instrucciones** o presione la tecla F11. Visual Studio resalta la instrucción que incluye la asignación de variables `name`. La ventana **Automático** muestra que `name` es `Nothing`, y la ventana de consola muestra la cadena "What is your name?".

1. Para responder a la solicitud, escriba una cadena en la ventana de consola y presione Entrar. La consola no responde y la cadena que especifique no se muestra en la ventana de la consola, pero el método <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> capturará en cambio la entrada.

1. Seleccione **Depurar** > **Paso a paso por instrucciones** o presione la tecla F11. Visual Studio resalta la instrucción que incluye la asignación de variables `date` (en C#) o `currentDate` (en Visual Basic). La ventana **Automático** muestra el valor de propiedad <xref:System.DateTime.Now?displayProperty=nameWithType> y el valor devuelto por la llamada al método <xref:System.Console.ReadLine%2A?displayProperty=nameWithType>. La ventana de la consola también muestra la cadena especificada cuando se solicitó la entrada.

1. Seleccione **Depurar** > **Paso a paso por instrucciones** o presione la tecla F11. La ventana **Automático** muestra el valor de la variable `date` tras la asignación desde la propiedad <xref:System.DateTime.Now?displayProperty=nameWithType>. La ventana de consola permanece sin cambios.

1. Seleccione **Depurar** > **Paso a paso por instrucciones** o presione la tecla F11. Visual Studio llama al método <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType>. Los valores de las variables `date` (o `currentDate`) y `name` aparecen en la ventana **Automático** y la ventana de consola muestra la cadena con formato.

1. Seleccione **Depurar** > **Paso a paso para salir** o presione la tecla Mayús y la tecla F11. Esta acción detiene la ejecución paso a paso. La ventana de la consola muestra un mensaje y espera a que presione una tecla.

1. Presione cualquier tecla para cerrar la ventana de consola y salir del modo de depuración.
---

## <a name="building-a-release-version"></a>Creación de una versión de lanzamiento

Una vez que ha probado la compilación de depuración de la aplicación, también debe compilar y probar la versión de lanzamiento. La versión de lanzamiento incorpora optimizaciones del compilador que en ocasiones afectan negativamente al comportamiento de una aplicación. Por ejemplo, las optimizaciones del compilador que están diseñadas para mejorar el rendimiento pueden crear condiciones de carrera en aplicaciones multiproceso o asincrónicas.

Para compilar y probar la versión de lanzamiento de la aplicación de la consola, cambie la configuración de compilación en la barra de herramientas de **Depurar** a **Versión**.

![Imagen](./media/debugging-with-visual-studio/toolbar2.png)

Cuando presiona F5 o selecciona **Compilar solución** en el menú **Compilar**, Visual Studio compila la versión de lanzamiento de la aplicación de consola. Puede probarla como hizo con la versión de depuración de la aplicación.

Cuando haya terminado de depurar la aplicación, el siguiente paso es publicar una versión implementable de la aplicación. Para obtener más información sobre cómo hacerlo, vea [Publicación de la aplicación Hola a todos con Visual Studio 2017](./publishing-with-visual-studio.md).
