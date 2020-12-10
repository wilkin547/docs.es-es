---
title: Depuración de una aplicación de consola de .NET con Visual Studio Code
description: Aprenda a depurar una aplicación de consola de .NET con Visual Studio Code.
ms.date: 05/26/2020
ms.openlocfilehash: 7215ed4a93b31ebac313c04708734667148c4e02
ms.sourcegitcommit: 30fef5b0ed76e334377d28fa8e80159b29353e10
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2020
ms.locfileid: "96556114"
---
# <a name="tutorial-debug-a-net-console-application-using-visual-studio-code"></a><span data-ttu-id="05a22-103">Tutorial: Depuración de una aplicación de consola de .NET con Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="05a22-103">Tutorial: Debug a .NET console application using Visual Studio Code</span></span>

<span data-ttu-id="05a22-104">En este tutorial se presentan las herramientas de depuración disponibles en Visual Studio Code para trabajar con aplicaciones de .NET.</span><span class="sxs-lookup"><span data-stu-id="05a22-104">This tutorial introduces the debugging tools available in Visual Studio Code for working with .NET apps.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="05a22-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="05a22-105">Prerequisites</span></span>

- <span data-ttu-id="05a22-106">Este tutorial funciona con la aplicación de consola que se crea en [Creación de una aplicación de consola de .NET con Visual Studio Code](with-visual-studio-code.md).</span><span class="sxs-lookup"><span data-stu-id="05a22-106">This tutorial works with the console app that you create in [Create a .NET console application using Visual Studio Code](with-visual-studio-code.md).</span></span>

## <a name="use-debug-build-configuration"></a><span data-ttu-id="05a22-107">Uso de la configuración de compilación de depuración</span><span class="sxs-lookup"><span data-stu-id="05a22-107">Use Debug build configuration</span></span>

<span data-ttu-id="05a22-108">*Depuración* y *Versión* son las configuraciones de compilación integradas de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="05a22-108">*Debug* and *Release* are .NET Core's built-in build configurations.</span></span> <span data-ttu-id="05a22-109">Use la configuración de compilación Depuración para depurar y la configuración de compilación Versión para la distribución final de la versión.</span><span class="sxs-lookup"><span data-stu-id="05a22-109">You use the Debug build configuration for debugging and the Release configuration for the final release distribution.</span></span>

<span data-ttu-id="05a22-110">En la configuración de depuración, el programa se compila sin optimizar y con toda la información de depuración simbólica.</span><span class="sxs-lookup"><span data-stu-id="05a22-110">In the Debug configuration, a program compiles with full symbolic debug information and no optimization.</span></span> <span data-ttu-id="05a22-111">La optimización complica la depuración, ya que la relación entre el código fuente y las instrucciones generadas es más compleja.</span><span class="sxs-lookup"><span data-stu-id="05a22-111">Optimization complicates debugging, because the relationship between source code and generated instructions is more complex.</span></span> <span data-ttu-id="05a22-112">La configuración de versión del programa no contiene información de depuración simbólica y está totalmente optimizada.</span><span class="sxs-lookup"><span data-stu-id="05a22-112">The release configuration of a program has no symbolic debug information and is fully optimized.</span></span>

<span data-ttu-id="05a22-113">De forma predeterminada, la configuración de lanzamiento de Visual Studio Code usa la configuración de compilación Depuración, por lo que no es necesario cambiarla antes de realizar esta operación.</span><span class="sxs-lookup"><span data-stu-id="05a22-113">By default, Visual Studio Code launch settings use the Debug build configuration, so you don't need to change it before debugging.</span></span>

1. <span data-ttu-id="05a22-114">Inicie Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="05a22-114">Start Visual Studio Code.</span></span>

1. <span data-ttu-id="05a22-115">Abra la carpeta del proyecto que ha creado en [Creación de una aplicación de consola de .NET con Visual Studio Code](with-visual-studio-code.md).</span><span class="sxs-lookup"><span data-stu-id="05a22-115">Open the folder of the project that you created in [Create a .NET console application using Visual Studio Code](with-visual-studio-code.md).</span></span>

## <a name="set-a-breakpoint"></a><span data-ttu-id="05a22-116">Establecer un punto de interrupción</span><span class="sxs-lookup"><span data-stu-id="05a22-116">Set a breakpoint</span></span>

<span data-ttu-id="05a22-117">Un *punto de interrupción* interrumpe temporalmente la ejecución de la aplicación antes de que se ejecute la línea con el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="05a22-117">A *breakpoint* temporarily interrupts the execution of the application before the line with the breakpoint is executed.</span></span>

1. <span data-ttu-id="05a22-118">Abra el archivo *Program.cs*.</span><span class="sxs-lookup"><span data-stu-id="05a22-118">Open the *Program.cs* file.</span></span>

1. <span data-ttu-id="05a22-119">Establezca un *punto de interrupción* en la línea que muestre el nombre, la fecha y la hora; para ello, haga clic en el margen izquierdo de la ventana de código.</span><span class="sxs-lookup"><span data-stu-id="05a22-119">Set a *breakpoint* on the line that displays the name, date, and time, by clicking in the left margin of the code window.</span></span> <span data-ttu-id="05a22-120">El margen izquierdo está a la izquierda de los números de línea.</span><span class="sxs-lookup"><span data-stu-id="05a22-120">The left margin is to the left of the line numbers.</span></span> <span data-ttu-id="05a22-121">Otras maneras de establecer un punto de interrupción consisten en presionar <kbd>F9</kbd> o seleccionar **Ejecutar** > **Alternar punto de interrupción** en el menú mientras se elige la línea de código.</span><span class="sxs-lookup"><span data-stu-id="05a22-121">Other ways to set a breakpoint are by pressing <kbd>F9</kbd> or choosing **Run** > **Toggle Breakpoint** from the menu while the line of code is selected.</span></span>

   <span data-ttu-id="05a22-122">Visual Studio Code marca la línea donde se establece el punto de interrupción con un punto rojo en el margen izquierdo.</span><span class="sxs-lookup"><span data-stu-id="05a22-122">Visual Studio Code indicates the line on which the breakpoint is set by displaying a red dot in the left margin.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/breakpoint-set.png" alt-text="Punto de interrupción":::

## <a name="set-up-for-terminal-input"></a><span data-ttu-id="05a22-124">Configuración para la entrada de terminal</span><span class="sxs-lookup"><span data-stu-id="05a22-124">Set up for terminal input</span></span>

<span data-ttu-id="05a22-125">El punto de interrupción se encuentra después de una llamada al método `Console.ReadLine`.</span><span class="sxs-lookup"><span data-stu-id="05a22-125">The breakpoint is located after a `Console.ReadLine` method call.</span></span> <span data-ttu-id="05a22-126">La **Consola de depuración** no acepta la entrada de terminal para un programa en ejecución.</span><span class="sxs-lookup"><span data-stu-id="05a22-126">The **Debug Console** doesn't accept terminal input for a running program.</span></span> <span data-ttu-id="05a22-127">Para controlar la entrada de terminal durante la depuración, puede usar el terminal integrado (una de las ventanas de Visual Studio Code) o un terminal externo.</span><span class="sxs-lookup"><span data-stu-id="05a22-127">To handle terminal input while debugging, you can use the integrated terminal (one of the Visual Studio Code windows) or an external terminal.</span></span> <span data-ttu-id="05a22-128">En este tutorial, usará el terminal integrado.</span><span class="sxs-lookup"><span data-stu-id="05a22-128">For this tutorial, you use the integrated terminal.</span></span>

1. <span data-ttu-id="05a22-129">Abra *.vscode/launch.json*.</span><span class="sxs-lookup"><span data-stu-id="05a22-129">Open *.vscode/launch.json*.</span></span>

1. <span data-ttu-id="05a22-130">Cambie la opción `console` de `internalConsole` a `integratedTerminal`:</span><span class="sxs-lookup"><span data-stu-id="05a22-130">Change the `console` setting from `internalConsole` to `integratedTerminal`:</span></span>

   ```json
   "console": "integratedTerminal",
   ```

1. <span data-ttu-id="05a22-131">Guarde los cambios.</span><span class="sxs-lookup"><span data-stu-id="05a22-131">Save your changes.</span></span>

## <a name="start-debugging"></a><span data-ttu-id="05a22-132">Iniciar depuración</span><span class="sxs-lookup"><span data-stu-id="05a22-132">Start debugging</span></span>

1. <span data-ttu-id="05a22-133">Abra la vista Depurar mediante el icono de depuración que hay en el menú de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="05a22-133">Open the Debug view by selecting the Debugging icon on the left side menu.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/select-debug-pane.png" alt-text="Abrir la pestaña Depurar en Visual Studio Code":::

1. <span data-ttu-id="05a22-135">Seleccione la flecha verde en la parte superior del panel, junto a **.NET Core Launch (console)** (Inicio de .NET Core [consola]).</span><span class="sxs-lookup"><span data-stu-id="05a22-135">Select the green arrow at the top of the pane, next to **.NET Core Launch (console)**.</span></span> <span data-ttu-id="05a22-136">Otras maneras de iniciar el programa en modo de depuración son presionar <kbd>F5</kbd> o elegir **Ejecutar** > **Iniciar depuración** en el menú.</span><span class="sxs-lookup"><span data-stu-id="05a22-136">Other ways to start the program in debugging mode are by pressing <kbd>F5</kbd> or choosing **Run** > **Start Debugging** from the menu.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/start-debugging.png" alt-text="Empezar la depuración":::

1. <span data-ttu-id="05a22-138">Seleccione la pestaña **Terminal** para ver el mensaje "What is your name?"</span><span class="sxs-lookup"><span data-stu-id="05a22-138">Select the **Terminal** tab to see the "What is your name?"</span></span> <span data-ttu-id="05a22-139">que muestra el programa antes de esperar una respuesta.</span><span class="sxs-lookup"><span data-stu-id="05a22-139">prompt that the program displays before waiting for a response.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/select-terminal.png" alt-text="Seleccionar la pestaña Terminal":::

1. <span data-ttu-id="05a22-141">Escriba una cadena en la ventana **Terminal** para responder a la pregunta del nombre y presione <kbd>Entrar</kbd>.</span><span class="sxs-lookup"><span data-stu-id="05a22-141">Enter a string in the **Terminal** window in response to the prompt for a name, and then press <kbd>Enter</kbd>.</span></span>

   <span data-ttu-id="05a22-142">La ejecución del programa se detiene cuando llega al punto de interrupción y antes de que se ejecute el método `Console.WriteLine`.</span><span class="sxs-lookup"><span data-stu-id="05a22-142">Program execution stops when it reaches the breakpoint and before the `Console.WriteLine` method executes.</span></span> <span data-ttu-id="05a22-143">La sección **Variables locales** de la ventana **Variables** muestra los valores de las variables definidas en el método que se ejecuta actualmente.</span><span class="sxs-lookup"><span data-stu-id="05a22-143">The **Locals** section of the **Variables** window displays the values of variables that are defined in the currently executing method.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/breakpoint-hit.png" alt-text="Punto de interrupción alcanzado donde se muestran las variables locales":::

## <a name="use-the-debug-console"></a><span data-ttu-id="05a22-145">Uso de la consola de depuración</span><span class="sxs-lookup"><span data-stu-id="05a22-145">Use the Debug Console</span></span>

<span data-ttu-id="05a22-146">La ventana **Consola de depuración** permite interactuar con la aplicación que está depurando.</span><span class="sxs-lookup"><span data-stu-id="05a22-146">The **Debug Console** window lets you interact with the application you're debugging.</span></span> <span data-ttu-id="05a22-147">Puede cambiar el valor de las variables para ver cómo afecta esto a su programa.</span><span class="sxs-lookup"><span data-stu-id="05a22-147">You can change the value of variables to see how it affects your program.</span></span>

1. <span data-ttu-id="05a22-148">Seleccione la pestaña **Consola de depuración**.</span><span class="sxs-lookup"><span data-stu-id="05a22-148">Select the **Debug Console** tab.</span></span>

1. <span data-ttu-id="05a22-149">Escriba `name = "Gracie"` en el símbolo del sistema de la parte inferior de la ventana **Consola de depuración** y presione la tecla <kbd>Entrar</kbd>.</span><span class="sxs-lookup"><span data-stu-id="05a22-149">Enter `name = "Gracie"` at the prompt at the bottom of the **Debug Console** window and press the <kbd>Enter</kbd> key.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/change-variable-values.png" alt-text="Cambiar los valores de las variables":::

1. <span data-ttu-id="05a22-151">Escriba `date = DateTime.Parse("2019-11-16T17:25:00Z").ToUniversalTime()` en la parte inferior de la ventana **Consola de depuración** y presione la tecla <kbd>Entrar</kbd>.</span><span class="sxs-lookup"><span data-stu-id="05a22-151">Enter `date = DateTime.Parse("2019-11-16T17:25:00Z").ToUniversalTime()` at the bottom of the **Debug Console** window and press the <kbd>Enter</kbd> key.</span></span>

   <span data-ttu-id="05a22-152">La ventana **Variables** muestra los nuevos valores de las variables `name` y `date`.</span><span class="sxs-lookup"><span data-stu-id="05a22-152">The **Variables** window displays the new values of the `name` and `date` variables.</span></span>

1. <span data-ttu-id="05a22-153">Para continuar con la ejecución del programa, seleccione el botón **Continuar** en la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="05a22-153">Continue program execution by selecting the **Continue** button in the toolbar.</span></span> <span data-ttu-id="05a22-154">Otra manera de continuar es presionar <kbd>F5</kbd>.</span><span class="sxs-lookup"><span data-stu-id="05a22-154">Another way to continue is by pressing <kbd>F5</kbd>.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/continue-debugging.png" alt-text="Continuar la depuración":::

1. <span data-ttu-id="05a22-156">Seleccione de nuevo la pestaña **Terminal**.</span><span class="sxs-lookup"><span data-stu-id="05a22-156">Select the **Terminal** tab again.</span></span>

   <span data-ttu-id="05a22-157">Los valores mostrados en la ventana de la consola corresponden a los cambios realizados en **Consola de depuración**.</span><span class="sxs-lookup"><span data-stu-id="05a22-157">The values displayed in the console window correspond to the changes you made in the **Debug Console**.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/changed-variable-values.png" alt-text="Terminal que muestra los valores especificados":::

1. <span data-ttu-id="05a22-159">Presione cualquier tecla para salir de la aplicación y detenga la depuración.</span><span class="sxs-lookup"><span data-stu-id="05a22-159">Press any key to exit the application and stop debugging.</span></span>

## <a name="set-a-conditional-breakpoint"></a><span data-ttu-id="05a22-160">Establecimiento de un punto de interrupción condicional</span><span class="sxs-lookup"><span data-stu-id="05a22-160">Set a conditional breakpoint</span></span>

<span data-ttu-id="05a22-161">El programa muestra la cadena que escribe el usuario.</span><span class="sxs-lookup"><span data-stu-id="05a22-161">The program displays the string that the user enters.</span></span> <span data-ttu-id="05a22-162">¿Qué sucede si el usuario no escribe nada?</span><span class="sxs-lookup"><span data-stu-id="05a22-162">What happens if the user doesn't enter anything?</span></span> <span data-ttu-id="05a22-163">Puede probarlo con una característica de depuración muy útil denominada *Punto de interrupción condicional*.</span><span class="sxs-lookup"><span data-stu-id="05a22-163">You can test this with a useful debugging feature called a *conditional breakpoint*.</span></span>

1. <span data-ttu-id="05a22-164">Haga clic con el botón derecho (o presione <kbd>Ctrl</kbd> y haga clic en macOS) sobre el punto rojo que representa al punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="05a22-164">Right-click (<kbd>Ctrl</kbd>-click on macOS) on the red dot that represents the breakpoint.</span></span> <span data-ttu-id="05a22-165">En el menú contextual, seleccione **Editar punto de interrupción** y se abrirá un cuadro de diálogo donde podrá escribir una expresión condicional.</span><span class="sxs-lookup"><span data-stu-id="05a22-165">In the context menu, select **Edit Breakpoint** to open a dialog that lets you enter a conditional expression.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/breakpoint-context-menu.png" alt-text="Menú contextual del punto de interrupción":::

1. <span data-ttu-id="05a22-167">Seleccione `Expression` en el menú desplegable, escriba esta expresión condicional y presione <kbd>Entrar</kbd>.</span><span class="sxs-lookup"><span data-stu-id="05a22-167">Select `Expression` in the drop-down, enter the following conditional expression, and press <kbd>Enter</kbd>.</span></span>

   ```csharp
   String.IsNullOrEmpty(name)
   ```

   :::image type="content" source="media/debugging-with-visual-studio-code/conditional-expression.png" alt-text="Escribir una expresión condicional":::

   <span data-ttu-id="05a22-169">Cada vez que se alcanza el punto de interrupción, el depurador llama al método `String.IsNullOrEmpty(name)` y se interrumpe en esta línea solo si la llamada al método devuelve `true`.</span><span class="sxs-lookup"><span data-stu-id="05a22-169">Each time the breakpoint is hit, the debugger calls the `String.IsNullOrEmpty(name)` method, and it breaks on this line only if the method call returns `true`.</span></span>

   <span data-ttu-id="05a22-170">En lugar de una expresión condicional, puede especificar un *número de llamadas*, que interrumpe la ejecución del programa antes de que se ejecute una instrucción un número de veces especificado.</span><span class="sxs-lookup"><span data-stu-id="05a22-170">Instead of a conditional expression, you can specify a *hit count*, which interrupts program execution before a statement is executed a specified number of times.</span></span> <span data-ttu-id="05a22-171">Otra opción consiste en especificar una *condición de filtro*, que interrumpe la ejecución del programa en función de atributos tales como un identificador de subproceso, un nombre de proceso o un nombre de subproceso.</span><span class="sxs-lookup"><span data-stu-id="05a22-171">Another option is to specify a *filter condition*, which interrupts program execution based on such attributes as a thread identifier, process name, or thread name.</span></span>

1. <span data-ttu-id="05a22-172">Inicie el programa con la depuración presionando <kbd>F5</kbd>.</span><span class="sxs-lookup"><span data-stu-id="05a22-172">Start the program with debugging by pressing <kbd>F5</kbd>.</span></span>

1. <span data-ttu-id="05a22-173">En la ventana <kbd>Terminal</kbd>, cuando se le pida que escriba su nombre, presione la tecla **Entrar**.</span><span class="sxs-lookup"><span data-stu-id="05a22-173">In the **Terminal** tab, press the <kbd>Enter</kbd> key when prompted to enter your name.</span></span>

   <span data-ttu-id="05a22-174">Como se ha cumplido la condición que especificó (`name` es `null` o <xref:System.String.Empty?displayProperty=nameWithType>), la ejecución del programa se detiene cuando se alcanza el punto de interrupción y antes de que se ejecute el método `Console.WriteLine`.</span><span class="sxs-lookup"><span data-stu-id="05a22-174">Because the condition you specified (`name` is either `null` or <xref:System.String.Empty?displayProperty=nameWithType>) has been satisfied, program execution stops when it reaches the breakpoint and before the `Console.WriteLine` method executes.</span></span>

   <span data-ttu-id="05a22-175">La ventana **Variables** muestra que el valor de la variable `name` es `""` o <xref:System.String.Empty?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="05a22-175">The **Variables** window shows that the value of the `name` variable is `""`, or <xref:System.String.Empty?displayProperty=nameWithType>.</span></span>

1. <span data-ttu-id="05a22-176">Confirme que el valor es una cadena vacía; para ello, escriba esta instrucción en la ventana **Consola de depuración** y presionando <kbd>Entrar</kbd>.</span><span class="sxs-lookup"><span data-stu-id="05a22-176">Confirm the value is an empty string by entering the following statement at the **Debug Console** prompt and pressing <kbd>Enter</kbd>.</span></span> <span data-ttu-id="05a22-177">El resultado es `true`.</span><span class="sxs-lookup"><span data-stu-id="05a22-177">The result is `true`.</span></span>

   ```csharp
   name == String.Empty
   ```

   :::image type="content" source="media/debugging-with-visual-studio-code/expression-in-debug-console.png" alt-text="La Consola de depuración devuelve un valor True después de ejecutar la instrucción":::

1. <span data-ttu-id="05a22-179">Seleccione el botón **Continuar** en la barra de herramientas para continuar la ejecución del programa.</span><span class="sxs-lookup"><span data-stu-id="05a22-179">Select the **Continue** button on the toolbar to continue program execution.</span></span>

1. <span data-ttu-id="05a22-180">Seleccione la pestaña **Terminal** y presione cualquier tecla para salir del programa y detener la depuración.</span><span class="sxs-lookup"><span data-stu-id="05a22-180">Select the **Terminal** tab, and press any key to exit the program and stop debugging.</span></span>

1. <span data-ttu-id="05a22-181">Para borrar el punto de interrupción, haga clic en el punto en el margen izquierdo de la ventana de código.</span><span class="sxs-lookup"><span data-stu-id="05a22-181">Clear the breakpoint by clicking on the dot in the left margin of the code window.</span></span> <span data-ttu-id="05a22-182">Otras formas de borrar un punto de interrupción consisten en presionar <kbd>F9</kbd> o elegir **Ejecutar > Alternar punto de interrupción** en el menú mientras se selecciona la línea de código.</span><span class="sxs-lookup"><span data-stu-id="05a22-182">Other ways to clear a breakpoint are by pressing <kbd>F9</kbd> or choosing **Run > Toggle Breakpoint** from the menu while the line of code is selected.</span></span>

1. <span data-ttu-id="05a22-183">Si recibe una advertencia que indica que se perderá la condición del punto de interrupción, seleccione **Quitar punto de interrupción**.</span><span class="sxs-lookup"><span data-stu-id="05a22-183">If you get a warning that the breakpoint condition will be lost, select **Remove Breakpoint**.</span></span>

## <a name="step-through-a-program"></a><span data-ttu-id="05a22-184">Ejecución paso a paso de un programa</span><span class="sxs-lookup"><span data-stu-id="05a22-184">Step through a program</span></span>

<span data-ttu-id="05a22-185">Visual Studio Code también permite recorrer línea a línea un programa y supervisar su ejecución.</span><span class="sxs-lookup"><span data-stu-id="05a22-185">Visual Studio Code also allows you to step line by line through a program and monitor its execution.</span></span> <span data-ttu-id="05a22-186">Normalmente, establecería un punto de interrupción y seguiría el flujo del programa mediante una pequeña parte de su código de programa.</span><span class="sxs-lookup"><span data-stu-id="05a22-186">Ordinarily, you'd set a breakpoint and follow program flow through a small part of your program code.</span></span> <span data-ttu-id="05a22-187">Como este programa es pequeño, puede ejecutar paso a paso el programa entero.</span><span class="sxs-lookup"><span data-stu-id="05a22-187">Since this program is small, you can step through the entire program.</span></span>

1. <span data-ttu-id="05a22-188">Establezca un punto de interrupción en la llave de apertura del método `Main`.</span><span class="sxs-lookup"><span data-stu-id="05a22-188">Set a breakpoint on the opening curly brace of the `Main` method.</span></span>

1. <span data-ttu-id="05a22-189">Presiona <kbd>F5</kbd> para iniciar la depuración.</span><span class="sxs-lookup"><span data-stu-id="05a22-189">Press <kbd>F5</kbd> to start debugging.</span></span>

   <span data-ttu-id="05a22-190">Visual Studio Code resalta la línea del punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="05a22-190">Visual Studio Code highlights the breakpoint line.</span></span>

   <span data-ttu-id="05a22-191">En este punto, la ventana **Variables** muestra que la matriz `args` está vacía, y `name` y `date` tienen valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="05a22-191">At this point, the **Variables** window shows that the `args` array is empty, and `name` and `date` have default values.</span></span>

1. <span data-ttu-id="05a22-192">Seleccione **Ejecutar** > **Paso a paso por instrucciones** o presione <kbd>F11</kbd>.</span><span class="sxs-lookup"><span data-stu-id="05a22-192">Select **Run** > **Step Into** or press <kbd>F11</kbd>.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/step-into.png" alt-text="Botón de depurar paso a paso por instrucciones":::

   <span data-ttu-id="05a22-194">Visual Studio Code resalta la línea siguiente.</span><span class="sxs-lookup"><span data-stu-id="05a22-194">Visual Studio Code highlights the next line.</span></span>

1. <span data-ttu-id="05a22-195">Seleccione **Ejecutar** > **Paso a paso por instrucciones** o presione <kbd>F11</kbd>.</span><span class="sxs-lookup"><span data-stu-id="05a22-195">Select **Run** > **Step Into** or press <kbd>F11</kbd>.</span></span>

   <span data-ttu-id="05a22-196">Visual Studio Code ejecuta `Console.WriteLine` para el mensaje de nombre y resalta la siguiente línea de ejecución.</span><span class="sxs-lookup"><span data-stu-id="05a22-196">Visual Studio Code executes the `Console.WriteLine` for the name prompt and highlights the next line of execution.</span></span> <span data-ttu-id="05a22-197">La línea siguiente es `Console.ReadLine` para `name`.</span><span class="sxs-lookup"><span data-stu-id="05a22-197">The next line is the `Console.ReadLine` for the `name`.</span></span> <span data-ttu-id="05a22-198">La ventana **Variables** no cambia y la pestaña **Terminal** muestra el mensaje "What is your name?"</span><span class="sxs-lookup"><span data-stu-id="05a22-198">The **Variables** window is unchanged, and the **Terminal** tab shows the "What is your name?"</span></span> <span data-ttu-id="05a22-199">.</span><span class="sxs-lookup"><span data-stu-id="05a22-199">prompt.</span></span>

1. <span data-ttu-id="05a22-200">Seleccione **Ejecutar** > **Paso a paso por instrucciones** o presione <kbd>F11</kbd>.</span><span class="sxs-lookup"><span data-stu-id="05a22-200">Select **Run** > **Step Into** or press <kbd>F11</kbd>.</span></span>

   <span data-ttu-id="05a22-201">Visual Studio resalta la asignación de la variable `name`.</span><span class="sxs-lookup"><span data-stu-id="05a22-201">Visual Studio highlights the `name` variable assignment.</span></span> <span data-ttu-id="05a22-202">La ventana **Variables** muestra que `name` todavía es `null`.</span><span class="sxs-lookup"><span data-stu-id="05a22-202">The **Variables** window shows that `name` is still `null`.</span></span>

1. <span data-ttu-id="05a22-203">Para responder al mensaje, escriba una cadena en la ventana Terminal y presione <kbd>Entrar</kbd>.</span><span class="sxs-lookup"><span data-stu-id="05a22-203">Respond to the prompt by entering a string in the Terminal tab and pressing <kbd>Enter</kbd>.</span></span>

   <span data-ttu-id="05a22-204">Es posible que la pestaña **Terminal** no muestre la cadena mientras la está escribiendo, pero el método <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> capturará la entrada.</span><span class="sxs-lookup"><span data-stu-id="05a22-204">The **Terminal** tab might not display the string you enter while you're entering it, but the <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> method will capture your input.</span></span>

1. <span data-ttu-id="05a22-205">Seleccione **Ejecutar** > **Paso a paso por instrucciones** o presione <kbd>F11</kbd>.</span><span class="sxs-lookup"><span data-stu-id="05a22-205">Select **Run** > **Step Into** or press <kbd>F11</kbd>.</span></span>

   <span data-ttu-id="05a22-206">Visual Studio Code resalta la asignación de la variable `date`.</span><span class="sxs-lookup"><span data-stu-id="05a22-206">Visual Studio Code highlights the `date` variable assignment.</span></span> <span data-ttu-id="05a22-207">La ventana **Variables** muestra el valor devuelto por la llamada al método <xref:System.Console.ReadLine%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="05a22-207">The **Variables** window shows the value returned by the call to the <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="05a22-208">En la pestaña **Terminal** se muestra la cadena que escribió en el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="05a22-208">The **Terminal** tab displays the string you entered at the prompt.</span></span>

1. <span data-ttu-id="05a22-209">Seleccione **Ejecutar** > **Paso a paso por instrucciones** o presione <kbd>F11</kbd>.</span><span class="sxs-lookup"><span data-stu-id="05a22-209">Select **Run** > **Step Into** or press <kbd>F11</kbd>.</span></span>

   <span data-ttu-id="05a22-210">La ventana **Variables** muestra el valor de la variable `date` tras la asignación desde la propiedad <xref:System.DateTime.Now?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="05a22-210">The **Variables** window shows the value of the `date` variable after the assignment from the <xref:System.DateTime.Now?displayProperty=nameWithType> property.</span></span>

1. <span data-ttu-id="05a22-211">Seleccione **Ejecutar** > **Paso a paso por instrucciones** o presione <kbd>F11</kbd>.</span><span class="sxs-lookup"><span data-stu-id="05a22-211">Select **Run** > **Step Into** or press <kbd>F11</kbd>.</span></span>

   <span data-ttu-id="05a22-212">Visual Studio Code llama al método <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="05a22-212">Visual Studio Code calls the <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="05a22-213">La ventana de la consola muestra la cadena con formato.</span><span class="sxs-lookup"><span data-stu-id="05a22-213">The console window displays the formatted string.</span></span>

1. <span data-ttu-id="05a22-214">Seleccione **Ejecutar** > **Paso a paso para salir** o presione <kbd>Mayús</kbd>+<kbd>F11</kbd>.</span><span class="sxs-lookup"><span data-stu-id="05a22-214">Select **Run** > **Step Out** or press <kbd>Shift</kbd>+<kbd>F11</kbd>.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/step-out.png" alt-text="Botón de depurar paso a paso para salir":::

1. <span data-ttu-id="05a22-216">Seleccione la pestaña **Terminal**.</span><span class="sxs-lookup"><span data-stu-id="05a22-216">Select the **Terminal** tab.</span></span>

   <span data-ttu-id="05a22-217">El terminal muestra "Presione cualquier tecla para salir..."</span><span class="sxs-lookup"><span data-stu-id="05a22-217">The terminal displays "Press any key to exit..."</span></span>

1. <span data-ttu-id="05a22-218">Presione cualquier tecla para salir de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="05a22-218">Press any key to exit the program.</span></span>

## <a name="use-release-build-configuration"></a><span data-ttu-id="05a22-219">Uso de la configuración de compilación de versión</span><span class="sxs-lookup"><span data-stu-id="05a22-219">Use Release build configuration</span></span>

<span data-ttu-id="05a22-220">Una vez que ha probado la versión de depuración de la aplicación, también debe compilar y probar la versión de lanzamiento.</span><span class="sxs-lookup"><span data-stu-id="05a22-220">Once you've tested the Debug version of your application, you should also compile and test the Release version.</span></span> <span data-ttu-id="05a22-221">La versión de lanzamiento incorpora optimizaciones del compilador que pueden afectar al comportamiento de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="05a22-221">The Release version incorporates compiler optimizations that can affect the behavior of an application.</span></span> <span data-ttu-id="05a22-222">Por ejemplo, las optimizaciones del compilador que están diseñadas para mejorar el rendimiento pueden crear condiciones de carrera en aplicaciones multiproceso.</span><span class="sxs-lookup"><span data-stu-id="05a22-222">For example, compiler optimizations that are designed to improve performance can create race conditions in multithreaded applications.</span></span>

<span data-ttu-id="05a22-223">Para compilar y probar la versión de lanzamiento de la aplicación de consola, abra el **Terminal** y ejecute este comando:</span><span class="sxs-lookup"><span data-stu-id="05a22-223">To build and test the Release version of your console application, open the **Terminal** and run the following command:</span></span>

```dotnetcli
dotnet run --configuration Release
```

## <a name="additional-resources"></a><span data-ttu-id="05a22-224">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="05a22-224">Additional resources</span></span>

* <span data-ttu-id="05a22-225">[Debugging in Visual Studio Code](https://code.visualstudio.com/docs/editor/debugging) (Depuración en Visual Studio Code)</span><span class="sxs-lookup"><span data-stu-id="05a22-225">[Debugging in Visual Studio Code](https://code.visualstudio.com/docs/editor/debugging)</span></span>

## <a name="next-steps"></a><span data-ttu-id="05a22-226">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="05a22-226">Next steps</span></span>

<span data-ttu-id="05a22-227">En este tutorial, ha usado las herramientas de depuración de Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="05a22-227">In this tutorial, you used Visual Studio Code debugging tools.</span></span> <span data-ttu-id="05a22-228">En el siguiente tutorial, publicará una versión de la aplicación que se puede implementar.</span><span class="sxs-lookup"><span data-stu-id="05a22-228">In the next tutorial, you publish a deployable version of the app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="05a22-229">Publicación de una aplicación de consola de .NET con Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="05a22-229">Publish a .NET console application using Visual Studio Code</span></span>](publishing-with-visual-studio-code.md)
