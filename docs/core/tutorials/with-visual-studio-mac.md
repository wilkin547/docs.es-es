---
title: Creación de una aplicación de consola de .NET Core con Visual Studio para Mac
description: Aprenda a crear una aplicación de consola de .NET Core con Visual Studio para Mac.
ms.date: 06/02/2020
ms.openlocfilehash: 0248e48865541a7c73b9e219a06a57996c5cf601
ms.sourcegitcommit: 48466b8fb7332ececff5dc388f19f6b3ff503dd4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/05/2020
ms.locfileid: "93400531"
---
# <a name="tutorial-create-a-net-core-console-application-using-visual-studio-for-mac"></a><span data-ttu-id="2c8a2-103">Tutorial: Creación de una aplicación de consola de .NET Core con Visual Studio para Mac</span><span class="sxs-lookup"><span data-stu-id="2c8a2-103">Tutorial: Create a .NET Core console application using Visual Studio for Mac</span></span>

<span data-ttu-id="2c8a2-104">En este tutorial se muestra cómo crear y ejecutar una aplicación de consola de .NET Core en Visual Studio para Mac.</span><span class="sxs-lookup"><span data-stu-id="2c8a2-104">This tutorial shows how to create and run a .NET Core console application using Visual Studio for Mac.</span></span>

> [!NOTE]
> <span data-ttu-id="2c8a2-105">Sus comentarios son muy importantes.</span><span class="sxs-lookup"><span data-stu-id="2c8a2-105">Your feedback is highly valued.</span></span> <span data-ttu-id="2c8a2-106">Hay dos maneras de proporcionar comentarios al equipo de desarrollo de Visual Studio para Mac:</span><span class="sxs-lookup"><span data-stu-id="2c8a2-106">There are two ways you can provide feedback to the development team on Visual Studio for Mac:</span></span>
>
> * <span data-ttu-id="2c8a2-107">En Visual Studio para Mac, seleccione **Ayuda** > **Notificar un problema** en el menú o **Notificar un problema** desde la pantalla de bienvenida, que abre una ventana para presentar un informe de errores.</span><span class="sxs-lookup"><span data-stu-id="2c8a2-107">In Visual Studio for Mac, select **Help** > **Report a Problem** from the menu or **Report a Problem** from the Welcome screen, which will open a window for filing a bug report.</span></span> <span data-ttu-id="2c8a2-108">Puede realizar un seguimiento de sus comentarios en el portal de la [Comunidad de desarrolladores](https://aka.ms/feedback/report?space=41).</span><span class="sxs-lookup"><span data-stu-id="2c8a2-108">You can track your feedback in the [Developer Community](https://aka.ms/feedback/report?space=41) portal.</span></span>
> * <span data-ttu-id="2c8a2-109">Para hacer una sugerencia, seleccione **Ayuda** > **Aportar una sugerencia** en el menú o **Aportar una sugerencia** desde la pantalla de bienvenida, que le lleva a la [página web de la Comunidad de desarrolladores de Visual Studio para Mac](https://aka.ms/feedback/suggest?space=41).</span><span class="sxs-lookup"><span data-stu-id="2c8a2-109">To make a suggestion, select **Help** > **Provide a Suggestion** from the menu or **Provide a Suggestion** from the Welcome screen, which will take you to the [Visual Studio for Mac Developer Community webpage](https://aka.ms/feedback/suggest?space=41).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2c8a2-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="2c8a2-110">Prerequisites</span></span>

* <span data-ttu-id="2c8a2-111">[Visual Studio para Mac, versión 8.6 o posterior](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).</span><span class="sxs-lookup"><span data-stu-id="2c8a2-111">[Visual Studio for Mac version 8.6 or later](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).</span></span> <span data-ttu-id="2c8a2-112">Seleccione la opción para instalar .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2c8a2-112">Select the option to install .NET Core.</span></span> <span data-ttu-id="2c8a2-113">La instalación de Xamarin es opcional para el desarrollo de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2c8a2-113">Installing Xamarin is optional for .NET Core development.</span></span> <span data-ttu-id="2c8a2-114">Para obtener más información, vea los siguientes recursos:</span><span class="sxs-lookup"><span data-stu-id="2c8a2-114">For more information, see the following resources:</span></span>

  * <span data-ttu-id="2c8a2-115">[Tutorial: Instalación de Visual Studio para Mac](/visualstudio/mac/installation).</span><span class="sxs-lookup"><span data-stu-id="2c8a2-115">[Tutorial: Install Visual Studio for Mac](/visualstudio/mac/installation).</span></span>
  * <span data-ttu-id="2c8a2-116">[Versiones de macOS compatibles](../install/windows.md).</span><span class="sxs-lookup"><span data-stu-id="2c8a2-116">[Supported macOS versions](../install/windows.md).</span></span>
  * <span data-ttu-id="2c8a2-117">[Versiones de .NET Core compatibles con Visual Studio para Mac](/visualstudio/mac/net-core-support).</span><span class="sxs-lookup"><span data-stu-id="2c8a2-117">[.NET Core versions supported by Visual Studio for Mac](/visualstudio/mac/net-core-support).</span></span>

## <a name="create-the-app"></a><span data-ttu-id="2c8a2-118">Creación de la aplicación</span><span class="sxs-lookup"><span data-stu-id="2c8a2-118">Create the app</span></span>

<span data-ttu-id="2c8a2-119">Cree un proyecto de aplicación de consola de .NET Core denominado "HelloWorld".</span><span class="sxs-lookup"><span data-stu-id="2c8a2-119">Create a .NET Core console app project named "HelloWorld".</span></span>

1. <span data-ttu-id="2c8a2-120">Inicie Visual Studio para Mac:</span><span class="sxs-lookup"><span data-stu-id="2c8a2-120">Start Visual Studio for Mac.</span></span>

1. <span data-ttu-id="2c8a2-121">Seleccione **Nuevo** en la ventana de inicio.</span><span class="sxs-lookup"><span data-stu-id="2c8a2-121">Select **New** in the start window.</span></span>

   :::image type="content" source="media/with-visual-studio-mac/visual-studio-mac-new-project.png" alt-text="Botón Nuevo en la pantalla Inicio de Visual Studio para Mac":::

1. <span data-ttu-id="2c8a2-123">En el cuadro de diálogo **Nuevo proyecto** , seleccione **Aplicación** en el nodo **Web and Console** (Web y consola).</span><span class="sxs-lookup"><span data-stu-id="2c8a2-123">In the **New Project** dialog, select **App** under the **Web and Console** node.</span></span> <span data-ttu-id="2c8a2-124">Seleccione la plantilla **Aplicación de consola** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2c8a2-124">Select the **Console Application** template, and select **Next**.</span></span>

   :::image type="content" source="media/with-visual-studio-mac/visual-studio-mac-new-dialog.png" alt-text="Lista de plantillas de Nuevo proyecto":::

1. <span data-ttu-id="2c8a2-126">En el cuadro de diálogo **Plataforma de destino** del cuadro de diálogo para **configurar la nueva aplicación de consola** , seleccione **.NET Core 3.1** y seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2c8a2-126">In the **Target Framework** drop-down of the **Configure your new Console Application** dialog, select **.NET Core 3.1** , and select **Next**.</span></span>

   :::image type="content" source="media/with-visual-studio-mac/target-framework.png" alt-text="Selección de la plataforma de destino":::

1. <span data-ttu-id="2c8a2-128">Escriba "HelloWorld" en **Nombre del proyecto** y seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="2c8a2-128">Type "HelloWorld" for the **Project Name** , and select **Create**.</span></span>

   :::image type="content" source="media/with-visual-studio-mac/visual-studio-mac-new-options.png" alt-text="Cuadro de diálogo de configuración de la nueva aplicación de consola":::

<span data-ttu-id="2c8a2-130">La plantilla crea una aplicación "Hola mundo" sencilla.</span><span class="sxs-lookup"><span data-stu-id="2c8a2-130">The template creates a simple "Hello World" application.</span></span> <span data-ttu-id="2c8a2-131">Llama al método <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> para mostrar "Hola mundo"</span><span class="sxs-lookup"><span data-stu-id="2c8a2-131">It calls the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method to display "Hello World!"</span></span> <span data-ttu-id="2c8a2-132">en la ventana de terminal.</span><span class="sxs-lookup"><span data-stu-id="2c8a2-132">in the terminal window.</span></span>

<span data-ttu-id="2c8a2-133">El código de plantilla define una clase, `Program`, con un único método, `Main`, que toma una matriz de <xref:System.String> como argumento:</span><span class="sxs-lookup"><span data-stu-id="2c8a2-133">The template code defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument:</span></span>

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

<span data-ttu-id="2c8a2-134">`Main` es el punto de entrada de la aplicación, el método que se llama automáticamente mediante el tiempo de ejecución cuando inicia la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2c8a2-134">`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application.</span></span> <span data-ttu-id="2c8a2-135">Los argumentos de línea de comandos proporcionados cuando se inicia la aplicación están disponibles en la matriz `args`.</span><span class="sxs-lookup"><span data-stu-id="2c8a2-135">Any command-line arguments supplied when the application is launched are available in the `args` array.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="2c8a2-136">Ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="2c8a2-136">Run the app</span></span>

1. <span data-ttu-id="2c8a2-137">Presione <kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>opción</kbd>+<kbd>command</kbd>+<kbd>entrar</kbd>) para ejecutar la aplicación sin depuración.</span><span class="sxs-lookup"><span data-stu-id="2c8a2-137">Press <kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>option</kbd>+<kbd>command</kbd>+<kbd>enter</kbd>) to run the app without debugging.</span></span>

   :::image type="content" source="media/with-visual-studio-mac/visual-studio-mac-output.png" alt-text="El terminal muestra Hola mundo.":::

1. <span data-ttu-id="2c8a2-139">Cierre la ventana de **Terminal**.</span><span class="sxs-lookup"><span data-stu-id="2c8a2-139">Close the **Terminal** window.</span></span>

## <a name="enhance-the-app"></a><span data-ttu-id="2c8a2-140">Mejora de la aplicación</span><span class="sxs-lookup"><span data-stu-id="2c8a2-140">Enhance the app</span></span>

<span data-ttu-id="2c8a2-141">Mejore la aplicación para pedir su nombre al usuario y mostrarlo con la fecha y la hora.</span><span class="sxs-lookup"><span data-stu-id="2c8a2-141">Enhance the application to prompt the user for their name and display it along with the date and time.</span></span>

1. <span data-ttu-id="2c8a2-142">En *Program.cs* , reemplace el contenido del método `Main`, que es la línea que llama a `Console.WriteLine`, por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="2c8a2-142">In *Program.cs* , replace the contents of the `Main` method, which is the line that calls `Console.WriteLine`, with the following code:</span></span>

   :::code language="csharp" source="./snippets/with-visual-studio/csharp/Program.cs" id="MainMethod":::

   <span data-ttu-id="2c8a2-143">Este código muestra un mensaje en la ventana de la consola y espera a que el usuario escriba una cadena y, luego, presione <kbd>Entrar</kbd>.</span><span class="sxs-lookup"><span data-stu-id="2c8a2-143">This code displays a prompt in the console window and waits until the user enters a string followed by the <kbd>enter</kbd> key.</span></span> <span data-ttu-id="2c8a2-144">Almacena esta cadena en una variable denominada `name`.</span><span class="sxs-lookup"><span data-stu-id="2c8a2-144">It stores this string in a variable named `name`.</span></span> <span data-ttu-id="2c8a2-145">También recupera el valor de la propiedad <xref:System.DateTime.Now?displayProperty=nameWithType>, que contiene la hora local actual, y lo asigna a una variable denominada `date`.</span><span class="sxs-lookup"><span data-stu-id="2c8a2-145">It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=nameWithType> property, which contains the current local time, and assigns it to a variable named `date`.</span></span> <span data-ttu-id="2c8a2-146">Asimismo, muestra estos valores en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="2c8a2-146">And it displays these values in the console window.</span></span> <span data-ttu-id="2c8a2-147">Por último, muestra un mensaje en la ventana de la consola y llama al método <xref:System.Console.ReadKey(System.Boolean)?displayProperty=nameWithType> para esperar a la entrada del usuario.</span><span class="sxs-lookup"><span data-stu-id="2c8a2-147">Finally, it displays a prompt in the console window and calls the <xref:System.Console.ReadKey(System.Boolean)?displayProperty=nameWithType> method to wait for user input.</span></span>

   <span data-ttu-id="2c8a2-148">El símbolo `\n` representa un carácter de nueva línea.</span><span class="sxs-lookup"><span data-stu-id="2c8a2-148">The `\n` represents a newline character.</span></span>

   <span data-ttu-id="2c8a2-149">El signo de dólar (`$`) delante de una cadena permite colocar expresiones como nombres de variable entre llaves en la cadena.</span><span class="sxs-lookup"><span data-stu-id="2c8a2-149">The dollar sign (`$`) in front of a string lets you put expressions such as variable names in curly braces in the string.</span></span> <span data-ttu-id="2c8a2-150">El valor de la expresión se inserta en la cadena en lugar de la expresión.</span><span class="sxs-lookup"><span data-stu-id="2c8a2-150">The expression value is inserted into the string in place of the expression.</span></span> <span data-ttu-id="2c8a2-151">Esta sintaxis se conoce como [cadenas interpoladas](../../csharp/language-reference/tokens/interpolated.md).</span><span class="sxs-lookup"><span data-stu-id="2c8a2-151">This syntax is referred to as [interpolated strings](../../csharp/language-reference/tokens/interpolated.md).</span></span>

1. <span data-ttu-id="2c8a2-152">Presione <kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>opción</kbd>+<kbd>command</kbd>+<kbd>entrar</kbd>) para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2c8a2-152">Press <kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>option</kbd>+<kbd>command</kbd>+<kbd>enter</kbd>) to run the app.</span></span>

1. <span data-ttu-id="2c8a2-153">Responda a la solicitud escribiendo un nombre y presionando la tecla <kbd>entrar</kbd>.</span><span class="sxs-lookup"><span data-stu-id="2c8a2-153">Respond to the prompt by entering a name and pressing <kbd>enter</kbd>.</span></span>

   :::image type="content" source="media/with-visual-studio-mac/hello-world-update.png" alt-text="Terminal muestra la salida del programa modificado":::

1. <span data-ttu-id="2c8a2-155">Cierre el terminal.</span><span class="sxs-lookup"><span data-stu-id="2c8a2-155">Close the terminal.</span></span>

## <a name="next-steps"></a><span data-ttu-id="2c8a2-156">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="2c8a2-156">Next steps</span></span>

<span data-ttu-id="2c8a2-157">En este tutorial, ha creado una aplicación de consola de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2c8a2-157">In this tutorial, you created a .NET Core console application.</span></span> <span data-ttu-id="2c8a2-158">En el siguiente tutorial, depurará la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2c8a2-158">In the next tutorial, you debug the app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="2c8a2-159">Depuración de una aplicación de consola de .NET Core con Visual Studio para Mac</span><span class="sxs-lookup"><span data-stu-id="2c8a2-159">Debug a .NET Core console application using Visual Studio for Mac</span></span>](debugging-with-visual-studio-mac.md)
