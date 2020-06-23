---
title: Creación de una aplicación de consola de .NET Core con Visual Studio para Mac
description: Aprenda a crear una aplicación de consola de .NET Core con Visual Studio para Mac.
ms.date: 06/02/2020
ms.openlocfilehash: 9cab838eaab2c59d8a0270267514f57acb7c60fb
ms.sourcegitcommit: 1eae045421d9ea2bfc82aaccfa5b1ff1b8c9e0e4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "84811670"
---
# <a name="tutorial-create-a-net-core-console-application-using-visual-studio-for-mac"></a><span data-ttu-id="df91d-103">Tutorial: Creación de una aplicación de consola de .NET Core con Visual Studio para Mac</span><span class="sxs-lookup"><span data-stu-id="df91d-103">Tutorial: Create a .NET Core console application using Visual Studio for Mac</span></span>

<span data-ttu-id="df91d-104">En este tutorial se muestra cómo crear y ejecutar una aplicación de consola de .NET Core en Visual Studio para Mac.</span><span class="sxs-lookup"><span data-stu-id="df91d-104">This tutorial shows how to create and run a .NET Core console application using Visual Studio for Mac.</span></span>

> [!NOTE]
> <span data-ttu-id="df91d-105">Sus comentarios son muy importantes.</span><span class="sxs-lookup"><span data-stu-id="df91d-105">Your feedback is highly valued.</span></span> <span data-ttu-id="df91d-106">Hay dos maneras de proporcionar comentarios al equipo de desarrollo de Visual Studio para Mac:</span><span class="sxs-lookup"><span data-stu-id="df91d-106">There are two ways you can provide feedback to the development team on Visual Studio for Mac:</span></span>
>
> * <span data-ttu-id="df91d-107">En Visual Studio para Mac, seleccione **Ayuda** > **Notificar un problema** en el menú o **Notificar un problema** desde la pantalla de bienvenida, que abre una ventana para presentar un informe de errores.</span><span class="sxs-lookup"><span data-stu-id="df91d-107">In Visual Studio for Mac, select **Help** > **Report a Problem** from the menu or **Report a Problem** from the Welcome screen, which will open a window for filing a bug report.</span></span> <span data-ttu-id="df91d-108">Puede realizar un seguimiento de sus comentarios en el portal de la [Comunidad de desarrolladores](https://developercommunity.visualstudio.com/spaces/8/index.html).</span><span class="sxs-lookup"><span data-stu-id="df91d-108">You can track your feedback in the [Developer Community](https://developercommunity.visualstudio.com/spaces/8/index.html) portal.</span></span>
> * <span data-ttu-id="df91d-109">Para hacer una sugerencia, seleccione **Ayuda** > **Aportar una sugerencia** en el menú o **Aportar una sugerencia** desde la pantalla de bienvenida, que le lleva a la [página web de la Comunidad de desarrolladores de Visual Studio para Mac](https://developercommunity.visualstudio.com/content/idea/post.html?space=41).</span><span class="sxs-lookup"><span data-stu-id="df91d-109">To make a suggestion, select **Help** > **Provide a Suggestion** from the menu or **Provide a Suggestion** from the Welcome screen, which will take you to the [Visual Studio for Mac Developer Community webpage](https://developercommunity.visualstudio.com/content/idea/post.html?space=41).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="df91d-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="df91d-110">Prerequisites</span></span>

* <span data-ttu-id="df91d-111">[Visual Studio para Mac, versión 8.6 o posterior](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).</span><span class="sxs-lookup"><span data-stu-id="df91d-111">[Visual Studio for Mac version 8.6 or later](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).</span></span> <span data-ttu-id="df91d-112">Seleccione la opción para instalar .NET Core.</span><span class="sxs-lookup"><span data-stu-id="df91d-112">Select the option to install .NET Core.</span></span> <span data-ttu-id="df91d-113">La instalación de Xamarin es opcional para el desarrollo de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="df91d-113">Installing Xamarin is optional for .NET Core development.</span></span> <span data-ttu-id="df91d-114">Para obtener más información, vea los siguientes recursos:</span><span class="sxs-lookup"><span data-stu-id="df91d-114">For more information, see the following resources:</span></span>

  * <span data-ttu-id="df91d-115">[Tutorial: Instalación de Visual Studio para Mac](/visualstudio/mac/installation).</span><span class="sxs-lookup"><span data-stu-id="df91d-115">[Tutorial: Install Visual Studio for Mac](/visualstudio/mac/installation).</span></span>
  * <span data-ttu-id="df91d-116">[Versiones de macOS compatibles](../install/dependencies.md?pivots=os-macos).</span><span class="sxs-lookup"><span data-stu-id="df91d-116">[Supported macOS versions](../install/dependencies.md?pivots=os-macos).</span></span>
  * <span data-ttu-id="df91d-117">[Versiones de .NET Core compatibles con Visual Studio para Mac](/visualstudio/mac/net-core-support).</span><span class="sxs-lookup"><span data-stu-id="df91d-117">[.NET Core versions supported by Visual Studio for Mac](/visualstudio/mac/net-core-support).</span></span>

## <a name="create-the-app"></a><span data-ttu-id="df91d-118">Creación de la aplicación</span><span class="sxs-lookup"><span data-stu-id="df91d-118">Create the app</span></span>

<span data-ttu-id="df91d-119">Cree un proyecto de aplicación de consola de .NET Core denominado "HelloWorld".</span><span class="sxs-lookup"><span data-stu-id="df91d-119">Create a .NET Core console app project named "HelloWorld".</span></span>

1. <span data-ttu-id="df91d-120">Inicie Visual Studio para Mac:</span><span class="sxs-lookup"><span data-stu-id="df91d-120">Start Visual Studio for Mac.</span></span>

1. <span data-ttu-id="df91d-121">Seleccione **Nuevo** en la ventana de inicio.</span><span class="sxs-lookup"><span data-stu-id="df91d-121">Select **New** in the start window.</span></span>

   :::image type="content" source="media/with-visual-studio-mac/visual-studio-mac-new-project.png" alt-text="Botón Nuevo en la pantalla Inicio de Visual Studio para Mac":::

1. <span data-ttu-id="df91d-123">En el cuadro de diálogo **Nuevo proyecto**, seleccione **Aplicación** en el nodo **Web and Console** (Web y consola).</span><span class="sxs-lookup"><span data-stu-id="df91d-123">In the **New Project** dialog, select **App** under the **Web and Console** node.</span></span> <span data-ttu-id="df91d-124">Seleccione la plantilla **Aplicación de consola** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="df91d-124">Select the **Console Application** template, and select **Next**.</span></span>

   :::image type="content" source="media/with-visual-studio-mac/visual-studio-mac-new-dialog.png" alt-text="Lista de plantillas de Nuevo proyecto":::

1. <span data-ttu-id="df91d-126">En el cuadro de diálogo **Plataforma de destino** del cuadro de diálogo para **configurar la nueva aplicación de consola**, seleccione **.NET Core 3.1** y seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="df91d-126">In the **Target Framework** drop-down of the **Configure your new Console Application** dialog, select **.NET Core 3.1**, and select **Next**.</span></span>

   :::image type="content" source="media/with-visual-studio-mac/target-framework.png" alt-text="Selección de la plataforma de destino":::

1. <span data-ttu-id="df91d-128">Escriba "HelloWorld" en **Nombre del proyecto** y seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="df91d-128">Type "HelloWorld" for the **Project Name**, and select **Create**.</span></span>

   :::image type="content" source="media/with-visual-studio-mac/visual-studio-mac-new-options.png" alt-text="Cuadro de diálogo de configuración de la nueva aplicación de consola":::

<span data-ttu-id="df91d-130">La plantilla crea una aplicación "Hola mundo" sencilla.</span><span class="sxs-lookup"><span data-stu-id="df91d-130">The template creates a simple "Hello World" application.</span></span> <span data-ttu-id="df91d-131">Llama al método <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> para mostrar "Hola mundo"</span><span class="sxs-lookup"><span data-stu-id="df91d-131">It calls the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method to display "Hello World!"</span></span> <span data-ttu-id="df91d-132">en la ventana de terminal.</span><span class="sxs-lookup"><span data-stu-id="df91d-132">in the terminal window.</span></span>

<span data-ttu-id="df91d-133">El código de plantilla define una clase, `Program`, con un único método, `Main`, que toma una matriz de <xref:System.String> como argumento:</span><span class="sxs-lookup"><span data-stu-id="df91d-133">The template code defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument:</span></span>

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

<span data-ttu-id="df91d-134">`Main` es el punto de entrada de la aplicación, el método que se llama automáticamente mediante el tiempo de ejecución cuando inicia la aplicación.</span><span class="sxs-lookup"><span data-stu-id="df91d-134">`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application.</span></span> <span data-ttu-id="df91d-135">Los argumentos de línea de comandos proporcionados cuando se inicia la aplicación están disponibles en la matriz `args`.</span><span class="sxs-lookup"><span data-stu-id="df91d-135">Any command-line arguments supplied when the application is launched are available in the `args` array.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="df91d-136">Ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="df91d-136">Run the app</span></span>

1. <span data-ttu-id="df91d-137">Presione <kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>opción</kbd>+<kbd>command</kbd>+<kbd>entrar</kbd>) para ejecutar la aplicación sin depuración.</span><span class="sxs-lookup"><span data-stu-id="df91d-137">Press <kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>option</kbd>+<kbd>command</kbd>+<kbd>enter</kbd>) to run the app without debugging.</span></span>

   :::image type="content" source="media/with-visual-studio-mac/visual-studio-mac-output.png" alt-text="El terminal muestra Hola mundo.":::

1. <span data-ttu-id="df91d-139">Cierre la ventana de **Terminal**.</span><span class="sxs-lookup"><span data-stu-id="df91d-139">Close the **Terminal** window.</span></span>

## <a name="enhance-the-app"></a><span data-ttu-id="df91d-140">Mejora de la aplicación</span><span class="sxs-lookup"><span data-stu-id="df91d-140">Enhance the app</span></span>

<span data-ttu-id="df91d-141">Mejore la aplicación para pedir su nombre al usuario y mostrarlo con la fecha y la hora.</span><span class="sxs-lookup"><span data-stu-id="df91d-141">Enhance the application to prompt the user for their name and display it along with the date and time.</span></span>

1. <span data-ttu-id="df91d-142">En *Program.cs*, reemplace el contenido del método `Main`, que es la línea que llama a `Console.WriteLine`, por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="df91d-142">In *Program.cs*, replace the contents of the `Main` method, which is the line that calls `Console.WriteLine`, with the following code:</span></span>

   :::code language="csharp" source="./snippets/with-visual-studio/csharp/Program.cs" id="MainMethod":::

   <span data-ttu-id="df91d-143">Este código muestra "What is your name?"</span><span class="sxs-lookup"><span data-stu-id="df91d-143">This code displays "What is your name?"</span></span> <span data-ttu-id="df91d-144">en la ventana de la consola y espera a que el usuario escriba una cadena y luego presione <kbd>entrar</kbd>.</span><span class="sxs-lookup"><span data-stu-id="df91d-144">in the console window and waits until the user enters a string followed by the <kbd>enter</kbd> key.</span></span> <span data-ttu-id="df91d-145">Almacena esta cadena en una variable denominada `name`.</span><span class="sxs-lookup"><span data-stu-id="df91d-145">It stores this string in a variable named `name`.</span></span> <span data-ttu-id="df91d-146">También recupera el valor de la propiedad <xref:System.DateTime.Now?displayProperty=nameWithType>, que contiene la hora local actual, y lo asigna a una variable denominada `date`.</span><span class="sxs-lookup"><span data-stu-id="df91d-146">It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=nameWithType> property, which contains the current local time, and assigns it to a variable named `date`.</span></span> <span data-ttu-id="df91d-147">Por último, muestra estos valores en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="df91d-147">Finally, it displays these values in the console window.</span></span>

   <span data-ttu-id="df91d-148">El símbolo `\n` representa un carácter de nueva línea.</span><span class="sxs-lookup"><span data-stu-id="df91d-148">The `\n` represents a newline character.</span></span>

   <span data-ttu-id="df91d-149">El signo de dólar (`$`) delante de una cadena permite colocar expresiones como nombres de variable entre llaves en la cadena.</span><span class="sxs-lookup"><span data-stu-id="df91d-149">The dollar sign (`$`) in front of a string lets you put expressions such as variable names in curly braces in the string.</span></span> <span data-ttu-id="df91d-150">El valor de la expresión se inserta en la cadena en lugar de la expresión.</span><span class="sxs-lookup"><span data-stu-id="df91d-150">The expression value is inserted into the string in place of the expression.</span></span> <span data-ttu-id="df91d-151">Esta sintaxis se conoce como [cadenas interpoladas](../../csharp/language-reference/tokens/interpolated.md).</span><span class="sxs-lookup"><span data-stu-id="df91d-151">This syntax is referred to as [interpolated strings](../../csharp/language-reference/tokens/interpolated.md).</span></span>

1. <span data-ttu-id="df91d-152">Presione <kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>opción</kbd>+<kbd>command</kbd>+<kbd>entrar</kbd>) para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="df91d-152">Press <kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>option</kbd>+<kbd>command</kbd>+<kbd>enter</kbd>) to run the app.</span></span>

1. <span data-ttu-id="df91d-153">Responda a la solicitud escribiendo un nombre y presionando la tecla <kbd>entrar</kbd>.</span><span class="sxs-lookup"><span data-stu-id="df91d-153">Respond to the prompt by entering a name and pressing <kbd>enter</kbd>.</span></span>

   :::image type="content" source="media/with-visual-studio-mac/hello-world-update.png" alt-text="Terminal muestra la salida del programa modificado":::

1. <span data-ttu-id="df91d-155">Cierre el terminal.</span><span class="sxs-lookup"><span data-stu-id="df91d-155">Close the terminal.</span></span>

## <a name="next-steps"></a><span data-ttu-id="df91d-156">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="df91d-156">Next steps</span></span>

<span data-ttu-id="df91d-157">En este tutorial, ha creado una aplicación de consola de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="df91d-157">In this tutorial, you created a .NET Core console application.</span></span> <span data-ttu-id="df91d-158">En el siguiente tutorial, depurará la aplicación.</span><span class="sxs-lookup"><span data-stu-id="df91d-158">In the next tutorial, you debug the app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="df91d-159">Depuración de una aplicación de consola de .NET Core con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="df91d-159">Debug a .NET Core console application in Visual Studio</span></span>](debugging-with-visual-studio-mac.md)
