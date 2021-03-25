---
title: Creación de una aplicación de consola de .NET con Visual Studio Code
description: Aprenda a crear una aplicación de consola de .NET con Visual Studio Code y la CLI de .NET.
ms.date: 11/17/2020
ms.openlocfilehash: 51e5a897985af7576de03659efdd8520cb8e58e6
ms.sourcegitcommit: 1d3af230ec30d8d061be7a887f6ba38a530c4ece
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "102511871"
---
# <a name="tutorial-create-a-net-console-application-using-visual-studio-code"></a><span data-ttu-id="50b24-103">Tutorial: Creación de una aplicación de consola de .NET con Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="50b24-103">Tutorial: Create a .NET console application using Visual Studio Code</span></span>

<span data-ttu-id="50b24-104">En este tutorial se muestra cómo crear y ejecutar una aplicación de consola de .NET mediante Visual Studio Code y la CLI de .NET.</span><span class="sxs-lookup"><span data-stu-id="50b24-104">This tutorial shows how to create and run a .NET console application by using Visual Studio Code and the .NET CLI.</span></span> <span data-ttu-id="50b24-105">Las tareas de proyecto, como crear, compilar y ejecutar un proyecto, se realizan mediante la CLI de .NET.</span><span class="sxs-lookup"><span data-stu-id="50b24-105">Project tasks, such as creating, compiling, and running a project are done by using the .NET CLI.</span></span> <span data-ttu-id="50b24-106">Puede seguir este tutorial con un editor de código diferente y ejecutar comandos en un terminal si lo prefiere.</span><span class="sxs-lookup"><span data-stu-id="50b24-106">You can follow this tutorial with a different code editor and run commands in a terminal if you prefer.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="50b24-107">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="50b24-107">Prerequisites</span></span>

1. <span data-ttu-id="50b24-108">[Visual Studio Code](https://code.visualstudio.com/) con la [extensión de C#](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) instalada.</span><span class="sxs-lookup"><span data-stu-id="50b24-108">[Visual Studio Code](https://code.visualstudio.com/) with the [C# extension](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) installed.</span></span> <span data-ttu-id="50b24-109">Para saber cómo instalar extensiones en Visual Studio Code, vea el [Marketplace de extensiones de VS Code](https://code.visualstudio.com/docs/editor/extension-gallery).</span><span class="sxs-lookup"><span data-stu-id="50b24-109">For information about how to install extensions on Visual Studio Code, see [VS Code Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery).</span></span>
2. <span data-ttu-id="50b24-110">[SDK de .NET 5.0 o posterior](https://dotnet.microsoft.com/download)</span><span class="sxs-lookup"><span data-stu-id="50b24-110">The [.NET 5.0 SDK or later](https://dotnet.microsoft.com/download)</span></span>

## <a name="create-the-app"></a><span data-ttu-id="50b24-111">Creación de la aplicación</span><span class="sxs-lookup"><span data-stu-id="50b24-111">Create the app</span></span>

<span data-ttu-id="50b24-112">Cree un proyecto de aplicación de consola de .NET denominado "HelloWorld".</span><span class="sxs-lookup"><span data-stu-id="50b24-112">Create a .NET console app project named "HelloWorld".</span></span>

1. <span data-ttu-id="50b24-113">Inicie Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="50b24-113">Start Visual Studio Code.</span></span>

1. <span data-ttu-id="50b24-114">Seleccione **Archivo** > **Abrir carpeta** (**Archivo** > **Abrir...** en macOS) en el menú principal.</span><span class="sxs-lookup"><span data-stu-id="50b24-114">Select **File** > **Open Folder** (**File** > **Open...** on macOS) from the main menu.</span></span>

1. <span data-ttu-id="50b24-115">En el cuadro de diálogo **Abrir carpeta**, cree una carpeta de *HelloWorld* y haga clic en **Seleccionar carpeta** (**Abrir** en macOS).</span><span class="sxs-lookup"><span data-stu-id="50b24-115">In the **Open Folder** dialog, create a *HelloWorld* folder and click **Select Folder** (**Open** on macOS).</span></span>

   <span data-ttu-id="50b24-116">De forma predeterminada, el nombre de la carpeta se convierte en el nombre del proyecto y del espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="50b24-116">The folder name becomes the project name and the namespace name by default.</span></span> <span data-ttu-id="50b24-117">Más adelante en el tutorial, agregará código que supone que el espacio de nombres del proyecto es `HelloWorld`.</span><span class="sxs-lookup"><span data-stu-id="50b24-117">You'll add code later in the tutorial that assumes the project namespace is `HelloWorld`.</span></span>

1. <span data-ttu-id="50b24-118">Para abrir el **Terminal**  en Visual Studio Code, seleccione **Ver** > **Terminal** en el menú principal.</span><span class="sxs-lookup"><span data-stu-id="50b24-118">Open the **Terminal** in Visual Studio Code by selecting **View** > **Terminal** from the main menu.</span></span>

   <span data-ttu-id="50b24-119">Se abre el **Terminal** con el símbolo del sistema en la carpeta *HelloWorld*.</span><span class="sxs-lookup"><span data-stu-id="50b24-119">The **Terminal** opens with the command prompt in the *HelloWorld* folder.</span></span>

1. <span data-ttu-id="50b24-120">En el **Terminal**, escriba este comando:</span><span class="sxs-lookup"><span data-stu-id="50b24-120">In the **Terminal**, enter the following command:</span></span>

   ```dotnetcli
   dotnet new console
   ```

<span data-ttu-id="50b24-121">La plantilla crea una aplicación "Hola mundo" sencilla.</span><span class="sxs-lookup"><span data-stu-id="50b24-121">The template creates a simple "Hello World" application.</span></span> <span data-ttu-id="50b24-122">Llama al método <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> para mostrar ":::no-loc text="Hello World!":::" en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="50b24-122">It calls the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method to display ":::no-loc text="Hello World!":::" in the console window.</span></span>

<span data-ttu-id="50b24-123">El código de plantilla define una clase, `Program`, con un solo método, `Main`, que toma una matriz de <xref:System.String> como argumento:</span><span class="sxs-lookup"><span data-stu-id="50b24-123">The template code defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument:</span></span>

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

<span data-ttu-id="50b24-124">`Main` es el punto de entrada de la aplicación, el método que se llama automáticamente mediante el tiempo de ejecución cuando inicia la aplicación.</span><span class="sxs-lookup"><span data-stu-id="50b24-124">`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application.</span></span> <span data-ttu-id="50b24-125">Los argumentos de línea de comandos proporcionados cuando se inicia la aplicación están disponibles en la matriz *args*.</span><span class="sxs-lookup"><span data-stu-id="50b24-125">Any command-line arguments supplied when the application is launched are available in the *args* array.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="50b24-126">Ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="50b24-126">Run the app</span></span>

<span data-ttu-id="50b24-127">Ejecute este comando en el **Terminal**:</span><span class="sxs-lookup"><span data-stu-id="50b24-127">Run the following command in the **Terminal**:</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="50b24-128">El programa muestra "Hola mundo"</span><span class="sxs-lookup"><span data-stu-id="50b24-128">The program displays "Hello World!"</span></span> <span data-ttu-id="50b24-129">y finaliza.</span><span class="sxs-lookup"><span data-stu-id="50b24-129">and ends.</span></span>

![El comando de ejecución de dotnet](media/with-visual-studio-code/dotnet-run-command.png)

## <a name="enhance-the-app"></a><span data-ttu-id="50b24-131">Mejora de la aplicación</span><span class="sxs-lookup"><span data-stu-id="50b24-131">Enhance the app</span></span>

<span data-ttu-id="50b24-132">Mejore la aplicación para pedir su nombre al usuario y mostrarlo con la fecha y la hora.</span><span class="sxs-lookup"><span data-stu-id="50b24-132">Enhance the application to prompt the user for their name and display it along with the date and time.</span></span>

1. <span data-ttu-id="50b24-133">Haga clic en el archivo *Program.cs* para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="50b24-133">Open *Program.cs* by clicking on it.</span></span>

   <span data-ttu-id="50b24-134">La primera vez que se abre un archivo de C# en Visual Studio Code, se carga [OmniSharp](https://www.omnisharp.net/) en el editor.</span><span class="sxs-lookup"><span data-stu-id="50b24-134">The first time you open a C# file in Visual Studio Code, [OmniSharp](https://www.omnisharp.net/) loads in the editor.</span></span>

   ![Abrir el archivo Program.cs](media/with-visual-studio-code/open-program-cs.png)

1. <span data-ttu-id="50b24-136">Seleccione **Sí** cuando Visual Studio Code le pida que agregue los recursos que faltan para compilar y depurar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="50b24-136">Select **Yes** when Visual Studio Code prompts you to add the missing assets to build and debug your app.</span></span>

   ![Solicitud de los recursos que faltan](media/with-visual-studio-code/missing-assets.png)

1. <span data-ttu-id="50b24-138">Reemplace el contenido del método `Main` en *Program.cs*, que es la línea que llama a `Console.WriteLine`, por este código:</span><span class="sxs-lookup"><span data-stu-id="50b24-138">Replace the contents of the `Main` method in *Program.cs*, which is the line that calls `Console.WriteLine`, with the following code:</span></span>

   :::code language="csharp" source="./snippets/with-visual-studio/csharp/Program.cs" id="MainMethod":::

   <span data-ttu-id="50b24-139">Este código muestra un mensaje en la ventana de la consola y espera a que el usuario escriba una cadena y, luego, presione <kbd>Entrar</kbd>.</span><span class="sxs-lookup"><span data-stu-id="50b24-139">This code displays a prompt in the console window and waits until the user enters a string followed by the <kbd>Enter</kbd> key.</span></span> <span data-ttu-id="50b24-140">Almacena esta cadena en una variable denominada `name`.</span><span class="sxs-lookup"><span data-stu-id="50b24-140">It stores this string in a variable named `name`.</span></span> <span data-ttu-id="50b24-141">También recupera el valor de la propiedad <xref:System.DateTime.Now?displayProperty=nameWithType>, que contiene la hora local actual, y lo asigna a una variable denominada `date`.</span><span class="sxs-lookup"><span data-stu-id="50b24-141">It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=nameWithType> property, which contains the current local time, and assigns it to a variable named `date`.</span></span> <span data-ttu-id="50b24-142">Asimismo, muestra estos valores en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="50b24-142">And it displays these values in the console window.</span></span> <span data-ttu-id="50b24-143">Por último, muestra un mensaje en la ventana de la consola y llama al método <xref:System.Console.ReadKey(System.Boolean)?displayProperty=nameWithType> para esperar a la entrada del usuario.</span><span class="sxs-lookup"><span data-stu-id="50b24-143">Finally, it displays a prompt in the console window and calls the <xref:System.Console.ReadKey(System.Boolean)?displayProperty=nameWithType> method to wait for user input.</span></span>

   <span data-ttu-id="50b24-144"><xref:System.Environment.NewLine> es una manera independiente de la plataforma y del lenguaje de representar un salto de línea.</span><span class="sxs-lookup"><span data-stu-id="50b24-144"><xref:System.Environment.NewLine> is a platform-independent and language-independent way to represent a line break.</span></span> <span data-ttu-id="50b24-145">Las alternativas son `\n` en C# y `vbCrLf` en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="50b24-145">Alternatives are `\n` in C# and `vbCrLf` in Visual Basic.</span></span>

   <span data-ttu-id="50b24-146">El signo de dólar (`$`) delante de una cadena permite colocar expresiones como nombres de variable entre llaves en la cadena.</span><span class="sxs-lookup"><span data-stu-id="50b24-146">The dollar sign (`$`) in front of a string lets you put expressions such as variable names in curly braces in the string.</span></span> <span data-ttu-id="50b24-147">El valor de la expresión se inserta en la cadena en lugar de la expresión.</span><span class="sxs-lookup"><span data-stu-id="50b24-147">The expression value is inserted into the string in place of the expression.</span></span> <span data-ttu-id="50b24-148">Esta sintaxis se conoce como [cadenas interpoladas](../../csharp/language-reference/tokens/interpolated.md).</span><span class="sxs-lookup"><span data-stu-id="50b24-148">This syntax is referred to as [interpolated strings](../../csharp/language-reference/tokens/interpolated.md).</span></span>

1. <span data-ttu-id="50b24-149">Guarde los cambios.</span><span class="sxs-lookup"><span data-stu-id="50b24-149">Save your changes.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="50b24-150">En Visual Studio Code, tiene que guardar los cambios explícitamente.</span><span class="sxs-lookup"><span data-stu-id="50b24-150">In Visual Studio Code, you have to explicitly save changes.</span></span> <span data-ttu-id="50b24-151">A diferencia de Visual Studio, los cambios de los archivos no se guardan automáticamente al compilar y ejecutar una aplicación.</span><span class="sxs-lookup"><span data-stu-id="50b24-151">Unlike Visual Studio, file changes are not automatically saved when you build and run an app.</span></span>

1. <span data-ttu-id="50b24-152">Ejecute el programa otra vez:</span><span class="sxs-lookup"><span data-stu-id="50b24-152">Run the program again:</span></span>

   ```dotnetcli
   dotnet run
   ```

1. <span data-ttu-id="50b24-153">Responda a la solicitud escribiendo un nombre y presionando la tecla <kbd>Entrar</kbd>.</span><span class="sxs-lookup"><span data-stu-id="50b24-153">Respond to the prompt by entering a name and pressing the <kbd>Enter</kbd> key.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/run-modified-program.png" alt-text="Ventana del Terminal con el resultado del programa modificado":::

1. <span data-ttu-id="50b24-155">Presione cualquier tecla para salir de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="50b24-155">Press any key to exit the program.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="50b24-156">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="50b24-156">Additional resources</span></span>

- <span data-ttu-id="50b24-157">[Setting up Visual Studio Code](https://code.visualstudio.com/docs/setup/setup-overview) (Configuración de Visual Studio Code)</span><span class="sxs-lookup"><span data-stu-id="50b24-157">[Setting up Visual Studio Code](https://code.visualstudio.com/docs/setup/setup-overview)</span></span>

## <a name="next-steps"></a><span data-ttu-id="50b24-158">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="50b24-158">Next steps</span></span>

<span data-ttu-id="50b24-159">En este tutorial, ha creado una aplicación de consola de .NET.</span><span class="sxs-lookup"><span data-stu-id="50b24-159">In this tutorial, you created a .NET console application.</span></span> <span data-ttu-id="50b24-160">En el siguiente tutorial, depurará la aplicación.</span><span class="sxs-lookup"><span data-stu-id="50b24-160">In the next tutorial, you debug the app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="50b24-161">Depuración de una aplicación de consola de .NET con Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="50b24-161">Debug a .NET console application using Visual Studio Code</span></span>](debugging-with-visual-studio-code.md)
