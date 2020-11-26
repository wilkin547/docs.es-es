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
# <a name="tutorial-debug-a-net-console-application-using-visual-studio"></a><span data-ttu-id="792ab-103">Tutorial: Depuración de una aplicación de consola de .NET con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="792ab-103">Tutorial: Debug a .NET console application using Visual Studio</span></span>

<span data-ttu-id="792ab-104">En este tutorial se presentan las herramientas de depuración que hay disponibles en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="792ab-104">This tutorial introduces the debugging tools available in Visual Studio.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="792ab-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="792ab-105">Prerequisites</span></span>

- <span data-ttu-id="792ab-106">Este tutorial funciona con la aplicación de consola que se crea en [Creación de una aplicación de consola de .NET con Visual Studio](with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="792ab-106">This tutorial works with the console app that you create in [Create a .NET console application using Visual Studio](with-visual-studio.md).</span></span>

## <a name="use-debug-build-configuration"></a><span data-ttu-id="792ab-107">Uso de la configuración de compilación de depuración</span><span class="sxs-lookup"><span data-stu-id="792ab-107">Use Debug build configuration</span></span>

<span data-ttu-id="792ab-108">*Depuración* y *Versión* son las configuraciones de compilación integradas de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="792ab-108">*Debug* and *Release* are Visual Studio's built-in build configurations.</span></span> <span data-ttu-id="792ab-109">Use la configuración de compilación Depuración para depurar y la configuración de compilación Versión para la distribución final de la versión.</span><span class="sxs-lookup"><span data-stu-id="792ab-109">You use the Debug build configuration for debugging and the Release configuration for the final release distribution.</span></span>

<span data-ttu-id="792ab-110">En la configuración de depuración, el programa se compila sin optimizar y con toda la información de depuración simbólica.</span><span class="sxs-lookup"><span data-stu-id="792ab-110">In the Debug configuration, a program compiles with full symbolic debug information and no optimization.</span></span> <span data-ttu-id="792ab-111">La optimización complica la depuración, ya que la relación entre el código fuente y las instrucciones generadas es más compleja.</span><span class="sxs-lookup"><span data-stu-id="792ab-111">Optimization complicates debugging, because the relationship between source code and generated instructions is more complex.</span></span> <span data-ttu-id="792ab-112">La configuración de versión del programa no contiene información de depuración simbólica y está totalmente optimizada.</span><span class="sxs-lookup"><span data-stu-id="792ab-112">The release configuration of a program has no symbolic debug information and is fully optimized.</span></span>

 <span data-ttu-id="792ab-113">De forma predeterminada, Visual Studio usa la configuración de compilación Depuración, por lo que no es necesario cambiarla antes de depurar.</span><span class="sxs-lookup"><span data-stu-id="792ab-113">By default, Visual Studio uses the Debug build configuration, so you don't need to change it before debugging.</span></span>

1. <span data-ttu-id="792ab-114">Inicie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="792ab-114">Start Visual Studio.</span></span>

1. <span data-ttu-id="792ab-115">Abra el proyecto que ha creado en [Creación de una aplicación de consola de .NET con Visual Studio](with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="792ab-115">Open the project that you created in [Create a .NET console application using Visual Studio](with-visual-studio.md).</span></span>

   <span data-ttu-id="792ab-116">La configuración de compilación actual se muestra en la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="792ab-116">The current build configuration is shown on the toolbar.</span></span> <span data-ttu-id="792ab-117">En la siguiente imagen de la barra de herramientas se muestra que Visual Studio está configurado para compilar la versión de depuración de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="792ab-117">The following toolbar image shows that Visual Studio is configured to compile the Debug version of the app:</span></span>

   :::image type="content" source="./media/debugging-with-visual-studio/visual-studio-toolbar-debug.png" alt-text="Barra de herramientas de Visual Studio con Depuración resaltado":::

## <a name="set-a-breakpoint"></a><span data-ttu-id="792ab-119">Establecer un punto de interrupción</span><span class="sxs-lookup"><span data-stu-id="792ab-119">Set a breakpoint</span></span>

<span data-ttu-id="792ab-120">Un *punto de interrupción* interrumpe temporalmente la ejecución de la aplicación antes de que se ejecute la línea con el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="792ab-120">A *breakpoint* temporarily interrupts the execution of the application before the line with the breakpoint is executed.</span></span>

1. <span data-ttu-id="792ab-121">Establezca un *punto de interrupción* en la línea que muestre el nombre, la fecha y la hora; para ello, haga clic en el margen izquierdo de la ventana de código de esa línea.</span><span class="sxs-lookup"><span data-stu-id="792ab-121">Set a *breakpoint* on the line that displays the name, date, and time, by clicking in the left margin of the code window on that line.</span></span> <span data-ttu-id="792ab-122">El margen izquierdo está a la izquierda de los números de línea.</span><span class="sxs-lookup"><span data-stu-id="792ab-122">The left margin is to the left of the line numbers.</span></span>  <span data-ttu-id="792ab-123">Otras maneras de establecer un punto de interrupción consisten en colocar el cursor en la línea de código y, después, presionar <kbd>F9</kbd> o seleccionar **Depurar** > **Alternar punto de interrupción** en la barra de menú.</span><span class="sxs-lookup"><span data-stu-id="792ab-123">Other ways to set a breakpoint are by placing the cursor in the line of code and then pressing <kbd>F9</kbd> or choosing **Debug** > **Toggle Breakpoint** from the menu bar.</span></span>

   <span data-ttu-id="792ab-124">En esta imagen vemos que, para indicar la línea en la que se establece el punto de interrupción, Visual Studio lo resalta y muestra un punto rojo en el margen izquierdo.</span><span class="sxs-lookup"><span data-stu-id="792ab-124">As the following image shows, Visual Studio indicates the line on which the breakpoint is set by highlighting it and displaying a red dot in the left margin.</span></span>

   :::image type="content" source="./media/debugging-with-visual-studio/set-breakpoint-in-editor.png" alt-text="Ventana del programa Visual Studio con el punto de interrupción establecido":::

1. <span data-ttu-id="792ab-126">Presione <kbd>F5</kbd> para ejecutar el programa en modo de depuración.</span><span class="sxs-lookup"><span data-stu-id="792ab-126">Press <kbd>F5</kbd> to run the program in Debug mode.</span></span> <span data-ttu-id="792ab-127">Otra manera de iniciar la depuración es elegir **Depuración** > **Iniciar depuración** en el menú.</span><span class="sxs-lookup"><span data-stu-id="792ab-127">Another way to start debugging is by choosing **Debug** > **Start Debugging** from the menu.</span></span>

1. <span data-ttu-id="792ab-128">Cuando el sistema le pida un nombre, escriba una cadena en la ventana de consola y luego presione <kbd>Entrar</kbd>.</span><span class="sxs-lookup"><span data-stu-id="792ab-128">Enter a string in the console window when the program prompts for a name, and then press <kbd>Enter</kbd>.</span></span>

1. <span data-ttu-id="792ab-129">La ejecución del programa se detiene cuando llega al punto de interrupción y antes de que se ejecute el método `Console.WriteLine`.</span><span class="sxs-lookup"><span data-stu-id="792ab-129">Program execution stops when it reaches the breakpoint and before the `Console.WriteLine` method executes.</span></span> <span data-ttu-id="792ab-130">La ventana **Variables locales** muestra los valores de las variables definidas en el método que se ejecuta actualmente.</span><span class="sxs-lookup"><span data-stu-id="792ab-130">The **Locals** window displays the values of variables that are defined in the currently executing method.</span></span>

   :::image type="content" source="./media/debugging-with-visual-studio/breakpoint-hit.png" alt-text="Captura de pantalla de un punto de interrupción en Visual Studio":::

## <a name="use-the-immediate-window"></a><span data-ttu-id="792ab-132">Uso de la ventana Inmediato</span><span class="sxs-lookup"><span data-stu-id="792ab-132">Use the Immediate window</span></span>

<span data-ttu-id="792ab-133">La ventana **Inmediato** le permite interactuar con la aplicación que está depurando.</span><span class="sxs-lookup"><span data-stu-id="792ab-133">The **Immediate** window lets you interact with the application you're debugging.</span></span> <span data-ttu-id="792ab-134">Puede cambiar el valor de las variables de forma interactiva para ver cómo afecta esto al programa.</span><span class="sxs-lookup"><span data-stu-id="792ab-134">You can interactively change the value of variables to see how it affects your program.</span></span>

1. <span data-ttu-id="792ab-135">Si la ventana **Inmediato** no está visible, muéstrela; para ello, elija **Depurar** > **Ventanas** > **Inmediato**.</span><span class="sxs-lookup"><span data-stu-id="792ab-135">If the **Immediate** window is not visible, display it by choosing **Debug** > **Windows** > **Immediate**.</span></span>

1. <span data-ttu-id="792ab-136">Escriba `name = "Gracie"` en la ventana **Inmediato** y presione la tecla <kbd>Entrar</kbd>.</span><span class="sxs-lookup"><span data-stu-id="792ab-136">Enter `name = "Gracie"` in the **Immediate** window and press the <kbd>Enter</kbd> key.</span></span>

1. <span data-ttu-id="792ab-137">Escriba `date = DateTime.Parse("2019-11-16T17:25:00Z").ToUniversalTime()` en la ventana **Inmediato** y presione la tecla <kbd>Entrar</kbd>.</span><span class="sxs-lookup"><span data-stu-id="792ab-137">Enter `date = DateTime.Parse("2019-11-16T17:25:00Z").ToUniversalTime()` in the **Immediate** window and press the <kbd>Enter</kbd> key.</span></span>

   <span data-ttu-id="792ab-138">La ventana **Inmediato** muestra el valor de la variable de cadena y las propiedades del valor <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="792ab-138">The **Immediate** window displays the value of the string variable and the properties of the <xref:System.DateTime> value.</span></span> <span data-ttu-id="792ab-139">Además, los valores de las variables se actualizan en la ventana **Variables locales**.</span><span class="sxs-lookup"><span data-stu-id="792ab-139">In addition, the values of the variables are updated in the **Locals** window.</span></span>

   :::image type="content" source="./media/debugging-with-visual-studio/locals-immediate-window.png" alt-text="Ventanas Variables locales e Inmediato en Visual Studio 2019":::

1. <span data-ttu-id="792ab-141">Presione <kbd>F5</kbd> para que continúe la ejecución del programa.</span><span class="sxs-lookup"><span data-stu-id="792ab-141">Press <kbd>F5</kbd> to continue program execution.</span></span> <span data-ttu-id="792ab-142">Otra manera de hacerlo es elegir **Depuración** > **Continuar** en el menú.</span><span class="sxs-lookup"><span data-stu-id="792ab-142">Another way to continue is by choosing **Debug** > **Continue** from the menu.</span></span>

   <span data-ttu-id="792ab-143">Los valores mostrados en la ventana de la consola corresponden a los cambios realizados en la ventana **Inmediato**.</span><span class="sxs-lookup"><span data-stu-id="792ab-143">The values displayed in the console window correspond to the changes you made in the **Immediate** window.</span></span>

   :::image type="content" source="./media/debugging-with-visual-studio/console-window.png" alt-text="Ventana de consola que muestra los valores especificados":::

1. <span data-ttu-id="792ab-145">Presione cualquier tecla para salir de la aplicación y detenga la depuración.</span><span class="sxs-lookup"><span data-stu-id="792ab-145">Press any key to exit the application and stop debugging.</span></span>

## <a name="set-a-conditional-breakpoint"></a><span data-ttu-id="792ab-146">Establecimiento de un punto de interrupción condicional</span><span class="sxs-lookup"><span data-stu-id="792ab-146">Set a conditional breakpoint</span></span>

<span data-ttu-id="792ab-147">El programa muestra la cadena que escribe el usuario.</span><span class="sxs-lookup"><span data-stu-id="792ab-147">The program displays the string that the user enters.</span></span> <span data-ttu-id="792ab-148">¿Qué sucede si el usuario no escribe nada?</span><span class="sxs-lookup"><span data-stu-id="792ab-148">What happens if the user doesn't enter anything?</span></span> <span data-ttu-id="792ab-149">Puede probarlo con una característica de depuración muy útil denominada *Punto de interrupción condicional*.</span><span class="sxs-lookup"><span data-stu-id="792ab-149">You can test this with a useful debugging feature called a *conditional breakpoint*.</span></span>

1. <span data-ttu-id="792ab-150">Haga clic con el botón derecho en el punto rojo que representa al punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="792ab-150">Right-click on the red dot that represents the breakpoint.</span></span> <span data-ttu-id="792ab-151">En el menú contextual, seleccione **Condiciones** para abrir el cuadro de diálogo **Configuración del punto de interrupción**.</span><span class="sxs-lookup"><span data-stu-id="792ab-151">In the context menu, select **Conditions** to open the **Breakpoint Settings** dialog.</span></span> <span data-ttu-id="792ab-152">Active la casilla **Condiciones** si aún no está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="792ab-152">Select the box for **Conditions** if it's not already selected.</span></span>

   :::image type="content" source="./media/debugging-with-visual-studio/breakpoint-settings.png" alt-text="Editor con el panel de configuración de puntos de interrupción: C#":::

1. <span data-ttu-id="792ab-154">En **Expresión condicional**, escriba el código siguiente en el campo que muestra el código de ejemplo que comprueba si `x` es 5.</span><span class="sxs-lookup"><span data-stu-id="792ab-154">For the **Conditional Expression**, enter the following code in the field that shows example code that tests if `x` is 5.</span></span> <span data-ttu-id="792ab-155">Si no se muestra el idioma que quiere usar, cambie el selector de idioma en la parte superior de la página.</span><span class="sxs-lookup"><span data-stu-id="792ab-155">If the language you want to use is not shown, change the language selector at the top of the page.</span></span>

   ```csharp
   String.IsNullOrEmpty(name)
   ```

   ```vb
   String.IsNullOrEmpty(name)
   ```

   <span data-ttu-id="792ab-156">Cada vez que se alcanza el punto de interrupción, el depurador llama al método `String.IsNullOrEmpty(name)` y se interrumpe en esta línea solo si la llamada al método devuelve `true`.</span><span class="sxs-lookup"><span data-stu-id="792ab-156">Each time the breakpoint is hit, the debugger calls the `String.IsNullOrEmpty(name)` method, and it breaks on this line only if the method call returns `true`.</span></span>

   <span data-ttu-id="792ab-157">En lugar de una expresión condicional, puede especificar un *número de llamadas*, que interrumpe la ejecución del programa antes de que se ejecute una instrucción un número de veces especificado.</span><span class="sxs-lookup"><span data-stu-id="792ab-157">Instead of a conditional expression, you can specify a *hit count*, which interrupts program execution before a statement is executed a specified number of times.</span></span> <span data-ttu-id="792ab-158">Otra opción consiste en especificar una *condición de filtro*, que interrumpe la ejecución del programa en función de atributos tales como un identificador de subproceso, un nombre de proceso o un nombre de subproceso.</span><span class="sxs-lookup"><span data-stu-id="792ab-158">Another option is to specify a *filter condition*, which interrupts program execution based on such attributes as a thread identifier, process name, or thread name.</span></span>

1. <span data-ttu-id="792ab-159">Seleccione **Cerrar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="792ab-159">Select **Close** to close the dialog.</span></span>

1. <span data-ttu-id="792ab-160">Inicie el programa con la depuración presionando <kbd>F5</kbd>.</span><span class="sxs-lookup"><span data-stu-id="792ab-160">Start the program with debugging by pressing <kbd>F5</kbd>.</span></span>

1. <span data-ttu-id="792ab-161">En la ventana de consola, cuando se le pida que escriba su nombre, presione la tecla <kbd>Entrar</kbd>.</span><span class="sxs-lookup"><span data-stu-id="792ab-161">In the console window, press the <kbd>Enter</kbd> key when prompted to enter your name.</span></span>

1. <span data-ttu-id="792ab-162">Como se ha cumplido la condición que especificó (`name` es `null` o <xref:System.String.Empty?displayProperty=nameWithType>), la ejecución del programa se detiene cuando se alcanza el punto de interrupción y antes de que se ejecute el método `Console.WriteLine`.</span><span class="sxs-lookup"><span data-stu-id="792ab-162">Because the condition you specified (`name` is either `null` or <xref:System.String.Empty?displayProperty=nameWithType>) has been satisfied, program execution stops when it reaches the breakpoint and before the `Console.WriteLine` method executes.</span></span>

1. <span data-ttu-id="792ab-163">Seleccione la ventana **Variables locales**, que muestra los valores de las variables que son locales para el método que se ejecuta actualmente.</span><span class="sxs-lookup"><span data-stu-id="792ab-163">Select the **Locals** window, which shows the values of variables that are local to the currently executing method.</span></span> <span data-ttu-id="792ab-164">En este caso, `Main` es el método que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="792ab-164">In this case, `Main` is the currently executing method.</span></span> <span data-ttu-id="792ab-165">Observe que el valor de la variable `name` es `""` o <xref:System.String.Empty?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="792ab-165">Observe that the value of the `name` variable is `""`, or <xref:System.String.Empty?displayProperty=nameWithType>.</span></span>

1. <span data-ttu-id="792ab-166">Confirme que el valor es una cadena vacía escribiendo la siguiente instrucción en la ventana **Inmediato** y presionando <kbd>Entrar</kbd>.</span><span class="sxs-lookup"><span data-stu-id="792ab-166">Confirm the value is an empty string by entering the following statement in the **Immediate** window and pressing <kbd>Enter</kbd>.</span></span> <span data-ttu-id="792ab-167">El resultado es `true`.</span><span class="sxs-lookup"><span data-stu-id="792ab-167">The result is `true`.</span></span>

   ```csharp
   ? name == String.Empty
   ```

   ```vb
   ? String.IsNullOrEmpty(name)
   ```

   <span data-ttu-id="792ab-168">El signo de interrogación dirige la ventana Inmediato para [evaluar una expresión](/visualstudio/ide/reference/immediate-window#enter-commands).</span><span class="sxs-lookup"><span data-stu-id="792ab-168">The question mark directs the immediate window to [evaluate an expression](/visualstudio/ide/reference/immediate-window#enter-commands).</span></span>

   :::image type="content" source="./media/debugging-with-visual-studio/immediate-window-output.png" alt-text="Ventana Inmediato en la que se devuelve un valor de True después de que se ejecute la instrucción: C#":::

1. <span data-ttu-id="792ab-170">Presione <kbd>F5</kbd> para que continúe la ejecución del programa.</span><span class="sxs-lookup"><span data-stu-id="792ab-170">Press <kbd>F5</kbd> to continue program execution.</span></span>

1. <span data-ttu-id="792ab-171">Presione cualquier tecla para cerrar la ventana de consola y detener la depuración.</span><span class="sxs-lookup"><span data-stu-id="792ab-171">Press any key to close the console window and stop debugging.</span></span>

1. <span data-ttu-id="792ab-172">Para borrar el punto de interrupción, haga clic en el punto en el margen izquierdo de la ventana de código.</span><span class="sxs-lookup"><span data-stu-id="792ab-172">Clear the breakpoint by clicking on the dot in the left margin of the code window.</span></span> <span data-ttu-id="792ab-173">Otras formas de borrar un punto de interrupción consisten en presionar <kbd>F9</kbd> o elegir **Depurar > Alternar punto de interrupción** mientras se selecciona la línea de código.</span><span class="sxs-lookup"><span data-stu-id="792ab-173">Other ways to clear a breakpoint are by pressing <kbd>F9</kbd> or choosing **Debug > Toggle Breakpoint** while the line of code is selected.</span></span>

## <a name="step-through-a-program"></a><span data-ttu-id="792ab-174">Ejecución paso a paso de un programa</span><span class="sxs-lookup"><span data-stu-id="792ab-174">Step through a program</span></span>

<span data-ttu-id="792ab-175">Visual Studio también le permite recorrer línea a línea un programa y supervisar su ejecución.</span><span class="sxs-lookup"><span data-stu-id="792ab-175">Visual Studio also allows you to step line by line through a program and monitor its execution.</span></span> <span data-ttu-id="792ab-176">Normalmente, establecería un punto de interrupción y seguiría el flujo del programa mediante una pequeña parte de su código de programa.</span><span class="sxs-lookup"><span data-stu-id="792ab-176">Ordinarily, you'd set a breakpoint and follow program flow through a small part of your program code.</span></span> <span data-ttu-id="792ab-177">Como este programa es pequeño, puede ejecutar paso a paso el programa entero.</span><span class="sxs-lookup"><span data-stu-id="792ab-177">Since this program is small, you can step through the entire program.</span></span>

1. <span data-ttu-id="792ab-178">Elija **Depurar** > **Depurar paso a paso por instrucciones**.</span><span class="sxs-lookup"><span data-stu-id="792ab-178">Choose **Debug** > **Step Into**.</span></span> <span data-ttu-id="792ab-179">Otra manera de depurar una instrucción cada vez es presionar <kbd>F11</kbd>.</span><span class="sxs-lookup"><span data-stu-id="792ab-179">Another way to debug one statement at a time is by pressing <kbd>F11</kbd>.</span></span>

   <span data-ttu-id="792ab-180">Visual Studio resalta y muestra una flecha junto a la siguiente línea de ejecución.</span><span class="sxs-lookup"><span data-stu-id="792ab-180">Visual Studio highlights and displays an arrow beside the next line of execution.</span></span>

   <span data-ttu-id="792ab-181">C#</span><span class="sxs-lookup"><span data-stu-id="792ab-181">C#</span></span>

   :::image type="content" source="./media/debugging-with-visual-studio/step-into-method.png" alt-text="Método Paso a paso por instrucciones de Visual Studio: C#":::

   <span data-ttu-id="792ab-183">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="792ab-183">Visual Basic</span></span>

   :::image type="content" source="./media/debugging-with-visual-studio/vb-step-into-method.png" alt-text="Método Paso a paso por instrucciones de Visual Studio: Visual Basic":::

   <span data-ttu-id="792ab-185">En este punto, la ventana **Variables locales** muestra que la matriz `args` está vacía, y `name` y `date` tienen valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="792ab-185">At this point, the **Locals** window shows that the `args` array is empty, and `name` and `date` have default values.</span></span> <span data-ttu-id="792ab-186">Además, Visual Studio ha abierto una ventana de consola en blanco.</span><span class="sxs-lookup"><span data-stu-id="792ab-186">In addition, Visual Studio has opened a blank console window.</span></span>

1. <span data-ttu-id="792ab-187">Presione <kbd>F11</kbd>.</span><span class="sxs-lookup"><span data-stu-id="792ab-187">Press <kbd>F11</kbd>.</span></span> <span data-ttu-id="792ab-188">Visual Studio ahora resalta la siguiente línea de ejecución.</span><span class="sxs-lookup"><span data-stu-id="792ab-188">Visual Studio now highlights the next line of execution.</span></span> <span data-ttu-id="792ab-189">La ventana **Variables locales** no cambia y la ventana de consola permanece en blanco.</span><span class="sxs-lookup"><span data-stu-id="792ab-189">The **Locals** window is unchanged, and the console window remains blank.</span></span>

   <span data-ttu-id="792ab-190">C#</span><span class="sxs-lookup"><span data-stu-id="792ab-190">C#</span></span>

   :::image type="content" source="./media/debugging-with-visual-studio/step-into-source-method.png" alt-text="Origen del método Paso a paso por instrucciones de Visual Studio: C#":::

   <span data-ttu-id="792ab-192">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="792ab-192">Visual Basic</span></span>

   :::image type="content" source="./media/debugging-with-visual-studio/vb-step-into-source-method.png" alt-text="Origen del método Paso a paso por instrucciones de Visual Studio: Visual Basic":::

1. <span data-ttu-id="792ab-194">Presione <kbd>F11</kbd>.</span><span class="sxs-lookup"><span data-stu-id="792ab-194">Press <kbd>F11</kbd>.</span></span> <span data-ttu-id="792ab-195">Visual Studio resalta la instrucción que incluye la asignación de variables `name`.</span><span class="sxs-lookup"><span data-stu-id="792ab-195">Visual Studio highlights the statement that includes the `name` variable assignment.</span></span> <span data-ttu-id="792ab-196">La ventana **Variables locales** muestra que `name` es `null`, y la ventana de consola muestra la cadena "What is your name?".</span><span class="sxs-lookup"><span data-stu-id="792ab-196">The **Locals** window shows that `name` is `null`, and the console window displays the string "What is your name?".</span></span>

1. <span data-ttu-id="792ab-197">Para responder a la solicitud, escriba una cadena en la ventana de consola y presione <kbd>Entrar</kbd>.</span><span class="sxs-lookup"><span data-stu-id="792ab-197">Respond to the prompt by entering a string in the console window and pressing <kbd>Enter</kbd>.</span></span> <span data-ttu-id="792ab-198">La consola no responde y la cadena que especificó no se muestra en la ventana de la consola, pero el método <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> capturará en cambio la entrada.</span><span class="sxs-lookup"><span data-stu-id="792ab-198">The console is unresponsive, and the string you entered isn't displayed in the console window, but the <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> method will nevertheless capture your input.</span></span>

1. <span data-ttu-id="792ab-199">Presione <kbd>F11</kbd>.</span><span class="sxs-lookup"><span data-stu-id="792ab-199">Press <kbd>F11</kbd>.</span></span> <span data-ttu-id="792ab-200">Visual Studio resalta la instrucción que incluye la asignación de la variable `date` (`currentDate` en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="792ab-200">Visual Studio highlights the statement that includes the `date` variable assignment (`currentDate` in Visual Basic).</span></span> <span data-ttu-id="792ab-201">La ventana **Variables locales** muestra el valor devuelto por la llamada al método <xref:System.Console.ReadLine%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="792ab-201">The **Locals** window shows the value returned by the call to the <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="792ab-202">La ventana de la consola también muestra la cadena que escribió en la solicitud.</span><span class="sxs-lookup"><span data-stu-id="792ab-202">The console window also displays the string you entered at the prompt.</span></span>

1. <span data-ttu-id="792ab-203">Presione <kbd>F11</kbd>.</span><span class="sxs-lookup"><span data-stu-id="792ab-203">Press <kbd>F11</kbd>.</span></span> <span data-ttu-id="792ab-204">La ventana **Variables locales** muestra el valor de la variable `date` tras la asignación desde la propiedad <xref:System.DateTime.Now?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="792ab-204">The **Locals** window shows the value of the `date` variable after the assignment from the <xref:System.DateTime.Now?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="792ab-205">La ventana de consola permanece sin cambios.</span><span class="sxs-lookup"><span data-stu-id="792ab-205">The console window is unchanged.</span></span>

1. <span data-ttu-id="792ab-206">Presione <kbd>F11</kbd>.</span><span class="sxs-lookup"><span data-stu-id="792ab-206">Press <kbd>F11</kbd>.</span></span> <span data-ttu-id="792ab-207">Visual Studio llama al método <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="792ab-207">Visual Studio calls the <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="792ab-208">La ventana de la consola muestra la cadena con formato.</span><span class="sxs-lookup"><span data-stu-id="792ab-208">The console window displays the formatted string.</span></span>

1. <span data-ttu-id="792ab-209">Elija **Depurar** > **Depurar paso a paso para salir**. Otra manera de detener la ejecución paso a paso es presionar <kbd>Mayús</kbd>+<kbd>F11</kbd>.</span><span class="sxs-lookup"><span data-stu-id="792ab-209">Choose **Debug** > **Step Out**. Another way to stop step-by-step execution is by pressing <kbd>Shift</kbd>+<kbd>F11</kbd>.</span></span>

   <span data-ttu-id="792ab-210">La ventana de la consola muestra un mensaje y espera a que presione una tecla.</span><span class="sxs-lookup"><span data-stu-id="792ab-210">The console window displays a message and waits for you to press a key.</span></span>

1. <span data-ttu-id="792ab-211">Presione cualquier tecla para cerrar la ventana de consola y detener la depuración.</span><span class="sxs-lookup"><span data-stu-id="792ab-211">Press any key to close the console window and stop debugging.</span></span>

## <a name="use-release-build-configuration"></a><span data-ttu-id="792ab-212">Uso de la configuración de compilación de versión</span><span class="sxs-lookup"><span data-stu-id="792ab-212">Use Release build configuration</span></span>

<span data-ttu-id="792ab-213">Una vez que ha probado la versión de depuración de la aplicación, también debe compilar y probar la versión de lanzamiento.</span><span class="sxs-lookup"><span data-stu-id="792ab-213">Once you've tested the Debug version of your application, you should also compile and test the Release version.</span></span> <span data-ttu-id="792ab-214">La versión de lanzamiento incorpora optimizaciones del compilador que en ocasiones afectan negativamente al comportamiento de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="792ab-214">The Release version incorporates compiler optimizations that can sometimes negatively affect the behavior of an application.</span></span> <span data-ttu-id="792ab-215">Por ejemplo, las optimizaciones del compilador que están diseñadas para mejorar el rendimiento pueden crear condiciones de carrera en aplicaciones multiproceso.</span><span class="sxs-lookup"><span data-stu-id="792ab-215">For example, compiler optimizations that are designed to improve performance can create race conditions in multithreaded applications.</span></span>

<span data-ttu-id="792ab-216">Para compilar y probar la versión de lanzamiento de la aplicación de la consola, cambie la configuración de compilación en la barra de herramientas de **Depurar** a **Versión**.</span><span class="sxs-lookup"><span data-stu-id="792ab-216">To build and test the Release version of your console application, change the build configuration on the toolbar from **Debug** to **Release**.</span></span>

:::image type="content" source="./media/debugging-with-visual-studio/visual-studio-toolbar-release.png" alt-text="Barra de herramientas predeterminada de Visual Studio con Versión resaltado":::

<span data-ttu-id="792ab-218">Cuando presiona <kbd>F5</kbd> o elije **Compilar solución** en el menú **Compilar**, Visual Studio compila la versión de lanzamiento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="792ab-218">When you press <kbd>F5</kbd> or choose **Build Solution** from the **Build** menu, Visual Studio compiles the Release version of the application.</span></span> <span data-ttu-id="792ab-219">Puede probarla como hizo con la versión de depuración.</span><span class="sxs-lookup"><span data-stu-id="792ab-219">You can test it as you did the Debug version.</span></span>

## <a name="next-steps"></a><span data-ttu-id="792ab-220">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="792ab-220">Next steps</span></span>

<span data-ttu-id="792ab-221">En este tutorial, ha usado las herramientas de depuración de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="792ab-221">In this tutorial, you used Visual Studio debugging tools.</span></span> <span data-ttu-id="792ab-222">En el siguiente tutorial, publicará una versión de la aplicación que se puede implementar.</span><span class="sxs-lookup"><span data-stu-id="792ab-222">In the next tutorial, you publish a deployable version of the app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="792ab-223">Publicación de una aplicación de consola de .NET con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="792ab-223">Publish a .NET console application using Visual Studio</span></span>](publishing-with-visual-studio.md)
