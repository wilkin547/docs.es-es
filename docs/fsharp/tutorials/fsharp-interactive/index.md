---
title: Referencia sobre F# interactivo (dotnet)
description: Obtenga información sobre cómo se utiliza F# interactivo (dotnet fsi) para ejecutar código de F# de manera interactiva en la consola o para ejecutar scripts de F#.
ms.date: 08/20/2020
f1_keywords:
- VS.ToolsOptionsPages.F#_Tools.F#_Interactive
ms.openlocfilehash: ae8d68140ddec8e18ee23e9a43b548907e1ab5c4
ms.sourcegitcommit: fe8877e564deb68d77fa4b79f55584ac8d7e8997
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2020
ms.locfileid: "90720327"
---
# <a name="interactive-programming-with-f"></a><span data-ttu-id="55fac-103">Programación interactiva con F\#</span><span class="sxs-lookup"><span data-stu-id="55fac-103">Interactive programming with F\#</span></span>

<span data-ttu-id="55fac-104">F# interactivo (dotnet fsi) se utiliza para ejecutar código de F# de manera interactiva en la consola o para ejecutar scripts de F#.</span><span class="sxs-lookup"><span data-stu-id="55fac-104">F# Interactive (dotnet fsi) is used to run F# code interactively at the console, or to execute F# scripts.</span></span> <span data-ttu-id="55fac-105">En otras palabras, F# Interactive ejecuta un bucle REPL (del inglés Read, Evaluate, Print Loop - bucle Leer, Evaluar, Imprimir) para el lenguaje F#.</span><span class="sxs-lookup"><span data-stu-id="55fac-105">In other words, F# interactive executes a REPL (Read, Evaluate, Print Loop) for the F# language.</span></span>

<span data-ttu-id="55fac-106">Para ejecutar F# interactivo desde la consola, ejecute `dotnet fsi`.</span><span class="sxs-lookup"><span data-stu-id="55fac-106">To run F# Interactive from the console, run `dotnet fsi`.</span></span> <span data-ttu-id="55fac-107">Encontrará `dotnet fsi` en cualquier SDK de .NET.</span><span class="sxs-lookup"><span data-stu-id="55fac-107">You will find `dotnet fsi` in any .NET SDK.</span></span>

<span data-ttu-id="55fac-108">Para obtener más información sobre las opciones de línea de comandos disponibles, vea [Opciones de F# Interactive](../../language-reference/fsharp-interactive-options.md).</span><span class="sxs-lookup"><span data-stu-id="55fac-108">For information about command line options available, see [F# Interactive Options](../../language-reference/fsharp-interactive-options.md).</span></span>

<span data-ttu-id="55fac-109">Para ejecutar F# Interactive a través de Visual Studio, puede hacer clic en el botón **F# Interactive** de la barra de herramientas o presionar las teclas **Ctrl+Alt+F**.</span><span class="sxs-lookup"><span data-stu-id="55fac-109">To run F# Interactive through Visual Studio, you can click the appropriate toolbar button labeled **F# Interactive**, or use the keys **Ctrl+Alt+F**.</span></span> <span data-ttu-id="55fac-110">De este modo, se abrirá la ventana interactiva, que es una ventana de herramientas en la que se ejecuta una sesión de F# Interactive.</span><span class="sxs-lookup"><span data-stu-id="55fac-110">Doing this will open the interactive window, a tool window running an F# Interactive session.</span></span> <span data-ttu-id="55fac-111">También puede seleccionar el código que quiere ejecutar en la ventana interactiva y presionar la combinación de teclas **Alt+ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="55fac-111">You can also select some code that you want to run in the interactive window and hit the key combination **Alt+Enter**.</span></span> <span data-ttu-id="55fac-112">F# Interactive se inicia en la ventana de herramientas con la etiqueta **F# Interactive**.</span><span class="sxs-lookup"><span data-stu-id="55fac-112">F# Interactive starts in a tool window labeled **F# Interactive**.</span></span> <span data-ttu-id="55fac-113">Cuando use esta combinación de teclas, asegúrese de que la ventana del editor tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="55fac-113">When you use this key combination, make sure that the editor window has the focus.</span></span>

<span data-ttu-id="55fac-114">Tanto si usa la consola como si usa Visual Studio, aparece un símbolo del sistema y el intérprete espera una entrada por parte del usuario.</span><span class="sxs-lookup"><span data-stu-id="55fac-114">Whether you are using the console or Visual Studio, a command prompt appears and the interpreter awaits your input.</span></span> <span data-ttu-id="55fac-115">Puede escribir código tal y como lo haría en un archivo de código fuente.</span><span class="sxs-lookup"><span data-stu-id="55fac-115">You can enter code just as you would in a code file.</span></span> <span data-ttu-id="55fac-116">Para compilar y ejecutar el código, escriba dos signos de punto y coma (**;;**) para finalizar una o varias líneas de entrada.</span><span class="sxs-lookup"><span data-stu-id="55fac-116">To compile and execute the code, enter two semicolons (**;;**) to terminate a line or several lines of input.</span></span>

<span data-ttu-id="55fac-117">F# Interactive intenta compilar el código y, si lo logra, lo ejecuta e imprime en pantalla la signatura de los tipos y valores que compiló.</span><span class="sxs-lookup"><span data-stu-id="55fac-117">F# Interactive attempts to compile the code and, if successful, it executes the code and prints the signature of the types and values that it compiled.</span></span> <span data-ttu-id="55fac-118">Si se producen errores, el intérprete imprime en pantalla los mensajes de error.</span><span class="sxs-lookup"><span data-stu-id="55fac-118">If errors occur, the interpreter prints the error messages.</span></span>

<span data-ttu-id="55fac-119">El código escrito en una misma sesión tiene acceso a cualquier construcción escrita anteriormente, de modo que es posible crear programas.</span><span class="sxs-lookup"><span data-stu-id="55fac-119">Code entered in the same session has access to any constructs entered previously, so you can build up programs.</span></span> <span data-ttu-id="55fac-120">Un búfer extenso de la ventana de herramientas permite copiar el código en un archivo si es necesario.</span><span class="sxs-lookup"><span data-stu-id="55fac-120">An extensive buffer in the tool window allows you to copy the code into a file if needed.</span></span>

<span data-ttu-id="55fac-121">Cuando F# Interactive se ejecuta en Visual Studio, lo hace de manera independiente del proyecto, de modo que, por ejemplo, no se pueden usar en F# Interactive las construcciones definidas en el proyecto a menos que se copie el código de dichas funciones en la ventana interactiva.</span><span class="sxs-lookup"><span data-stu-id="55fac-121">When run in Visual Studio, F# Interactive runs independently of your project, so, for example, you cannot use constructs defined in your project in F# Interactive unless you copy the code for the function into the interactive window.</span></span>

<span data-ttu-id="55fac-122">Si tiene un proyecto abierto que hace referencia a algunas bibliotecas, puede hacer referencia a ellas en F# Interactive a través del **Explorador de soluciones**.</span><span class="sxs-lookup"><span data-stu-id="55fac-122">If you have a project open that references some libraries, you can reference these in F# Interactive through **Solution Explorer**.</span></span> <span data-ttu-id="55fac-123">Para hacer referencia a una biblioteca en F# Interactive, expanda el nodo **Referencias**, abra el menú contextual de la biblioteca y seleccione **Enviar a F# Interactive**.</span><span class="sxs-lookup"><span data-stu-id="55fac-123">To reference a library in F# Interactive, expand the **References** node, open the shortcut menu for the library, and choose **Send to F# Interactive**.</span></span>

<span data-ttu-id="55fac-124">Puede controlar los argumentos (opciones) de la línea de comandos de F# Interactive ajustando la configuración.</span><span class="sxs-lookup"><span data-stu-id="55fac-124">You can control the F# Interactive command line arguments (options) by adjusting the settings.</span></span> <span data-ttu-id="55fac-125">En el menú **Herramientas**, seleccione **Opciones...** y, después, expanda **Herramientas de F#**.</span><span class="sxs-lookup"><span data-stu-id="55fac-125">On the **Tools** menu, select **Options...**, and then expand **F# Tools**.</span></span> <span data-ttu-id="55fac-126">Las dos configuraciones que puede cambiar son las opciones de F# Interactive y la opción **F# Interactive de 64 bits**, que solo es relevante si ejecuta F# Interactive en un equipo de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="55fac-126">The two settings that you can change are the F# Interactive options and the **64-bit F# Interactive** setting, which is relevant only if you are running F# Interactive on a 64-bit machine.</span></span> <span data-ttu-id="55fac-127">Este valor determina si desea ejecutar la versión de 64 bits dedicada de fsi.exe o de fsianycpu.exe, que usa la arquitectura del equipo para determinar si debe ejecutarse como un proceso de 32 o de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="55fac-127">This setting determines whether you want to run the dedicated 64-bit version of fsi.exe or fsianycpu.exe, which uses the machine architecture to determine whether to run as a 32-bit or 64-bit process.</span></span>

## <a name="scripting-with-f"></a><span data-ttu-id="55fac-128">Scripting con F\#</span><span class="sxs-lookup"><span data-stu-id="55fac-128">Scripting with F\#</span></span>

<span data-ttu-id="55fac-129">Los scripts usan la extensión de archivo **.fsx** o **.fsscript**.</span><span class="sxs-lookup"><span data-stu-id="55fac-129">Scripts use the file extension **.fsx** or **.fsscript**.</span></span> <span data-ttu-id="55fac-130">En lugar de compilar el código fuente y después ejecutar el ensamblado compilado, se puede ejecutar simplemente **dotnet fsi** y especificar el nombre de archivo del script de código fuente de F#. F# interactivo lee el código y lo ejecuta en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="55fac-130">Instead of compiling source code and then later running the compiled assembly, you can just run **dotnet fsi** and specify the filename of the script of F# source code, and F# interactive reads the code and executes it in real time.</span></span>

## <a name="differences-between-the-interactive-scripting-and-compiled-environments"></a><span data-ttu-id="55fac-131">Diferencias entre los entornos interactivo, compilado y de scripting</span><span class="sxs-lookup"><span data-stu-id="55fac-131">Differences between the interactive, scripting, and compiled environments</span></span>

<span data-ttu-id="55fac-132">Al compilar código en F# Interactive, tanto si se ejecuta de forma interactiva como si ejecuta un script, se define el símbolo **INTERACTIVE**.</span><span class="sxs-lookup"><span data-stu-id="55fac-132">When you are compiling code in F# Interactive, whether you are running interactively or running a script, the symbol **INTERACTIVE** is defined.</span></span> <span data-ttu-id="55fac-133">Al compilar código en el compilador, se define el símbolo **COMPILED**.</span><span class="sxs-lookup"><span data-stu-id="55fac-133">When you are compiling code in the compiler, the symbol **COMPILED** is defined.</span></span> <span data-ttu-id="55fac-134">Por consiguiente, si el código debe ser diferente en modo interactivo y en modo compilado, se pueden usar las directivas de preprocesador de la compilación condicional para determinar cuál se va a usar.</span><span class="sxs-lookup"><span data-stu-id="55fac-134">Thus, if code needs to be different in compiled and interactive modes, you can use preprocessor directives for conditional compilation to determine which to use.</span></span>

<span data-ttu-id="55fac-135">Cuando se ejecutan scripts en F# Interactive, están disponibles algunas directivas que no están disponibles cuando se ejecuta el compilador.</span><span class="sxs-lookup"><span data-stu-id="55fac-135">Some directives are available when you are executing scripts in F# Interactive that are not available when you are executing the compiler.</span></span> <span data-ttu-id="55fac-136">En la siguiente tabla se resumen las directivas que están disponibles cuando se usa F# Interactive.</span><span class="sxs-lookup"><span data-stu-id="55fac-136">The following table summarizes directives that are available when you are using F# Interactive.</span></span>

|<span data-ttu-id="55fac-137">Directiva</span><span class="sxs-lookup"><span data-stu-id="55fac-137">Directive</span></span>|<span data-ttu-id="55fac-138">Descripción</span><span class="sxs-lookup"><span data-stu-id="55fac-138">Description</span></span>|
|---------|-----------|
|<span data-ttu-id="55fac-139">**#help**</span><span class="sxs-lookup"><span data-stu-id="55fac-139">**#help**</span></span>|<span data-ttu-id="55fac-140">Muestra información sobre las directivas disponibles.</span><span class="sxs-lookup"><span data-stu-id="55fac-140">Displays information about available directives.</span></span>|
|<span data-ttu-id="55fac-141">**#I**</span><span class="sxs-lookup"><span data-stu-id="55fac-141">**#I**</span></span>|<span data-ttu-id="55fac-142">Especifica una ruta de búsqueda de ensamblado entre comillas.</span><span class="sxs-lookup"><span data-stu-id="55fac-142">Specifies an assembly search path in quotation marks.</span></span>|
|<span data-ttu-id="55fac-143">**#load**</span><span class="sxs-lookup"><span data-stu-id="55fac-143">**#load**</span></span>|<span data-ttu-id="55fac-144">Lee un archivo de código fuente, lo compila y lo ejecuta.</span><span class="sxs-lookup"><span data-stu-id="55fac-144">Reads a source file, compiles it, and runs it.</span></span>|
|<span data-ttu-id="55fac-145">**#quit**</span><span class="sxs-lookup"><span data-stu-id="55fac-145">**#quit**</span></span>|<span data-ttu-id="55fac-146">Termina una sesión de F# Interactive.</span><span class="sxs-lookup"><span data-stu-id="55fac-146">Terminates an F# Interactive session.</span></span>|
|<span data-ttu-id="55fac-147">**#r**</span><span class="sxs-lookup"><span data-stu-id="55fac-147">**#r**</span></span>|<span data-ttu-id="55fac-148">Hace referencia a un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="55fac-148">References an assembly.</span></span>|
|<span data-ttu-id="55fac-149">**#time ["on"&#124;"off"]**</span><span class="sxs-lookup"><span data-stu-id="55fac-149">**#time ["on"&#124;"off"]**</span></span>|<span data-ttu-id="55fac-150">Por sí solo, **#time** activa y desactiva la presentación de información sobre el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="55fac-150">By itself, **#time** toggles whether to display performance information.</span></span> <span data-ttu-id="55fac-151">Cuando está habilitado, F# Interactive mide el tiempo real, el tiempo de CPU y la información sobre recolección de elementos no utilizados que se interpreta y ejecuta.</span><span class="sxs-lookup"><span data-stu-id="55fac-151">When it is enabled, F# Interactive measures real time, CPU time, and garbage collection information for each section of code that is interpreted and executed.</span></span>|

<span data-ttu-id="55fac-152">Al especificar los archivos o rutas de acceso en F# Interactive, se espera un literal de cadena.</span><span class="sxs-lookup"><span data-stu-id="55fac-152">When you specify files or paths in F# Interactive, a string literal is expected.</span></span> <span data-ttu-id="55fac-153">Por tanto, los archivos y las rutas de acceso deben estar entre comillas y se aplicarán los caracteres de escape habituales.</span><span class="sxs-lookup"><span data-stu-id="55fac-153">Therefore, files and paths must be in quotation marks, and the usual escape characters apply.</span></span> <span data-ttu-id="55fac-154">Asimismo, puede usar el carácter @ para hacer que F# Interactive interprete una cadena que contenga una ruta de acceso como una cadena textual.</span><span class="sxs-lookup"><span data-stu-id="55fac-154">Also, you can use the @ character to cause F# Interactive to interpret a string that contains a path as a verbatim string.</span></span> <span data-ttu-id="55fac-155">Esto hace que F# Interactive pase por alto cualquier carácter de escape.</span><span class="sxs-lookup"><span data-stu-id="55fac-155">This causes F# Interactive to ignore any escape characters.</span></span>

<span data-ttu-id="55fac-156">Una de las diferencias entre el modo compilado y el modo interactivo es la manera en que se obtiene acceso a los argumentos de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="55fac-156">One of the differences between compiled and interactive mode is the way you access command line arguments.</span></span> <span data-ttu-id="55fac-157">En modo compilado, use **System.Environment.GetCommandLineArgs**.</span><span class="sxs-lookup"><span data-stu-id="55fac-157">In compiled mode, use **System.Environment.GetCommandLineArgs**.</span></span> <span data-ttu-id="55fac-158">En los scripts, use **fsi.CommandLineArgs**.</span><span class="sxs-lookup"><span data-stu-id="55fac-158">In scripts, use **fsi.CommandLineArgs**.</span></span>

<span data-ttu-id="55fac-159">En el código siguiente se muestra cómo crear una función que lea los argumentos de la línea de comandos en un script y cómo hacer referencia a otro ensamblado desde un script.</span><span class="sxs-lookup"><span data-stu-id="55fac-159">The following code illustrates how to create a function that reads the command line arguments in a script and also demonstrates how to reference another assembly from a script.</span></span> <span data-ttu-id="55fac-160">El primer archivo de código, **MyAssembly.fs**, contiene el código del ensamblado al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="55fac-160">The first code file, **MyAssembly.fs**, is the code for the assembly being referenced.</span></span> <span data-ttu-id="55fac-161">Compile este archivo con la línea de comandos: **fsc -a MyAssembly.fs** y, después, ejecute el segundo archivo como un script con la línea de comandos: **fsi --exec file1.fsx** test</span><span class="sxs-lookup"><span data-stu-id="55fac-161">Compile this file with the command line: **fsc -a MyAssembly.fs** and then execute the second file as a script with the command line: **fsi --exec file1.fsx** test</span></span>

```fsharp
// MyAssembly.fs
module MyAssembly
let myFunction x y = x + 2 * y
```

```fsharp
// file1.fsx
#r "MyAssembly.dll"

printfn "Command line arguments: "

for arg in fsi.CommandLineArgs do
    printfn "%s" arg

printfn "%A" (MyAssembly.myFunction 10 40)
```

<span data-ttu-id="55fac-162">La salida es como sigue:</span><span class="sxs-lookup"><span data-stu-id="55fac-162">The output is as follows:</span></span>

```console
Command line arguments:
file1.fsx
test
90
```

## <a name="package-management-in-f-interactive"></a><span data-ttu-id="55fac-163">Administración de paquetes en F# interactivo</span><span class="sxs-lookup"><span data-stu-id="55fac-163">Package Management in F# Interactive</span></span>

[!NOTE] <span data-ttu-id="55fac-164">La administración de paquetes está disponible como una característica en vista previa en las versiones de `dotnet fsi` incluidas en la versión `3.1.300` y posteriores del SDK de .NET, así como en todas las versiones `5.*` del SDK de .NET.</span><span class="sxs-lookup"><span data-stu-id="55fac-164">Package management is available as a preview feature in versions of `dotnet fsi` shipped in the `3.1.300` and greater versions of the .NET SDK, as well as all `5.*` versions of the .NET SDK.</span></span> <span data-ttu-id="55fac-165">Para habilitarla en esta versión preliminar, ejecute `dotnet fsi` con el argumento `--langversion:preview`.</span><span class="sxs-lookup"><span data-stu-id="55fac-165">To enable it in this preview release, run `dotnet fsi` with the `--langversion:preview` argument.</span></span>

<span data-ttu-id="55fac-166">La sintaxis de `#r` para hacer referencia a un archivo DLL en F# interactivo también se puede usar para hacer referencia a un paquete NuGet a través de la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="55fac-166">The `#r` syntax for referencing a DLL in F# Interactive can also be used to reference a nuget package via the following syntax:</span></span>

```fsharp
#r "nuget: <package name>
```

<span data-ttu-id="55fac-167">Por ejemplo, para hacer referencia al paquete `FSharp.Data`, use la referencia `#r` siguiente:</span><span class="sxs-lookup"><span data-stu-id="55fac-167">For example, to reference the `FSharp.Data` package, use the following `#r` reference:</span></span>

```fsharp
#r "nuget: FSharp.Data"
```

<span data-ttu-id="55fac-168">Después de ejecutar esta línea, la última versión del paquete `FSharp.Data` se descargará en la memoria caché de NuGet y se hará referencia a ella en la sesión de F# interactivo actual.</span><span class="sxs-lookup"><span data-stu-id="55fac-168">After executing this line, the latest version of the `FSharp.Data` package will be downloaded to your nuget cache and referenced in the current F# Interactive session.</span></span>

<span data-ttu-id="55fac-169">Además del nombre del paquete, se puede hacer referencia a versiones específicas de un paquete con una sintaxis abreviada:</span><span class="sxs-lookup"><span data-stu-id="55fac-169">In addition to the package name, specific versions of a package can be referenced via a short syntax:</span></span>

```fsharp
#r "nuget: FSharp.Data, 3.3.2"
```

<span data-ttu-id="55fac-170">o de un modo más explícito:</span><span class="sxs-lookup"><span data-stu-id="55fac-170">or in a more explicit fashion:</span></span>

```fsharp
#r "nuget: FSharp.Data, Version=3.3.2"
```

## <a name="related-articles"></a><span data-ttu-id="55fac-171">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="55fac-171">Related articles</span></span>

|<span data-ttu-id="55fac-172">Title</span><span class="sxs-lookup"><span data-stu-id="55fac-172">Title</span></span>|<span data-ttu-id="55fac-173">Descripción</span><span class="sxs-lookup"><span data-stu-id="55fac-173">Description</span></span>|
|-----|-----------|
|[<span data-ttu-id="55fac-174">Opciones de F# Interactive</span><span class="sxs-lookup"><span data-stu-id="55fac-174">F# Interactive Options</span></span>](../../language-reference/fsharp-interactive-options.md)|<span data-ttu-id="55fac-175">Describe la sintaxis y las opciones de línea de comandos de F# interactivo, fsi.exe.</span><span class="sxs-lookup"><span data-stu-id="55fac-175">Describes command-line syntax and options for the F# Interactive, fsi.exe.</span></span>|
