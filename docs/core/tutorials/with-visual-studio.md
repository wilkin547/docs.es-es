---
title: Creación de una aplicación de consola con .NET Core en Visual Studio
description: Obtenga información sobre cómo crear una aplicación de consola de .NET Core con C# o Visual Basic mediante Visual Studio.
author: BillWagner
ms.author: wiwagn
ms.date: 05/20/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 9c3456cd8c940e53e8a70c1d3a7c3b09de77c21d
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2020
ms.locfileid: "84201583"
---
# <a name="tutorial-create-a-net-core-console-application-in-visual-studio-2019"></a><span data-ttu-id="f8319-103">Tutorial: Creación de una aplicación de consola de .NET Core en Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="f8319-103">Tutorial: Create a .NET Core console application in Visual Studio 2019</span></span>

<span data-ttu-id="f8319-104">En este tutorial se muestra cómo crear y ejecutar una aplicación de consola de .NET Core en Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="f8319-104">This tutorial shows how to create and run a .NET Core console application in Visual Studio 2019.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f8319-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="f8319-105">Prerequisites</span></span>

- <span data-ttu-id="f8319-106">[Visual Studio 2019, versión 16.6 o posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) con la carga de trabajo **Desarrollo multiplataforma de .NET Core** instalada.</span><span class="sxs-lookup"><span data-stu-id="f8319-106">[Visual Studio 2019 version 16.6 or a later version](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the **.NET Core cross-platform development** workload installed.</span></span> <span data-ttu-id="f8319-107">El SDK de .NET Core 3.1 se instala automáticamente al seleccionar esta carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f8319-107">The .NET Core 3.1 SDK is automatically installed when you select this workload.</span></span>

  <span data-ttu-id="f8319-108">Para más información, consulte la sección [Instalación con Visual Studio](../install/sdk.md?pivots=os-windows#install-with-visual-studio) del artículo [Instalación del SDK de .NET Core](../install/sdk.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="f8319-108">For more information, see the [Install with Visual Studio](../install/sdk.md?pivots=os-windows#install-with-visual-studio) section on the [Install the .NET Core SDK](../install/sdk.md?pivots=os-windows) article.</span></span>

## <a name="create-the-app"></a><span data-ttu-id="f8319-109">Creación de la aplicación</span><span class="sxs-lookup"><span data-stu-id="f8319-109">Create the app</span></span>

<!-- markdownlint-disable MD025 -->

1. <span data-ttu-id="f8319-110">Abra Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="f8319-110">Open Visual Studio 2019.</span></span>

1. <span data-ttu-id="f8319-111">Cree un nuevo proyecto de aplicación de consola de .NET Core denominado "HelloWorld".</span><span class="sxs-lookup"><span data-stu-id="f8319-111">Create a new .NET Core console app project named "HelloWorld".</span></span>

   1. <span data-ttu-id="f8319-112">En la página de inicio, elija **Crear un proyecto nuevo**.</span><span class="sxs-lookup"><span data-stu-id="f8319-112">On the start page, choose **Create a new project**.</span></span>

      ![Botón Crear un proyecto nuevo seleccionado en la página de inicio de Visual Studio](./media/with-visual-studio/start-window.png)

   1. <span data-ttu-id="f8319-114">En la página **Crear un proyecto**, escriba **consola** en el cuadro de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="f8319-114">On the **Create a new project** page, enter **console** in the search box.</span></span> <span data-ttu-id="f8319-115">Después, elija **C#** o **Visual Basic** en la lista de lenguajes y luego elija **Todas las plataformas** en la lista de plataformas.</span><span class="sxs-lookup"><span data-stu-id="f8319-115">Next, choose **C#** or **Visual Basic** from the language list, and then choose **All platforms** from the platform list.</span></span> <span data-ttu-id="f8319-116">Elija la plantilla **Aplicación de consola (.NET Core)** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f8319-116">Choose the **Console App (.NET Core)** template, and then choose **Next**.</span></span>

      ![Creación de una nueva ventana de proyecto con filtros seleccionados](./media/with-visual-studio/create-new-project.png)

      > [!TIP]
      > <span data-ttu-id="f8319-118">Si no ve las plantillas de .NET Core, es probable que falte la carga de trabajo necesaria.</span><span class="sxs-lookup"><span data-stu-id="f8319-118">If you don't see the .NET Core templates, you're probably missing the required workload.</span></span> <span data-ttu-id="f8319-119">En el mensaje **¿No encuentra lo que busca?** , elija el vínculo **Instalar más herramientas y características**.</span><span class="sxs-lookup"><span data-stu-id="f8319-119">Under the **Not finding what you're looking for?** message, choose the **Install more tools and features** link.</span></span> <span data-ttu-id="f8319-120">Se abre el Instalador de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f8319-120">The Visual Studio Installer opens.</span></span> <span data-ttu-id="f8319-121">Asegúrese de que tiene instalada la carga de trabajo **Desarrollo multiplataforma de .NET Core**.</span><span class="sxs-lookup"><span data-stu-id="f8319-121">Make sure you have the **.NET Core cross-platform development** workload installed.</span></span>

   1. <span data-ttu-id="f8319-122">En la página **Configurar el nuevo proyecto**, escriba **HelloWorld** en el cuadro **Nombre del proyecto**.</span><span class="sxs-lookup"><span data-stu-id="f8319-122">On the **Configure your new project** page,  enter **HelloWorld** in the **Project name** box.</span></span> <span data-ttu-id="f8319-123">Luego, elija **Crear**.</span><span class="sxs-lookup"><span data-stu-id="f8319-123">Then choose **Create**.</span></span>

      ![Configuración de la ventana de nuevo proyecto con los campos de nombre de proyecto, ubicación y nombre de la solución](./media/with-visual-studio/configure-new-project.png)

   <span data-ttu-id="f8319-125">La plantilla de aplicación de consola para .NET Core define una clase, `Program`, con un único método, `Main`, que adopta una matriz <xref:System.String> como argumento.</span><span class="sxs-lookup"><span data-stu-id="f8319-125">The Console Application template for .NET Core defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument.</span></span> <span data-ttu-id="f8319-126">`Main` es el punto de entrada de la aplicación, el método que se llama automáticamente mediante el tiempo de ejecución cuando inicia la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f8319-126">`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application.</span></span> <span data-ttu-id="f8319-127">Los argumentos de línea de comandos proporcionados cuando se inicia la aplicación están disponibles en la matriz *args*.</span><span class="sxs-lookup"><span data-stu-id="f8319-127">Any command-line arguments supplied when the application is launched are available in the *args* array.</span></span>

   <span data-ttu-id="f8319-128">Si no se muestra el idioma que quiere usar, cambie el selector de idioma en la parte superior de la página.</span><span class="sxs-lookup"><span data-stu-id="f8319-128">If the language you want to use is not shown, change the language selector at the top of the page.</span></span>

   ```csharp
   using System;

   namespace HelloWorld
   {
       class Program
       {
           static void Main(string[] args)
           {
               Console.WriteLine("Hello World!");
           }
       }
   }
   ```

   ```vb
   Imports System

   Module Program
       Sub Main(args As String())
           Console.WriteLine("Hello World!")
       End Sub
   End Module
   ```

   <span data-ttu-id="f8319-129">La plantilla crea una aplicación "Hola mundo" sencilla.</span><span class="sxs-lookup"><span data-stu-id="f8319-129">The template creates a simple "Hello World" application.</span></span> <span data-ttu-id="f8319-130">Llama al método <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> para mostrar "Hola mundo"</span><span class="sxs-lookup"><span data-stu-id="f8319-130">It calls the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method to display "Hello World!"</span></span> <span data-ttu-id="f8319-131">en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="f8319-131">in the console window.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="f8319-132">Ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="f8319-132">Run the app</span></span>

1. <span data-ttu-id="f8319-133">Para ejecutar el programa, elija **HelloWorld** en la barra de herramientas o presione **F5**.</span><span class="sxs-lookup"><span data-stu-id="f8319-133">To run the program, choose **HelloWorld** on the toolbar, or press **F5**.</span></span>

   ![Barra de herramientas de Visual Studio con el botón Ejecutar HelloWorld seleccionado](./media/with-visual-studio/run-program.png)

   <span data-ttu-id="f8319-135">Se abre la ventana de la consola con el texto "Hello World"</span><span class="sxs-lookup"><span data-stu-id="f8319-135">A console window opens with the text "Hello World!"</span></span> <span data-ttu-id="f8319-136">impreso en la pantalla y parte de la información de depuración de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f8319-136">printed on the screen and some Visual Studio debug information.</span></span>

   ![Ventana de la consola que muestra Hola mundo Presione cualquier tecla para continuar](./media/with-visual-studio/hello-world-console.png)

1. <span data-ttu-id="f8319-138">Presione cualquier tecla para cerrar la ventana de consola.</span><span class="sxs-lookup"><span data-stu-id="f8319-138">Press any key to close the console window.</span></span>

## <a name="enhance-the-app"></a><span data-ttu-id="f8319-139">Mejora de la aplicación</span><span class="sxs-lookup"><span data-stu-id="f8319-139">Enhance the app</span></span>

<span data-ttu-id="f8319-140">Mejore la aplicación para pedir su nombre al usuario y mostrarlo con la fecha y la hora.</span><span class="sxs-lookup"><span data-stu-id="f8319-140">Enhance the application to prompt the user for their name and display it along with the date and time.</span></span> <span data-ttu-id="f8319-141">Estas instrucciones modifican la aplicación y la vuelven a ejecutar:</span><span class="sxs-lookup"><span data-stu-id="f8319-141">The following instructions modify the app and run it again:</span></span>

1. <span data-ttu-id="f8319-142">Reemplace el contenido del método `Main`, que actualmente es solo la línea que llama a `Console.WriteLine`, con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="f8319-142">Replace the contents of the `Main` method, which is currently just the line that calls `Console.WriteLine`, with the following code:</span></span>

   :::code language="csharp" source="./snippets/with-visual-studio/csharp/Program.cs" id="Snippet1":::

   :::code language="vb" source="./snippets/with-visual-studio/vb/Program.vb" id="Snippet1":::

   <span data-ttu-id="f8319-143">Este código muestra "What is your name?"</span><span class="sxs-lookup"><span data-stu-id="f8319-143">This code displays "What is your name?"</span></span> <span data-ttu-id="f8319-144">en la ventana de la consola y espera a que el usuario escriba una cadena seguida de la tecla Entrar.</span><span class="sxs-lookup"><span data-stu-id="f8319-144">in the console window and waits until the user enters a string followed by the Enter key.</span></span> <span data-ttu-id="f8319-145">Almacena esta cadena en una variable denominada `name`.</span><span class="sxs-lookup"><span data-stu-id="f8319-145">It stores this string in a variable named `name`.</span></span> <span data-ttu-id="f8319-146">También recupera el valor de la propiedad <xref:System.DateTime.Now?displayProperty=nameWithType>, que contiene la hora local actual, y lo asigna a una variable denominada `date` (`currentDate` en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="f8319-146">It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=nameWithType> property, which contains the current local time, and assigns it to a variable named `date` (`currentDate` in Visual Basic).</span></span> <span data-ttu-id="f8319-147">Por último, muestra estos valores en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="f8319-147">Finally, it displays these values in the console window.</span></span>

   <span data-ttu-id="f8319-148">El símbolo `\n` (`vbCrLf` en Visual Basic) representa un carácter de nueva línea.</span><span class="sxs-lookup"><span data-stu-id="f8319-148">The `\n` (`vbCrLf` in Visual Basic) represents a newline character.</span></span>

   <span data-ttu-id="f8319-149">El signo de dólar (`$`) delante de una cadena permite colocar expresiones como nombres de variable entre llaves en la cadena.</span><span class="sxs-lookup"><span data-stu-id="f8319-149">The dollar sign (`$`) in front of a string lets you put expressions such as variable names in curly braces in the string.</span></span> <span data-ttu-id="f8319-150">El valor de la expresión se inserta en la cadena en lugar de la expresión.</span><span class="sxs-lookup"><span data-stu-id="f8319-150">The expression value is inserted into the string in place of the expression.</span></span> <span data-ttu-id="f8319-151">Esta sintaxis se conoce como [cadenas interpoladas](../../csharp/language-reference/tokens/interpolated.md).</span><span class="sxs-lookup"><span data-stu-id="f8319-151">This syntax is referred to as [interpolated strings](../../csharp/language-reference/tokens/interpolated.md).</span></span>

1. <span data-ttu-id="f8319-152">Para ejecutar el programa, elija **HelloWorld** en la barra de herramientas o presione **F5**.</span><span class="sxs-lookup"><span data-stu-id="f8319-152">To run the program, choose **HelloWorld** on the toolbar, or press **F5**.</span></span>

1. <span data-ttu-id="f8319-153">Responda a la solicitud escribiendo un nombre y presionando la tecla **Entrar**.</span><span class="sxs-lookup"><span data-stu-id="f8319-153">Respond to the prompt by entering a name and pressing the **Enter** key.</span></span>

   ![Ventana de la consola con el resultado del programa modificado](./media/with-visual-studio/hello-world-update.png)

1. <span data-ttu-id="f8319-155">Presione cualquier tecla para cerrar la ventana de consola.</span><span class="sxs-lookup"><span data-stu-id="f8319-155">Press any key to close the console window.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f8319-156">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="f8319-156">Next steps</span></span>

<span data-ttu-id="f8319-157">En este tutorial, ha creado una aplicación de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f8319-157">In this tutorial, you created a .NET Core application.</span></span> <span data-ttu-id="f8319-158">En el siguiente tutorial, depurará la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f8319-158">In the next tutorial, you debug the app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f8319-159">Depuración de una aplicación de consola de .NET Core con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f8319-159">Debug a .NET Core console application in Visual Studio</span></span>](debugging-with-visual-studio.md)
