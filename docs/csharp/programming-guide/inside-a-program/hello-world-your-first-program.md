---
title: Hola mundo, su primer programa (Guía de programación de C#)
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- cs.program
- vs.csharp.startpage.firstapplication
helpviewer_keywords:
- examples [C#], Hello World
- Hello World example [C#]
ms.assetid: 6493182a-b0b6-4539-a719-518a168cb730
ms.openlocfilehash: 7ff65867f9f81118cad30852c439f8b3491bf1aa
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56969731"
---
# <a name="hello-world----your-first-program-c-programming-guide"></a><span data-ttu-id="2d7ab-102">Hola mundo, su primer programa (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="2d7ab-102">Hello World -- Your first program (C# Programming Guide)</span></span>

<span data-ttu-id="2d7ab-103">En el siguiente procedimiento se crea una versión de C# del programa tradicional "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="2d7ab-103">The following procedure creates a C# version of the traditional "Hello World!"</span></span> <span data-ttu-id="2d7ab-104">.</span><span class="sxs-lookup"><span data-stu-id="2d7ab-104">program.</span></span> <span data-ttu-id="2d7ab-105">El programa muestra la cadena `Hello World!`.</span><span class="sxs-lookup"><span data-stu-id="2d7ab-105">The program displays the string `Hello World!`</span></span>

<span data-ttu-id="2d7ab-106">Para obtener más ejemplos de los conceptos preliminares, vea [Introducción a Visual C# y Visual Basic](/visualstudio/ide/getting-started-with-visual-csharp-and-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="2d7ab-106">For more examples of introductory concepts, see [Getting Started with Visual C# and Visual Basic](/visualstudio/ide/getting-started-with-visual-csharp-and-visual-basic).</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-create-and-run-a-console-application"></a><span data-ttu-id="2d7ab-107">Para crear y ejecutar una aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="2d7ab-107">To create and run a console application</span></span>

1. <span data-ttu-id="2d7ab-108">Inicie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2d7ab-108">Start Visual Studio.</span></span>

2. <span data-ttu-id="2d7ab-109">En la barra de menús, elija **Archivo**, **Nuevo**, **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="2d7ab-109">On the menu bar, choose **File**, **New**, **Project**.</span></span>

     <span data-ttu-id="2d7ab-110">Aparece el cuadro de diálogo **Nuevo proyecto** .</span><span class="sxs-lookup"><span data-stu-id="2d7ab-110">The **New Project** dialog box opens.</span></span>

3. <span data-ttu-id="2d7ab-111">Expanda **Instalado**, **Plantillas**, **Visual C#** y, luego, elija **Aplicación de consola**.</span><span class="sxs-lookup"><span data-stu-id="2d7ab-111">Expand **Installed**, expand **Templates**, expand **Visual C#**, and then choose **Console Application**.</span></span>

4. <span data-ttu-id="2d7ab-112">En el cuadro **Nombre**, escriba un nombre para el proyecto y, después, elija el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2d7ab-112">In the **Name** box, specify a name for your project, and then choose the **OK** button.</span></span>

     <span data-ttu-id="2d7ab-113">El proyecto nuevo aparece en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="2d7ab-113">The new project appears in **Solution Explorer**.</span></span>

5. <span data-ttu-id="2d7ab-114">Si Program.cs no está abierto en el **Editor de código**, abra el menú contextual de **Program.cs** en el **Explorador de soluciones** y elija **Ver código**.</span><span class="sxs-lookup"><span data-stu-id="2d7ab-114">If Program.cs isn't open in the **Code Editor**, open the shortcut menu for **Program.cs** in **Solution Explorer**, and then choose **View Code**.</span></span>

6. <span data-ttu-id="2d7ab-115">Reemplace el contenido de Program.cs por el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="2d7ab-115">Replace the contents of Program.cs with the following code.</span></span>

     [!code-csharp[csProgGuide#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#21)]

7. <span data-ttu-id="2d7ab-116">Pulse la tecla F5 para ejecutar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="2d7ab-116">Choose the F5 key to run the project.</span></span> <span data-ttu-id="2d7ab-117">Aparecerá una ventana del símbolo del sistema que contiene la línea `Hello World!`.</span><span class="sxs-lookup"><span data-stu-id="2d7ab-117">A Command Prompt window appears that contains the line `Hello World!`</span></span>

<span data-ttu-id="2d7ab-118">Después se examinan las partes importantes de este programa.</span><span class="sxs-lookup"><span data-stu-id="2d7ab-118">Next, the important parts of this program are examined.</span></span>

## <a name="comments"></a><span data-ttu-id="2d7ab-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2d7ab-119">Comments</span></span>

<span data-ttu-id="2d7ab-120">La primera línea contiene un comentario.</span><span class="sxs-lookup"><span data-stu-id="2d7ab-120">The first line contains a comment.</span></span> <span data-ttu-id="2d7ab-121">Los caracteres `//` convierten el resto de la línea en un comentario.</span><span class="sxs-lookup"><span data-stu-id="2d7ab-121">The characters `//` convert the rest of the line to a comment.</span></span>

 [!code-csharp[csProgGuide#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#32)]

<span data-ttu-id="2d7ab-122">También puede convertir un bloque de texto en un comentario escribiéndolo entre los caracteres `/*` y `*/`.</span><span class="sxs-lookup"><span data-stu-id="2d7ab-122">You can also comment out a block of text by enclosing it between the `/*` and `*/` characters.</span></span> <span data-ttu-id="2d7ab-123">Esta implementación se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="2d7ab-123">This is shown in the following example.</span></span>

 [!code-csharp[csProgGuide#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#33)]

## <a name="main-method"></a><span data-ttu-id="2d7ab-124">Main (método)</span><span class="sxs-lookup"><span data-stu-id="2d7ab-124">Main method</span></span>

<span data-ttu-id="2d7ab-125">Una aplicación de la consola de C# debe contener un método `Main`, en el que se inicia y finaliza un control.</span><span class="sxs-lookup"><span data-stu-id="2d7ab-125">A C# console application must contain a `Main` method, in which control starts and ends.</span></span> <span data-ttu-id="2d7ab-126">El método `Main` es donde se crean los objetos y se ejecutan otros métodos.</span><span class="sxs-lookup"><span data-stu-id="2d7ab-126">The `Main` method is where you create objects and execute other methods.</span></span>

<span data-ttu-id="2d7ab-127">El método `Main` es un método [estático](../../../csharp/language-reference/keywords/static.md) que reside dentro de una clase o de un struct.</span><span class="sxs-lookup"><span data-stu-id="2d7ab-127">The `Main` method is a [static](../../../csharp/language-reference/keywords/static.md) method that resides inside a class or a struct.</span></span> <span data-ttu-id="2d7ab-128">En el ejemplo anterior de "Hello World!",</span><span class="sxs-lookup"><span data-stu-id="2d7ab-128">In the previous "Hello World!"</span></span> <span data-ttu-id="2d7ab-129">reside en una clase denominada `Hello`.</span><span class="sxs-lookup"><span data-stu-id="2d7ab-129">example, it resides in a class named `Hello`.</span></span> <span data-ttu-id="2d7ab-130">Puede declarar el método `Main` de una de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="2d7ab-130">You can declare the `Main` method in one of the following ways:</span></span>

- <span data-ttu-id="2d7ab-131">Puede devolver `void`.</span><span class="sxs-lookup"><span data-stu-id="2d7ab-131">It can return `void`.</span></span>

     [!code-csharp[csProgGuideMain#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#12)]

- <span data-ttu-id="2d7ab-132">También puede devolver un entero.</span><span class="sxs-lookup"><span data-stu-id="2d7ab-132">It can also return an integer.</span></span>

     [!code-csharp[csProgGuideMain#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#13)]

- <span data-ttu-id="2d7ab-133">Puede tomar argumentos con cualquiera de los tipos de valor devueltos.</span><span class="sxs-lookup"><span data-stu-id="2d7ab-133">With either of the return types, it can take arguments.</span></span>

     [!code-csharp[csProgGuideMain#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#19)]

     <span data-ttu-id="2d7ab-134">o bien</span><span class="sxs-lookup"><span data-stu-id="2d7ab-134">-or-</span></span>

     [!code-csharp[csProgGuideMain#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#18)]

<span data-ttu-id="2d7ab-135">El parámetro del método `Main`, `args`, es una matriz `string` que contiene los argumentos de la línea de comandos usados para invocar el programa.</span><span class="sxs-lookup"><span data-stu-id="2d7ab-135">The parameter of the `Main` method, `args`, is a `string` array that contains the command-line arguments used to invoke the program.</span></span> <span data-ttu-id="2d7ab-136">A diferencia de C++, la matriz no incluye el nombre del archivo ejecutable (.exe).</span><span class="sxs-lookup"><span data-stu-id="2d7ab-136">Unlike in C++, the array does not include the name of the executable (exe) file.</span></span>

<span data-ttu-id="2d7ab-137">Para obtener más información sobre cómo usar los argumentos de la línea de comandos, vea los ejemplos de [Main() y argumentos de línea de comandos](../../../csharp/programming-guide/main-and-command-args/index.md) y [Cómo: Crear y utilizar ensamblados mediante la línea de comandos](../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-and-use-assemblies-using-the-command-line.md).</span><span class="sxs-lookup"><span data-stu-id="2d7ab-137">For more information about how to use command-line arguments, see the examples in [Main() and Command-Line Arguments](../../../csharp/programming-guide/main-and-command-args/index.md) and [How to: Create and Use Assemblies Using the Command Line](../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-and-use-assemblies-using-the-command-line.md).</span></span>

<span data-ttu-id="2d7ab-138">La llamada a <xref:System.Console.ReadKey%2A> al final del método `Main` evita que se cierre la ventana de la consola antes de que pueda leer la salida al ejecutar el programa en modo de depuración; para ello, presione F5.</span><span class="sxs-lookup"><span data-stu-id="2d7ab-138">The call to <xref:System.Console.ReadKey%2A> at the end of the `Main` method prevents the console window from closing before you have a chance to read the output when you run your program in debug mode, by pressing F5.</span></span>

## <a name="input-and-output"></a><span data-ttu-id="2d7ab-139">Entrada y salida</span><span class="sxs-lookup"><span data-stu-id="2d7ab-139">Input and output</span></span>

<span data-ttu-id="2d7ab-140">Los programas de C# suelen usar los servicios de entrada y salida proporcionados por la biblioteca en tiempo de ejecución de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2d7ab-140">C# programs generally use the input/output services provided by the run-time library of the .NET Framework.</span></span> <span data-ttu-id="2d7ab-141">La instrucción `System.Console.WriteLine("Hello World!");` utiliza el método <xref:System.Console.WriteLine%2A>.</span><span class="sxs-lookup"><span data-stu-id="2d7ab-141">The statement `System.Console.WriteLine("Hello World!");` uses the <xref:System.Console.WriteLine%2A> method.</span></span> <span data-ttu-id="2d7ab-142">Este es uno de los métodos de salida de la clase <xref:System.Console> en la biblioteca de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="2d7ab-142">This is one of the output methods of the <xref:System.Console> class in the run-time library.</span></span> <span data-ttu-id="2d7ab-143">Muestra el parámetro de cadena en la secuencia de salida estándar, seguida de una nueva línea.</span><span class="sxs-lookup"><span data-stu-id="2d7ab-143">It displays its string parameter on the standard output stream followed by a new line.</span></span> <span data-ttu-id="2d7ab-144">Hay otros métodos <xref:System.Console> disponibles para las distintas operaciones de entrada y salida.</span><span class="sxs-lookup"><span data-stu-id="2d7ab-144">Other <xref:System.Console> methods are available for different input and output operations.</span></span> <span data-ttu-id="2d7ab-145">Si incluye la directiva `using System;` al inicio del programa, puede usar directamente las clases y los métodos <xref:System> sin calificarlos totalmente.</span><span class="sxs-lookup"><span data-stu-id="2d7ab-145">If you include the `using System;` directive at the beginning of the program, you can directly use the <xref:System> classes and methods without fully qualifying them.</span></span> <span data-ttu-id="2d7ab-146">Por ejemplo, puede llamar a `Console.WriteLine` en vez de llamar a `System.Console.WriteLine`:</span><span class="sxs-lookup"><span data-stu-id="2d7ab-146">For example, you can call `Console.WriteLine` instead of `System.Console.WriteLine`:</span></span>

 [!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]

 [!code-csharp[csProgGuide#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#23)]

<span data-ttu-id="2d7ab-147">Para obtener más información sobre los métodos de entrada y salida, vea <xref:System.IO>.</span><span class="sxs-lookup"><span data-stu-id="2d7ab-147">For more information about input/output methods, see <xref:System.IO>.</span></span>

## <a name="command-line-compilation-and-execution"></a><span data-ttu-id="2d7ab-148">Compilación y ejecución de línea de comandos</span><span class="sxs-lookup"><span data-stu-id="2d7ab-148">Command-line compilation and execution</span></span>

<span data-ttu-id="2d7ab-149">Puede compilar el programa "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="2d7ab-149">You can compile the "Hello World!"</span></span> <span data-ttu-id="2d7ab-150">con la línea de comandos en lugar del entorno de desarrollo integrado (IDE) de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2d7ab-150">program by using the command line instead of the Visual Studio Integrated Development Environment (IDE).</span></span>

### <a name="to-compile-and-run-from-a-command-prompt"></a><span data-ttu-id="2d7ab-151">Para compilar y ejecutar desde un símbolo del sistema</span><span class="sxs-lookup"><span data-stu-id="2d7ab-151">To compile and run from a command prompt</span></span>

1. <span data-ttu-id="2d7ab-152">Pegue el código del procedimiento anterior en cualquier editor de texto y guarde el archivo como un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="2d7ab-152">Paste the code from the preceding procedure into any text editor, and then save the file as a text file.</span></span> <span data-ttu-id="2d7ab-153">Asigne al archivo el nombre `Hello.cs`.</span><span class="sxs-lookup"><span data-stu-id="2d7ab-153">Name the file `Hello.cs`.</span></span> <span data-ttu-id="2d7ab-154">Los archivos de código fuente de C# usan la extensión `.cs`.</span><span class="sxs-lookup"><span data-stu-id="2d7ab-154">C# source code files use the extension `.cs`.</span></span>

2. <span data-ttu-id="2d7ab-155">Siga uno de los pasos siguientes para abrir una ventana del símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="2d7ab-155">Perform one of the following steps to open a command-prompt window:</span></span>

    - <span data-ttu-id="2d7ab-156">En Windows 10, en el menú **Inicio**, busque `Developer Command Prompt` y pulse o elija **Developer Command Prompt for VS 2017** (Símbolo del sistema para desarrolladores de VS2017).</span><span class="sxs-lookup"><span data-stu-id="2d7ab-156">In Windows 10, on the **Start** menu, search for `Developer Command Prompt`, and then tap or choose **Developer Command Prompt for VS 2017**.</span></span>

         <span data-ttu-id="2d7ab-157">Aparecerá una ventana del símbolo del sistema para desarrolladores.</span><span class="sxs-lookup"><span data-stu-id="2d7ab-157">A Developer Command Prompt window appears.</span></span>

    - <span data-ttu-id="2d7ab-158">En Windows 7, abra el menú **Inicio**, expanda la carpeta de la versión actual de Visual Studio, abra el menú contextual de **Visual Studio Tools** y elija **Developer Command Prompt for VS 2017** (Símbolo del sistema para desarrolladores de VS2017).</span><span class="sxs-lookup"><span data-stu-id="2d7ab-158">In Windows 7, open the **Start** menu, expand the folder for the current version of Visual Studio, open the shortcut menu for **Visual Studio Tools**, and then choose **Developer Command Prompt for VS 2017**.</span></span>

         <span data-ttu-id="2d7ab-159">Aparecerá una ventana del símbolo del sistema para desarrolladores.</span><span class="sxs-lookup"><span data-stu-id="2d7ab-159">A Developer Command Prompt window appears.</span></span>

    - <span data-ttu-id="2d7ab-160">Habilite las compilaciones de la línea de comandos desde una ventana estándar del símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="2d7ab-160">Enable command-line builds from a standard Command Prompt window.</span></span>

         <span data-ttu-id="2d7ab-161">Vea [Cómo: Establecer variables de entorno para la línea de comandos de Visual Studio](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md).</span><span class="sxs-lookup"><span data-stu-id="2d7ab-161">See [How to: Set Environment Variables for the Visual Studio Command Line](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md).</span></span>

3. <span data-ttu-id="2d7ab-162">En la ventana del símbolo del sistema, vaya a la carpeta que contiene el archivo `Hello.cs`.</span><span class="sxs-lookup"><span data-stu-id="2d7ab-162">In the command-prompt window, navigate to the folder that contains your `Hello.cs` file.</span></span>

4. <span data-ttu-id="2d7ab-163">Escriba el comando siguiente para compilar `Hello.cs`.</span><span class="sxs-lookup"><span data-stu-id="2d7ab-163">Enter the following command to compile `Hello.cs`.</span></span>

     `csc Hello.cs`

     <span data-ttu-id="2d7ab-164">Si el programa no tiene ningún error de compilación, se creará un archivo ejecutable denominado `Hello.exe`.</span><span class="sxs-lookup"><span data-stu-id="2d7ab-164">If your program has no compilation errors, an executable file that is named `Hello.exe` is created.</span></span>

5. <span data-ttu-id="2d7ab-165">En la ventana del símbolo del sistema, escriba el siguiente comando para ejecutar el programa:</span><span class="sxs-lookup"><span data-stu-id="2d7ab-165">In the command-prompt window, enter the following command to run the program:</span></span>

     `Hello`

 <span data-ttu-id="2d7ab-166">Para obtener más información sobre el compilador de C# y sus opciones, vea [C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md) (Opciones del compilador de C#).</span><span class="sxs-lookup"><span data-stu-id="2d7ab-166">For more information about the C# compiler and its options, see [C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2d7ab-167">Vea también</span><span class="sxs-lookup"><span data-stu-id="2d7ab-167">See also</span></span>

- [<span data-ttu-id="2d7ab-168">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="2d7ab-168">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="2d7ab-169">Dentro de un programa de C#</span><span class="sxs-lookup"><span data-stu-id="2d7ab-169">Inside a C# Program</span></span>](../../../csharp/programming-guide/inside-a-program/index.md)
- [<span data-ttu-id="2d7ab-170">Cadenas</span><span class="sxs-lookup"><span data-stu-id="2d7ab-170">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)
- [<span data-ttu-id="2d7ab-171">Ejemplos y tutoriales</span><span class="sxs-lookup"><span data-stu-id="2d7ab-171">Samples and tutorials</span></span>](../../../samples-and-tutorials/index.md)
- [<span data-ttu-id="2d7ab-172">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="2d7ab-172">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="2d7ab-173">Main() y argumentos de la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="2d7ab-173">Main() and Command-Line Arguments</span></span>](../../../csharp/programming-guide/main-and-command-args/index.md)
- [<span data-ttu-id="2d7ab-174">Introducción a Visual C# y Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2d7ab-174">Getting Started with Visual C# and Visual Basic</span></span>](/visualstudio/ide/getting-started-with-visual-csharp-and-visual-basic)