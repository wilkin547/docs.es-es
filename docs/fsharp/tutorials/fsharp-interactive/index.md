---
title: Referencia sobre F# interactivo (dotnet)
description: Obtenga información sobre cómo se utiliza F# interactivo (dotnet fsi) para ejecutar código de F# de manera interactiva en la consola o para ejecutar scripts de F#.
ms.date: 10/31/2020
f1_keywords:
- VS.ToolsOptionsPages.F#_Tools.F#_Interactive
ms.openlocfilehash: 770ac24feababcfc840ae26196ba8b6180d378a0
ms.sourcegitcommit: 74d05613d6c57106f83f82ce8ee71176874ea3f0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2020
ms.locfileid: "93282016"
---
# <a name="interactive-programming-with-f"></a><span data-ttu-id="fa620-103">Programación interactiva con F\#</span><span class="sxs-lookup"><span data-stu-id="fa620-103">Interactive programming with F\#</span></span>

<span data-ttu-id="fa620-104">F# interactivo (dotnet fsi) se utiliza para ejecutar código de F# de manera interactiva en la consola o para ejecutar scripts de F#.</span><span class="sxs-lookup"><span data-stu-id="fa620-104">F# Interactive (dotnet fsi) is used to run F# code interactively at the console, or to execute F# scripts.</span></span> <span data-ttu-id="fa620-105">En otras palabras, F# Interactive ejecuta un bucle REPL (del inglés Read, Evaluate, Print Loop - bucle Leer, Evaluar, Imprimir) para el lenguaje F#.</span><span class="sxs-lookup"><span data-stu-id="fa620-105">In other words, F# interactive executes a REPL (Read, Evaluate, Print Loop) for the F# language.</span></span>

<span data-ttu-id="fa620-106">Para ejecutar F# interactivo desde la consola, ejecute `dotnet fsi`.</span><span class="sxs-lookup"><span data-stu-id="fa620-106">To run F# Interactive from the console, run `dotnet fsi`.</span></span> <span data-ttu-id="fa620-107">Encontrará `dotnet fsi` en cualquier SDK de .NET.</span><span class="sxs-lookup"><span data-stu-id="fa620-107">You will find `dotnet fsi` in any .NET SDK.</span></span>

<span data-ttu-id="fa620-108">Para obtener más información sobre las opciones de línea de comandos disponibles, vea [Opciones de F# Interactive](../../language-reference/fsharp-interactive-options.md).</span><span class="sxs-lookup"><span data-stu-id="fa620-108">For information about command line options available, see [F# Interactive Options](../../language-reference/fsharp-interactive-options.md).</span></span>

## <a name="executing-code-directly-in-f-interactive"></a><span data-ttu-id="fa620-109">Ejecución del código directamente en F# interactivo</span><span class="sxs-lookup"><span data-stu-id="fa620-109">Executing code directly in F# Interactive</span></span>

<span data-ttu-id="fa620-110">Dado que F# interactivo es un REPL (read–eval–print loop), puede ejecutar el código en él de forma interactiva.</span><span class="sxs-lookup"><span data-stu-id="fa620-110">Because F# Interactive is a REPL (read-eval-print loop), you can execute code interactively in it.</span></span> <span data-ttu-id="fa620-111">Este es un ejemplo de una sesión interactiva después de ejecutar `dotnet fsi` desde la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="fa620-111">Here is an example of an interactive session after executing `dotnet fsi` from the command line:</span></span>

```console
Microsoft (R) F# Interactive version 11.0.0.0 for F# 5.0
Copyright (c) Microsoft Corporation. All Rights Reserved.

For help type #help;;

> let square x = x *  x;;
val square : x:int -> int

> square 12;;
val it : int = 144

> printfn "Hello, FSI!"
- ;;
Hello, FSI!
val it : unit = ()
```

<span data-ttu-id="fa620-112">Observará dos cuestiones principales:</span><span class="sxs-lookup"><span data-stu-id="fa620-112">You'll notice two main things:</span></span>

1. <span data-ttu-id="fa620-113">Todo el código debe terminar con un punto y coma doble (`;;`) para que se evalúe.</span><span class="sxs-lookup"><span data-stu-id="fa620-113">All code must be terminated with a double semicolon (`;;`) to be evaluated</span></span>
2. <span data-ttu-id="fa620-114">El código se evalúa y se almacena en un valor `it`.</span><span class="sxs-lookup"><span data-stu-id="fa620-114">Code is evaluated and stored in an `it` value.</span></span> <span data-ttu-id="fa620-115">Puede hacer referencia a `it` de forma interactiva.</span><span class="sxs-lookup"><span data-stu-id="fa620-115">You can reference `it` interactively.</span></span>

<span data-ttu-id="fa620-116">F# interactivo también admite la entrada de varias líneas.</span><span class="sxs-lookup"><span data-stu-id="fa620-116">F# Interactive also supports multi-line input.</span></span> <span data-ttu-id="fa620-117">Solo tiene que terminar el envío con un punto y coma doble (`;;`).</span><span class="sxs-lookup"><span data-stu-id="fa620-117">You just need to terminate your submission with a double semicolon (`;;`).</span></span> <span data-ttu-id="fa620-118">Observe el siguiente fragmento de código que se ha pegado en F# interactivo para su evaluación:</span><span class="sxs-lookup"><span data-stu-id="fa620-118">Consider the following snippet that has been pasted into and evaluated by F# Interactive:</span></span>

```console
> let getOddSquares xs =
-     xs
-     |> List.filter (fun x -> x % 2 <> 0)
-     |> List.map (fun x -> x * x)
-
- printfn "%A" (getOddSquares [1..10]);;
[1; 9; 25; 49; 81]
val getOddSquares : xs:int list -> int list
val it : unit = ()

>
```

<span data-ttu-id="fa620-119">Se conserva el formato del código, y la entrada termina con un punto y coma doble (`;;`).</span><span class="sxs-lookup"><span data-stu-id="fa620-119">The code's formatting is preserved, and there is a double semiclon (`;;`) terminating the input.</span></span> <span data-ttu-id="fa620-120">F# interactivo evaluó el código e imprimió los resultados.</span><span class="sxs-lookup"><span data-stu-id="fa620-120">F# Interactive then evaluated the code and printed the results!</span></span>

## <a name="scripting-with-f"></a><span data-ttu-id="fa620-121">Scripting con F\#</span><span class="sxs-lookup"><span data-stu-id="fa620-121">Scripting with F\#</span></span>

<span data-ttu-id="fa620-122">La evaluación del código de forma interactiva en F# interactivo puede ser una magnífica herramienta de aprendizaje, pero se dará cuenta rápidamente de que no es tan productivo como escribir código en un editor normal.</span><span class="sxs-lookup"><span data-stu-id="fa620-122">Evaluating code interactively in F# Interactive can be a great learning tool, but you'll quickly find that it's not as productive as writing code in a normal editor.</span></span> <span data-ttu-id="fa620-123">Para admitir la edición normal de código, puede escribir scripts de F#.</span><span class="sxs-lookup"><span data-stu-id="fa620-123">To support normal code editing, you can write F# scripts.</span></span>

<span data-ttu-id="fa620-124">Los scripts usan la extensión de archivo **.fsx**.</span><span class="sxs-lookup"><span data-stu-id="fa620-124">Scripts use the file extension **.fsx**.</span></span> <span data-ttu-id="fa620-125">En lugar de compilar el código fuente y después ejecutar el ensamblado compilado, se puede ejecutar simplemente **dotnet fsi** y especificar el nombre de archivo del script de código fuente de F#. F# interactivo lee el código y lo ejecuta en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="fa620-125">Instead of compiling source code and then later running the compiled assembly, you can just run **dotnet fsi** and specify the filename of the script of F# source code, and F# interactive reads the code and executes it in real time.</span></span> <span data-ttu-id="fa620-126">Por ejemplo, vamos a analizar el siguiente script llamado `Script.fsx`:</span><span class="sxs-lookup"><span data-stu-id="fa620-126">For example, consider the following script called `Script.fsx`:</span></span>

```fsharp
let getOddSquares xs =
    xs
    |> List.filter (fun x -> x % 2 <> 0)
    |> List.map (fun x -> x * x)

getOddSquares [1..10]
```

<span data-ttu-id="fa620-127">Cuando este archivo se crea en el equipo, puede ejecutarlo con `dotnet fsi` y ver la salida directamente en la ventana de terminal:</span><span class="sxs-lookup"><span data-stu-id="fa620-127">When this file is created in your machine, you can run it with `dotnet fsi` and see the output directly in your terminal window:</span></span>

```console
dotnet fsi Script.fsx
[1; 9; 25; 49; 81]
```

<span data-ttu-id="fa620-128">El scripting de F# es compatible de forma nativa con [Visual Studio](../../get-started/get-started-visual-studio.md), [Visual Studio Code](../../get-started/get-started-vscode.md) y [Visual Studio para Mac](../../get-started/get-started-visual-studio-for-mac.md).</span><span class="sxs-lookup"><span data-stu-id="fa620-128">F# scripting is natively supported in [Visual Studio](../../get-started/get-started-visual-studio.md), [Visual Studio Code](../../get-started/get-started-vscode.md), and [Visual Studio for Mac](../../get-started/get-started-visual-studio-for-mac.md).</span></span>

## <a name="referencing-packages-in-f-interactive"></a><span data-ttu-id="fa620-129">Referencia a paquetes en F# interactivo</span><span class="sxs-lookup"><span data-stu-id="fa620-129">Referencing packages in F# Interactive</span></span>

> [!NOTE] <span data-ttu-id="fa620-130">La administración de paquetes es una característica de F# 5 que está disponible actualmente con el último SDK de .NET 5.</span><span class="sxs-lookup"><span data-stu-id="fa620-130">Package management is an F# 5 feature and is currently available using the latest .NET 5 SDK.</span></span>

<span data-ttu-id="fa620-131">F# interactivo permite hacer referencia a paquetes de NuGet con la sintaxis `#r "nuget:"` y una versión opcional:</span><span class="sxs-lookup"><span data-stu-id="fa620-131">F# Interactive supports referencing NuGet packages with the `#r "nuget:"` syntax and an optional version:</span></span>

```fsharp
#r "nuget: Newtonsoft.Json"
open Newtonsoft.Json

let data = {| Name = "Don Syme"; Occupation = "F# Creator" |}
JsonConvert.SerializeObject(data)
```

<span data-ttu-id="fa620-132">Si no se especifica ninguna versión, se usa el paquete más alto disponible que no se encuentra en versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="fa620-132">If a version is not specified, the highest available non-preview package is taken.</span></span> <span data-ttu-id="fa620-133">Para hacer referencia a una versión concreta, introduzca la versión con una coma.</span><span class="sxs-lookup"><span data-stu-id="fa620-133">To reference a specific version, introduce the version via a comma.</span></span> <span data-ttu-id="fa620-134">Esto puede ser útil cuando se hace referencia a una versión preliminar de un paquete.</span><span class="sxs-lookup"><span data-stu-id="fa620-134">This can be handy when referencing a preview version of a package.</span></span> <span data-ttu-id="fa620-135">Por ejemplo, considere este script mediante una versión preliminar de [DiffSharp](https://diffsharp.github.io/):</span><span class="sxs-lookup"><span data-stu-id="fa620-135">For example, consider this script using a preview version of [DiffSharp](https://diffsharp.github.io/):</span></span>

```fsharp
#r "nuget: DiffSharp-lite,1.0.0-preview-328097867"
open DiffSharp

// A 1D tensor
let t1 = dsharp.tensor [ 0.0 .. 0.2 .. 1.0 ]

// A 2x2 tensor
let t2 = dsharp.tensor [ [ 0; 1 ]; [ 2; 2 ] ]

// Define a scalar-to-scalar function
let f (x: Tensor) = sin (sqrt x)

printfn "%A" (f (dsharp.tensor 1.2))
```

<span data-ttu-id="fa620-136">Puede especificar tantas referencias de paquete como desee en un script.</span><span class="sxs-lookup"><span data-stu-id="fa620-136">You can specify as many package references as you like in a script.</span></span>

## <a name="referencing-assemblies-on-disk-with-f-interactive"></a><span data-ttu-id="fa620-137">Referencias a ensamblados en el disco con F# interactivo</span><span class="sxs-lookup"><span data-stu-id="fa620-137">Referencing assemblies on disk with F# interactive</span></span>

<span data-ttu-id="fa620-138">Como alternativa, si tiene un ensamblado en el disco y desea hacer referencia a él en un script, puede usar la sintaxis `#r` para especificar un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="fa620-138">Alternatively, if you have an assembly on disk and wish to reference that in a script, you can use the `#r` syntax to specify an assembly.</span></span> <span data-ttu-id="fa620-139">Considere el siguiente código en un proyecto compilado en `MyAssembly.dll`:</span><span class="sxs-lookup"><span data-stu-id="fa620-139">Consider the following code in a project compiled into `MyAssembly.dll`:</span></span>

```fsharp
// MyAssembly.fs
module MyAssembly
let myFunction x y = x + 2 * y
```

<span data-ttu-id="fa620-140">Una vez compilado, puede hacer referencia a él en un archivo denominado `Script.fsx` similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="fa620-140">One compiled, you can reference it in a file called `Script.fsx` like so:</span></span>

```fsharp
#r "path/to/MyAssembly.dll"

printfn "%A" (MyAssembly.myFunction 10 40)
```

<span data-ttu-id="fa620-141">La salida es como sigue:</span><span class="sxs-lookup"><span data-stu-id="fa620-141">The output is as follows:</span></span>

```console
dotnet fsi Script.fsx
90
```

<span data-ttu-id="fa620-142">Puede especificar tantas referencias de ensamblado como desee en un script.</span><span class="sxs-lookup"><span data-stu-id="fa620-142">You can specify as many assembly references as you like in a script.</span></span>

## <a name="loading-other-scripts"></a><span data-ttu-id="fa620-143">Carga de otros scripts</span><span class="sxs-lookup"><span data-stu-id="fa620-143">Loading other scripts</span></span>

<span data-ttu-id="fa620-144">Al crear scripts, a menudo puede ser útil usar diferentes scripts para distintas tareas.</span><span class="sxs-lookup"><span data-stu-id="fa620-144">When scripting, it can often be helpful to use different scripts for different tasks.</span></span> <span data-ttu-id="fa620-145">En ocasiones, es posible que desee volver a usar el código del script en otro.</span><span class="sxs-lookup"><span data-stu-id="fa620-145">Sometimes you may want to re-use code from on script in another.</span></span> <span data-ttu-id="fa620-146">En lugar de copiar y pegar su contenido en el archivo, puede cargarlo y evaluarlo con `#load`.</span><span class="sxs-lookup"><span data-stu-id="fa620-146">Rather than copy-pasting its contents into your file, you can simple load and evaluate it with `#load`.</span></span>

<span data-ttu-id="fa620-147">Observe la sintaxis `Script1.fsx` siguiente:</span><span class="sxs-lookup"><span data-stu-id="fa620-147">Consider the following `Script1.fsx`:</span></span>

```fsharp
let square x = x * x
```

<span data-ttu-id="fa620-148">Y también el uso del archivo `Script2.fsx`:</span><span class="sxs-lookup"><span data-stu-id="fa620-148">And the consuming file, `Script2.fsx`:</span></span>

```fsharp
#load "Script1.fsx"
open Script1

printfn "%d" (square 12)
```

<span data-ttu-id="fa620-149">Tenga en cuenta que la declaración `open Script1` es obligatoria.</span><span class="sxs-lookup"><span data-stu-id="fa620-149">Note that the `open Script1` declaration is required.</span></span> <span data-ttu-id="fa620-150">Esto se debe a que las construcciones de un script de F# se compilan en un módulo de nivel superior cuyo nombre coincide con el del archivo de script en el que está incluido.</span><span class="sxs-lookup"><span data-stu-id="fa620-150">This is because constructs in an F# script are compiled into a top-level module that is the name of the script file it is in.</span></span>

<span data-ttu-id="fa620-151">Puede evaluar `Script2.fsx` de una forma similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="fa620-151">You can evaluate `Script2.fsx` like so:</span></span>

```console
dotnet fsi Script2.fsx
144
```

<span data-ttu-id="fa620-152">Puede especificar tantas directivas `#load` como desee en un script.</span><span class="sxs-lookup"><span data-stu-id="fa620-152">You can specify as many `#load` directives as you like in a script.</span></span>

## <a name="using-the-fsi-object-in-f-code"></a><span data-ttu-id="fa620-153">Uso del objeto `fsi` en el código de F#</span><span class="sxs-lookup"><span data-stu-id="fa620-153">Using the `fsi` object in F# code</span></span>

<span data-ttu-id="fa620-154">Los scripts de F# tienen acceso a un objeto `fsi` personalizado que representa la sesión de F# interactivo.</span><span class="sxs-lookup"><span data-stu-id="fa620-154">F# scripts have access to a custom `fsi` object that represents the F# Interactive session.</span></span> <span data-ttu-id="fa620-155">Permite personalizar aspectos como el formato de la salida.</span><span class="sxs-lookup"><span data-stu-id="fa620-155">It allows you to customize things like output formatting.</span></span> <span data-ttu-id="fa620-156">También define la forma de acceder a los argumentos de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="fa620-156">It is also how you can access command-line arguments.</span></span>

<span data-ttu-id="fa620-157">En el ejemplo siguiente se muestra cómo usar argumentos de la línea de comandos y la forma de acceder a ellos:</span><span class="sxs-lookup"><span data-stu-id="fa620-157">The following example shows how to get and use command-line arguments:</span></span>

```fsharp
let args = fsi.CommandLineArgs

for arg in args do
    printfn "%s" arg
```

<span data-ttu-id="fa620-158">Cuando se evalúa, imprime todos los argumentos.</span><span class="sxs-lookup"><span data-stu-id="fa620-158">When evaluated, it prints all arguments.</span></span> <span data-ttu-id="fa620-159">El primer argumento siempre es el nombre del script que se evalúa:</span><span class="sxs-lookup"><span data-stu-id="fa620-159">The first argument is always the name of the script that is evaluated:</span></span>

```dotnet
dotnet fsi Script1.fsx hello world from fsi
Script1.fsx
hello
world
from
fsi
```

<span data-ttu-id="fa620-160">Tenga en cuenta que también puede utilizar `System.Environment.GetCommandLineArgs()` para acceder a los mismos argumentos.</span><span class="sxs-lookup"><span data-stu-id="fa620-160">Note that you can also use `System.Environment.GetCommandLineArgs()` to access the same arguments.</span></span>

## <a name="f-interactive-directive-reference"></a><span data-ttu-id="fa620-161">Referencia a directivas de F# interactivo</span><span class="sxs-lookup"><span data-stu-id="fa620-161">F# Interactive directive reference</span></span>

<span data-ttu-id="fa620-162">Las directivas `#r` y `#load` abordadas anteriormente solo están disponibles en F# interactivo.</span><span class="sxs-lookup"><span data-stu-id="fa620-162">The `#r` and `#load` directives seen previously are only available in F# Interactive.</span></span> <span data-ttu-id="fa620-163">Hay varias directivas que solo están disponibles en F# interactivo:</span><span class="sxs-lookup"><span data-stu-id="fa620-163">There are several directives only available in F# Interactive:</span></span>

|<span data-ttu-id="fa620-164">Directiva</span><span class="sxs-lookup"><span data-stu-id="fa620-164">Directive</span></span>|<span data-ttu-id="fa620-165">Descripción</span><span class="sxs-lookup"><span data-stu-id="fa620-165">Description</span></span>|
|---------|-----------|
|`#r "nuget:..."`|<span data-ttu-id="fa620-166">Hace referencia a un paquete de NuGet</span><span class="sxs-lookup"><span data-stu-id="fa620-166">References a package from Nuget</span></span>|
|`#r "assembly-name.dll"`|<span data-ttu-id="fa620-167">Hace referencia a un ensamblado del disco</span><span class="sxs-lookup"><span data-stu-id="fa620-167">References an assembly on disk</span></span>|
|`#load "file-name.fsx"`|<span data-ttu-id="fa620-168">Lee un archivo de código fuente, lo compila y lo ejecuta.</span><span class="sxs-lookup"><span data-stu-id="fa620-168">Reads a source file, compiles it, and runs it.</span></span>|
|`#help`|<span data-ttu-id="fa620-169">Muestra información sobre las directivas disponibles.</span><span class="sxs-lookup"><span data-stu-id="fa620-169">Displays information about available directives.</span></span>|
|`#I`|<span data-ttu-id="fa620-170">Especifica una ruta de búsqueda de ensamblado entre comillas.</span><span class="sxs-lookup"><span data-stu-id="fa620-170">Specifies an assembly search path in quotation marks.</span></span>|
|`#quit`|<span data-ttu-id="fa620-171">Termina una sesión de F# Interactive.</span><span class="sxs-lookup"><span data-stu-id="fa620-171">Terminates an F# Interactive session.</span></span>|
|<span data-ttu-id="fa620-172">`#time "on"` o `#time "off"`</span><span class="sxs-lookup"><span data-stu-id="fa620-172">`#time "on"` or `#time "off"`</span></span>|<span data-ttu-id="fa620-173">Por sí solo, `#time` activa y desactiva la presentación de información sobre el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="fa620-173">By itself, `#time` toggles whether to display performance information.</span></span> <span data-ttu-id="fa620-174">Si el valor es `"on"`, F# interactivo mide el tiempo real, el tiempo de CPU y la información sobre recolección de elementos no utilizados que se interpreta y ejecuta.</span><span class="sxs-lookup"><span data-stu-id="fa620-174">When it is `"on"`, F# Interactive measures real time, CPU time, and garbage collection information for each section of code that is interpreted and executed.</span></span>|

<span data-ttu-id="fa620-175">Al especificar los archivos o rutas de acceso en F# Interactive, se espera un literal de cadena.</span><span class="sxs-lookup"><span data-stu-id="fa620-175">When you specify files or paths in F# Interactive, a string literal is expected.</span></span> <span data-ttu-id="fa620-176">Por tanto, los archivos y las rutas de acceso deben estar entre comillas y se aplicarán los caracteres de escape habituales.</span><span class="sxs-lookup"><span data-stu-id="fa620-176">Therefore, files and paths must be in quotation marks, and the usual escape characters apply.</span></span> <span data-ttu-id="fa620-177">Puede usar el carácter `@` para conseguir que F# interactivo interprete una cadena que contenga una ruta de acceso como una cadena textual.</span><span class="sxs-lookup"><span data-stu-id="fa620-177">You can use the `@` character to cause F# Interactive to interpret a string that contains a path as a verbatim string.</span></span> <span data-ttu-id="fa620-178">Esto hace que F# Interactive pase por alto cualquier carácter de escape.</span><span class="sxs-lookup"><span data-stu-id="fa620-178">This causes F# Interactive to ignore any escape characters.</span></span>

## <a name="interactive-and-compiled-preprocessor-directives"></a><span data-ttu-id="fa620-179">Directivas de preprocesador compiladas e interactivas</span><span class="sxs-lookup"><span data-stu-id="fa620-179">Interactive and compiled preprocessor directives</span></span>

<span data-ttu-id="fa620-180">Al compilar código en F# interactivo, tanto si se ejecuta de forma interactiva como si ejecuta un script, se define el símbolo **INTERACTIVE**.</span><span class="sxs-lookup"><span data-stu-id="fa620-180">When you compile code in F# Interactive, whether you are running interactively or running a script, the symbol **INTERACTIVE** is defined.</span></span> <span data-ttu-id="fa620-181">Al compilar código en el compilador, se define el símbolo **COMPILED**.</span><span class="sxs-lookup"><span data-stu-id="fa620-181">When you compile code in the compiler, the symbol **COMPILED** is defined.</span></span> <span data-ttu-id="fa620-182">Por consiguiente, si el código debe ser diferente en modo interactivo y en modo compilado, se pueden usar estas directivas de preprocesador de la compilación condicional para determinar cuál se va a usar.</span><span class="sxs-lookup"><span data-stu-id="fa620-182">Thus, if code needs to be different in compiled and interactive modes, you can use these preprocessor directives for conditional compilation to determine which to use.</span></span> <span data-ttu-id="fa620-183">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="fa620-183">For example:</span></span>

```fsharp
#if INTERACTIVE
// Some code that executes only in FSI
// ...
#endif
```

## <a name="using-f-interactive-in-visual-studio"></a><span data-ttu-id="fa620-184">Uso de F# interactivo en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="fa620-184">Using F# Interactive in Visual Studio</span></span>

<span data-ttu-id="fa620-185">Para ejecutar F# Interactive a través de Visual Studio, puede hacer clic en el botón **F# Interactive** de la barra de herramientas o presionar las teclas **Ctrl+Alt+F**.</span><span class="sxs-lookup"><span data-stu-id="fa620-185">To run F# Interactive through Visual Studio, you can click the appropriate toolbar button labeled **F# Interactive** , or use the keys **Ctrl+Alt+F**.</span></span> <span data-ttu-id="fa620-186">De este modo, se abrirá la ventana interactiva, que es una ventana de herramientas en la que se ejecuta una sesión de F# Interactive.</span><span class="sxs-lookup"><span data-stu-id="fa620-186">Doing this will open the interactive window, a tool window running an F# Interactive session.</span></span> <span data-ttu-id="fa620-187">También puede seleccionar el código que quiere ejecutar en la ventana interactiva y presionar la combinación de teclas **Alt+ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="fa620-187">You can also select some code that you want to run in the interactive window and hit the key combination **Alt+Enter**.</span></span> <span data-ttu-id="fa620-188">F# Interactive se inicia en la ventana de herramientas con la etiqueta **F# Interactive**.</span><span class="sxs-lookup"><span data-stu-id="fa620-188">F# Interactive starts in a tool window labeled **F# Interactive**.</span></span> <span data-ttu-id="fa620-189">Cuando use esta combinación de teclas, asegúrese de que la ventana del editor tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="fa620-189">When you use this key combination, make sure that the editor window has the focus.</span></span>

<span data-ttu-id="fa620-190">Tanto si usa la consola como si usa Visual Studio, aparece un símbolo del sistema y el intérprete espera una entrada por parte del usuario.</span><span class="sxs-lookup"><span data-stu-id="fa620-190">Whether you are using the console or Visual Studio, a command prompt appears and the interpreter awaits your input.</span></span> <span data-ttu-id="fa620-191">Puede escribir código tal y como lo haría en un archivo de código fuente.</span><span class="sxs-lookup"><span data-stu-id="fa620-191">You can enter code just as you would in a code file.</span></span> <span data-ttu-id="fa620-192">Para compilar y ejecutar el código, escriba dos signos de punto y coma ( **;;** ) para finalizar una o varias líneas de entrada.</span><span class="sxs-lookup"><span data-stu-id="fa620-192">To compile and execute the code, enter two semicolons ( **;;** ) to terminate a line or several lines of input.</span></span>

<span data-ttu-id="fa620-193">F# Interactive intenta compilar el código y, si lo logra, lo ejecuta e imprime en pantalla la signatura de los tipos y valores que compiló.</span><span class="sxs-lookup"><span data-stu-id="fa620-193">F# Interactive attempts to compile the code and, if successful, it executes the code and prints the signature of the types and values that it compiled.</span></span> <span data-ttu-id="fa620-194">Si se producen errores, el intérprete imprime en pantalla los mensajes de error.</span><span class="sxs-lookup"><span data-stu-id="fa620-194">If errors occur, the interpreter prints the error messages.</span></span>

<span data-ttu-id="fa620-195">El código escrito en una misma sesión tiene acceso a cualquier construcción escrita anteriormente, de modo que es posible crear programas.</span><span class="sxs-lookup"><span data-stu-id="fa620-195">Code entered in the same session has access to any constructs entered previously, so you can build up programs.</span></span> <span data-ttu-id="fa620-196">Un búfer extenso de la ventana de herramientas permite copiar el código en un archivo si es necesario.</span><span class="sxs-lookup"><span data-stu-id="fa620-196">An extensive buffer in the tool window allows you to copy the code into a file if needed.</span></span>

<span data-ttu-id="fa620-197">Cuando F# Interactive se ejecuta en Visual Studio, lo hace de manera independiente del proyecto, de modo que, por ejemplo, no se pueden usar en F# Interactive las construcciones definidas en el proyecto a menos que se copie el código de dichas funciones en la ventana interactiva.</span><span class="sxs-lookup"><span data-stu-id="fa620-197">When run in Visual Studio, F# Interactive runs independently of your project, so, for example, you cannot use constructs defined in your project in F# Interactive unless you copy the code for the function into the interactive window.</span></span>

<span data-ttu-id="fa620-198">Puede controlar los argumentos (opciones) de la línea de comandos de F# Interactive ajustando la configuración.</span><span class="sxs-lookup"><span data-stu-id="fa620-198">You can control the F# Interactive command line arguments (options) by adjusting the settings.</span></span> <span data-ttu-id="fa620-199">En el menú **Herramientas** , seleccione **Opciones...** y, después, expanda **Herramientas de F#**.</span><span class="sxs-lookup"><span data-stu-id="fa620-199">On the **Tools** menu, select **Options...** , and then expand **F# Tools**.</span></span> <span data-ttu-id="fa620-200">Las dos configuraciones que puede cambiar son las opciones de F# Interactive y la opción **F# Interactive de 64 bits** , que solo es relevante si ejecuta F# Interactive en un equipo de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="fa620-200">The two settings that you can change are the F# Interactive options and the **64-bit F# Interactive** setting, which is relevant only if you are running F# Interactive on a 64-bit machine.</span></span> <span data-ttu-id="fa620-201">Este valor determina si desea ejecutar la versión de 64 bits dedicada de **fsi.exe** o **fsianycpu.exe** , que usa la arquitectura del equipo para determinar si debe ejecutarse como un proceso de 32 o 64 bits.</span><span class="sxs-lookup"><span data-stu-id="fa620-201">This setting determines whether you want to run the dedicated 64-bit version of **fsi.exe** or **fsianycpu.exe** , which uses the machine architecture to determine whether to run as a 32-bit or 64-bit process.</span></span>

## <a name="related-articles"></a><span data-ttu-id="fa620-202">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="fa620-202">Related articles</span></span>

|<span data-ttu-id="fa620-203">Title</span><span class="sxs-lookup"><span data-stu-id="fa620-203">Title</span></span>|<span data-ttu-id="fa620-204">Descripción</span><span class="sxs-lookup"><span data-stu-id="fa620-204">Description</span></span>|
|-----|-----------|
|[<span data-ttu-id="fa620-205">Opciones de F# Interactive</span><span class="sxs-lookup"><span data-stu-id="fa620-205">F# Interactive Options</span></span>](../../language-reference/fsharp-interactive-options.md)|<span data-ttu-id="fa620-206">Describe la sintaxis y las opciones de línea de comandos de F# interactivo, fsi.exe.</span><span class="sxs-lookup"><span data-stu-id="fa620-206">Describes command-line syntax and options for the F# Interactive, fsi.exe.</span></span>|
