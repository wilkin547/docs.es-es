---
title: 'Hola mundo: su primer programa con Visual Studio en Windows o Mac - Guía C# de programación'
ms.date: 09/12/2019
f1_keywords:
- cs.program
- vs.csharp.startpage.firstapplication
helpviewer_keywords:
- examples [C#], Hello World
- Hello World example [C#]
ms.assetid: 6493182a-b0b6-4539-a719-518a168cb730
ms.openlocfilehash: 6d78ec83fec72b30f5cee398af1816d0cac35886
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/01/2020
ms.locfileid: "84241869"
---
# <a name="hello-world----your-first-program"></a><span data-ttu-id="1004d-102">Hola mundo, su primer programa</span><span class="sxs-lookup"><span data-stu-id="1004d-102">Hello World -- Your first program</span></span>

<span data-ttu-id="1004d-103">En este artículo, usará Visual Studio para crear el tradicional programa "¡Hola mundo!"</span><span class="sxs-lookup"><span data-stu-id="1004d-103">In this article, you'll use Visual Studio to create the traditional "Hello World!"</span></span> <span data-ttu-id="1004d-104">.</span><span class="sxs-lookup"><span data-stu-id="1004d-104">program.</span></span> <span data-ttu-id="1004d-105">Visual Studio es un entorno de desarrollo integrado (IDE) profesional con muchas características diseñadas para el desarrollo de .NET.</span><span class="sxs-lookup"><span data-stu-id="1004d-105">Visual Studio is a professional Integrated Development Environment (IDE) with many features designed for .NET development.</span></span> <span data-ttu-id="1004d-106">Para crear este programa solo usará algunas de las características de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1004d-106">You'll use only a few of the features in Visual Studio to create this program.</span></span> <span data-ttu-id="1004d-107">Para más información sobre Visual Studio, vea [Introducción a Visual C#](/visualstudio/ide/quickstart-csharp-console).</span><span class="sxs-lookup"><span data-stu-id="1004d-107">To learn more about Visual Studio, see [Getting Started with Visual C#](/visualstudio/ide/quickstart-csharp-console).</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="create-a-new-application"></a><span data-ttu-id="1004d-108">Creación de una aplicación</span><span class="sxs-lookup"><span data-stu-id="1004d-108">Create a new application</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="windows"></a>[<span data-ttu-id="1004d-109">Windows</span><span class="sxs-lookup"><span data-stu-id="1004d-109">Windows</span></span>](#tab/windows)

<span data-ttu-id="1004d-110">Inicie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1004d-110">Start Visual Studio.</span></span> <span data-ttu-id="1004d-111">Verá la siguiente imagen en Windows:</span><span class="sxs-lookup"><span data-stu-id="1004d-111">You'll see the following image on Windows:</span></span>

![Pantalla de bienvenida de Visual Studio para Windows](./media/hello-world-your-first-program/visual-studio-windows-start-screen.png)

<span data-ttu-id="1004d-113">Seleccione **Crear un nuevo proyecto** en la esquina inferior derecha de la imagen.</span><span class="sxs-lookup"><span data-stu-id="1004d-113">Select **Create a new project** in the lower right corner of the image.</span></span> <span data-ttu-id="1004d-114">Visual Studio muestra el cuadro de diálogo **Nuevo proyecto**:</span><span class="sxs-lookup"><span data-stu-id="1004d-114">Visual Studio displays the **New Project** dialog:</span></span>

![Pantalla de nuevo proyecto de Visual Studio en Windows](./media/hello-world-your-first-program/visual-studio-windows-new-project.png)

> [!NOTE]
> <span data-ttu-id="1004d-116">Si es la primera vez que inicia Visual Studio, la lista de **plantillas de proyecto recientes** estará vacía.</span><span class="sxs-lookup"><span data-stu-id="1004d-116">If this is the first time you've started Visual Studio, the **Recent project templates** list is empty.</span></span>

<span data-ttu-id="1004d-117">En el cuadro de diálogo de nuevo proyecto, elija "Aplicación de consola (.NET Core)" y luego presione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1004d-117">On the new project dialog, choose "Console App (.NET Core)" and then press **Next**.</span></span> <span data-ttu-id="1004d-118">Asigne un nombre al proyecto, como "HolaMundo" y, después, presione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="1004d-118">Give your project a name, such as "HelloWorld", then press **Create**.</span></span>

<span data-ttu-id="1004d-119">Visual Studio abre el proyecto.</span><span class="sxs-lookup"><span data-stu-id="1004d-119">Visual Studio opens your project.</span></span> <span data-ttu-id="1004d-120">Ya es un ejemplo básico de</span><span class="sxs-lookup"><span data-stu-id="1004d-120">It's already a basic "Hello World!"</span></span> <span data-ttu-id="1004d-121">"Hola mundo".</span><span class="sxs-lookup"><span data-stu-id="1004d-121">example.</span></span> <span data-ttu-id="1004d-122">Presione `Ctrl` + `F5` para ejecutar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="1004d-122">Press `Ctrl` + `F5` to run your project.</span></span> <span data-ttu-id="1004d-123">Visual Studio compila el proyecto y convierte el código fuente en un archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="1004d-123">Visual Studio builds your project, converting the source code into an executable.</span></span> <span data-ttu-id="1004d-124">Después, inicia una ventana de comandos que ejecuta la nueva aplicación.</span><span class="sxs-lookup"><span data-stu-id="1004d-124">Then, it launches a command window that runs your new application.</span></span> <span data-ttu-id="1004d-125">Debería mostrarse el texto siguiente en la ventana:</span><span class="sxs-lookup"><span data-stu-id="1004d-125">You should see the following text in the window:</span></span>

```console
Hello World!

C:\Program Files\dotnet\dotnet.exe (process 11964) exited with code 0.
Press any key to close this window . . .
```

<span data-ttu-id="1004d-126">Presione cualquier tecla para cerrar la ventana.</span><span class="sxs-lookup"><span data-stu-id="1004d-126">Press a key to close the window.</span></span>

# <a name="macos"></a>[<span data-ttu-id="1004d-127">macOS</span><span class="sxs-lookup"><span data-stu-id="1004d-127">macOS</span></span>](#tab/macos)

<span data-ttu-id="1004d-128">Inicie Visual Studio para Mac:</span><span class="sxs-lookup"><span data-stu-id="1004d-128">Start Visual Studio for Mac.</span></span> <span data-ttu-id="1004d-129">Verá la siguiente imagen en Mac:</span><span class="sxs-lookup"><span data-stu-id="1004d-129">You'll see the following image on Mac:</span></span>

![Pantalla de bienvenida de Visual Studio para Mac](./media/hello-world-your-first-program/visual-studio-mac-start-screen.png)

> [!NOTE]
> <span data-ttu-id="1004d-131">Si es la primera vez que inicia Visual Studio para Mac, la lista de **proyectos recientes** estará vacía.</span><span class="sxs-lookup"><span data-stu-id="1004d-131">If this is the first time you've started Visual Studio for Mac, the **Recent projects** list is empty.</span></span>

<span data-ttu-id="1004d-132">Seleccione **Nuevo** en la esquina superior derecha de la imagen.</span><span class="sxs-lookup"><span data-stu-id="1004d-132">Select **New** in the upper right corner of the image.</span></span> <span data-ttu-id="1004d-133">Visual Studio para Mac muestra el cuadro de diálogo **Nuevo proyecto**:</span><span class="sxs-lookup"><span data-stu-id="1004d-133">Visual Studio for Mac displays the **New Project** dialog:</span></span>

![Pantalla de nuevo proyecto de Visual Studio en Mac](./media/hello-world-your-first-program/visual-studio-mac-new-project.png)

<span data-ttu-id="1004d-135">En el cuadro de diálogo de nuevo proyecto, elija ".NET Core" y "Aplicación de consola" y luego presione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1004d-135">On the new project dialog, choose ".NET Core", and "Console App" and then press **Next**.</span></span> <span data-ttu-id="1004d-136">Tendrá que seleccionar la plataforma de destino.</span><span class="sxs-lookup"><span data-stu-id="1004d-136">You'll need to select the target framework.</span></span> <span data-ttu-id="1004d-137">El valor predeterminado es correcto, así que presione Siguiente.</span><span class="sxs-lookup"><span data-stu-id="1004d-137">The default is fine, so press next.</span></span> <span data-ttu-id="1004d-138">Asigne un nombre al proyecto, como "HolaMundo" y, después, presione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="1004d-138">Give your project a name, such as "HelloWorld", then press **Create**.</span></span> <span data-ttu-id="1004d-139">Puede usar la ubicación predeterminada del proyecto.</span><span class="sxs-lookup"><span data-stu-id="1004d-139">You can use the default project location.</span></span> <span data-ttu-id="1004d-140">No agregue este proyecto al control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="1004d-140">Don't add this project to source control.</span></span>

<span data-ttu-id="1004d-141">Visual Studio para Mac abre el proyecto.</span><span class="sxs-lookup"><span data-stu-id="1004d-141">Visual Studio for Mac opens your project.</span></span> <span data-ttu-id="1004d-142">Ya es un ejemplo básico de</span><span class="sxs-lookup"><span data-stu-id="1004d-142">It's already a basic "Hello World!"</span></span> <span data-ttu-id="1004d-143">"Hola mundo".</span><span class="sxs-lookup"><span data-stu-id="1004d-143">example.</span></span> <span data-ttu-id="1004d-144">Presione `Ctrl` + `Fn` + `F5` para ejecutar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="1004d-144">Press `Ctrl` + `Fn` + `F5` to run your project.</span></span> <span data-ttu-id="1004d-145">Visual Studio para Mac compila el proyecto y convierte el código fuente en un archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="1004d-145">Visual Studio for Mac builds your project, converting the source code into an executable.</span></span> <span data-ttu-id="1004d-146">Después, inicia una ventana de comandos que ejecuta la nueva aplicación.</span><span class="sxs-lookup"><span data-stu-id="1004d-146">Then, it launches a command window that runs your new application.</span></span> <span data-ttu-id="1004d-147">Debería mostrarse el texto siguiente en la ventana:</span><span class="sxs-lookup"><span data-stu-id="1004d-147">You should see the following text in the window:</span></span>

```console
Hello World!

Press any key to close this window . . .
```

<span data-ttu-id="1004d-148">Presione una tecla para finalizar la sesión.</span><span class="sxs-lookup"><span data-stu-id="1004d-148">Press a key to end the session.</span></span>

---

## <a name="elements-of-a-c-program"></a><span data-ttu-id="1004d-149">Elementos de un programa en C#</span><span class="sxs-lookup"><span data-stu-id="1004d-149">Elements of a C# program</span></span>

<span data-ttu-id="1004d-150">Examinemos las partes importantes de este programa.</span><span class="sxs-lookup"><span data-stu-id="1004d-150">Let's examine the important parts of this program.</span></span> <span data-ttu-id="1004d-151">La primera línea contiene un comentario.</span><span class="sxs-lookup"><span data-stu-id="1004d-151">The first line contains a comment.</span></span> <span data-ttu-id="1004d-152">Los caracteres `//` convierten el resto de la línea en un comentario.</span><span class="sxs-lookup"><span data-stu-id="1004d-152">The characters `//` convert the rest of the line to a comment.</span></span>

[!code-csharp[csProgGuide#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#32)]

<span data-ttu-id="1004d-153">También puede convertir un bloque de texto en un comentario escribiéndolo entre los caracteres `/*` y `*/`.</span><span class="sxs-lookup"><span data-stu-id="1004d-153">You can also comment out a block of text by enclosing it between the `/*` and `*/` characters.</span></span> <span data-ttu-id="1004d-154">Esta implementación se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="1004d-154">This is shown in the following example.</span></span>

[!code-csharp[csProgGuide#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#33)]

<span data-ttu-id="1004d-155">Una aplicación de la consola de C# debe contener un método `Main`, en el que se inicia y finaliza un control.</span><span class="sxs-lookup"><span data-stu-id="1004d-155">A C# console application must contain a `Main` method, in which control starts and ends.</span></span> <span data-ttu-id="1004d-156">El método `Main` es donde se crean los objetos y se ejecutan otros métodos.</span><span class="sxs-lookup"><span data-stu-id="1004d-156">The `Main` method is where you create objects and execute other methods.</span></span>

<span data-ttu-id="1004d-157">El método `Main` es un método [estático](../../language-reference/keywords/static.md) que reside dentro de una clase o de un struct.</span><span class="sxs-lookup"><span data-stu-id="1004d-157">The `Main` method is a [static](../../language-reference/keywords/static.md) method that resides inside a class or a struct.</span></span> <span data-ttu-id="1004d-158">En el ejemplo anterior de "Hello World!",</span><span class="sxs-lookup"><span data-stu-id="1004d-158">In the previous "Hello World!"</span></span> <span data-ttu-id="1004d-159">reside en una clase denominada `Hello`.</span><span class="sxs-lookup"><span data-stu-id="1004d-159">example, it resides in a class named `Hello`.</span></span> <span data-ttu-id="1004d-160">Puede declarar el método `Main` de una de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="1004d-160">You can declare the `Main` method in one of the following ways:</span></span>

- <span data-ttu-id="1004d-161">Puede devolver `void`.</span><span class="sxs-lookup"><span data-stu-id="1004d-161">It can return `void`.</span></span> <span data-ttu-id="1004d-162">Esto significa que el programa no devuelve un valor.</span><span class="sxs-lookup"><span data-stu-id="1004d-162">That means your program doesn't return a value.</span></span>

[!code-csharp[csProgGuideMain#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#12)]

- <span data-ttu-id="1004d-163">También puede devolver un entero.</span><span class="sxs-lookup"><span data-stu-id="1004d-163">It can also return an integer.</span></span> <span data-ttu-id="1004d-164">El entero es el **código de salida** de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1004d-164">The integer is the **exit code** for your application.</span></span>

[!code-csharp[csProgGuideMain#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#13)]

- <span data-ttu-id="1004d-165">Puede tomar argumentos con cualquiera de los tipos de valor devueltos.</span><span class="sxs-lookup"><span data-stu-id="1004d-165">With either of the return types, it can take arguments.</span></span>

[!code-csharp[csProgGuideMain#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#19)]

<span data-ttu-id="1004d-166">o bien</span><span class="sxs-lookup"><span data-stu-id="1004d-166">-or-</span></span>

[!code-csharp[csProgGuideMain#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#18)]

<span data-ttu-id="1004d-167">El parámetro del método `Main`, `args`, es una matriz `string` que contiene los argumentos de la línea de comandos usados para invocar el programa.</span><span class="sxs-lookup"><span data-stu-id="1004d-167">The parameter of the `Main` method, `args`, is a `string` array that contains the command-line arguments used to invoke the program.</span></span>

<span data-ttu-id="1004d-168">Para obtener más información sobre cómo usar los argumentos de la línea de comandos, vea los ejemplos de [Main() y argumentos de línea de comandos](../main-and-command-args/index.md).</span><span class="sxs-lookup"><span data-stu-id="1004d-168">For more information about how to use command-line arguments, see the examples in [Main() and Command-Line Arguments](../main-and-command-args/index.md).</span></span>

## <a name="input-and-output"></a><span data-ttu-id="1004d-169">Entrada y salida</span><span class="sxs-lookup"><span data-stu-id="1004d-169">Input and output</span></span>

<span data-ttu-id="1004d-170">Los programas de C# suelen usar los servicios de entrada y salida proporcionados por la biblioteca en tiempo de ejecución de .NET.</span><span class="sxs-lookup"><span data-stu-id="1004d-170">C# programs generally use the input/output services provided by the run-time library of .NET.</span></span> <span data-ttu-id="1004d-171">La instrucción `System.Console.WriteLine("Hello World!");` utiliza el método <xref:System.Console.WriteLine%2A>.</span><span class="sxs-lookup"><span data-stu-id="1004d-171">The statement `System.Console.WriteLine("Hello World!");` uses the <xref:System.Console.WriteLine%2A> method.</span></span> <span data-ttu-id="1004d-172">Este es uno de los métodos de salida de la clase <xref:System.Console> en la biblioteca de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1004d-172">This is one of the output methods of the <xref:System.Console> class in the run-time library.</span></span> <span data-ttu-id="1004d-173">Muestra el parámetro de cadena en la secuencia de salida estándar, seguida de una nueva línea.</span><span class="sxs-lookup"><span data-stu-id="1004d-173">It displays its string parameter on the standard output stream followed by a new line.</span></span> <span data-ttu-id="1004d-174">Hay otros métodos <xref:System.Console> disponibles para las distintas operaciones de entrada y salida.</span><span class="sxs-lookup"><span data-stu-id="1004d-174">Other <xref:System.Console> methods are available for different input and output operations.</span></span> <span data-ttu-id="1004d-175">Si incluye la directiva `using System;` al inicio del programa, puede usar directamente las clases y los métodos <xref:System> sin calificarlos totalmente.</span><span class="sxs-lookup"><span data-stu-id="1004d-175">If you include the `using System;` directive at the beginning of the program, you can directly use the <xref:System> classes and methods without fully qualifying them.</span></span> <span data-ttu-id="1004d-176">Por ejemplo, puede llamar a `Console.WriteLine` en vez de llamar a `System.Console.WriteLine`:</span><span class="sxs-lookup"><span data-stu-id="1004d-176">For example, you can call `Console.WriteLine` instead of `System.Console.WriteLine`:</span></span>

[!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]

[!code-csharp[csProgGuide#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#23)]

<span data-ttu-id="1004d-177">Para obtener más información sobre los métodos de entrada y salida, vea <xref:System.IO>.</span><span class="sxs-lookup"><span data-stu-id="1004d-177">For more information about input/output methods, see <xref:System.IO>.</span></span>

## <a name="see-also"></a><span data-ttu-id="1004d-178">Vea también</span><span class="sxs-lookup"><span data-stu-id="1004d-178">See also</span></span>

- [<span data-ttu-id="1004d-179">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="1004d-179">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="1004d-180">Ejemplos y tutoriales</span><span class="sxs-lookup"><span data-stu-id="1004d-180">Samples and tutorials</span></span>](../../../samples-and-tutorials/index.md)
- [<span data-ttu-id="1004d-181">Main() y argumentos de la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="1004d-181">Main() and Command-Line Arguments</span></span>](../main-and-command-args/index.md)
- [<span data-ttu-id="1004d-182">Introducción a Visual C#</span><span class="sxs-lookup"><span data-stu-id="1004d-182">Getting Started with Visual C#</span></span>](/visualstudio/ide/quickstart-csharp-console)
