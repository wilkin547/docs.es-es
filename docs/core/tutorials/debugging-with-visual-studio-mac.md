---
title: Depuración de una aplicación de consola de .NET Core con Visual Studio para Mac
description: Aprenda a depurar una aplicación de consola de .NET Core con Visual Studio para Mac.
ms.date: 06/08/2020
ms.openlocfilehash: 4941605923a9897d481aca4ec31408ab62e873f3
ms.sourcegitcommit: 1cbd77da54405ea7dba343ac0334fb03237d25d2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2020
ms.locfileid: "84713488"
---
# <a name="tutorial-debug-a-net-core-console-application-using-visual-studio-for-mac"></a>Tutorial: Depuración de una aplicación de consola de .NET Core con Visual Studio para Mac

En este tutorial se presentan las herramientas de depuración que hay disponibles en Visual Studio para Mac.

## <a name="prerequisites"></a>Requisitos previos

- Este tutorial funciona con la aplicación de consola que se crea en [Creación de una aplicación de consola de .NET Core en Visual Studio para Mac](using-on-mac-vs.md).

## <a name="use-debug-build-configuration"></a>Uso de la configuración de compilación de depuración

*Depuración* y *Versión* son las configuraciones de compilación integradas de Visual Studio. Use la configuración de compilación Depuración para depurar y la configuración de compilación Versión para la distribución final de la versión.

En la configuración de depuración, el programa se compila sin optimizar y con toda la información de depuración simbólica. La optimización complica la depuración, ya que la relación entre el código fuente y las instrucciones generadas es más compleja. La configuración de versión del programa no contiene información de depuración simbólica y está totalmente optimizada.

De forma predeterminada, Visual Studio usa la configuración de compilación Depuración, por lo que no es necesario cambiarla antes de depurar.

1. Inicie Visual Studio para Mac:

1. Abra el proyecto que creó en [Creación de una aplicación de consola de .NET Core en Visual Studio para Mac](using-on-mac-vs.md).

   La configuración de compilación actual se muestra en la barra de herramientas. En la siguiente imagen de la barra de herramientas se muestra que Visual Studio está configurado para compilar la versión de depuración de la aplicación:

   :::image type="content" source="media/debugging-with-visual-studio-mac/visual-studio-toolbar-debug.png" alt-text="Barra de herramientas de Visual Studio con Depuración resaltado":::

## <a name="set-a-breakpoint"></a>Establecer un punto de interrupción

Un *punto de interrupción* interrumpe temporalmente la ejecución de la aplicación antes de que se ejecute la línea con el punto de interrupción.

1. Establezca un punto de interrupción en la línea que muestra el nombre, la fecha y la hora. Para ello, coloque el cursor en la línea de código y presione <kbd>⌘</kbd><kbd>\\</kbd> (<kbd>command</kbd>+<kbd>\\</kbd>). Otra manera de establecer un punto de interrupción es seleccionar **Ejecutar** > **Alternar punto de interrupción** en el menú.

   Para indicar la línea en la que se establece el punto de interrupción, Visual Studio lo resalta y muestra un punto rojo en el margen izquierdo.

   :::image type="content" source="media/debugging-with-visual-studio-mac/set-breakpoint-in-editor.png" alt-text="Ventana del programa Visual Studio con el punto de interrupción establecido":::

1. Presione <kbd>⌘</kbd><kbd>↵</kbd> (<kbd>command</kbd>+<kbd>entrar</kbd>) para iniciar el programa en modo de depuración. Otra manera de iniciar la depuración es elegir **Ejecutar** > **Iniciar depuración** en el menú.

1. Cuando el sistema le pida un nombre, escriba una cadena en la ventana de terminar y luego presione <kbd>Entrar</kbd>.

1. La ejecución del programa se detiene cuando llega al punto de interrupción y antes de que se ejecute el método `Console.WriteLine`.

   :::image type="content" source="media/debugging-with-visual-studio-mac/breakpoint-hit.png" alt-text="Captura de pantalla de un punto de interrupción en Visual Studio":::

## <a name="use-the-immediate-window"></a>Uso de la ventana Inmediato

La ventana **Inmediato** le permite interactuar con la aplicación que está depurando. Puede cambiar el valor de las variables de forma interactiva para ver cómo afecta esto al programa.

1. Si la ventana **Inmediato** no está visible, muéstrela; para ello, elija **Ver** > **Paneles de depuración** > **Inmediato**.

1. Escriba `name = "Gracie"` en la ventana **Inmediato** y presione <kbd>Entrar</kbd>.

1. Escriba `date = date.AddDays(1)` en la ventana **Inmediato** y presione <kbd>Entrar</kbd>.

   La ventana **Inmediato** muestra el nuevo valor de la variable de cadena y las propiedades del valor <xref:System.DateTime>.

   :::image type="content" source="media/debugging-with-visual-studio-mac/immediate-window.png" alt-text="Ventana Inmediato en Visual Studio":::

   La ventana **Variables locales** muestra los valores de las variables definidas en el método que se ejecuta actualmente. Los valores de las variables que acaba de cambiar se actualizan en la ventana **Variables locales**.

   :::image type="content" source="media/debugging-with-visual-studio-mac/locals-window.png" alt-text="Ventana Variables locales de Visual Studio":::

1. Presione <kbd>⌘</kbd><kbd>↵</kbd> (<kbd>command</kbd>+<kbd>entrar</kbd>) para continuar con la depuración.

   Los valores mostrados en el terminar corresponden a los cambios realizados en la ventana **Inmediato**.

   Si no ve el terminal, seleccione **Terminal - HelloWorld** en la barra de navegación inferior.

   :::image type="content" source="media/debugging-with-visual-studio-mac/terminal-hello-world.png" alt-text="Terminal - HelloWorld en la barra de navegación inferior":::

1. Presione cualquier tecla para salir de la aplicación.

1. Cierre ventana de terminal.

## <a name="set-a-conditional-breakpoint"></a>Establecimiento de un punto de interrupción condicional

El programa muestra la cadena que escribe el usuario. ¿Qué sucede si el usuario no escribe nada? Puede probarlo con una característica de depuración muy útil denominada *Punto de interrupción condicional*.

1. Haga clic pulsando <kbd>control</kbd> en el punto rojo que representa al punto de interrupción. En el menú contextual, seleccione **Editar punto de interrupción**.

1. En el cuadro de diálogo **Editar punto de interrupción**, escriba el código siguiente en el campo **Y se cumpla la siguiente condición** y seleccione **Aplicar**.

   ```csharp
   String.IsNullOrEmpty(name)
   ```

   :::image type="content" source="media/debugging-with-visual-studio-mac/breakpoint-settings.png" alt-text="Editor con el panel de configuración de punto de interrupción":::

   Cada vez que se alcanza el punto de interrupción, el depurador llama al método `String.IsNullOrEmpty(name)` y se interrumpe en esta línea solo si la llamada al método devuelve `true`.

   En lugar de una expresión condicional, puede especificar un *número de llamadas*, que interrumpe la ejecución del programa antes de que una instrucción se ejecute un número especificado de veces.

1. Presione <kbd>⌘</kbd><kbd>↵</kbd> (<kbd>command</kbd>+<kbd>entrar</kbd>) para iniciar la depuración.

1. En la ventana de terminal, presione <kbd>entrar</kbd> cuando se le pida que escriba su nombre.

   Como se ha cumplido la condición que especificó (`name` es `null` o <xref:System.String.Empty?displayProperty=nameWithType>), la ejecución del programa se detiene cuando se alcanza el punto de interrupción.

1. Seleccione la ventana **Variables locales**, que muestra los valores de las variables que son locales para el método que se ejecuta actualmente. En este caso, `Main` es el método que se está ejecutando actualmente. Observe que el valor de la variable `name` es `""`; esto es, <xref:System.String.Empty?displayProperty=nameWithType>.

1. También puede ver que el valor es una cadena vacía escribiendo el nombre de la variable `name` en la ventana **Inmediato** y presionando <kbd>entrar</kbd>.

   :::image type="content" source="media/debugging-with-visual-studio-mac/immediate-window-output.png" alt-text="La ventana Inmediato que muestra el nombre es una cadena vacía":::

1. Presione <kbd>⌘</kbd><kbd>↵</kbd> (<kbd>command</kbd>+<kbd>entrar</kbd>) para continuar con la depuración.

1. En la ventana de terminal, presione cualquier tecla para salir del programa.

1. Cierre la ventana de terminal.

1. Para borrar el punto de interrupción, haga clic en el punto rojo en el margen izquierdo de la ventana de código. Otra manera de hacerlo es elegir **Ejecutar > Alternar punto de interrupción** con la línea de código seleccionada.

## <a name="step-through-a-program"></a>Ejecución paso a paso de un programa

Visual Studio también le permite recorrer línea a línea un programa y supervisar su ejecución. Normalmente, establecería un punto de interrupción y seguiría el flujo del programa mediante una pequeña parte de su código de programa. Como este programa es pequeño, puede ejecutar paso a paso el programa entero.

1. Establezca un punto de interrupción en la llave que marca el inicio del método `Main` (presione <kbd>command</kbd>+<kbd>\\</kbd>).

1. Presione <kbd>⌘</kbd><kbd>↵</kbd> (<kbd>command</kbd>+<kbd>entrar</kbd>) para iniciar la depuración.

   Visual Studio se detiene en la línea con el punto de interrupción.

1. Presione <kbd>⇧</kbd><kbd>⌘</kbd><kbd>I</kbd> (<kbd>mayús</kbd>+<kbd>command</kbd>+<kbd>l</kbd>) o seleccione **Ejecutar** > **Depurar paso a paso por instrucciones** para avanzar una línea.

   Visual Studio resalta y muestra una flecha junto a la siguiente línea de ejecución.

   :::image type="content" source="media/debugging-with-visual-studio-mac/step-into-method.png" alt-text="Método depurar paso a paso por instrucciones de Visual Studio":::

   En este punto, la ventana **Variables locales** muestra que la matriz `args` está vacía, y `name` y `date` tienen valores predeterminados. Además, Visual Studio ha abierto una ventana de consola en blanco.

1. Presione <kbd>⇧</kbd><kbd>⌘</kbd><kbd>I</kbd> (<kbd>mayús</kbd>+<kbd>command</kbd>+<kbd>I</kbd>).

   Visual Studio resalta la instrucción que incluye la asignación de variables `name`. La ventana **Variables locales** muestra que `name` es `null`, y terminal muestra la cadena "What is your name?" (¿Cómo te llamas?).

1. Para responder a la solicitud, escriba una cadena en la ventana de consola y presione <kbd>entrar</kbd>.

1. Presione <kbd>⇧</kbd><kbd>⌘</kbd><kbd>I</kbd> (<kbd>mayús</kbd>+<kbd>command</kbd>+<kbd>I</kbd>).

   Visual Studio resalta la instrucción que incluye la asignación de variables `date`. La ventana **Variables locales** muestra el valor devuelto por la llamada al método <xref:System.Console.ReadLine%2A?displayProperty=nameWithType>. En el terminal se muestra la cadena que escribió en el símbolo del sistema.

1. Presione <kbd>⇧</kbd><kbd>⌘</kbd><kbd>I</kbd> (<kbd>mayús</kbd>+<kbd>command</kbd>+<kbd>I</kbd>).

   La ventana **Variables locales** muestra el valor de la variable `date` tras la asignación desde la propiedad <xref:System.DateTime.Now?displayProperty=nameWithType>. El terminal no se modifica.

1. Presione <kbd>⇧</kbd><kbd>⌘</kbd><kbd>I</kbd> (<kbd>mayús</kbd>+<kbd>command</kbd>+<kbd>I</kbd>).

   Visual Studio llama al método <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType>. El terminal muestra la cadena con formato.

1. Presione <kbd>⇧</kbd><kbd>⌘</kbd><kbd>U</kbd> (<kbd>mayús</kbd>+<kbd>command</kbd>+<kbd>U</kbd>) o seleccione **Ejecutar** > **Paso a paso para salir**.

   El terminal muestra un mensaje y espera a que presione una tecla.

1. Presione cualquier tecla para salir de la aplicación.

## <a name="use-release-build-configuration"></a>Uso de la configuración de compilación de versión

Una vez que ha probado la versión de depuración de la aplicación, también debe compilar y probar la versión de lanzamiento. La versión de lanzamiento incorpora optimizaciones del compilador que afectan negativamente al comportamiento de una aplicación. Por ejemplo, las optimizaciones del compilador que están diseñadas para mejorar el rendimiento pueden crear condiciones de carrera en aplicaciones multiproceso.

Para compilar y probar la configuración de versión de la aplicación de consola, realice los pasos siguientes:

1. Cambie la configuración de compilación en la barra de herramientas de **Depurar** a **Versión**.

   :::image type="content" source="media/debugging-with-visual-studio-mac/visual-studio-toolbar-release.png" alt-text="Barra de herramientas predeterminada de Visual Studio con Depuración resaltado":::

1. Presione <kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>opción</kbd>+<kbd>command</kbd>+<kbd>entrar</kbd>) para ejecutar sin depurar.

## <a name="next-steps"></a>Pasos siguientes

En este tutorial, ha usado las herramientas de depuración de Visual Studio. En el siguiente tutorial, publicará una versión de la aplicación que se puede implementar.

> [!div class="nextstepaction"]
> [Publicación de una aplicación de consola de .NET Core con Visual Studio para Mac](publishing-with-visual-studio-mac.md)
