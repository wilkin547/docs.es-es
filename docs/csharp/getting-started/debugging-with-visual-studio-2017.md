---
title: "Depuración de la aplicación Hola a todos en C# con Visual Studio 2017"
description: "Aprenda a depurar una aplicación Hola a todos, escrita en C# con Visual Studio 2017"
keywords: ".NET Core, aplicación de consola de .NET Core, depuración de .NET Core"
author: BillWagner
ms.author: wiwagn
ms.date: 10/24/2016
ms.topic: article
ms.prod: .net-core
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: cb213625-cc60-438b-9b9e-49aed0e4a974
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 6a6a461984c140d180cf70cd7a1a33818a40b451
ms.lasthandoff: 03/13/2017

---

# <a name="debugging-your-c-hello-world-application-with-visual-studio-2017"></a>Depuración de la aplicación Hola a todos en C# con Visual Studio 2017 #

Hasta ahora, ha seguido los pasos descritos en [Building a c# Hello World Application with .NET Core in Visual Studio 2017](.\with-visual-studio-2017.md) (Compilación de una aplicación Hola a todos en C# con .NET Core en Visual Studio 2017) para crear y ejecutar una aplicación de consola sencilla. Cuando haya escrito y compilado una aplicación, puede comenzar a probarla. Visual Studio incluye un conjunto completo de herramientas de depuración que puede usar para probar y solucionar problemas de la aplicación. Echemos un vistazo a algunas de ellas mientras depuramos nuestra aplicación.

## <a name="debugging-in-debug-mode"></a>Depuración en modo de depuración ##

El modo de depuración es una de las dos configuraciones de compilación predeterminadas de Visual Studio. (La otra es modo de versión). La configuración de compilación actual se muestra en la barra de herramientas. La siguiente ilustración muestra que nuestra aplicación se compilará en modo de depuración.

   ![Imagen](./media/debugmode.jpg)

Siempre debe empezar probando el programa en modo de depuración. El modo de depuración desactiva la mayoría de las optimizaciones del compilador y proporciona información más completa en el archivo de base de datos de símbolos (archivos .pdb) de salida del proceso de compilación.

## <a name="setting-a-breakpoint"></a>Establecer un punto de interrupción ##

Vamos a ejecutar nuestro programa en modo de depuración y probar algunas características de depuración:

1. Establezca un punto de interrupción; sitúe el cursor en la línea que dice `Console.WriteLine("\nHello, {0}, on {1:d} at {1:t}", name, date);` y haga clic en el margen izquierdo de la ventana de código o elija el elemento de menú **Depurar**, **Alternar puntos de interrupción**. (Un punto de interrupción interrumpe temporalmente la ejecución de la aplicación *antes de* que se ejecute la línea con el punto de interrupción). Como se muestra en la siguiente ilustración, para indicar la línea en la que se establece el punto de interrupción, Visual Studio lo resalta y muestra un círculo rojo en el margen izquierdo.

   ![Imagen](./media/setbreakpoint_2017.jpg)

1. Ejecute el programa en modo de depuración; para ello, seleccione el botón "Hola a todos" con la flecha verde en la barra de herramientas, presione F5 o elija **Depurar**, **Iniciar depuración**.

1. Cuando el sistema le pida un nombre, escriba una cadena en la ventana de consola y presione Entrar.

1. La ejecución del programa se detiene cuando llega al punto de interrupción y antes de que se ejecute el método `Console.WriteLine`. Visual Studio debe tener el aspecto de la siguiente ilustración. Tenga en cuenta que la ventana **Automático** muestra los valores de variables que se usan en torno a la línea actual. (La ventana **Variables locales** muestra los valores de variables definidas en el método que se ejecuta actualmente).

   ![Imagen](./media/breakpoint_2017.jpg)

1. Vamos a intentar cambiar el valor de las variables para ver cómo afecta esto a nuestro programa. Si la **ventana Inmediato** no está visible, múestrela, para ello, elija el elemento de menú **Depurar**, **Ventanas**, **Inmediato**. La **ventana Inmediato** le permite interactuar con la aplicación que está depurando.

1. Puede cambiar los valores de las variables de manera interactiva. Escriba `name = "Yuma"` en la ventana Inmediato y presione la tecla Entrar.

1. Escriba `date = new DateTime(2016,11,01,11,59,00)` en la ventana Inmediato y presione la tecla Entrar.

   La siguiente imagen muestra la **ventana Inmediato**:

   ![Imagen](./media/immediatewindow.jpg)

   Tenga en cuenta que la ventana muestra el valor de la variable de cadena y las propiedades del valor @System.DateTime. Además, el valor de las variables se actualiza en las ventanas **Automático** y **Variables locales**.

1. Seleccione el botón **Continuar** en la barra de herramientas para continuar con la ejecución del programa, o elija el elemento de menú **Depurar**, **Continuar**. La ventana de consola resultante debe ser similar a la siguiente imagen. Tenga en cuenta que los valores mostrados en la ventana de consola también corresponden a los cambios realizados en la **ventana Inmediato**.

   ![Imagen](./media/changed.jpg)

1. Presione cualquier tecla para salir de la aplicación y finalice el modo de depuración.

## <a name="setting-a-conditional-breakpoint"></a>Establecimiento de un punto de interrupción condicional ##

Ahora sabemos que nuestro programa mostrará correctamente la cadena que el usuario inserta. ¿Pero qué sucede si el usuario no inserta nada? Podemos probar esto y durante el proceso usar otra característica de depuración, la posibilidad de establecer un punto de interrupción condicional.

Para establecer un punto de interrupción condicional y probar lo que sucede cuando el usuario no especifica una cadena, haga lo siguiente:

1. Haga clic con el botón derecho en el punto rojo que representa al punto de interrupción. En el menú contextual, seleccione **Condiciones...** para abrir el diálogo **Configuración del punto de interrupción** que se muestra en la ilustración siguiente.

   ![Imagen](./media/breakpoint_settings.jpg)

1. En el cuadro de texto que pone "por ejemplo, x == 5", escriba lo siguiente:

   ```csharp
   String.IsNullOrEmpty(name)
   ```

   En este caso, estamos probando una condición de código. También podemos especificar un número de llamadas, qué es lo que interrumpe la ejecución antes de que una instrucción se ejecute un número especificado de veces; o una condición de filtro, qué es lo que interrumpe la ejecución del programa en función de atributos tales como identificador de subproceso, nombre de proceso o nombre de subproceso.

1. Elija el botón **Cerrar** para cerrar el diálogo.

1. Ejecute el programa en modo de depuración.

1. En la ventana de consola, cuando se le pida que escriba su nombre, presione la tecla Entrar.

1. Como la condición que hemos especificado se ha satisfecho, `name` es `null` o [String.Empty](xref:System.String.Empty), la ejecución del programa se detiene cuando se alcanza el punto de interrupción y antes de que se ejecute el método `Console.WriteLine`.

1. Elija la ventana **Variables locales**, que muestra los valores de las variables que son locales para el método que se ejecuta actualmente, en este caso el método `Main`.

1. Tenga en cuenta que el valor de la variable `name` es "" o [String.Empty](xref:System.String.Empty). Para confirmar esto, escriba la siguiente instrucción en la **ventana Inmediato**:

   ```csharp
   ? name == String.Empty
   ```

   En la siguiente ilustración se muestra el resultado.

   ![Imagen](./media/emptystring.jpg)

1. Elija el botón **Continuar** en la barra de herramientas para continuar la ejecución del programa.

1. Presione cualquier tecla para cerrar la ventana de consola y salir del modo de depuración.

1. Para borrar el punto de interrupción, haga clic en el punto en el margen izquierdo de la ventana de código, o elija el elemento de menú **Depurar**, **Alternar puntos de interrupción**.

## <a name="stepping-through-a-program"></a>Ejecución paso a paso de un programa ##

Visual Studio también nos permite recorrer línea a línea un programa y supervisar su ejecución. Normalmente, establecería un punto de interrupción y usaría esta característica para seguir el flujo del programa mediante una pequeña parte de su código de programa. Sin embargo, como nuestro programa es pequeño, vamos a ejecutar paso a paso el programa entero realizando lo siguiente:

1. En la barra de menús, elija **Depurar**, **Paso a paso por instrucciones**, o presione la tecla F11. Visual Studio resalta y muestra una flecha junto a la línea que se va a ejecutar a continuación, como se muestra en la siguiente ilustración.

   ![Imagen](./media/step_into.jpg)

   En este punto, la ventana **Automático** muestra que nuestro programa ha definido solo una variable `args`. Dado que no hemos pasado ningún argumento de línea de comandos al programa, su valor es una matriz de cadena vacía. Además, Visual Studio ha abierto una ventana de consola en blanco.

1. Elija **Depurar**, **Paso a paso por instrucciones**, o presione la tecla F11. Visual Studio ahora resalta la siguiente línea que se va a ejecutar. Como se muestra en la ilustración, el código tarda en ejecutarse 3 milésimas de segundo entre la última instrucción y esta. `args` sigue siendo la única variable declarada y la ventana de consola aún está en blanco.

   ![Imagen](./media/step_into_2.jpg)

1. Elija **Depurar**, **Paso a paso por instrucciones**, o presione la tecla F11. Visual Studio resalta la instrucción que incluye la asignación de variables `name`. La ventana **Automático** muestra que `name` es `null`, y la ventana de consola muestra la cadena "What is your name?".

1. Para responder a la solicitud, escriba una cadena en la ventana de consola y presione Entrar. La consola dejará de responder y la cadena que especifique no se mostrará en la ventana de consola, pero el método [Console.ReadLine](xref:System.Console.ReadLine) capturará sin embargo la entrada.

1. Elija **Depurar**, **Paso a paso por instrucciones**, o presione la tecla F11. Visual Studio resalta la instrucción que incluye la asignación de variables `date`. La ventana **Automático** muestra el valor de propiedad [DateTime.Now](xref:System.DateTime.Now) y el valor devuelto por la llamada al método [Console.ReadLine](xref:System.Console.ReadLine). La ventana de la consola también muestra la cadena especificada cuando se solicitó la entrada.

1. Elija **Depurar**, **Paso a paso por instrucciones**, o presione la tecla F11. La ventana **Automático** muestra ahora el valor de la variable `date` tras la asignación desde la propiedad [DateTime.Now](xref:System.DateTime.Now). La ventana de consola permanece sin cambios.

1. Elija **Depurar**, **Paso a paso por instrucciones**, o presione la tecla F11. Visual Studio llama al método [Console.WriteLine](xref:System.Console.WriteLine(System.String,System.Object,System.Object)). Los valores de las variables `date` y `name` aparecen en la ventana **Automático** y la ventana de consola muestra la cadena con formato.

1. Elija **Depurar**, **Paso a paso para salir**, o presione la tecla MAYÚS y la tecla F11. Esta acción detiene la ejecución paso a paso. La ventana de consola muestra un mensaje y espera a que presionemos una tecla.

1. Presione cualquier tecla para cerrar la ventana de consola y salir del modo de depuración.

## <a name="building-a-release-version"></a>Creación de una versión ##

Una vez que ha probado la compilación de depuración de la aplicación, debe compilar y probar la versión. La versión incorpora optimizaciones del compilador que en ocasiones afectan al comportamiento de una aplicación. Por ejemplo, las optimizaciones del compilador que están diseñadas para mejorar el rendimiento pueden crear condiciones de carrera en aplicaciones multiproceso o asincrónicas.

Para compilar y probar la versión de la aplicación de consola, cambie la configuración de compilación en la barra de herramientas de **Depurar** a **Versión**, como se muestra en la ilustración siguiente.

![Imagen](./media/release.jpg)

Cuando presiona F5 o elige **Compilar solución** en el menú **Compilar**, Visual Studio compila la versión de la aplicación de consola para que la pruebe. A continuación, puede ejecutarla y probarla como hizo con la versión de depuración de la aplicación.

Cuando haya terminado de depurar la aplicación, el siguiente paso es publicar una versión de distribución de la aplicación. Para más información sobre cómo hacerlo, consulte [Publicación de la aplicación Hola a todos con Visual Studio 2017](./publishing-with-visual-studio-2017.md).

