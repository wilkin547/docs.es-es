---
title: Introducción a F# en Visual Studio
description: Obtenga información sobre cómo F# usar con Visual Studio.
ms.date: 12/20/2019
ms.openlocfilehash: 9bf47fb08ea3df0aa0d5064043d94f030d45d568
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75337344"
---
# <a name="get-started-with-f-in-visual-studio"></a><span data-ttu-id="094e4-103">Introducción a F# en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="094e4-103">Get started with F# in Visual Studio</span></span>

<span data-ttu-id="094e4-104">F#y las herramientas F# visuales se admiten en el entorno de desarrollo integrado (IDE) de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="094e4-104">F# and the Visual F# tooling are supported in the Visual Studio integrated development environment (IDE).</span></span>

<span data-ttu-id="094e4-105">Para empezar, asegúrese de que tiene [Visual Studio instalado con F# compatibilidad](install-fsharp.md#install-f-with-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="094e4-105">To begin, ensure that you have [Visual Studio installed with F# support](install-fsharp.md#install-f-with-visual-studio).</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="094e4-106">Creación de una aplicación de consola</span><span class="sxs-lookup"><span data-stu-id="094e4-106">Create a console application</span></span>

<span data-ttu-id="094e4-107">Uno de los proyectos más básicos de Visual Studio es la aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="094e4-107">One of the most basic projects in Visual Studio is the console app.</span></span> <span data-ttu-id="094e4-108">Aquí se muestra cómo crear uno:</span><span class="sxs-lookup"><span data-stu-id="094e4-108">Here's how to create one:</span></span>

1. <span data-ttu-id="094e4-109">Abra Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="094e4-109">Open Visual Studio 2019.</span></span>

2. <span data-ttu-id="094e4-110">En la ventana de inicio, elija **Crear un proyecto nuevo**.</span><span class="sxs-lookup"><span data-stu-id="094e4-110">On the start window, choose **Create a new project**.</span></span>

3. <span data-ttu-id="094e4-111">En la página **crear un nuevo proyecto** , elija **F#** en la lista idioma.</span><span class="sxs-lookup"><span data-stu-id="094e4-111">On the **Create a new project** page, choose **F#** from the Language list.</span></span>

4. <span data-ttu-id="094e4-112">Seleccione la plantilla **aplicación de consola (.net Core)** y, a continuación, elija **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="094e4-112">Choose the **Console App (.NET Core)** template, and then choose **Next**.</span></span>

5. <span data-ttu-id="094e4-113">En la página **configurar el nuevo proyecto** , escriba un nombre en el cuadro **nombre del proyecto** .</span><span class="sxs-lookup"><span data-stu-id="094e4-113">On the **Configure your new project** page, enter a name in the **Project name** box.</span></span> <span data-ttu-id="094e4-114">Luego, elija **Crear**.</span><span class="sxs-lookup"><span data-stu-id="094e4-114">Then, choose **Create**.</span></span>

   <span data-ttu-id="094e4-115">Visual Studio crea el nuevo F# proyecto.</span><span class="sxs-lookup"><span data-stu-id="094e4-115">Visual Studio creates the new F# project.</span></span> <span data-ttu-id="094e4-116">Puede verlo en la ventana Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="094e4-116">You can see it in the Solution Explorer window.</span></span>

## <a name="write-the-code"></a><span data-ttu-id="094e4-117">Escribir el código</span><span class="sxs-lookup"><span data-stu-id="094e4-117">Write the code</span></span>

<span data-ttu-id="094e4-118">Comencemos por escribir código.</span><span class="sxs-lookup"><span data-stu-id="094e4-118">Let's get started by writing some code.</span></span> <span data-ttu-id="094e4-119">Asegúrese de que el archivo de `Program.fs` está abierto y, a continuación, reemplace el contenido por lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="094e4-119">Make sure that the `Program.fs` file is open, and then replace its contents with the following:</span></span>

[!code-fsharp[HelloSquare](~/samples/snippets/fsharp/getting-started/hello-square.fs)]

<span data-ttu-id="094e4-120">En el ejemplo de código anterior se define una función llamada `square` que toma una entrada denominada `x` y la multiplica por sí misma.</span><span class="sxs-lookup"><span data-stu-id="094e4-120">The previous code sample defines a function called `square` that takes an input named `x` and multiplies it by itself.</span></span> <span data-ttu-id="094e4-121">Dado F# que utiliza la [inferencia de tipos](../language-reference/type-inference.md), no es necesario especificar el tipo de `x`.</span><span class="sxs-lookup"><span data-stu-id="094e4-121">Because F# uses [Type inference](../language-reference/type-inference.md), the type of `x` doesn't need to be specified.</span></span> <span data-ttu-id="094e4-122">El F# compilador entiende los tipos en los que la multiplicación es válida y asigna un tipo a `x` en función de cómo se llama a `square`.</span><span class="sxs-lookup"><span data-stu-id="094e4-122">The F# compiler understands the types where multiplication is valid and assigns a type to `x` based on how `square` is called.</span></span> <span data-ttu-id="094e4-123">Si mantiene el mouse sobre `square`, debería ver lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="094e4-123">If you hover over `square`, you should see the following:</span></span>

```fsharp
val square: x:int -> int
```

<span data-ttu-id="094e4-124">Esto es lo que se conoce como la firma de tipo de la función.</span><span class="sxs-lookup"><span data-stu-id="094e4-124">This is what is known as the function's type signature.</span></span> <span data-ttu-id="094e4-125">Se puede leer de la siguiente manera: "Square es una función que toma un entero denominado x y genera un entero".</span><span class="sxs-lookup"><span data-stu-id="094e4-125">It can be read like this: "Square is a function that takes an integer named x and produces an integer".</span></span> <span data-ttu-id="094e4-126">El compilador dio `square` el tipo de `int` por ahora; Esto se debe a que la multiplicación no es genérica en *todos los* tipos, sino en un conjunto cerrado de tipos.</span><span class="sxs-lookup"><span data-stu-id="094e4-126">The compiler gave `square` the `int` type for now; this is because multiplication is not generic across *all* types but rather a closed set of types.</span></span> <span data-ttu-id="094e4-127">El F# compilador ajustará la firma de tipo si llama a `square` con un tipo de entrada diferente, como un `float`.</span><span class="sxs-lookup"><span data-stu-id="094e4-127">The F# compiler will adjust the type signature if you call `square` with a different input type, such as a `float`.</span></span>

<span data-ttu-id="094e4-128">Otra función, `main`, se define, que está decorada con el atributo `EntryPoint`.</span><span class="sxs-lookup"><span data-stu-id="094e4-128">Another function, `main`, is defined, which is decorated with the `EntryPoint` attribute.</span></span> <span data-ttu-id="094e4-129">Este atributo indica al F# compilador que la ejecución del programa debe comenzar allí.</span><span class="sxs-lookup"><span data-stu-id="094e4-129">This attribute tells the F# compiler that program execution should start there.</span></span> <span data-ttu-id="094e4-130">Sigue la misma Convención que otros [lenguajes de programación de estilo C](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), donde se pueden pasar argumentos de línea de comandos a esta función y se devuelve un código entero (normalmente `0`).</span><span class="sxs-lookup"><span data-stu-id="094e4-130">It follows the same convention as other [C-style programming languages](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), where command-line arguments can be passed to this function, and an integer code is returned (typically `0`).</span></span>

<span data-ttu-id="094e4-131">Está en la función de punto de entrada, `main`, que llama a la función de `square` con un argumento de `12`.</span><span class="sxs-lookup"><span data-stu-id="094e4-131">It is in the entry point function, `main`, that you call the `square` function with an argument of `12`.</span></span> <span data-ttu-id="094e4-132">A F# continuación, el compilador asigna el tipo de `square` que se va a `int -> int` (es decir, una función que toma un `int` y genera un `int`).</span><span class="sxs-lookup"><span data-stu-id="094e4-132">The F# compiler then assigns the type of `square` to be `int -> int` (that is, a function that takes an `int` and produces an `int`).</span></span> <span data-ttu-id="094e4-133">La llamada a `printfn` es una función de impresión con formato que usa una cadena de formato e imprime el resultado (y una nueva línea).</span><span class="sxs-lookup"><span data-stu-id="094e4-133">The call to `printfn` is a formatted printing function that uses a format string and prints the result (and a new line).</span></span> <span data-ttu-id="094e4-134">La cadena de formato, similar a los lenguajes de programación de estilo C, tiene parámetros (`%d`) que corresponden a los argumentos que se le pasan, en este caso `12` y `(square 12)`.</span><span class="sxs-lookup"><span data-stu-id="094e4-134">The format string, similar to C-style programming languages, has parameters (`%d`) that correspond to the arguments that are passed to it, in this case, `12` and `(square 12)`.</span></span>

## <a name="run-the-code"></a><span data-ttu-id="094e4-135">Ejecución del código</span><span class="sxs-lookup"><span data-stu-id="094e4-135">Run the code</span></span>

<span data-ttu-id="094e4-136">Puede ejecutar el código y ver los resultados presionando **Ctrl**+**F5**.</span><span class="sxs-lookup"><span data-stu-id="094e4-136">You can run the code and see the results by pressing **Ctrl**+**F5**.</span></span> <span data-ttu-id="094e4-137">Como alternativa, puede elegir el > de **depurar** **iniciar sin depurar** en la barra de menús de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="094e4-137">Alternatively, you can choose the **Debug** > **Start Without Debugging** from the top-level menu bar.</span></span> <span data-ttu-id="094e4-138">Esto ejecuta el programa sin depuración.</span><span class="sxs-lookup"><span data-stu-id="094e4-138">This runs the program without debugging.</span></span>

<span data-ttu-id="094e4-139">El siguiente resultado se imprime en la ventana de la consola que abrió Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="094e4-139">The following output prints to the console window that Visual Studio opened:</span></span>

```console
12 squared is: 144!
```

<span data-ttu-id="094e4-140">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="094e4-140">Congratulations!</span></span> <span data-ttu-id="094e4-141">Ha creado su primer F# proyecto en Visual Studio, ha escrito una F# función que calcula e imprime un valor y ejecuta el proyecto para ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="094e4-141">You've created your first F# project in Visual Studio, written an F# function that calculates and prints a value, and run the project to see the results.</span></span>

## <a name="next-steps"></a><span data-ttu-id="094e4-142">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="094e4-142">Next steps</span></span>

<span data-ttu-id="094e4-143">Si no lo ha hecho ya, consulte el [paseo F# ](../tour.md)por, que cubre algunas de las características principales del F# lenguaje.</span><span class="sxs-lookup"><span data-stu-id="094e4-143">If you haven't already, check out the [Tour of F#](../tour.md), which covers some of the core features of the F# language.</span></span> <span data-ttu-id="094e4-144">Proporciona información general sobre algunas de las funcionalidades de F# y ejemplos de código que puede copiar en Visual Studio y ejecutar.</span><span class="sxs-lookup"><span data-stu-id="094e4-144">It provides an overview of some of the capabilities of F# and ample code samples that you can copy into Visual Studio and run.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="094e4-145">Paseo por F</span><span class="sxs-lookup"><span data-stu-id="094e4-145">Tour of F#</span></span>](../tour.md)

## <a name="see-also"></a><span data-ttu-id="094e4-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="094e4-146">See also</span></span>

- [<span data-ttu-id="094e4-147">F#Referencia del lenguaje</span><span class="sxs-lookup"><span data-stu-id="094e4-147">F# language reference</span></span>](../language-reference/index.md)
- [<span data-ttu-id="094e4-148">Inferencia de tipos</span><span class="sxs-lookup"><span data-stu-id="094e4-148">Type inference</span></span>](../language-reference/type-inference.md)
- [<span data-ttu-id="094e4-149">Referencia de símbolos y operadores</span><span class="sxs-lookup"><span data-stu-id="094e4-149">Symbol and operator reference</span></span>](../language-reference/symbol-and-operator-reference/index.md)
