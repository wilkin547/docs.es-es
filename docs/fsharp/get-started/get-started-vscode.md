---
title: Introducción a F# en Visual Studio Code
description: Aprenda a usar F# con Visual Studio Code y el conjunto de complementos de Ionide.
ms.date: 12/23/2018
ms.openlocfilehash: 2fa0518488d37b2130aaba96028ac92dac77eb97
ms.sourcegitcommit: a2d0e1f66367367065bc8dc0dde488ab536da73f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2019
ms.locfileid: "71082983"
---
# <a name="get-started-with-f-in-visual-studio-code"></a><span data-ttu-id="b2618-103">Introducción a F# en Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="b2618-103">Get Started with F# in Visual Studio Code</span></span>

<span data-ttu-id="b2618-104">Puede escribir F# en [Visual Studio Code](https://code.visualstudio.com) con el [complemento Ionide](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp) para obtener una excelente experiencia de entorno de desarrollo integrado (IDE) multiplataforma y flexible con IntelliSense y refactorizaciones de código básicas.</span><span class="sxs-lookup"><span data-stu-id="b2618-104">You can write F# in [Visual Studio Code](https://code.visualstudio.com) with the [Ionide plugin](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp) to get a great cross-platform, lightweight Integrated Development Environment (IDE) experience with IntelliSense and basic code refactorings.</span></span> <span data-ttu-id="b2618-105">Visite [Ionide.IO](http://ionide.io) para obtener más información sobre el complemento.</span><span class="sxs-lookup"><span data-stu-id="b2618-105">Visit [Ionide.io](http://ionide.io) to learn more about the plugin.</span></span>

<span data-ttu-id="b2618-106">Para empezar, asegúrese de que tiene [ F# y el complemento Ionide instalado correctamente](install-fsharp.md#install-f-with-visual-studio-code).</span><span class="sxs-lookup"><span data-stu-id="b2618-106">To begin, ensure that you have [F# and the Ionide plugin correctly installed](install-fsharp.md#install-f-with-visual-studio-code).</span></span>

> [!NOTE]
> <span data-ttu-id="b2618-107">Ionide generará proyectos F# de .NET Framework, no dotnet Core, que pueden tener problemas de compatibilidad entre plataformas.</span><span class="sxs-lookup"><span data-stu-id="b2618-107">Ionide will generate .NET Framework F# projects, not dotnet core, which can have cross-platform compatibility issues.</span></span> <span data-ttu-id="b2618-108">Si está ejecutando en **Linux** o **OSX**, una forma más sencilla de empezar es usar las [herramientas de línea de comandos](get-started-command-line.md).</span><span class="sxs-lookup"><span data-stu-id="b2618-108">If you are running on **Linux** or **OSX**, a simpler way to get started is to use the [command-line tools](get-started-command-line.md).</span></span>

## <a name="creating-your-first-project-with-ionide"></a><span data-ttu-id="b2618-109">Crear su primer proyecto con Ionide</span><span class="sxs-lookup"><span data-stu-id="b2618-109">Creating your first project with Ionide</span></span>

<span data-ttu-id="b2618-110">Para crear un nuevo F# proyecto, abra Visual Studio Code en una nueva carpeta (puede asignarle el nombre que desee).</span><span class="sxs-lookup"><span data-stu-id="b2618-110">To create a new F# project, open Visual Studio Code in a new folder (you can name it whatever you like).</span></span>

<span data-ttu-id="b2618-111">A continuación, abra la paleta de comandos (**ver > paleta de comandos**) y escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b2618-111">Next, open the command palette (**View > Command Palette**) and type the following:</span></span>

```console
> F# new project
```

<span data-ttu-id="b2618-112">Esto está basado en el proyecto de [falsificación](https://github.com/fsharp-editing/Forge).</span><span class="sxs-lookup"><span data-stu-id="b2618-112">This is powered by the [FORGE](https://github.com/fsharp-editing/Forge) project.</span></span>

> [!NOTE]
> <span data-ttu-id="b2618-113">Si no ve las opciones de plantilla, intente actualizar las plantillas ejecutando el siguiente comando en la paleta de `>F#: Refresh Project Templates`comandos:.</span><span class="sxs-lookup"><span data-stu-id="b2618-113">If you don't see template options, try refreshing templates by running the following command in the Command Palette: `>F#: Refresh Project Templates`.</span></span>

<span data-ttu-id="b2618-114">Seleccione "F#: Nuevo proyecto "presionando **entrar**.</span><span class="sxs-lookup"><span data-stu-id="b2618-114">Select "F#: New Project" by hitting **Enter**.</span></span> <span data-ttu-id="b2618-115">Esto le llevará al paso siguiente, que es para seleccionar una plantilla de proyecto.</span><span class="sxs-lookup"><span data-stu-id="b2618-115">This takes you to the next step, which is for selecting a project template.</span></span>

<span data-ttu-id="b2618-116">Seleccione la `classlib` plantilla y presione **entrar**.</span><span class="sxs-lookup"><span data-stu-id="b2618-116">Pick the `classlib` template and hit **Enter**.</span></span>

<span data-ttu-id="b2618-117">A continuación, elija un directorio en el que crear el proyecto.</span><span class="sxs-lookup"><span data-stu-id="b2618-117">Next, pick a directory to create the project in.</span></span> <span data-ttu-id="b2618-118">Si lo deja en blanco, se usa el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="b2618-118">If you leave it blank, it uses the current directory.</span></span>

<span data-ttu-id="b2618-119">Por último, asigne un nombre al proyecto en el paso final.</span><span class="sxs-lookup"><span data-stu-id="b2618-119">Finally, name your project in the final step.</span></span> <span data-ttu-id="b2618-120">F#usa [mayúsculas y minúsculas Pascal](http://c2.com/cgi/wiki?PascalCase) para los nombres de proyecto.</span><span class="sxs-lookup"><span data-stu-id="b2618-120">F# uses [Pascal case](http://c2.com/cgi/wiki?PascalCase) for project names.</span></span> <span data-ttu-id="b2618-121">En este artículo `ClassLibraryDemo` se usa como nombre.</span><span class="sxs-lookup"><span data-stu-id="b2618-121">This article uses `ClassLibraryDemo` as the name.</span></span> <span data-ttu-id="b2618-122">Una vez que haya escrito el nombre que desea para el proyecto, presione **entrar**.</span><span class="sxs-lookup"><span data-stu-id="b2618-122">Once you've entered the name you want for your project, hit **Enter**.</span></span>

<span data-ttu-id="b2618-123">Si siguió el paso anterior, debería obtener el Visual Studio Code área de trabajo en el lado izquierdo para que aparezca con lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b2618-123">If you followed the previous step, you should get the Visual Studio Code Workspace on the left-hand side to appear with the following:</span></span>

1. <span data-ttu-id="b2618-124">El F# proyecto en sí, debajo `ClassLibraryDemo` de la carpeta.</span><span class="sxs-lookup"><span data-stu-id="b2618-124">The F# project itself, underneath the `ClassLibraryDemo` folder.</span></span>
2. <span data-ttu-id="b2618-125">La estructura de directorios correcta para agregar paquetes [`Paket`](https://fsprojects.github.io/Paket/)a través de.</span><span class="sxs-lookup"><span data-stu-id="b2618-125">The correct directory structure for adding packages via [`Paket`](https://fsprojects.github.io/Paket/).</span></span>
3. <span data-ttu-id="b2618-126">Un script de compilación multiplataforma con [`FAKE`](https://fsharp.github.io/FAKE/).</span><span class="sxs-lookup"><span data-stu-id="b2618-126">A cross-platform build script with [`FAKE`](https://fsharp.github.io/FAKE/).</span></span>
4. <span data-ttu-id="b2618-127">Ejecutable `paket.exe` que puede capturar paquetes y resolver las dependencias automáticamente.</span><span class="sxs-lookup"><span data-stu-id="b2618-127">The `paket.exe` executable that can fetch packages and resolve dependencies for you.</span></span>
5. <span data-ttu-id="b2618-128">Un `.gitignore` archivo si desea agregar este proyecto al control de código fuente basado en Git.</span><span class="sxs-lookup"><span data-stu-id="b2618-128">A `.gitignore` file if you wish to add this project to Git-based source control.</span></span>

## <a name="writing-some-code"></a><span data-ttu-id="b2618-129">Escribir código</span><span class="sxs-lookup"><span data-stu-id="b2618-129">Writing some code</span></span>

<span data-ttu-id="b2618-130">Abra la carpeta *ClassLibraryDemo* .</span><span class="sxs-lookup"><span data-stu-id="b2618-130">Open the *ClassLibraryDemo* folder.</span></span>  <span data-ttu-id="b2618-131">Debería ver los archivos siguientes:</span><span class="sxs-lookup"><span data-stu-id="b2618-131">You should see the following files:</span></span>

1. <span data-ttu-id="b2618-132">`ClassLibraryDemo.fs`, un F# archivo de implementación con una clase definida.</span><span class="sxs-lookup"><span data-stu-id="b2618-132">`ClassLibraryDemo.fs`, an F# implementation file with a class defined.</span></span>
2. <span data-ttu-id="b2618-133">`ClassLibraryDemo.fsproj`, un F# archivo de proyecto que se usa para compilar este proyecto.</span><span class="sxs-lookup"><span data-stu-id="b2618-133">`ClassLibraryDemo.fsproj`, an F# project file used to build this project.</span></span>
3. <span data-ttu-id="b2618-134">`Script.fsx`, un F# archivo de script que carga el archivo de código fuente.</span><span class="sxs-lookup"><span data-stu-id="b2618-134">`Script.fsx`, an F# script file that loads the source file.</span></span>
4. <span data-ttu-id="b2618-135">`paket.references`, un archivo Paket que especifica las dependencias del proyecto.</span><span class="sxs-lookup"><span data-stu-id="b2618-135">`paket.references`, a Paket file that specifies the project dependencies.</span></span>

<span data-ttu-id="b2618-136">Abra `Script.fsx`y agregue el código siguiente al final de la misma:</span><span class="sxs-lookup"><span data-stu-id="b2618-136">Open `Script.fsx`, and add the following code at the end of it:</span></span>

[!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/to-pig-latin.fsx)]

<span data-ttu-id="b2618-137">Esta función convierte una palabra en una forma de [Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin).</span><span class="sxs-lookup"><span data-stu-id="b2618-137">This function converts a word to a form of [Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin).</span></span> <span data-ttu-id="b2618-138">El siguiente paso es evaluarlo mediante F# Interactive (FSI).</span><span class="sxs-lookup"><span data-stu-id="b2618-138">The next step is to evaluate it using F# Interactive (FSI).</span></span>

<span data-ttu-id="b2618-139">Resalte toda la función (debe tener 11 líneas de longitud).</span><span class="sxs-lookup"><span data-stu-id="b2618-139">Highlight the entire function (it should be 11 lines long).</span></span> <span data-ttu-id="b2618-140">Una vez resaltado, mantenga presionada la tecla **Alt** y presione **entrar**.</span><span class="sxs-lookup"><span data-stu-id="b2618-140">Once it is highlighted, hold the **Alt** key and hit **Enter**.</span></span> <span data-ttu-id="b2618-141">Observará que aparece una ventana emergente y debería mostrar algo parecido a esto:</span><span class="sxs-lookup"><span data-stu-id="b2618-141">You'll notice a window pop up below, and it should show something like this:</span></span>

![Ejemplo de F# salida interactiva con Ionide](./media/getting-started-vscode/vscode-fsi.png)

<span data-ttu-id="b2618-143">Esto hizo tres cosas:</span><span class="sxs-lookup"><span data-stu-id="b2618-143">This did three things:</span></span>

1. <span data-ttu-id="b2618-144">Se inició el proceso FSI.</span><span class="sxs-lookup"><span data-stu-id="b2618-144">It started the FSI process.</span></span>
2. <span data-ttu-id="b2618-145">Envió el código que resaltó en el proceso FSI.</span><span class="sxs-lookup"><span data-stu-id="b2618-145">It sent the code you highlighted over the FSI process.</span></span>
3. <span data-ttu-id="b2618-146">El proceso FSI evaluó el código que ha enviado.</span><span class="sxs-lookup"><span data-stu-id="b2618-146">The FSI process evaluated the code you sent over.</span></span>

<span data-ttu-id="b2618-147">Dado que lo que envió es una [función](../language-reference/functions/index.md), ahora puede llamar a esa función con FSI.</span><span class="sxs-lookup"><span data-stu-id="b2618-147">Because what you sent over was a [function](../language-reference/functions/index.md), you can now call that function with FSI!</span></span> <span data-ttu-id="b2618-148">En la ventana interactiva, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b2618-148">In the interactive window, type the following:</span></span>

```fsharp
toPigLatin "banana";;
```

<span data-ttu-id="b2618-149">Debería ver el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="b2618-149">You should see the following result:</span></span>

```fsharp
val it : string = "ananabay"
```

<span data-ttu-id="b2618-150">Ahora, vamos a probar una vocal como la primera letra.</span><span class="sxs-lookup"><span data-stu-id="b2618-150">Now, let's try with a vowel as the first letter.</span></span> <span data-ttu-id="b2618-151">Escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b2618-151">Enter the following:</span></span>

```fsharp
toPigLatin "apple";;
```

<span data-ttu-id="b2618-152">Debería ver el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="b2618-152">You should see the following result:</span></span>

```fsharp
val it : string = "appleyay"
```

<span data-ttu-id="b2618-153">Parece que la función funciona según lo esperado.</span><span class="sxs-lookup"><span data-stu-id="b2618-153">The function appears to be working as expected.</span></span> <span data-ttu-id="b2618-154">Enhorabuena, acaba de escribir su primera F# función en Visual Studio Code y la evaluó con FSI.</span><span class="sxs-lookup"><span data-stu-id="b2618-154">Congratulations, you just wrote your first F# function in Visual Studio Code and evaluated it with FSI!</span></span>

> [!NOTE]
> <span data-ttu-id="b2618-155">Como puede haber observado, las líneas de FSI se terminan con `;;`.</span><span class="sxs-lookup"><span data-stu-id="b2618-155">As you may have noticed, the lines in FSI are terminated with `;;`.</span></span> <span data-ttu-id="b2618-156">Esto se debe a que FSI le permite escribir varias líneas.</span><span class="sxs-lookup"><span data-stu-id="b2618-156">This is because FSI allows you to enter multiple lines.</span></span> <span data-ttu-id="b2618-157">Al `;;` final permite que FSI sepa cuándo finaliza el código.</span><span class="sxs-lookup"><span data-stu-id="b2618-157">The `;;` at the end lets FSI know when the code is finished.</span></span>

## <a name="explaining-the-code"></a><span data-ttu-id="b2618-158">Explicación del código</span><span class="sxs-lookup"><span data-stu-id="b2618-158">Explaining the code</span></span>

<span data-ttu-id="b2618-159">Si no está seguro de lo que realmente está haciendo el código, aquí se muestra paso a paso.</span><span class="sxs-lookup"><span data-stu-id="b2618-159">If you're not sure about what the code is actually doing, here's a step-by-step.</span></span>

<span data-ttu-id="b2618-160">Como puede ver, `toPigLatin` es una función que toma una palabra como su entrada y la convierte en una representación de Pig-latín de esa palabra.</span><span class="sxs-lookup"><span data-stu-id="b2618-160">As you can see, `toPigLatin` is a function that takes a word as its input and converts it to a Pig-Latin representation of that word.</span></span> <span data-ttu-id="b2618-161">Las reglas para esto son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="b2618-161">The rules for this are as follows:</span></span>

<span data-ttu-id="b2618-162">Si el primer carácter de una palabra comienza con una vocal, agregue "Yay" al final de la palabra.</span><span class="sxs-lookup"><span data-stu-id="b2618-162">If the first character in a word starts with a vowel, add "yay" to the end of the word.</span></span> <span data-ttu-id="b2618-163">Si no se inicia con una vocal, mueva el primer carácter al final de la palabra y agréguele "Ay".</span><span class="sxs-lookup"><span data-stu-id="b2618-163">If it doesn't start with a vowel, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="b2618-164">Es posible que haya observado lo siguiente en FSI:</span><span class="sxs-lookup"><span data-stu-id="b2618-164">You may have noticed the following in FSI:</span></span>

```fsharp
val toPigLatin : word:string -> string
```

<span data-ttu-id="b2618-165">Esto indica que `toPigLatin` es una función que toma `string` como entrada (llamada `word`) y devuelve otra `string`.</span><span class="sxs-lookup"><span data-stu-id="b2618-165">This states that `toPigLatin` is a function that takes in a `string` as input (called `word`), and returns another `string`.</span></span> <span data-ttu-id="b2618-166">Esto se conoce como la [firma de tipo de la función](https://fsharpforfunandprofit.com/posts/function-signatures/), una parte fundamental F# de la clave para entender F# el código.</span><span class="sxs-lookup"><span data-stu-id="b2618-166">This is known as the [type signature of the function](https://fsharpforfunandprofit.com/posts/function-signatures/), a fundamental piece of F# that's key to understanding F# code.</span></span> <span data-ttu-id="b2618-167">También observará esto si mantiene el puntero sobre la función en Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="b2618-167">You'll also notice this if you hover over the function in Visual Studio Code.</span></span>

<span data-ttu-id="b2618-168">En el cuerpo de la función, observará dos partes distintas:</span><span class="sxs-lookup"><span data-stu-id="b2618-168">In the body of the function, you'll notice two distinct parts:</span></span>

1. <span data-ttu-id="b2618-169">Función interna, denominada `isVowel`, que determina si un carácter determinado (`c`) es una vocal comprobando si coincide con uno de los patrones proporcionados a través de la coincidencia de [patrones](../language-reference/pattern-matching.md):</span><span class="sxs-lookup"><span data-stu-id="b2618-169">An inner function, called `isVowel`, that determines if a given character (`c`) is a vowel by checking if it matches one of the provided patterns via [Pattern Matching](../language-reference/pattern-matching.md):</span></span>

   [!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L2-L6)]

2. <span data-ttu-id="b2618-170">[`if..then..else`](../language-reference/conditional-expressions-if-then-else.md) Expresión que comprueba si el primer carácter es una vocal y crea un valor devuelto fuera de los caracteres de entrada en función de si el primer carácter era una vocal o no:</span><span class="sxs-lookup"><span data-stu-id="b2618-170">An [`if..then..else`](../language-reference/conditional-expressions-if-then-else.md) expression that checks if the first character is a vowel, and constructs a return value out of the input characters based on if the first character was a vowel or not:</span></span>

   [!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L8-L11)]

<span data-ttu-id="b2618-171">El flujo de `toPigLatin` es así:</span><span class="sxs-lookup"><span data-stu-id="b2618-171">The flow of `toPigLatin` is thus:</span></span>

<span data-ttu-id="b2618-172">Comprueba si el primer carácter de la palabra de entrada es una vocal.</span><span class="sxs-lookup"><span data-stu-id="b2618-172">Check if the first character of the input word is a vowel.</span></span> <span data-ttu-id="b2618-173">Si es así, adjunte "Yay" al final de la palabra.</span><span class="sxs-lookup"><span data-stu-id="b2618-173">If it is, attach "yay" to the end of the word.</span></span> <span data-ttu-id="b2618-174">En caso contrario, mueva el primer carácter al final de la palabra y agréguele "Ay".</span><span class="sxs-lookup"><span data-stu-id="b2618-174">Otherwise, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="b2618-175">Hay un aspecto final que se debe tener en cuenta: no hay ninguna instrucción explícita para devolver de la función, a diferencia de muchos otros lenguajes.</span><span class="sxs-lookup"><span data-stu-id="b2618-175">There's one final thing to notice about this: there's no explicit instruction to return from the function, unlike many other languages out there.</span></span> <span data-ttu-id="b2618-176">Esto se debe F# a que se basa en expresiones y la última expresión del cuerpo de una función es el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="b2618-176">This is because F# is Expression-based, and the last expression in the body of a function is the return value.</span></span> <span data-ttu-id="b2618-177">Dado `if..then..else` que es una expresión, el cuerpo `then` del bloque `else` o el cuerpo del bloque se devolverá en función del valor de entrada.</span><span class="sxs-lookup"><span data-stu-id="b2618-177">Because `if..then..else` is itself an expression, the body of the `then` block or the body of the `else` block will be returned depending on the input value.</span></span>

## <a name="moving-your-script-code-into-the-implementation-file"></a><span data-ttu-id="b2618-178">Mover el código de script al archivo de implementación</span><span class="sxs-lookup"><span data-stu-id="b2618-178">Moving your script code into the implementation file</span></span>

<span data-ttu-id="b2618-179">En las secciones anteriores de este artículo se ha mostrado un primer paso F# común en la escritura del código: escribir una función inicial y ejecutarla de forma interactiva con FSI.</span><span class="sxs-lookup"><span data-stu-id="b2618-179">The previous sections in this article demonstrated a common first step in writing F# code: writing an initial function and executing it interactively with FSI.</span></span> <span data-ttu-id="b2618-180">Esto se conoce como desarrollo controlado por REPL, donde [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) representa el bucle de lectura-evaluación-impresión.</span><span class="sxs-lookup"><span data-stu-id="b2618-180">This is known as REPL-driven development, where [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) stands for "Read-Evaluate-Print Loop".</span></span> <span data-ttu-id="b2618-181">Es una excelente manera de experimentar con la funcionalidad hasta que tenga algo que funcione.</span><span class="sxs-lookup"><span data-stu-id="b2618-181">It's a great way to experiment with functionality until you have something working.</span></span>

<span data-ttu-id="b2618-182">El siguiente paso del desarrollo controlado por REPL es trasladar el código de trabajo F# a un archivo de implementación.</span><span class="sxs-lookup"><span data-stu-id="b2618-182">The next step in REPL-driven development is to move working code into an F# implementation file.</span></span> <span data-ttu-id="b2618-183">Después, el F# compilador puede compilar en un ensamblado que se pueda ejecutar.</span><span class="sxs-lookup"><span data-stu-id="b2618-183">It can then be compiled by the F# compiler into an assembly that can be executed.</span></span>

<span data-ttu-id="b2618-184">Para empezar, Abra `ClassLibraryDemo.fs`.</span><span class="sxs-lookup"><span data-stu-id="b2618-184">To begin, open `ClassLibraryDemo.fs`.</span></span>  <span data-ttu-id="b2618-185">Observará que parte del código ya está en él.</span><span class="sxs-lookup"><span data-stu-id="b2618-185">You'll notice that some code is already in there.</span></span> <span data-ttu-id="b2618-186">Continúe y elimine la definición de clase, pero asegúrese de dejar la [`namespace`](../language-reference/namespaces.md) declaración en la parte superior.</span><span class="sxs-lookup"><span data-stu-id="b2618-186">Go ahead and delete the class definition, but make sure to leave the [`namespace`](../language-reference/namespaces.md) declaration at the top.</span></span>

<span data-ttu-id="b2618-187">A continuación, cree un [`module`](../language-reference/modules.md) nuevo `PigLatin` denominado y copie `toPigLatin` la función en él de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="b2618-187">Next, create a new [`module`](../language-reference/modules.md) called `PigLatin` and copy the `toPigLatin` function into it as such:</span></span>

[!code-fsharp[ToPigLatin](~/samples/snippets/fsharp/getting-started/pig-latin.fs#L1-L14)]

<span data-ttu-id="b2618-188">A continuación, vuelva `Script.fsx` a abrir el archivo y elimine `toPigLatin` toda la función, pero asegúrese de mantener las dos líneas siguientes en el archivo:</span><span class="sxs-lookup"><span data-stu-id="b2618-188">Next, open the `Script.fsx` file again, and delete the entire `toPigLatin` function, but make sure to keep the following two lines in the file:</span></span>

```fsharp
#load "ClassLibraryDemo.fs"
open ClassLibraryDemo
```

<span data-ttu-id="b2618-189">Seleccione ambas líneas de texto y presione Alt + Entrar para ejecutar estas líneas en FSI.</span><span class="sxs-lookup"><span data-stu-id="b2618-189">Select both lines of text and press Alt+Enter to execute these lines in FSI.</span></span> <span data-ttu-id="b2618-190">Estos cargarán el contenido de la biblioteca de Pig Latin en el proceso FSI `open` y `ClassLibraryDemo` el espacio de nombres para que tenga acceso a la funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="b2618-190">These will load the contents of the Pig Latin library into the FSI process and `open` the `ClassLibraryDemo` namespace so that you have access to the functionality.</span></span>

<span data-ttu-id="b2618-191">A continuación, en la ventana FSI, llame a la función `PigLatin` con el módulo que definió anteriormente:</span><span class="sxs-lookup"><span data-stu-id="b2618-191">Next, in the FSI window, call the function with the `PigLatin` module that you defined earlier:</span></span>

```console
> PigLatin.toPigLatin "banana";;
val it : string = "ananabay"
> PigLatin.toPigLatin "apple";;
val it : string = "appleyay"
```

<span data-ttu-id="b2618-192">Correcto</span><span class="sxs-lookup"><span data-stu-id="b2618-192">Success!</span></span> <span data-ttu-id="b2618-193">Obtiene los mismos resultados que antes, pero ahora se carga desde un F# archivo de implementación.</span><span class="sxs-lookup"><span data-stu-id="b2618-193">You get the same results as before, but now loaded from an F# implementation file.</span></span> <span data-ttu-id="b2618-194">La principal diferencia es que F# los archivos de código fuente se compilan en ensamblados que se pueden ejecutar en cualquier lugar, no solo en FSI.</span><span class="sxs-lookup"><span data-stu-id="b2618-194">The major difference here is that F# source files are compiled into assemblies that can be executed anywhere, not just in FSI.</span></span>

## <a name="summary"></a><span data-ttu-id="b2618-195">Resumen</span><span class="sxs-lookup"><span data-stu-id="b2618-195">Summary</span></span>

<span data-ttu-id="b2618-196">En este artículo, ha aprendido lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b2618-196">In this article, you've learned:</span></span>

1. <span data-ttu-id="b2618-197">Cómo configurar Visual Studio Code con Ionide.</span><span class="sxs-lookup"><span data-stu-id="b2618-197">How to set up Visual Studio Code with Ionide.</span></span>
2. <span data-ttu-id="b2618-198">Cómo crear su primer F# proyecto con Ionide.</span><span class="sxs-lookup"><span data-stu-id="b2618-198">How to create your first F# project with Ionide.</span></span>
3. <span data-ttu-id="b2618-199">Cómo usar F# scripting para escribir la primera F# función en Ionide y, a continuación, ejecutarla en FSI.</span><span class="sxs-lookup"><span data-stu-id="b2618-199">How to use F# Scripting to write your first F# function in Ionide and then execute it in FSI.</span></span>
4. <span data-ttu-id="b2618-200">Cómo migrar el código de script al F# origen y, después, llamar a ese código desde FSI.</span><span class="sxs-lookup"><span data-stu-id="b2618-200">How to migrate your script code to F# source and then call that code from FSI.</span></span>

<span data-ttu-id="b2618-201">Ahora está preparado para escribir mucho más F# código con Visual Studio Code y Ionide.</span><span class="sxs-lookup"><span data-stu-id="b2618-201">You're now equipped to write much more F# code using Visual Studio Code and Ionide.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="b2618-202">solución de problemas</span><span class="sxs-lookup"><span data-stu-id="b2618-202">Troubleshooting</span></span>

<span data-ttu-id="b2618-203">Estas son algunas de las formas en que puede solucionar ciertos problemas que pueden surgir:</span><span class="sxs-lookup"><span data-stu-id="b2618-203">Here are a few ways you can troubleshoot certain problems that you might run into:</span></span>

1. <span data-ttu-id="b2618-204">Para obtener las características de edición de código de Ionide F# , los archivos deben guardarse en el disco y dentro de una carpeta que esté abierta en el área de trabajo Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="b2618-204">To get the code editing features of Ionide, your F# files need to be saved to disk and inside of a folder that is open in the Visual Studio Code workspace.</span></span>
2. <span data-ttu-id="b2618-205">Si ha realizado cambios en el sistema o ha instalado los requisitos previos de Ionide con Visual Studio Code abrir, reinicie Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="b2618-205">If you've made changes to your system or installed Ionide prerequisites with Visual Studio Code open, restart Visual Studio Code.</span></span>
3. <span data-ttu-id="b2618-206">Compruebe que puede usar el F# compilador F# e interactivo desde la línea de comandos sin una ruta de acceso completa.</span><span class="sxs-lookup"><span data-stu-id="b2618-206">Check that you can use the F# compiler and F# interactive from the command line without a fully-qualified path.</span></span> <span data-ttu-id="b2618-207">Puede `fsc` hacerlo escribiendo en una línea de comandos para el `fsi` F# compilador y, o `fsharpi` bien para las F# herramientas visuales en Windows y mono en Mac/Linux, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="b2618-207">You can do so by typing `fsc` in a command line for the F# compiler, and `fsi` or `fsharpi` for the Visual F# tools on Windows and Mono on Mac/Linux, respectively.</span></span>
4. <span data-ttu-id="b2618-208">Si tiene caracteres no válidos en los directorios del proyecto, es posible que Ionide no funcione.</span><span class="sxs-lookup"><span data-stu-id="b2618-208">If you have invalid characters in your project directories, Ionide might not work.</span></span>  <span data-ttu-id="b2618-209">Cambie el nombre de los directorios del proyecto si éste es el caso.</span><span class="sxs-lookup"><span data-stu-id="b2618-209">Rename your project directories if this is the case.</span></span>
5. <span data-ttu-id="b2618-210">Si no funciona ninguno de los comandos de Ionide, compruebe los enlaces de la [Visual Studio Code](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) para ver si se están reemplazando por accidente.</span><span class="sxs-lookup"><span data-stu-id="b2618-210">If none of the Ionide commands are working, check your [Visual Studio Code keybindings](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) to see if you're overriding them by accident.</span></span>
6. <span data-ttu-id="b2618-211">Si Ionide se ha interrumpido en el equipo y ninguno de los anteriores ha solucionado el problema, `ionide-fsharp` intente quitar el directorio en la máquina y vuelva a instalar el conjunto de complementos.</span><span class="sxs-lookup"><span data-stu-id="b2618-211">If Ionide is broken on your machine and none of the above has fixed your problem, try removing the `ionide-fsharp` directory on your machine and reinstall the plugin suite.</span></span>

<span data-ttu-id="b2618-212">Ionide es un proyecto de código abierto creado y mantenido por miembros de F# la comunidad.</span><span class="sxs-lookup"><span data-stu-id="b2618-212">Ionide is an open source project built and maintained by members of the F# community.</span></span> <span data-ttu-id="b2618-213">Informe de los problemas y no dude en contribuir en [el Ionide-VSCode: Repositorio](https://github.com/ionide/ionide-vscode-fsharp)de github de FSharp.</span><span class="sxs-lookup"><span data-stu-id="b2618-213">Please report issues and feel free to contribute at the [Ionide-VSCode: FSharp GitHub repository](https://github.com/ionide/ionide-vscode-fsharp).</span></span>

<span data-ttu-id="b2618-214">Si tiene un problema para notificar, siga [las instrucciones para obtener los registros que se van a usar al informar de un problema](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting).</span><span class="sxs-lookup"><span data-stu-id="b2618-214">If you have an issue to report, please follow [the instructions for getting logs to use when reporting an issue](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting).</span></span>

<span data-ttu-id="b2618-215">También puede solicitar más ayuda de la comunidad y F# los desarrolladores de Ionide en el [canal de Gitter de Ionide](https://gitter.im/ionide/ionide-project).</span><span class="sxs-lookup"><span data-stu-id="b2618-215">You can also ask for further help from the Ionide developers and F# community in the [Ionide Gitter channel](https://gitter.im/ionide/ionide-project).</span></span>

## <a name="next-steps"></a><span data-ttu-id="b2618-216">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="b2618-216">Next steps</span></span>

<span data-ttu-id="b2618-217">Para obtener más información F# acerca de y las características del lenguaje, consulte el [paseo F# ](../tour.md)por.</span><span class="sxs-lookup"><span data-stu-id="b2618-217">To learn more about F# and the features of the language, check out [Tour of F#](../tour.md).</span></span>
