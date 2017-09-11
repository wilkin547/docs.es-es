---
title: "Compilación de una aplicación Hola a todos con .NET Core y Visual Basic en Visual Studio 2017"
description: "Obtenga información sobre cómo crear una sencilla aplicación de consola .NET Core con Visual Basic mediante Visual Studio 2017."
keywords: ".NET Core, aplicación de consola .NET Core, Visual Studio 2017"
author: rpetrusha
ms.author: ronpet
ms.date: 08/07/2017
ms.topic: article
ms.prod: .net-core
ms.technology: devlang-vb
ms.devlang: vb
ms.translationtype: HT
ms.sourcegitcommit: e0271ba3392ce8861dc916714af8c16d4581ce4f
ms.openlocfilehash: 8eeb4cc5be716ede4397189429ed882dff4d9e91
ms.contentlocale: es-es
ms.lasthandoff: 08/13/2017

---

# <a name="build-a-visual-basic-hello-world-application-with-net-core-in-visual-studio-2017"></a><span data-ttu-id="a9fba-104">Compilación de una aplicación Hola a todos en Visual Basic con .NET Core en Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="a9fba-104">Build a Visual Basic Hello World application with .NET Core in Visual Studio 2017</span></span>

<span data-ttu-id="a9fba-105">En este tema se proporciona una introducción detallada para compilar, depurar y publicar una sencilla aplicación de consola .NET Core con Visual Basic en Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="a9fba-105">This topic provides a step-by-step introduction to building, debugging, and publishing a simple .NET Core console application using Visual Basic in Visual Studio 2017.</span></span> <span data-ttu-id="a9fba-106">Visual Studio 2017 proporciona un entorno de desarrollo completo para la compilación de aplicaciones .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a9fba-106">Visual Studio 2017 provides a full-featured development environment for building .NET Core applications.</span></span> <span data-ttu-id="a9fba-107">Siempre que la aplicación no tenga dependencias específicas de la plataforma, la aplicación puede ejecutarse en cualquier plataforma que tenga como destino .NET Core y en cualquier sistema que tenga instalado .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a9fba-107">As long as the application doesn't have platform-specific dependencies, the application can run on any platform that .NET Core targets and on any system that has .NET Core installed.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a9fba-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a9fba-108">Prerequisites</span></span>

<span data-ttu-id="a9fba-109">[Visual Studio de 2017](https://www.visualstudio.com/downloads/) con la carga de trabajo "Desarrollo multiplataforma de .NET Core" instalada.</span><span class="sxs-lookup"><span data-stu-id="a9fba-109">[Visual Studio 2017](https://www.visualstudio.com/downloads/) with the ".NET Core cross-platform development" workload installed.</span></span> <span data-ttu-id="a9fba-110">Puede desarrollar su aplicación con .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="a9fba-110">You can develop your app with .NET Core 2.0.</span></span>

<span data-ttu-id="a9fba-111">Para obtener más información, vea [Requisitos previos para .NET Core en Windows](../../core/windows-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="a9fba-111">For more information, see [Prerequisites for .NET Core on Windows](../../core/windows-prerequisites.md).</span></span>

## <a name="a-simple-hello-world-application"></a><span data-ttu-id="a9fba-112">Una aplicación Hola mundo sencilla</span><span class="sxs-lookup"><span data-stu-id="a9fba-112">A simple Hello World application</span></span>

<span data-ttu-id="a9fba-113">Comience creando una aplicación de consola "Hola mundo" sencilla.</span><span class="sxs-lookup"><span data-stu-id="a9fba-113">Begin by creating a simple "Hello World" console application.</span></span> <span data-ttu-id="a9fba-114">Siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="a9fba-114">Follow these steps:</span></span>

1. <span data-ttu-id="a9fba-115">Inicie Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="a9fba-115">Launch Visual Studio 2017.</span></span> <span data-ttu-id="a9fba-116">Seleccione **Archivo** > **Nuevo** > **Proyecto** de la barra de menús.</span><span class="sxs-lookup"><span data-stu-id="a9fba-116">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="a9fba-117">En el cuadro de diálogo *Nuevo proyecto**, seleccione el nodo **Visual Basic** seguido del nodo **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="a9fba-117">In the *New Project** dialog, select the **Visual Basic** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="a9fba-118">Después, seleccione la plantilla del proyecto **Aplicación de consola (.NET Core)**.</span><span class="sxs-lookup"><span data-stu-id="a9fba-118">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="a9fba-119">En el cuadro de texto **Nombre**, escriba "Hola mundo".</span><span class="sxs-lookup"><span data-stu-id="a9fba-119">In the **Name** text box, type "HelloWorld".</span></span> <span data-ttu-id="a9fba-120">Seleccione el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a9fba-120">Select the **OK** button.</span></span>

   ![Cuadro de diálogo Nuevo proyecto con la aplicación de consola seleccionada](./media/vb-with-visual-studio/new-project.png)
   
1. <span data-ttu-id="a9fba-122">Visual Studio usa la plantilla para crear el proyecto.</span><span class="sxs-lookup"><span data-stu-id="a9fba-122">Visual Studio uses the template to create your project.</span></span> <span data-ttu-id="a9fba-123">La plantilla de aplicación de consola de Visual Basic para .NET Core define automáticamente una clase, `Program`, con un único método, `Main`, que adopta una matriz <xref:System.String> como argumento.</span><span class="sxs-lookup"><span data-stu-id="a9fba-123">The Visual Basic Console Application template for .NET Core automatically defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument.</span></span> <span data-ttu-id="a9fba-124">`Main` es el punto de entrada de la aplicación, el método que se llama automáticamente mediante el tiempo de ejecución cuando inicia la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a9fba-124">`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application.</span></span> <span data-ttu-id="a9fba-125">Los argumentos de línea de comandos proporcionados cuando se inicia la aplicación están disponibles en la matriz *args*.</span><span class="sxs-lookup"><span data-stu-id="a9fba-125">Any command-line arguments supplied when the application is launched are available in the *args* array.</span></span>

   ![Visual Studio y el nuevo proyecto Hola mundo](./media/vb-with-visual-studio/devenv.png)

   <span data-ttu-id="a9fba-127">La plantilla crea una aplicación "Hola mundo" sencilla.</span><span class="sxs-lookup"><span data-stu-id="a9fba-127">The template creates a simple "Hello World" application.</span></span> <span data-ttu-id="a9fba-128">Llama al método <xref:System.Console.WriteLine(System.String)?displayProperty=fullName> para mostrar la cadena literal "Hola mundo"</span><span class="sxs-lookup"><span data-stu-id="a9fba-128">It calls the <xref:System.Console.WriteLine(System.String)?displayProperty=fullName> method to display the literal string "Hello World!"</span></span> <span data-ttu-id="a9fba-129">en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="a9fba-129">in the console window.</span></span> <span data-ttu-id="a9fba-130">Al seleccionar el botón **HelloWorld** con la flecha verde en la barra de herramientas, puede ejecutar el programa en modo de depuración.</span><span class="sxs-lookup"><span data-stu-id="a9fba-130">By selecting the **HelloWorld** button with the green arrow on the toolbar, you can run the program in Debug mode.</span></span> <span data-ttu-id="a9fba-131">Si lo hace, la ventana de la consola se mostrará durante poco tiempo antes de cerrarse.</span><span class="sxs-lookup"><span data-stu-id="a9fba-131">If you do, the console window is visible for only a brief time interval before it closes.</span></span> <span data-ttu-id="a9fba-132">Esto ocurre porque el método `Main` finaliza y la aplicación termina en cuanto se ejecuta la única instrucción en el método `Main`.</span><span class="sxs-lookup"><span data-stu-id="a9fba-132">This occurs because the `Main` method terminates and the application ends as soon as the single statement in the `Main` method executes.</span></span>

1. <span data-ttu-id="a9fba-133">Para que la aplicación se pause antes de que se cierre la ventana de la consola, agregue el siguiente código inmediatamente después de la llamada al método <xref:System.Console.WriteLine(System.String)?displayProperty=fullName>:</span><span class="sxs-lookup"><span data-stu-id="a9fba-133">To cause the application to pause before it closes the console window, add the following code immediately after the call to the <xref:System.Console.WriteLine(System.String)?displayProperty=fullName> method:</span></span>

   ```vb
   Console.Write("Press any key to continue...")
   Console.ReadKey(true)
   ```
   <span data-ttu-id="a9fba-134">Este código pide al usuario que presione cualquier tecla y, a continuación, detiene el programa hasta que se presiona una tecla.</span><span class="sxs-lookup"><span data-stu-id="a9fba-134">This code prompts the user to press any key and then pauses the program until a key is pressed.</span></span>

1. <span data-ttu-id="a9fba-135">En la barra de menús, seleccione **Compilar** > **Compilar solución**.</span><span class="sxs-lookup"><span data-stu-id="a9fba-135">On the menu bar, select **Build** > **Build Solution**.</span></span> <span data-ttu-id="a9fba-136">De esta forma, el programa se compila en un lenguaje intermedio (IL) que se convierte en código binario mediante un compilador Just-In-Time (JIT).</span><span class="sxs-lookup"><span data-stu-id="a9fba-136">This compiles your program into an intermediate language (IL) that's converted into binary code by a just-in-time (JIT) compiler.</span></span>

1. <span data-ttu-id="a9fba-137">Seleccione el botón **HelloWorld** con la flecha verde en la barra de herramientas para ejecutar el programa.</span><span class="sxs-lookup"><span data-stu-id="a9fba-137">Run the program by selecting the **HelloWorld** button with the green arrow on the toolbar.</span></span>

   ![Ventana de la consola que muestra Hola mundo Presione cualquier tecla para continuar](./media/with-visual-studio/helloworld1.png)

1. <span data-ttu-id="a9fba-139">Presione cualquier tecla para cerrar la ventana de consola.</span><span class="sxs-lookup"><span data-stu-id="a9fba-139">Press any key to close the console window.</span></span>

## <a name="enhancing-the-hello-world-application"></a><span data-ttu-id="a9fba-140">Mejorar la aplicación Hola mundo</span><span class="sxs-lookup"><span data-stu-id="a9fba-140">Enhancing the Hello World application</span></span>

<span data-ttu-id="a9fba-141">Mejore su aplicación para pedir su nombre al usuario y mostrarlo junto con la fecha y la hora.</span><span class="sxs-lookup"><span data-stu-id="a9fba-141">Enhance your application to prompt the user for his or her name and to display it along with the date and time.</span></span> <span data-ttu-id="a9fba-142">Para modificar y probar el programa, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a9fba-142">To modify and test the program, do the following:</span></span>

1. <span data-ttu-id="a9fba-143">Escriba el siguiente código de Visual Basic en la ventana de código inmediatamente después del corchete de apertura que sigue a la línea `Sub Main(args As String())` y antes del primer corchete de cierre:</span><span class="sxs-lookup"><span data-stu-id="a9fba-143">Enter the following Visual Basic code in the code window immediately after the opening bracket that follows the `Sub Main(args As String())` line and before the first closing bracket:</span></span>

   <span data-ttu-id="a9fba-144">[!code-vb[GettingStarted#1](../../../samples/snippets/core/tutorials/vb-with-visual-studio/helloworld.vb#1)]</span><span class="sxs-lookup"><span data-stu-id="a9fba-144">[!code-vb[GettingStarted#1](../../../samples/snippets/core/tutorials/vb-with-visual-studio/helloworld.vb#1)]</span></span>

   <span data-ttu-id="a9fba-145">Este código reemplaza las instrucciones <xref:System.Console.WriteLine%2A?displayProperty=fullName>, <xref:System.Console.Write%2A?displayProperty=fullName> y <xref:System.Console.ReadKey%2A?displayProperty=fullName> existentes.</span><span class="sxs-lookup"><span data-stu-id="a9fba-145">This code replaces the existing <xref:System.Console.WriteLine%2A?displayProperty=fullName>, <xref:System.Console.Write%2A?displayProperty=fullName>, and <xref:System.Console.ReadKey%2A?displayProperty=fullName> statements.</span></span>

   ![Archivo del programa Visual Studio con el método Main actualizado](./media/vb-with-visual-studio/codewindow.png)

   <span data-ttu-id="a9fba-147">Este código muestra "What is your name?"</span><span class="sxs-lookup"><span data-stu-id="a9fba-147">This code displays "What is your name?"</span></span> <span data-ttu-id="a9fba-148">en la ventana de la consola y espera a que el usuario escriba una cadena seguida de la tecla Entrar.</span><span class="sxs-lookup"><span data-stu-id="a9fba-148">in the console window and waits until the user enters a string followed by the Enter key.</span></span> <span data-ttu-id="a9fba-149">Almacena esta cadena en una variable denominada `name`.</span><span class="sxs-lookup"><span data-stu-id="a9fba-149">It stores this string into a variable named `name`.</span></span> <span data-ttu-id="a9fba-150">También recupera el valor de la propiedad <xref:System.DateTime.Now?displayProperty=fullName>, que contiene la hora local actual, y lo asigna a una variable denominada `currentDate`.</span><span class="sxs-lookup"><span data-stu-id="a9fba-150">It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=fullName> property, which contains the current local time, and assigns it to a variable named `currentDate`.</span></span> <span data-ttu-id="a9fba-151">Por último, usa una [cadena interpolada](../../csharp/language-reference/keywords/interpolated-strings.md) para mostrar estos valores en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="a9fba-151">Finally, it uses an [interpolated string](../../csharp/language-reference/keywords/interpolated-strings.md) to display these values in the console window.</span></span>

1. <span data-ttu-id="a9fba-152">Compile el programa; para ello, seleccione **Generar** > **Compilar solución**.</span><span class="sxs-lookup"><span data-stu-id="a9fba-152">Compile the program by choosing **Build** > **Build Solution**.</span></span>

1. <span data-ttu-id="a9fba-153">Ejecute el programa en modo de depuración en Visual Studio; para ello, seleccione la flecha verde en la barra de herramientas, presione F5 o seleccione el elemento de menú **Depurar** > **Iniciar depuración**.</span><span class="sxs-lookup"><span data-stu-id="a9fba-153">Run the program in Debug mode in Visual Studio by selecting the green arrow on the toolbar, pressing F5, or choosing the **Debug** > **Start Debugging** menu item.</span></span> <span data-ttu-id="a9fba-154">Responda a la solicitud escribiendo un nombre y presionando la tecla Entrar.</span><span class="sxs-lookup"><span data-stu-id="a9fba-154">Respond to the prompt by entering a name and pressing the Enter key.</span></span>

   ![Ventana de la consola con el resultado del programa modificado](./media/with-visual-studio/helloworld2.png)

1. <span data-ttu-id="a9fba-156">Presione cualquier tecla para cerrar la ventana de consola.</span><span class="sxs-lookup"><span data-stu-id="a9fba-156">Press any key to close the console window.</span></span>

<span data-ttu-id="a9fba-157">Ha creado y ejecutado la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a9fba-157">You've created and run your application.</span></span> <span data-ttu-id="a9fba-158">Para desarrollar una aplicación profesional, realice algunos pasos adicionales para preparar el lanzamiento de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="a9fba-158">To develop a professional application, take some additional steps to make your application ready for release:</span></span>

- <span data-ttu-id="a9fba-159">Para obtener información sobre la depuración de la aplicación, vea [Depuración de la aplicación Hola a todos en C# con Visual Studio 2017](debugging-with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="a9fba-159">For information on debugging your application, see [Debugging your C# Hello World application with Visual Studio 2017](debugging-with-visual-studio.md).</span></span>

- <span data-ttu-id="a9fba-160">Para obtener información sobre el desarrollo y publicación de una versión de distribución de la aplicación, vea [Publicación de la aplicación Hola a todos en C# con Visual Studio 2017](publishing-with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="a9fba-160">For information on developing and publishing a distributable version of your application, see [Publishing your C# Hello World application with Visual Studio 2017](publishing-with-visual-studio.md).</span></span>

<!--
## Related topics

Instead of a console application, you can also build a class library with .NET Core and Visual Studio 2017. For a step-by-step introduction, see [Building a class library with C# and .NET Core in Visual Studio 2017](library-with-visual-studio.md).

You can also develop a .NET Core console app on Mac, Linux, and Windows by using [Visual Studio Code](https://code.visualstudio.com/), a downloadable code editor. For a step-by-step tutorial, see [Getting Started with Visual Studio Code](with-visual-studio-code.md). -->

