---
title: Introducción a F# en Visual Studio Code
description: Aprenda a usar F# con Visual Studio Code y Ionide complemento suite.
ms.date: 12/23/2018
ms.openlocfilehash: 34802551bf4e34abb5aa0130643f32dbce68f1b2
ms.sourcegitcommit: 3b9b7ae6771712337d40374d2fef6b25b0d53df6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/04/2019
ms.locfileid: "54029559"
---
# <a name="get-started-with-f-in-visual-studio-code"></a><span data-ttu-id="da0cc-103">Introducción a F# en Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="da0cc-103">Get Started with F# in Visual Studio Code</span></span>

<span data-ttu-id="da0cc-104">Puede escribir F# en [Visual Studio Code](https://code.visualstudio.com) con el [Ionide complemento](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp) para obtener una gran experiencia de entorno de desarrollo integrado (IDE) ligero en varias plataformas, con IntelliSense y el código básico refactorizaciones.</span><span class="sxs-lookup"><span data-stu-id="da0cc-104">You can write F# in [Visual Studio Code](https://code.visualstudio.com) with the [Ionide plugin](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp) to get a great cross-platform, lightweight Integrated Development Environment (IDE) experience with IntelliSense and basic code refactorings.</span></span> <span data-ttu-id="da0cc-105">Visite [Ionide.io](http://ionide.io) para obtener más información sobre el complemento.</span><span class="sxs-lookup"><span data-stu-id="da0cc-105">Visit [Ionide.io](http://ionide.io) to learn more about the plugin.</span></span>

<span data-ttu-id="da0cc-106">Para empezar, asegúrese de que tiene [ F# y ha instalado correctamente el complemento de Ionide](install-fsharp.md#install-f-with-visual-studio-code).</span><span class="sxs-lookup"><span data-stu-id="da0cc-106">To begin, ensure that you have [F# and the Ionide plugin correctly installed](install-fsharp.md#install-f-with-visual-studio-code).</span></span>

## <a name="creating-your-first-project-with-ionide"></a><span data-ttu-id="da0cc-107">Crear su primer proyecto con Ionide</span><span class="sxs-lookup"><span data-stu-id="da0cc-107">Creating your first project with Ionide</span></span>

<span data-ttu-id="da0cc-108">Para crear un nuevo F# del proyecto, abra Visual Studio Code en una nueva carpeta (puede denominarlo que prefiera).</span><span class="sxs-lookup"><span data-stu-id="da0cc-108">To create a new F# project, open Visual Studio Code in a new folder (you can name it whatever you like).</span></span>

<span data-ttu-id="da0cc-109">A continuación, abra la paleta de comandos (**Vista > Paleta de comandos**) y escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="da0cc-109">Next, open the command palette (**View > Command Palette**) and type the following:</span></span>

```
> F# new project
```

<span data-ttu-id="da0cc-110">Esto funciona con el [FALSIFICAR](https://github.com/fsharp-editing/Forge) proyecto.</span><span class="sxs-lookup"><span data-stu-id="da0cc-110">This is powered by the [FORGE](https://github.com/fsharp-editing/Forge) project.</span></span>

> [!NOTE]
> <span data-ttu-id="da0cc-111">Si no ve las opciones de plantilla, pruebe a actualizar las plantillas ejecutando el siguiente comando en la paleta de comandos: `>F#: Refresh Project Templates`.</span><span class="sxs-lookup"><span data-stu-id="da0cc-111">If you don't see template options, try refreshing templates by running the following command in the Command Palette: `>F#: Refresh Project Templates`.</span></span>

<span data-ttu-id="da0cc-112">Seleccione "F#: Nuevo proyecto"pulsando **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="da0cc-112">Select "F#: New Project" by hitting **Enter**.</span></span> <span data-ttu-id="da0cc-113">Esto le lleva al paso siguiente, que es para seleccionar una plantilla de proyecto.</span><span class="sxs-lookup"><span data-stu-id="da0cc-113">This takes you to the next step, which is for selecting a project template.</span></span>

<span data-ttu-id="da0cc-114">Elegir el `classlib` plantilla del sistema y presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="da0cc-114">Pick the `classlib` template and hit **Enter**.</span></span>

<span data-ttu-id="da0cc-115">A continuación, seleccione un directorio para crear el proyecto en.</span><span class="sxs-lookup"><span data-stu-id="da0cc-115">Next, pick a directory to create the project in.</span></span> <span data-ttu-id="da0cc-116">Si se deja en blanco, usa el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="da0cc-116">If you leave it blank, it uses the current directory.</span></span>

<span data-ttu-id="da0cc-117">Por último, nombre del proyecto en el paso final.</span><span class="sxs-lookup"><span data-stu-id="da0cc-117">Finally, name your project in the final step.</span></span> <span data-ttu-id="da0cc-118">F#usa [mayúsculas y minúsculas Pascal](http://c2.com/cgi/wiki?PascalCase) los nombres de proyecto.</span><span class="sxs-lookup"><span data-stu-id="da0cc-118">F# uses [Pascal case](http://c2.com/cgi/wiki?PascalCase) for project names.</span></span> <span data-ttu-id="da0cc-119">Este artículo se usa `ClassLibraryDemo` como el nombre.</span><span class="sxs-lookup"><span data-stu-id="da0cc-119">This article uses `ClassLibraryDemo` as the name.</span></span> <span data-ttu-id="da0cc-120">Una vez que haya escrito el nombre que desee para el proyecto, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="da0cc-120">Once you've entered the name you want for your project, hit **Enter**.</span></span>

<span data-ttu-id="da0cc-121">Si ha seguido el paso anterior, debería obtener Visual Studio código de área de trabajo en el lado izquierdo que aparezca con el siguiente:</span><span class="sxs-lookup"><span data-stu-id="da0cc-121">If you followed the previous step, you should get the Visual Studio Code Workspace on the left-hand side to appear with the following:</span></span>

1. <span data-ttu-id="da0cc-122">El F# propio proyecto, debajo de la directiva el `ClassLibraryDemo` carpeta.</span><span class="sxs-lookup"><span data-stu-id="da0cc-122">The F# project itself, underneath the `ClassLibraryDemo` folder.</span></span>
2. <span data-ttu-id="da0cc-123">Para agregar paquetes a través de la estructura de directorio correcto [ `Paket` ](https://fsprojects.github.io/Paket/).</span><span class="sxs-lookup"><span data-stu-id="da0cc-123">The correct directory structure for adding packages via [`Paket`](https://fsprojects.github.io/Paket/).</span></span>
3. <span data-ttu-id="da0cc-124">Una multiplataforma crear secuencia de comandos con [ `FAKE` ](https://fsharp.github.io/FAKE/).</span><span class="sxs-lookup"><span data-stu-id="da0cc-124">A cross-platform build script with [`FAKE`](https://fsharp.github.io/FAKE/).</span></span>
4. <span data-ttu-id="da0cc-125">El `paket.exe` ejecutable que puede capturar paquetes y resolver las dependencias para usted.</span><span class="sxs-lookup"><span data-stu-id="da0cc-125">The `paket.exe` executable that can fetch packages and resolve dependencies for you.</span></span>
5. <span data-ttu-id="da0cc-126">Un `.gitignore` archivo si desea agregar este proyecto al control de código fuente basados en Git.</span><span class="sxs-lookup"><span data-stu-id="da0cc-126">A `.gitignore` file if you wish to add this project to Git-based source control.</span></span>

## <a name="writing-some-code"></a><span data-ttu-id="da0cc-127">Escribir código</span><span class="sxs-lookup"><span data-stu-id="da0cc-127">Writing some code</span></span>

<span data-ttu-id="da0cc-128">Abra el *ClassLibraryDemo* carpeta.</span><span class="sxs-lookup"><span data-stu-id="da0cc-128">Open the *ClassLibraryDemo* folder.</span></span>  <span data-ttu-id="da0cc-129">Debería ver los archivos siguientes:</span><span class="sxs-lookup"><span data-stu-id="da0cc-129">You should see the following files:</span></span>

1. <span data-ttu-id="da0cc-130">`ClassLibraryDemo.fs`, un F# archivo de implementación con una clase definida.</span><span class="sxs-lookup"><span data-stu-id="da0cc-130">`ClassLibraryDemo.fs`, an F# implementation file with a class defined.</span></span>
2. <span data-ttu-id="da0cc-131">`ClassLibraryDemo.fsproj`, un F# archivo de proyecto utilizado para compilar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="da0cc-131">`ClassLibraryDemo.fsproj`, an F# project file used to build this project.</span></span>
3. <span data-ttu-id="da0cc-132">`Script.fsx`, un F# archivo de script que se carga el archivo de origen.</span><span class="sxs-lookup"><span data-stu-id="da0cc-132">`Script.fsx`, an F# script file that loads the source file.</span></span>
4. <span data-ttu-id="da0cc-133">`paket.references`, un archivo Paket que especifica las dependencias del proyecto.</span><span class="sxs-lookup"><span data-stu-id="da0cc-133">`paket.references`, a Paket file that specifies the project dependencies.</span></span>

<span data-ttu-id="da0cc-134">Abra `Script.fsx`y agregue el código siguiente al final de la misma:</span><span class="sxs-lookup"><span data-stu-id="da0cc-134">Open `Script.fsx`, and add the following code at the end of it:</span></span>

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx)]

<span data-ttu-id="da0cc-135">Esta función convierte una palabra en un formulario de [Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin).</span><span class="sxs-lookup"><span data-stu-id="da0cc-135">This function converts a word to a form of [Pig Latin](https://en.wikipedia.org/wiki/Pig_Latin).</span></span> <span data-ttu-id="da0cc-136">El siguiente paso es evaluar mediante F# interactivo (FSI).</span><span class="sxs-lookup"><span data-stu-id="da0cc-136">The next step is to evaluate it using F# Interactive (FSI).</span></span>

<span data-ttu-id="da0cc-137">Resaltar toda la función (debe ser 11 líneas de largo).</span><span class="sxs-lookup"><span data-stu-id="da0cc-137">Highlight the entire function (it should be 11 lines long).</span></span> <span data-ttu-id="da0cc-138">Una vez que se resalta, mantenga el **Alt** clave y posicionamiento **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="da0cc-138">Once it is highlighted, hold the **Alt** key and hit **Enter**.</span></span> <span data-ttu-id="da0cc-139">Verá una ventana emergente a continuación, y debe aparecer algo parecido a esto:</span><span class="sxs-lookup"><span data-stu-id="da0cc-139">You'll notice a window pop up below, and it should show something like this:</span></span>

![Ejemplo de F# interactivo de salida con Ionide](media/getting-started-vscode/vscode-fsi.png)

<span data-ttu-id="da0cc-141">Esto hizo tres cosas:</span><span class="sxs-lookup"><span data-stu-id="da0cc-141">This did three things:</span></span>

1. <span data-ttu-id="da0cc-142">Inició el proceso FSI.</span><span class="sxs-lookup"><span data-stu-id="da0cc-142">It started the FSI process.</span></span>
2. <span data-ttu-id="da0cc-143">El código resaltado que envíe a través del proceso FSI.</span><span class="sxs-lookup"><span data-stu-id="da0cc-143">It sent the code you highlighted over the FSI process.</span></span>
3. <span data-ttu-id="da0cc-144">El proceso FSI evalúa el código que envían a través.</span><span class="sxs-lookup"><span data-stu-id="da0cc-144">The FSI process evaluated the code you sent over.</span></span>

<span data-ttu-id="da0cc-145">Debido a que era lo que se envía a través de un [función](../language-reference/functions/index.md), ahora puede llamar a esa función con FSI!</span><span class="sxs-lookup"><span data-stu-id="da0cc-145">Because what you sent over was a [function](../language-reference/functions/index.md), you can now call that function with FSI!</span></span> <span data-ttu-id="da0cc-146">En la ventana interactiva, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="da0cc-146">In the interactive window, type the following:</span></span>

```fsharp
toPigLatin "banana";;
```

<span data-ttu-id="da0cc-147">Debería ver el resultado siguiente:</span><span class="sxs-lookup"><span data-stu-id="da0cc-147">You should see the following result:</span></span>

```fsharp
val it : string = "ananabay"
```

<span data-ttu-id="da0cc-148">Ahora, vamos a probar con una vocal como la primera letra.</span><span class="sxs-lookup"><span data-stu-id="da0cc-148">Now, let's try with a vowel as the first letter.</span></span> <span data-ttu-id="da0cc-149">Escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="da0cc-149">Enter the following:</span></span>

```fsharp
toPigLatin "apple";;
```

<span data-ttu-id="da0cc-150">Debería ver el resultado siguiente:</span><span class="sxs-lookup"><span data-stu-id="da0cc-150">You should see the following result:</span></span>

```fsharp
val it : string = "appleyay"
```

<span data-ttu-id="da0cc-151">La función parece que funciona según lo previsto.</span><span class="sxs-lookup"><span data-stu-id="da0cc-151">The function appears to be working as expected.</span></span> <span data-ttu-id="da0cc-152">Enhorabuena, acaba de escribir su primer F# funcionan en Visual Studio Code y se evalúa con FSI!</span><span class="sxs-lookup"><span data-stu-id="da0cc-152">Congratulations, you just wrote your first F# function in Visual Studio Code and evaluated it with FSI!</span></span>

> [!NOTE]
> <span data-ttu-id="da0cc-153">Como habrá advertido, las líneas en FSI terminan con `;;`.</span><span class="sxs-lookup"><span data-stu-id="da0cc-153">As you may have noticed, the lines in FSI are terminated with `;;`.</span></span> <span data-ttu-id="da0cc-154">Esto es porque FSI le permite escribir varias líneas.</span><span class="sxs-lookup"><span data-stu-id="da0cc-154">This is because FSI allows you to enter multiple lines.</span></span> <span data-ttu-id="da0cc-155">El `;;` al final sabrá FSI cuando finalice el código.</span><span class="sxs-lookup"><span data-stu-id="da0cc-155">The `;;` at the end lets FSI know when the code is finished.</span></span>

## <a name="explaining-the-code"></a><span data-ttu-id="da0cc-156">Que explica el código</span><span class="sxs-lookup"><span data-stu-id="da0cc-156">Explaining the code</span></span>

<span data-ttu-id="da0cc-157">Si no está seguro acerca de lo que realmente está haciendo el código, este es un paso a paso.</span><span class="sxs-lookup"><span data-stu-id="da0cc-157">If you're not sure about what the code is actually doing, here's a step-by-step.</span></span>

<span data-ttu-id="da0cc-158">Como puede ver, `toPigLatin` es una función que toma una palabra como entrada y lo convierte en una representación de Pig Latin de esa palabra.</span><span class="sxs-lookup"><span data-stu-id="da0cc-158">As you can see, `toPigLatin` is a function that takes a word as its input and converts it to a Pig-Latin representation of that word.</span></span> <span data-ttu-id="da0cc-159">Las reglas para esto son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="da0cc-159">The rules for this are as follows:</span></span>

<span data-ttu-id="da0cc-160">Si el primer carácter de una palabra comienza con una vocal, agregue "¡viva" al final de la palabra.</span><span class="sxs-lookup"><span data-stu-id="da0cc-160">If the first character in a word starts with a vowel, add "yay" to the end of the word.</span></span> <span data-ttu-id="da0cc-161">Si no se inicia con una vocal, mover ese primer carácter al final de la palabra y "ay" Agregar a ella.</span><span class="sxs-lookup"><span data-stu-id="da0cc-161">If it doesn't start with a vowel, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="da0cc-162">Es podrán que haya observado lo siguiente en FSI:</span><span class="sxs-lookup"><span data-stu-id="da0cc-162">You may have noticed the following in FSI:</span></span>

```fsharp
val toPigLatin : word:string -> string
```

<span data-ttu-id="da0cc-163">Esto indica que `toPigLatin` es una función que toma un `string` como entrada (denominado `word`) y devuelve otra `string`.</span><span class="sxs-lookup"><span data-stu-id="da0cc-163">This states that `toPigLatin` is a function that takes in a `string` as input (called `word`), and returns another `string`.</span></span> <span data-ttu-id="da0cc-164">Esto se conoce como el [signatura de tipo de la función](https://fsharpforfunandprofit.com/posts/function-signatures/), una parte fundamental de F# que es clave para comprender F# código.</span><span class="sxs-lookup"><span data-stu-id="da0cc-164">This is known as the [type signature of the function](https://fsharpforfunandprofit.com/posts/function-signatures/), a fundamental piece of F# that's key to understanding F# code.</span></span> <span data-ttu-id="da0cc-165">También podrá observar si mantiene el mouse sobre la función en Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="da0cc-165">You'll also notice this if you hover over the function in Visual Studio Code.</span></span>

<span data-ttu-id="da0cc-166">En el cuerpo de la función, verá dos partes distintas:</span><span class="sxs-lookup"><span data-stu-id="da0cc-166">In the body of the function, you'll notice two distinct parts:</span></span>

1. <span data-ttu-id="da0cc-167">Una función interna, llamada `isVowel`, que determina si un carácter determinado (`c`) es una vocal comprobando si coincide con uno de los patrones proporcionados a través de [coincidencia de patrones](../language-reference/pattern-matching.md):</span><span class="sxs-lookup"><span data-stu-id="da0cc-167">An inner function, called `isVowel`, that determines if a given character (`c`) is a vowel by checking if it matches one of the provided patterns via [Pattern Matching](../language-reference/pattern-matching.md):</span></span>

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L2-L6)]

2. <span data-ttu-id="da0cc-168">Un [ `if..then..else` ](../language-reference/conditional-expressions-if-then-else.md) expresión que comprueba si el primer carácter sea una vocal y construcciones un retorno de valor fuera de los caracteres de entrada en función de si el primer carácter o no era una vocal:</span><span class="sxs-lookup"><span data-stu-id="da0cc-168">An [`if..then..else`](../language-reference/conditional-expressions-if-then-else.md) expression that checks if the first character is a vowel, and constructs a return value out of the input characters based on if the first character was a vowel or not:</span></span>

   [!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/to-pig-latin.fsx#L8-L11)]

<span data-ttu-id="da0cc-169">El flujo de `toPigLatin` por tanto, es:</span><span class="sxs-lookup"><span data-stu-id="da0cc-169">The flow of `toPigLatin` is thus:</span></span>

<span data-ttu-id="da0cc-170">Compruebe si el primer carácter de la palabra de entrada sea una vocal.</span><span class="sxs-lookup"><span data-stu-id="da0cc-170">Check if the first character of the input word is a vowel.</span></span> <span data-ttu-id="da0cc-171">Si es así, adjuntar "¡viva" al final de la palabra.</span><span class="sxs-lookup"><span data-stu-id="da0cc-171">If it is, attach "yay" to the end of the word.</span></span> <span data-ttu-id="da0cc-172">En caso contrario, mueva ese primer carácter al final de la palabra y "ay" Agregar a ella.</span><span class="sxs-lookup"><span data-stu-id="da0cc-172">Otherwise, move that first character to the end of the word and add "ay" to it.</span></span>

<span data-ttu-id="da0cc-173">Hay una última cosa a tener en cuenta sobre esto: no hay ninguna instrucción explícita para devolver de la función, a diferencia de muchos otros lenguajes ahí.</span><span class="sxs-lookup"><span data-stu-id="da0cc-173">There's one final thing to notice about this: there's no explicit instruction to return from the function, unlike many other languages out there.</span></span> <span data-ttu-id="da0cc-174">Esto es porque F# está basado en la expresión, y la última expresión en el cuerpo de una función es el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="da0cc-174">This is because F# is Expression-based, and the last expression in the body of a function is the return value.</span></span> <span data-ttu-id="da0cc-175">Dado que `if..then..else` es en sí mismo una expresión, el cuerpo de la `then` bloque o en el cuerpo de la `else` bloque se devolverán según el valor de entrada.</span><span class="sxs-lookup"><span data-stu-id="da0cc-175">Because `if..then..else` is itself an expression, the body of the `then` block or the body of the `else` block will be returned depending on the input value.</span></span>

## <a name="moving-your-script-code-into-the-implementation-file"></a><span data-ttu-id="da0cc-176">Migración de código de script en el archivo de implementación</span><span class="sxs-lookup"><span data-stu-id="da0cc-176">Moving your script code into the implementation file</span></span>

<span data-ttu-id="da0cc-177">Las secciones anteriores de este artículo muestran un primer paso común escrito F# código: escribir una función inicial y se ejecuta interactivamente con FSI.</span><span class="sxs-lookup"><span data-stu-id="da0cc-177">The previous sections in this article demonstrated a common first step in writing F# code: writing an initial function and executing it interactively with FSI.</span></span> <span data-ttu-id="da0cc-178">Esto se conoce como el desarrollo controlado por REPL, donde [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) es el acrónimo "Read-Evaluate-Print Loop".</span><span class="sxs-lookup"><span data-stu-id="da0cc-178">This is known as REPL-driven development, where [REPL](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop) stands for "Read-Evaluate-Print Loop".</span></span> <span data-ttu-id="da0cc-179">Es una excelente manera de experimentar con la funcionalidad hasta que haya algo funcione.</span><span class="sxs-lookup"><span data-stu-id="da0cc-179">It's a great way to experiment with functionality until you have something working.</span></span>

<span data-ttu-id="da0cc-180">El siguiente paso en el desarrollo controlado por REPL es mover el código de trabajo en un F# archivo de implementación.</span><span class="sxs-lookup"><span data-stu-id="da0cc-180">The next step in REPL-driven development is to move working code into an F# implementation file.</span></span> <span data-ttu-id="da0cc-181">A continuación, se puede compilar si la F# compilador en un ensamblado que se puede ejecutar.</span><span class="sxs-lookup"><span data-stu-id="da0cc-181">It can then be compiled by the F# compiler into an assembly that can be executed.</span></span>

<span data-ttu-id="da0cc-182">Para comenzar, abra `ClassLibraryDemo.fs`.</span><span class="sxs-lookup"><span data-stu-id="da0cc-182">To begin, open `ClassLibraryDemo.fs`.</span></span>  <span data-ttu-id="da0cc-183">Observará que algún código ya está en no existe.</span><span class="sxs-lookup"><span data-stu-id="da0cc-183">You'll notice that some code is already in there.</span></span> <span data-ttu-id="da0cc-184">Siga adelante y eliminar la definición de clase, pero asegúrese de dejar el [ `namespace` ](../language-reference/namespaces.md) declaración en la parte superior.</span><span class="sxs-lookup"><span data-stu-id="da0cc-184">Go ahead and delete the class definition, but make sure to leave the [`namespace`](../language-reference/namespaces.md) declaration at the top.</span></span>

<span data-ttu-id="da0cc-185">A continuación, cree un nuevo [ `module` ](../language-reference/modules.md) llamado `PigLatin` y copie el `toPigLatin` función como tal en él:</span><span class="sxs-lookup"><span data-stu-id="da0cc-185">Next, create a new [`module`](../language-reference/modules.md) called `PigLatin` and copy the `toPigLatin` function into it as such:</span></span>

[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/pig-latin.fs#L1-L14)]

<span data-ttu-id="da0cc-186">A continuación, abra el `Script.fsx` archivo nuevo y eliminar toda la `toPigLatin` funcionando, pero asegúrese de mantener las dos líneas siguientes en el archivo:</span><span class="sxs-lookup"><span data-stu-id="da0cc-186">Next, open the `Script.fsx` file again, and delete the entire `toPigLatin` function, but make sure to keep the following two lines in the file:</span></span>

```fsharp
#load "ClassLibraryDemo.fs"
open ClassLibraryDemo
```
<span data-ttu-id="da0cc-187">Seleccione ambas líneas de texto y presione Alt + Intro para ejecutar estas líneas en FSI.</span><span class="sxs-lookup"><span data-stu-id="da0cc-187">Select both lines of text and press Alt+Enter to execute these lines in FSI.</span></span> <span data-ttu-id="da0cc-188">Estos cargará el contenido de la biblioteca de Pig Latin en el proceso FSI y `open` el `ClassLibraryDemo` espacio de nombres para que tengan acceso a la funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="da0cc-188">These will load the contents of the Pig Latin library into the FSI process and `open` the `ClassLibraryDemo` namespace so that you have access to the functionality.</span></span>

<span data-ttu-id="da0cc-189">A continuación, en la ventana FSI, llame a la función con el `PigLatin` módulo que definió anteriormente:</span><span class="sxs-lookup"><span data-stu-id="da0cc-189">Next, in the FSI window, call the function with the `PigLatin` module that you defined earlier:</span></span>

```
> PigLatin.toPigLatin "banana";;
val it : string = "ananabay"
> PigLatin.toPigLatin "apple";;
val it : string = "appleyay"
```

<span data-ttu-id="da0cc-190">Correcto</span><span class="sxs-lookup"><span data-stu-id="da0cc-190">Success!</span></span> <span data-ttu-id="da0cc-191">Obtener los mismos resultados como antes, pero ahora se cargan desde un F# archivo de implementación.</span><span class="sxs-lookup"><span data-stu-id="da0cc-191">You get the same results as before, but now loaded from an F# implementation file.</span></span> <span data-ttu-id="da0cc-192">La principal diferencia es que F# archivos de código fuente se compilan en ensamblados que se pueden ejecutar en cualquier lugar, no solo en FSI.</span><span class="sxs-lookup"><span data-stu-id="da0cc-192">The major difference here is that F# source files are compiled into assemblies that can be executed anywhere, not just in FSI.</span></span>

## <a name="summary"></a><span data-ttu-id="da0cc-193">Resumen</span><span class="sxs-lookup"><span data-stu-id="da0cc-193">Summary</span></span>

<span data-ttu-id="da0cc-194">En este artículo, ha aprendido:</span><span class="sxs-lookup"><span data-stu-id="da0cc-194">In this article, you've learned:</span></span>

1. <span data-ttu-id="da0cc-195">Cómo configurar Visual Studio Code con Ionide.</span><span class="sxs-lookup"><span data-stu-id="da0cc-195">How to set up Visual Studio Code with Ionide.</span></span>
2. <span data-ttu-id="da0cc-196">Cómo crear su primer F# proyecto con Ionide.</span><span class="sxs-lookup"><span data-stu-id="da0cc-196">How to create your first F# project with Ionide.</span></span>
3. <span data-ttu-id="da0cc-197">Cómo usar F# secuencias de comandos para escribir su primer F# funcionar en Ionide y, a continuación, ejecútelo de FSI.</span><span class="sxs-lookup"><span data-stu-id="da0cc-197">How to use F# Scripting to write your first F# function in Ionide and then execute it in FSI.</span></span>
4. <span data-ttu-id="da0cc-198">Cómo migrar el código de script a F# de origen y, a continuación, invocar dicho código desde FSI.</span><span class="sxs-lookup"><span data-stu-id="da0cc-198">How to migrate your script code to F# source and then call that code from FSI.</span></span>

<span data-ttu-id="da0cc-199">Ahora está equipado para escribir mucho más F# del código mediante Visual Studio Code y Ionide.</span><span class="sxs-lookup"><span data-stu-id="da0cc-199">You're now equipped to write much more F# code using Visual Studio Code and Ionide.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="da0cc-200">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="da0cc-200">Troubleshooting</span></span>

<span data-ttu-id="da0cc-201">Estas son algunas maneras de que solucionar ciertos problemas que pueden surgir:</span><span class="sxs-lookup"><span data-stu-id="da0cc-201">Here are a few ways you can troubleshoot certain problems that you might run into:</span></span>

1. <span data-ttu-id="da0cc-202">Para obtener el código en la edición de las características de Ionide, su F# los archivos deben guardarse en el disco y dentro de una carpeta que está abierta en el área de trabajo de Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="da0cc-202">To get the code editing features of Ionide, your F# files need to be saved to disk and inside of a folder that is open in the Visual Studio Code workspace.</span></span>
2. <span data-ttu-id="da0cc-203">Si ha realizado cambios en el sistema o instalar requisitos previos de Ionide con código de Visual Studio abierta, reinicie Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="da0cc-203">If you've made changes to your system or installed Ionide prerequisites with Visual Studio Code open, restart Visual Studio Code.</span></span>
3. <span data-ttu-id="da0cc-204">Compruebe que puede usar el F# compilador y F# interactivo desde la línea de comandos sin una ruta de acceso completa.</span><span class="sxs-lookup"><span data-stu-id="da0cc-204">Check that you can use the F# compiler and F# interactive from the command line without a fully-qualified path.</span></span> <span data-ttu-id="da0cc-205">Puede hacerlo escribiendo `fsc` en una línea de comandos para el F# compilador, y `fsi` o `fsharpi` para el objeto Visual F# herramientas en Windows y Mono en Mac/Linux, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="da0cc-205">You can do so by typing `fsc` in a command line for the F# compiler, and `fsi` or `fsharpi` for the Visual F# tools on Windows and Mono on Mac/Linux, respectively.</span></span>
4. <span data-ttu-id="da0cc-206">Si tiene caracteres no válidos en los directorios del proyecto, Ionide podría no funcionar.</span><span class="sxs-lookup"><span data-stu-id="da0cc-206">If you have invalid characters in your project directories, Ionide might not work.</span></span>  <span data-ttu-id="da0cc-207">Cambiar el nombre de los directorios de proyecto si este es el caso.</span><span class="sxs-lookup"><span data-stu-id="da0cc-207">Rename your project directories if this is the case.</span></span>
5. <span data-ttu-id="da0cc-208">Si ninguno de los comandos Ionide está trabajando, compruebe su [enlaces de teclado de Visual Studio Code](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) para ver si se está reemplazando por accidente.</span><span class="sxs-lookup"><span data-stu-id="da0cc-208">If none of the Ionide commands are working, check your [Visual Studio Code keybindings](https://code.visualstudio.com/docs/customization/keybindings#_customizing-shortcuts) to see if you're overriding them by accident.</span></span>
6. <span data-ttu-id="da0cc-209">Si Ionide se divide en el equipo y ninguno de los anteriores ha se ha corregido el problema, pruebe a quitar el `ionide-fsharp` directorio en el equipo y vuelva a instalar el conjunto de complemento.</span><span class="sxs-lookup"><span data-stu-id="da0cc-209">If Ionide is broken on your machine and none of the above has fixed your problem, try removing the `ionide-fsharp` directory on your machine and reinstall the plugin suite.</span></span>

<span data-ttu-id="da0cc-210">Ionide es un proyecto de código abierto creado y mantenido por los miembros de la F# Comunidad.</span><span class="sxs-lookup"><span data-stu-id="da0cc-210">Ionide is an open source project built and maintained by members of the F# community.</span></span> <span data-ttu-id="da0cc-211">Por favor, notificar problemas y no dude en contribuir en el [Ionide VSCode: Repositorio de FSharp GitHub](https://github.com/ionide/ionide-vscode-fsharp).</span><span class="sxs-lookup"><span data-stu-id="da0cc-211">Please report issues and feel free to contribute at the [Ionide-VSCode: FSharp GitHub repository](https://github.com/ionide/ionide-vscode-fsharp).</span></span>

<span data-ttu-id="da0cc-212">Si tiene un problema al informe, siga [las instrucciones para obtener los registros que se usará al informar de un problema](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting).</span><span class="sxs-lookup"><span data-stu-id="da0cc-212">If you have an issue to report, please follow [the instructions for getting logs to use when reporting an issue](https://github.com/ionide/ionide-vscode-fsharp#how-to-get-logs-for-debugging--issue-reporting).</span></span>

<span data-ttu-id="da0cc-213">También puede pedir ayuda adicional de los desarrolladores Ionide y F# Comunidad en el [Ionide Gitter canal](https://gitter.im/ionide/ionide-project).</span><span class="sxs-lookup"><span data-stu-id="da0cc-213">You can also ask for further help from the Ionide developers and F# community in the [Ionide Gitter channel](https://gitter.im/ionide/ionide-project).</span></span>

## <a name="next-steps"></a><span data-ttu-id="da0cc-214">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="da0cc-214">Next steps</span></span>

<span data-ttu-id="da0cc-215">Para obtener más información sobre F# y las características del lenguaje, eche un vistazo [paseo F# ](../tour.md).</span><span class="sxs-lookup"><span data-stu-id="da0cc-215">To learn more about F# and the features of the language, check out [Tour of F#](../tour.md).</span></span>
