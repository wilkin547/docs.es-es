---
title: Introducción a F# en Visual Studio para Mac
description: Aprenda a usar F# con Visual Studio para Mac.
ms.date: 07/03/2018
ms.openlocfilehash: a6997f139d7e6c5fdf77878442db0b0b75b3d727
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59331876"
---
# <a name="get-started-with-f-in-visual-studio-for-mac"></a><span data-ttu-id="38a4e-103">Introducción a F# en Visual Studio para Mac</span><span class="sxs-lookup"><span data-stu-id="38a4e-103">Get started with F# in Visual Studio for Mac</span></span>

<span data-ttu-id="38a4e-104">F#y el objeto Visual F# se admiten las herramientas de Visual Studio para Mac IDE.</span><span class="sxs-lookup"><span data-stu-id="38a4e-104">F# and the Visual F# tooling are supported in the Visual Studio for Mac IDE.</span></span> <span data-ttu-id="38a4e-105">Asegúrese de que tiene [Visual Studio para Mac instalados](install-fsharp.md#install-f-with-visual-studio-for-mac).</span><span class="sxs-lookup"><span data-stu-id="38a4e-105">Ensure that you have [Visual Studio for Mac installed](install-fsharp.md#install-f-with-visual-studio-for-mac).</span></span>

## <a name="creating-a-console-application"></a><span data-ttu-id="38a4e-106">Creación de una aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="38a4e-106">Creating a console application</span></span>

<span data-ttu-id="38a4e-107">Uno de los proyectos en Visual Studio para Mac más básicos es la aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="38a4e-107">One of the most basic projects in Visual Studio for Mac is the Console Application.</span></span>  <span data-ttu-id="38a4e-108">A continuación le mostramos cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="38a4e-108">Here's how to do it.</span></span>  <span data-ttu-id="38a4e-109">Una vez abierto Visual Studio para Mac:</span><span class="sxs-lookup"><span data-stu-id="38a4e-109">Once Visual Studio for Mac is open:</span></span>

1. <span data-ttu-id="38a4e-110">En el **archivo** menú, elija **nueva solución**.</span><span class="sxs-lookup"><span data-stu-id="38a4e-110">On the **File** menu, point to **New Solution**.</span></span>

2. <span data-ttu-id="38a4e-111">En el cuadro de diálogo nuevo proyecto, hay 2 distintas plantillas de aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="38a4e-111">In the New Project dialog, there are 2 different templates for Console Application.</span></span>  <span data-ttu-id="38a4e-112">Hay uno en otras opciones -> .NET que tiene como destino .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="38a4e-112">There is one under Other -> .NET which targets the .NET Framework.</span></span>  <span data-ttu-id="38a4e-113">La otra plantilla está en .NET Core -> aplicación destinada a .NET Core.</span><span class="sxs-lookup"><span data-stu-id="38a4e-113">The other template is under .NET Core -> App which targets .NET Core.</span></span>  <span data-ttu-id="38a4e-114">Cualquier plantilla debería funcionar con el propósito de este artículo.</span><span class="sxs-lookup"><span data-stu-id="38a4e-114">Either template should work for the purpose of this article.</span></span>

3. <span data-ttu-id="38a4e-115">En la aplicación de consola, cambie C# a F# si es necesario.</span><span class="sxs-lookup"><span data-stu-id="38a4e-115">Under console app, change C# to F# if needed.</span></span>  <span data-ttu-id="38a4e-116">Elija la **siguiente** botón para desplazarse hacia delante.</span><span class="sxs-lookup"><span data-stu-id="38a4e-116">Choose the **Next** button to move forward!</span></span>  

4. <span data-ttu-id="38a4e-117">Asigne un nombre al proyecto y elija las opciones que desee para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="38a4e-117">Give your project a name, and choose the options you want for the app.</span></span>  <span data-ttu-id="38a4e-118">Tenga en cuenta, el panel de vista previa al lado de la pantalla que muestra la estructura de directorios que se creará en función de las opciones seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="38a4e-118">Notice, the preview pane to the side of the screen that will show the directory structure that will be created based on the options selected.</span></span>  

5. <span data-ttu-id="38a4e-119">Haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="38a4e-119">Click **Create**.</span></span>  <span data-ttu-id="38a4e-120">Ahora debería ver un F# proyecto en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="38a4e-120">You should now see an F# project in the Solution Explorer.</span></span>

## <a name="writing-your-code"></a><span data-ttu-id="38a4e-121">Escribir el código</span><span class="sxs-lookup"><span data-stu-id="38a4e-121">Writing your code</span></span>

<span data-ttu-id="38a4e-122">Vamos a empezar a escribir código en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="38a4e-122">Let's get started by writing some code first.</span></span>  <span data-ttu-id="38a4e-123">Asegúrese de que el `Program.fs` archivo está abierto y, a continuación, reemplace su contenido por lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="38a4e-123">Make sure that the `Program.fs` file is open, and then replace its contents with the following:</span></span>

[!code-fsharp[HelloSquare](../../../samples/snippets/fsharp/getting-started/hello-square.fs)]

<span data-ttu-id="38a4e-124">En el ejemplo de código anterior, una función `square` se ha definido que toma una entrada denominada `x` y lo multiplica por sí mismo.</span><span class="sxs-lookup"><span data-stu-id="38a4e-124">In the previous code sample, a function `square` has been defined which takes an input named `x` and multiplies it by itself.</span></span>  <span data-ttu-id="38a4e-125">Dado que F# usa [inferencia](../language-reference/type-inference.md), el tipo de `x` no deben especificarse.</span><span class="sxs-lookup"><span data-stu-id="38a4e-125">Because F# uses [Type Inference](../language-reference/type-inference.md), the type of `x` doesn't need to be specified.</span></span>  <span data-ttu-id="38a4e-126">El F# compilador entiende los tipos que es válida la multiplicación y asignará un tipo a `x` según cómo `square` se llama.</span><span class="sxs-lookup"><span data-stu-id="38a4e-126">The F# compiler understands the types where multiplication is valid, and will assign a type to `x` based on how `square` is called.</span></span>  <span data-ttu-id="38a4e-127">Si se mantiene el mouse sobre `square`, debería aparecer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="38a4e-127">If you hover over `square`, you should see the following:</span></span>

```
val square: x:int -> int
```

<span data-ttu-id="38a4e-128">Esto es lo que se conoce como la firma del tipo de la función.</span><span class="sxs-lookup"><span data-stu-id="38a4e-128">This is what is known as the function's type signature.</span></span>  <span data-ttu-id="38a4e-129">Se puede leer como esta: "Cuadrado es una función que toma un número entero denominado x y genera un número entero".</span><span class="sxs-lookup"><span data-stu-id="38a4e-129">It can be read like this: "Square is a function which takes an integer named x and produces an integer".</span></span>  <span data-ttu-id="38a4e-130">Tenga en cuenta que el compilador proporcionaba `square` el `int` tipo por ahora: Esto es porque no es genérica a través de la multiplicación *todas* tipos, pero es bastante genérico a través de un conjunto cerrado de tipos.</span><span class="sxs-lookup"><span data-stu-id="38a4e-130">Note that the compiler gave `square` the `int` type for now - this is because multiplication is not generic across *all* types, but rather is generic across a closed set of types.</span></span>  <span data-ttu-id="38a4e-131">El F# compilador seleccionada `int` en este punto, pero se ajustará la firma del tipo si se llama a `square` con otro tipo de entrada, como un `float`.</span><span class="sxs-lookup"><span data-stu-id="38a4e-131">The F# compiler picked `int` at this point, but it will adjust the type signature if you call `square` with a different input type, such as a `float`.</span></span>

<span data-ttu-id="38a4e-132">Otra función `main`, se define, que está decorada con el `EntryPoint` atributo para indicar el F# compilador que la ejecución del programa debe empezar por ahí.</span><span class="sxs-lookup"><span data-stu-id="38a4e-132">Another function, `main`, is defined, which is decorated with the `EntryPoint` attribute to tell the F# compiler that program execution should start there.</span></span>  <span data-ttu-id="38a4e-133">Sigue la misma convención que otros [lenguajes de programación de estilo C](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), donde se pueden pasar argumentos de línea de comandos a esta función y se devuelve un código entero (normalmente `0`).</span><span class="sxs-lookup"><span data-stu-id="38a4e-133">It follows the same convention as other [C-style programming languages](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), where command-line arguments can be passed to this function, and an integer code is returned (typically `0`).</span></span>

<span data-ttu-id="38a4e-134">Se encuentra en esta función que llamamos el `square` función con un argumento de `12`.</span><span class="sxs-lookup"><span data-stu-id="38a4e-134">It is in this function that we call the `square` function with an argument of `12`.</span></span>  <span data-ttu-id="38a4e-135">El F# compilador, a continuación, asigna el tipo de `square` sea `int -> int` (es decir, una función que toma un `int` y genera un `int`).</span><span class="sxs-lookup"><span data-stu-id="38a4e-135">The F# compiler then assigns the type of `square` to be `int -> int` (that is, a function which takes an `int` and produces an `int`).</span></span>  <span data-ttu-id="38a4e-136">La llamada a `printfn` es una función de impresión con formato que usa una cadena de formato, similar a lenguajes de programación de estilo C, los parámetros que corresponden a los especificados en la cadena de formato y, a continuación, imprime el resultado y una nueva línea.</span><span class="sxs-lookup"><span data-stu-id="38a4e-136">The call to `printfn` is a formatted printing function which uses a format string, similar to C-style programming languages, parameters which correspond to those specified in the format string, and then prints the result and a new line.</span></span>

## <a name="running-your-code"></a><span data-ttu-id="38a4e-137">Ejecución del código</span><span class="sxs-lookup"><span data-stu-id="38a4e-137">Running your code</span></span>

<span data-ttu-id="38a4e-138">Puede ejecutar el código y ver los resultados, haga clic en **ejecutar** en el menú de nivel superior y, a continuación, **iniciar sin depurar**.</span><span class="sxs-lookup"><span data-stu-id="38a4e-138">You can run the code and see results by clicking on **Run** from the top level menu and then **Start Without Debugging**.</span></span>  <span data-ttu-id="38a4e-139">Esto ejecutará el programa sin depuración y le permite ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="38a4e-139">This will run the program without debugging and allows you to see the results.</span></span>

<span data-ttu-id="38a4e-140">Ahora debería ver lo siguiente que se imprimen en la ventana de consola que apareció Visual Studio para Mac:</span><span class="sxs-lookup"><span data-stu-id="38a4e-140">You should now see the following printed to the console window that Visual Studio for Mac popped up:</span></span>

```
12 squared is 144!
```

<span data-ttu-id="38a4e-141">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="38a4e-141">Congratulations!</span></span>  <span data-ttu-id="38a4e-142">Ha creado su primer F# proyecto en Visual Studio para Mac, escribe un F# función imprime los resultados de llamar a función y ejecutar el proyecto para ver algunos resultados.</span><span class="sxs-lookup"><span data-stu-id="38a4e-142">You've created your first F# project in Visual Studio for Mac, written an F# function printed the results of calling that function, and run the project to see some results.</span></span>

## <a name="using-f-interactive"></a><span data-ttu-id="38a4e-143">Uso de F# interactivo</span><span class="sxs-lookup"><span data-stu-id="38a4e-143">Using F# Interactive</span></span>

<span data-ttu-id="38a4e-144">Una de las mejores características del objeto Visual F# herramientas en Visual Studio para Mac es el F# ventana interactiva.</span><span class="sxs-lookup"><span data-stu-id="38a4e-144">One of the best features of the Visual F# tooling in Visual Studio for Mac is the F# Interactive Window.</span></span>  <span data-ttu-id="38a4e-145">Permite enviar código a través de un proceso donde puede llamar a ese código y ver el resultado de forma interactiva.</span><span class="sxs-lookup"><span data-stu-id="38a4e-145">It allows you to send code over to a process where you can call that code and see the result interactively.</span></span>

<span data-ttu-id="38a4e-146">Para empezar a usarlo, resalte el `square` definida en el código de función.</span><span class="sxs-lookup"><span data-stu-id="38a4e-146">To begin using it, highlight the `square` function defined in your code.</span></span>  <span data-ttu-id="38a4e-147">A continuación, haga clic en **editar** en el menú de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="38a4e-147">Next, click on **Edit** from the top level menu.</span></span>  <span data-ttu-id="38a4e-148">A continuación, seleccione **Enviar selección a F# interactivo**.</span><span class="sxs-lookup"><span data-stu-id="38a4e-148">Next select **Send selection to F# Interactive**.</span></span>  <span data-ttu-id="38a4e-149">Esto ejecuta el código en el F# ventana interactiva.</span><span class="sxs-lookup"><span data-stu-id="38a4e-149">This executes the code in the F# Interactive Window.</span></span>  <span data-ttu-id="38a4e-150">Como alternativa, puede haga clic con el botón derecho en la selección y elija **Enviar selección a F# interactivo**.</span><span class="sxs-lookup"><span data-stu-id="38a4e-150">Alternatively, you can right click on the selection and choose **Send selection to F# Interactive**.</span></span>  <span data-ttu-id="38a4e-151">Debería ver el F# ventana interactiva aparecen con lo siguiente en él:</span><span class="sxs-lookup"><span data-stu-id="38a4e-151">You should see the F# Interactive Window appear with the following in it:</span></span>

```
>

val square : x:int -> int

>
```

<span data-ttu-id="38a4e-152">Esto muestra la misma firma de función para el `square` función, que vio anteriormente cuando al mantener el mouse sobre la función.</span><span class="sxs-lookup"><span data-stu-id="38a4e-152">This shows the same function signature for the `square` function, which you saw earlier when you hovered over the function.</span></span>  <span data-ttu-id="38a4e-153">Dado que `square` ahora está definida en el F# proceso interactivo, podemos llamarlo con valores diferentes:</span><span class="sxs-lookup"><span data-stu-id="38a4e-153">Because `square` is now defined in the F# Interactive process, you can call it with different values:</span></span>

```
> square 12;;
val it : int = 144
>square 13;;
val it : int = 169
```

<span data-ttu-id="38a4e-154">Esto ejecuta la función, el resultado se enlaza a un nuevo nombre `it`y muestra el tipo y el valor de `it`.</span><span class="sxs-lookup"><span data-stu-id="38a4e-154">This executes the function, binds the result to a new name `it`, and displays the type and value of `it`.</span></span>  <span data-ttu-id="38a4e-155">Tenga en cuenta que es preciso finalizar cada línea con `;;`.</span><span class="sxs-lookup"><span data-stu-id="38a4e-155">Note that you must terminate each line with `;;`.</span></span>  <span data-ttu-id="38a4e-156">Se trata cómo F# interactivo sabe cuando finalice la llamada de función.</span><span class="sxs-lookup"><span data-stu-id="38a4e-156">This is how F# Interactive knows when your function call is finished.</span></span>  <span data-ttu-id="38a4e-157">También puede definir nuevas funciones en F# interactivo:</span><span class="sxs-lookup"><span data-stu-id="38a4e-157">You can also define new functions in F# Interactive:</span></span>

```
> let isOdd x = x % 2 <> 0;;

val isOdd : x:int -> bool

> isOdd 12;;
val it : bool = false
```

<span data-ttu-id="38a4e-158">Lo anterior define una nueva función, `isOdd`, que toma un `int` y comprueba si es impar.</span><span class="sxs-lookup"><span data-stu-id="38a4e-158">The above defines a new function, `isOdd`, which takes an `int` and checks to see if it's odd!</span></span>  <span data-ttu-id="38a4e-159">Puede llamar a esta función para ver lo que devuelve con diferentes entradas.</span><span class="sxs-lookup"><span data-stu-id="38a4e-159">You can call this function to see what it returns with different inputs.</span></span>  <span data-ttu-id="38a4e-160">Puede llamar a funciones dentro de las llamadas de función:</span><span class="sxs-lookup"><span data-stu-id="38a4e-160">You can call functions within function calls:</span></span>

```
> isOdd (square 15);;
val it : bool = true
```

<span data-ttu-id="38a4e-161">También puede usar el [operador de canalización hacia delante](../language-reference/symbol-and-operator-reference/index.md) para canalizar el valor en las dos funciones:</span><span class="sxs-lookup"><span data-stu-id="38a4e-161">You can also use the [pipe-forward operator](../language-reference/symbol-and-operator-reference/index.md) to pipeline the value into the two functions:</span></span>

```
> 15 |> square |> isOdd;;
val it : bool = true
```

<span data-ttu-id="38a4e-162">El operador de canalización hacia delante y mucho más, se tratan en los tutoriales posteriores.</span><span class="sxs-lookup"><span data-stu-id="38a4e-162">The pipe-forward operator, and more, are covered in later tutorials.</span></span>

<span data-ttu-id="38a4e-163">Esto es sólo un vistazo a lo que puede hacer con F# interactivo.</span><span class="sxs-lookup"><span data-stu-id="38a4e-163">This is only a glimpse into what you can do with F# Interactive.</span></span>  <span data-ttu-id="38a4e-164">Para obtener más información, consulte [programación interactiva con F# ](../tutorials/fsharp-interactive/index.md).</span><span class="sxs-lookup"><span data-stu-id="38a4e-164">To learn more, check out [Interactive Programming with F#](../tutorials/fsharp-interactive/index.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="38a4e-165">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="38a4e-165">Next steps</span></span>

<span data-ttu-id="38a4e-166">Si no lo ha hecho ya, consulte el [paseo F# ](../tour.md), donde abordan algunas de las características principales de la F# lenguaje.</span><span class="sxs-lookup"><span data-stu-id="38a4e-166">If you haven't already, check out the [Tour of F#](../tour.md), which covers some of the core features of the F# language.</span></span>  <span data-ttu-id="38a4e-167">Se le ofrecerá una visión general de algunas de las capacidades de F#y proporcionan ejemplos de código suficiente que puede copiar en Visual Studio para Mac y en ejecución.</span><span class="sxs-lookup"><span data-stu-id="38a4e-167">It will give you an overview of some of the capabilities of F#, and provide ample code samples that you can copy into Visual Studio for Mac and run.</span></span>  <span data-ttu-id="38a4e-168">También hay algunos excelentes recursos externos, puede usar, exhibió en el [ F# guía](../index.md).</span><span class="sxs-lookup"><span data-stu-id="38a4e-168">There are also some great external resources you can use, showcased in the [F# Guide](../index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="38a4e-169">Vea también</span><span class="sxs-lookup"><span data-stu-id="38a4e-169">See also</span></span>

- [<span data-ttu-id="38a4e-170">Visual F#</span><span class="sxs-lookup"><span data-stu-id="38a4e-170">Visual F#</span></span>](../index.md)
- [<span data-ttu-id="38a4e-171">Paseo por F#</span><span class="sxs-lookup"><span data-stu-id="38a4e-171">Tour of F#</span></span>](../tour.md)
- [<span data-ttu-id="38a4e-172">F#referencia del lenguaje</span><span class="sxs-lookup"><span data-stu-id="38a4e-172">F# language reference</span></span>](../language-reference/index.md)
- [<span data-ttu-id="38a4e-173">Inferencia de tipos</span><span class="sxs-lookup"><span data-stu-id="38a4e-173">Type inference</span></span>](../language-reference/type-inference.md)
- [<span data-ttu-id="38a4e-174">Referencia de símbolos y el operador</span><span class="sxs-lookup"><span data-stu-id="38a4e-174">Symbol and operator reference</span></span>](../language-reference/symbol-and-operator-reference/index.md)
