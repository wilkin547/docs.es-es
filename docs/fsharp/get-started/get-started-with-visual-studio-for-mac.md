---
title: 'Introducción a F # en Visual Studio para Mac'
description: 'Obtenga información sobre cómo usar F # con Visual Studio para Mac.'
ms.date: 07/03/2018
ms.openlocfilehash: d2ad24ad18bb31419b39508f2cf555c82fbe2e0b
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2020
ms.locfileid: "96437987"
---
# <a name="get-started-with-f-in-visual-studio-for-mac"></a><span data-ttu-id="ca67b-103">Introducción a F # en Visual Studio para Mac</span><span class="sxs-lookup"><span data-stu-id="ca67b-103">Get started with F# in Visual Studio for Mac</span></span>

<span data-ttu-id="ca67b-104">F # y las herramientas de Visual F# se admiten en el IDE de Visual Studio para Mac.</span><span class="sxs-lookup"><span data-stu-id="ca67b-104">F# and the Visual F# tooling are supported in the Visual Studio for Mac IDE.</span></span> <span data-ttu-id="ca67b-105">Asegúrese de que ha [instalado Visual Studio para Mac](install-fsharp.md#install-f-with-visual-studio-for-mac).</span><span class="sxs-lookup"><span data-stu-id="ca67b-105">Ensure that you have [Visual Studio for Mac installed](install-fsharp.md#install-f-with-visual-studio-for-mac).</span></span>

## <a name="creating-a-console-application"></a><span data-ttu-id="ca67b-106">Creación de una aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="ca67b-106">Creating a console application</span></span>

<span data-ttu-id="ca67b-107">Uno de los proyectos más básicos de Visual Studio para Mac es la aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="ca67b-107">One of the most basic projects in Visual Studio for Mac is the Console Application.</span></span>  <span data-ttu-id="ca67b-108">Aquí se muestra cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="ca67b-108">Here's how to do it.</span></span>  <span data-ttu-id="ca67b-109">Una vez que Visual Studio para Mac está abierto:</span><span class="sxs-lookup"><span data-stu-id="ca67b-109">Once Visual Studio for Mac is open:</span></span>

1. <span data-ttu-id="ca67b-110">En el menú **archivo** , elija **nueva solución**.</span><span class="sxs-lookup"><span data-stu-id="ca67b-110">On the **File** menu, point to **New Solution**.</span></span>

2. <span data-ttu-id="ca67b-111">En el cuadro de diálogo nuevo proyecto, hay dos plantillas diferentes para la aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="ca67b-111">In the New Project dialog, there are 2 different templates for Console Application.</span></span>  <span data-ttu-id="ca67b-112">Hay una en otras > .NET que tiene como destino el .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ca67b-112">There is one under Other -> .NET which targets the .NET Framework.</span></span>  <span data-ttu-id="ca67b-113">La otra plantilla está en .NET Core-> aplicación que tiene como destino .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ca67b-113">The other template is under .NET Core -> App which targets .NET Core.</span></span>  <span data-ttu-id="ca67b-114">Cualquier plantilla debe funcionar para este artículo.</span><span class="sxs-lookup"><span data-stu-id="ca67b-114">Either template should work for the purpose of this article.</span></span>

3. <span data-ttu-id="ca67b-115">En aplicación de consola, cambie C# a F # si es necesario.</span><span class="sxs-lookup"><span data-stu-id="ca67b-115">Under console app, change C# to F# if needed.</span></span>  <span data-ttu-id="ca67b-116">Elija el botón **siguiente** para avanzar.</span><span class="sxs-lookup"><span data-stu-id="ca67b-116">Choose the **Next** button to move forward!</span></span>  

4. <span data-ttu-id="ca67b-117">Asigne un nombre al proyecto y elija las opciones que quiera para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ca67b-117">Give your project a name, and choose the options you want for the app.</span></span>  <span data-ttu-id="ca67b-118">Fíjese en el panel de vista previa en el lateral de la pantalla que mostrará la estructura de directorios que se creará en función de las opciones seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="ca67b-118">Notice, the preview pane to the side of the screen that will show the directory structure that will be created based on the options selected.</span></span>  

5. <span data-ttu-id="ca67b-119">Haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="ca67b-119">Click **Create**.</span></span>  <span data-ttu-id="ca67b-120">Ahora debería ver un proyecto de F # en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="ca67b-120">You should now see an F# project in the Solution Explorer.</span></span>

## <a name="writing-your-code"></a><span data-ttu-id="ca67b-121">Escritura del código</span><span class="sxs-lookup"><span data-stu-id="ca67b-121">Writing your code</span></span>

<span data-ttu-id="ca67b-122">Vamos a empezar por escribir código primero.</span><span class="sxs-lookup"><span data-stu-id="ca67b-122">Let's get started by writing some code first.</span></span>  <span data-ttu-id="ca67b-123">Asegúrese de que el `Program.fs` archivo está abierto y, a continuación, reemplace el contenido por lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ca67b-123">Make sure that the `Program.fs` file is open, and then replace its contents with the following:</span></span>

[!code-fsharp[HelloSquare](~/samples/snippets/fsharp/getting-started/hello-square.fs)]

<span data-ttu-id="ca67b-124">En el ejemplo de código anterior, se ha definido una función `square` que toma una entrada denominada `x` y la multiplica por sí misma.</span><span class="sxs-lookup"><span data-stu-id="ca67b-124">In the previous code sample, a function `square` has been defined which takes an input named `x` and multiplies it by itself.</span></span>  <span data-ttu-id="ca67b-125">Dado que F # usa la [inferencia de tipos](../language-reference/type-inference.md), `x` no es necesario especificar el tipo de.</span><span class="sxs-lookup"><span data-stu-id="ca67b-125">Because F# uses [Type Inference](../language-reference/type-inference.md), the type of `x` doesn't need to be specified.</span></span>  <span data-ttu-id="ca67b-126">El compilador de F # entiende los tipos en los que la multiplicación es válida y asignará un tipo a `x` basándose en cómo `square` se llama a.</span><span class="sxs-lookup"><span data-stu-id="ca67b-126">The F# compiler understands the types where multiplication is valid, and will assign a type to `x` based on how `square` is called.</span></span>  <span data-ttu-id="ca67b-127">Si mantiene el puntero sobre `square` , debería ver lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ca67b-127">If you hover over `square`, you should see the following:</span></span>

```console
val square: x:int -> int
```

<span data-ttu-id="ca67b-128">Esto es lo que se conoce como la firma de tipo de la función.</span><span class="sxs-lookup"><span data-stu-id="ca67b-128">This is what is known as the function's type signature.</span></span>  <span data-ttu-id="ca67b-129">Se puede leer de la siguiente manera: "Square es una función que toma un entero denominado x y genera un entero".</span><span class="sxs-lookup"><span data-stu-id="ca67b-129">It can be read like this: "Square is a function which takes an integer named x and produces an integer".</span></span>  <span data-ttu-id="ca67b-130">Tenga en cuenta que el compilador dio `square` el `int` tipo por ahora: esto se debe a que la multiplicación no es genérica en *todos los* tipos, sino que es genérica en un conjunto cerrado de tipos.</span><span class="sxs-lookup"><span data-stu-id="ca67b-130">Note that the compiler gave `square` the `int` type for now - this is because multiplication is not generic across *all* types, but rather is generic across a closed set of types.</span></span>  <span data-ttu-id="ca67b-131">El compilador de F # eligió `int` en este punto, pero ajustará la firma del tipo si llama `square` a con otro tipo de entrada, como `float` .</span><span class="sxs-lookup"><span data-stu-id="ca67b-131">The F# compiler picked `int` at this point, but it will adjust the type signature if you call `square` with a different input type, such as a `float`.</span></span>

<span data-ttu-id="ca67b-132">Otra función, `main` , se define, que se decora con el `EntryPoint` atributo para indicar al compilador de F # que la ejecución del programa debe comenzar allí.</span><span class="sxs-lookup"><span data-stu-id="ca67b-132">Another function, `main`, is defined, which is decorated with the `EntryPoint` attribute to tell the F# compiler that program execution should start there.</span></span>  <span data-ttu-id="ca67b-133">Sigue la misma Convención que otros [lenguajes de programación de estilo C](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), donde se pueden pasar argumentos de línea de comandos a esta función y se devuelve un código entero (normalmente `0` ).</span><span class="sxs-lookup"><span data-stu-id="ca67b-133">It follows the same convention as other [C-style programming languages](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), where command-line arguments can be passed to this function, and an integer code is returned (typically `0`).</span></span>

<span data-ttu-id="ca67b-134">En esta función se llama a la `square` función con un argumento de `12` .</span><span class="sxs-lookup"><span data-stu-id="ca67b-134">It is in this function that we call the `square` function with an argument of `12`.</span></span>  <span data-ttu-id="ca67b-135">A continuación, el compilador de F # asigna el tipo de `square` a `int -> int` (es decir, una función que toma `int` y produce `int` ).</span><span class="sxs-lookup"><span data-stu-id="ca67b-135">The F# compiler then assigns the type of `square` to be `int -> int` (that is, a function which takes an `int` and produces an `int`).</span></span>  <span data-ttu-id="ca67b-136">La llamada a `printfn` es una función de impresión con formato que usa una cadena de formato, similar a los lenguajes de programación de estilo C, los parámetros que se corresponden con los especificados en la cadena de formato y, a continuación, imprime el resultado y una nueva línea.</span><span class="sxs-lookup"><span data-stu-id="ca67b-136">The call to `printfn` is a formatted printing function which uses a format string, similar to C-style programming languages, parameters which correspond to those specified in the format string, and then prints the result and a new line.</span></span>

## <a name="running-your-code"></a><span data-ttu-id="ca67b-137">Ejecución de código</span><span class="sxs-lookup"><span data-stu-id="ca67b-137">Running your code</span></span>

<span data-ttu-id="ca67b-138">Puede ejecutar el código y ver los resultados haciendo clic en **Ejecutar** en el menú de nivel superior y, a continuación, **iniciar sin depurar**.</span><span class="sxs-lookup"><span data-stu-id="ca67b-138">You can run the code and see results by clicking on **Run** from the top level menu and then **Start Without Debugging**.</span></span>  <span data-ttu-id="ca67b-139">Así se ejecutará el programa sin depurar y podrá ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="ca67b-139">This will run the program without debugging and allows you to see the results.</span></span>

<span data-ttu-id="ca67b-140">Ahora debería ver lo siguiente impreso en la ventana de la consola que Visual Studio para Mac emerge:</span><span class="sxs-lookup"><span data-stu-id="ca67b-140">You should now see the following printed to the console window that Visual Studio for Mac popped up:</span></span>

```console
12 squared is 144!
```

<span data-ttu-id="ca67b-141">Enhorabuena.</span><span class="sxs-lookup"><span data-stu-id="ca67b-141">Congratulations!</span></span>  <span data-ttu-id="ca67b-142">Ha creado su primer proyecto de F # en Visual Studio para Mac, ha escrito una función de F # y ha impreso los resultados de una llamada a esa función, y ejecuta el proyecto para ver algunos resultados.</span><span class="sxs-lookup"><span data-stu-id="ca67b-142">You've created your first F# project in Visual Studio for Mac, written an F# function printed the results of calling that function, and run the project to see some results.</span></span>

## <a name="using-f-interactive"></a><span data-ttu-id="ca67b-143">Usar F# interactivo</span><span class="sxs-lookup"><span data-stu-id="ca67b-143">Using F# Interactive</span></span>

<span data-ttu-id="ca67b-144">Una de las mejores características de las herramientas de Visual F# en Visual Studio para Mac es la ventana de F# interactivo.</span><span class="sxs-lookup"><span data-stu-id="ca67b-144">One of the best features of the Visual F# tooling in Visual Studio for Mac is the F# Interactive Window.</span></span>  <span data-ttu-id="ca67b-145">Permite enviar código a un proceso en el que se puede llamar a ese código y ver el resultado de forma interactiva.</span><span class="sxs-lookup"><span data-stu-id="ca67b-145">It allows you to send code over to a process where you can call that code and see the result interactively.</span></span>

<span data-ttu-id="ca67b-146">Para empezar a usarlo, resalte la `square` función definida en el código.</span><span class="sxs-lookup"><span data-stu-id="ca67b-146">To begin using it, highlight the `square` function defined in your code.</span></span>  <span data-ttu-id="ca67b-147">A continuación, haga clic en **Editar** en el menú de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="ca67b-147">Next, click on **Edit** from the top level menu.</span></span>  <span data-ttu-id="ca67b-148">A continuación, seleccione **Enviar selección a F# interactivo**.</span><span class="sxs-lookup"><span data-stu-id="ca67b-148">Next select **Send selection to F# Interactive**.</span></span>  <span data-ttu-id="ca67b-149">Esto ejecuta el código en la ventana F# interactivo.</span><span class="sxs-lookup"><span data-stu-id="ca67b-149">This executes the code in the F# Interactive Window.</span></span>  <span data-ttu-id="ca67b-150">Como alternativa, puede hacer clic con el botón derecho en la selección y elegir **Enviar selección a F# interactivo**.</span><span class="sxs-lookup"><span data-stu-id="ca67b-150">Alternatively, you can right click on the selection and choose **Send selection to F# Interactive**.</span></span>  <span data-ttu-id="ca67b-151">Debería ver que la ventana de F# interactivo aparece con lo siguiente en ella:</span><span class="sxs-lookup"><span data-stu-id="ca67b-151">You should see the F# Interactive Window appear with the following in it:</span></span>

```console
>

val square : x:int -> int

>
```

<span data-ttu-id="ca67b-152">Esto muestra la misma firma de función para la `square` función, que vio anteriormente al mantener el mouse sobre la función.</span><span class="sxs-lookup"><span data-stu-id="ca67b-152">This shows the same function signature for the `square` function, which you saw earlier when you hovered over the function.</span></span>  <span data-ttu-id="ca67b-153">Dado `square` que ahora se define en el proceso de F# interactivo, puede llamarlo con valores diferentes:</span><span class="sxs-lookup"><span data-stu-id="ca67b-153">Because `square` is now defined in the F# Interactive process, you can call it with different values:</span></span>

```console
> square 12;;
val it : int = 144
>square 13;;
val it : int = 169
```

<span data-ttu-id="ca67b-154">De esta forma, se ejecuta la función, se enlaza el resultado a un nuevo nombre `it` y se muestra el tipo y el valor de `it` .</span><span class="sxs-lookup"><span data-stu-id="ca67b-154">This executes the function, binds the result to a new name `it`, and displays the type and value of `it`.</span></span>  <span data-ttu-id="ca67b-155">Tenga en cuenta que debe terminar cada línea con `;;` .</span><span class="sxs-lookup"><span data-stu-id="ca67b-155">Note that you must terminate each line with `;;`.</span></span>  <span data-ttu-id="ca67b-156">Así es como F# interactivo sabe cuándo finaliza la llamada de función.</span><span class="sxs-lookup"><span data-stu-id="ca67b-156">This is how F# Interactive knows when your function call is finished.</span></span>  <span data-ttu-id="ca67b-157">También puede definir nuevas funciones en F# interactivo:</span><span class="sxs-lookup"><span data-stu-id="ca67b-157">You can also define new functions in F# Interactive:</span></span>

```console
> let isOdd x = x % 2 <> 0;;

val isOdd : x:int -> bool

> isOdd 12;;
val it : bool = false
```

<span data-ttu-id="ca67b-158">Lo anterior define una nueva función, `isOdd` , que toma `int` y comprueba si es impar.</span><span class="sxs-lookup"><span data-stu-id="ca67b-158">The above defines a new function, `isOdd`, which takes an `int` and checks to see if it's odd!</span></span>  <span data-ttu-id="ca67b-159">Puede llamar a esta función para ver lo que devuelve con diferentes entradas.</span><span class="sxs-lookup"><span data-stu-id="ca67b-159">You can call this function to see what it returns with different inputs.</span></span>  <span data-ttu-id="ca67b-160">Puede llamar a funciones dentro de las llamadas de función:</span><span class="sxs-lookup"><span data-stu-id="ca67b-160">You can call functions within function calls:</span></span>

```console
> isOdd (square 15);;
val it : bool = true
```

<span data-ttu-id="ca67b-161">También puede usar el [operador de canalización directa](../language-reference/symbol-and-operator-reference/index.md) para canalizar el valor en las dos funciones:</span><span class="sxs-lookup"><span data-stu-id="ca67b-161">You can also use the [pipe-forward operator](../language-reference/symbol-and-operator-reference/index.md) to pipeline the value into the two functions:</span></span>

```console
> 15 |> square |> isOdd;;
val it : bool = true
```

<span data-ttu-id="ca67b-162">El operador de canalización hacia delante, y más, se trata en los tutoriales posteriores.</span><span class="sxs-lookup"><span data-stu-id="ca67b-162">The pipe-forward operator, and more, are covered in later tutorials.</span></span>

<span data-ttu-id="ca67b-163">Esto solo es un vistazo a lo que puede hacer con F# interactivo.</span><span class="sxs-lookup"><span data-stu-id="ca67b-163">This is only a glimpse into what you can do with F# Interactive.</span></span>  <span data-ttu-id="ca67b-164">Para obtener más información, consulte [programación interactiva con F #](../tools/fsharp-interactive/index.md).</span><span class="sxs-lookup"><span data-stu-id="ca67b-164">To learn more, check out [Interactive Programming with F#](../tools/fsharp-interactive/index.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="ca67b-165">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="ca67b-165">Next steps</span></span>

<span data-ttu-id="ca67b-166">Si todavía no lo ha hecho, consulte el [paseo por f #](../tour.md), que trata algunas de las características principales del lenguaje f #.</span><span class="sxs-lookup"><span data-stu-id="ca67b-166">If you haven't already, check out the [Tour of F#](../tour.md), which covers some of the core features of the F# language.</span></span>  <span data-ttu-id="ca67b-167">Le proporcionará una visión general de algunas de las funcionalidades de F # y proporcionará ejemplos de código que puede copiar en Visual Studio para Mac y ejecutar.</span><span class="sxs-lookup"><span data-stu-id="ca67b-167">It will give you an overview of some of the capabilities of F#, and provide ample code samples that you can copy into Visual Studio for Mac and run.</span></span>  <span data-ttu-id="ca67b-168">También hay algunos excelentes recursos externos que puede usar, que se muestran en la [Guía de F #](../index.yml).</span><span class="sxs-lookup"><span data-stu-id="ca67b-168">There are also some great external resources you can use, showcased in the [F# Guide](../index.yml).</span></span>

## <a name="see-also"></a><span data-ttu-id="ca67b-169">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ca67b-169">See also</span></span>

- [<span data-ttu-id="ca67b-170">Guía de F#</span><span class="sxs-lookup"><span data-stu-id="ca67b-170">F# guide</span></span>](../index.yml)
- [<span data-ttu-id="ca67b-171">Paseo por F#</span><span class="sxs-lookup"><span data-stu-id="ca67b-171">Tour of F#</span></span>](../tour.md)
- [<span data-ttu-id="ca67b-172">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="ca67b-172">F# language reference</span></span>](../language-reference/index.md)
- [<span data-ttu-id="ca67b-173">Inferencia de tipos</span><span class="sxs-lookup"><span data-stu-id="ca67b-173">Type inference</span></span>](../language-reference/type-inference.md)
- [<span data-ttu-id="ca67b-174">Referencia de símbolos y operadores</span><span class="sxs-lookup"><span data-stu-id="ca67b-174">Symbol and operator reference</span></span>](../language-reference/symbol-and-operator-reference/index.md)
