---
title: 'Empezar a trabajar con F # en Visual Studio para Mac'
description: "Obtenga información acerca de cómo usar F # con Visual Studio para Mac."
keywords: "visual f#, f#, programación funcional"
author: mizzle-mo
ms.author: phcart
ms.date: 02/13/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 8db75596-19a9-4eda-b20d-a12d517c8cc1
ms.openlocfilehash: beee874e3a549531b520d4ac2150bc10dcab7725
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="get-started-with-f-in-visual-studio-for-mac"></a><span data-ttu-id="4237d-104">Empezar a trabajar con F # en Visual Studio para Mac</span><span class="sxs-lookup"><span data-stu-id="4237d-104">Get started with F# in Visual Studio for Mac</span></span>

<span data-ttu-id="4237d-105">F # y las herramientas de Visual F # se admiten en Visual Studio para Mac IDE.</span><span class="sxs-lookup"><span data-stu-id="4237d-105">F# and the Visual F# tooling are supported in the Visual Studio for Mac IDE.</span></span>  <span data-ttu-id="4237d-106">Para empezar, debe [descargar Visual Studio para Mac](https://www.visualstudio.com/downloads/download-visual-studio-vs), si no lo ha hecho ya.</span><span class="sxs-lookup"><span data-stu-id="4237d-106">To begin, you should [download Visual Studio for Mac](https://www.visualstudio.com/downloads/download-visual-studio-vs), if you haven't already.</span></span>  <span data-ttu-id="4237d-107">En este artículo usa la 2017 de comunidad de Visual Studio para Mac, pero puede usar F # con la versión de su elección.</span><span class="sxs-lookup"><span data-stu-id="4237d-107">This article uses the Visual Studio Community 2017 for Mac, but you can use F# with the version of your choice.</span></span>

## <a name="installing-f"></a><span data-ttu-id="4237d-108">Instalación de F #</span><span class="sxs-lookup"><span data-stu-id="4237d-108">Installing F#</span></span> #

<span data-ttu-id="4237d-109">Después de descargar Visual Studio para Mac, le pedirá que elija qué desea instalar.</span><span class="sxs-lookup"><span data-stu-id="4237d-109">After downloading Visual Studio for Mac, it will prompt you to choose what you want to install.</span></span>  <span data-ttu-id="4237d-110">Para los fines de este artículo se deja los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="4237d-110">For the purposes of this article we will be leaving the defaults.</span></span>  <span data-ttu-id="4237d-111">A diferencia de Visual Studio para Windows, no es necesario instalar específicamente la compatibilidad de F #.</span><span class="sxs-lookup"><span data-stu-id="4237d-111">In contrast to Visual Studio for Windows, you do not need to specifically install F# support.</span></span>  <span data-ttu-id="4237d-112">Presione "Instalar" para continuar.</span><span class="sxs-lookup"><span data-stu-id="4237d-112">Press "Install" to proceed.</span></span>

<span data-ttu-id="4237d-113">Una vez finalizada la instalación, seleccione "Iniciar Visual Studio".</span><span class="sxs-lookup"><span data-stu-id="4237d-113">After the install completes, choose "Start Visual Studio".</span></span>  <span data-ttu-id="4237d-114">También puede iniciar a través de buscador en macOS.</span><span class="sxs-lookup"><span data-stu-id="4237d-114">You can also launch it through Finder on macOS.</span></span>

## <a name="creating-a-console-application"></a><span data-ttu-id="4237d-115">Crear una aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="4237d-115">Creating a console application</span></span>

<span data-ttu-id="4237d-116">Uno de los proyectos en Visual Studio para Mac más básicos es la aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="4237d-116">One of the most basic projects in Visual Studio for Mac is the Console Application.</span></span>  <span data-ttu-id="4237d-117">A continuación le mostramos cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="4237d-117">Here's how to do it.</span></span>  <span data-ttu-id="4237d-118">Una vez abierto Visual Studio para Mac:</span><span class="sxs-lookup"><span data-stu-id="4237d-118">Once Visual Studio for Mac is open:</span></span>

1. <span data-ttu-id="4237d-119">En el **archivo** menú, elija **nueva solución**.</span><span class="sxs-lookup"><span data-stu-id="4237d-119">On the **File** menu, point to **New Solution**.</span></span>

2.  <span data-ttu-id="4237d-120">En el cuadro de diálogo nuevo proyecto, hay 2 plantillas distintas para la aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="4237d-120">In the New Project dialog, there are 2 different templates for Console Application.</span></span>  <span data-ttu-id="4237d-121">Hay uno en otros -> .NET que tenga como destino .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4237d-121">There is one under Other -> .NET which targets the .NET Framework.</span></span>  <span data-ttu-id="4237d-122">La otra plantilla es .NET Core -> aplicación destinada a .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4237d-122">The other template is under .NET Core -> App which targets .NET Core.</span></span>  <span data-ttu-id="4237d-123">Cualquier plantilla debería funcionar con el propósito de este artículo.</span><span class="sxs-lookup"><span data-stu-id="4237d-123">Either template should work for the purpose of this article.</span></span>

3. <span data-ttu-id="4237d-124">En la aplicación de consola, cambiar C# para F # si es necesario.</span><span class="sxs-lookup"><span data-stu-id="4237d-124">Under console app, change C# to F# if needed.</span></span>  <span data-ttu-id="4237d-125">Elija la **siguiente** botón para desplazarse hacia delante.</span><span class="sxs-lookup"><span data-stu-id="4237d-125">Choose the **Next** button to move forward!</span></span>  

4. <span data-ttu-id="4237d-126">Asigne un nombre al proyecto y elija las opciones que desee para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4237d-126">Give your project a name, and choose the options you want for the app.</span></span>  <span data-ttu-id="4237d-127">Observe, el panel de vista previa al lado de la pantalla que muestra la estructura de directorios que se va a crear en función de las opciones seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="4237d-127">Notice, the preview pane to the side of the screen that will show the directory structure that will be created based on the options selected.</span></span>  

5. <span data-ttu-id="4237d-128">Haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="4237d-128">Click **Create**.</span></span>  <span data-ttu-id="4237d-129">Ahora debería ver un proyecto de F # en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="4237d-129">You should now see an F# project in the Solution Explorer.</span></span>

## <a name="writing-your-code"></a><span data-ttu-id="4237d-130">Escribir el código</span><span class="sxs-lookup"><span data-stu-id="4237d-130">Writing your code</span></span>

<span data-ttu-id="4237d-131">Vamos a empezar a escribir código en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="4237d-131">Let's get started by writing some code first.</span></span>  <span data-ttu-id="4237d-132">Asegúrese de que el `Program.fs` archivo está abierto y, a continuación, reemplace el contenido con lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4237d-132">Make sure that the `Program.fs` file is open, and then replace its contents with the following:</span></span>

[!code-fsharp[HelloSquare](../../../samples/snippets/fsharp/getting-started/hello-square.fs)]

<span data-ttu-id="4237d-133">En el ejemplo de código anterior, una función `square` se ha definido que toma una entrada con el nombre `x` y lo multiplica por sí mismo.</span><span class="sxs-lookup"><span data-stu-id="4237d-133">In the previous code sample, a function `square` has been defined which takes an input named `x` and multiplies it by itself.</span></span>  <span data-ttu-id="4237d-134">Dado que F # utiliza [inferencia](../language-reference/type-inference.md), el tipo de `x` no deben especificarse.</span><span class="sxs-lookup"><span data-stu-id="4237d-134">Because F# uses [Type Inference](../language-reference/type-inference.md), the type of `x` doesn't need to be specified.</span></span>  <span data-ttu-id="4237d-135">El compilador de F # entiende los tipos donde la multiplicación es válida y se asignará un tipo a `x` en función de cómo `square` se llama.</span><span class="sxs-lookup"><span data-stu-id="4237d-135">The F# compiler understands the types where multiplication is valid, and will assign a type to `x` based on how `square` is called.</span></span>  <span data-ttu-id="4237d-136">Si mantiene el mouse sobre `square`, debería aparecer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4237d-136">If you hover over `square`, you should see the following:</span></span>

```
val square: x:int -> int
```

<span data-ttu-id="4237d-137">Esto es lo que se conoce como firma de tipo de la función.</span><span class="sxs-lookup"><span data-stu-id="4237d-137">This is what is known as the function's type signature.</span></span>  <span data-ttu-id="4237d-138">Puede leerse como el siguiente: "cuadrado es una función que toma un número entero denominado x y genera un número entero".</span><span class="sxs-lookup"><span data-stu-id="4237d-138">It can be read like this: "Square is a function which takes an integer named x and produces an integer".</span></span>  <span data-ttu-id="4237d-139">Tenga en cuenta que el compilador dio `square` el `int` tipo por ahora - esto es porque no es genérica a través de la multiplicación *todos los* tipos, pero, en su lugar, a través de un conjunto cerrado de tipos, es genérico.</span><span class="sxs-lookup"><span data-stu-id="4237d-139">Note that the compiler gave `square` the `int` type for now - this is because multiplication is not generic across *all* types, but rather is generic across a closed set of types.</span></span>  <span data-ttu-id="4237d-140">El compilador de F # seleccionado `int` en este punto, pero se ajustará la signatura de tipo si se llama a `square` con otro tipo de entrada, como un `float`.</span><span class="sxs-lookup"><span data-stu-id="4237d-140">The F# compiler picked `int` at this point, but it will adjust the type signature if you call `square` with a different input type, such as a `float`.</span></span>

<span data-ttu-id="4237d-141">Otra función, `main`, se define, que se decora con el `EntryPoint` atributo para indicar al compilador de F # ejecución del programa debe empezar por ahí.</span><span class="sxs-lookup"><span data-stu-id="4237d-141">Another function, `main`, is defined, which is decorated with the `EntryPoint` attribute to tell the F# compiler that program execution should start there.</span></span>  <span data-ttu-id="4237d-142">Sigue la misma convención que otro [lenguajes de programación de estilo C](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), donde los argumentos de línea de comandos se pueden pasar a esta función y se devuelve un código entero (normalmente `0`).</span><span class="sxs-lookup"><span data-stu-id="4237d-142">It follows the same convention as other [C-style programming languages](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), where command-line arguments can be passed to this function, and an integer code is returned (typically `0`).</span></span>

<span data-ttu-id="4237d-143">Se encuentra en esta función que se llame a la `square` función con un argumento de `12`.</span><span class="sxs-lookup"><span data-stu-id="4237d-143">It is in this function that we call the `square` function with an argument of `12`.</span></span>  <span data-ttu-id="4237d-144">El compilador de F #, a continuación, asigna el tipo de `square` como `int -> int` (es decir, una función que toma un `int` y genera un `int`).</span><span class="sxs-lookup"><span data-stu-id="4237d-144">The F# compiler then assigns the type of `square` to be `int -> int` (that is, a function which takes an `int` and produces an `int`).</span></span>  <span data-ttu-id="4237d-145">La llamada a `printfn` es una función de impresión con formato que usa una cadena de formato, similar a los lenguajes de programación de estilo C, los parámetros que corresponden a los indicados en la cadena de formato y, a continuación, se imprime el resultado y una nueva línea.</span><span class="sxs-lookup"><span data-stu-id="4237d-145">The call to `printfn` is a formatted printing function which uses a format string, similar to C-style programming languages, parameters which correspond to those specified in the format string, and then prints the result and a new line.</span></span>

## <a name="running-your-code"></a><span data-ttu-id="4237d-146">Ejecución del código</span><span class="sxs-lookup"><span data-stu-id="4237d-146">Running your code</span></span>

<span data-ttu-id="4237d-147">Puede ejecutar el código y ver los resultados, haga clic en **ejecutar** en el menú de nivel superior y, a continuación, **iniciar sin depurar**.</span><span class="sxs-lookup"><span data-stu-id="4237d-147">You can run the code and see results by clicking on **Run** from the top level menu and then **Start Without Debugging**.</span></span>  <span data-ttu-id="4237d-148">Esto ejecutará el programa sin depurar y le permite ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="4237d-148">This will run the program without debugging and allows you to see the results.</span></span>

<span data-ttu-id="4237d-149">Ahora debería aparecer el siguiente imprime en la ventana de consola que aparecieron Visual Studio para Mac:</span><span class="sxs-lookup"><span data-stu-id="4237d-149">You should now see the following printed to the console window that Visual Studio for Mac popped up:</span></span>

```
12 squared is 144!
```

<span data-ttu-id="4237d-150">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="4237d-150">Congratulations!</span></span>  <span data-ttu-id="4237d-151">Ha creado su primer proyecto de F # en Visual Studio para Mac, escribe que una función de F # imprime los resultados de la llamada a esa función y ejecute el proyecto para ver algunos resultados.</span><span class="sxs-lookup"><span data-stu-id="4237d-151">You've created your first F# project in Visual Studio for Mac, written an F# function printed the results of calling that function, and run the project to see some results.</span></span>

## <a name="using-f-interactive"></a><span data-ttu-id="4237d-152">Uso de F # Interactive</span><span class="sxs-lookup"><span data-stu-id="4237d-152">Using F# Interactive</span></span>

<span data-ttu-id="4237d-153">Una de las mejores características de Visual F # conjunto de herramientas en Visual Studio para Mac es la ventana interactiva de F #.</span><span class="sxs-lookup"><span data-stu-id="4237d-153">One of the best features of the Visual F# tooling in Visual Studio for Mac is the F# Interactive Window.</span></span>  <span data-ttu-id="4237d-154">Permite enviar código a través a un proceso donde puede llamar a ese código y ver el resultado de forma interactiva.</span><span class="sxs-lookup"><span data-stu-id="4237d-154">It allows you to send code over to a process where you can call that code and see the result interactively.</span></span>

<span data-ttu-id="4237d-155">Para empezar a usarlo, resalte el `square` función definida en el código.</span><span class="sxs-lookup"><span data-stu-id="4237d-155">To begin using it, highlight the `square` function defined in your code.</span></span>  <span data-ttu-id="4237d-156">A continuación, haga clic en **editar** en el menú de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="4237d-156">Next, click on **Edit** from the top level menu.</span></span>  <span data-ttu-id="4237d-157">A continuación seleccione **Enviar selección a F # Interactive**.</span><span class="sxs-lookup"><span data-stu-id="4237d-157">Next select **Send selection to F# Interactive**.</span></span>  <span data-ttu-id="4237d-158">Esto ejecuta el código en la ventana interactiva de F #.</span><span class="sxs-lookup"><span data-stu-id="4237d-158">This executes the code in the F# Interactive Window.</span></span>  <span data-ttu-id="4237d-159">Como alternativa, puede haga clic con el botón secundario en la selección y elija **Enviar selección a F # Interactive**.</span><span class="sxs-lookup"><span data-stu-id="4237d-159">Alternatively, you can right click on the selection and choose **Send selection to F# Interactive**.</span></span>  <span data-ttu-id="4237d-160">Debe aparecer la ventana interactiva de F # con lo siguiente en él:</span><span class="sxs-lookup"><span data-stu-id="4237d-160">You should see the F# Interactive Window appear with the following in it:</span></span>

```
>

val square : x:int -> int

>
```

<span data-ttu-id="4237d-161">Esto muestra la misma firma de función para el `square` función, que vio anteriormente cuando mantiene el mouse sobre la función.</span><span class="sxs-lookup"><span data-stu-id="4237d-161">This shows the same function signature for the `square` function, which you saw earlier when you hovered over the function.</span></span>  <span data-ttu-id="4237d-162">Dado que `square` es ahora definido en el proceso de F # Interactive, se puede llamar con valores diferentes:</span><span class="sxs-lookup"><span data-stu-id="4237d-162">Because `square` is now defined in the F# Interactive process, you can call it with different values:</span></span>

```
> square 12;;
val it : int = 144
>square 13;;
val it : int = 169
```

<span data-ttu-id="4237d-163">Esto ejecuta la función, se enlaza el resultado a un nuevo nombre `it`y muestra el tipo y el valor de `it`.</span><span class="sxs-lookup"><span data-stu-id="4237d-163">This executes the function, binds the result to a new name `it`, and displays the type and value of `it`.</span></span>  <span data-ttu-id="4237d-164">Tenga en cuenta que debe finalizar cada línea con `;;`.</span><span class="sxs-lookup"><span data-stu-id="4237d-164">Note that you must terminate each line with `;;`.</span></span>  <span data-ttu-id="4237d-165">Se trata cómo F # Interactive sabe cuando finalice la llamada de función.</span><span class="sxs-lookup"><span data-stu-id="4237d-165">This is how F# Interactive knows when your function call is finished.</span></span>  <span data-ttu-id="4237d-166">También puede definir nuevas funciones en F # Interactive:</span><span class="sxs-lookup"><span data-stu-id="4237d-166">You can also define new functions in F# Interactive:</span></span>

```
> let isOdd x = x % 2 <> 0;;

val isOdd : x:int -> bool

> isOdd 12;;
val it : bool = false
```

<span data-ttu-id="4237d-167">Los pasos anteriores, define una nueva función, `isOdd`, que toma un `int` y comprueba si es impar.</span><span class="sxs-lookup"><span data-stu-id="4237d-167">The above defines a new function, `isOdd`, which takes an `int` and checks to see if it's odd!</span></span>  <span data-ttu-id="4237d-168">Puede llamar a esta función para ver lo que devuelve con diferentes entradas.</span><span class="sxs-lookup"><span data-stu-id="4237d-168">You can call this function to see what it returns with different inputs.</span></span>  <span data-ttu-id="4237d-169">Puede llamar a funciones dentro de las llamadas a funciones:</span><span class="sxs-lookup"><span data-stu-id="4237d-169">You can call functions within function calls:</span></span>

```
> isOdd (square 15);;
val it : bool = true
```

<span data-ttu-id="4237d-170">También puede usar el [operador de canalización hacia delante](../language-reference/symbol-and-operator-reference/index.md) debe canalizar el valor en las dos funciones:</span><span class="sxs-lookup"><span data-stu-id="4237d-170">You can also use the [pipe-forward operator](../language-reference/symbol-and-operator-reference/index.md) to pipeline the value into the two functions:</span></span>

```
> 15 |> square |> isOdd;;
val it : bool = true
```

<span data-ttu-id="4237d-171">El operador de canalización hacia delante etc., se tratan en los tutoriales posteriores.</span><span class="sxs-lookup"><span data-stu-id="4237d-171">The pipe-forward operator, and more, are covered in later tutorials.</span></span>

<span data-ttu-id="4237d-172">Esto es sólo un vistazo a lo que puede hacer con F # Interactive.</span><span class="sxs-lookup"><span data-stu-id="4237d-172">This is only a glimpse into what you can do with F# Interactive.</span></span>  <span data-ttu-id="4237d-173">Para obtener más información, visite [programación interactiva con F #](../tutorials/fsharp-interactive/index.md).</span><span class="sxs-lookup"><span data-stu-id="4237d-173">To learn more, check out [Interactive Programming with F#](../tutorials/fsharp-interactive/index.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="4237d-174">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="4237d-174">Next steps</span></span>

<span data-ttu-id="4237d-175">Si no lo ha hecho ya, consulte el [paseo de F #](../tour.md), donde abordan algunas de las características principales del lenguaje F #.</span><span class="sxs-lookup"><span data-stu-id="4237d-175">If you haven't already, check out the [Tour of F#](../tour.md), which covers some of the core features of the F# language.</span></span>  <span data-ttu-id="4237d-176">Se ofrece una visión general de algunas de las capacidades de F # y se proporcionan ejemplos de código de un amplio que puede copiar en Visual Studio para Mac y ejecutar.</span><span class="sxs-lookup"><span data-stu-id="4237d-176">It will give you an overview of some of the capabilities of F#, and provide ample code samples that you can copy into Visual Studio for Mac and run.</span></span>  <span data-ttu-id="4237d-177">También hay algunos recursos externos excelentes que puede utilizar, exhibió en el [Guía de F #](../index.md).</span><span class="sxs-lookup"><span data-stu-id="4237d-177">There are also some great external resources you can use, showcased in the [F# Guide](../index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4237d-178">Vea también</span><span class="sxs-lookup"><span data-stu-id="4237d-178">See also</span></span>
 [<span data-ttu-id="4237d-179">Visual F#</span><span class="sxs-lookup"><span data-stu-id="4237d-179">Visual F#</span></span>](../index.md)  
 [<span data-ttu-id="4237d-180">Paseo por F</span><span class="sxs-lookup"><span data-stu-id="4237d-180">Tour of F#</span></span>](../tour.md)  
 [<span data-ttu-id="4237d-181">Referencia del lenguaje F #</span><span class="sxs-lookup"><span data-stu-id="4237d-181">F# language reference</span></span>](../language-reference/index.md)  
 [<span data-ttu-id="4237d-182">Inferencia de tipos</span><span class="sxs-lookup"><span data-stu-id="4237d-182">Type inference</span></span>](../language-reference/type-inference.md)  
 [<span data-ttu-id="4237d-183">Referencia de símbolos y el operador</span><span class="sxs-lookup"><span data-stu-id="4237d-183">Symbol and operator reference</span></span>](../language-reference/symbol-and-operator-reference/index.md)  
