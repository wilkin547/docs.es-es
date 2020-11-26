---
title: Depuración de una aplicación de consola de .NET con Visual Studio
description: Aprenda a depurar una aplicación de consola de .NET con Visual Studio.
ms.date: 06/08/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 8a914dc6cf069c011ea5b077ada514bf8cec331d
ms.sourcegitcommit: 5114e7847e0ff8ddb8c266802d47af78567949cf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/19/2020
ms.locfileid: "94916199"
---
# <a name="tutorial-debug-a-net-console-application-using-visual-studio"></a>Tutorial: Depuración de una aplicación de consola de .NET con Visual Studio

En este tutorial se presentan las herramientas de depuración que hay disponibles en Visual Studio.

## <a name="prerequisites"></a>Requisitos previos

- Este tutorial funciona con la aplicación de consola que se crea en [Creación de una aplicación de consola de .NET con Visual Studio](with-visual-studio.md).

## <a name="use-debug-build-configuration"></a>Uso de la configuración de compilación de depuración

*Depuración* y *Versión* son las configuraciones de compilación integradas de Visual Studio. Use la configuración de compilación Depuración para depurar y la configuración de compilación Versión para la distribución final de la versión.

En la configuración de depuración, el programa se compila sin optimizar y con toda la información de depuración simbólica. La optimización complica la depuración, ya que la relación entre el código fuente y las instrucciones generadas es más compleja. La configuración de versión del programa no contiene información de depuración simbólica y está totalmente optimizada.

 De forma predeterminada, Visual Studio usa la configuración de compilación Depuración, por lo que no es necesario cambiarla antes de depurar.

1. Inicie Visual Studio.

1. Abra el proyecto que ha creado en [Creación de una aplicación de consola de .NET con Visual Studio](with-visual-studio.md).

   La configuración de compilación actual se muestra en la barra de herramientas. En la siguiente imagen de la barra de herramientas se muestra que Visual Studio está configurado para compilar la versión de depuración de la aplicación:

   :::image type="content" source="./media/debugging-with-visual-studio/visual-studio-toolbar-debug.png" alt-text="Barra de herramientas de Visual Studio con Depuración resaltado":::

## <a name="set-a-breakpoint"></a>Establecer un punto de interrupción

Un *punto de interrupción* interrumpe temporalmente la ejecución de la aplicación antes de que se ejecute la línea con el punto de interrupción.

1. Establezca un *punto de interrupción* en la línea que muestre el nombre, la fecha y la hora; para ello, haga clic en el margen izquierdo de la ventana de código de esa línea. El margen izquierdo está a la izquierda de los números de línea.  Otras maneras de establecer un punto de interrupción consisten en colocar el cursor en la línea de código y, después, presionar <kbd>F9</kbd> o seleccionar **Depurar** > **Alternar punto de interrupción** en la barra de menú.

   En esta imagen vemos que, para indicar la línea en la que se establece el punto de interrupción, Visual Studio lo resalta y muestra un punto rojo en el margen izquierdo.

   :::image type="content" source="./media/debugging-with-visual-studio/set-breakpoint-in-editor.png" alt-text="Ventana del programa Visual Studio con el punto de interrupción establecido":::

1. Presione <kbd>F5</kbd> para ejecutar el programa en modo de depuración. Otra manera de iniciar la depuración es elegir **Depuración** > **Iniciar depuración** en el menú.

1. Cuando el sistema le pida un nombre, escriba una cadena en la ventana de consola y luego presione <kbd>Entrar</kbd>.

1. La ejecución del programa se detiene cuando llega al punto de interrupción y antes de que se ejecute el método `Console.WriteLine`. La ventana **Variables locales** muestra los valores de las variables definidas en el método que se ejecuta actualmente.

   :::image type="content" source="./media/debugging-with-visual-studio/breakpoint-hit.png" alt-text="Captura de pantalla de un punto de interrupción en Visual Studio":::

## <a name="use-the-immediate-window"></a>Uso de la ventana Inmediato

La ventana **Inmediato** le permite interactuar con la aplicación que está depurando. Puede cambiar el valor de las variables de forma interactiva para ver cómo afecta esto al programa.

1. Si la ventana **Inmediato** no está visible, muéstrela; para ello, elija **Depurar** > **Ventanas** > **Inmediato**.

1. Escriba `name = "Gracie"` en la ventana **Inmediato** y presione la tecla <kbd>Entrar</kbd>.

1. Escriba `date = DateTime.Parse("2019-11-16T17:25:00Z").ToUniversalTime()` en la ventana **Inmediato** y presione la tecla <kbd>Entrar</kbd>.

   La ventana **Inmediato** muestra el valor de la variable de cadena y las propiedades del valor <xref:System.DateTime>. Además, los valores de las variables se actualizan en la ventana **Variables locales**.

   :::image type="content" source="./media/debugging-with-visual-studio/locals-immediate-window.png" alt-text="Ventanas Variables locales e Inmediato en Visual Studio 2019":::

1. Presione <kbd>F5</kbd> para que continúe la ejecución del programa. Otra manera de hacerlo es elegir **Depuración** > **Continuar** en el menú.

   Los valores mostrados en la ventana de la consola corresponden a los cambios realizados en la ventana **Inmediato**.

   :::image type="content" source="./media/debugging-with-visual-studio/console-window.png" alt-text="Ventana de consola que muestra los valores especificados":::

1. Presione cualquier tecla para salir de la aplicación y detenga la depuración.

## <a name="set-a-conditional-breakpoint"></a>Establecimiento de un punto de interrupción condicional

El programa muestra la cadena que escribe el usuario. ¿Qué sucede si el usuario no escribe nada? Puede probarlo con una característica de depuración muy útil denominada *Punto de interrupción condicional*.

1. Haga clic con el botón derecho en el punto rojo que representa al punto de interrupción. En el menú contextual, seleccione **Condiciones** para abrir el cuadro de diálogo **Configuración del punto de interrupción**. Active la casilla **Condiciones** si aún no está seleccionada.

   :::image type="content" source="./media/debugging-with-visual-studio/breakpoint-settings.png" alt-text="Editor con el panel de configuración de puntos de interrupción: C#":::

1. En **Expresión condicional**, escriba el código siguiente en el campo que muestra el código de ejemplo que comprueba si `x` es 5. Si no se muestra el idioma que quiere usar, cambie el selector de idioma en la parte superior de la página.

   ```csharp
   String.IsNullOrEmpty(name)
   ```

   ```vb
   String.IsNullOrEmpty(name)
   ```

   Cada vez que se alcanza el punto de interrupción, el depurador llama al método `String.IsNullOrEmpty(name)` y se interrumpe en esta línea solo si la llamada al método devuelve `true`.

   En lugar de una expresión condicional, puede especificar un *número de llamadas*, que interrumpe la ejecución del programa antes de que se ejecute una instrucción un número de veces especificado. Otra opción consiste en especificar una *condición de filtro*, que interrumpe la ejecución del programa en función de atributos tales como un identificador de subproceso, un nombre de proceso o un nombre de subproceso.

1. Seleccione **Cerrar** para cerrar el cuadro de diálogo.

1. Inicie el programa con la depuración presionando <kbd>F5</kbd>.

1. En la ventana de consola, cuando se le pida que escriba su nombre, presione la tecla <kbd>Entrar</kbd>.

1. Como se ha cumplido la condición que especificó (`name` es `null` o <xref:System.String.Empty?displayProperty=nameWithType>), la ejecución del programa se detiene cuando se alcanza el punto de interrupción y antes de que se ejecute el método `Console.WriteLine`.

1. Seleccione la ventana **Variables locales**, que muestra los valores de las variables que son locales para el método que se ejecuta actualmente. En este caso, `Main` es el método que se está ejecutando actualmente. Observe que el valor de la variable `name` es `""` o <xref:System.String.Empty?displayProperty=nameWithType>.

1. Confirme que el valor es una cadena vacía escribiendo la siguiente instrucción en la ventana **Inmediato** y presionando <kbd>Entrar</kbd>. El resultado es `true`.

   ```csharp
   ? name == String.Empty
   ```

   ```vb
   ? String.IsNullOrEmpty(name)
   ```

   El signo de interrogación dirige la ventana Inmediato para [evaluar una expresión](/visualstudio/ide/reference/immediate-window#enter-commands).

   :::image type="content" source="./media/debugging-with-visual-studio/immediate-window-output.png" alt-text="Ventana Inmediato en la que se devuelve un valor de True después de que se ejecute la instrucción: C#":::

1. Presione <kbd>F5</kbd> para que continúe la ejecución del programa.

1. Presione cualquier tecla para cerrar la ventana de consola y detener la depuración.

1. Para borrar el punto de interrupción, haga clic en el punto en el margen izquierdo de la ventana de código. Otras formas de borrar un punto de interrupción consisten en presionar <kbd>F9</kbd> o elegir **Depurar > Alternar punto de interrupción** mientras se selecciona la línea de código.

## <a name="step-through-a-program"></a>Ejecución paso a paso de un programa

Visual Studio también le permite recorrer línea a línea un programa y supervisar su ejecución. Normalmente, establecería un punto de interrupción y seguiría el flujo del programa mediante una pequeña parte de su código de programa. Como este programa es pequeño, puede ejecutar paso a paso el programa entero.

1. Elija **Depurar** > **Depurar paso a paso por instrucciones**. Otra manera de depurar una instrucción cada vez es presionar <kbd>F11</kbd>.

   Visual Studio resalta y muestra una flecha junto a la siguiente línea de ejecución.

   C#

   :::image type="content" source="./media/debugging-with-visual-studio/step-into-method.png" alt-text="Método Paso a paso por instrucciones de Visual Studio: C#":::

   Visual Basic

   :::image type="content" source="./media/debugging-with-visual-studio/vb-step-into-method.png" alt-text="Método Paso a paso por instrucciones de Visual Studio: Visual Basic":::

   En este punto, la ventana **Variables locales** muestra que la matriz `args` está vacía, y `name` y `date` tienen valores predeterminados. Además, Visual Studio ha abierto una ventana de consola en blanco.

1. Presione <kbd>F11</kbd>. Visual Studio ahora resalta la siguiente línea de ejecución. La ventana **Variables locales** no cambia y la ventana de consola permanece en blanco.

   C#

   :::image type="content" source="./media/debugging-with-visual-studio/step-into-source-method.png" alt-text="Origen del método Paso a paso por instrucciones de Visual Studio: C#":::

   Visual Basic

   :::image type="content" source="./media/debugging-with-visual-studio/vb-step-into-source-method.png" alt-text="Origen del método Paso a paso por instrucciones de Visual Studio: Visual Basic":::

1. Presione <kbd>F11</kbd>. Visual Studio resalta la instrucción que incluye la asignación de variables `name`. La ventana **Variables locales** muestra que `name` es `null`, y la ventana de consola muestra la cadena "What is your name?".

1. Para responder a la solicitud, escriba una cadena en la ventana de consola y presione <kbd>Entrar</kbd>. La consola no responde y la cadena que especificó no se muestra en la ventana de la consola, pero el método <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> capturará en cambio la entrada.

1. Presione <kbd>F11</kbd>. Visual Studio resalta la instrucción que incluye la asignación de la variable `date` (`currentDate` en Visual Basic). La ventana **Variables locales** muestra el valor devuelto por la llamada al método <xref:System.Console.ReadLine%2A?displayProperty=nameWithType>. La ventana de la consola también muestra la cadena que escribió en la solicitud.

1. Presione <kbd>F11</kbd>. La ventana **Variables locales** muestra el valor de la variable `date` tras la asignación desde la propiedad <xref:System.DateTime.Now?displayProperty=nameWithType>. La ventana de consola permanece sin cambios.

1. Presione <kbd>F11</kbd>. Visual Studio llama al método <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType>. La ventana de la consola muestra la cadena con formato.

1. Elija **Depurar** > **Depurar paso a paso para salir**. Otra manera de detener la ejecución paso a paso es presionar <kbd>Mayús</kbd>+<kbd>F11</kbd>.

   La ventana de la consola muestra un mensaje y espera a que presione una tecla.

1. Presione cualquier tecla para cerrar la ventana de consola y detener la depuración.

## <a name="use-release-build-configuration"></a>Uso de la configuración de compilación de versión

Una vez que ha probado la versión de depuración de la aplicación, también debe compilar y probar la versión de lanzamiento. La versión de lanzamiento incorpora optimizaciones del compilador que en ocasiones afectan negativamente al comportamiento de una aplicación. Por ejemplo, las optimizaciones del compilador que están diseñadas para mejorar el rendimiento pueden crear condiciones de carrera en aplicaciones multiproceso.

Para compilar y probar la versión de lanzamiento de la aplicación de la consola, cambie la configuración de compilación en la barra de herramientas de **Depurar** a **Versión**.

:::image type="content" source="./media/debugging-with-visual-studio/visual-studio-toolbar-release.png" alt-text="Barra de herramientas predeterminada de Visual Studio con Versión resaltado":::

Cuando presiona <kbd>F5</kbd> o elije **Compilar solución** en el menú **Compilar**, Visual Studio compila la versión de lanzamiento de la aplicación. Puede probarla como hizo con la versión de depuración.

## <a name="next-steps"></a>Pasos siguientes

En este tutorial, ha usado las herramientas de depuración de Visual Studio. En el siguiente tutorial, publicará una versión de la aplicación que se puede implementar.

> [!div class="nextstepaction"]
> [Publicación de una aplicación de consola de .NET con Visual Studio](publishing-with-visual-studio.md)
