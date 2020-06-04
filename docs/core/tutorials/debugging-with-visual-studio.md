---
title: Depuración de una aplicación de consola de .NET Core con Visual Studio
description: Obtenga información sobre cómo depurar una aplicación de consola de .NET Core con Visual Studio.
ms.date: 05/20/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 4bd2a8a0e4b3cea55e209306dd3788552e4b61f3
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84005419"
---
# <a name="tutorial-debug-a-net-core-console-application-using-visual-studio"></a><span data-ttu-id="a079f-103">Tutorial: Depuración de una aplicación de consola de .NET Core con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a079f-103">Tutorial: Debug a .NET Core console application using Visual Studio</span></span>

<span data-ttu-id="a079f-104">En este tutorial se presentan las herramientas de depuración que hay disponibles en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a079f-104">This tutorial introduces the debugging tools available in Visual Studio.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a079f-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a079f-105">Prerequisites</span></span>

- <span data-ttu-id="a079f-106">Este tutorial funciona con la aplicación de consola que se crea en [Creación de una aplicación de consola de .NET Core en Visual Studio 2019](with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="a079f-106">This tutorial works with the console app that you create in [Create a .NET Core console application in Visual Studio 2019](with-visual-studio.md).</span></span>

## <a name="debug-build-configuration"></a><span data-ttu-id="a079f-107">Depuración de la configuración de compilación</span><span class="sxs-lookup"><span data-stu-id="a079f-107">Debug build configuration</span></span>

<span data-ttu-id="a079f-108">El modo de *depuración* y *versión* son dos de las configuraciones de compilación predeterminadas de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a079f-108">*Debug* and *Release* are two of Visual Studio's default build configurations.</span></span> <span data-ttu-id="a079f-109">La configuración de compilación actual se muestra en la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="a079f-109">The current build configuration is shown on the toolbar.</span></span> <span data-ttu-id="a079f-110">En la siguiente imagen de la barra de herramientas se muestra que Visual Studio está configurado para compilar la versión de depuración de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="a079f-110">The following toolbar image shows that Visual Studio is configured to compile the Debug version of the app:</span></span>

![Barra de herramientas de Visual Studio con Depuración resaltado](./media/debugging-with-visual-studio/visual-studio-toolbar-debug.png)

<span data-ttu-id="a079f-112">Empiece por ejecutar la versión de depuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a079f-112">Begin by running the Debug version of the app.</span></span> <span data-ttu-id="a079f-113">La configuración de compilación de depuración desactiva la mayoría de las optimizaciones del compilador y proporciona información más completa durante el proceso de compilación.</span><span class="sxs-lookup"><span data-stu-id="a079f-113">The Debug build configuration turns off most compiler optimizations and provides richer information during the build process.</span></span>

## <a name="set-a-breakpoint"></a><span data-ttu-id="a079f-114">Establecer un punto de interrupción</span><span class="sxs-lookup"><span data-stu-id="a079f-114">Set a breakpoint</span></span>

<!-- markdownlint-disable MD025 -->

1. <span data-ttu-id="a079f-115">Establezca un *punto de interrupción* en la línea que muestre el nombre, la fecha y la hora; para ello, haga clic en el margen izquierdo de la ventana de código de esa línea.</span><span class="sxs-lookup"><span data-stu-id="a079f-115">Set a *breakpoint* on the line that displays the name, date, and time, by clicking in the left margin of the code window on that line.</span></span> <span data-ttu-id="a079f-116">Otra manera de establecer un punto de interrupción consiste en colocar el cursor en la línea de código y después presionar **F9** o seleccionar **Depurar** > **Alternar punto de interrupción** en la barra de menús.</span><span class="sxs-lookup"><span data-stu-id="a079f-116">Another way to set a breakpoint is by placing the cursor in the line of code and then pressing **F9** or choosing **Debug** > **Toggle Breakpoint** from the menu bar.</span></span>

   <span data-ttu-id="a079f-117">Un punto de interrupción interrumpe temporalmente la ejecución de la aplicación *antes* de que se ejecute la línea con el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="a079f-117">A breakpoint temporarily interrupts the execution of the application *before* the line with the breakpoint is executed.</span></span>

   <span data-ttu-id="a079f-118">En esta imagen vemos que, para indicar la línea en la que se establece el punto de interrupción, Visual Studio lo resalta y muestra un punto rojo en el margen izquierdo.</span><span class="sxs-lookup"><span data-stu-id="a079f-118">As the following image shows, Visual Studio indicates the line on which the breakpoint is set by highlighting it and displaying a red dot in the left margin.</span></span>

   ![Ventana del programa Visual Studio con el punto de interrupción establecido](./media/debugging-with-visual-studio/set-breakpoint-in-editor.png)

1. <span data-ttu-id="a079f-120">Ejecute el programa en el modo de depuración; para ello, seleccione el botón **HelloWorld** con la flecha verde en la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="a079f-120">Run the program in Debug mode by selecting the **HelloWorld** button with the green arrow on the toolbar.</span></span> <span data-ttu-id="a079f-121">Otra manera de empezar la depuración consiste en presionar **F5** o elegir **Depuración** > **Iniciar depuración**.</span><span class="sxs-lookup"><span data-stu-id="a079f-121">Other ways to start debugging are by pressing **F5** or by choosing **Debug** > **Start Debugging**.</span></span>

1. <span data-ttu-id="a079f-122">Cuando el sistema le pida un nombre, escriba una cadena en la ventana de consola y luego presione **Entrar**.</span><span class="sxs-lookup"><span data-stu-id="a079f-122">Enter a string in the console window when the program prompts for a name, and then press **Enter**.</span></span>

1. <span data-ttu-id="a079f-123">La ejecución del programa se detiene cuando llega al punto de interrupción y antes de que se ejecute el método `Console.WriteLine`.</span><span class="sxs-lookup"><span data-stu-id="a079f-123">Program execution stops when it reaches the breakpoint and before the `Console.WriteLine` method executes.</span></span> <span data-ttu-id="a079f-124">La ventana **Variables locales** muestra los valores de las variables definidas en el método que se ejecuta actualmente.</span><span class="sxs-lookup"><span data-stu-id="a079f-124">The **Locals** window displays the values of variables that are defined in the currently executing method.</span></span>

   ![Captura de pantalla de un punto de interrupción en Visual Studio](./media/debugging-with-visual-studio/breakpoint-hit.png)

1. <span data-ttu-id="a079f-126">La ventana **Inmediato** le permite interactuar con la aplicación que está depurando.</span><span class="sxs-lookup"><span data-stu-id="a079f-126">The **Immediate** window lets you interact with the application you're debugging.</span></span> <span data-ttu-id="a079f-127">Puede cambiar el valor de las variables de forma interactiva para ver cómo afecta esto al programa.</span><span class="sxs-lookup"><span data-stu-id="a079f-127">You can interactively change the value of variables to see how it affects your program.</span></span>

   1. <span data-ttu-id="a079f-128">Si la ventana **Inmediato** no está visible, muéstrela; para ello, elija **Depurar** > **Ventanas** > **Inmediato**.</span><span class="sxs-lookup"><span data-stu-id="a079f-128">If the **Immediate** window is not visible, display it by choosing **Debug** > **Windows** > **Immediate**.</span></span>

   1. <span data-ttu-id="a079f-129">Escriba `name = "Gracie"` en la ventana **Inmediato** y presione la tecla **Entrar**.</span><span class="sxs-lookup"><span data-stu-id="a079f-129">Enter `name = "Gracie"` in the **Immediate** window and press the **Enter** key.</span></span>

   1. <span data-ttu-id="a079f-130">Escriba `date = DateTime.Parse("2019-11-16T17:25:00Z").ToUniversalTime()` en la ventana **Inmediato** y presione la tecla **Entrar**.</span><span class="sxs-lookup"><span data-stu-id="a079f-130">Enter `date = DateTime.Parse("2019-11-16T17:25:00Z").ToUniversalTime()` in the **Immediate** window and press the **Enter** key.</span></span>

   <span data-ttu-id="a079f-131">La ventana **Inmediato** muestra el valor de la variable de cadena y las propiedades del valor <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="a079f-131">The **Immediate** window displays the value of the string variable and the properties of the <xref:System.DateTime> value.</span></span> <span data-ttu-id="a079f-132">Además, los valores de las variables se actualizan en la ventana **Variables locales**.</span><span class="sxs-lookup"><span data-stu-id="a079f-132">In addition, the values of the variables are updated in the **Locals** window.</span></span>

   ![Ventanas Variables locales e Inmediato en Visual Studio 2019](./media/debugging-with-visual-studio/locals-immediate-window.png)

1. <span data-ttu-id="a079f-134">Para continuar con la ejecución del programa, seleccione el botón **Continuar** en la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="a079f-134">Continue program execution by selecting the **Continue** button in the toolbar.</span></span> <span data-ttu-id="a079f-135">Otra manera de hacerlo es a través de **Depurar** > **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="a079f-135">Another way to continue is by choosing **Debug** > **Continue**.</span></span>

   <span data-ttu-id="a079f-136">Los valores mostrados en la ventana de la consola corresponden a los cambios realizados en la ventana **Inmediato**.</span><span class="sxs-lookup"><span data-stu-id="a079f-136">The values displayed in the console window correspond to the changes you made in the **Immediate** window.</span></span>

   ![Ventana de consola que muestra los valores especificados](./media/debugging-with-visual-studio/console-window.png)

1. <span data-ttu-id="a079f-138">Presione cualquier tecla para salir de la aplicación y detenga la depuración.</span><span class="sxs-lookup"><span data-stu-id="a079f-138">Press any key to exit the application and stop debugging.</span></span>

## <a name="set-a-conditional-breakpoint"></a><span data-ttu-id="a079f-139">Establecimiento de un punto de interrupción condicional</span><span class="sxs-lookup"><span data-stu-id="a079f-139">Set a conditional breakpoint</span></span>

<span data-ttu-id="a079f-140">El programa muestra la cadena que escribe el usuario.</span><span class="sxs-lookup"><span data-stu-id="a079f-140">The program displays the string that the user enters.</span></span> <span data-ttu-id="a079f-141">¿Qué sucede si el usuario no escribe nada?</span><span class="sxs-lookup"><span data-stu-id="a079f-141">What happens if the user doesn't enter anything?</span></span> <span data-ttu-id="a079f-142">Puede probar esto con una característica de depuración útil que se denomina *punto de interrupción condicional*, que interrumpe la ejecución del programa cuando se cumplen una o más condiciones.</span><span class="sxs-lookup"><span data-stu-id="a079f-142">You can test this with a useful debugging feature called a *conditional breakpoint*, which breaks program execution when one or more conditions are met.</span></span>

<span data-ttu-id="a079f-143">Para establecer un punto de interrupción condicional y probar lo que sucede cuando el usuario no especifica una cadena, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a079f-143">To set a conditional breakpoint and test what happens when the user fails to enter a string, do the following:</span></span>

1. <span data-ttu-id="a079f-144">Haga clic con el botón derecho en el punto rojo que representa al punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="a079f-144">Right-click on the red dot that represents the breakpoint.</span></span> <span data-ttu-id="a079f-145">En el menú contextual, seleccione **Condiciones** para abrir el cuadro de diálogo **Configuración del punto de interrupción**.</span><span class="sxs-lookup"><span data-stu-id="a079f-145">In the context menu, select **Conditions** to open the **Breakpoint Settings** dialog.</span></span> <span data-ttu-id="a079f-146">Active la casilla **Condiciones** si aún no está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a079f-146">Select the box for **Conditions** if it's not already selected.</span></span>

   ![Editor con el panel de configuración de puntos de interrupción: C#](./media/debugging-with-visual-studio/breakpoint-settings.png)

1. <span data-ttu-id="a079f-148">En **Expresión condicional**, escriba el código siguiente en el campo que muestra el código de ejemplo que comprueba si `x` es 5.</span><span class="sxs-lookup"><span data-stu-id="a079f-148">For the **Conditional Expression**, enter the following code in the field that shows example code that tests if `x` is 5.</span></span> <span data-ttu-id="a079f-149">Si no se muestra el idioma que quiere usar, cambie el selector de idioma en la parte superior de la página.</span><span class="sxs-lookup"><span data-stu-id="a079f-149">If the language you want to use is not shown, change the language selector at the top of the page.</span></span>

   ```csharp
   String.IsNullOrEmpty(name)
   ```

   ```vb
   String.IsNullOrEmpty(name)
   ```

   <span data-ttu-id="a079f-150">Cada vez que se alcanza el punto de interrupción, el depurador llama al método `String.IsNullOrEmpty(name)` y se interrumpe en esta línea solo si la llamada al método devuelve `true`.</span><span class="sxs-lookup"><span data-stu-id="a079f-150">Each time the breakpoint is hit, the debugger calls the `String.IsNullOrEmpty(name)` method, and it breaks on this line only if the method call returns `true`.</span></span>

   <span data-ttu-id="a079f-151">En lugar de una expresión condicional, puede especificar un *número de llamadas*, que es lo que interrumpe la ejecución antes de que una instrucción se ejecute un número especificado de veces; o una *condición de filtro*, que es lo que interrumpe la ejecución del programa en función de atributos, como un identificador de subproceso, un nombre de proceso o un nombre de subproceso.</span><span class="sxs-lookup"><span data-stu-id="a079f-151">Instead of a conditional expression, you can specify a *hit count*, which interrupts program execution before a statement is executed a specified number of times, or a *filter condition*, which interrupts program execution based on such attributes as a thread identifier, process name, or thread name.</span></span>

1. <span data-ttu-id="a079f-152">Seleccione **Cerrar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="a079f-152">Select **Close** to close the dialog.</span></span>

1. <span data-ttu-id="a079f-153">Inicie el programa con la depuración presionando **F5**.</span><span class="sxs-lookup"><span data-stu-id="a079f-153">Start the program with debugging by pressing **F5**.</span></span>

1. <span data-ttu-id="a079f-154">En la ventana de consola, cuando se le pida que escriba su nombre, presione la tecla **Entrar**.</span><span class="sxs-lookup"><span data-stu-id="a079f-154">In the console window, press the **Enter** key when prompted to enter your name.</span></span>

1. <span data-ttu-id="a079f-155">Como se ha cumplido la condición que especificó (`name` es `null` o <xref:System.String.Empty?displayProperty=nameWithType>), la ejecución del programa se detiene cuando se alcanza el punto de interrupción y antes de que se ejecute el método `Console.WriteLine`.</span><span class="sxs-lookup"><span data-stu-id="a079f-155">Because the condition you specified (`name` is either `null` or <xref:System.String.Empty?displayProperty=nameWithType>) has been satisfied, program execution stops when it reaches the breakpoint and before the `Console.WriteLine` method executes.</span></span>

1. <span data-ttu-id="a079f-156">Seleccione la ventana **Variables locales**, que muestra los valores de las variables que son locales para el método que se ejecuta actualmente.</span><span class="sxs-lookup"><span data-stu-id="a079f-156">Select the **Locals** window, which shows the values of variables that are local to the currently executing method.</span></span> <span data-ttu-id="a079f-157">En este caso, `Main` es el método que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="a079f-157">In this case, `Main` is the currently executing method.</span></span> <span data-ttu-id="a079f-158">Observe que el valor de la variable `name` es `""` o <xref:System.String.Empty?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a079f-158">Observe that the value of the `name` variable is `""`, or <xref:System.String.Empty?displayProperty=nameWithType>.</span></span>

1. <span data-ttu-id="a079f-159">Confirme que el valor es una cadena vacía escribiendo la siguiente instrucción en la ventana **Inmediato** y presionando **Entrar**.</span><span class="sxs-lookup"><span data-stu-id="a079f-159">Confirm the value is an empty string by entering the following statement in the **Immediate** window and pressing **Enter**.</span></span> <span data-ttu-id="a079f-160">El resultado es `true`.</span><span class="sxs-lookup"><span data-stu-id="a079f-160">The result is `true`.</span></span>

   ```csharp
   ? name == String.Empty
   ```

   ```vb
   ? String.IsNullOrEmpty(name)
   ```

   <span data-ttu-id="a079f-161">El signo de interrogación dirige la ventana Inmediato para [evaluar una expresión](/visualstudio/ide/reference/immediate-window#enter-commands).</span><span class="sxs-lookup"><span data-stu-id="a079f-161">The question mark directs the immediate window to [evaluate an expression](/visualstudio/ide/reference/immediate-window#enter-commands).</span></span>

   ![Ventana Inmediato en la que se devuelve un valor de True después de que se ejecute la instrucción: C#](./media/debugging-with-visual-studio/immediate-window-output.png)

1. <span data-ttu-id="a079f-163">Seleccione el botón **Continuar** en la barra de herramientas para continuar la ejecución del programa.</span><span class="sxs-lookup"><span data-stu-id="a079f-163">Select the **Continue** button on the toolbar to continue program execution.</span></span>

1. <span data-ttu-id="a079f-164">Presione cualquier tecla para cerrar la ventana de consola y detener la depuración.</span><span class="sxs-lookup"><span data-stu-id="a079f-164">Press any key to close the console window and stop debugging.</span></span>

1. <span data-ttu-id="a079f-165">Para borrar el punto de interrupción, haga clic en el punto en el margen izquierdo de la ventana de código.</span><span class="sxs-lookup"><span data-stu-id="a079f-165">Clear the breakpoint by clicking on the dot in the left margin of the code window.</span></span> <span data-ttu-id="a079f-166">Otra manera de hacerlo es elegir **Depurar > Alternar punto de interrupción** mientras se selecciona la línea de código.</span><span class="sxs-lookup"><span data-stu-id="a079f-166">Another way to clear a breakpoint is by choosing **Debug > Toggle Breakpoint** while the line of code is selected.</span></span>

## <a name="step-through-a-program"></a><span data-ttu-id="a079f-167">Ejecución paso a paso de un programa</span><span class="sxs-lookup"><span data-stu-id="a079f-167">Step through a program</span></span>

<span data-ttu-id="a079f-168">Visual Studio también le permite recorrer línea a línea un programa y supervisar su ejecución.</span><span class="sxs-lookup"><span data-stu-id="a079f-168">Visual Studio also allows you to step line by line through a program and monitor its execution.</span></span> <span data-ttu-id="a079f-169">Normalmente, establecería un punto de interrupción y seguiría el flujo del programa mediante una pequeña parte de su código de programa.</span><span class="sxs-lookup"><span data-stu-id="a079f-169">Ordinarily, you'd set a breakpoint and follow program flow through a small part of your program code.</span></span> <span data-ttu-id="a079f-170">Como este programa es pequeño, puede ejecutar paso a paso el programa entero.</span><span class="sxs-lookup"><span data-stu-id="a079f-170">Since your program is small, you can step through the entire program.</span></span>

1. <span data-ttu-id="a079f-171">Elija **Depurar** > **Depurar paso a paso por instrucciones**.</span><span class="sxs-lookup"><span data-stu-id="a079f-171">Choose **Debug** > **Step Into**.</span></span> <span data-ttu-id="a079f-172">Otra manera de depurar una instrucción cada vez es presionar **F11**.</span><span class="sxs-lookup"><span data-stu-id="a079f-172">Another way to debug one statement at a time is by pressing **F11**.</span></span>

   <span data-ttu-id="a079f-173">Visual Studio resalta y muestra una flecha junto a la siguiente línea de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a079f-173">Visual Studio highlights and displays an arrow beside the next line of execution.</span></span>

   <span data-ttu-id="a079f-174">C#</span><span class="sxs-lookup"><span data-stu-id="a079f-174">C#</span></span>

   ![Método Paso a paso por instrucciones de Visual Studio: C#](./media/debugging-with-visual-studio/step-into-method.png)

   <span data-ttu-id="a079f-176">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a079f-176">Visual Basic</span></span>

   ![Método Paso a paso por instrucciones de Visual Studio: Visual Basic](./media/debugging-with-visual-studio/vb-step-into-method.png)

   <span data-ttu-id="a079f-178">En este punto, la ventana **Variables locales** muestra que la matriz `args` está vacía, y `name` y `date` tienen valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="a079f-178">At this point, the **Locals** window shows that the `args` array is empty, and `name` and `date` have default values.</span></span> <span data-ttu-id="a079f-179">Además, Visual Studio ha abierto una ventana de consola en blanco.</span><span class="sxs-lookup"><span data-stu-id="a079f-179">In addition, Visual Studio has opened a blank console window.</span></span>

1. <span data-ttu-id="a079f-180">Presione **F11**.</span><span class="sxs-lookup"><span data-stu-id="a079f-180">Press **F11**.</span></span> <span data-ttu-id="a079f-181">Visual Studio ahora resalta la siguiente línea de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a079f-181">Visual Studio now highlights the next line of execution.</span></span> <span data-ttu-id="a079f-182">La ventana **Variables locales** no cambia y la ventana de consola permanece en blanco.</span><span class="sxs-lookup"><span data-stu-id="a079f-182">The **Locals** window is unchanged, and the console window remains blank.</span></span>

   <span data-ttu-id="a079f-183">C#</span><span class="sxs-lookup"><span data-stu-id="a079f-183">C#</span></span>

   ![Origen del método Paso a paso por instrucciones de Visual Studio: C#](./media/debugging-with-visual-studio/step-into-source-method.png)

   <span data-ttu-id="a079f-185">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a079f-185">Visual Basic</span></span>

   ![Origen del método Paso a paso por instrucciones de Visual Studio: Visual Basic](./media/debugging-with-visual-studio/vb-step-into-source-method.png)

1. <span data-ttu-id="a079f-187">Presione **F11**.</span><span class="sxs-lookup"><span data-stu-id="a079f-187">Press **F11**.</span></span> <span data-ttu-id="a079f-188">Visual Studio resalta la instrucción que incluye la asignación de variables `name`.</span><span class="sxs-lookup"><span data-stu-id="a079f-188">Visual Studio highlights the statement that includes the `name` variable assignment.</span></span> <span data-ttu-id="a079f-189">La ventana **Variables locales** muestra que `name` es `null`, y la ventana de consola muestra la cadena "What is your name?".</span><span class="sxs-lookup"><span data-stu-id="a079f-189">The **Locals** window shows that `name` is `null`, and the console window displays the string "What is your name?".</span></span>

1. <span data-ttu-id="a079f-190">Para responder a la solicitud, escriba una cadena en la ventana de consola y presione **Entrar**.</span><span class="sxs-lookup"><span data-stu-id="a079f-190">Respond to the prompt by entering a string in the console window and pressing **Enter**.</span></span> <span data-ttu-id="a079f-191">La consola no responde y la cadena que especificó no se muestra en la ventana de la consola, pero el método <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> capturará en cambio la entrada.</span><span class="sxs-lookup"><span data-stu-id="a079f-191">The console is unresponsive, and the string you entered isn't displayed in the console window, but the <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> method will nevertheless capture your input.</span></span>

1. <span data-ttu-id="a079f-192">Presione **F11**.</span><span class="sxs-lookup"><span data-stu-id="a079f-192">Press **F11**.</span></span> <span data-ttu-id="a079f-193">Visual Studio resalta la instrucción que incluye la asignación de la variable `date` (`currentDate` en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="a079f-193">Visual Studio highlights the statement that includes the `date` variable assignment (`currentDate` in Visual Basic).</span></span> <span data-ttu-id="a079f-194">La ventana **Variables locales** muestra el valor devuelto por la llamada al método <xref:System.Console.ReadLine%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a079f-194">The **Locals** window shows the value returned by the call to the <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="a079f-195">La ventana de la consola también muestra la cadena que escribió en la solicitud.</span><span class="sxs-lookup"><span data-stu-id="a079f-195">The console window also displays the string you entered at the prompt.</span></span>

1. <span data-ttu-id="a079f-196">Presione **F11**.</span><span class="sxs-lookup"><span data-stu-id="a079f-196">Press **F11**.</span></span> <span data-ttu-id="a079f-197">La ventana **Variables locales** muestra el valor de la variable `date` tras la asignación desde la propiedad <xref:System.DateTime.Now?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a079f-197">The **Locals** window shows the value of the `date` variable after the assignment from the <xref:System.DateTime.Now?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="a079f-198">La ventana de consola permanece sin cambios.</span><span class="sxs-lookup"><span data-stu-id="a079f-198">The console window is unchanged.</span></span>

1. <span data-ttu-id="a079f-199">Presione **F11**.</span><span class="sxs-lookup"><span data-stu-id="a079f-199">Press **F11**.</span></span> <span data-ttu-id="a079f-200">Visual Studio llama al método <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a079f-200">Visual Studio calls the <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="a079f-201">La ventana de la consola muestra la cadena con formato.</span><span class="sxs-lookup"><span data-stu-id="a079f-201">The console window displays the formatted string.</span></span>

1. <span data-ttu-id="a079f-202">Elija **Depurar** > **Depurar paso a paso para salir**. Otra manera de detener la ejecución paso a paso es presionar **Mayús**+**F11**.</span><span class="sxs-lookup"><span data-stu-id="a079f-202">Choose **Debug** > **Step Out**. Another way to stop step-by-step execution is by pressing **Shift**+**F11**.</span></span>

   <span data-ttu-id="a079f-203">La ventana de la consola muestra un mensaje y espera a que presione una tecla.</span><span class="sxs-lookup"><span data-stu-id="a079f-203">The console window displays a message and waits for you to press a key.</span></span>

1. <span data-ttu-id="a079f-204">Presione cualquier tecla para cerrar la ventana de consola y detener la depuración.</span><span class="sxs-lookup"><span data-stu-id="a079f-204">Press any key to close the console window and stop debugging.</span></span>

## <a name="build-a-release-version"></a><span data-ttu-id="a079f-205">Creación de una versión de lanzamiento</span><span class="sxs-lookup"><span data-stu-id="a079f-205">Build a Release version</span></span>

<span data-ttu-id="a079f-206">Una vez que ha probado la versión de depuración de la aplicación, también debe compilar y probar la versión de lanzamiento.</span><span class="sxs-lookup"><span data-stu-id="a079f-206">Once you've tested the Debug version of your application, you should also compile and test the Release version.</span></span> <span data-ttu-id="a079f-207">La versión de lanzamiento incorpora optimizaciones del compilador que en ocasiones afectan negativamente al comportamiento de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="a079f-207">The Release version incorporates compiler optimizations that can sometimes negatively affect the behavior of an application.</span></span> <span data-ttu-id="a079f-208">Por ejemplo, las optimizaciones del compilador que están diseñadas para mejorar el rendimiento pueden crear condiciones de carrera en aplicaciones multiproceso.</span><span class="sxs-lookup"><span data-stu-id="a079f-208">For example, compiler optimizations that are designed to improve performance can create race conditions in multithreaded applications.</span></span>

<span data-ttu-id="a079f-209">Para compilar y probar la versión de lanzamiento de la aplicación de la consola, cambie la configuración de compilación en la barra de herramientas de **Depurar** a **Versión**.</span><span class="sxs-lookup"><span data-stu-id="a079f-209">To build and test the Release version of your console application, change the build configuration on the toolbar from **Debug** to **Release**.</span></span>

![Barra de herramientas predeterminada de Visual Studio con Depuración resaltado](./media/debugging-with-visual-studio/visual-studio-toolbar-release.png)

<span data-ttu-id="a079f-211">Cuando presiona **F5** o elije **Compilar solución** en el menú **Compilar**, Visual Studio compila la versión de lanzamiento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a079f-211">When you press **F5** or choose **Build Solution** from the **Build** menu, Visual Studio compiles the Release version of the application.</span></span> <span data-ttu-id="a079f-212">Puede probarla como hizo con la versión de depuración.</span><span class="sxs-lookup"><span data-stu-id="a079f-212">You can test it as you did the Debug version.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a079f-213">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="a079f-213">Next steps</span></span>

<span data-ttu-id="a079f-214">En este tutorial, ha usado las herramientas de depuración de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a079f-214">In this tutorial, you used Visual Studio debugging tools.</span></span> <span data-ttu-id="a079f-215">En el siguiente tutorial, publicará una versión de la aplicación que se puede implementar.</span><span class="sxs-lookup"><span data-stu-id="a079f-215">In the next tutorial, you publish a deployable version of the app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="a079f-216">Publicación de una aplicación de consola de .NET Core con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a079f-216">Publish a .NET Core console application with Visual Studio</span></span>](publishing-with-visual-studio.md)
