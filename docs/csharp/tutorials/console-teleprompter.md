---
title: Aplicación de consola
description: Este tutorial le enseña varias características de .NET Core y el lenguaje C#.
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 883cd93d-50ce-4144-b7c9-2df28d9c11a0
ms.openlocfilehash: dba6125dd359a47115b0f363a081dc000ce29e6a
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2018
---
# <a name="console-application"></a><span data-ttu-id="3987e-104">Aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="3987e-104">Console Application</span></span>

<span data-ttu-id="3987e-105">Este tutorial le enseña varias características de .NET Core y el lenguaje C#.</span><span class="sxs-lookup"><span data-stu-id="3987e-105">This tutorial teaches you a number of features in .NET Core and the C# language.</span></span> <span data-ttu-id="3987e-106">Aprenderá lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3987e-106">You’ll learn:</span></span>

- <span data-ttu-id="3987e-107">Los aspectos básicos de la interfaz de línea de comandos (CLI) de .NET Core</span><span class="sxs-lookup"><span data-stu-id="3987e-107">The basics of the .NET Core Command Line Interface (CLI)</span></span>
- <span data-ttu-id="3987e-108">La estructura de una aplicación de consola en C#</span><span class="sxs-lookup"><span data-stu-id="3987e-108">The structure of a C# Console Application</span></span>
- <span data-ttu-id="3987e-109">E/S de consola</span><span class="sxs-lookup"><span data-stu-id="3987e-109">Console I/O</span></span>
- <span data-ttu-id="3987e-110">Aspectos básicos de las API de E/S de archivo en .NET</span><span class="sxs-lookup"><span data-stu-id="3987e-110">The basics of File I/O APIs in .NET</span></span>
- <span data-ttu-id="3987e-111">Aspectos básicos de la programación asincrónica basada en tareas en .NET</span><span class="sxs-lookup"><span data-stu-id="3987e-111">The basics of the Task-based Asynchronous Programming in .NET</span></span>

<span data-ttu-id="3987e-112">Creará una aplicación que lea un archivo de texto y refleje el contenido de ese archivo de texto en la consola.</span><span class="sxs-lookup"><span data-stu-id="3987e-112">You’ll build an application that reads a text file, and echoes the contents of that text file to the console.</span></span> <span data-ttu-id="3987e-113">El ritmo de la salida a la consola se ajusta para que coincida con la lectura en voz alta.</span><span class="sxs-lookup"><span data-stu-id="3987e-113">The output to the console is paced to match reading it aloud.</span></span> <span data-ttu-id="3987e-114">Para aumentar o reducir el ritmo, presione las teclas "<" o ">".</span><span class="sxs-lookup"><span data-stu-id="3987e-114">You can speed up or slow down the pace by pressing the ‘<’ or ‘>’ keys.</span></span>

<span data-ttu-id="3987e-115">Hay muchas características en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="3987e-115">There are a lot of features in this tutorial.</span></span> <span data-ttu-id="3987e-116">Vamos a compilarlas una a una.</span><span class="sxs-lookup"><span data-stu-id="3987e-116">Let’s build them one by one.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3987e-117">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="3987e-117">Prerequisites</span></span>

<span data-ttu-id="3987e-118">Deberá configurar la máquina para ejecutar .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3987e-118">You’ll need to setup your machine to run .NET Core.</span></span> <span data-ttu-id="3987e-119">Puede encontrar las instrucciones de instalación en la página de [.NET Core](https://www.microsoft.com/net/core).</span><span class="sxs-lookup"><span data-stu-id="3987e-119">You can find the installation instructions on the [.NET Core](https://www.microsoft.com/net/core) page.</span></span> <span data-ttu-id="3987e-120">Puede ejecutar esta aplicación en Windows, Linux, Mac OS o en un contenedor de Docker.</span><span class="sxs-lookup"><span data-stu-id="3987e-120">You can run this application on Windows, Linux, macOS or in a Docker container.</span></span>
<span data-ttu-id="3987e-121">Deberá instalar su editor de código favorito.</span><span class="sxs-lookup"><span data-stu-id="3987e-121">You’ll need to install your favorite code editor.</span></span>

## <a name="create-the-application"></a><span data-ttu-id="3987e-122">Crear la aplicación</span><span class="sxs-lookup"><span data-stu-id="3987e-122">Create the Application</span></span>

<span data-ttu-id="3987e-123">El primer paso es crear una nueva aplicación.</span><span class="sxs-lookup"><span data-stu-id="3987e-123">The first step is to create a new application.</span></span> <span data-ttu-id="3987e-124">Abra un símbolo del sistema y cree un nuevo directorio para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3987e-124">Open a command prompt and create a new directory for your application.</span></span> <span data-ttu-id="3987e-125">Conviértalo en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="3987e-125">Make that the current directory.</span></span> <span data-ttu-id="3987e-126">Escriba el comando `dotnet new console` en el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="3987e-126">Type the command `dotnet new console` at the command prompt.</span></span> <span data-ttu-id="3987e-127">Esta acción crea los archivos de inicio para una aplicación básica "Hola mundo".</span><span class="sxs-lookup"><span data-stu-id="3987e-127">This creates the starter files for a basic "Hello World" application.</span></span>

<span data-ttu-id="3987e-128">Antes de comenzar a realizar modificaciones, vamos a recorrer los pasos para ejecutar la aplicación Hola a todos sencilla.</span><span class="sxs-lookup"><span data-stu-id="3987e-128">Before you start making modifications, let’s go through the steps to run the simple Hello World application.</span></span> <span data-ttu-id="3987e-129">Después de crear la aplicación, escriba `dotnet restore` en el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="3987e-129">After creating the application, type `dotnet restore` at the command prompt.</span></span> <span data-ttu-id="3987e-130">Este comando ejecuta el proceso de restauración de paquetes de NuGet.</span><span class="sxs-lookup"><span data-stu-id="3987e-130">This command runs the NuGet package restore process.</span></span> <span data-ttu-id="3987e-131">NuGet es un administrador de paquetes .NET.</span><span class="sxs-lookup"><span data-stu-id="3987e-131">NuGet is a .NET package manager.</span></span> <span data-ttu-id="3987e-132">Este comando permite descargar cualquiera de las dependencias que faltan para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="3987e-132">This command downloads any of the missing dependencies for your project.</span></span> <span data-ttu-id="3987e-133">Como se trata de un nuevo proyecto, ninguna de las dependencias está en su lugar, así que con la primera ejecución se descargará .NET Core Framework.</span><span class="sxs-lookup"><span data-stu-id="3987e-133">As this is a new project, none of the dependencies are in place, so the first run will download the .NET Core framework.</span></span> <span data-ttu-id="3987e-134">Después de este paso inicial, solo deberá ejecutar `dotnet restore` al agregar nuevos paquetes dependientes, o actualizar las versiones de cualquiera de sus dependencias.</span><span class="sxs-lookup"><span data-stu-id="3987e-134">After this initial step, you will only need to run `dotnet restore` when you add new dependent packages, or update the versions of any of your dependencies.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="3987e-135">Después de restaurar los paquetes, ejecutará `dotnet build`.</span><span class="sxs-lookup"><span data-stu-id="3987e-135">After restoring packages, you run `dotnet build`.</span></span> <span data-ttu-id="3987e-136">Esta acción ejecuta el motor de compilación y crea el ejecutable de aplicación.</span><span class="sxs-lookup"><span data-stu-id="3987e-136">This executes the build engine and creates your application executable.</span></span> <span data-ttu-id="3987e-137">Por último, ejecute `dotnet run` para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3987e-137">Finally, you execute `dotnet run` to run your application.</span></span>

<span data-ttu-id="3987e-138">El código de la aplicación sencilla Hola a todos está todo en Program.cs.</span><span class="sxs-lookup"><span data-stu-id="3987e-138">The simple Hello World application code is all in Program.cs.</span></span> <span data-ttu-id="3987e-139">Abra ese archivo con el editor de texto de su elección.</span><span class="sxs-lookup"><span data-stu-id="3987e-139">Open that file with your favorite text editor.</span></span> <span data-ttu-id="3987e-140">Nos disponemos a realizar nuestros primeros cambios.</span><span class="sxs-lookup"><span data-stu-id="3987e-140">We’re about to make our first changes.</span></span>
<span data-ttu-id="3987e-141">En la parte superior del archivo, verá una instrucción using:</span><span class="sxs-lookup"><span data-stu-id="3987e-141">At the top of the file, see a using statement:</span></span>

```csharp
using System;
```

<span data-ttu-id="3987e-142">Esta instrucción indica al compilador que cualquier tipo del espacio de nombres `System` está en el ámbito.</span><span class="sxs-lookup"><span data-stu-id="3987e-142">This statement tells the compiler that any types from the `System` namespace are in scope.</span></span> <span data-ttu-id="3987e-143">Al igual que otros lenguajes orientados a objetos que pueda haber usado, C# utiliza espacios de nombres para organizar los tipos.</span><span class="sxs-lookup"><span data-stu-id="3987e-143">Like other Object Oriented languages you may have used, C# uses namespaces to organize types.</span></span> <span data-ttu-id="3987e-144">Este programa Hola mundo no es diferente.</span><span class="sxs-lookup"><span data-stu-id="3987e-144">This Hello World program is no different.</span></span> <span data-ttu-id="3987e-145">Puede ver que el programa se incluye en el espacio de nombres y el nombre se basa en el del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="3987e-145">You can see that the program is enclosed in the namespace with the name based on the name of the current directory.</span></span> <span data-ttu-id="3987e-146">Para este tutorial, vamos a cambiar el nombre del espacio de nombres por `TeleprompterConsole`:</span><span class="sxs-lookup"><span data-stu-id="3987e-146">For this tutorial, let's change the name of the namespace to `TeleprompterConsole`:</span></span>

```csharp
namespace TeleprompterConsole
```

## <a name="reading-and-echoing-the-file"></a><span data-ttu-id="3987e-147">Lectura y reflejo del archivo</span><span class="sxs-lookup"><span data-stu-id="3987e-147">Reading and Echoing the File</span></span>

<span data-ttu-id="3987e-148">La primera característica que se va a agregar es la capacidad de leer un archivo de texto y visualizar todo ese texto en la consola.</span><span class="sxs-lookup"><span data-stu-id="3987e-148">The first feature to add is the ability to read a text file and display all that text to the console.</span></span> <span data-ttu-id="3987e-149">En primer lugar, vamos a agregar un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="3987e-149">First, let’s add a text file.</span></span> <span data-ttu-id="3987e-150">Copie el archivo [sampleQuotes.txt](https://github.com/dotnet/samples/raw/master/csharp/getting-started/console-teleprompter/sampleQuotes.txt) del repositorio de GitHub de este [ejemplo](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-teleprompter) en su directorio del proyecto.</span><span class="sxs-lookup"><span data-stu-id="3987e-150">Copy the [sampleQuotes.txt](https://github.com/dotnet/samples/raw/master/csharp/getting-started/console-teleprompter/sampleQuotes.txt) file from the GitHub repository for this [sample](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-teleprompter) into your project directory.</span></span> <span data-ttu-id="3987e-151">Servirá como script para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3987e-151">This will serve as the script for your application.</span></span> <span data-ttu-id="3987e-152">Si quiere obtener información sobre cómo descargar la aplicación de ejemplo de este tema, vea las instrucciones del tema [Ejemplos y tutoriales](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="3987e-152">If you would like information on how to download the sample app for this topic, see the instructions in the [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples) topic.</span></span>

<span data-ttu-id="3987e-153">Luego, agregue el siguiente método a la clase `Program` (justo debajo del método `Main`):</span><span class="sxs-lookup"><span data-stu-id="3987e-153">Next, add the following method in your `Program` class (right below the `Main` method):</span></span>

```csharp
static IEnumerable<string> ReadFrom(string file)
{
    string line;
    using (var reader = File.OpenText(file))
    {
        while ((line = reader.ReadLine()) != null)
        {
            yield return line;
        }
    }
}
```

<span data-ttu-id="3987e-154">Este método usa tipos de dos nuevos espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="3987e-154">This method uses types from two new namespaces.</span></span> <span data-ttu-id="3987e-155">Para compilar esto, deberá agregar las dos líneas siguientes a la parte superior del archivo:</span><span class="sxs-lookup"><span data-stu-id="3987e-155">For this to compile you’ll need to add the following two lines to the top of the file:</span></span>

```csharp
using System.Collections.Generic;
using System.IO;
```

<span data-ttu-id="3987e-156">La interfaz <xref:System.Collections.Generic.IEnumerable%601> se define en el espacio de nombres <xref:System.Collections.Generic>.</span><span class="sxs-lookup"><span data-stu-id="3987e-156">The <xref:System.Collections.Generic.IEnumerable%601> interface is defined in the <xref:System.Collections.Generic> namespace.</span></span> <span data-ttu-id="3987e-157">La clase <xref:System.IO.File> se define en el espacio de nombres <xref:System.IO>.</span><span class="sxs-lookup"><span data-stu-id="3987e-157">The <xref:System.IO.File> class is defined in the <xref:System.IO> namespace.</span></span>

<span data-ttu-id="3987e-158">Este método es un tipo especial de método de C# llamado *método de iterador*.</span><span class="sxs-lookup"><span data-stu-id="3987e-158">This method is a special type of C# method called an *Iterator method*.</span></span> <span data-ttu-id="3987e-159">Los métodos de enumerador devuelven secuencias que se evalúan de forma diferida.</span><span class="sxs-lookup"><span data-stu-id="3987e-159">Enumerator methods return sequences that are evaluated lazily.</span></span> <span data-ttu-id="3987e-160">Eso significa que cada elemento de la secuencia se genera como lo solicita el código que consume la secuencia.</span><span class="sxs-lookup"><span data-stu-id="3987e-160">That means each item in the sequence is generated as it is requested by the code consuming the sequence.</span></span> <span data-ttu-id="3987e-161">Los métodos de enumerador son métodos que contienen una o varias instrucciones [`yield return`](../language-reference/keywords/yield.md).</span><span class="sxs-lookup"><span data-stu-id="3987e-161">Enumerator methods are methods that contain one or more [`yield return`](../language-reference/keywords/yield.md) statements.</span></span> <span data-ttu-id="3987e-162">El objeto que devuelve el método `ReadFrom` contiene el código para generar cada elemento en la secuencia.</span><span class="sxs-lookup"><span data-stu-id="3987e-162">The object returned by the `ReadFrom` method contains the code to generate each item in the sequence.</span></span> <span data-ttu-id="3987e-163">En este ejemplo, que implica la lectura de la siguiente línea de texto del archivo de origen y la devolución de esa cadena,</span><span class="sxs-lookup"><span data-stu-id="3987e-163">In this example, that involves reading the next line of text from the source file, and returning that string.</span></span> <span data-ttu-id="3987e-164">cada vez que el código de llamada solicita el siguiente elemento de la secuencia, el código lee la siguiente línea de texto del archivo y la devuelve.</span><span class="sxs-lookup"><span data-stu-id="3987e-164">Each time the calling code requests the next item from the sequence, the code reads the next line of text from the file and returns it.</span></span> <span data-ttu-id="3987e-165">Cuando el archivo se ha leído completamente, la secuencia indica que no hay más elementos.</span><span class="sxs-lookup"><span data-stu-id="3987e-165">When the file is completely read, the sequence indicates that there are no more items.</span></span>

<span data-ttu-id="3987e-166">Hay otros dos elementos de la sintaxis de C# con los que podría no estar familiarizado.</span><span class="sxs-lookup"><span data-stu-id="3987e-166">There are two other C# syntax elements that may be new to you.</span></span> <span data-ttu-id="3987e-167">La instrucción [`using`](../language-reference/keywords/using-statement.md) de este método administra la limpieza de recursos.</span><span class="sxs-lookup"><span data-stu-id="3987e-167">The [`using`](../language-reference/keywords/using-statement.md) statement in this method manages resource cleanup.</span></span> <span data-ttu-id="3987e-168">La variable que se inicializa en la instrucción `using` (`reader`, en este ejemplo) debe implementar la interfaz <xref:System.IDisposable>.</span><span class="sxs-lookup"><span data-stu-id="3987e-168">The variable that is initialized in the `using` statement (`reader`, in this example) must implement the <xref:System.IDisposable> interface.</span></span> <span data-ttu-id="3987e-169">Esa interfaz define un único método, `Dispose`, que se debe llamar cuando sea necesario liberar el recurso.</span><span class="sxs-lookup"><span data-stu-id="3987e-169">That interface defines a single method, `Dispose`, that should be called when the resource should be released.</span></span> <span data-ttu-id="3987e-170">El compilador genera esa llamada cuando la ejecución llega a la llave de cierre de la instrucción `using`.</span><span class="sxs-lookup"><span data-stu-id="3987e-170">The compiler generates that call when execution reaches the closing brace of the `using` statement.</span></span> <span data-ttu-id="3987e-171">El código generado por el compilador garantiza que el recurso se libera incluso si se produce una excepción desde el código en el bloqueo definido mediante la instrucción using.</span><span class="sxs-lookup"><span data-stu-id="3987e-171">The compiler-generated code ensures that the resource is released even if an exception is thrown from the code in the block defined by the using statement.</span></span>

<span data-ttu-id="3987e-172">La variable `reader` se define mediante la palabra clave `var`.</span><span class="sxs-lookup"><span data-stu-id="3987e-172">The `reader` variable is defined using the `var` keyword.</span></span> <span data-ttu-id="3987e-173">[`var`](../language-reference/keywords/var.md) define una *variable local con tipo implícito*.</span><span class="sxs-lookup"><span data-stu-id="3987e-173">[`var`](../language-reference/keywords/var.md) defines an *implicitly typed local variable*.</span></span> <span data-ttu-id="3987e-174">Esto significa que el tipo de la variable viene determinado por el tipo en tiempo de compilación del objeto asignado a la variable.</span><span class="sxs-lookup"><span data-stu-id="3987e-174">That means the type of the variable is determined by the compile-time type of the object assigned to the variable.</span></span> <span data-ttu-id="3987e-175">Aquí, ese es el valor devuelto por el método <xref:System.IO.File.OpenText(System.String)>, que es un objeto <xref:System.IO.StreamReader>.</span><span class="sxs-lookup"><span data-stu-id="3987e-175">Here, that is the return value from the <xref:System.IO.File.OpenText(System.String)> method, which is a <xref:System.IO.StreamReader> object.</span></span>

<span data-ttu-id="3987e-176">Ahora, vamos a rellenar el código para leer el archivo en el método `Main`:</span><span class="sxs-lookup"><span data-stu-id="3987e-176">Now, let’s fill in the code to read the file in the `Main` method:</span></span>

```csharp
var lines = ReadFrom("sampleQuotes.txt");
foreach (var line in lines)
{
    Console.WriteLine(line);
}
```

<span data-ttu-id="3987e-177">Ejecute el programa (mediante `dotnet run`) y podrá ver cada línea impresa en la consola.</span><span class="sxs-lookup"><span data-stu-id="3987e-177">Run the program (using `dotnet run`) and you can see every line printed out to the console.</span></span>

## <a name="adding-delays-and-formatting-output"></a><span data-ttu-id="3987e-178">Adición de retrasos y formato de salida</span><span class="sxs-lookup"><span data-stu-id="3987e-178">Adding Delays and Formatting output</span></span>

<span data-ttu-id="3987e-179">Lo que tiene se va a mostrar lejos, demasiado rápido para leerlo en voz alta.</span><span class="sxs-lookup"><span data-stu-id="3987e-179">What you have is being displayed far too fast to read aloud.</span></span> <span data-ttu-id="3987e-180">Ahora debe agregar los retrasos en la salida.</span><span class="sxs-lookup"><span data-stu-id="3987e-180">Now you need to add the delays in the output.</span></span> <span data-ttu-id="3987e-181">Cuando empiece, estará creando parte del código principal que permite el procesamiento asincrónico.</span><span class="sxs-lookup"><span data-stu-id="3987e-181">As you start, you’ll be building some of the core code that enables asynchronous processing.</span></span> <span data-ttu-id="3987e-182">Sin embargo, a estos primeros pasos le seguirán algunos antipatrones.</span><span class="sxs-lookup"><span data-stu-id="3987e-182">However, these first steps will follow a few anti-patterns.</span></span> <span data-ttu-id="3987e-183">Los antipatrones se señalan en los comentarios cuando se agrega el código y el código se actualizará en los pasos posteriores.</span><span class="sxs-lookup"><span data-stu-id="3987e-183">The anti-patterns are pointed out in comments as you add the code, and the code will be updated in later steps.</span></span>

<span data-ttu-id="3987e-184">Hay dos pasos hasta esta sección.</span><span class="sxs-lookup"><span data-stu-id="3987e-184">There are two steps to this section.</span></span> <span data-ttu-id="3987e-185">Primero, actualizará el método Iterator para devolver palabras sueltas en lugar de líneas enteras.</span><span class="sxs-lookup"><span data-stu-id="3987e-185">First, you’ll update the iterator method to return single words instead of entire lines.</span></span> <span data-ttu-id="3987e-186">Para ello, son necesarias estas modificaciones.</span><span class="sxs-lookup"><span data-stu-id="3987e-186">That’s done with these modifications.</span></span> <span data-ttu-id="3987e-187">Reemplace la instrucción `yield return line;` por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="3987e-187">Replace the `yield return line;` statement with the following code:</span></span>

```csharp
var words = line.Split(' ');
foreach (var word in words)
{
    yield return word + " ";
}
yield return Environment.NewLine;
```

<span data-ttu-id="3987e-188">A continuación, debe modificar el modo en que se consumen las líneas del archivo y agregar un retraso después de escribir cada palabra.</span><span class="sxs-lookup"><span data-stu-id="3987e-188">Next, you need to modify how you consume the lines of the file, and add a delay after writing each word.</span></span> <span data-ttu-id="3987e-189">Reemplace la instrucción `Console.WriteLine(line)` del método `Main` por el bloqueo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3987e-189">Replace the `Console.WriteLine(line)` statement in the `Main` method with the following block:</span></span>

```csharp
Console.Write(line);
if (!string.IsNullOrWhiteSpace(line))
{
    var pause = Task.Delay(200);
    // Synchronously waiting on a task is an
    // anti-pattern. This will get fixed in later
    // steps.
    pause.Wait();
}
```

<span data-ttu-id="3987e-190">La clase <xref:System.Threading.Tasks.Task> está en el espacio de nombres <xref:System.Threading.Tasks>, así que debe agregar esa instrucción `using` en la parte superior del archivo:</span><span class="sxs-lookup"><span data-stu-id="3987e-190">The <xref:System.Threading.Tasks.Task> class is in the <xref:System.Threading.Tasks> namespace, so you need to add that `using` statement at the top of file:</span></span>

```csharp
using System.Threading.Tasks;
```

<span data-ttu-id="3987e-191">Ejecute el ejemplo y compruebe la salida.</span><span class="sxs-lookup"><span data-stu-id="3987e-191">Run the sample, and check the output.</span></span> <span data-ttu-id="3987e-192">Ahora, se imprime cada palabra suelta, seguido de un retraso de 200 ms.</span><span class="sxs-lookup"><span data-stu-id="3987e-192">Now, each single word is printed, followed by a 200 ms delay.</span></span> <span data-ttu-id="3987e-193">Sin embargo, la salida mostrada indica algunos problemas porque el archivo de texto de origen tiene varias líneas con más de 80 caracteres sin un salto de línea.</span><span class="sxs-lookup"><span data-stu-id="3987e-193">However, the displayed output shows some issues because the source text file has several lines that have more than 80 characters without a line break.</span></span> <span data-ttu-id="3987e-194">Este texto puede ser difícil de leer al desplazarse por él.</span><span class="sxs-lookup"><span data-stu-id="3987e-194">That can be hard to read while it's scrolling by.</span></span> <span data-ttu-id="3987e-195">Esto es fácil de corregir.</span><span class="sxs-lookup"><span data-stu-id="3987e-195">That’s easy to fix.</span></span> <span data-ttu-id="3987e-196">Simplemente realizará el seguimiento de la longitud de cada línea y generará una nueva línea cada vez que la longitud de la línea alcance un determinado umbral.</span><span class="sxs-lookup"><span data-stu-id="3987e-196">You’ll just keep track of the length of each line, and generate a new line whenever the line length reaches a certain threshold.</span></span> <span data-ttu-id="3987e-197">Declare una variable local después de la declaración de `words` en el método `ReadFrom` que contiene la longitud de línea:</span><span class="sxs-lookup"><span data-stu-id="3987e-197">Declare a local variable after the declaration of `words` in the `ReadFrom` method that holds the line length:</span></span>

```csharp
var lineLength = 0;
```

<span data-ttu-id="3987e-198">A continuación, agregue el código siguiente después de la instrucción `yield return word + " ";` (antes de la llave de cierre):</span><span class="sxs-lookup"><span data-stu-id="3987e-198">Then, add the following code after the `yield return word + " ";` statement (before the closing brace):</span></span>

```csharp
lineLength += word.Length + 1;
if (lineLength > 70)
{
    yield return Environment.NewLine;
    lineLength = 0;
}
```

<span data-ttu-id="3987e-199">Ejecute el ejemplo y podrá leer en alto a su ritmo preconfigurado.</span><span class="sxs-lookup"><span data-stu-id="3987e-199">Run the sample, and you’ll be able to read aloud at its pre-configured pace.</span></span>

## <a name="async-tasks"></a><span data-ttu-id="3987e-200">Tareas asincrónicas</span><span class="sxs-lookup"><span data-stu-id="3987e-200">Async Tasks</span></span>

<span data-ttu-id="3987e-201">En este paso final, agregará el código para escribir la salida de manera asincrónica en una tarea, mientras se ejecuta también otra tarea para leer la entrada del usuario si quiere aumentar o reducir la velocidad de la pantalla de texto.</span><span class="sxs-lookup"><span data-stu-id="3987e-201">In this final step, you’ll add the code to write the output asynchronously in one task, while also running another task to read input from the user if they want to speed up or slow down the text display.</span></span> <span data-ttu-id="3987e-202">Incluye unos cuantos pasos y, al final, tendrá todas las actualizaciones que necesita.</span><span class="sxs-lookup"><span data-stu-id="3987e-202">This has a few steps in it and by the end, you’ll have all the updates that you need.</span></span>
<span data-ttu-id="3987e-203">El primer paso es crear un método de devolución <xref:System.Threading.Tasks.Task> asincrónico que represente el código que ha creado hasta el momento para leer y visualizar el archivo.</span><span class="sxs-lookup"><span data-stu-id="3987e-203">The first step is to create an asynchronous <xref:System.Threading.Tasks.Task> returning method that represents the code you’ve created so far to read and display the file.</span></span>

<span data-ttu-id="3987e-204">Agregue este método a su clase `Program` (se toma del cuerpo del método `Main`):</span><span class="sxs-lookup"><span data-stu-id="3987e-204">Add this method to your `Program` class (it’s taken from the body of your `Main` method):</span></span>

```csharp
private static async Task ShowTeleprompter()
{
    var words = ReadFrom("sampleQuotes.txt");
    foreach (var word in words)
    {
        Console.Write(word);
        if (!string.IsNullOrWhiteSpace(word))
        {
            await Task.Delay(200);
        }
    }
}
```

<span data-ttu-id="3987e-205">Advertirá dos cambios.</span><span class="sxs-lookup"><span data-stu-id="3987e-205">You’ll notice two changes.</span></span> <span data-ttu-id="3987e-206">Primero, en el cuerpo del método, en lugar de llamar a <xref:System.Threading.Tasks.Task.Wait> para esperar a que finalice una tarea de manera sincrónica, esta versión usa la palabra clave `await`.</span><span class="sxs-lookup"><span data-stu-id="3987e-206">First, in the body of the method, instead of calling <xref:System.Threading.Tasks.Task.Wait> to synchronously wait for a task to finish, this version uses the `await` keyword.</span></span> <span data-ttu-id="3987e-207">Para ello, debe agregar el modificador `async` a la signatura del método.</span><span class="sxs-lookup"><span data-stu-id="3987e-207">In order to do that, you need to add the `async` modifier to the method signature.</span></span> <span data-ttu-id="3987e-208">Este método devuelve un objeto `Task`.</span><span class="sxs-lookup"><span data-stu-id="3987e-208">This method returns a `Task`.</span></span> <span data-ttu-id="3987e-209">Observe que no hay ninguna instrucción Return que devuelva un objeto `Task`.</span><span class="sxs-lookup"><span data-stu-id="3987e-209">Notice that there are no return statements that return a `Task` object.</span></span> <span data-ttu-id="3987e-210">En su lugar, ese objeto `Task` se crea mediante el código que genera el compilador cuando usa el operador `await`.</span><span class="sxs-lookup"><span data-stu-id="3987e-210">Instead, that `Task` object is created by code the compiler generates when you use the `await` operator.</span></span> <span data-ttu-id="3987e-211">Puede imaginar que este método devuelve cuando alcanza un valor de `await`.</span><span class="sxs-lookup"><span data-stu-id="3987e-211">You can imagine that this method returns when it reaches an `await`.</span></span> <span data-ttu-id="3987e-212">El valor devuelto de `Task` indica que el trabajo no ha finalizado.</span><span class="sxs-lookup"><span data-stu-id="3987e-212">The returned `Task` indicates that the work has not completed.</span></span>
<span data-ttu-id="3987e-213">El método se reanuda cuando se completa la tarea en espera.</span><span class="sxs-lookup"><span data-stu-id="3987e-213">The method resumes when the awaited task completes.</span></span> <span data-ttu-id="3987e-214">Cuando se ha ejecutado hasta su finalización, el valor de `Task` devuelto indica que se ha completado.</span><span class="sxs-lookup"><span data-stu-id="3987e-214">When it has executed to completion, the returned `Task` indicates that it is complete.</span></span>
<span data-ttu-id="3987e-215">El código de llamada puede supervisar ese valor de `Task` devuelto para determinar cuándo se ha completado.</span><span class="sxs-lookup"><span data-stu-id="3987e-215">Calling code can monitor that returned `Task` to determine when it has completed.</span></span>

<span data-ttu-id="3987e-216">Puede llamar a este nuevo método en su método `Main`:</span><span class="sxs-lookup"><span data-stu-id="3987e-216">You can call this new method in your `Main` method:</span></span>

```csharp
ShowTeleprompter().Wait();
```

<span data-ttu-id="3987e-217">Aquí, en `Main`, el código espera de manera sincrónica.</span><span class="sxs-lookup"><span data-stu-id="3987e-217">Here, in `Main`, the code does synchronously wait.</span></span> <span data-ttu-id="3987e-218">Siempre que sea posible, debe usar el operador `await` en lugar de esperar sincrónicamente.</span><span class="sxs-lookup"><span data-stu-id="3987e-218">You should use the `await` operator instead of synchronously waiting whenever possible.</span></span> <span data-ttu-id="3987e-219">Sin embargo, en el método `Main` de una aplicación de consola, no puede usar el operador `await`.</span><span class="sxs-lookup"><span data-stu-id="3987e-219">But, in a console application’s `Main` method, you cannot use the `await` operator.</span></span> <span data-ttu-id="3987e-220">Si así fuera, la aplicación se cerraría antes de que todas las tareas se hubieran completado.</span><span class="sxs-lookup"><span data-stu-id="3987e-220">That would result in the application exiting before all tasks have completed.</span></span>

> [!NOTE]
> <span data-ttu-id="3987e-221">Si usa C# 7.1 o una versión posterior, puede crear aplicaciones de consola con el [método `async` `Main`](../whats-new/csharp-7-1.md#async-main).</span><span class="sxs-lookup"><span data-stu-id="3987e-221">If you use C# 7.1 or later, you can create console applications with [`async` `Main` method](../whats-new/csharp-7-1.md#async-main).</span></span>

<span data-ttu-id="3987e-222">A continuación, debe escribir el segundo método asincrónico para leer de la consola y controlar las teclas "<" y ">".</span><span class="sxs-lookup"><span data-stu-id="3987e-222">Next, you need to write the second asynchronous method to read from the Console and watch for the ‘<’ and ‘>’ keys.</span></span> <span data-ttu-id="3987e-223">Este es el método que agrega para esa tarea:</span><span class="sxs-lookup"><span data-stu-id="3987e-223">Here’s the method you add for that task:</span></span>

```csharp
private static async Task GetInput()
{
    var delay = 200;
    Action work = () =>
    {
        do {
            var key = Console.ReadKey(true);
            if (key.KeyChar == '>')
            {
                delay -= 10;
            }
            else if (key.KeyChar == '<')
            {
                delay += 10;
            }
        } while (true);
    };
    await Task.Run(work);
}
```

<span data-ttu-id="3987e-224">Se crea una expresión lambda que representa un delegado de <xref:System.Action> que lee una clave de la consola y modifica una variable local que representa el retraso cuando el usuario presiona las teclas "<" o ">".</span><span class="sxs-lookup"><span data-stu-id="3987e-224">This creates a lambda expression to represent an <xref:System.Action> delegate that reads a key from the Console and modifies a local variable representing the delay when the user presses the ‘<’ or ‘>’ keys.</span></span> <span data-ttu-id="3987e-225">Este método usa <xref:System.Console.ReadKey> para bloquear y esperar a que el usuario presione una tecla.</span><span class="sxs-lookup"><span data-stu-id="3987e-225">This method uses <xref:System.Console.ReadKey> to block and wait for the user to press a key.</span></span>

<span data-ttu-id="3987e-226">Para finalizar esta característica, debe crear un nuevo método de devolución `async Task` que inicie estas dos tareas (`GetInput` y `ShowTeleprompter`) y también administre los datos compartidos entre ellas.</span><span class="sxs-lookup"><span data-stu-id="3987e-226">To finish this feature, you need to create a new `async Task` returning method that starts both of these tasks (`GetInput` and `ShowTeleprompter`), and also manages the shared data between these two tasks.</span></span>

<span data-ttu-id="3987e-227">Es hora de crear una clase que controle los datos compartidos entre estas dos tareas.</span><span class="sxs-lookup"><span data-stu-id="3987e-227">It’s time to create a class that can handle the shared data between these two tasks.</span></span> <span data-ttu-id="3987e-228">Esta clase contiene dos propiedades públicas: el retraso y una marca `Done` para indicar que el archivo se ha leído completamente:</span><span class="sxs-lookup"><span data-stu-id="3987e-228">This class contains two public properties: the delay, and a flag `Done` to indicate that the file has been completely read:</span></span>

```csharp
namespace TeleprompterConsole
{
    internal class TelePrompterConfig
    {
        private object lockHandle = new object();
        public int DelayInMilliseconds { get; private set; } = 200;

        public void UpdateDelay(int increment) // negative to speed up
        {
            var newDelay = Min(DelayInMilliseconds + increment, 1000);
            newDelay = Max(newDelay, 20);
            lock (lockHandle)
            {
                DelayInMilliseconds = newDelay;
            }
        }

        public bool Done { get; private set; }

        public void SetDone()
        {
            Done = true;
        }
    }
}
```

<span data-ttu-id="3987e-229">Coloque esa clase en un archivo nuevo e inclúyala en el espacio de nombres `TeleprompterConsole`, como se ha mostrado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="3987e-229">Put that class in a new file, and enclose that class in the `TeleprompterConsole` namespace as shown above.</span></span> <span data-ttu-id="3987e-230">También deberá agregar una instrucción `using static` para que pueda hacer referencia a los métodos `Min` y `Max` sin la clase incluida o los nombres de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="3987e-230">You’ll also need to add a `using static` statement so that you can reference the `Min` and `Max` methods without the enclosing class or namespace names.</span></span> <span data-ttu-id="3987e-231">Una instrucción [`using static`](../language-reference/keywords/using-static.md) importa los métodos de una clase,</span><span class="sxs-lookup"><span data-stu-id="3987e-231">A [`using static`](../language-reference/keywords/using-static.md) statement imports the methods from one class.</span></span> <span data-ttu-id="3987e-232">mientras que las instrucciones `using` usadas hasta el momento han importado todas las clases de un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="3987e-232">This is in contrast with the `using` statements used up to this point that have imported all classes from a namespace.</span></span>

```csharp
using static System.Math;
```

<span data-ttu-id="3987e-233">La otra característica del lenguaje que es nueva es la instrucción [`lock`](../language-reference/keywords/lock-statement.md).</span><span class="sxs-lookup"><span data-stu-id="3987e-233">The other language feature that’s new is the [`lock`](../language-reference/keywords/lock-statement.md) statement.</span></span> <span data-ttu-id="3987e-234">Esta instrucción garantiza que solo un subproceso pueda estar en ese código en un momento dado.</span><span class="sxs-lookup"><span data-stu-id="3987e-234">This statement ensures that only a single thread can be in that code at any given time.</span></span> <span data-ttu-id="3987e-235">Si un subproceso está en la sección bloqueada, otros subprocesos deben esperar a que el primer subproceso salga de esa sección.</span><span class="sxs-lookup"><span data-stu-id="3987e-235">If one thread is in the locked section, other threads must wait for the first thread to exit that section.</span></span> <span data-ttu-id="3987e-236">La instrucción `lock` usa un objeto que protege la sección de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="3987e-236">The `lock` statement uses an object that guards the lock section.</span></span> <span data-ttu-id="3987e-237">Esta clase sigue un giro estándar para bloquear un objeto privado en la clase.</span><span class="sxs-lookup"><span data-stu-id="3987e-237">This class follows a standard idiom to lock a private object in the class.</span></span>

<span data-ttu-id="3987e-238">A continuación, debe actualizar los métodos `ShowTeleprompter` y `GetInput` para usar el nuevo objeto `config`.</span><span class="sxs-lookup"><span data-stu-id="3987e-238">Next, you need to update the `ShowTeleprompter` and `GetInput` methods to use the new `config` object.</span></span> <span data-ttu-id="3987e-239">Escriba un método final `async` de devolución de `Task` para iniciar ambas tareas y salir cuando la primera tarea finalice:</span><span class="sxs-lookup"><span data-stu-id="3987e-239">Write one final `Task` returning `async` method to start both tasks and exit when the first task finishes:</span></span>

```csharp
private static async Task RunTeleprompter()
{
    var config = new TelePrompterConfig();
    var displayTask = ShowTeleprompter(config);

    var speedTask = GetInput(config);
    await Task.WhenAny(displayTask, speedTask);
}
```

<span data-ttu-id="3987e-240">El método nuevo aquí es la llamada a <xref:System.Threading.Tasks.Task.WhenAny(System.Threading.Tasks.Task[])>.</span><span class="sxs-lookup"><span data-stu-id="3987e-240">The one new method here is the <xref:System.Threading.Tasks.Task.WhenAny(System.Threading.Tasks.Task[])> call.</span></span> <span data-ttu-id="3987e-241">Dicha llamada crea un valor de `Task` que finaliza en cuanto alguna de las tareas de su lista de argumentos se completa.</span><span class="sxs-lookup"><span data-stu-id="3987e-241">That creates a `Task` that finishes as soon as any of the tasks in its argument list completes.</span></span>

<span data-ttu-id="3987e-242">A continuación, debe actualizar los métodos `ShowTeleprompter` y `GetInput` para usar el objeto `config` para el retraso:</span><span class="sxs-lookup"><span data-stu-id="3987e-242">Next, you need to update both the `ShowTeleprompter` and `GetInput` methods to use the `config` object for the delay:</span></span>

```csharp
private static async Task ShowTeleprompter(TelePrompterConfig config)
{
    var words = ReadFrom("sampleQuotes.txt");
    foreach (var line in words)
    {
        Console.Write(line);
        if (!string.IsNullOrWhiteSpace(line))
        {
            await Task.Delay(config.DelayInMilliseconds);
        }
    }
    config.SetDone();
}

private static async Task GetInput(TelePrompterConfig config)
{
    Action work = () =>
    {
        do {
            var key = Console.ReadKey(true);
            if (key.KeyChar == '>')
                config.UpdateDelay(-10);
            else if (key.KeyChar == '<')
                config.UpdateDelay(10);
        } while (!config.Done);
    };
    await Task.Run(work);
}
```

<span data-ttu-id="3987e-243">Esta nueva versión de `ShowTeleprompter` llama a un nuevo método de la clase `TeleprompterConfig`.</span><span class="sxs-lookup"><span data-stu-id="3987e-243">This new version of `ShowTeleprompter` calls a new method in the `TeleprompterConfig` class.</span></span> <span data-ttu-id="3987e-244">Ahora, debe actualizar `Main` para llamar a `RunTeleprompter` en lugar de a `ShowTeleprompter`:</span><span class="sxs-lookup"><span data-stu-id="3987e-244">Now, you need to update `Main` to call `RunTeleprompter` instead of `ShowTeleprompter`:</span></span>

```csharp
RunTeleprompter().Wait();
```

## <a name="conclusion"></a><span data-ttu-id="3987e-245">Conclusión</span><span class="sxs-lookup"><span data-stu-id="3987e-245">Conclusion</span></span>

<span data-ttu-id="3987e-246">En este tutorial se han mostrado varias características en torno al lenguaje C# y las bibliotecas .NET Core, relacionadas con el trabajo en aplicaciones de consola.</span><span class="sxs-lookup"><span data-stu-id="3987e-246">This tutorial showed you a number of the features around the C# language and the .NET Core libraries related to working in Console applications.</span></span>
<span data-ttu-id="3987e-247">Puede partir de este conocimiento para explorar más sobre el lenguaje y las clases aquí presentadas.</span><span class="sxs-lookup"><span data-stu-id="3987e-247">You can build on this knowledge to explore more about the language, and the classes introduced here.</span></span> <span data-ttu-id="3987e-248">Ha visto los conceptos básicos de E/S de archivo y consola, el uso con bloqueo y sin bloqueo de la programación asincrónica basada en tareas, un paseo por el lenguaje C# y cómo se organizan los programas en C#. También ha conocido la interfaz de la línea de comandos y las herramientas de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3987e-248">You’ve seen the basics of File and Console I/O, blocking and non-blocking use of the Task-based asynchronous programming, a tour of the C# language and how C# programs are organized and the .NET Core Command Line Interface and tools.</span></span>

<span data-ttu-id="3987e-249">Para obtener más información sobre la E/S de archivo, consulte el tema [E/S de archivos y secuencias](../../standard/io/index.md).</span><span class="sxs-lookup"><span data-stu-id="3987e-249">For more information about File I/O, see the [File and Stream I/O](../../standard/io/index.md) topic.</span></span> <span data-ttu-id="3987e-250">Para obtener más información sobre el modelo de programación asincrónica que se ha usado en este tutorial, vea los temas [Programación asincrónica basada en tareas](../..//standard/parallel-programming/task-based-asynchronous-programming.md) y [Programación asincrónica](../async.md).</span><span class="sxs-lookup"><span data-stu-id="3987e-250">For more information about asynchronous programming model used in this tutorial, see the [Task-based Asynchronous Programming](../..//standard/parallel-programming/task-based-asynchronous-programming.md) topic and the [Asynchronous programming](../async.md) topic.</span></span>
