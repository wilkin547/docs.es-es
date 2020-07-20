---
title: Depuración de una aplicación de consola de .NET Core con Visual Studio para Mac
description: Aprenda a depurar una aplicación de consola de .NET Core con Visual Studio para Mac.
ms.date: 06/08/2020
ms.openlocfilehash: 7e2a25266fab40b5ef1d0a38b8bbf06a6843746b
ms.sourcegitcommit: 3492dafceb5d4183b6b0d2f3bdf4a1abc4d5ed8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/16/2020
ms.locfileid: "86416017"
---
# <a name="tutorial-debug-a-net-core-console-application-using-visual-studio-for-mac"></a><span data-ttu-id="3ceef-103">Tutorial: Depuración de una aplicación de consola de .NET Core con Visual Studio para Mac</span><span class="sxs-lookup"><span data-stu-id="3ceef-103">Tutorial: Debug a .NET Core console application using Visual Studio for Mac</span></span>

<span data-ttu-id="3ceef-104">En este tutorial se presentan las herramientas de depuración que hay disponibles en Visual Studio para Mac.</span><span class="sxs-lookup"><span data-stu-id="3ceef-104">This tutorial introduces the debugging tools available in Visual Studio for Mac.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3ceef-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="3ceef-105">Prerequisites</span></span>

- <span data-ttu-id="3ceef-106">Este tutorial funciona con la aplicación de consola que se crea en [Creación de una aplicación de consola de .NET Core en Visual Studio para Mac](with-visual-studio-mac.md).</span><span class="sxs-lookup"><span data-stu-id="3ceef-106">This tutorial works with the console app that you create in [Create a .NET Core console application in Visual Studio for Mac](with-visual-studio-mac.md).</span></span>

## <a name="use-debug-build-configuration"></a><span data-ttu-id="3ceef-107">Uso de la configuración de compilación de depuración</span><span class="sxs-lookup"><span data-stu-id="3ceef-107">Use Debug build configuration</span></span>

<span data-ttu-id="3ceef-108">*Depuración* y *Versión* son las configuraciones de compilación integradas de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3ceef-108">*Debug* and *Release* are Visual Studio's built-in build configurations.</span></span> <span data-ttu-id="3ceef-109">Use la configuración de compilación Depuración para depurar y la configuración de compilación Versión para la distribución final de la versión.</span><span class="sxs-lookup"><span data-stu-id="3ceef-109">You use the Debug build configuration for debugging and the Release configuration for the final release distribution.</span></span>

<span data-ttu-id="3ceef-110">En la configuración de depuración, el programa se compila sin optimizar y con toda la información de depuración simbólica.</span><span class="sxs-lookup"><span data-stu-id="3ceef-110">In the Debug configuration, a program compiles with full symbolic debug information and no optimization.</span></span> <span data-ttu-id="3ceef-111">La optimización complica la depuración, ya que la relación entre el código fuente y las instrucciones generadas es más compleja.</span><span class="sxs-lookup"><span data-stu-id="3ceef-111">Optimization complicates debugging, because the relationship between source code and generated instructions is more complex.</span></span> <span data-ttu-id="3ceef-112">La configuración de versión del programa no contiene información de depuración simbólica y está totalmente optimizada.</span><span class="sxs-lookup"><span data-stu-id="3ceef-112">The release configuration of a program has no symbolic debug information and is fully optimized.</span></span>

<span data-ttu-id="3ceef-113">De forma predeterminada, Visual Studio usa la configuración de compilación Depuración, por lo que no es necesario cambiarla antes de depurar.</span><span class="sxs-lookup"><span data-stu-id="3ceef-113">By default, Visual Studio uses the Debug build configuration, so you don't need to change it before debugging.</span></span>

1. <span data-ttu-id="3ceef-114">Inicie Visual Studio para Mac:</span><span class="sxs-lookup"><span data-stu-id="3ceef-114">Start Visual Studio for Mac.</span></span>

1. <span data-ttu-id="3ceef-115">Abra el proyecto que creó en [Creación de una aplicación de consola de .NET Core en Visual Studio para Mac](with-visual-studio-mac.md).</span><span class="sxs-lookup"><span data-stu-id="3ceef-115">Open the project that you created in [Create a .NET Core console application in Visual Studio for Mac](with-visual-studio-mac.md).</span></span>

   <span data-ttu-id="3ceef-116">La configuración de compilación actual se muestra en la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="3ceef-116">The current build configuration is shown on the toolbar.</span></span> <span data-ttu-id="3ceef-117">En la siguiente imagen de la barra de herramientas se muestra que Visual Studio está configurado para compilar la versión de depuración de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="3ceef-117">The following toolbar image shows that Visual Studio is configured to compile the Debug version of the app:</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-mac/visual-studio-toolbar-debug.png" alt-text="Barra de herramientas de Visual Studio con Depuración resaltado":::

## <a name="set-a-breakpoint"></a><span data-ttu-id="3ceef-119">Establecer un punto de interrupción</span><span class="sxs-lookup"><span data-stu-id="3ceef-119">Set a breakpoint</span></span>

<span data-ttu-id="3ceef-120">Un *punto de interrupción* interrumpe temporalmente la ejecución de la aplicación antes de que se ejecute la línea con el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="3ceef-120">A *breakpoint* temporarily interrupts the execution of the application before the line with the breakpoint is executed.</span></span>

1. <span data-ttu-id="3ceef-121">Establezca un punto de interrupción en la línea que muestra el nombre, la fecha y la hora.</span><span class="sxs-lookup"><span data-stu-id="3ceef-121">Set a breakpoint on the line that displays the name, date, and time.</span></span> <span data-ttu-id="3ceef-122">Para ello, coloque el cursor en la línea de código y presione <kbd>⌘</kbd><kbd>\\</kbd> (<kbd>command</kbd>+<kbd>\\</kbd>).</span><span class="sxs-lookup"><span data-stu-id="3ceef-122">To do that, place the cursor in the line of code and press <kbd>⌘</kbd><kbd>\\</kbd> (<kbd>command</kbd>+<kbd>\\</kbd>).</span></span> <span data-ttu-id="3ceef-123">Otra manera de establecer un punto de interrupción es seleccionar **Ejecutar** > **Alternar punto de interrupción** en el menú.</span><span class="sxs-lookup"><span data-stu-id="3ceef-123">Another way to set a breakpoint is by selecting **Run** > **Toggle Breakpoint** from the menu.</span></span>

   <span data-ttu-id="3ceef-124">Para indicar la línea en la que se establece el punto de interrupción, Visual Studio lo resalta y muestra un punto rojo en el margen izquierdo.</span><span class="sxs-lookup"><span data-stu-id="3ceef-124">Visual Studio indicates the line on which the breakpoint is set by highlighting it and displaying a red dot in the left margin.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-mac/set-breakpoint-in-editor.png" alt-text="Ventana del programa Visual Studio con el punto de interrupción establecido":::

1. <span data-ttu-id="3ceef-126">Presione <kbd>⌘</kbd><kbd>↵</kbd> (<kbd>command</kbd>+<kbd>entrar</kbd>) para iniciar el programa en modo de depuración.</span><span class="sxs-lookup"><span data-stu-id="3ceef-126">Press <kbd>⌘</kbd><kbd>↵</kbd> (<kbd>command</kbd>+<kbd>enter</kbd>) to start the program in debugging mode.</span></span> <span data-ttu-id="3ceef-127">Otra manera de iniciar la depuración es elegir **Ejecutar** > **Iniciar depuración** en el menú.</span><span class="sxs-lookup"><span data-stu-id="3ceef-127">Another way to start debugging is by choosing **Run** > **Start Debugging** from the menu.</span></span>

1. <span data-ttu-id="3ceef-128">Cuando el sistema le pida un nombre, escriba una cadena en la ventana de terminar y luego presione <kbd>Entrar</kbd>.</span><span class="sxs-lookup"><span data-stu-id="3ceef-128">Enter a string in the terminal window when the program prompts for a name, and then press <kbd>enter</kbd>.</span></span>

1. <span data-ttu-id="3ceef-129">La ejecución del programa se detiene cuando llega al punto de interrupción y antes de que se ejecute el método `Console.WriteLine`.</span><span class="sxs-lookup"><span data-stu-id="3ceef-129">Program execution stops when it reaches the breakpoint, before the `Console.WriteLine` method executes.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-mac/breakpoint-hit.png" alt-text="Captura de pantalla de un punto de interrupción en Visual Studio":::

## <a name="use-the-immediate-window"></a><span data-ttu-id="3ceef-131">Uso de la ventana Inmediato</span><span class="sxs-lookup"><span data-stu-id="3ceef-131">Use the Immediate window</span></span>

<span data-ttu-id="3ceef-132">La ventana **Inmediato** le permite interactuar con la aplicación que está depurando.</span><span class="sxs-lookup"><span data-stu-id="3ceef-132">The **Immediate** window lets you interact with the application you're debugging.</span></span> <span data-ttu-id="3ceef-133">Puede cambiar el valor de las variables de forma interactiva para ver cómo afecta esto al programa.</span><span class="sxs-lookup"><span data-stu-id="3ceef-133">You can interactively change the value of variables to see how it affects your program.</span></span>

1. <span data-ttu-id="3ceef-134">Si la ventana **Inmediato** no está visible, muéstrela; para ello, elija **Ver** > **Paneles de depuración** > **Inmediato**.</span><span class="sxs-lookup"><span data-stu-id="3ceef-134">If the **Immediate** window is not visible, display it by choosing **View** > **Debug Pads** > **Immediate**.</span></span>

1. <span data-ttu-id="3ceef-135">Escriba `name = "Gracie"` en la ventana **Inmediato** y presione <kbd>Entrar</kbd>.</span><span class="sxs-lookup"><span data-stu-id="3ceef-135">Enter `name = "Gracie"` in the **Immediate** window and press <kbd>enter</kbd>.</span></span>

1. <span data-ttu-id="3ceef-136">Escriba `date = date.AddDays(1)` en la ventana **Inmediato** y presione <kbd>Entrar</kbd>.</span><span class="sxs-lookup"><span data-stu-id="3ceef-136">Enter `date = date.AddDays(1)` in the **Immediate** window and press <kbd>enter</kbd>.</span></span>

   <span data-ttu-id="3ceef-137">La ventana **Inmediato** muestra el nuevo valor de la variable de cadena y las propiedades del valor <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="3ceef-137">The **Immediate** window displays the new value of the string variable and the properties of the <xref:System.DateTime> value.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-mac/immediate-window.png" alt-text="Ventana Inmediato en Visual Studio":::

   <span data-ttu-id="3ceef-139">La ventana **Variables locales** muestra los valores de las variables definidas en el método que se ejecuta actualmente.</span><span class="sxs-lookup"><span data-stu-id="3ceef-139">The **Locals** window displays the values of variables that are defined in the currently executing method.</span></span> <span data-ttu-id="3ceef-140">Los valores de las variables que acaba de cambiar se actualizan en la ventana **Variables locales**.</span><span class="sxs-lookup"><span data-stu-id="3ceef-140">The values of the variables that you just changed are updated in the **Locals** window.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-mac/locals-window.png" alt-text="Ventana Variables locales de Visual Studio":::

1. <span data-ttu-id="3ceef-142">Presione <kbd>⌘</kbd><kbd>↵</kbd> (<kbd>command</kbd>+<kbd>entrar</kbd>) para continuar con la depuración.</span><span class="sxs-lookup"><span data-stu-id="3ceef-142">Press <kbd>⌘</kbd><kbd>↵</kbd> (<kbd>command</kbd>+<kbd>enter</kbd>) to continue debugging.</span></span>

   <span data-ttu-id="3ceef-143">Los valores mostrados en el terminar corresponden a los cambios realizados en la ventana **Inmediato**.</span><span class="sxs-lookup"><span data-stu-id="3ceef-143">The values displayed in the terminal correspond to the changes you made in the **Immediate** window.</span></span>

   <span data-ttu-id="3ceef-144">Si no ve el terminal, seleccione **Terminal - HelloWorld** en la barra de navegación inferior.</span><span class="sxs-lookup"><span data-stu-id="3ceef-144">If you don't see the Terminal, select **Terminal - HelloWorld** in the bottom navigation bar.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-mac/terminal-hello-world.png" alt-text="Terminal - HelloWorld en la barra de navegación inferior":::

1. <span data-ttu-id="3ceef-146">Presione cualquier tecla para salir de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3ceef-146">Press any key to exit the program.</span></span>

1. <span data-ttu-id="3ceef-147">Cierre ventana de terminal.</span><span class="sxs-lookup"><span data-stu-id="3ceef-147">Close the terminal window.</span></span>

## <a name="set-a-conditional-breakpoint"></a><span data-ttu-id="3ceef-148">Establecimiento de un punto de interrupción condicional</span><span class="sxs-lookup"><span data-stu-id="3ceef-148">Set a conditional breakpoint</span></span>

<span data-ttu-id="3ceef-149">El programa muestra la cadena que escribe el usuario.</span><span class="sxs-lookup"><span data-stu-id="3ceef-149">The program displays a string that the user enters.</span></span> <span data-ttu-id="3ceef-150">¿Qué sucede si el usuario no escribe nada?</span><span class="sxs-lookup"><span data-stu-id="3ceef-150">What happens if the user doesn't enter anything?</span></span> <span data-ttu-id="3ceef-151">Puede probarlo con una característica de depuración muy útil denominada *Punto de interrupción condicional*.</span><span class="sxs-lookup"><span data-stu-id="3ceef-151">You can test this with a useful debugging feature called a *conditional breakpoint*.</span></span>

1. <span data-ttu-id="3ceef-152">Haga clic pulsando <kbd>control</kbd> en el punto rojo que representa al punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="3ceef-152"><kbd>ctrl</kbd>-click on the red dot that represents the breakpoint.</span></span> <span data-ttu-id="3ceef-153">En el menú contextual, seleccione **Editar punto de interrupción**.</span><span class="sxs-lookup"><span data-stu-id="3ceef-153">In the context menu, select **Edit Breakpoint**.</span></span>

1. <span data-ttu-id="3ceef-154">En el cuadro de diálogo **Editar punto de interrupción**, escriba el código siguiente en el campo **Y se cumpla la siguiente condición** y seleccione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="3ceef-154">In the **Edit Breakpoint** dialog, enter the following code in the field that follows **And the following condition is true**, and select **Apply**.</span></span>

   ```csharp
   String.IsNullOrEmpty(name)
   ```

   :::image type="content" source="media/debugging-with-visual-studio-mac/breakpoint-settings.png" alt-text="Editor con el panel de configuración de punto de interrupción":::

   <span data-ttu-id="3ceef-156">Cada vez que se alcanza el punto de interrupción, el depurador llama al método `String.IsNullOrEmpty(name)` y se interrumpe en esta línea solo si la llamada al método devuelve `true`.</span><span class="sxs-lookup"><span data-stu-id="3ceef-156">Each time the breakpoint is hit, the debugger calls the `String.IsNullOrEmpty(name)` method, and it breaks on this line only if the method call returns `true`.</span></span>

   <span data-ttu-id="3ceef-157">En lugar de una expresión condicional, puede especificar un *número de llamadas*, que interrumpe la ejecución del programa antes de que una instrucción se ejecute un número especificado de veces.</span><span class="sxs-lookup"><span data-stu-id="3ceef-157">Instead of a conditional expression, you can specify a *hit count*, which interrupts program execution before a statement is executed a specified number of times.</span></span>

1. <span data-ttu-id="3ceef-158">Presione <kbd>⌘</kbd><kbd>↵</kbd> (<kbd>command</kbd>+<kbd>entrar</kbd>) para iniciar la depuración.</span><span class="sxs-lookup"><span data-stu-id="3ceef-158">Press <kbd>⌘</kbd><kbd>↵</kbd> (<kbd>command</kbd>+<kbd>enter</kbd>) to start debugging.</span></span>

1. <span data-ttu-id="3ceef-159">En la ventana de terminal, presione <kbd>entrar</kbd> cuando se le pida que escriba su nombre.</span><span class="sxs-lookup"><span data-stu-id="3ceef-159">In the terminal window, press <kbd>enter</kbd> when prompted to enter your name.</span></span>

   <span data-ttu-id="3ceef-160">Como se ha cumplido la condición que especificó (`name` es `null` o <xref:System.String.Empty?displayProperty=nameWithType>), la ejecución del programa se detiene cuando se alcanza el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="3ceef-160">Because the condition you specified (`name` is either `null` or <xref:System.String.Empty?displayProperty=nameWithType>) has been satisfied, program execution stops when it reaches the breakpoint.</span></span>

1. <span data-ttu-id="3ceef-161">Seleccione la ventana **Variables locales**, que muestra los valores de las variables que son locales para el método que se ejecuta actualmente.</span><span class="sxs-lookup"><span data-stu-id="3ceef-161">Select the **Locals** window, which shows the values of variables that are local to the currently executing method.</span></span> <span data-ttu-id="3ceef-162">En este caso, `Main` es el método que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="3ceef-162">In this case, `Main` is the currently executing method.</span></span> <span data-ttu-id="3ceef-163">Observe que el valor de la variable `name` es `""`; esto es, <xref:System.String.Empty?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3ceef-163">Observe that the value of the `name` variable is `""`, that is, <xref:System.String.Empty?displayProperty=nameWithType>.</span></span>

1. <span data-ttu-id="3ceef-164">También puede ver que el valor es una cadena vacía escribiendo el nombre de la variable `name` en la ventana **Inmediato** y presionando <kbd>entrar</kbd>.</span><span class="sxs-lookup"><span data-stu-id="3ceef-164">You can also see that the value is an empty string by entering the `name` variable name in the **Immediate** window and pressing <kbd>enter</kbd>.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-mac/immediate-window-output.png" alt-text="La ventana Inmediato que muestra el nombre es una cadena vacía":::

1. <span data-ttu-id="3ceef-166">Presione <kbd>⌘</kbd><kbd>↵</kbd> (<kbd>command</kbd>+<kbd>entrar</kbd>) para continuar con la depuración.</span><span class="sxs-lookup"><span data-stu-id="3ceef-166">Press <kbd>⌘</kbd><kbd>↵</kbd> (<kbd>command</kbd>+<kbd>enter</kbd>) to continue debugging.</span></span>

1. <span data-ttu-id="3ceef-167">En la ventana de terminal, presione cualquier tecla para salir del programa.</span><span class="sxs-lookup"><span data-stu-id="3ceef-167">In the terminal window, press any key to exit the program.</span></span>

1. <span data-ttu-id="3ceef-168">Cierre la ventana de terminal.</span><span class="sxs-lookup"><span data-stu-id="3ceef-168">Close the terminal window.</span></span>

1. <span data-ttu-id="3ceef-169">Para borrar el punto de interrupción, haga clic en el punto rojo en el margen izquierdo de la ventana de código.</span><span class="sxs-lookup"><span data-stu-id="3ceef-169">Clear the breakpoint by clicking on the red dot in the left margin of the code window.</span></span> <span data-ttu-id="3ceef-170">Otra manera de hacerlo es elegir **Ejecutar > Alternar punto de interrupción** con la línea de código seleccionada.</span><span class="sxs-lookup"><span data-stu-id="3ceef-170">Another way to clear a breakpoint is by choosing **Run > Toggle Breakpoint** while the line of code is selected.</span></span>

## <a name="step-through-a-program"></a><span data-ttu-id="3ceef-171">Ejecución paso a paso de un programa</span><span class="sxs-lookup"><span data-stu-id="3ceef-171">Step through a program</span></span>

<span data-ttu-id="3ceef-172">Visual Studio también le permite recorrer línea a línea un programa y supervisar su ejecución.</span><span class="sxs-lookup"><span data-stu-id="3ceef-172">Visual Studio also allows you to step line by line through a program and monitor its execution.</span></span> <span data-ttu-id="3ceef-173">Normalmente, establecería un punto de interrupción y seguiría el flujo del programa mediante una pequeña parte de su código de programa.</span><span class="sxs-lookup"><span data-stu-id="3ceef-173">Ordinarily, you'd set a breakpoint and follow program flow through a small part of your program code.</span></span> <span data-ttu-id="3ceef-174">Como este programa es pequeño, puede ejecutar paso a paso el programa entero.</span><span class="sxs-lookup"><span data-stu-id="3ceef-174">Since this program is small, you can step through the entire program.</span></span>

1. <span data-ttu-id="3ceef-175">Establezca un punto de interrupción en la llave que marca el inicio del método `Main` (presione <kbd>command</kbd>+<kbd>\\</kbd>).</span><span class="sxs-lookup"><span data-stu-id="3ceef-175">Set a breakpoint on the curly brace that marks the start of the `Main` method (press <kbd>command</kbd>+<kbd>\\</kbd>).</span></span>

1. <span data-ttu-id="3ceef-176">Presione <kbd>⌘</kbd><kbd>↵</kbd> (<kbd>command</kbd>+<kbd>entrar</kbd>) para iniciar la depuración.</span><span class="sxs-lookup"><span data-stu-id="3ceef-176">Press <kbd>⌘</kbd><kbd>↵</kbd> (<kbd>command</kbd>+<kbd>enter</kbd>) to start debugging.</span></span>

   <span data-ttu-id="3ceef-177">Visual Studio se detiene en la línea con el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="3ceef-177">Visual Studio stops on the line with the breakpoint.</span></span>

1. <span data-ttu-id="3ceef-178">Presione <kbd>⇧</kbd><kbd>⌘</kbd><kbd>I</kbd> (<kbd>mayús</kbd>+<kbd>command</kbd>+<kbd>l</kbd>) o seleccione **Ejecutar** > **Depurar paso a paso por instrucciones** para avanzar una línea.</span><span class="sxs-lookup"><span data-stu-id="3ceef-178">Press <kbd>⇧</kbd><kbd>⌘</kbd><kbd>I</kbd> (<kbd>shift</kbd>+<kbd>command</kbd>+<kbd>I</kbd>) or select **Run** > **Step Into** to advance one line.</span></span>

   <span data-ttu-id="3ceef-179">Visual Studio resalta y muestra una flecha junto a la siguiente línea de ejecución.</span><span class="sxs-lookup"><span data-stu-id="3ceef-179">Visual Studio highlights and displays an arrow beside the next line of execution.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-mac/step-into-method.png" alt-text="Método depurar paso a paso por instrucciones de Visual Studio":::

   <span data-ttu-id="3ceef-181">En este punto, la ventana **Variables locales** muestra que la matriz `args` está vacía, y `name` y `date` tienen valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="3ceef-181">At this point, the **Locals** window shows that the `args` array is empty, and `name` and `date` have default values.</span></span> <span data-ttu-id="3ceef-182">Además, Visual Studio ha abierto una ventana de consola en blanco.</span><span class="sxs-lookup"><span data-stu-id="3ceef-182">In addition, Visual Studio has opened a blank terminal.</span></span>

1. <span data-ttu-id="3ceef-183">Presione <kbd>⇧</kbd><kbd>⌘</kbd><kbd>I</kbd> (<kbd>mayús</kbd>+<kbd>command</kbd>+<kbd>I</kbd>).</span><span class="sxs-lookup"><span data-stu-id="3ceef-183">Press <kbd>⇧</kbd><kbd>⌘</kbd><kbd>I</kbd> (<kbd>shift</kbd>+<kbd>command</kbd>+<kbd>I</kbd>).</span></span>

   <span data-ttu-id="3ceef-184">Visual Studio resalta la instrucción que incluye la asignación de variables `name`.</span><span class="sxs-lookup"><span data-stu-id="3ceef-184">Visual Studio highlights the statement that includes the `name` variable assignment.</span></span> <span data-ttu-id="3ceef-185">La ventana **Variables locales** muestra que `name` es `null`, y terminal muestra la cadena "What is your name?" (¿Cómo te llamas?).</span><span class="sxs-lookup"><span data-stu-id="3ceef-185">The **Locals** window shows that `name` is `null`, and the terminal displays the string "What is your name?".</span></span>

1. <span data-ttu-id="3ceef-186">Para responder a la solicitud, escriba una cadena en la ventana de consola y presione <kbd>entrar</kbd>.</span><span class="sxs-lookup"><span data-stu-id="3ceef-186">Respond to the prompt by entering a string in the console window and pressing <kbd>enter</kbd>.</span></span>

1. <span data-ttu-id="3ceef-187">Presione <kbd>⇧</kbd><kbd>⌘</kbd><kbd>I</kbd> (<kbd>mayús</kbd>+<kbd>command</kbd>+<kbd>I</kbd>).</span><span class="sxs-lookup"><span data-stu-id="3ceef-187">Press <kbd>⇧</kbd><kbd>⌘</kbd><kbd>I</kbd> (<kbd>shift</kbd>+<kbd>command</kbd>+<kbd>I</kbd>).</span></span>

   <span data-ttu-id="3ceef-188">Visual Studio resalta la instrucción que incluye la asignación de variables `date`.</span><span class="sxs-lookup"><span data-stu-id="3ceef-188">Visual Studio highlights the statement that includes the `date` variable assignment.</span></span> <span data-ttu-id="3ceef-189">La ventana **Variables locales** muestra el valor devuelto por la llamada al método <xref:System.Console.ReadLine%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3ceef-189">The **Locals** window shows the value returned by the call to the <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="3ceef-190">En el terminal se muestra la cadena que escribió en el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="3ceef-190">The terminal displays the string you entered at the prompt.</span></span>

1. <span data-ttu-id="3ceef-191">Presione <kbd>⇧</kbd><kbd>⌘</kbd><kbd>I</kbd> (<kbd>mayús</kbd>+<kbd>command</kbd>+<kbd>I</kbd>).</span><span class="sxs-lookup"><span data-stu-id="3ceef-191">Press <kbd>⇧</kbd><kbd>⌘</kbd><kbd>I</kbd> (<kbd>shift</kbd>+<kbd>command</kbd>+<kbd>I</kbd>).</span></span>

   <span data-ttu-id="3ceef-192">La ventana **Variables locales** muestra el valor de la variable `date` tras la asignación desde la propiedad <xref:System.DateTime.Now?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3ceef-192">The **Locals** window shows the value of the `date` variable after the assignment from the <xref:System.DateTime.Now?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="3ceef-193">El terminal no se modifica.</span><span class="sxs-lookup"><span data-stu-id="3ceef-193">The terminal is unchanged.</span></span>

1. <span data-ttu-id="3ceef-194">Presione <kbd>⇧</kbd><kbd>⌘</kbd><kbd>I</kbd> (<kbd>mayús</kbd>+<kbd>command</kbd>+<kbd>I</kbd>).</span><span class="sxs-lookup"><span data-stu-id="3ceef-194">Press <kbd>⇧</kbd><kbd>⌘</kbd><kbd>I</kbd> (<kbd>shift</kbd>+<kbd>command</kbd>+<kbd>I</kbd>).</span></span>

   <span data-ttu-id="3ceef-195">Visual Studio llama al método <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3ceef-195">Visual Studio calls the <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="3ceef-196">El terminal muestra la cadena con formato.</span><span class="sxs-lookup"><span data-stu-id="3ceef-196">The terminal displays the formatted string.</span></span>

1. <span data-ttu-id="3ceef-197">Presione <kbd>⇧</kbd><kbd>⌘</kbd><kbd>U</kbd> (<kbd>mayús</kbd>+<kbd>command</kbd>+<kbd>U</kbd>) o seleccione **Ejecutar** > **Paso a paso para salir**.</span><span class="sxs-lookup"><span data-stu-id="3ceef-197">Press <kbd>⇧</kbd><kbd>⌘</kbd><kbd>U</kbd> (<kbd>shift</kbd>+<kbd>command</kbd>+<kbd>U</kbd>) or select **Run** > **Step Out**.</span></span>

   <span data-ttu-id="3ceef-198">El terminal muestra un mensaje y espera a que presione una tecla.</span><span class="sxs-lookup"><span data-stu-id="3ceef-198">The terminal displays a message and waits for you to press a key.</span></span>

1. <span data-ttu-id="3ceef-199">Presione cualquier tecla para salir de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3ceef-199">Press any key to exit the program.</span></span>

## <a name="use-release-build-configuration"></a><span data-ttu-id="3ceef-200">Uso de la configuración de compilación de versión</span><span class="sxs-lookup"><span data-stu-id="3ceef-200">Use Release build configuration</span></span>

<span data-ttu-id="3ceef-201">Una vez que ha probado la versión de depuración de la aplicación, también debe compilar y probar la versión de lanzamiento.</span><span class="sxs-lookup"><span data-stu-id="3ceef-201">Once you've tested the Debug version of your application, you should also compile and test the Release version.</span></span> <span data-ttu-id="3ceef-202">La versión de lanzamiento incorpora optimizaciones del compilador que afectan negativamente al comportamiento de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="3ceef-202">The Release version incorporates compiler optimizations that can negatively affect the behavior of an application.</span></span> <span data-ttu-id="3ceef-203">Por ejemplo, las optimizaciones del compilador que están diseñadas para mejorar el rendimiento pueden crear condiciones de carrera en aplicaciones multiproceso.</span><span class="sxs-lookup"><span data-stu-id="3ceef-203">For example, compiler optimizations that are designed to improve performance can create race conditions in multithreaded applications.</span></span>

<span data-ttu-id="3ceef-204">Para compilar y probar la configuración de versión de la aplicación de consola, realice los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="3ceef-204">To build and test the Release version of the console application, do the following steps:</span></span>

1. <span data-ttu-id="3ceef-205">Cambie la configuración de compilación en la barra de herramientas de **Depurar** a **Versión**.</span><span class="sxs-lookup"><span data-stu-id="3ceef-205">Change the build configuration on the toolbar from **Debug** to **Release**.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-mac/visual-studio-toolbar-release.png" alt-text="Barra de herramientas predeterminada de Visual Studio con Depuración resaltado":::

1. <span data-ttu-id="3ceef-207">Presione <kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>opción</kbd>+<kbd>command</kbd>+<kbd>entrar</kbd>) para ejecutar sin depurar.</span><span class="sxs-lookup"><span data-stu-id="3ceef-207">Press <kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>option</kbd>+<kbd>command</kbd>+<kbd>enter</kbd>) to run without debugging.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3ceef-208">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="3ceef-208">Next steps</span></span>

<span data-ttu-id="3ceef-209">En este tutorial, ha usado las herramientas de depuración de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3ceef-209">In this tutorial, you used Visual Studio debugging tools.</span></span> <span data-ttu-id="3ceef-210">En el siguiente tutorial, publicará una versión de la aplicación que se puede implementar.</span><span class="sxs-lookup"><span data-stu-id="3ceef-210">In the next tutorial, you publish a deployable version of the app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="3ceef-211">Publicación de una aplicación de consola de .NET Core con Visual Studio para Mac</span><span class="sxs-lookup"><span data-stu-id="3ceef-211">Publish a .NET Core console application with Visual Studio for Mac</span></span>](publishing-with-visual-studio-mac.md)
