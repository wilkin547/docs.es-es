---
title: Creación de una aplicación de consola de .NET con Visual Studio para Mac
description: Aprenda a crear una aplicación de consola de .NET con Visual Studio para Mac.
ms.date: 11/30/2020
ms.openlocfilehash: 4add8309338b8618265a66b9e71dab2df38ca8d0
ms.sourcegitcommit: 1d3af230ec30d8d061be7a887f6ba38a530c4ece
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "102511832"
---
# <a name="tutorial-create-a-net-console-application-using-visual-studio-for-mac"></a><span data-ttu-id="c3923-103">Tutorial: Creación de una aplicación de consola de .NET con Visual Studio para Mac</span><span class="sxs-lookup"><span data-stu-id="c3923-103">Tutorial: Create a .NET console application using Visual Studio for Mac</span></span>

<span data-ttu-id="c3923-104">En este tutorial se muestra cómo crear y ejecutar una aplicación de consola de .NET en Visual Studio para Mac.</span><span class="sxs-lookup"><span data-stu-id="c3923-104">This tutorial shows how to create and run a .NET console application using Visual Studio for Mac.</span></span>

> [!NOTE]
> <span data-ttu-id="c3923-105">Sus comentarios son muy importantes.</span><span class="sxs-lookup"><span data-stu-id="c3923-105">Your feedback is highly valued.</span></span> <span data-ttu-id="c3923-106">Hay dos maneras de proporcionar comentarios al equipo de desarrollo de Visual Studio para Mac:</span><span class="sxs-lookup"><span data-stu-id="c3923-106">There are two ways you can provide feedback to the development team on Visual Studio for Mac:</span></span>
>
> * <span data-ttu-id="c3923-107">En Visual Studio para Mac, seleccione **Ayuda** > **Notificar un problema** en el menú o **Notificar un problema** desde la pantalla de bienvenida, que abre una ventana para presentar un informe de errores.</span><span class="sxs-lookup"><span data-stu-id="c3923-107">In Visual Studio for Mac, select **Help** > **Report a Problem** from the menu or **Report a Problem** from the Welcome screen, which will open a window for filing a bug report.</span></span> <span data-ttu-id="c3923-108">Puede realizar un seguimiento de sus comentarios en el portal de la [Comunidad de desarrolladores](https://aka.ms/feedback/report?space=41).</span><span class="sxs-lookup"><span data-stu-id="c3923-108">You can track your feedback in the [Developer Community](https://aka.ms/feedback/report?space=41) portal.</span></span>
> * <span data-ttu-id="c3923-109">Para hacer una sugerencia, seleccione **Ayuda** > **Aportar una sugerencia** en el menú o **Aportar una sugerencia** desde la pantalla de bienvenida, que le lleva a la [página web de la Comunidad de desarrolladores de Visual Studio para Mac](https://aka.ms/feedback/suggest?space=41).</span><span class="sxs-lookup"><span data-stu-id="c3923-109">To make a suggestion, select **Help** > **Provide a Suggestion** from the menu or **Provide a Suggestion** from the Welcome screen, which will take you to the [Visual Studio for Mac Developer Community webpage](https://aka.ms/feedback/suggest?space=41).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c3923-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="c3923-110">Prerequisites</span></span>

* <span data-ttu-id="c3923-111">[Visual Studio para Mac, versión 8.8 o posterior](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)</span><span class="sxs-lookup"><span data-stu-id="c3923-111">[Visual Studio for Mac version 8.8 or later](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).</span></span> <span data-ttu-id="c3923-112">Seleccione la opción para instalar .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c3923-112">Select the option to install .NET Core.</span></span> <span data-ttu-id="c3923-113">La instalación de Xamarin es opcional para el desarrollo con .NET.</span><span class="sxs-lookup"><span data-stu-id="c3923-113">Installing Xamarin is optional for .NET development.</span></span> <span data-ttu-id="c3923-114">Para obtener más información, vea los siguientes recursos:</span><span class="sxs-lookup"><span data-stu-id="c3923-114">For more information, see the following resources:</span></span>

  * <span data-ttu-id="c3923-115">[Tutorial: Instalación de Visual Studio para Mac](/visualstudio/mac/installation).</span><span class="sxs-lookup"><span data-stu-id="c3923-115">[Tutorial: Install Visual Studio for Mac](/visualstudio/mac/installation).</span></span>
  * <span data-ttu-id="c3923-116">[Versiones de macOS compatibles](../install/windows.md).</span><span class="sxs-lookup"><span data-stu-id="c3923-116">[Supported macOS versions](../install/windows.md).</span></span>
  * <span data-ttu-id="c3923-117">[Versiones de .NET compatibles con Visual Studio para Mac](/visualstudio/mac/net-core-support).</span><span class="sxs-lookup"><span data-stu-id="c3923-117">[.NET versions supported by Visual Studio for Mac](/visualstudio/mac/net-core-support).</span></span>

## <a name="create-the-app"></a><span data-ttu-id="c3923-118">Creación de la aplicación</span><span class="sxs-lookup"><span data-stu-id="c3923-118">Create the app</span></span>

1. <span data-ttu-id="c3923-119">Inicie Visual Studio para Mac:</span><span class="sxs-lookup"><span data-stu-id="c3923-119">Start Visual Studio for Mac.</span></span>

1. <span data-ttu-id="c3923-120">Seleccione **Nuevo** en la ventana de inicio.</span><span class="sxs-lookup"><span data-stu-id="c3923-120">Select **New** in the start window.</span></span>

   :::image type="content" source="media/with-visual-studio-mac/visual-studio-mac-new-project.png" alt-text="Botón Nuevo en la pantalla Inicio de Visual Studio para Mac":::

1. <span data-ttu-id="c3923-122">En el cuadro de diálogo **Nuevo proyecto**, seleccione **Aplicación** en el nodo **Web and Console** (Web y consola).</span><span class="sxs-lookup"><span data-stu-id="c3923-122">In the **New Project** dialog, select **App** under the **Web and Console** node.</span></span> <span data-ttu-id="c3923-123">Seleccione la plantilla **Aplicación de consola** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c3923-123">Select the **Console Application** template, and select **Next**.</span></span>

   :::image type="content" source="media/with-visual-studio-mac/visual-studio-mac-new-dialog.png" alt-text="Lista de plantillas de Nuevo proyecto":::

1. <span data-ttu-id="c3923-125">En la lista desplegable **Plataforma de destino** del cuadro de diálogo para **Configure your new Console Application** (Configurar una nueva aplicación de consola), seleccione **.NET 5.0** y elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c3923-125">In the **Target Framework** drop-down of the **Configure your new Console Application** dialog, select **.NET 5.0**, and select **Next**.</span></span>

1. <span data-ttu-id="c3923-126">Escriba "HelloWorld" en **Nombre del proyecto** y seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="c3923-126">Type "HelloWorld" for the **Project Name**, and select **Create**.</span></span>

   :::image type="content" source="media/with-visual-studio-mac/visual-studio-mac-new-options.png" alt-text="Cuadro de diálogo de configuración de la nueva aplicación de consola":::

<span data-ttu-id="c3923-128">La plantilla crea una aplicación "Hola mundo" sencilla.</span><span class="sxs-lookup"><span data-stu-id="c3923-128">The template creates a simple "Hello World" application.</span></span> <span data-ttu-id="c3923-129">Llama al método <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> para mostrar "Hola mundo"</span><span class="sxs-lookup"><span data-stu-id="c3923-129">It calls the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method to display "Hello World!"</span></span> <span data-ttu-id="c3923-130">en la ventana de terminal.</span><span class="sxs-lookup"><span data-stu-id="c3923-130">in the terminal window.</span></span>

<span data-ttu-id="c3923-131">El código de plantilla define una clase, `Program`, con un único método, `Main`, que toma una matriz de <xref:System.String> como argumento:</span><span class="sxs-lookup"><span data-stu-id="c3923-131">The template code defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument:</span></span>

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

<span data-ttu-id="c3923-132">`Main` es el punto de entrada de la aplicación, el método que se llama automáticamente mediante el tiempo de ejecución cuando inicia la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c3923-132">`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application.</span></span> <span data-ttu-id="c3923-133">Los argumentos de línea de comandos proporcionados cuando se inicia la aplicación están disponibles en la matriz `args`.</span><span class="sxs-lookup"><span data-stu-id="c3923-133">Any command-line arguments supplied when the application is launched are available in the `args` array.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="c3923-134">Ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="c3923-134">Run the app</span></span>

1. <span data-ttu-id="c3923-135">Presione <kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>opción</kbd>+<kbd>command</kbd>+<kbd>entrar</kbd>) para ejecutar la aplicación sin depuración.</span><span class="sxs-lookup"><span data-stu-id="c3923-135">Press <kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>option</kbd>+<kbd>command</kbd>+<kbd>enter</kbd>) to run the app without debugging.</span></span>

   :::image type="content" source="media/with-visual-studio-mac/visual-studio-mac-output.png" alt-text="El terminal muestra Hola mundo.":::

1. <span data-ttu-id="c3923-137">Cierre la ventana de **Terminal**.</span><span class="sxs-lookup"><span data-stu-id="c3923-137">Close the **Terminal** window.</span></span>

## <a name="enhance-the-app"></a><span data-ttu-id="c3923-138">Mejora de la aplicación</span><span class="sxs-lookup"><span data-stu-id="c3923-138">Enhance the app</span></span>

<span data-ttu-id="c3923-139">Mejore la aplicación para pedir su nombre al usuario y mostrarlo con la fecha y la hora.</span><span class="sxs-lookup"><span data-stu-id="c3923-139">Enhance the application to prompt the user for their name and display it along with the date and time.</span></span>

1. <span data-ttu-id="c3923-140">En *Program.cs*, reemplace el contenido del método `Main`, que es la línea que llama a `Console.WriteLine`, por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="c3923-140">In *Program.cs*, replace the contents of the `Main` method, which is the line that calls `Console.WriteLine`, with the following code:</span></span>

   :::code language="csharp" source="./snippets/with-visual-studio/csharp/Program.cs" id="MainMethod":::

   <span data-ttu-id="c3923-141">Este código muestra un mensaje en la ventana de la consola y espera a que el usuario escriba una cadena y, luego, presione <kbd>Entrar</kbd>.</span><span class="sxs-lookup"><span data-stu-id="c3923-141">This code displays a prompt in the console window and waits until the user enters a string followed by the <kbd>enter</kbd> key.</span></span> <span data-ttu-id="c3923-142">Almacena esta cadena en una variable denominada `name`.</span><span class="sxs-lookup"><span data-stu-id="c3923-142">It stores this string in a variable named `name`.</span></span> <span data-ttu-id="c3923-143">También recupera el valor de la propiedad <xref:System.DateTime.Now?displayProperty=nameWithType>, que contiene la hora local actual, y lo asigna a una variable denominada `date`.</span><span class="sxs-lookup"><span data-stu-id="c3923-143">It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=nameWithType> property, which contains the current local time, and assigns it to a variable named `date`.</span></span> <span data-ttu-id="c3923-144">Asimismo, muestra estos valores en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="c3923-144">And it displays these values in the console window.</span></span> <span data-ttu-id="c3923-145">Por último, muestra un mensaje en la ventana de la consola y llama al método <xref:System.Console.ReadKey(System.Boolean)?displayProperty=nameWithType> para esperar a la entrada del usuario.</span><span class="sxs-lookup"><span data-stu-id="c3923-145">Finally, it displays a prompt in the console window and calls the <xref:System.Console.ReadKey(System.Boolean)?displayProperty=nameWithType> method to wait for user input.</span></span>

   <span data-ttu-id="c3923-146"><xref:System.Environment.NewLine> es una manera independiente de la plataforma y del lenguaje de representar un salto de línea.</span><span class="sxs-lookup"><span data-stu-id="c3923-146"><xref:System.Environment.NewLine> is a platform-independent and language-independent way to represent a line break.</span></span> <span data-ttu-id="c3923-147">Las alternativas son `\n` en C# y `vbCrLf` en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c3923-147">Alternatives are `\n` in C# and `vbCrLf` in Visual Basic.</span></span>

   <span data-ttu-id="c3923-148">El signo de dólar (`$`) delante de una cadena permite colocar expresiones como nombres de variable entre llaves en la cadena.</span><span class="sxs-lookup"><span data-stu-id="c3923-148">The dollar sign (`$`) in front of a string lets you put expressions such as variable names in curly braces in the string.</span></span> <span data-ttu-id="c3923-149">El valor de la expresión se inserta en la cadena en lugar de la expresión.</span><span class="sxs-lookup"><span data-stu-id="c3923-149">The expression value is inserted into the string in place of the expression.</span></span> <span data-ttu-id="c3923-150">Esta sintaxis se conoce como [cadenas interpoladas](../../csharp/language-reference/tokens/interpolated.md).</span><span class="sxs-lookup"><span data-stu-id="c3923-150">This syntax is referred to as [interpolated strings](../../csharp/language-reference/tokens/interpolated.md).</span></span>

1. <span data-ttu-id="c3923-151">Presione <kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>opción</kbd>+<kbd>command</kbd>+<kbd>entrar</kbd>) para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c3923-151">Press <kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>option</kbd>+<kbd>command</kbd>+<kbd>enter</kbd>) to run the app.</span></span>

1. <span data-ttu-id="c3923-152">Responda a la solicitud escribiendo un nombre y presionando la tecla <kbd>entrar</kbd>.</span><span class="sxs-lookup"><span data-stu-id="c3923-152">Respond to the prompt by entering a name and pressing <kbd>enter</kbd>.</span></span>

   :::image type="content" source="media/with-visual-studio-mac/hello-world-update.png" alt-text="Terminal muestra la salida del programa modificado":::

1. <span data-ttu-id="c3923-154">Cierre el terminal.</span><span class="sxs-lookup"><span data-stu-id="c3923-154">Close the terminal.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c3923-155">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="c3923-155">Next steps</span></span>

<span data-ttu-id="c3923-156">En este tutorial, ha creado una aplicación de consola de .NET.</span><span class="sxs-lookup"><span data-stu-id="c3923-156">In this tutorial, you created a .NET console application.</span></span> <span data-ttu-id="c3923-157">En el siguiente tutorial, depurará la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c3923-157">In the next tutorial, you debug the app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="c3923-158">Depuración de una aplicación de consola de .NET con Visual Studio para Mac</span><span class="sxs-lookup"><span data-stu-id="c3923-158">Debug a .NET console application using Visual Studio for Mac</span></span>](debugging-with-visual-studio-mac.md)
