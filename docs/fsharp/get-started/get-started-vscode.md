---
title: Introducción a F# en Visual Studio Code
description: 'Obtenga información sobre cómo usar F # con Visual Studio Code y el conjunto de complementos de Ionide.'
ms.date: 12/23/2018
ms.openlocfilehash: 11fb0d443fb7c2b3f270d45bfeaa91102ba28efd
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "96739807"
---
# <a name="get-started-with-f-in-visual-studio-code"></a><span data-ttu-id="9445e-103">Introducción a F# en Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="9445e-103">Get Started with F# in Visual Studio Code</span></span>

<span data-ttu-id="9445e-104">Puede escribir F # en [Visual Studio Code](https://code.visualstudio.com) con el [complemento Ionide](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp) para obtener una excelente experiencia de entorno de desarrollo integrado (IDE) multiplataforma y ligera con IntelliSense y refactorizaciones de código.</span><span class="sxs-lookup"><span data-stu-id="9445e-104">You can write F# in [Visual Studio Code](https://code.visualstudio.com) with the [Ionide plugin](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp) to get a great cross-platform, lightweight Integrated Development Environment (IDE) experience with IntelliSense and code refactorings.</span></span> <span data-ttu-id="9445e-105">Visite [Ionide.IO](https://ionide.io) para obtener más información sobre el complemento.</span><span class="sxs-lookup"><span data-stu-id="9445e-105">Visit [Ionide.io](https://ionide.io) to learn more about the plugin.</span></span>

<span data-ttu-id="9445e-106">Para empezar, asegúrese de que tiene [F # y el complemento Ionide correctamente instalado](install-fsharp.md#install-f-with-visual-studio-code).</span><span class="sxs-lookup"><span data-stu-id="9445e-106">To begin, ensure that you have [F# and the Ionide plugin correctly installed](install-fsharp.md#install-f-with-visual-studio-code).</span></span>

## <a name="create-your-first-project-with-ionide"></a><span data-ttu-id="9445e-107">Cree su primer proyecto con Ionide</span><span class="sxs-lookup"><span data-stu-id="9445e-107">Create your first project with Ionide</span></span>

<span data-ttu-id="9445e-108">Para crear un nuevo proyecto de F #, abra una línea de comandos y cree un nuevo proyecto con el CLI de .NET Core:</span><span class="sxs-lookup"><span data-stu-id="9445e-108">To create a new F# project, open a command line and create a new project with the .NET Core CLI:</span></span>

```dotnetcli
dotnet new console -lang "F#" -o FirstIonideProject
```

<span data-ttu-id="9445e-109">Una vez finalizado, cambie el directorio al proyecto y abra Visual Studio Code:</span><span class="sxs-lookup"><span data-stu-id="9445e-109">Once it completes, change directory to the project and open Visual Studio Code:</span></span>

```console
cd FirstIonideProject
code .
```

<span data-ttu-id="9445e-110">Una vez que el proyecto se cargue en Visual Studio Code, debería ver el panel de Explorador de soluciones de F # en el lado izquierdo de la ventana abierta.</span><span class="sxs-lookup"><span data-stu-id="9445e-110">After the project loads on Visual Studio Code, you should see the F# Solution Explorer pane on the left-hand side of your window open.</span></span> <span data-ttu-id="9445e-111">Esto significa que Ionide ha cargado correctamente el proyecto que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="9445e-111">This means Ionide has successfully loaded the project you just created.</span></span> <span data-ttu-id="9445e-112">Puede escribir código en el editor antes de este momento, pero cuando esto suceda, todo ha terminado de cargarse.</span><span class="sxs-lookup"><span data-stu-id="9445e-112">You can write code in the editor before this point in time, but once this happens, everything has finished loading.</span></span>

## <a name="configure-f-interactive"></a><span data-ttu-id="9445e-113">Configuración de F # Interactive</span><span class="sxs-lookup"><span data-stu-id="9445e-113">Configure F# interactive</span></span>

<span data-ttu-id="9445e-114">En primer lugar, asegúrese de que el scripting de .NET Core es el entorno de scripting predeterminado:</span><span class="sxs-lookup"><span data-stu-id="9445e-114">First, ensure that .NET Core scripting is your default scripting environment:</span></span>

1. <span data-ttu-id="9445e-115">Abra la configuración de Visual Studio Code (configuración de preferencias de **código**  >  **Preferences**  >  **Settings**).</span><span class="sxs-lookup"><span data-stu-id="9445e-115">Open the Visual Studio Code settings (**Code** > **Preferences** > **Settings**).</span></span>
1. <span data-ttu-id="9445e-116">Busque el término **script de F #**.</span><span class="sxs-lookup"><span data-stu-id="9445e-116">Search for the term **F# Script**.</span></span>
1. <span data-ttu-id="9445e-117">Haga clic en la casilla que indica **FSharp: usar scripts de SDK**.</span><span class="sxs-lookup"><span data-stu-id="9445e-117">Click the checkbox that says **FSharp: use SDK scripts**.</span></span>

<span data-ttu-id="9445e-118">Esto es necesario actualmente debido a algunos comportamientos heredados en scripting basado en .NET Framework que no funcionan con el scripting de .NET Core y Ionide está intentando actualmente la compatibilidad con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="9445e-118">This is currently necessary due to some legacy behaviors in .NET Framework-based scripting that don't work with .NET Core scripting, and Ionide is currently striving for that backwards compatibility.</span></span> <span data-ttu-id="9445e-119">En el futuro, el scripting de .NET Core se convertirá en el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="9445e-119">In the future, .NET Core scripting will become the default.</span></span>

### <a name="write-your-first-script"></a><span data-ttu-id="9445e-120">escritura del primer script</span><span class="sxs-lookup"><span data-stu-id="9445e-120">Write your first script</span></span>

<span data-ttu-id="9445e-121">Una vez que haya configurado Visual Studio Code para usar el scripting de .NET Core, vaya a la vista del explorador en Visual Studio Code y cree un archivo nuevo.</span><span class="sxs-lookup"><span data-stu-id="9445e-121">Once you've configured Visual Studio Code to use .NET Core scripting, navigate to the Explorer view in Visual Studio Code and create a new file.</span></span> <span data-ttu-id="9445e-122">Asígnele el nombre *MyFirstScript. FSX*.</span><span class="sxs-lookup"><span data-stu-id="9445e-122">Name it *MyFirstScript.fsx*.</span></span>

<span data-ttu-id="9445e-123">Ahora, agregue el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="9445e-123">Now add the following code to it:</span></span>

[!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/to-pig-latin.fsx)]

<span data-ttu-id="9445e-124">Esta función convierte una palabra en una forma de [Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin).</span><span class="sxs-lookup"><span data-stu-id="9445e-124">This function converts a word to a form of [Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin).</span></span> <span data-ttu-id="9445e-125">El siguiente paso es evaluarlo mediante F# interactivo (FSI).</span><span class="sxs-lookup"><span data-stu-id="9445e-125">The next step is to evaluate it using F# Interactive (FSI).</span></span>

<span data-ttu-id="9445e-126">Resalte toda la función (debe tener 11 líneas de longitud).</span><span class="sxs-lookup"><span data-stu-id="9445e-126">Highlight the entire function (it should be 11 lines long).</span></span> <span data-ttu-id="9445e-127">Una vez resaltado, mantenga presionada la tecla **Alt** y presione **entrar**.</span><span class="sxs-lookup"><span data-stu-id="9445e-127">Once it's highlighted, hold the **Alt** key and hit **Enter**.</span></span> <span data-ttu-id="9445e-128">Observará que aparece una ventana de terminal en la parte inferior de la pantalla y debería tener un aspecto similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="9445e-128">You'll notice a terminal window pop up on the bottom of the screen, and it should look similar to this:</span></span>

![Ejemplo de salida de F# interactivo con Ionide](./media/getting-started-vscode/vscode-fsi.png)

<span data-ttu-id="9445e-130">Esto hizo tres cosas:</span><span class="sxs-lookup"><span data-stu-id="9445e-130">This did three things:</span></span>

1. <span data-ttu-id="9445e-131">Se inició el proceso FSI.</span><span class="sxs-lookup"><span data-stu-id="9445e-131">It started the FSI process.</span></span>
2. <span data-ttu-id="9445e-132">Envió el código que resaltó en el proceso FSI.</span><span class="sxs-lookup"><span data-stu-id="9445e-132">It sent the code you highlighted over the FSI process.</span></span>
3. <span data-ttu-id="9445e-133">El proceso FSI evaluó el código que ha enviado.</span><span class="sxs-lookup"><span data-stu-id="9445e-133">The FSI process evaluated the code you sent over.</span></span>

<span data-ttu-id="9445e-134">Dado que lo que envió es una [función](../language-reference/functions/index.md), ahora puede llamar a esa función con FSI.</span><span class="sxs-lookup"><span data-stu-id="9445e-134">Because what you sent over was a [function](../language-reference/functions/index.md), you can now call that function with FSI!</span></span> <span data-ttu-id="9445e-135">En la ventana interactiva, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9445e-135">In the interactive window, type the following:</span></span>

```fsharp
toPigLatin "banana";;
```

<span data-ttu-id="9445e-136">Debería ver el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="9445e-136">You should see the following result:</span></span>

```fsharp
val it : string = "ananabay"
```

<span data-ttu-id="9445e-137">Ahora, vamos a probar una vocal como la primera letra.</span><span class="sxs-lookup"><span data-stu-id="9445e-137">Now, let's try with a vowel as the first letter.</span></span> <span data-ttu-id="9445e-138">Escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9445e-138">Enter the following:</span></span>

```fsharp
toPigLatin "apple";;
```

<span data-ttu-id="9445e-139">Debería ver el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="9445e-139">You should see the following result:</span></span>

```fsharp
val it : string = "appleyay"
```

<span data-ttu-id="9445e-140">Parece que la función funciona según lo esperado.</span><span class="sxs-lookup"><span data-stu-id="9445e-140">The function appears to be working as expected.</span></span> <span data-ttu-id="9445e-141">Enhorabuena, acaba de escribir su primera función de F # en Visual Studio Code y la evaluó con FSI.</span><span class="sxs-lookup"><span data-stu-id="9445e-141">Congratulations, you just wrote your first F# function in Visual Studio Code and evaluated it with FSI!</span></span>

> [!NOTE]
> <span data-ttu-id="9445e-142">Como puede haber observado, las líneas de FSI se terminan con `;;` .</span><span class="sxs-lookup"><span data-stu-id="9445e-142">As you may have noticed, the lines in FSI are terminated with `;;`.</span></span> <span data-ttu-id="9445e-143">Esto se debe a que FSI le permite escribir varias líneas.</span><span class="sxs-lookup"><span data-stu-id="9445e-143">This is because FSI allows you to enter multiple lines.</span></span> <span data-ttu-id="9445e-144">Al `;;` final permite que FSI sepa cuándo finaliza el código.</span><span class="sxs-lookup"><span data-stu-id="9445e-144">The `;;` at the end lets FSI know when the code is finished.</span></span>

## <a name="explaining-the-code"></a><span data-ttu-id="9445e-145">Explicación del código</span><span class="sxs-lookup"><span data-stu-id="9445e-145">Explaining the code</span></span>

<span data-ttu-id="9445e-146">Si no está seguro de lo que realmente está haciendo el código, aquí se muestra paso a paso.</span><span class="sxs-lookup"><span data-stu-id="9445e-146">If you're not sure about what the code is actually doing, here's a step-by-step.</span></span>

<span data-ttu-id="9445e-147">Como puede ver, `toPigLatin` es una función que toma una palabra como su entrada y la convierte en una representación Pig-Latin de esa palabra.</span><span class="sxs-lookup"><span data-stu-id="9445e-147">As you can see, `toPigLatin` is a function that takes a word as its input and converts it to a Pig-Latin representation of that word.</span></span> <span data-ttu-id="9445e-148">Las reglas para esto son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="9445e-148">The rules for this are as follows:</span></span>

<span data-ttu-id="9445e-149">Si el primer carácter de una palabra comienza con una vocal, agregue "Yay" al final de la palabra.</span><span class="sxs-lookup"><span data-stu-id="9445e-149">If the first character in a word starts with a vowel, add "yay" to the end of the word.</span></span> <span data-ttu-id="9445e-150">Si no se inicia con una vocal, mueva el primer carácter al final de la palabra y agréguele "Ay".</span><span class="sxs-lookup"><span data-stu-id="9445e-150">If it doesn't start with a vowel, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="9445e-151">Es posible que haya observado lo siguiente en FSI:</span><span class="sxs-lookup"><span data-stu-id="9445e-151">You may have noticed the following in FSI:</span></span>

```fsharp
val toPigLatin : word:string -> string
```

<span data-ttu-id="9445e-152">Esto indica que `toPigLatin` es una función que toma `string` como entrada (llamada `word` ) y devuelve otra `string` .</span><span class="sxs-lookup"><span data-stu-id="9445e-152">This states that `toPigLatin` is a function that takes in a `string` as input (called `word`), and returns another `string`.</span></span> <span data-ttu-id="9445e-153">Esto se conoce como la [firma de tipo de la función](https://fsharpforfunandprofit.com/posts/function-signatures/), una parte fundamental de f # que es clave para entender el código de f #.</span><span class="sxs-lookup"><span data-stu-id="9445e-153">This is known as the [type signature of the function](https://fsharpforfunandprofit.com/posts/function-signatures/), a fundamental piece of F# that's key to understanding F# code.</span></span> <span data-ttu-id="9445e-154">También observará esto si mantiene el puntero sobre la función en Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="9445e-154">You'll also notice this if you hover over the function in Visual Studio Code.</span></span>

<span data-ttu-id="9445e-155">En el cuerpo de la función, observará dos partes distintas:</span><span class="sxs-lookup"><span data-stu-id="9445e-155">In the body of the function, you'll notice two distinct parts:</span></span>

1. <span data-ttu-id="9445e-156">Función interna, denominada `isVowel` , que determina si un carácter determinado ( `c` ) es una vocal comprobando si coincide con uno de los patrones proporcionados a través de la [coincidencia de patrones](../language-reference/pattern-matching.md):</span><span class="sxs-lookup"><span data-stu-id="9445e-156">An inner function, called `isVowel`, that determines if a given character (`c`) is a vowel by checking if it matches one of the provided patterns via [Pattern Matching](../language-reference/pattern-matching.md):</span></span>

   [!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L2-L6)]

2. <span data-ttu-id="9445e-157">[`if..then..else`](../language-reference/conditional-expressions-if-then-else.md)Expresión que comprueba si el primer carácter es una vocal y crea un valor devuelto fuera de los caracteres de entrada en función de si el primer carácter era una vocal o no:</span><span class="sxs-lookup"><span data-stu-id="9445e-157">An [`if..then..else`](../language-reference/conditional-expressions-if-then-else.md) expression that checks if the first character is a vowel, and constructs a return value out of the input characters based on if the first character was a vowel or not:</span></span>

   [!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L8-L11)]

<span data-ttu-id="9445e-158">El flujo de `toPigLatin` es así:</span><span class="sxs-lookup"><span data-stu-id="9445e-158">The flow of `toPigLatin` is thus:</span></span>

<span data-ttu-id="9445e-159">Comprueba si el primer carácter de la palabra de entrada es una vocal.</span><span class="sxs-lookup"><span data-stu-id="9445e-159">Check if the first character of the input word is a vowel.</span></span> <span data-ttu-id="9445e-160">Si es así, adjunte "Yay" al final de la palabra.</span><span class="sxs-lookup"><span data-stu-id="9445e-160">If it is, attach "yay" to the end of the word.</span></span> <span data-ttu-id="9445e-161">En caso contrario, mueva el primer carácter al final de la palabra y agréguele "Ay".</span><span class="sxs-lookup"><span data-stu-id="9445e-161">Otherwise, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="9445e-162">Hay un aspecto final que se debe tener en cuenta: en F #, no hay ninguna instrucción explícita que devolver desde la función.</span><span class="sxs-lookup"><span data-stu-id="9445e-162">There's one final thing to notice about this: in F#, there's no explicit instruction to return from the function.</span></span> <span data-ttu-id="9445e-163">Esto se debe a que F # está basado en expresiones y la última expresión evaluada en el cuerpo de una función determina el valor devuelto de esa función.</span><span class="sxs-lookup"><span data-stu-id="9445e-163">This is because F# is expression-based, and the last expression evaluated in the body of a function determines the return value of that function.</span></span> <span data-ttu-id="9445e-164">Dado que `if..then..else` es una expresión, la evaluación del cuerpo del `then` bloque o el cuerpo del `else` bloque determina el valor devuelto por la `toPigLatin` función.</span><span class="sxs-lookup"><span data-stu-id="9445e-164">Because `if..then..else` is itself an expression, evaluation of the body of the `then` block or the body of the `else` block determines the value returned by the `toPigLatin` function.</span></span>

## <a name="turn-the-console-app-into-a-pig-latin-generator"></a><span data-ttu-id="9445e-165">Convertir la aplicación de consola en un generador de Pig Latin</span><span class="sxs-lookup"><span data-stu-id="9445e-165">Turn the console app into a Pig Latin generator</span></span>

<span data-ttu-id="9445e-166">En las secciones anteriores de este artículo se ha mostrado un primer paso común en la escritura de código de F #: escribir una función inicial y ejecutarla de forma interactiva con FSI.</span><span class="sxs-lookup"><span data-stu-id="9445e-166">The previous sections in this article demonstrated a common first step in writing F# code: writing an initial function and executing it interactively with FSI.</span></span> <span data-ttu-id="9445e-167">Esto se conoce como desarrollo controlado por REPL, donde [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) representa el bucle de lectura-evaluación-impresión.</span><span class="sxs-lookup"><span data-stu-id="9445e-167">This is known as REPL-driven development, where [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) stands for "Read-Evaluate-Print Loop".</span></span> <span data-ttu-id="9445e-168">Es una excelente manera de experimentar con la funcionalidad hasta que tenga algo que funcione.</span><span class="sxs-lookup"><span data-stu-id="9445e-168">It's a great way to experiment with functionality until you have something working.</span></span>

<span data-ttu-id="9445e-169">El siguiente paso en el desarrollo basado en REPL es trasladar el código de trabajo a un archivo de implementación de F #.</span><span class="sxs-lookup"><span data-stu-id="9445e-169">The next step in REPL-driven development is to move working code into an F# implementation file.</span></span> <span data-ttu-id="9445e-170">Después, el compilador de F # puede compilar en un ensamblado que se pueda ejecutar.</span><span class="sxs-lookup"><span data-stu-id="9445e-170">It can then be compiled by the F# compiler into an assembly that can be executed.</span></span>

<span data-ttu-id="9445e-171">Para empezar, abra el archivo *Program. FS* que creó anteriormente con el CLI de .net Core.</span><span class="sxs-lookup"><span data-stu-id="9445e-171">To begin, open the *Program.fs* file that you created earlier with the .NET Core CLI.</span></span> <span data-ttu-id="9445e-172">Observará que parte del código ya está en él.</span><span class="sxs-lookup"><span data-stu-id="9445e-172">You'll notice that some code is already in there.</span></span>

<span data-ttu-id="9445e-173">A continuación, cree una nueva [`module`](../language-reference/modules.md) llamada `PigLatin` y copie la `toPigLatin` función que creó anteriormente en ella como tal:</span><span class="sxs-lookup"><span data-stu-id="9445e-173">Next, create a new [`module`](../language-reference/modules.md) called `PigLatin` and copy the `toPigLatin` function you created earlier into it as such:</span></span>

[!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/pig-latin.fs#L3-L14)]

<span data-ttu-id="9445e-174">Este módulo debe estar por encima de la `main` función y por debajo de la `open System` declaración.</span><span class="sxs-lookup"><span data-stu-id="9445e-174">This module should be above the `main` function and below the `open System` declaration.</span></span> <span data-ttu-id="9445e-175">El orden de las declaraciones es importante en F #, por lo que deberá definir la función antes de llamarla en un archivo.</span><span class="sxs-lookup"><span data-stu-id="9445e-175">Order of declarations matters in F#, so you'll need to define the function before you call it in a file.</span></span>

<span data-ttu-id="9445e-176">Ahora, en la `main` función, llame a la función de generador de Pig Latin en los argumentos:</span><span class="sxs-lookup"><span data-stu-id="9445e-176">Now, in the `main` function, call your Pig Latin generator function on the arguments:</span></span>

```fsharp
[<EntryPoint>]
let main argv =
    for name in argv do
        let newName = PigLatin.toPigLatin name
        printfn %"{name} in Pig Latin is: {newName}"

    0
```

<span data-ttu-id="9445e-177">Ahora puede ejecutar la aplicación de consola desde la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="9445e-177">Now you can run your console app from the command line:</span></span>

```dotnetcli
dotnet run apple banana
```

<span data-ttu-id="9445e-178">Y verá que genera el mismo resultado que el archivo de script, pero esta vez como un programa en ejecución.</span><span class="sxs-lookup"><span data-stu-id="9445e-178">And you'll see that it outputs the same result as your script file, but this time as a running program!</span></span>

## <a name="troubleshooting-ionide"></a><span data-ttu-id="9445e-179">Solución de problemas de Ionide</span><span class="sxs-lookup"><span data-stu-id="9445e-179">Troubleshooting Ionide</span></span>

<span data-ttu-id="9445e-180">Estas son algunas de las formas en que puede solucionar ciertos problemas que pueden surgir:</span><span class="sxs-lookup"><span data-stu-id="9445e-180">Here are a few ways you can troubleshoot certain problems that you might run into:</span></span>

1. <span data-ttu-id="9445e-181">Para obtener las características de edición de código de Ionide, los archivos de F # deben guardarse en el disco y dentro de una carpeta que esté abierta en el área de trabajo Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="9445e-181">To get the code editing features of Ionide, your F# files need to be saved to disk and inside of a folder that is open in the Visual Studio Code workspace.</span></span>
1. <span data-ttu-id="9445e-182">Si ha realizado cambios en el sistema o ha instalado los requisitos previos de Ionide con Visual Studio Code abrir, reinicie Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="9445e-182">If you've made changes to your system or installed Ionide prerequisites with Visual Studio Code open, restart Visual Studio Code.</span></span>
1. <span data-ttu-id="9445e-183">Si tiene caracteres no válidos en los directorios del proyecto, es posible que Ionide no funcione.</span><span class="sxs-lookup"><span data-stu-id="9445e-183">If you have invalid characters in your project directories, Ionide might not work.</span></span>  <span data-ttu-id="9445e-184">Cambie el nombre de los directorios del proyecto si éste es el caso.</span><span class="sxs-lookup"><span data-stu-id="9445e-184">Rename your project directories if this is the case.</span></span>
1. <span data-ttu-id="9445e-185">Si no funciona ninguno de los comandos de Ionide, compruebe los [enlaces de teclado de Visual Studio Code](https://code.visualstudio.com/docs/getstarted/keybindings#_advanced-customization) para ver si se están reemplazando por accidente.</span><span class="sxs-lookup"><span data-stu-id="9445e-185">If none of the Ionide commands are working, check your [Visual Studio Code Key Bindings](https://code.visualstudio.com/docs/getstarted/keybindings#_advanced-customization) to see if you're overriding them by accident.</span></span>
1. <span data-ttu-id="9445e-186">Si Ionide se ha interrumpido en el equipo y ninguno de los anteriores ha solucionado el problema, intente quitar el `ionide-fsharp` directorio en la máquina y vuelva a instalar el conjunto de complementos.</span><span class="sxs-lookup"><span data-stu-id="9445e-186">If Ionide is broken on your machine and none of the above has fixed your problem, try removing the `ionide-fsharp` directory on your machine and reinstall the plugin suite.</span></span>
1. <span data-ttu-id="9445e-187">Si un proyecto no se cargó (el Explorador de soluciones de F # lo mostrará), haga clic con el botón derecho en el proyecto y haga clic en **Ver detalles** para obtener más información de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="9445e-187">If a project failed to load (the F# Solution Explorer will show this), right-click on that project and click **See details** to get more diagnostic info.</span></span>

<span data-ttu-id="9445e-188">Ionide es un proyecto de código abierto creado y mantenido por miembros de la comunidad de F #.</span><span class="sxs-lookup"><span data-stu-id="9445e-188">Ionide is an open source project built and maintained by members of the F# community.</span></span> <span data-ttu-id="9445e-189">Informe de los problemas y no dude en contribuir en el [repositorio de github ionide-vscode-FSharp](https://github.com/ionide/ionide-vscode-fsharp).</span><span class="sxs-lookup"><span data-stu-id="9445e-189">Please report issues and feel free to contribute at the [ionide-vscode-fsharp GitHub repository](https://github.com/ionide/ionide-vscode-fsharp).</span></span>

<span data-ttu-id="9445e-190">También puede solicitar más ayuda de los desarrolladores de Ionide y de la comunidad de F # en el [canal de Gitter de Ionide](https://gitter.im/ionide/ionide-project).</span><span class="sxs-lookup"><span data-stu-id="9445e-190">You can also ask for further help from the Ionide developers and F# community in the [Ionide Gitter channel](https://gitter.im/ionide/ionide-project).</span></span>

## <a name="next-steps"></a><span data-ttu-id="9445e-191">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="9445e-191">Next steps</span></span>

<span data-ttu-id="9445e-192">Para obtener más información sobre F # y las características del lenguaje, consulte [paseo por f #](../tour.md).</span><span class="sxs-lookup"><span data-stu-id="9445e-192">To learn more about F# and the features of the language, check out [Tour of F#](../tour.md).</span></span>
