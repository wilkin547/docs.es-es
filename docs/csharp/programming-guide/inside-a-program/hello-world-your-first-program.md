---
title: "Hello World, su primer programa (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: get-started-article
f1_keywords:
- cs.program
- vs.csharp.startpage.firstapplication
dev_langs:
- CSharp
helpviewer_keywords:
- examples [C#], Hello World
- Hello World example [C#]
ms.assetid: 6493182a-b0b6-4539-a719-518a168cb730
caps.latest.revision: 39
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: b7cb84362c96dac50ae5136334138b55ed1ce00b
ms.openlocfilehash: 03891f83885cf41ab157ebd78ef7e72767b4b163
ms.contentlocale: es-es
ms.lasthandoff: 07/31/2017

---
# <a name="hello-world----your-first-program-c-programming-guide"></a><span data-ttu-id="60ea0-102">Hello World, su primer programa (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="60ea0-102">Hello World -- Your First Program (C# Programming Guide)</span></span>
<span data-ttu-id="60ea0-103">En el siguiente procedimiento se crea una versión de C# del programa tradicional "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="60ea0-103">The following procedure creates a C# version of the traditional "Hello World!"</span></span> <span data-ttu-id="60ea0-104">.</span><span class="sxs-lookup"><span data-stu-id="60ea0-104">program.</span></span> <span data-ttu-id="60ea0-105">El programa muestra la cadena `Hello World!`.</span><span class="sxs-lookup"><span data-stu-id="60ea0-105">The program displays the string `Hello World!`</span></span>  
  
 <span data-ttu-id="60ea0-106">Para obtener más ejemplos de los conceptos preliminares, vea [Introducción a Visual C# y Visual Basic](/visualstudio/ide/getting-started-with-visual-csharp-and-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="60ea0-106">For more examples of introductory concepts, see [Getting Started with Visual C# and Visual Basic](/visualstudio/ide/getting-started-with-visual-csharp-and-visual-basic).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-and-run-a-console-application"></a><span data-ttu-id="60ea0-107">Para crear y ejecutar una aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="60ea0-107">To create and run a console application</span></span>  
  
1.  <span data-ttu-id="60ea0-108">Inicie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="60ea0-108">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="60ea0-109">En la barra de menús, elija **Archivo**, **Nuevo**, **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="60ea0-109">On the menu bar, choose **File**, **New**, **Project**.</span></span>  
  
     <span data-ttu-id="60ea0-110">Aparece el cuadro de diálogo **Nuevo proyecto** .</span><span class="sxs-lookup"><span data-stu-id="60ea0-110">The **New Project** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="60ea0-111">Expanda **Instalado**, **Plantillas**, **Visual C#** y, luego, elija **Aplicación de consola**.</span><span class="sxs-lookup"><span data-stu-id="60ea0-111">Expand **Installed**, expand **Templates**, expand **Visual C#**, and then choose **Console Application**.</span></span>  
  
4.  <span data-ttu-id="60ea0-112">En el cuadro **Nombre**, escriba un nombre para el proyecto y, después, elija el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="60ea0-112">In the **Name** box, specify a name for your project, and then choose the **OK** button.</span></span>  
  
     <span data-ttu-id="60ea0-113">El proyecto nuevo aparece en el **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="60ea0-113">The new project appears in **Solution Explorer**.</span></span>  
  
5.  <span data-ttu-id="60ea0-114">Si Program.cs no está abierto en el **Editor de código**, abra el menú contextual de **Program.cs** en el **Explorador de soluciones** y elija **Ver código**.</span><span class="sxs-lookup"><span data-stu-id="60ea0-114">If Program.cs isn't open in the **Code Editor**, open the shortcut menu for **Program.cs** in **Solution Explorer**, and then choose **View Code**.</span></span>  
  
6.  <span data-ttu-id="60ea0-115">Reemplace el contenido de Program.cs por el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="60ea0-115">Replace the contents of Program.cs with the following code.</span></span>  
  
     <span data-ttu-id="60ea0-116">[!code-cs[csProgGuide#21](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="60ea0-116">[!code-cs[csProgGuide#21](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_1.cs)]</span></span>  
  
7.  <span data-ttu-id="60ea0-117">Pulse la tecla F5 para ejecutar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="60ea0-117">Choose the F5 key to run the project.</span></span> <span data-ttu-id="60ea0-118">Aparecerá una ventana del símbolo del sistema que contiene la línea `Hello World!`.</span><span class="sxs-lookup"><span data-stu-id="60ea0-118">A Command Prompt window appears that contains the line `Hello World!`</span></span>  
  
 <span data-ttu-id="60ea0-119">Después se examinan las partes importantes de este programa.</span><span class="sxs-lookup"><span data-stu-id="60ea0-119">Next, the important parts of this program are examined.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="60ea0-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="60ea0-120">Comments</span></span>  
 <span data-ttu-id="60ea0-121">La primera línea contiene un comentario.</span><span class="sxs-lookup"><span data-stu-id="60ea0-121">The first line contains a comment.</span></span> <span data-ttu-id="60ea0-122">Los caracteres `//` convierten el resto de la línea en un comentario.</span><span class="sxs-lookup"><span data-stu-id="60ea0-122">The characters `//` convert the rest of the line to a comment.</span></span>  
  
 <span data-ttu-id="60ea0-123">[!code-cs[csProgGuide#32](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="60ea0-123">[!code-cs[csProgGuide#32](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_2.cs)]</span></span>  
  
 <span data-ttu-id="60ea0-124">También puede convertir un bloque de texto en un comentario escribiéndolo entre los caracteres `/*` y `*/`.</span><span class="sxs-lookup"><span data-stu-id="60ea0-124">You can also comment out a block of text by enclosing it between the `/*` and `*/` characters.</span></span> <span data-ttu-id="60ea0-125">Esta implementación se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="60ea0-125">This is shown in the following example.</span></span>  
  
 <span data-ttu-id="60ea0-126">[!code-cs[csProgGuide#33](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="60ea0-126">[!code-cs[csProgGuide#33](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_3.cs)]</span></span>  
  
## <a name="main-method"></a><span data-ttu-id="60ea0-127">Método main</span><span class="sxs-lookup"><span data-stu-id="60ea0-127">Main Method</span></span>  
 <span data-ttu-id="60ea0-128">Una aplicación de la consola de C# debe contener un método `Main`, en el que se inicia y finaliza un control.</span><span class="sxs-lookup"><span data-stu-id="60ea0-128">A C# console application must contain a `Main` method, in which control starts and ends.</span></span> <span data-ttu-id="60ea0-129">El método `Main` es donde se crean los objetos y se ejecutan otros métodos.</span><span class="sxs-lookup"><span data-stu-id="60ea0-129">The `Main` method is where you create objects and execute other methods.</span></span>  
  
 <span data-ttu-id="60ea0-130">El método `Main` es un método [estático](../../../csharp/language-reference/keywords/static.md) que reside dentro de una clase o de un struct.</span><span class="sxs-lookup"><span data-stu-id="60ea0-130">The `Main` method is a [static](../../../csharp/language-reference/keywords/static.md) method that resides inside a class or a struct.</span></span> <span data-ttu-id="60ea0-131">En el ejemplo anterior de "Hello World!",</span><span class="sxs-lookup"><span data-stu-id="60ea0-131">In the previous "Hello World!"</span></span> <span data-ttu-id="60ea0-132">reside en una clase denominada `Hello`.</span><span class="sxs-lookup"><span data-stu-id="60ea0-132">example, it resides in a class named `Hello`.</span></span> <span data-ttu-id="60ea0-133">Puede declarar el método `Main` de una de las siguientes maneras:</span><span class="sxs-lookup"><span data-stu-id="60ea0-133">You can declare the `Main` method in one of the following ways:</span></span>  
  
-   <span data-ttu-id="60ea0-134">Puede devolver `void`.</span><span class="sxs-lookup"><span data-stu-id="60ea0-134">It can return `void`.</span></span>  
  
     <span data-ttu-id="60ea0-135">[!code-cs[csProgGuideMain#12](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="60ea0-135">[!code-cs[csProgGuideMain#12](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_4.cs)]</span></span>  
  
-   <span data-ttu-id="60ea0-136">También puede devolver un entero.</span><span class="sxs-lookup"><span data-stu-id="60ea0-136">It can also return an integer.</span></span>  
  
     <span data-ttu-id="60ea0-137">[!code-cs[csProgGuideMain#13](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="60ea0-137">[!code-cs[csProgGuideMain#13](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_5.cs)]</span></span>  
  
-   <span data-ttu-id="60ea0-138">Puede tomar argumentos con cualquiera de los tipos de valor devueltos.</span><span class="sxs-lookup"><span data-stu-id="60ea0-138">With either of the return types, it can take arguments.</span></span>  
  
     <span data-ttu-id="60ea0-139">[!code-cs[csProgGuideMain#19](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="60ea0-139">[!code-cs[csProgGuideMain#19](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_6.cs)]</span></span>  
  
     <span data-ttu-id="60ea0-140">O bien</span><span class="sxs-lookup"><span data-stu-id="60ea0-140">-or-</span></span>  
  
     <span data-ttu-id="60ea0-141">[!code-cs[csProgGuideMain#18](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="60ea0-141">[!code-cs[csProgGuideMain#18](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_7.cs)]</span></span>  
  
 <span data-ttu-id="60ea0-142">El parámetro del método `Main`, `args`, es una matriz `string` que contiene los argumentos de la línea de comandos usados para invocar el programa.</span><span class="sxs-lookup"><span data-stu-id="60ea0-142">The parameter of the `Main` method, `args`, is a `string` array that contains the command-line arguments used to invoke the program.</span></span> <span data-ttu-id="60ea0-143">A diferencia de C++, la matriz no incluye el nombre del archivo ejecutable (.exe).</span><span class="sxs-lookup"><span data-stu-id="60ea0-143">Unlike in C++, the array does not include the name of the executable (exe) file.</span></span>  
  
 <span data-ttu-id="60ea0-144">Para obtener más información sobre cómo usar los argumentos de la línea de comandos, vea los ejemplos de [Main() y argumentos de línea de comandos](../../../csharp/programming-guide/main-and-command-args/index.md) y [Cómo: Crear y utilizar ensamblados desde la línea de comandos](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4).</span><span class="sxs-lookup"><span data-stu-id="60ea0-144">For more information about how to use command-line arguments, see the examples in [Main() and Command-Line Arguments](../../../csharp/programming-guide/main-and-command-args/index.md) and [How to: Create and Use Assemblies Using the Command Line](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4).</span></span>  
  
 <span data-ttu-id="60ea0-145">La llamada a <xref:System.Console.ReadKey%2A> al final del método `Main` evita que se cierre la ventana de la consola antes de que pueda leer la salida al ejecutar el programa en modo de depuración; para ello, presione F5.</span><span class="sxs-lookup"><span data-stu-id="60ea0-145">The call to <xref:System.Console.ReadKey%2A> at the end of the `Main` method prevents the console window from closing before you have a chance to read the output when you run your program in debug mode, by pressing F5.</span></span>  
  
## <a name="input-and-output"></a><span data-ttu-id="60ea0-146">Entrada y salida</span><span class="sxs-lookup"><span data-stu-id="60ea0-146">Input and Output</span></span>  
 <span data-ttu-id="60ea0-147">Los programas de C# suelen usar los servicios de entrada y salida proporcionados por la biblioteca en tiempo de ejecución de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="60ea0-147">C# programs generally use the input/output services provided by the run-time library of the .NET Framework.</span></span> <span data-ttu-id="60ea0-148">La instrucción `System.Console.WriteLine("Hello World!");` utiliza el método <xref:System.Console.WriteLine%2A>.</span><span class="sxs-lookup"><span data-stu-id="60ea0-148">The statement `System.Console.WriteLine("Hello World!");` uses the <xref:System.Console.WriteLine%2A> method.</span></span> <span data-ttu-id="60ea0-149">Este es uno de los métodos de salida de la clase <xref:System.Console> en la biblioteca de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="60ea0-149">This is one of the output methods of the <xref:System.Console> class in the run-time library.</span></span> <span data-ttu-id="60ea0-150">Muestra el parámetro de cadena en la secuencia de salida estándar, seguida de una nueva línea.</span><span class="sxs-lookup"><span data-stu-id="60ea0-150">It displays its string parameter on the standard output stream followed by a new line.</span></span> <span data-ttu-id="60ea0-151">Hay otros métodos <xref:System.Console> disponibles para las distintas operaciones de entrada y salida.</span><span class="sxs-lookup"><span data-stu-id="60ea0-151">Other <xref:System.Console> methods are available for different input and output operations.</span></span> <span data-ttu-id="60ea0-152">Si incluye la directiva `using System;` al inicio del programa, puede usar directamente las clases y los métodos <xref:System> sin calificarlos totalmente.</span><span class="sxs-lookup"><span data-stu-id="60ea0-152">If you include the `using System;` directive at the beginning of the program, you can directly use the <xref:System> classes and methods without fully qualifying them.</span></span> <span data-ttu-id="60ea0-153">Por ejemplo, puede llamar a `Console.WriteLine` en vez de llamar a `System.Console.WriteLine`:</span><span class="sxs-lookup"><span data-stu-id="60ea0-153">For example, you can call `Console.WriteLine` instead of `System.Console.WriteLine`:</span></span>  
  
 <span data-ttu-id="60ea0-154">[!code-cs[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_8.cs)]</span><span class="sxs-lookup"><span data-stu-id="60ea0-154">[!code-cs[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_8.cs)]</span></span>  
  
 <span data-ttu-id="60ea0-155">[!code-cs[csProgGuide#23](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_9.cs)]</span><span class="sxs-lookup"><span data-stu-id="60ea0-155">[!code-cs[csProgGuide#23](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/hello-world-your-first-program_9.cs)]</span></span>  
  
 <span data-ttu-id="60ea0-156">Para obtener más información sobre los métodos de entrada y salida, vea <xref:System.IO>.</span><span class="sxs-lookup"><span data-stu-id="60ea0-156">For more information about input/output methods, see <xref:System.IO>.</span></span>  
  
## <a name="command-line-compilation-and-execution"></a><span data-ttu-id="60ea0-157">Compilación y ejecución en la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="60ea0-157">Command-Line Compilation and Execution</span></span>  
 <span data-ttu-id="60ea0-158">Puede compilar el programa "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="60ea0-158">You can compile the "Hello World!"</span></span> <span data-ttu-id="60ea0-159">con la línea de comandos en lugar del entorno de desarrollo integrado (IDE) de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="60ea0-159">program by using the command line instead of the Visual Studio Integrated Development Environment (IDE).</span></span>  
  
#### <a name="to-compile-and-run-from-a-command-prompt"></a><span data-ttu-id="60ea0-160">Para compilar y ejecutar desde un símbolo del sistema</span><span class="sxs-lookup"><span data-stu-id="60ea0-160">To compile and run from a command prompt</span></span>  
  
1.  <span data-ttu-id="60ea0-161">Pegue el código del procedimiento anterior en cualquier editor de texto y guarde el archivo como un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="60ea0-161">Paste the code from the preceding procedure into any text editor, and then save the file as a text file.</span></span> <span data-ttu-id="60ea0-162">Asigne al archivo el nombre `Hello.cs`.</span><span class="sxs-lookup"><span data-stu-id="60ea0-162">Name the file `Hello.cs`.</span></span> <span data-ttu-id="60ea0-163">Los archivos de código fuente de C# usan la extensión `.cs`.</span><span class="sxs-lookup"><span data-stu-id="60ea0-163">C# source code files use the extension `.cs`.</span></span>  
  
2.  <span data-ttu-id="60ea0-164">Siga uno de los pasos siguientes para abrir una ventana del símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="60ea0-164">Perform one of the following steps to open a command-prompt window:</span></span>  
  
    -   <span data-ttu-id="60ea0-165">En Windows 10, en el menú **Inicio**, busque `Developer Command Prompt` y pulse o elija **Developer Command Prompt for VS 2017** (Símbolo del sistema para desarrolladores de VS2017).</span><span class="sxs-lookup"><span data-stu-id="60ea0-165">In Windows 10, on the **Start** menu, search for `Developer Command Prompt`, and then tap or choose **Developer Command Prompt for VS 2017**.</span></span>  
  
         <span data-ttu-id="60ea0-166">Aparecerá una ventana del símbolo del sistema para desarrolladores.</span><span class="sxs-lookup"><span data-stu-id="60ea0-166">A Developer Command Prompt window appears.</span></span>  
  
    -   <span data-ttu-id="60ea0-167">En Windows 7, abra el menú **Inicio**, expanda la carpeta de la versión actual de Visual Studio, abra el menú contextual de **Visual Studio Tools** y elija **Developer Command Prompt for VS 2017** (Símbolo del sistema para desarrolladores de VS2017).</span><span class="sxs-lookup"><span data-stu-id="60ea0-167">In Windows 7, open the **Start** menu, expand the folder for the current version of Visual Studio, open the shortcut menu for **Visual Studio Tools**, and then choose **Developer Command Prompt for VS 2017**.</span></span>  
  
         <span data-ttu-id="60ea0-168">Aparecerá una ventana del símbolo del sistema para desarrolladores.</span><span class="sxs-lookup"><span data-stu-id="60ea0-168">A Developer Command Prompt window appears.</span></span>  
  
    -   <span data-ttu-id="60ea0-169">Habilite las compilaciones de la línea de comandos desde una ventana estándar del símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="60ea0-169">Enable command-line builds from a standard Command Prompt window.</span></span>  
  
         <span data-ttu-id="60ea0-170">Vea [Cómo: Establecer variables de entorno para la línea de comandos de Visual Studio](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md).</span><span class="sxs-lookup"><span data-stu-id="60ea0-170">See [How to: Set Environment Variables for the Visual Studio Command Line](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md).</span></span>  
  
3.  <span data-ttu-id="60ea0-171">En la ventana del símbolo del sistema, vaya a la carpeta que contiene el archivo `Hello.cs`.</span><span class="sxs-lookup"><span data-stu-id="60ea0-171">In the command-prompt window, navigate to the folder that contains your `Hello.cs` file.</span></span>  
  
4.  <span data-ttu-id="60ea0-172">Escriba el comando siguiente para compilar `Hello.cs`.</span><span class="sxs-lookup"><span data-stu-id="60ea0-172">Enter the following command to compile `Hello.cs`.</span></span>  
  
     `csc Hello.cs`  
  
     <span data-ttu-id="60ea0-173">Si el programa no tiene ningún error de compilación, se creará un archivo ejecutable denominado `Hello.exe`.</span><span class="sxs-lookup"><span data-stu-id="60ea0-173">If your program has no compilation errors, an executable file that is named `Hello.exe` is created.</span></span>  
  
5.  <span data-ttu-id="60ea0-174">En la ventana del símbolo del sistema, escriba el siguiente comando para ejecutar el programa:</span><span class="sxs-lookup"><span data-stu-id="60ea0-174">In the command-prompt window, enter the following command to run the program:</span></span>  
  
     `Hello`  
  
 <span data-ttu-id="60ea0-175">Para obtener más información sobre el compilador de C# y sus opciones, vea [C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md) (Opciones del compilador de C#).</span><span class="sxs-lookup"><span data-stu-id="60ea0-175">For more information about the C# compiler and its options, see [C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="60ea0-176">Vea también</span><span class="sxs-lookup"><span data-stu-id="60ea0-176">See Also</span></span>  
 <span data-ttu-id="60ea0-177">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="60ea0-177">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="60ea0-178">[Dentro de un programa de C#](../../../csharp/programming-guide/inside-a-program/index.md) </span><span class="sxs-lookup"><span data-stu-id="60ea0-178">[Inside a C# Program](../../../csharp/programming-guide/inside-a-program/index.md) </span></span>  
 <span data-ttu-id="60ea0-179">[Cadenas](../../../csharp/programming-guide/strings/index.md) </span><span class="sxs-lookup"><span data-stu-id="60ea0-179">[Strings](../../../csharp/programming-guide/strings/index.md) </span></span>  
 <span data-ttu-id="60ea0-180">[\<paveover>C# Sample Applications](http://msdn.microsoft.com/en-us/9a9d7aaa-51d3-4224-b564-95409b0f3e15)  (<paveover> Aplicaciones de ejemplo de C#)</span><span class="sxs-lookup"><span data-stu-id="60ea0-180">[\<paveover>C# Sample Applications](http://msdn.microsoft.com/en-us/9a9d7aaa-51d3-4224-b564-95409b0f3e15) </span></span>  
 <span data-ttu-id="60ea0-181">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="60ea0-181">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="60ea0-182">[Main() y argumentos de línea de comandos](../../../csharp/programming-guide/main-and-command-args/index.md) </span><span class="sxs-lookup"><span data-stu-id="60ea0-182">[Main() and Command-Line Arguments](../../../csharp/programming-guide/main-and-command-args/index.md) </span></span>  
 [<span data-ttu-id="60ea0-183">Introducción a Visual C# y Visual Basic</span><span class="sxs-lookup"><span data-stu-id="60ea0-183">Getting Started with Visual C# and Visual Basic</span></span>](/visualstudio/ide/getting-started-with-visual-csharp-and-visual-basic)

