---
title: 'Empezar a trabajar con F # en Visual Studio'
description: "Obtenga información acerca de cómo usar F # con Visual Studio."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 02/13/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 8db75596-19a9-4eda-b20d-a12d517c8cc1
ms.openlocfilehash: 944bbbba6a26634ace269d86cbbdde9ef9de7bcd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="get-started-with-f-in-visual-studio"></a><span data-ttu-id="8f8d0-104">Empezar a trabajar con F # en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="8f8d0-104">Get started with F# in Visual Studio</span></span>

<span data-ttu-id="8f8d0-105">F # y las herramientas de Visual F # se admiten en el IDE de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="8f8d0-105">F# and the Visual F# tooling are supported in the Visual Studio IDE.</span></span>  <span data-ttu-id="8f8d0-106">Para empezar, debe [descargar Visual Studio](https://www.visualstudio.com/downloads/download-visual-studio-vs), si no lo ha hecho ya.</span><span class="sxs-lookup"><span data-stu-id="8f8d0-106">To begin, you should [download Visual Studio](https://www.visualstudio.com/downloads/download-visual-studio-vs), if you haven't already.</span></span>  <span data-ttu-id="8f8d0-107">En este artículo usa Visual Studio 2017 Community Edition, pero puede usar F # con la versión de su elección.</span><span class="sxs-lookup"><span data-stu-id="8f8d0-107">This article uses the Visual Studio 2017 Community Edition, but you can use F# with the version of your choice.</span></span>

## <a name="installing-f"></a><span data-ttu-id="8f8d0-108">Instalación de F #</span><span class="sxs-lookup"><span data-stu-id="8f8d0-108">Installing F#</span></span> #

<span data-ttu-id="8f8d0-109">Si va a descargar Visual Studio por primera vez, instalará primero el instalador de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="8f8d0-109">If you're downloading Visual Studio for the first time, it will first install the Visual Studio installer.</span></span>  <span data-ttu-id="8f8d0-110">Instalar cualquier versión de Visual Studio de 2017 desde el instalador.</span><span class="sxs-lookup"><span data-stu-id="8f8d0-110">Install any version of Visual Studio 2017 from the installer.</span></span> <span data-ttu-id="8f8d0-111">Si ya tiene instalado, haga clic en **modificar**.</span><span class="sxs-lookup"><span data-stu-id="8f8d0-111">If you already have it installed, click **Modify**.</span></span>

<span data-ttu-id="8f8d0-112">A continuación, verá una lista de las cargas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8f8d0-112">You'll next see a list of Workloads.</span></span> <span data-ttu-id="8f8d0-113">Puede instalar F # a través de cualquiera de las cargas de trabajo siguientes:</span><span class="sxs-lookup"><span data-stu-id="8f8d0-113">You can install F# through any of the following workloads:</span></span>

|<span data-ttu-id="8f8d0-114">Carga de trabajo</span><span class="sxs-lookup"><span data-stu-id="8f8d0-114">Workload</span></span>|<span data-ttu-id="8f8d0-115">Acción</span><span class="sxs-lookup"><span data-stu-id="8f8d0-115">Action</span></span>|
|--------|------|
| <span data-ttu-id="8f8d0-116">Desarrollo multiplataforma de .NET Core</span><span class="sxs-lookup"><span data-stu-id="8f8d0-116">.NET Core cross-platform development</span></span> | <span data-ttu-id="8f8d0-117">Ninguna acción - F # se instala de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="8f8d0-117">No action - F# is installed by default</span></span> |
| <span data-ttu-id="8f8d0-118">Desarrollo web y ASP.NET</span><span class="sxs-lookup"><span data-stu-id="8f8d0-118">ASP.NET and web development</span></span> | <span data-ttu-id="8f8d0-119">Ninguna acción - F # se instala de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="8f8d0-119">No action - F# is installed by default</span></span> |
| <span data-ttu-id="8f8d0-120">Desarrollo de Azure</span><span class="sxs-lookup"><span data-stu-id="8f8d0-120">Azure development</span></span> | <span data-ttu-id="8f8d0-121">Ninguna acción - F # se instala de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="8f8d0-121">No action - F# is installed by default</span></span> |
| <span data-ttu-id="8f8d0-122">Desarrollo móvil con .NET</span><span class="sxs-lookup"><span data-stu-id="8f8d0-122">Mobile development with .NET</span></span> | <span data-ttu-id="8f8d0-123">Ninguna acción - F # se instala de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="8f8d0-123">No action - F# is installed by default</span></span> |
| <span data-ttu-id="8f8d0-124">Aplicaciones analíticas y de ciencia de datos</span><span class="sxs-lookup"><span data-stu-id="8f8d0-124">Data science and analytical applications</span></span> | <span data-ttu-id="8f8d0-125">Ninguna acción - F # se instala de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="8f8d0-125">No action - F# is installed by default</span></span> |
| <span data-ttu-id="8f8d0-126">Desarrollo de escritorio de .NET</span><span class="sxs-lookup"><span data-stu-id="8f8d0-126">.NET desktop development</span></span> | <span data-ttu-id="8f8d0-127">Seleccione **compatibilidad con el escritorio del lenguaje F #** desde el lado derecho</span><span class="sxs-lookup"><span data-stu-id="8f8d0-127">Select **F# desktop language support** from the right-hand side</span></span> |
| <span data-ttu-id="8f8d0-128">Almacenamiento y procesamiento de datos</span><span class="sxs-lookup"><span data-stu-id="8f8d0-128">Data storage and processing</span></span> | <span data-ttu-id="8f8d0-129">Seleccione **compatibilidad con el escritorio del lenguaje F #** desde el lado derecho</span><span class="sxs-lookup"><span data-stu-id="8f8d0-129">Select **F# desktop language support** from the right-hand side</span></span> |

<span data-ttu-id="8f8d0-130">A continuación, haga clic en **modificar** en el lado inferior derecho.</span><span class="sxs-lookup"><span data-stu-id="8f8d0-130">Next, click **Modify** in the lower right-hand side.</span></span>  <span data-ttu-id="8f8d0-131">Este modo se instalará todo lo que ha seleccionado.</span><span class="sxs-lookup"><span data-stu-id="8f8d0-131">This will install everything you have selected.</span></span>  <span data-ttu-id="8f8d0-132">A continuación, puede abrir Visual Studio de 2017 con compatibilidad con el lenguaje F # haciendo clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="8f8d0-132">You can then open Visual Studio 2017 with F# language support by clicking **Launch**.</span></span>

## <a name="creating-a-console-application"></a><span data-ttu-id="8f8d0-133">Crear una aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="8f8d0-133">Creating a console application</span></span>

<span data-ttu-id="8f8d0-134">Uno de los proyectos más básicos en Visual Studio es la aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="8f8d0-134">One of the most basic projects in Visual Studio is the Console Application.</span></span>  <span data-ttu-id="8f8d0-135">A continuación le mostramos cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="8f8d0-135">Here's how to do it.</span></span>  <span data-ttu-id="8f8d0-136">Una vez abierto Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="8f8d0-136">Once Visual Studio is open:</span></span>

1. <span data-ttu-id="8f8d0-137">En el **archivo** menú, elija **New**y, a continuación, elija **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="8f8d0-137">On the **File** menu, point to **New**, and then choose **Project**.</span></span>

2.  <span data-ttu-id="8f8d0-138">En el icono nuevo proyecto del cuadro de diálogo, en **plantillas**, debería ver **Visual F #**.</span><span class="sxs-lookup"><span data-stu-id="8f8d0-138">In the New Project dialog, under **Templates**, you should see **Visual F#**.</span></span>  <span data-ttu-id="8f8d0-139">Active esta casilla para mostrar las plantillas de F #.</span><span class="sxs-lookup"><span data-stu-id="8f8d0-139">Choose this to show the F# templates.</span></span>

3. <span data-ttu-id="8f8d0-140">Seleccione **.NET principales de aplicación de consola** o **aplicación de consola**.</span><span class="sxs-lookup"><span data-stu-id="8f8d0-140">Select either **.NET Core Console app** or **Console app**.</span></span>

3. <span data-ttu-id="8f8d0-141">Elija la **bien** botón para crear el proyecto de F #.</span><span class="sxs-lookup"><span data-stu-id="8f8d0-141">Choose the **Okay** button to create the F# project!</span></span>  <span data-ttu-id="8f8d0-142">Ahora debería ver un proyecto de F # en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="8f8d0-142">You should now see an F# project in the Solution Explorer.</span></span>

## <a name="writing-your-code"></a><span data-ttu-id="8f8d0-143">Escribir el código</span><span class="sxs-lookup"><span data-stu-id="8f8d0-143">Writing your code</span></span>

<span data-ttu-id="8f8d0-144">Vamos a empezar a escribir código en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="8f8d0-144">Let's get started by writing some code first.</span></span>  <span data-ttu-id="8f8d0-145">Asegúrese de que el `Program.fs` archivo está abierto y, a continuación, reemplace el contenido con lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8f8d0-145">Make sure that the `Program.fs` file is open, and then replace its contents with the following:</span></span>

[!code-fsharp[HelloSquare](../../../samples/snippets/fsharp/getting-started/hello-square.fs)]

<span data-ttu-id="8f8d0-146">En el ejemplo de código anterior, una función `square` se ha definido que toma una entrada con el nombre `x` y lo multiplica por sí mismo.</span><span class="sxs-lookup"><span data-stu-id="8f8d0-146">In the previous code sample, a function `square` has been defined which takes an input named `x` and multiplies it by itself.</span></span>  <span data-ttu-id="8f8d0-147">Dado que F # utiliza [inferencia](../language-reference/type-inference.md), el tipo de `x` no deben especificarse.</span><span class="sxs-lookup"><span data-stu-id="8f8d0-147">Because F# uses [Type Inference](../language-reference/type-inference.md), the type of `x` doesn't need to be specified.</span></span>  <span data-ttu-id="8f8d0-148">El compilador de F # entiende los tipos donde la multiplicación es válida y se asignará un tipo a `x` en función de cómo `square` se llama.</span><span class="sxs-lookup"><span data-stu-id="8f8d0-148">The F# compiler understands the types where multiplication is valid, and will assign a type to `x` based on how `square` is called.</span></span>  <span data-ttu-id="8f8d0-149">Si mantiene el mouse sobre `square`, debería aparecer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8f8d0-149">If you hover over `square`, you should see the following:</span></span>

```
val square: x:int -> int
```

<span data-ttu-id="8f8d0-150">Esto es lo que se conoce como firma de tipo de la función.</span><span class="sxs-lookup"><span data-stu-id="8f8d0-150">This is what is known as the function's type signature.</span></span>  <span data-ttu-id="8f8d0-151">Puede leerse como el siguiente: "cuadrado es una función que toma un número entero denominado x y genera un número entero".</span><span class="sxs-lookup"><span data-stu-id="8f8d0-151">It can be read like this: "Square is a function which takes an integer named x and produces an integer".</span></span>  <span data-ttu-id="8f8d0-152">Tenga en cuenta que el compilador dio `square` el `int` tipo por ahora - esto es porque no es genérica a través de la multiplicación *todos los* tipos, pero, en su lugar, a través de un conjunto cerrado de tipos, es genérico.</span><span class="sxs-lookup"><span data-stu-id="8f8d0-152">Note that the compiler gave `square` the `int` type for now - this is because multiplication is not generic across *all* types, but rather is generic across a closed set of types.</span></span>  <span data-ttu-id="8f8d0-153">El compilador de F # seleccionado `int` en este punto, pero se ajustará la signatura de tipo si se llama a `square` con otro tipo de entrada, como un `float`.</span><span class="sxs-lookup"><span data-stu-id="8f8d0-153">The F# compiler picked `int` at this point, but it will adjust the type signature if you call `square` with a different input type, such as a `float`.</span></span>

<span data-ttu-id="8f8d0-154">Otra función, `main`, se define, que se decora con el `EntryPoint` atributo para indicar al compilador de F # ejecución del programa debe empezar por ahí.</span><span class="sxs-lookup"><span data-stu-id="8f8d0-154">Another function, `main`, is defined, which is decorated with the `EntryPoint` attribute to tell the F# compiler that program execution should start there.</span></span>  <span data-ttu-id="8f8d0-155">Sigue la misma convención que otro [lenguajes de programación de estilo C](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), donde los argumentos de línea de comandos se pueden pasar a esta función y se devuelve un código entero (normalmente `0`).</span><span class="sxs-lookup"><span data-stu-id="8f8d0-155">It follows the same convention as other [C-style programming languages](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), where command-line arguments can be passed to this function, and an integer code is returned (typically `0`).</span></span>

<span data-ttu-id="8f8d0-156">Se encuentra en esta función que se llame a la `square` función con un argumento de `12`.</span><span class="sxs-lookup"><span data-stu-id="8f8d0-156">It is in this function that we call the `square` function with an argument of `12`.</span></span>  <span data-ttu-id="8f8d0-157">El compilador de F #, a continuación, asigna el tipo de `square` como `int -> int` (es decir, una función que toma un `int` y genera un `int`).</span><span class="sxs-lookup"><span data-stu-id="8f8d0-157">The F# compiler then assigns the type of `square` to be `int -> int` (that is, a function which takes an `int` and produces an `int`).</span></span>  <span data-ttu-id="8f8d0-158">La llamada a `printfn` es una función de impresión con formato que usa una cadena de formato, similar a los lenguajes de programación de estilo C, los parámetros que corresponden a los indicados en la cadena de formato y, a continuación, se imprime el resultado y una nueva línea.</span><span class="sxs-lookup"><span data-stu-id="8f8d0-158">The call to `printfn` is a formatted printing function which uses a format string, similar to C-style programming languages, parameters which correspond to those specified in the format string, and then prints the result and a new line.</span></span>

## <a name="running-your-code"></a><span data-ttu-id="8f8d0-159">Ejecución del código</span><span class="sxs-lookup"><span data-stu-id="8f8d0-159">Running your code</span></span>

<span data-ttu-id="8f8d0-160">Puede ejecutar el código y ver resultados presionando **ctrl-f5**.</span><span class="sxs-lookup"><span data-stu-id="8f8d0-160">You can run the code and see results by pressing **ctrl-f5**.</span></span>  <span data-ttu-id="8f8d0-161">Esto ejecutará el programa sin depurar y le permite ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="8f8d0-161">This will run the program without debugging and allows you to see the results.</span></span>  <span data-ttu-id="8f8d0-162">Como alternativa, puede elegir la **depurar** menú de nivel superior de elementos en Visual Studio y elija **iniciar sin depurar**.</span><span class="sxs-lookup"><span data-stu-id="8f8d0-162">Alternatively, you can choose the **Debug** top-level menu item in Visual Studio and choose **Start Without Debugging**.</span></span>

<span data-ttu-id="8f8d0-163">Ahora debería aparecer el siguiente imprime en la ventana de consola que aparecieron Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="8f8d0-163">You should now see the following printed to the console window that Visual Studio popped up:</span></span>

```
12 squared is 144!
```

<span data-ttu-id="8f8d0-164">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="8f8d0-164">Congratulations!</span></span>  <span data-ttu-id="8f8d0-165">Ha creado su primer proyecto de F # en Visual Studio, escribe que una función de F # imprime los resultados de la llamada a esa función y ejecute el proyecto para ver algunos resultados.</span><span class="sxs-lookup"><span data-stu-id="8f8d0-165">You've created your first F# project in Visual Studio, written an F# function printed the results of calling that function, and run the project to see some results.</span></span>

## <a name="using-f-interactive"></a><span data-ttu-id="8f8d0-166">Uso de F # Interactive</span><span class="sxs-lookup"><span data-stu-id="8f8d0-166">Using F# Interactive</span></span>

<span data-ttu-id="8f8d0-167">Una de las mejores características de la Visual F # herramientas en Visual Studio es la ventana interactiva de F #.</span><span class="sxs-lookup"><span data-stu-id="8f8d0-167">One of the best features of the Visual F# tooling in Visual Studio is the F# Interactive Window.</span></span>  <span data-ttu-id="8f8d0-168">Permite enviar código a través a un proceso donde puede llamar a ese código y ver el resultado de forma interactiva.</span><span class="sxs-lookup"><span data-stu-id="8f8d0-168">It allows you to send code over to a process where you can call that code and see the result interactively.</span></span>

<span data-ttu-id="8f8d0-169">Para empezar a usarlo, resalte el `square` función definida en el código.</span><span class="sxs-lookup"><span data-stu-id="8f8d0-169">To begin using it, highlight the `square` function defined in your code.</span></span>  <span data-ttu-id="8f8d0-170">A continuación, mantenga presionada la **Alt** clave y presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="8f8d0-170">Next, hold the **Alt** key and press **Enter**.</span></span>  <span data-ttu-id="8f8d0-171">Esto ejecuta el código en la ventana interactiva de F #.</span><span class="sxs-lookup"><span data-stu-id="8f8d0-171">This executes the code in the F# Interactive Window.</span></span>  <span data-ttu-id="8f8d0-172">Debe aparecer la ventana interactiva de F # con lo siguiente en él:</span><span class="sxs-lookup"><span data-stu-id="8f8d0-172">You should see the F# Interactive Window appear with the following in it:</span></span>

```
>

val square : x:int -> int

>
```

<span data-ttu-id="8f8d0-173">Esto muestra la misma firma de función para el `square` función, que vio anteriormente cuando mantiene el mouse sobre la función.</span><span class="sxs-lookup"><span data-stu-id="8f8d0-173">This shows the same function signature for the `square` function, which you saw earlier when you hovered over the function.</span></span>  <span data-ttu-id="8f8d0-174">Dado que `square` es ahora definido en el proceso de F # Interactive, se puede llamar con valores diferentes:</span><span class="sxs-lookup"><span data-stu-id="8f8d0-174">Because `square` is now defined in the F# Interactive process, you can call it with different values:</span></span>

```
> square 12;;
val it : int = 144
>square 13;;
val it : int = 169
```

<span data-ttu-id="8f8d0-175">Esto ejecuta la función, se enlaza el resultado a un nuevo nombre `it`y muestra el tipo y el valor de `it`.</span><span class="sxs-lookup"><span data-stu-id="8f8d0-175">This executes the function, binds the result to a new name `it`, and displays the type and value of `it`.</span></span>  <span data-ttu-id="8f8d0-176">Tenga en cuenta que debe finalizar cada línea con `;;`.</span><span class="sxs-lookup"><span data-stu-id="8f8d0-176">Note that you must terminate each line with `;;`.</span></span>  <span data-ttu-id="8f8d0-177">Se trata cómo F # Interactive sabe cuando finalice la llamada de función.</span><span class="sxs-lookup"><span data-stu-id="8f8d0-177">This is how F# Interactive knows when your function call is finished.</span></span>  <span data-ttu-id="8f8d0-178">También puede definir nuevas funciones en F # Interactive:</span><span class="sxs-lookup"><span data-stu-id="8f8d0-178">You can also define new functions in F# Interactive:</span></span>

```
> let isOdd x = x % 2 <> 0;;

val isOdd : x:int -> bool

> isOdd 12;;
val it : bool = false
```

<span data-ttu-id="8f8d0-179">Los pasos anteriores, define una nueva función, `isOdd`, que toma un `int` y comprueba si es impar.</span><span class="sxs-lookup"><span data-stu-id="8f8d0-179">The above defines a new function, `isOdd`, which takes an `int` and checks to see if it's odd!</span></span> <span data-ttu-id="8f8d0-180">Puede llamar a esta función para ver lo que devuelve con diferentes entradas.</span><span class="sxs-lookup"><span data-stu-id="8f8d0-180">You can call this function to see what it returns with different inputs.</span></span>  <span data-ttu-id="8f8d0-181">Puede llamar a funciones dentro de las llamadas a funciones:</span><span class="sxs-lookup"><span data-stu-id="8f8d0-181">You can call functions within function calls:</span></span>

```
> isOdd (square 15);;
val it : bool = true
```

<span data-ttu-id="8f8d0-182">También puede usar el [operador de canalización hacia delante](../language-reference/symbol-and-operator-reference/index.md) debe canalizar el valor en las dos funciones:</span><span class="sxs-lookup"><span data-stu-id="8f8d0-182">You can also use the [pipe-forward operator](../language-reference/symbol-and-operator-reference/index.md) to pipeline the value into the two functions:</span></span>

```
> 15 |> square |> isOdd;;
val it : bool = true
```

<span data-ttu-id="8f8d0-183">El operador de canalización hacia delante etc., se tratan en los tutoriales posteriores.</span><span class="sxs-lookup"><span data-stu-id="8f8d0-183">The pipe-forward operator, and more, are covered in later tutorials.</span></span>

<span data-ttu-id="8f8d0-184">Esto es sólo un vistazo a lo que puede hacer con F # Interactive.</span><span class="sxs-lookup"><span data-stu-id="8f8d0-184">This is only a glimpse into what you can do with F# Interactive.</span></span> <span data-ttu-id="8f8d0-185">Para obtener más información, visite [programación interactiva con F #](../tutorials/fsharp-interactive/index.md).</span><span class="sxs-lookup"><span data-stu-id="8f8d0-185">To learn more, check out [Interactive Programming with F#](../tutorials/fsharp-interactive/index.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="8f8d0-186">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="8f8d0-186">Next steps</span></span>

<span data-ttu-id="8f8d0-187">Si no lo ha hecho ya, consulte el [paseo de F #](../tour.md), donde abordan algunas de las características principales del lenguaje F #.</span><span class="sxs-lookup"><span data-stu-id="8f8d0-187">If you haven't already, check out the [Tour of F#](../tour.md), which covers some of the core features of the F# language.</span></span>  <span data-ttu-id="8f8d0-188">Se ofrece una visión general de algunas de las capacidades de F # y se proporcionan ejemplos de código de un amplio que puede copiar en Visual Studio y ejecutar.</span><span class="sxs-lookup"><span data-stu-id="8f8d0-188">It will give you an overview of some of the capabilities of F#, and provide ample code samples that you can copy into Visual Studio and run.</span></span>  <span data-ttu-id="8f8d0-189">También hay algunos recursos externos excelentes que puede utilizar, exhibió en el [Guía de F #](../index.md).</span><span class="sxs-lookup"><span data-stu-id="8f8d0-189">There are also some great external resources you can use, showcased in the [F# Guide](../index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8f8d0-190">Vea también</span><span class="sxs-lookup"><span data-stu-id="8f8d0-190">See also</span></span>
 [<span data-ttu-id="8f8d0-191">Visual F#</span><span class="sxs-lookup"><span data-stu-id="8f8d0-191">Visual F#</span></span>](index.md)  
 [<span data-ttu-id="8f8d0-192">Paseo por F</span><span class="sxs-lookup"><span data-stu-id="8f8d0-192">Tour of F#</span></span>](../tour.md)  
 [<span data-ttu-id="8f8d0-193">Referencia del lenguaje F #</span><span class="sxs-lookup"><span data-stu-id="8f8d0-193">F# language reference</span></span>](../language-reference/index.md)  
 [<span data-ttu-id="8f8d0-194">Inferencia de tipos</span><span class="sxs-lookup"><span data-stu-id="8f8d0-194">Type inference</span></span>](../language-reference/type-inference.md)  
 [<span data-ttu-id="8f8d0-195">Referencia de símbolos y el operador</span><span class="sxs-lookup"><span data-stu-id="8f8d0-195">Symbol and operator reference</span></span>](../language-reference/symbol-and-operator-reference/index.md)  
