---
title: 'Hola mundo: su primer programa con Visual Studio en Windows o Mac - Guía C# de programación'
description: Visual Studio es un entorno de desarrollo profesional con muchas características para el desarrollo de .NET. Use Visual Studio para crear una versión de C# de Hola mundo.
ms.date: 09/12/2019
f1_keywords:
- cs.program
- vs.csharp.startpage.firstapplication
helpviewer_keywords:
- examples [C#], Hello World
- Hello World example [C#]
ms.assetid: 6493182a-b0b6-4539-a719-518a168cb730
ms.openlocfilehash: b78937b8ba1c7d4718bfb6252dac705945336d2a
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301832"
---
# <a name="hello-world----your-first-program"></a><span data-ttu-id="a2f4a-104">Hola mundo, su primer programa</span><span class="sxs-lookup"><span data-stu-id="a2f4a-104">Hello World -- Your first program</span></span>

<span data-ttu-id="a2f4a-105">En este artículo, usará Visual Studio para crear el tradicional programa "¡Hola mundo!"</span><span class="sxs-lookup"><span data-stu-id="a2f4a-105">In this article, you'll use Visual Studio to create the traditional "Hello World!"</span></span> <span data-ttu-id="a2f4a-106">.</span><span class="sxs-lookup"><span data-stu-id="a2f4a-106">program.</span></span> <span data-ttu-id="a2f4a-107">Visual Studio es un entorno de desarrollo integrado (IDE) profesional con muchas características diseñadas para el desarrollo de .NET.</span><span class="sxs-lookup"><span data-stu-id="a2f4a-107">Visual Studio is a professional Integrated Development Environment (IDE) with many features designed for .NET development.</span></span> <span data-ttu-id="a2f4a-108">Para crear este programa solo usará algunas de las características de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a2f4a-108">You'll use only a few of the features in Visual Studio to create this program.</span></span> <span data-ttu-id="a2f4a-109">Para más información sobre Visual Studio, vea [Introducción a Visual C#](/visualstudio/ide/quickstart-csharp-console).</span><span class="sxs-lookup"><span data-stu-id="a2f4a-109">To learn more about Visual Studio, see [Getting Started with Visual C#](/visualstudio/ide/quickstart-csharp-console).</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="create-a-new-application"></a><span data-ttu-id="a2f4a-110">Creación de una aplicación</span><span class="sxs-lookup"><span data-stu-id="a2f4a-110">Create a new application</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="windows"></a>[<span data-ttu-id="a2f4a-111">Windows</span><span class="sxs-lookup"><span data-stu-id="a2f4a-111">Windows</span></span>](#tab/windows)

<span data-ttu-id="a2f4a-112">Inicie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a2f4a-112">Start Visual Studio.</span></span> <span data-ttu-id="a2f4a-113">Verá la siguiente imagen en Windows:</span><span class="sxs-lookup"><span data-stu-id="a2f4a-113">You'll see the following image on Windows:</span></span>

![Pantalla de bienvenida de Visual Studio para Windows](./media/hello-world-your-first-program/visual-studio-windows-start-screen.png)

<span data-ttu-id="a2f4a-115">Seleccione **Crear un nuevo proyecto** en la esquina inferior derecha de la imagen.</span><span class="sxs-lookup"><span data-stu-id="a2f4a-115">Select **Create a new project** in the lower right corner of the image.</span></span> <span data-ttu-id="a2f4a-116">Visual Studio muestra el cuadro de diálogo **Nuevo proyecto**:</span><span class="sxs-lookup"><span data-stu-id="a2f4a-116">Visual Studio displays the **New Project** dialog:</span></span>

![Pantalla de nuevo proyecto de Visual Studio en Windows](./media/hello-world-your-first-program/visual-studio-windows-new-project.png)

> [!NOTE]
> <span data-ttu-id="a2f4a-118">Si es la primera vez que inicia Visual Studio, la lista de **plantillas de proyecto recientes** estará vacía.</span><span class="sxs-lookup"><span data-stu-id="a2f4a-118">If this is the first time you've started Visual Studio, the **Recent project templates** list is empty.</span></span>

<span data-ttu-id="a2f4a-119">En el cuadro de diálogo de nuevo proyecto, elija "Aplicación de consola (.NET Core)" y luego presione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a2f4a-119">On the new project dialog, choose "Console App (.NET Core)" and then press **Next**.</span></span> <span data-ttu-id="a2f4a-120">Asigne un nombre al proyecto, como "HolaMundo" y, después, presione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="a2f4a-120">Give your project a name, such as "HelloWorld", then press **Create**.</span></span>

<span data-ttu-id="a2f4a-121">Visual Studio abre el proyecto.</span><span class="sxs-lookup"><span data-stu-id="a2f4a-121">Visual Studio opens your project.</span></span> <span data-ttu-id="a2f4a-122">Ya es un ejemplo básico de</span><span class="sxs-lookup"><span data-stu-id="a2f4a-122">It's already a basic "Hello World!"</span></span> <span data-ttu-id="a2f4a-123">"Hola mundo".</span><span class="sxs-lookup"><span data-stu-id="a2f4a-123">example.</span></span> <span data-ttu-id="a2f4a-124">Presione `Ctrl` + `F5` para ejecutar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="a2f4a-124">Press `Ctrl` + `F5` to run your project.</span></span> <span data-ttu-id="a2f4a-125">Visual Studio compila el proyecto y convierte el código fuente en un archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="a2f4a-125">Visual Studio builds your project, converting the source code into an executable.</span></span> <span data-ttu-id="a2f4a-126">Después, inicia una ventana de comandos que ejecuta la nueva aplicación.</span><span class="sxs-lookup"><span data-stu-id="a2f4a-126">Then, it launches a command window that runs your new application.</span></span> <span data-ttu-id="a2f4a-127">Debería mostrarse el texto siguiente en la ventana:</span><span class="sxs-lookup"><span data-stu-id="a2f4a-127">You should see the following text in the window:</span></span>

```console
Hello World!

C:\Program Files\dotnet\dotnet.exe (process 11964) exited with code 0.
Press any key to close this window . . .
```

<span data-ttu-id="a2f4a-128">Presione cualquier tecla para cerrar la ventana.</span><span class="sxs-lookup"><span data-stu-id="a2f4a-128">Press a key to close the window.</span></span>

# <a name="macos"></a>[<span data-ttu-id="a2f4a-129">macOS</span><span class="sxs-lookup"><span data-stu-id="a2f4a-129">macOS</span></span>](#tab/macos)

<span data-ttu-id="a2f4a-130">Inicie Visual Studio para Mac:</span><span class="sxs-lookup"><span data-stu-id="a2f4a-130">Start Visual Studio for Mac.</span></span> <span data-ttu-id="a2f4a-131">Verá la siguiente imagen en Mac:</span><span class="sxs-lookup"><span data-stu-id="a2f4a-131">You'll see the following image on Mac:</span></span>

![Pantalla de bienvenida de Visual Studio para Mac](./media/hello-world-your-first-program/visual-studio-mac-start-screen.png)

> [!NOTE]
> <span data-ttu-id="a2f4a-133">Si es la primera vez que inicia Visual Studio para Mac, la lista de **proyectos recientes** estará vacía.</span><span class="sxs-lookup"><span data-stu-id="a2f4a-133">If this is the first time you've started Visual Studio for Mac, the **Recent projects** list is empty.</span></span>

<span data-ttu-id="a2f4a-134">Seleccione **Nuevo** en la esquina superior derecha de la imagen.</span><span class="sxs-lookup"><span data-stu-id="a2f4a-134">Select **New** in the upper right corner of the image.</span></span> <span data-ttu-id="a2f4a-135">Visual Studio para Mac muestra el cuadro de diálogo **Nuevo proyecto**:</span><span class="sxs-lookup"><span data-stu-id="a2f4a-135">Visual Studio for Mac displays the **New Project** dialog:</span></span>

![Pantalla de nuevo proyecto de Visual Studio en Mac](./media/hello-world-your-first-program/visual-studio-mac-new-project.png)

<span data-ttu-id="a2f4a-137">En el cuadro de diálogo de nuevo proyecto, elija ".NET Core" y "Aplicación de consola" y luego presione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a2f4a-137">On the new project dialog, choose ".NET Core", and "Console App" and then press **Next**.</span></span> <span data-ttu-id="a2f4a-138">Tendrá que seleccionar la plataforma de destino.</span><span class="sxs-lookup"><span data-stu-id="a2f4a-138">You'll need to select the target framework.</span></span> <span data-ttu-id="a2f4a-139">El valor predeterminado es correcto, así que presione Siguiente.</span><span class="sxs-lookup"><span data-stu-id="a2f4a-139">The default is fine, so press next.</span></span> <span data-ttu-id="a2f4a-140">Asigne un nombre al proyecto, como "HolaMundo" y, después, presione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="a2f4a-140">Give your project a name, such as "HelloWorld", then press **Create**.</span></span> <span data-ttu-id="a2f4a-141">Puede usar la ubicación predeterminada del proyecto.</span><span class="sxs-lookup"><span data-stu-id="a2f4a-141">You can use the default project location.</span></span> <span data-ttu-id="a2f4a-142">No agregue este proyecto al control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="a2f4a-142">Don't add this project to source control.</span></span>

<span data-ttu-id="a2f4a-143">Visual Studio para Mac abre el proyecto.</span><span class="sxs-lookup"><span data-stu-id="a2f4a-143">Visual Studio for Mac opens your project.</span></span> <span data-ttu-id="a2f4a-144">Ya es un ejemplo básico de</span><span class="sxs-lookup"><span data-stu-id="a2f4a-144">It's already a basic "Hello World!"</span></span> <span data-ttu-id="a2f4a-145">"Hola mundo".</span><span class="sxs-lookup"><span data-stu-id="a2f4a-145">example.</span></span> <span data-ttu-id="a2f4a-146">Presione `Ctrl` + `Fn` + `F5` para ejecutar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="a2f4a-146">Press `Ctrl` + `Fn` + `F5` to run your project.</span></span> <span data-ttu-id="a2f4a-147">Visual Studio para Mac compila el proyecto y convierte el código fuente en un archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="a2f4a-147">Visual Studio for Mac builds your project, converting the source code into an executable.</span></span> <span data-ttu-id="a2f4a-148">Después, inicia una ventana de comandos que ejecuta la nueva aplicación.</span><span class="sxs-lookup"><span data-stu-id="a2f4a-148">Then, it launches a command window that runs your new application.</span></span> <span data-ttu-id="a2f4a-149">Debería mostrarse el texto siguiente en la ventana:</span><span class="sxs-lookup"><span data-stu-id="a2f4a-149">You should see the following text in the window:</span></span>

```console
Hello World!

Press any key to close this window . . .
```

<span data-ttu-id="a2f4a-150">Presione una tecla para finalizar la sesión.</span><span class="sxs-lookup"><span data-stu-id="a2f4a-150">Press a key to end the session.</span></span>

---

## <a name="elements-of-a-c-program"></a><span data-ttu-id="a2f4a-151">Elementos de un programa en C#</span><span class="sxs-lookup"><span data-stu-id="a2f4a-151">Elements of a C# program</span></span>

<span data-ttu-id="a2f4a-152">Examinemos las partes importantes de este programa.</span><span class="sxs-lookup"><span data-stu-id="a2f4a-152">Let's examine the important parts of this program.</span></span> <span data-ttu-id="a2f4a-153">La primera línea contiene un comentario.</span><span class="sxs-lookup"><span data-stu-id="a2f4a-153">The first line contains a comment.</span></span> <span data-ttu-id="a2f4a-154">Los caracteres `//` convierten el resto de la línea en un comentario.</span><span class="sxs-lookup"><span data-stu-id="a2f4a-154">The characters `//` convert the rest of the line to a comment.</span></span>

[!code-csharp[csProgGuide#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#32)]

<span data-ttu-id="a2f4a-155">También puede convertir un bloque de texto en un comentario escribiéndolo entre los caracteres `/*` y `*/`.</span><span class="sxs-lookup"><span data-stu-id="a2f4a-155">You can also comment out a block of text by enclosing it between the `/*` and `*/` characters.</span></span> <span data-ttu-id="a2f4a-156">Esta implementación se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="a2f4a-156">This is shown in the following example.</span></span>

[!code-csharp[csProgGuide#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#33)]

<span data-ttu-id="a2f4a-157">Una aplicación de la consola de C# debe contener un método `Main`, en el que se inicia y finaliza un control.</span><span class="sxs-lookup"><span data-stu-id="a2f4a-157">A C# console application must contain a `Main` method, in which control starts and ends.</span></span> <span data-ttu-id="a2f4a-158">El método `Main` es donde se crean los objetos y se ejecutan otros métodos.</span><span class="sxs-lookup"><span data-stu-id="a2f4a-158">The `Main` method is where you create objects and execute other methods.</span></span>

<span data-ttu-id="a2f4a-159">El método `Main` es un método [estático](../../language-reference/keywords/static.md) que reside dentro de una clase o de un struct.</span><span class="sxs-lookup"><span data-stu-id="a2f4a-159">The `Main` method is a [static](../../language-reference/keywords/static.md) method that resides inside a class or a struct.</span></span> <span data-ttu-id="a2f4a-160">En el ejemplo anterior de "Hello World!",</span><span class="sxs-lookup"><span data-stu-id="a2f4a-160">In the previous "Hello World!"</span></span> <span data-ttu-id="a2f4a-161">reside en una clase denominada `Hello`.</span><span class="sxs-lookup"><span data-stu-id="a2f4a-161">example, it resides in a class named `Hello`.</span></span> <span data-ttu-id="a2f4a-162">Puede declarar el método `Main` de una de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="a2f4a-162">You can declare the `Main` method in one of the following ways:</span></span>

- <span data-ttu-id="a2f4a-163">Puede devolver `void`.</span><span class="sxs-lookup"><span data-stu-id="a2f4a-163">It can return `void`.</span></span> <span data-ttu-id="a2f4a-164">Esto significa que el programa no devuelve un valor.</span><span class="sxs-lookup"><span data-stu-id="a2f4a-164">That means your program doesn't return a value.</span></span>

[!code-csharp[csProgGuideMain#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#12)]

- <span data-ttu-id="a2f4a-165">También puede devolver un entero.</span><span class="sxs-lookup"><span data-stu-id="a2f4a-165">It can also return an integer.</span></span> <span data-ttu-id="a2f4a-166">El entero es el **código de salida** de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a2f4a-166">The integer is the **exit code** for your application.</span></span>

[!code-csharp[csProgGuideMain#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#13)]

- <span data-ttu-id="a2f4a-167">Puede tomar argumentos con cualquiera de los tipos de valor devueltos.</span><span class="sxs-lookup"><span data-stu-id="a2f4a-167">With either of the return types, it can take arguments.</span></span>

[!code-csharp[csProgGuideMain#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#19)]

<span data-ttu-id="a2f4a-168">o bien</span><span class="sxs-lookup"><span data-stu-id="a2f4a-168">-or-</span></span>

[!code-csharp[csProgGuideMain#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#18)]

<span data-ttu-id="a2f4a-169">El parámetro del método `Main`, `args`, es una matriz `string` que contiene los argumentos de la línea de comandos usados para invocar el programa.</span><span class="sxs-lookup"><span data-stu-id="a2f4a-169">The parameter of the `Main` method, `args`, is a `string` array that contains the command-line arguments used to invoke the program.</span></span>

<span data-ttu-id="a2f4a-170">Para obtener más información sobre cómo usar los argumentos de la línea de comandos, vea los ejemplos de [Main() y argumentos de línea de comandos](../main-and-command-args/index.md).</span><span class="sxs-lookup"><span data-stu-id="a2f4a-170">For more information about how to use command-line arguments, see the examples in [Main() and Command-Line Arguments](../main-and-command-args/index.md).</span></span>

## <a name="input-and-output"></a><span data-ttu-id="a2f4a-171">Entrada y salida</span><span class="sxs-lookup"><span data-stu-id="a2f4a-171">Input and output</span></span>

<span data-ttu-id="a2f4a-172">Los programas de C# suelen usar los servicios de entrada y salida proporcionados por la biblioteca en tiempo de ejecución de .NET.</span><span class="sxs-lookup"><span data-stu-id="a2f4a-172">C# programs generally use the input/output services provided by the run-time library of .NET.</span></span> <span data-ttu-id="a2f4a-173">La instrucción `System.Console.WriteLine("Hello World!");` utiliza el método <xref:System.Console.WriteLine%2A>.</span><span class="sxs-lookup"><span data-stu-id="a2f4a-173">The statement `System.Console.WriteLine("Hello World!");` uses the <xref:System.Console.WriteLine%2A> method.</span></span> <span data-ttu-id="a2f4a-174">Este es uno de los métodos de salida de la clase <xref:System.Console> en la biblioteca de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a2f4a-174">This is one of the output methods of the <xref:System.Console> class in the run-time library.</span></span> <span data-ttu-id="a2f4a-175">Muestra el parámetro de cadena en la secuencia de salida estándar, seguida de una nueva línea.</span><span class="sxs-lookup"><span data-stu-id="a2f4a-175">It displays its string parameter on the standard output stream followed by a new line.</span></span> <span data-ttu-id="a2f4a-176">Hay otros métodos <xref:System.Console> disponibles para las distintas operaciones de entrada y salida.</span><span class="sxs-lookup"><span data-stu-id="a2f4a-176">Other <xref:System.Console> methods are available for different input and output operations.</span></span> <span data-ttu-id="a2f4a-177">Si incluye la directiva `using System;` al inicio del programa, puede usar directamente las clases y los métodos <xref:System> sin calificarlos totalmente.</span><span class="sxs-lookup"><span data-stu-id="a2f4a-177">If you include the `using System;` directive at the beginning of the program, you can directly use the <xref:System> classes and methods without fully qualifying them.</span></span> <span data-ttu-id="a2f4a-178">Por ejemplo, puede llamar a `Console.WriteLine` en vez de llamar a `System.Console.WriteLine`:</span><span class="sxs-lookup"><span data-stu-id="a2f4a-178">For example, you can call `Console.WriteLine` instead of `System.Console.WriteLine`:</span></span>

[!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]

[!code-csharp[csProgGuide#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#23)]

<span data-ttu-id="a2f4a-179">Para obtener más información sobre los métodos de entrada y salida, vea <xref:System.IO>.</span><span class="sxs-lookup"><span data-stu-id="a2f4a-179">For more information about input/output methods, see <xref:System.IO>.</span></span>

## <a name="see-also"></a><span data-ttu-id="a2f4a-180">Vea también</span><span class="sxs-lookup"><span data-stu-id="a2f4a-180">See also</span></span>

- [<span data-ttu-id="a2f4a-181">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="a2f4a-181">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="a2f4a-182">Ejemplos y tutoriales</span><span class="sxs-lookup"><span data-stu-id="a2f4a-182">Samples and tutorials</span></span>](../../../samples-and-tutorials/index.md)
- [<span data-ttu-id="a2f4a-183">Main() y argumentos de la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="a2f4a-183">Main() and Command-Line Arguments</span></span>](../main-and-command-args/index.md)
- [<span data-ttu-id="a2f4a-184">Introducción a Visual C#</span><span class="sxs-lookup"><span data-stu-id="a2f4a-184">Getting Started with Visual C#</span></span>](/visualstudio/ide/quickstart-csharp-console)
