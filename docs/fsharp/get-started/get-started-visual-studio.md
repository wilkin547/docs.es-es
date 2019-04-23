---
title: Introducción a F# en Visual Studio
description: Aprenda a usar F# con Visual Studio.
ms.date: 07/03/2018
ms.openlocfilehash: 020e5d32b3aa5d5a2195c19d70d8fe684fbd56ef
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59331915"
---
# <a name="get-started-with-f-in-visual-studio"></a><span data-ttu-id="a8c1c-103">Introducción a F# en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a8c1c-103">Get started with F# in Visual Studio</span></span>

<span data-ttu-id="a8c1c-104">F#y el objeto Visual F# se admiten las herramientas del IDE de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a8c1c-104">F# and the Visual F# tooling are supported in the Visual Studio IDE.</span></span>

<span data-ttu-id="a8c1c-105">Para empezar, asegúrese de que tiene [instaladas de Visual Studio con F# ](install-fsharp.md#install-f-with-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="a8c1c-105">To begin, ensure that you have [Visual Studio installed with F#](install-fsharp.md#install-f-with-visual-studio).</span></span>

## <a name="creating-a-console-application"></a><span data-ttu-id="a8c1c-106">Creación de una aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="a8c1c-106">Creating a console application</span></span>

<span data-ttu-id="a8c1c-107">Uno de los proyectos en Visual Studio más básicos es la aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="a8c1c-107">One of the most basic projects in Visual Studio is the Console Application.</span></span>  <span data-ttu-id="a8c1c-108">A continuación le mostramos cómo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="a8c1c-108">Here's how to do it.</span></span>  <span data-ttu-id="a8c1c-109">Una vez abierto Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="a8c1c-109">Once Visual Studio is open:</span></span>

1. <span data-ttu-id="a8c1c-110">En el **archivo** menú, elija **New**y, a continuación, elija **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="a8c1c-110">On the **File** menu, point to **New**, and then choose **Project**.</span></span>

2. <span data-ttu-id="a8c1c-111">En el nuevo proyecto en el cuadro de diálogo, **plantillas**, debería ver **Visual F#** .</span><span class="sxs-lookup"><span data-stu-id="a8c1c-111">In the New Project dialog, under **Templates**, you should see **Visual F#**.</span></span>  <span data-ttu-id="a8c1c-112">Elija esta opción para mostrar el F# plantillas.</span><span class="sxs-lookup"><span data-stu-id="a8c1c-112">Choose this to show the F# templates.</span></span>

3. <span data-ttu-id="a8c1c-113">Seleccione **aplicación de consola de .NET Core** o **aplicación de consola**.</span><span class="sxs-lookup"><span data-stu-id="a8c1c-113">Select either **.NET Core Console app** or **Console app**.</span></span>

3. <span data-ttu-id="a8c1c-114">Elija la **bien** botón para crear el F# proyecto!</span><span class="sxs-lookup"><span data-stu-id="a8c1c-114">Choose the **Okay** button to create the F# project!</span></span>  <span data-ttu-id="a8c1c-115">Ahora debería ver un F# proyecto en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="a8c1c-115">You should now see an F# project in the Solution Explorer.</span></span>

## <a name="writing-your-code"></a><span data-ttu-id="a8c1c-116">Escribir el código</span><span class="sxs-lookup"><span data-stu-id="a8c1c-116">Writing your code</span></span>

<span data-ttu-id="a8c1c-117">Vamos a empezar a escribir código en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="a8c1c-117">Let's get started by writing some code first.</span></span>  <span data-ttu-id="a8c1c-118">Asegúrese de que el `Program.fs` archivo está abierto y, a continuación, reemplace su contenido por lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a8c1c-118">Make sure that the `Program.fs` file is open, and then replace its contents with the following:</span></span>

[!code-fsharp[HelloSquare](../../../samples/snippets/fsharp/getting-started/hello-square.fs)]

<span data-ttu-id="a8c1c-119">En el ejemplo de código anterior, una función `square` se ha definido que toma una entrada denominada `x` y lo multiplica por sí mismo.</span><span class="sxs-lookup"><span data-stu-id="a8c1c-119">In the previous code sample, a function `square` has been defined which takes an input named `x` and multiplies it by itself.</span></span>  <span data-ttu-id="a8c1c-120">Dado que F# usa [inferencia](../language-reference/type-inference.md), el tipo de `x` no deben especificarse.</span><span class="sxs-lookup"><span data-stu-id="a8c1c-120">Because F# uses [Type Inference](../language-reference/type-inference.md), the type of `x` doesn't need to be specified.</span></span>  <span data-ttu-id="a8c1c-121">El F# compilador entiende los tipos que es válida la multiplicación y asignará un tipo a `x` según cómo `square` se llama.</span><span class="sxs-lookup"><span data-stu-id="a8c1c-121">The F# compiler understands the types where multiplication is valid, and will assign a type to `x` based on how `square` is called.</span></span>  <span data-ttu-id="a8c1c-122">Si se mantiene el mouse sobre `square`, debería aparecer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a8c1c-122">If you hover over `square`, you should see the following:</span></span>

```
val square: x:int -> int
```

<span data-ttu-id="a8c1c-123">Esto es lo que se conoce como la firma del tipo de la función.</span><span class="sxs-lookup"><span data-stu-id="a8c1c-123">This is what is known as the function's type signature.</span></span>  <span data-ttu-id="a8c1c-124">Se puede leer como esta: "Cuadrado es una función que toma un número entero denominado x y genera un número entero".</span><span class="sxs-lookup"><span data-stu-id="a8c1c-124">It can be read like this: "Square is a function which takes an integer named x and produces an integer".</span></span>  <span data-ttu-id="a8c1c-125">Tenga en cuenta que el compilador proporcionaba `square` el `int` tipo por ahora: Esto es porque no es genérica a través de la multiplicación *todas* tipos, pero es bastante genérico a través de un conjunto cerrado de tipos.</span><span class="sxs-lookup"><span data-stu-id="a8c1c-125">Note that the compiler gave `square` the `int` type for now - this is because multiplication is not generic across *all* types, but rather is generic across a closed set of types.</span></span>  <span data-ttu-id="a8c1c-126">El F# compilador seleccionada `int` en este punto, pero se ajustará la firma del tipo si se llama a `square` con otro tipo de entrada, como un `float`.</span><span class="sxs-lookup"><span data-stu-id="a8c1c-126">The F# compiler picked `int` at this point, but it will adjust the type signature if you call `square` with a different input type, such as a `float`.</span></span>

<span data-ttu-id="a8c1c-127">Otra función `main`, se define, que está decorada con el `EntryPoint` atributo para indicar el F# compilador que la ejecución del programa debe empezar por ahí.</span><span class="sxs-lookup"><span data-stu-id="a8c1c-127">Another function, `main`, is defined, which is decorated with the `EntryPoint` attribute to tell the F# compiler that program execution should start there.</span></span>  <span data-ttu-id="a8c1c-128">Sigue la misma convención que otros [lenguajes de programación de estilo C](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), donde se pueden pasar argumentos de línea de comandos a esta función y se devuelve un código entero (normalmente `0`).</span><span class="sxs-lookup"><span data-stu-id="a8c1c-128">It follows the same convention as other [C-style programming languages](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), where command-line arguments can be passed to this function, and an integer code is returned (typically `0`).</span></span>

<span data-ttu-id="a8c1c-129">Se encuentra en esta función que llamamos el `square` función con un argumento de `12`.</span><span class="sxs-lookup"><span data-stu-id="a8c1c-129">It is in this function that we call the `square` function with an argument of `12`.</span></span>  <span data-ttu-id="a8c1c-130">El F# compilador, a continuación, asigna el tipo de `square` sea `int -> int` (es decir, una función que toma un `int` y genera un `int`).</span><span class="sxs-lookup"><span data-stu-id="a8c1c-130">The F# compiler then assigns the type of `square` to be `int -> int` (that is, a function which takes an `int` and produces an `int`).</span></span>  <span data-ttu-id="a8c1c-131">La llamada a `printfn` es una función de impresión con formato que usa una cadena de formato, similar a lenguajes de programación de estilo C, los parámetros que corresponden a los especificados en la cadena de formato y, a continuación, imprime el resultado y una nueva línea.</span><span class="sxs-lookup"><span data-stu-id="a8c1c-131">The call to `printfn` is a formatted printing function which uses a format string, similar to C-style programming languages, parameters which correspond to those specified in the format string, and then prints the result and a new line.</span></span>

## <a name="running-your-code"></a><span data-ttu-id="a8c1c-132">Ejecución del código</span><span class="sxs-lookup"><span data-stu-id="a8c1c-132">Running your code</span></span>

<span data-ttu-id="a8c1c-133">Puede ejecutar el código y ver resultados presionando **Ctrl**+**F5**.</span><span class="sxs-lookup"><span data-stu-id="a8c1c-133">You can run the code and see results by pressing **Ctrl**+**F5**.</span></span>  <span data-ttu-id="a8c1c-134">Esto ejecuta el programa sin depurarlo y le permite ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="a8c1c-134">This runs the program without debugging and allows you to see the results.</span></span>  <span data-ttu-id="a8c1c-135">Como alternativa, puede elegir el **depurar** en Visual Studio de elemento de menú de nivel superior y elija **iniciar sin depurar**.</span><span class="sxs-lookup"><span data-stu-id="a8c1c-135">Alternatively, you can choose the **Debug** top-level menu item in Visual Studio and choose **Start Without Debugging**.</span></span>

<span data-ttu-id="a8c1c-136">Ahora debería ver lo siguiente que se imprimen en la ventana de consola que apareció Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="a8c1c-136">You should now see the following printed to the console window that Visual Studio popped up:</span></span>

```
12 squared is 144!
```

<span data-ttu-id="a8c1c-137">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="a8c1c-137">Congratulations!</span></span>  <span data-ttu-id="a8c1c-138">Ha creado su primer F# proyecto en Visual Studio, escribe un F# función imprime los resultados de llamar a función y ejecutar el proyecto para ver algunos resultados.</span><span class="sxs-lookup"><span data-stu-id="a8c1c-138">You've created your first F# project in Visual Studio, written an F# function printed the results of calling that function, and run the project to see some results.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a8c1c-139">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="a8c1c-139">Next steps</span></span>

<span data-ttu-id="a8c1c-140">Si no lo ha hecho ya, consulte el [paseo F# ](../tour.md), donde abordan algunas de las características principales de la F# lenguaje.</span><span class="sxs-lookup"><span data-stu-id="a8c1c-140">If you haven't already, check out the [Tour of F#](../tour.md), which covers some of the core features of the F# language.</span></span>  <span data-ttu-id="a8c1c-141">Se le ofrecerá una visión general de algunas de las capacidades de F#y proporcionan ejemplos de código suficiente que puede copiar en Visual Studio y ejecutar.</span><span class="sxs-lookup"><span data-stu-id="a8c1c-141">It will give you an overview of some of the capabilities of F#, and provide ample code samples that you can copy into Visual Studio and run.</span></span>  <span data-ttu-id="a8c1c-142">También hay algunos excelentes recursos externos, puede usar, exhibió en el [ F# guía](../index.md).</span><span class="sxs-lookup"><span data-stu-id="a8c1c-142">There are also some great external resources you can use, showcased in the [F# Guide](../index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a8c1c-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8c1c-143">See also</span></span>

- [<span data-ttu-id="a8c1c-144">Paseo por F</span><span class="sxs-lookup"><span data-stu-id="a8c1c-144">Tour of F#</span></span>](../tour.md)
- [<span data-ttu-id="a8c1c-145">F#referencia del lenguaje</span><span class="sxs-lookup"><span data-stu-id="a8c1c-145">F# language reference</span></span>](../language-reference/index.md)
- [<span data-ttu-id="a8c1c-146">Inferencia de tipos</span><span class="sxs-lookup"><span data-stu-id="a8c1c-146">Type inference</span></span>](../language-reference/type-inference.md)
- [<span data-ttu-id="a8c1c-147">Referencia de símbolos y el operador</span><span class="sxs-lookup"><span data-stu-id="a8c1c-147">Symbol and operator reference</span></span>](../language-reference/symbol-and-operator-reference/index.md)
