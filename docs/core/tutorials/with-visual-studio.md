---
title: Creación de una aplicación de consola de .NET con Visual Studio
description: Obtenga información sobre cómo crear una aplicación de consola de .NET con C# o Visual Basic mediante Visual Studio.
ms.date: 06/08/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: a3a27c1baaab135108ef475d77c35d607c45fa82
ms.sourcegitcommit: 4d5e25a46aa7cd0d29b4b9227b92987354d444c4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2021
ms.locfileid: "98794796"
---
# <a name="tutorial-create-a-net-console-application-using-visual-studio"></a><span data-ttu-id="ebd6f-103">Tutorial: Creación de una aplicación de consola de .NET con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ebd6f-103">Tutorial: Create a .NET console application using Visual Studio</span></span>

<span data-ttu-id="ebd6f-104">En este tutorial se muestra cómo crear y ejecutar una aplicación de consola de .NET en Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="ebd6f-104">This tutorial shows how to create and run a .NET console application in Visual Studio 2019.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ebd6f-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="ebd6f-105">Prerequisites</span></span>

- <span data-ttu-id="ebd6f-106">[Visual Studio 2019, versión 16.8 o posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) con la carga de trabajo **Desarrollo multiplataforma de .NET Core** instalada.</span><span class="sxs-lookup"><span data-stu-id="ebd6f-106">[Visual Studio 2019 version 16.8 or a later version](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the **.NET Core cross-platform development** workload installed.</span></span> <span data-ttu-id="ebd6f-107">El SDK de .NET 5.0 se instala automáticamente al seleccionar esta carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ebd6f-107">The .NET 5.0 SDK is automatically installed when you select this workload.</span></span>

  <span data-ttu-id="ebd6f-108">Para obtener más información, vea [Instalación del SDK de .NET con Visual Studio](../install/windows.md#install-with-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="ebd6f-108">For more information, see [Install the .NET SDK with Visual Studio](../install/windows.md#install-with-visual-studio).</span></span>

## <a name="create-the-app"></a><span data-ttu-id="ebd6f-109">Creación de la aplicación</span><span class="sxs-lookup"><span data-stu-id="ebd6f-109">Create the app</span></span>

<span data-ttu-id="ebd6f-110">Cree un proyecto de aplicación de consola de .NET denominado "HelloWorld".</span><span class="sxs-lookup"><span data-stu-id="ebd6f-110">Create a .NET console app project named "HelloWorld".</span></span>

1. <span data-ttu-id="ebd6f-111">Inicie Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="ebd6f-111">Start Visual Studio 2019.</span></span>

1. <span data-ttu-id="ebd6f-112">Seleccione **Herramientas** > **Opciones** > **Entorno** > **Características de vista previa** y después **Mostrar todas las plantillas de .NET Core en el nuevo proyecto (requiere reinicio)** .</span><span class="sxs-lookup"><span data-stu-id="ebd6f-112">Select **Tools** > **Options** > **Environment** > **Preview features**, and then select **Show all .NET Core templates in the New project (requires restart)**.</span></span>

   :::image type="content" source="media/with-visual-studio/dotnet-options.png" alt-text="Opción Mostrar todas las plantillas de .NET":::

1. <span data-ttu-id="ebd6f-114">Cierre y vuelva a abrir Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ebd6f-114">Close and reopen Visual Studio.</span></span>

1. <span data-ttu-id="ebd6f-115">En la página de inicio, elija **Crear un proyecto nuevo**.</span><span class="sxs-lookup"><span data-stu-id="ebd6f-115">On the start page, choose **Create a new project**.</span></span>

   :::image type="content" source="./media/with-visual-studio/start-window.png" alt-text="Botón Crear un proyecto nuevo seleccionado en la página de inicio de Visual Studio":::

1. <span data-ttu-id="ebd6f-117">En la página **Crear un proyecto**, escriba **consola** en el cuadro de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="ebd6f-117">On the **Create a new project** page, enter **console** in the search box.</span></span> <span data-ttu-id="ebd6f-118">Después, elija **C#** o **Visual Basic** en la lista de lenguajes y luego elija **Todas las plataformas** en la lista de plataformas.</span><span class="sxs-lookup"><span data-stu-id="ebd6f-118">Next, choose **C#** or **Visual Basic** from the language list, and then choose **All platforms** from the platform list.</span></span> <span data-ttu-id="ebd6f-119">Elija la plantilla **Aplicación de consola** y, después, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ebd6f-119">Choose the **Console Application** template, and then choose **Next**.</span></span>

   :::image type="content" source="./media/with-visual-studio/create-new-project.png" alt-text="Creación de una nueva ventana de proyecto con filtros seleccionados":::

   > [!TIP]
   > <span data-ttu-id="ebd6f-121">Si no ve las plantillas de .NET, es probable que falte la carga de trabajo necesaria.</span><span class="sxs-lookup"><span data-stu-id="ebd6f-121">If you don't see the .NET templates, you're probably missing the required workload.</span></span> <span data-ttu-id="ebd6f-122">En el mensaje **¿No encuentra lo que busca?** , elija el vínculo **Instalar más herramientas y características**.</span><span class="sxs-lookup"><span data-stu-id="ebd6f-122">Under the **Not finding what you're looking for?** message, choose the **Install more tools and features** link.</span></span> <span data-ttu-id="ebd6f-123">Se abre el Instalador de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ebd6f-123">The Visual Studio Installer opens.</span></span> <span data-ttu-id="ebd6f-124">Asegúrese de que tiene instalada la carga de trabajo **Desarrollo multiplataforma de .NET Core**.</span><span class="sxs-lookup"><span data-stu-id="ebd6f-124">Make sure you have the **.NET Core cross-platform development** workload installed.</span></span>

1. <span data-ttu-id="ebd6f-125">En el cuadro de diálogo **Configurar el nuevo proyecto**, escriba **HelloWorld** en el cuadro **Nombre del proyecto**.</span><span class="sxs-lookup"><span data-stu-id="ebd6f-125">In the **Configure your new project** dialog,  enter **HelloWorld** in the **Project name** box.</span></span> <span data-ttu-id="ebd6f-126">Luego, elija **Crear**.</span><span class="sxs-lookup"><span data-stu-id="ebd6f-126">Then choose **Create**.</span></span>

   :::image type="content" source="./media/with-visual-studio/configure-new-project.png" alt-text="Configuración de la ventana de nuevo proyecto con los campos de nombre de proyecto, ubicación y nombre de la solución":::

1. <span data-ttu-id="ebd6f-128">En el cuadro de diálogo **Información adicional**, seleccione **.NET 5.0 (actual)** y después **Crear**.</span><span class="sxs-lookup"><span data-stu-id="ebd6f-128">In the **Additional information** dialog, select **.NET 5.0 (Current)**, and then select **Create**.</span></span>

   :::image type="content" source="media/with-visual-studio/additional-info.png" alt-text="Cuadro de diálogo Información adicional":::

<span data-ttu-id="ebd6f-130">La plantilla crea una aplicación "Hola mundo" sencilla.</span><span class="sxs-lookup"><span data-stu-id="ebd6f-130">The template creates a simple "Hello World" application.</span></span> <span data-ttu-id="ebd6f-131">Llama al método <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> para mostrar "Hola mundo"</span><span class="sxs-lookup"><span data-stu-id="ebd6f-131">It calls the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method to display "Hello World!"</span></span> <span data-ttu-id="ebd6f-132">en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="ebd6f-132">in the console window.</span></span>

<span data-ttu-id="ebd6f-133">El código de plantilla define una clase, `Program`, con un único método, `Main`, que toma una matriz de <xref:System.String> como argumento:</span><span class="sxs-lookup"><span data-stu-id="ebd6f-133">The template code defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument:</span></span>

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

<span data-ttu-id="ebd6f-134">`Main` es el punto de entrada de la aplicación, el método que se llama automáticamente mediante el tiempo de ejecución cuando inicia la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ebd6f-134">`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application.</span></span> <span data-ttu-id="ebd6f-135">Los argumentos de línea de comandos proporcionados cuando se inicia la aplicación están disponibles en la matriz *args*.</span><span class="sxs-lookup"><span data-stu-id="ebd6f-135">Any command-line arguments supplied when the application is launched are available in the *args* array.</span></span>

<span data-ttu-id="ebd6f-136">Si no se muestra el idioma que quiere usar, cambie el selector de idioma en la parte superior de la página.</span><span class="sxs-lookup"><span data-stu-id="ebd6f-136">If the language you want to use is not shown, change the language selector at the top of the page.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="ebd6f-137">Ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="ebd6f-137">Run the app</span></span>

1. <span data-ttu-id="ebd6f-138">Presione <kbd>Ctrl</kbd>+<kbd>F5</kbd> para ejecutar el programa sin depurar.</span><span class="sxs-lookup"><span data-stu-id="ebd6f-138">Press <kbd>Ctrl</kbd>+<kbd>F5</kbd> to run the program without debugging.</span></span>

   <span data-ttu-id="ebd6f-139">Se abre la ventana de la consola con el texto "Hello World"</span><span class="sxs-lookup"><span data-stu-id="ebd6f-139">A console window opens with the text "Hello World!"</span></span> <span data-ttu-id="ebd6f-140">impreso en la pantalla.</span><span class="sxs-lookup"><span data-stu-id="ebd6f-140">printed on the screen.</span></span>

   :::image type="content" source="./media/with-visual-studio/hello-world-console.png" alt-text="Ventana de la consola que muestra Hola mundo Presione cualquier tecla para continuar":::

1. <span data-ttu-id="ebd6f-142">Presione cualquier tecla para cerrar la ventana de consola.</span><span class="sxs-lookup"><span data-stu-id="ebd6f-142">Press any key to close the console window.</span></span>

## <a name="enhance-the-app"></a><span data-ttu-id="ebd6f-143">Mejora de la aplicación</span><span class="sxs-lookup"><span data-stu-id="ebd6f-143">Enhance the app</span></span>

<span data-ttu-id="ebd6f-144">Mejore la aplicación para pedir su nombre al usuario y mostrarlo con la fecha y la hora.</span><span class="sxs-lookup"><span data-stu-id="ebd6f-144">Enhance the application to prompt the user for their name and display it along with the date and time.</span></span>

1. <span data-ttu-id="ebd6f-145">En *Program.cs* o *Program.vb*, reemplace el contenido del método `Main`, que es la línea que llama a `Console.WriteLine`, por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="ebd6f-145">In *Program.cs* or *Program.vb*, replace the contents of the `Main` method, which is the line that calls `Console.WriteLine`, with the following code:</span></span>

   :::code language="csharp" source="./snippets/with-visual-studio/csharp/Program.cs" id="MainMethod":::
   :::code language="vb" source="./snippets/with-visual-studio/vb/Program.vb" id="MainMethod":::

   <span data-ttu-id="ebd6f-146">Este código muestra un mensaje en la ventana de la consola y espera a que el usuario escriba una cadena y, luego, presione <kbd>Entrar</kbd>.</span><span class="sxs-lookup"><span data-stu-id="ebd6f-146">This code displays a prompt in the console window and waits until the user enters a string followed by the <kbd>Enter</kbd> key.</span></span> <span data-ttu-id="ebd6f-147">Almacena esta cadena en una variable denominada `name`.</span><span class="sxs-lookup"><span data-stu-id="ebd6f-147">It stores this string in a variable named `name`.</span></span> <span data-ttu-id="ebd6f-148">También recupera el valor de la propiedad <xref:System.DateTime.Now?displayProperty=nameWithType>, que contiene la hora local actual, y lo asigna a una variable denominada `date` (`currentDate` en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="ebd6f-148">It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=nameWithType> property, which contains the current local time, and assigns it to a variable named `date` (`currentDate` in Visual Basic).</span></span> <span data-ttu-id="ebd6f-149">Asimismo, muestra estos valores en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="ebd6f-149">And it displays these values in the console window.</span></span> <span data-ttu-id="ebd6f-150">Por último, muestra un mensaje en la ventana de la consola y llama al método <xref:System.Console.ReadKey(System.Boolean)?displayProperty=nameWithType> para esperar a la entrada del usuario.</span><span class="sxs-lookup"><span data-stu-id="ebd6f-150">Finally, it displays a prompt in the console window and calls the <xref:System.Console.ReadKey(System.Boolean)?displayProperty=nameWithType> method to wait for user input.</span></span>

   <span data-ttu-id="ebd6f-151">El código `\n` (o `vbCrLf` en el código Visual Basic) representa un carácter de nueva línea.</span><span class="sxs-lookup"><span data-stu-id="ebd6f-151">The `\n` (or `vbCrLf` in the Visual Basic code) represents a newline character.</span></span>

   <span data-ttu-id="ebd6f-152">El signo de dólar (`$`) delante de una cadena permite colocar expresiones como nombres de variable entre llaves en la cadena.</span><span class="sxs-lookup"><span data-stu-id="ebd6f-152">The dollar sign (`$`) in front of a string lets you put expressions such as variable names in curly braces in the string.</span></span> <span data-ttu-id="ebd6f-153">El valor de la expresión se inserta en la cadena en lugar de la expresión.</span><span class="sxs-lookup"><span data-stu-id="ebd6f-153">The expression value is inserted into the string in place of the expression.</span></span> <span data-ttu-id="ebd6f-154">Esta sintaxis se conoce como [cadenas interpoladas](../../csharp/language-reference/tokens/interpolated.md).</span><span class="sxs-lookup"><span data-stu-id="ebd6f-154">This syntax is referred to as [interpolated strings](../../csharp/language-reference/tokens/interpolated.md).</span></span>

1. <span data-ttu-id="ebd6f-155">Presione <kbd>Ctrl</kbd>+<kbd>F5</kbd> para ejecutar el programa sin depurar.</span><span class="sxs-lookup"><span data-stu-id="ebd6f-155">Press <kbd>Ctrl</kbd>+<kbd>F5</kbd> to run the program without debugging.</span></span>

1. <span data-ttu-id="ebd6f-156">Responda a la solicitud escribiendo un nombre y presionando la tecla <kbd>Entrar</kbd>.</span><span class="sxs-lookup"><span data-stu-id="ebd6f-156">Respond to the prompt by entering a name and pressing the <kbd>Enter</kbd> key.</span></span>

   :::image type="content" source="./media/with-visual-studio/hello-world-update.png" alt-text="Ventana de la consola con el resultado del programa modificado":::

1. <span data-ttu-id="ebd6f-158">Presione cualquier tecla para cerrar la ventana de consola.</span><span class="sxs-lookup"><span data-stu-id="ebd6f-158">Press any key to close the console window.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ebd6f-159">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="ebd6f-159">Additional resources</span></span>

- [<span data-ttu-id="ebd6f-160">Versiones actuales y versiones de compatibilidad a largo plazo</span><span class="sxs-lookup"><span data-stu-id="ebd6f-160">Current releases and long-term support releases</span></span>](../releases-and-support.md#net-core-and-net-5-version-lifecycles)

## <a name="next-steps"></a><span data-ttu-id="ebd6f-161">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="ebd6f-161">Next steps</span></span>

<span data-ttu-id="ebd6f-162">En este tutorial, ha creado una aplicación de consola de .NET.</span><span class="sxs-lookup"><span data-stu-id="ebd6f-162">In this tutorial, you created a .NET console application.</span></span> <span data-ttu-id="ebd6f-163">En el siguiente tutorial, depurará la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ebd6f-163">In the next tutorial, you debug the app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="ebd6f-164">Depuración de una aplicación de consola de .NET con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="ebd6f-164">Debug a .NET console application using Visual Studio</span></span>](debugging-with-visual-studio.md)
