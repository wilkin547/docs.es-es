---
title: Creación de una aplicación de consola de .NET Core con Visual Studio
description: Obtenga información sobre cómo crear una aplicación de consola de .NET Core con C# o Visual Basic mediante Visual Studio.
ms.date: 06/08/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 7ef8e17b8a42defc0858123332976d30c83f20c8
ms.sourcegitcommit: 1cbd77da54405ea7dba343ac0334fb03237d25d2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2020
ms.locfileid: "84700437"
---
# <a name="tutorial-create-a-net-core-console-application-using-visual-studio"></a><span data-ttu-id="392ad-103">Tutorial: Creación de una aplicación de consola de .NET Core con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="392ad-103">Tutorial: Create a .NET Core console application using Visual Studio</span></span>

<span data-ttu-id="392ad-104">En este tutorial se muestra cómo crear y ejecutar una aplicación de consola de .NET Core en Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="392ad-104">This tutorial shows how to create and run a .NET Core console application in Visual Studio 2019.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="392ad-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="392ad-105">Prerequisites</span></span>

- <span data-ttu-id="392ad-106">[Visual Studio 2019, versión 16.6 o posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) con la carga de trabajo **Desarrollo multiplataforma de .NET Core** instalada.</span><span class="sxs-lookup"><span data-stu-id="392ad-106">[Visual Studio 2019 version 16.6 or a later version](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the **.NET Core cross-platform development** workload installed.</span></span> <span data-ttu-id="392ad-107">El SDK de .NET Core 3.1 se instala automáticamente al seleccionar esta carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="392ad-107">The .NET Core 3.1 SDK is automatically installed when you select this workload.</span></span>

  <span data-ttu-id="392ad-108">Para más información, consulte [Instalación del SDK de .NET Core con Visual Studio](../install/sdk.md?pivots=os-windows#install-with-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="392ad-108">For more information, see [Install the .NET Core SDK with Visual Studio](../install/sdk.md?pivots=os-windows#install-with-visual-studio).</span></span>

## <a name="create-the-app"></a><span data-ttu-id="392ad-109">Creación de la aplicación</span><span class="sxs-lookup"><span data-stu-id="392ad-109">Create the app</span></span>

<span data-ttu-id="392ad-110">Cree un proyecto de aplicación de consola de .NET Core denominado "HelloWorld".</span><span class="sxs-lookup"><span data-stu-id="392ad-110">Create a .NET Core console app project named "HelloWorld".</span></span>

1. <span data-ttu-id="392ad-111">Inicie Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="392ad-111">Start Visual Studio 2019.</span></span>

1. <span data-ttu-id="392ad-112">En la página de inicio, elija **Crear un proyecto nuevo**.</span><span class="sxs-lookup"><span data-stu-id="392ad-112">On the start page, choose **Create a new project**.</span></span>

   ![Botón Crear un proyecto nuevo seleccionado en la página de inicio de Visual Studio](./media/with-visual-studio/start-window.png)

1. <span data-ttu-id="392ad-114">En la página **Crear un proyecto**, escriba **consola** en el cuadro de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="392ad-114">On the **Create a new project** page, enter **console** in the search box.</span></span> <span data-ttu-id="392ad-115">Después, elija **C#** o **Visual Basic** en la lista de lenguajes y luego elija **Todas las plataformas** en la lista de plataformas.</span><span class="sxs-lookup"><span data-stu-id="392ad-115">Next, choose **C#** or **Visual Basic** from the language list, and then choose **All platforms** from the platform list.</span></span> <span data-ttu-id="392ad-116">Elija la plantilla **Aplicación de consola (.NET Core)** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="392ad-116">Choose the **Console App (.NET Core)** template, and then choose **Next**.</span></span>

   ![Creación de una nueva ventana de proyecto con filtros seleccionados](./media/with-visual-studio/create-new-project.png)

   > [!TIP]
   > <span data-ttu-id="392ad-118">Si no ve las plantillas de .NET Core, es probable que falte la carga de trabajo necesaria.</span><span class="sxs-lookup"><span data-stu-id="392ad-118">If you don't see the .NET Core templates, you're probably missing the required workload.</span></span> <span data-ttu-id="392ad-119">En el mensaje **¿No encuentra lo que busca?** , elija el vínculo **Instalar más herramientas y características**.</span><span class="sxs-lookup"><span data-stu-id="392ad-119">Under the **Not finding what you're looking for?** message, choose the **Install more tools and features** link.</span></span> <span data-ttu-id="392ad-120">Se abre el Instalador de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="392ad-120">The Visual Studio Installer opens.</span></span> <span data-ttu-id="392ad-121">Asegúrese de que tiene instalada la carga de trabajo **Desarrollo multiplataforma de .NET Core**.</span><span class="sxs-lookup"><span data-stu-id="392ad-121">Make sure you have the **.NET Core cross-platform development** workload installed.</span></span>

1. <span data-ttu-id="392ad-122">En el cuadro de diálogo **Configurar el nuevo proyecto**, escriba **HelloWorld** en el cuadro **Nombre del proyecto**.</span><span class="sxs-lookup"><span data-stu-id="392ad-122">In the **Configure your new project** dialog,  enter **HelloWorld** in the **Project name** box.</span></span> <span data-ttu-id="392ad-123">Luego, elija **Crear**.</span><span class="sxs-lookup"><span data-stu-id="392ad-123">Then choose **Create**.</span></span>

   ![Configuración de la ventana de nuevo proyecto con los campos de nombre de proyecto, ubicación y nombre de la solución](./media/with-visual-studio/configure-new-project.png)

<span data-ttu-id="392ad-125">La plantilla crea una aplicación "Hola mundo" sencilla.</span><span class="sxs-lookup"><span data-stu-id="392ad-125">The template creates a simple "Hello World" application.</span></span> <span data-ttu-id="392ad-126">Llama al método <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> para mostrar "Hola mundo"</span><span class="sxs-lookup"><span data-stu-id="392ad-126">It calls the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method to display "Hello World!"</span></span> <span data-ttu-id="392ad-127">en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="392ad-127">in the console window.</span></span>

<span data-ttu-id="392ad-128">El código de plantilla define una clase, `Program`, con un solo método, `Main`, que toma una matriz de <xref:System.String> como argumento:</span><span class="sxs-lookup"><span data-stu-id="392ad-128">The template code defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument:</span></span>

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

<span data-ttu-id="392ad-129">`Main` es el punto de entrada de la aplicación, el método que se llama automáticamente mediante el tiempo de ejecución cuando inicia la aplicación.</span><span class="sxs-lookup"><span data-stu-id="392ad-129">`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application.</span></span> <span data-ttu-id="392ad-130">Los argumentos de línea de comandos proporcionados cuando se inicia la aplicación están disponibles en la matriz *args*.</span><span class="sxs-lookup"><span data-stu-id="392ad-130">Any command-line arguments supplied when the application is launched are available in the *args* array.</span></span>

<span data-ttu-id="392ad-131">Si no se muestra el idioma que quiere usar, cambie el selector de idioma en la parte superior de la página.</span><span class="sxs-lookup"><span data-stu-id="392ad-131">If the language you want to use is not shown, change the language selector at the top of the page.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="392ad-132">Ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="392ad-132">Run the app</span></span>

1. <span data-ttu-id="392ad-133">Presione <kbd>Mayús</kbd>+<kbd>F5</kbd> para ejecutar el programa sin depuración.</span><span class="sxs-lookup"><span data-stu-id="392ad-133">Press <kbd>Shift</kbd>+<kbd>F5</kbd> to run the program without debugging.</span></span>

   <span data-ttu-id="392ad-134">Se abre la ventana de la consola con el texto "Hello World"</span><span class="sxs-lookup"><span data-stu-id="392ad-134">A console window opens with the text "Hello World!"</span></span> <span data-ttu-id="392ad-135">impreso en la pantalla y parte de la información de depuración de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="392ad-135">printed on the screen and some Visual Studio debug information.</span></span>

   ![Ventana de la consola que muestra Hola mundo Presione cualquier tecla para continuar](./media/with-visual-studio/hello-world-console.png)

1. <span data-ttu-id="392ad-137">Presione cualquier tecla para cerrar la ventana de consola.</span><span class="sxs-lookup"><span data-stu-id="392ad-137">Press any key to close the console window.</span></span>

## <a name="enhance-the-app"></a><span data-ttu-id="392ad-138">Mejora de la aplicación</span><span class="sxs-lookup"><span data-stu-id="392ad-138">Enhance the app</span></span>

<span data-ttu-id="392ad-139">Mejore la aplicación para pedir su nombre al usuario y mostrarlo con la fecha y la hora.</span><span class="sxs-lookup"><span data-stu-id="392ad-139">Enhance the application to prompt the user for their name and display it along with the date and time.</span></span>

1. <span data-ttu-id="392ad-140">En *Program.cs* o *Program.vb*, reemplace el contenido del método `Main`, que es la línea que llama a `Console.WriteLine`, por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="392ad-140">In *Program.cs* or *Program.vb*, replace the contents of the `Main` method, which is the line that calls `Console.WriteLine`, with the following code:</span></span>

   [!code-csharp[GettingStarted#1](./snippets/with-visual-studio/csharp/Program.cs#1)]
   [!code-vb[GettingStarted#1](./snippets/with-visual-studio/vb/Program.vb#1)]

   <span data-ttu-id="392ad-141">Este código muestra "What is your name?"</span><span class="sxs-lookup"><span data-stu-id="392ad-141">This code displays "What is your name?"</span></span> <span data-ttu-id="392ad-142">en la ventana de la consola y espera a que el usuario escriba una cadena y luego presione <kbd>Entrar</kbd>.</span><span class="sxs-lookup"><span data-stu-id="392ad-142">in the console window and waits until the user enters a string followed by the <kbd>Enter</kbd> key.</span></span> <span data-ttu-id="392ad-143">Almacena esta cadena en una variable denominada `name`.</span><span class="sxs-lookup"><span data-stu-id="392ad-143">It stores this string in a variable named `name`.</span></span> <span data-ttu-id="392ad-144">También recupera el valor de la propiedad <xref:System.DateTime.Now?displayProperty=nameWithType>, que contiene la hora local actual, y lo asigna a una variable denominada `date` (`currentDate` en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="392ad-144">It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=nameWithType> property, which contains the current local time, and assigns it to a variable named `date` (`currentDate` in Visual Basic).</span></span> <span data-ttu-id="392ad-145">Por último, muestra estos valores en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="392ad-145">Finally, it displays these values in the console window.</span></span>

   <span data-ttu-id="392ad-146">El símbolo `\n` (`vbCrLf` en Visual Basic) representa un carácter de nueva línea.</span><span class="sxs-lookup"><span data-stu-id="392ad-146">The `\n` (`vbCrLf` in Visual Basic) represents a newline character.</span></span>

   <span data-ttu-id="392ad-147">El signo de dólar (`$`) delante de una cadena permite colocar expresiones como nombres de variable entre llaves en la cadena.</span><span class="sxs-lookup"><span data-stu-id="392ad-147">The dollar sign (`$`) in front of a string lets you put expressions such as variable names in curly braces in the string.</span></span> <span data-ttu-id="392ad-148">El valor de la expresión se inserta en la cadena en lugar de la expresión.</span><span class="sxs-lookup"><span data-stu-id="392ad-148">The expression value is inserted into the string in place of the expression.</span></span> <span data-ttu-id="392ad-149">Esta sintaxis se conoce como [cadenas interpoladas](../../csharp/language-reference/tokens/interpolated.md).</span><span class="sxs-lookup"><span data-stu-id="392ad-149">This syntax is referred to as [interpolated strings](../../csharp/language-reference/tokens/interpolated.md).</span></span>

1. <span data-ttu-id="392ad-150">Presione <kbd>Mayús</kbd>+<kbd>F5</kbd> para ejecutar el programa sin depuración.</span><span class="sxs-lookup"><span data-stu-id="392ad-150">Press <kbd>Shift</kbd>+<kbd>F5</kbd> to run the program without debugging.</span></span>

1. <span data-ttu-id="392ad-151">Responda a la solicitud escribiendo un nombre y presionando la tecla <kbd>Entrar</kbd>.</span><span class="sxs-lookup"><span data-stu-id="392ad-151">Respond to the prompt by entering a name and pressing the <kbd>Enter</kbd> key.</span></span>

   ![Ventana de la consola con el resultado del programa modificado](./media/with-visual-studio/hello-world-update.png)

1. <span data-ttu-id="392ad-153">Presione cualquier tecla para cerrar la ventana de consola.</span><span class="sxs-lookup"><span data-stu-id="392ad-153">Press any key to close the console window.</span></span>

## <a name="next-steps"></a><span data-ttu-id="392ad-154">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="392ad-154">Next steps</span></span>

<span data-ttu-id="392ad-155">En este tutorial, ha creado una aplicación de consola de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="392ad-155">In this tutorial, you created a .NET Core console application.</span></span> <span data-ttu-id="392ad-156">En el siguiente tutorial, depurará la aplicación.</span><span class="sxs-lookup"><span data-stu-id="392ad-156">In the next tutorial, you debug the app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="392ad-157">Depuración de una aplicación de consola de .NET Core con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="392ad-157">Debug a .NET Core console application in Visual Studio</span></span>](debugging-with-visual-studio.md)
