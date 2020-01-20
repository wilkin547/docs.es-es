---
title: Creación de una aplicación Hola mundo de C# con .NET Core en Visual Studio
description: Obtenga información sobre cómo crear su primera aplicación de consola .NET Core con C# o Visual Basic mediante Visual Studio 2017.
author: BillWagner
ms.author: wiwagn
ms.date: 12/09/2019
ms.custom: vs-dotnet
ms.openlocfilehash: ba996e4add1cfe44681154b00a6530b1f3e70b37
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714000"
---
# <a name="tutorial-create-your-first-net-core-console-application-in-visual-studio-2019"></a><span data-ttu-id="21978-103">Tutorial: Creación de su primera aplicación de consola con .NET Core en Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="21978-103">Tutorial: Create your first .NET Core console application in Visual Studio 2019</span></span>

<span data-ttu-id="21978-104">En este artículo se proporciona una introducción paso a paso para crear y ejecutar una aplicación de consola Hola mundo con .NET Core en Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="21978-104">This article provides a step-by-step introduction to create and run a Hello World .NET Core console application in Visual Studio 2019.</span></span> <span data-ttu-id="21978-105">Tradicionalmente, se usa una aplicación Hola mundo para introducir a los principiantes en un nuevo lenguaje de programación.</span><span class="sxs-lookup"><span data-stu-id="21978-105">A Hello World application is traditionally used to introduce beginners to a new programming language.</span></span> <span data-ttu-id="21978-106">En este programa simplemente muestra la frase "Hola mundo"</span><span class="sxs-lookup"><span data-stu-id="21978-106">This program simply displays the phrase "Hello World!"</span></span> <span data-ttu-id="21978-107">en la pantalla.</span><span class="sxs-lookup"><span data-stu-id="21978-107">on the screen.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="21978-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="21978-108">Prerequisites</span></span>

- <span data-ttu-id="21978-109">[Visual Studio 2019, versión 16.4 o posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) con la carga de trabajo **Desarrollo multiplataforma de .NET Core** instalada</span><span class="sxs-lookup"><span data-stu-id="21978-109">[Visual Studio 2019 version 16.4 or a later version](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the **.NET Core cross-platform development** workload installed.</span></span> <span data-ttu-id="21978-110">El SDK de .NET Core 3.1 se instala automáticamente al seleccionar esta carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="21978-110">.NET Core 3.1 SDK is automatically installed when you select this workload.</span></span>

<span data-ttu-id="21978-111">Para más información, consulte la sección [Instalación con Visual Studio](../install/sdk.md?pivots=os-windows#install-with-visual-studio) del artículo [Instalación del SDK de .NET Core](../install/sdk.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="21978-111">For more information, see the [Install with Visual Studio](../install/sdk.md?pivots=os-windows#install-with-visual-studio) section on the [Install the .NET Core SDK](../install/sdk.md?pivots=os-windows) article.</span></span>

## <a name="create-the-app"></a><span data-ttu-id="21978-112">Creación de la aplicación</span><span class="sxs-lookup"><span data-stu-id="21978-112">Create the app</span></span>

<span data-ttu-id="21978-113">Las instrucciones siguientes crean una sencilla aplicación de consola de Hola mundo:</span><span class="sxs-lookup"><span data-stu-id="21978-113">The following instructions create a simple Hello World console application:</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="ctabcsharp"></a>[<span data-ttu-id="21978-114">C#</span><span class="sxs-lookup"><span data-stu-id="21978-114">C#</span></span>](#tab/csharp)

1. <span data-ttu-id="21978-115">Abra Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="21978-115">Open Visual Studio 2019.</span></span>

1. <span data-ttu-id="21978-116">Cree un nuevo proyecto de aplicación de consola de .Net Core en C# denominado "HelloWorld".</span><span class="sxs-lookup"><span data-stu-id="21978-116">Create a new C# .NET Core console app project named "HelloWorld".</span></span>

   1. <span data-ttu-id="21978-117">En la ventana de inicio, elija **Crear un proyecto nuevo**.</span><span class="sxs-lookup"><span data-stu-id="21978-117">On the start window, choose **Create a new project**.</span></span>

      ![Botón Crear un proyecto seleccionado en la ventana de inicio de Visual Studio](./media/with-visual-studio/start-window.png)

   1. <span data-ttu-id="21978-119">En la página **Crear un proyecto**, escriba **consola** en el cuadro de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="21978-119">On the **Create a new project** page, enter **console** in the search box.</span></span> <span data-ttu-id="21978-120">Después, elija **C#** en la lista de lenguajes y, luego, **Todas las plataformas** en la lista de plataformas.</span><span class="sxs-lookup"><span data-stu-id="21978-120">Next, choose **C#** from the Language list, and then choose **All platforms** from the Platform list.</span></span> <span data-ttu-id="21978-121">Elija la plantilla **Aplicación de consola (.NET Core)** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="21978-121">Choose the **Console App (.NET Core)** template, and then choose **Next**.</span></span>

      ![Creación de una nueva ventana de proyecto con filtros seleccionados](./media/with-visual-studio/create-new-project.png)

      > [!TIP]
      > <span data-ttu-id="21978-123">Si no ve las plantillas de .NET Core, es probable que falte la carga de trabajo necesaria instalada.</span><span class="sxs-lookup"><span data-stu-id="21978-123">If you don't see the .NET Core templates, you're probably missing the required workload installed.</span></span> <span data-ttu-id="21978-124">En el mensaje **¿No encuentra lo que busca?** , elija el vínculo **Instalar más herramientas y características**.</span><span class="sxs-lookup"><span data-stu-id="21978-124">Under the **Not finding what you're looking for?** message, choose the **Install more tools and features** link.</span></span> <span data-ttu-id="21978-125">Se abre el Instalador de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="21978-125">The Visual Studio Installer opens.</span></span> <span data-ttu-id="21978-126">Asegúrese de que tiene instalada la carga de trabajo **Desarrollo multiplataforma de .NET Core**.</span><span class="sxs-lookup"><span data-stu-id="21978-126">Make sure you have the **.NET Core cross-platform development** workload installed.</span></span>

   1. <span data-ttu-id="21978-127">En la página **Configurar el nuevo proyecto**, escriba **HelloWorld** en el cuadro **Nombre del proyecto**.</span><span class="sxs-lookup"><span data-stu-id="21978-127">On the **Configure your new project** page,  enter **HelloWorld** in the **Project name** box.</span></span> <span data-ttu-id="21978-128">Luego, elija **Crear**.</span><span class="sxs-lookup"><span data-stu-id="21978-128">Then, choose **Create**.</span></span>

      ![Configuración de la ventana de nuevo proyecto con los campos de nombre de proyecto, ubicación y nombre de la solución](./media/with-visual-studio/configure-new-project.png)

   <span data-ttu-id="21978-130">La plantilla de aplicación de consola de C# para .NET Core define automáticamente una clase, `Program`, con un único método, `Main`, que adopta una matriz <xref:System.String> como argumento.</span><span class="sxs-lookup"><span data-stu-id="21978-130">The C# Console Application template for .NET Core automatically defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument.</span></span> <span data-ttu-id="21978-131">`Main` es el punto de entrada de la aplicación, el método que se llama automáticamente mediante el tiempo de ejecución cuando inicia la aplicación.</span><span class="sxs-lookup"><span data-stu-id="21978-131">`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application.</span></span> <span data-ttu-id="21978-132">Los argumentos de línea de comandos proporcionados cuando se inicia la aplicación están disponibles en la matriz *args*.</span><span class="sxs-lookup"><span data-stu-id="21978-132">Any command-line arguments supplied when the application is launched are available in the *args* array.</span></span>

   ![Visual Studio y el nuevo proyecto Hola mundo](./media/with-visual-studio/visual-studio-main-window.png)

# <a name="visual-basictabvb"></a>[<span data-ttu-id="21978-134">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="21978-134">Visual Basic</span></span>](#tab/vb)

1. <span data-ttu-id="21978-135">Abra Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="21978-135">Open Visual Studio 2019.</span></span>

1. <span data-ttu-id="21978-136">Cree un nuevo proyecto de aplicación de consola de .NET Core con Visual Basic denominado "HelloWorld".</span><span class="sxs-lookup"><span data-stu-id="21978-136">Create a new Visual Basic .NET Core console app project named "HelloWorld".</span></span>

   1. <span data-ttu-id="21978-137">En la ventana de inicio, elija **Crear un proyecto nuevo**.</span><span class="sxs-lookup"><span data-stu-id="21978-137">On the start window, choose **Create a new project**.</span></span>

      ![Botón Crear un proyecto seleccionado en la ventana de inicio de Visual Studio](./media/with-visual-studio/start-window.png)

   1. <span data-ttu-id="21978-139">En la página **Crear un proyecto**, escriba **consola** en el cuadro de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="21978-139">On the **Create a new project** page, enter **console** in the search box.</span></span> <span data-ttu-id="21978-140">Después, elija **Visual Basic** en la lista de lenguajes y luego, **Todas las plataformas** en la lista de plataformas.</span><span class="sxs-lookup"><span data-stu-id="21978-140">Next, choose **Visual Basic** from the Language list, and then choose **All platforms** from the Platform list.</span></span> <span data-ttu-id="21978-141">Elija la plantilla **Aplicación de consola (.NET Core)** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="21978-141">Choose the **Console App (.NET Core)** template, and then choose **Next**.</span></span>

      ![Elija la plantilla Visual Basic para la Aplicación de consola (.NET Framework).](./media/with-visual-studio/vb/create-new-project.png)

      > [!TIP]
      > <span data-ttu-id="21978-143">Si no ve las plantillas de .NET Core, es probable que falte la carga de trabajo necesaria instalada.</span><span class="sxs-lookup"><span data-stu-id="21978-143">If you don't see the .NET Core templates, you're probably missing the required workload installed.</span></span> <span data-ttu-id="21978-144">En el mensaje **¿No encuentra lo que busca?** , elija el vínculo **Instalar más herramientas y características**.</span><span class="sxs-lookup"><span data-stu-id="21978-144">Under the **Not finding what you're looking for?** message, choose the **Install more tools and features** link.</span></span> <span data-ttu-id="21978-145">Se abre el Instalador de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="21978-145">The Visual Studio Installer opens.</span></span> <span data-ttu-id="21978-146">Asegúrese de que tiene instalada la carga de trabajo **Desarrollo multiplataforma de .NET Core**.</span><span class="sxs-lookup"><span data-stu-id="21978-146">Make sure you have the **.NET Core cross-platform development** workload installed.</span></span>

   1. <span data-ttu-id="21978-147">En la página **Configurar el nuevo proyecto**, escriba **HelloWorld** en el cuadro **Nombre del proyecto**.</span><span class="sxs-lookup"><span data-stu-id="21978-147">On the **Configure your new project** page,  enter **HelloWorld** in the **Project name** box.</span></span> <span data-ttu-id="21978-148">Luego, elija **Crear**.</span><span class="sxs-lookup"><span data-stu-id="21978-148">Then, choose **Create**.</span></span>

   <span data-ttu-id="21978-149">La plantilla de aplicación de consola para .NET Core define automáticamente una clase, `Program`, con un único método, `Main`, que adopta una matriz <xref:System.String> como argumento.</span><span class="sxs-lookup"><span data-stu-id="21978-149">The console app template for .NET Core automatically defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument.</span></span> <span data-ttu-id="21978-150">`Main` es el punto de entrada de la aplicación, el método que se llama automáticamente mediante el tiempo de ejecución cuando inicia la aplicación.</span><span class="sxs-lookup"><span data-stu-id="21978-150">`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application.</span></span> <span data-ttu-id="21978-151">Los argumentos de línea de comandos proporcionados cuando se inicia la aplicación están disponibles en el parámetro `args`.</span><span class="sxs-lookup"><span data-stu-id="21978-151">Any command-line arguments supplied when the application is launched are available in the `args` parameter.</span></span>

   ![Visual Studio y el nuevo proyecto Hola mundo](./media/with-visual-studio/vb/visual-studio-main-window.png)

---

   <span data-ttu-id="21978-153">La plantilla crea una aplicación "Hola mundo" sencilla.</span><span class="sxs-lookup"><span data-stu-id="21978-153">The template creates a simple "Hello World" application.</span></span> <span data-ttu-id="21978-154">Llama al método <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> para mostrar la cadena literal "Hola mundo"</span><span class="sxs-lookup"><span data-stu-id="21978-154">It calls the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method to display the literal string "Hello World!"</span></span> <span data-ttu-id="21978-155">en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="21978-155">in the console window.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="21978-156">Ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="21978-156">Run the app</span></span>

1. <span data-ttu-id="21978-157">Para ejecutar el programa, elija **HelloWorld** en la barra de herramientas o presione **F5**.</span><span class="sxs-lookup"><span data-stu-id="21978-157">To run the program, choose **HelloWorld** on the toolbar, or press **F5**.</span></span>

   ![Barra de herramientas de Visual Studio con el botón Ejecutar HelloWorld seleccionado](./media/with-visual-studio/run-program.png)

   <span data-ttu-id="21978-159">Se abre la ventana de la consola con el texto "Hello World"</span><span class="sxs-lookup"><span data-stu-id="21978-159">A console window opens with the text "Hello World!"</span></span> <span data-ttu-id="21978-160">impreso en la pantalla y parte de la información de depuración de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="21978-160">printed on the screen and some Visual Studio debug information.</span></span>

   ![Ventana de la consola que muestra Hola mundo Presione cualquier tecla para continuar](./media/with-visual-studio/hello-world-console.png)

1. <span data-ttu-id="21978-162">Presione cualquier tecla para cerrar la ventana de consola.</span><span class="sxs-lookup"><span data-stu-id="21978-162">Press any key to close the console window.</span></span>

## <a name="enhance-the-app"></a><span data-ttu-id="21978-163">Mejora de la aplicación</span><span class="sxs-lookup"><span data-stu-id="21978-163">Enhance the app</span></span>

<span data-ttu-id="21978-164">Mejore su aplicación para pedir su nombre al usuario y mostrarlo junto con la fecha y la hora.</span><span class="sxs-lookup"><span data-stu-id="21978-164">Enhance your application to prompt the user for their name and display it along with the date and time.</span></span> <span data-ttu-id="21978-165">Las instrucciones siguientes modifican y ejecutan de nuevo la aplicación:</span><span class="sxs-lookup"><span data-stu-id="21978-165">The following instructions modify and run the app again:</span></span>

# <a name="ctabcsharp"></a>[<span data-ttu-id="21978-166">C#</span><span class="sxs-lookup"><span data-stu-id="21978-166">C#</span></span>](#tab/csharp)

1. <span data-ttu-id="21978-167">Reemplace el contenido del método `Main`, que actualmente es solo la línea que llama a `Console.WriteLine`, con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="21978-167">Replace the contents of the `Main` method, which is currently just the line that calls `Console.WriteLine`, with the following code:</span></span>

   [!code-csharp[GettingStarted#1](~/samples/snippets/csharp/getting_started/with_visual_studio/helloworld.cs#1)]

   <span data-ttu-id="21978-168">Este código muestra "What is your name?"</span><span class="sxs-lookup"><span data-stu-id="21978-168">This code displays "What is your name?"</span></span> <span data-ttu-id="21978-169">en la ventana de la consola y espera a que el usuario escriba una cadena seguida de la tecla Entrar.</span><span class="sxs-lookup"><span data-stu-id="21978-169">in the console window and waits until the user enters a string followed by the Enter key.</span></span> <span data-ttu-id="21978-170">Almacena esta cadena en una variable denominada `name`.</span><span class="sxs-lookup"><span data-stu-id="21978-170">It stores this string into a variable named `name`.</span></span> <span data-ttu-id="21978-171">También recupera el valor de la propiedad <xref:System.DateTime.Now?displayProperty=nameWithType>, que contiene la hora local actual, y lo asigna a una variable denominada `date`.</span><span class="sxs-lookup"><span data-stu-id="21978-171">It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=nameWithType> property, which contains the current local time, and assigns it to a variable named `date`.</span></span> <span data-ttu-id="21978-172">Por último, usa una [cadena interpolada](../../csharp/language-reference/tokens/interpolated.md) para mostrar estos valores en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="21978-172">Finally, it uses an [interpolated string](../../csharp/language-reference/tokens/interpolated.md) to display these values in the console window.</span></span>

1. <span data-ttu-id="21978-173">Compile el programa; para ello, seleccione **Generar** > **Compilar solución**.</span><span class="sxs-lookup"><span data-stu-id="21978-173">Compile the program by choosing **Build** > **Build Solution**.</span></span>

1. <span data-ttu-id="21978-174">Para ejecutar el programa, elija **HelloWorld** en la barra de herramientas o presione **F5**.</span><span class="sxs-lookup"><span data-stu-id="21978-174">To run the program, choose **HelloWorld** on the toolbar, or press **F5**.</span></span>

1. <span data-ttu-id="21978-175">Responda a la solicitud escribiendo un nombre y presionando la tecla **Entrar**.</span><span class="sxs-lookup"><span data-stu-id="21978-175">Respond to the prompt by entering a name and pressing the **Enter** key.</span></span>

   ![Ventana de la consola con el resultado del programa modificado](./media/with-visual-studio/hello-world-update.png)

1. <span data-ttu-id="21978-177">Presione cualquier tecla para cerrar la ventana de consola.</span><span class="sxs-lookup"><span data-stu-id="21978-177">Press any key to close the console window.</span></span>

# <a name="visual-basictabvb"></a>[<span data-ttu-id="21978-178">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="21978-178">Visual Basic</span></span>](#tab/vb)

1. <span data-ttu-id="21978-179">Reemplace el contenido del método `Main`, que actualmente es solo la línea que llama a `Console.WriteLine`, con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="21978-179">Replace the contents of the `Main` method, which is currently just the line that calls `Console.WriteLine`, with the following code:</span></span>

   [!code-vb[GettingStarted#1](~/samples/snippets/core/tutorials/vb-with-visual-studio/helloworld.vb#1)]

   <span data-ttu-id="21978-180">Este código muestra "What is your name?"</span><span class="sxs-lookup"><span data-stu-id="21978-180">This code displays "What is your name?"</span></span> <span data-ttu-id="21978-181">en la ventana de la consola y espera a que el usuario escriba una cadena seguida de la tecla Entrar.</span><span class="sxs-lookup"><span data-stu-id="21978-181">in the console window and waits until the user enters a string followed by the Enter key.</span></span> <span data-ttu-id="21978-182">Almacena esta cadena en una variable denominada `name`.</span><span class="sxs-lookup"><span data-stu-id="21978-182">It stores this string into a variable named `name`.</span></span> <span data-ttu-id="21978-183">También recupera el valor de la propiedad <xref:System.DateTime.Now?displayProperty=nameWithType>, que contiene la hora local actual, y lo asigna a una variable denominada `date`.</span><span class="sxs-lookup"><span data-stu-id="21978-183">It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=nameWithType> property, which contains the current local time, and assigns it to a variable named `date`.</span></span> <span data-ttu-id="21978-184">Por último, usa una [cadena interpolada](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md) para mostrar estos valores en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="21978-184">Finally, it uses an [interpolated string](../../visual-basic/programming-guide/language-features/strings/interpolated-strings.md) to display these values in the console window.</span></span>

1. <span data-ttu-id="21978-185">Compile el programa; para ello, seleccione **Generar** > **Compilar solución**.</span><span class="sxs-lookup"><span data-stu-id="21978-185">Compile the program by choosing **Build** > **Build Solution**.</span></span>

1. <span data-ttu-id="21978-186">Para ejecutar el programa, elija **HelloWorld** en la barra de herramientas o presione **F5**.</span><span class="sxs-lookup"><span data-stu-id="21978-186">To run the program, choose **HelloWorld** on the toolbar, or press **F5**.</span></span>

1. <span data-ttu-id="21978-187">Responda a la solicitud escribiendo un nombre y presionando la tecla **Entrar**.</span><span class="sxs-lookup"><span data-stu-id="21978-187">Respond to the prompt by entering a name and pressing the **Enter** key.</span></span>

   ![Ventana de la consola con el resultado del programa modificado](./media/with-visual-studio/hello-world-update.png)

1. <span data-ttu-id="21978-189">Presione cualquier tecla para cerrar la ventana de consola.</span><span class="sxs-lookup"><span data-stu-id="21978-189">Press any key to close the console window.</span></span>

---

## <a name="next-steps"></a><span data-ttu-id="21978-190">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="21978-190">Next steps</span></span>

<span data-ttu-id="21978-191">En este artículo, ha creado y ejecutado su primera aplicación de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="21978-191">In this article, you've created and run your first .NET Core application.</span></span> <span data-ttu-id="21978-192">En el paso siguiente, va a depurar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="21978-192">In the next step, you debug your app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="21978-193">Depuración de una aplicación "Hola mundo" con .NET Core en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="21978-193">Debug a .NET Core Hello World application in Visual Studio</span></span>](debugging-with-visual-studio.md)
