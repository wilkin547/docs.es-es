---
title: Funciones
description: Obtenga información sobre las funciones de F# y cómo F# admite las construcciones más comunes de la programación funcional.
ms.date: 05/16/2016
ms.openlocfilehash: e49183e0634dee1750757abadbfe9e9c824f51a8
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596479"
---
# <a name="functions"></a><span data-ttu-id="0cd72-103">Funciones</span><span class="sxs-lookup"><span data-stu-id="0cd72-103">Functions</span></span>

<span data-ttu-id="0cd72-104">Las funciones son la unidad fundamental de la ejecución del programa en cualquier lenguaje de programación.</span><span class="sxs-lookup"><span data-stu-id="0cd72-104">Functions are the fundamental unit of program execution in any programming language.</span></span> <span data-ttu-id="0cd72-105">Al igual que en otros lenguajes, una función de F# tiene un nombre, puede tener parámetros y tomar argumentos, y tiene un cuerpo.</span><span class="sxs-lookup"><span data-stu-id="0cd72-105">As in other languages, an F# function has a name, can have parameters and take arguments, and has a body.</span></span> <span data-ttu-id="0cd72-106">F# también admite construcciones de programación funcional como el tratamiento de las funciones como valores, el uso de funciones sin nombre en expresiones, la composición de funciones para crear nuevas funciones, funciones currificadas y la definición implícita de funciones mediante la aplicación parcial de argumentos de función.</span><span class="sxs-lookup"><span data-stu-id="0cd72-106">F# also supports functional programming constructs such as treating functions as values, using unnamed functions in expressions, composition of functions to form new functions, curried functions, and the implicit definition of functions by way of the partial application of function arguments.</span></span>

<span data-ttu-id="0cd72-107">Las funciones se definen mediante la palabra clave `let`, o bien, si la función es recursiva, la combinación de palabras clave `let rec`.</span><span class="sxs-lookup"><span data-stu-id="0cd72-107">You define functions by using the `let` keyword, or, if the function is recursive, the `let rec` keyword combination.</span></span>

## <a name="syntax"></a><span data-ttu-id="0cd72-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0cd72-108">Syntax</span></span>

```fsharp
// Non-recursive function definition.
let [inline] function-name parameter-list [ : return-type ] = function-body
// Recursive function definition.
let rec function-name parameter-list = recursive-function-body
```

## <a name="remarks"></a><span data-ttu-id="0cd72-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0cd72-109">Remarks</span></span>

<span data-ttu-id="0cd72-110">El *nombre de la función* es un identificador que representa la función.</span><span class="sxs-lookup"><span data-stu-id="0cd72-110">The *function-name* is an identifier that represents the function.</span></span> <span data-ttu-id="0cd72-111">La *lista de parámetros* consta de parámetros sucesivos separados por espacios.</span><span class="sxs-lookup"><span data-stu-id="0cd72-111">The *parameter-list* consists of successive parameters that are separated by spaces.</span></span> <span data-ttu-id="0cd72-112">Se puede especificar un tipo explícito para cada parámetro, tal como se describe en la sección Parámetros.</span><span class="sxs-lookup"><span data-stu-id="0cd72-112">You can specify an explicit type for each parameter, as described in the Parameters section.</span></span> <span data-ttu-id="0cd72-113">Si no se especifica un tipo de argumento concreto, el compilador intenta deducir el tipo del cuerpo de la función.</span><span class="sxs-lookup"><span data-stu-id="0cd72-113">If you do not specify a specific argument type, the compiler attempts to infer the type from the function body.</span></span> <span data-ttu-id="0cd72-114">El *cuerpo de la función* consta de una expresión.</span><span class="sxs-lookup"><span data-stu-id="0cd72-114">The *function-body* consists of an expression.</span></span> <span data-ttu-id="0cd72-115">La expresión que forma el cuerpo de la función suele ser una expresión compuesta formada por varias expresiones que culminan en una expresión final que es el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="0cd72-115">The expression that makes up the function body is typically a compound expression consisting of a number of expressions that culminate in a final expression that is the return value.</span></span> <span data-ttu-id="0cd72-116">El *tipo de valor devuelto* es un signo de dos puntos seguido de un tipo y es opcional.</span><span class="sxs-lookup"><span data-stu-id="0cd72-116">The *return-type* is a colon followed by a type and is optional.</span></span> <span data-ttu-id="0cd72-117">Si no se especifica explícitamente el tipo del valor devuelto, el compilador determina el tipo de valor devuelto a partir de la expresión final.</span><span class="sxs-lookup"><span data-stu-id="0cd72-117">If you do not specify the type of the return value explicitly, the compiler determines the return type from the final expression.</span></span>

<span data-ttu-id="0cd72-118">Una definición de función simple es similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="0cd72-118">A simple function definition resembles the following:</span></span>

```fsharp
let f x = x + 1
```

<span data-ttu-id="0cd72-119">En el ejemplo anterior, el nombre de función es `f`, el argumento es `x`, que tiene el tipo `int`, el cuerpo de la función es `x + 1` y el valor devuelto es de tipo `int`.</span><span class="sxs-lookup"><span data-stu-id="0cd72-119">In the previous example, the function name is `f`, the argument is `x`, which has type `int`, the function body is `x + 1`, and the return value is of type `int`.</span></span>

<span data-ttu-id="0cd72-120">Las funciones se pueden marcar como `inline`.</span><span class="sxs-lookup"><span data-stu-id="0cd72-120">Functions can be marked `inline`.</span></span> <span data-ttu-id="0cd72-121">Para más información sobre `inline`, vea [Inline Functions](inline-functions.md) (Funciones insertadas).</span><span class="sxs-lookup"><span data-stu-id="0cd72-121">For information about `inline`, see [Inline Functions](inline-functions.md).</span></span>

## <a name="scope"></a><span data-ttu-id="0cd72-122">Ámbito</span><span class="sxs-lookup"><span data-stu-id="0cd72-122">Scope</span></span>

<span data-ttu-id="0cd72-123">En cualquier nivel de ámbito distinto al ámbito de módulo, no es un error volver a usar un nombre de función o valor.</span><span class="sxs-lookup"><span data-stu-id="0cd72-123">At any level of scope other than module scope, it is not an error to reuse a value or function name.</span></span> <span data-ttu-id="0cd72-124">Si se vuelve a usar un nombre, el último nombre declarado prevalece sobre el declarado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="0cd72-124">If you reuse a name, the name declared later shadows the name declared earlier.</span></span> <span data-ttu-id="0cd72-125">Pero en el ámbito de nivel superior en un módulo, los nombres deben ser únicos.</span><span class="sxs-lookup"><span data-stu-id="0cd72-125">However, at the top level scope in a module, names must be unique.</span></span> <span data-ttu-id="0cd72-126">Por ejemplo, el código siguiente produce un error cuando aparece en el ámbito de módulo, pero no cuando aparece dentro de una función:</span><span class="sxs-lookup"><span data-stu-id="0cd72-126">For example, the following code produces an error when it appears at module scope, but not when it appears inside a function:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet101.fs)]

<span data-ttu-id="0cd72-127">Pero el código siguiente es aceptable en cualquier nivel de ámbito:</span><span class="sxs-lookup"><span data-stu-id="0cd72-127">But the following code is acceptable at any level of scope:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet102.fs)]

### <a name="parameters"></a><span data-ttu-id="0cd72-128">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0cd72-128">Parameters</span></span>

<span data-ttu-id="0cd72-129">Los nombres de los parámetros aparecen después del nombre de función.</span><span class="sxs-lookup"><span data-stu-id="0cd72-129">Names of parameters are listed after the function name.</span></span> <span data-ttu-id="0cd72-130">Se puede especificar un tipo para un parámetro, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0cd72-130">You can specify a type for a parameter, as shown in the following example:</span></span>

```fsharp
let f (x : int) = x + 1
```

<span data-ttu-id="0cd72-131">Si se especifica un tipo, sigue al nombre del parámetro y se separa del nombre mediante dos puntos.</span><span class="sxs-lookup"><span data-stu-id="0cd72-131">If you specify a type, it follows the name of the parameter and is separated from the name by a colon.</span></span> <span data-ttu-id="0cd72-132">Si se omite el tipo del parámetro, el compilador infiere el tipo de parámetro.</span><span class="sxs-lookup"><span data-stu-id="0cd72-132">If you omit the type for the parameter, the parameter type is inferred by the compiler.</span></span> <span data-ttu-id="0cd72-133">Por ejemplo, en la siguiente definición de función, se deduce que el argumento `x` es del tipo `int` porque 1 es de tipo `int`.</span><span class="sxs-lookup"><span data-stu-id="0cd72-133">For example, in the following function definition, the argument `x` is inferred to be of type `int` because 1 is of type `int`.</span></span>

```fsharp
let f x = x + 1
```

<span data-ttu-id="0cd72-134">Pero el compilador intentará que la función sea lo más genérica posible.</span><span class="sxs-lookup"><span data-stu-id="0cd72-134">However, the compiler will attempt to make the function as generic as possible.</span></span> <span data-ttu-id="0cd72-135">Por ejemplo, observe el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="0cd72-135">For example, note the following code:</span></span>

```fsharp
let f x = (x, x)
```

<span data-ttu-id="0cd72-136">La función crea una tupla a partir de un argumento de cualquier tipo.</span><span class="sxs-lookup"><span data-stu-id="0cd72-136">The function creates a tuple from one argument of any type.</span></span> <span data-ttu-id="0cd72-137">Dado que no se especifica el tipo, la función se puede usar con cualquier tipo de argumento.</span><span class="sxs-lookup"><span data-stu-id="0cd72-137">Because the type is not specified, the function can be used with any argument type.</span></span> <span data-ttu-id="0cd72-138">Para más información, vea [Automatic Generalization](../generics/automatic-generalization.md) (Generalización automática).</span><span class="sxs-lookup"><span data-stu-id="0cd72-138">For more information, see [Automatic Generalization](../generics/automatic-generalization.md).</span></span>

## <a name="function-bodies"></a><span data-ttu-id="0cd72-139">Cuerpos de función</span><span class="sxs-lookup"><span data-stu-id="0cd72-139">Function Bodies</span></span>

<span data-ttu-id="0cd72-140">El cuerpo de una función puede contener definiciones de variables locales y funciones.</span><span class="sxs-lookup"><span data-stu-id="0cd72-140">A function body can contain definitions of local variables and functions.</span></span> <span data-ttu-id="0cd72-141">Estas variables y funciones están en ámbito en el cuerpo de la función actual, pero no fuera de ella.</span><span class="sxs-lookup"><span data-stu-id="0cd72-141">Such variables and functions are in scope in the body of the current function but not outside it.</span></span> <span data-ttu-id="0cd72-142">Una vez habilitada la opción de sintaxis ligera, se debe usar sangría para indicar que es una definición de un cuerpo de función, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0cd72-142">When you have the lightweight syntax option enabled, you must use indentation to indicate that a definition is in a function body, as shown in the following example:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet103.fs)]

<span data-ttu-id="0cd72-143">Para más información, vea [Code Formatting Guidelines](../../style-guide/formatting.md) (Instrucciones de formato de código) y [Verbose Syntax](../verbose-syntax.md) (Sintaxis detallada).</span><span class="sxs-lookup"><span data-stu-id="0cd72-143">For more information, see [Code Formatting Guidelines](../../style-guide/formatting.md) and [Verbose Syntax](../verbose-syntax.md).</span></span>

## <a name="return-values"></a><span data-ttu-id="0cd72-144">Valores devueltos</span><span class="sxs-lookup"><span data-stu-id="0cd72-144">Return Values</span></span>

<span data-ttu-id="0cd72-145">El compilador usa la expresión final en el cuerpo de una función para determinar el tipo y el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="0cd72-145">The compiler uses the final expression in a function body to determine the return value and type.</span></span> <span data-ttu-id="0cd72-146">Es posible que el compilador deduzca el tipo de la expresión final a partir las expresiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="0cd72-146">The compiler might infer the type of the final expression from previous expressions.</span></span> <span data-ttu-id="0cd72-147">En la función `cylinderVolume`, como se muestra en la sección anterior, el tipo de `pi` se determina a partir del tipo del literal `3.14159` como `float`.</span><span class="sxs-lookup"><span data-stu-id="0cd72-147">In the function `cylinderVolume`, shown in the previous section, the type of `pi` is determined from the type of the literal `3.14159` to be `float`.</span></span> <span data-ttu-id="0cd72-148">El compilador usa el tipo de `pi` para determinar el tipo de la expresión `h * pi * r * r` como `float`.</span><span class="sxs-lookup"><span data-stu-id="0cd72-148">The compiler uses the type of `pi` to determine the type of the expression `h * pi * r * r` to be `float`.</span></span> <span data-ttu-id="0cd72-149">Por tanto, el tipo de valor devuelto global de la función es `float`.</span><span class="sxs-lookup"><span data-stu-id="0cd72-149">Therefore, the overall return type of the function is `float`.</span></span>

<span data-ttu-id="0cd72-150">Para especificar explícitamente el valor devuelto, escriba el código de esta forma:</span><span class="sxs-lookup"><span data-stu-id="0cd72-150">To specify the return value explicitly, write the code as follows:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet105.fs)]

<span data-ttu-id="0cd72-151">Tal como se escribe el código anterior, el compilador aplica **float** a toda la función. Si también quiere aplicarlo a los tipos de parámetro, use el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="0cd72-151">As the code is written above, the compiler applies **float** to the entire function; if you mean to apply it to the parameter types as well, use the following code:</span></span>

```fsharp
let cylinderVolume (radius : float) (length : float) : float
```

## <a name="calling-a-function"></a><span data-ttu-id="0cd72-152">Llamar a una función</span><span class="sxs-lookup"><span data-stu-id="0cd72-152">Calling a Function</span></span>

<span data-ttu-id="0cd72-153">Las funciones se llaman especificando el nombre de la función seguido de un espacio y, después, los argumentos separados por espacios.</span><span class="sxs-lookup"><span data-stu-id="0cd72-153">You call functions by specifying the function name followed by a space and then any arguments separated by spaces.</span></span> <span data-ttu-id="0cd72-154">Por ejemplo, para llamar a la función **cylinderVolume** y asignar el resultado al valor **vol**, se escribe el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="0cd72-154">For example, to call the function **cylinderVolume** and assign the result to the value **vol**, you write the following code:</span></span>

```fsharp
let vol = cylinderVolume 2.0 3.0
```

## <a name="partial-application-of-arguments"></a><span data-ttu-id="0cd72-155">Aplicación parcial de argumentos</span><span class="sxs-lookup"><span data-stu-id="0cd72-155">Partial Application of Arguments</span></span>

<span data-ttu-id="0cd72-156">Si se proporcionan menos argumentos que los especificados, se crea una nueva función que espera los argumentos restantes.</span><span class="sxs-lookup"><span data-stu-id="0cd72-156">If you supply fewer than the specified number of arguments, you create a new function that expects the remaining arguments.</span></span> <span data-ttu-id="0cd72-157">Este método de control de argumentos se conoce como *currificación* y es una característica de los lenguajes de programación funcionales como F#.</span><span class="sxs-lookup"><span data-stu-id="0cd72-157">This method of handling arguments is referred to as *currying* and is a characteristic of functional programming languages like F#.</span></span> <span data-ttu-id="0cd72-158">Por ejemplo, supongamos que está trabajando con dos tamaños de canalización: una tiene un radio de **2,0** y la otra tiene un radio de **3,0**.</span><span class="sxs-lookup"><span data-stu-id="0cd72-158">For example, suppose you are working with two sizes of pipe: one has a radius of **2.0** and the other has a radius of **3.0**.</span></span> <span data-ttu-id="0cd72-159">Se podrían crear funciones que determinen el volumen de canalización de esta forma:</span><span class="sxs-lookup"><span data-stu-id="0cd72-159">You could create functions that determine the volume of pipe as follows:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet106.fs)]

<span data-ttu-id="0cd72-160">Después, se proporcionaría el argumento adicional según sea necesario para las distintas longitudes de canalización de los dos tamaños diferentes:</span><span class="sxs-lookup"><span data-stu-id="0cd72-160">You would then supply the additional argument as needed for various lengths of pipe of the two different sizes:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet107.fs)]

## <a name="recursive-functions"></a><span data-ttu-id="0cd72-161">Funciones recursivas</span><span class="sxs-lookup"><span data-stu-id="0cd72-161">Recursive Functions</span></span>

<span data-ttu-id="0cd72-162">Las *funciones recursivas* son funciones que se llaman a sí mismas.</span><span class="sxs-lookup"><span data-stu-id="0cd72-162">*Recursive functions* are functions that call themselves.</span></span> <span data-ttu-id="0cd72-163">Requieren que se especifique la palabra clave **rec** después de la palabra clave **let**.</span><span class="sxs-lookup"><span data-stu-id="0cd72-163">They require that you specify the **rec** keyword following the **let** keyword.</span></span> <span data-ttu-id="0cd72-164">La función recursiva se invoca desde el interior del cuerpo de la función de la misma forma que se invocaría cualquier llamada de función.</span><span class="sxs-lookup"><span data-stu-id="0cd72-164">Invoke the recursive function from within the body of the function just as you would invoke any function call.</span></span> <span data-ttu-id="0cd72-165">La siguiente función recursiva calcula el número *n* de Fibonacci.</span><span class="sxs-lookup"><span data-stu-id="0cd72-165">The following recursive function computes the *n*<sup>th</sup> Fibonacci number.</span></span> <span data-ttu-id="0cd72-166">La secuencia de números de Fibonacci se conoce desde la antigüedad y es una secuencia en la que cada número sucesivo es la suma de los dos números anteriores en la secuencia.</span><span class="sxs-lookup"><span data-stu-id="0cd72-166">The Fibonacci number sequence has been known since antiquity and is a sequence in which each successive number is the sum of the previous two numbers in the sequence.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet108.fs)]

<span data-ttu-id="0cd72-167">Es posible que algunas funciones recursivas desborden la pila del programa o tengan un rendimiento ineficaz si no se escriben con cuidado y con el conocimiento de determinadas técnicas especiales, como el uso de acumuladores y continuaciones.</span><span class="sxs-lookup"><span data-stu-id="0cd72-167">Some recursive functions might overflow the program stack or perform inefficiently if you do not write them with care and with awareness of special techniques, such as the use of accumulators and continuations.</span></span>

## <a name="function-values"></a><span data-ttu-id="0cd72-168">Valores de función</span><span class="sxs-lookup"><span data-stu-id="0cd72-168">Function Values</span></span>

<span data-ttu-id="0cd72-169">En F#, todas las funciones se consideran valores, de hecho, se conocen como *valores de función*.</span><span class="sxs-lookup"><span data-stu-id="0cd72-169">In F#, all functions are considered values; in fact, they are known as *function values*.</span></span> <span data-ttu-id="0cd72-170">Dado que las funciones son valores, se pueden usar como argumentos de otras funciones o en otros contextos donde se usan los valores.</span><span class="sxs-lookup"><span data-stu-id="0cd72-170">Because functions are values, they can be used as arguments to other functions or in other contexts where values are used.</span></span> <span data-ttu-id="0cd72-171">El siguiente ejemplo muestra una función que toma un valor de función como argumento:</span><span class="sxs-lookup"><span data-stu-id="0cd72-171">Following is an example of a function that takes a function value as an argument:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet109.fs)]

<span data-ttu-id="0cd72-172">El tipo de un valor de función se especifica mediante el token `->`.</span><span class="sxs-lookup"><span data-stu-id="0cd72-172">You specify the type of a function value by using the `->` token.</span></span> <span data-ttu-id="0cd72-173">En el lado izquierdo de este token está el tipo del argumento y, en el lado derecho, el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="0cd72-173">On the left side of this token is the type of the argument, and on the right side is the return value.</span></span> <span data-ttu-id="0cd72-174">En el ejemplo anterior, `apply1` es una función que toma una función `transform` como argumento, donde `transform` es una función que toma un entero y devuelve otro entero.</span><span class="sxs-lookup"><span data-stu-id="0cd72-174">In the previous example, `apply1` is a function that takes a function `transform` as an argument, where `transform` is a function that takes an integer and returns another integer.</span></span> <span data-ttu-id="0cd72-175">En el código siguiente se muestra cómo usar `apply1`:</span><span class="sxs-lookup"><span data-stu-id="0cd72-175">The following code shows how to use `apply1`:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet110.fs)]

<span data-ttu-id="0cd72-176">El valor de `result` será 101 después de ejecutar el código anterior.</span><span class="sxs-lookup"><span data-stu-id="0cd72-176">The value of `result` will be 101 after the previous code runs.</span></span>

<span data-ttu-id="0cd72-177">Si hay varios argumentos, se separan por sucesivos tokens `->`, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0cd72-177">Multiple arguments are separated by successive `->` tokens, as shown in the following example:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet111.fs)]

<span data-ttu-id="0cd72-178">El resultado es 200.</span><span class="sxs-lookup"><span data-stu-id="0cd72-178">The result is 200.</span></span>

## <a name="lambda-expressions"></a><span data-ttu-id="0cd72-179">Expresiones lambda</span><span class="sxs-lookup"><span data-stu-id="0cd72-179">Lambda Expressions</span></span>

<span data-ttu-id="0cd72-180">Una *expresión lambda* es una función sin nombre.</span><span class="sxs-lookup"><span data-stu-id="0cd72-180">A *lambda expression* is an unnamed function.</span></span> <span data-ttu-id="0cd72-181">En los ejemplos anteriores, en lugar de definir las funciones con nombre **increment** y **mul**, se podrían usar expresiones lambda de esta forma:</span><span class="sxs-lookup"><span data-stu-id="0cd72-181">In the previous examples, instead of defining named functions **increment** and **mul**, you could use lambda expressions as follows:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet112.fs)]

<span data-ttu-id="0cd72-182">Las expresiones lambda se definen mediante la palabra clave `fun`.</span><span class="sxs-lookup"><span data-stu-id="0cd72-182">You define lambda expressions by using the `fun` keyword.</span></span> <span data-ttu-id="0cd72-183">Una expresión lambda es similar a una definición de función, salvo que en lugar del token `=` se usa el token `->` para separar la lista de argumentos del cuerpo de la función.</span><span class="sxs-lookup"><span data-stu-id="0cd72-183">A lambda expression resembles a function definition, except that instead of the `=` token, the `->` token is used to separate the argument list from the function body.</span></span> <span data-ttu-id="0cd72-184">Al igual que en una definición de función normal, se pueden deducir o especificar explícitamente los tipos de argumento, y el tipo de valor devuelto de la expresión lambda se deduce del tipo de la última expresión en el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="0cd72-184">As in a regular function definition, the argument types can be inferred or specified explicitly, and the return type of the lambda expression is inferred from the type of the last expression in the body.</span></span> <span data-ttu-id="0cd72-185">Para obtener más información, vea [Expresiones lambda: Palabra clave `fun`](lambda-expressions-the-fun-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="0cd72-185">For more information, see [Lambda Expressions: The `fun` Keyword](lambda-expressions-the-fun-keyword.md).</span></span>

## <a name="function-composition-and-pipelining"></a><span data-ttu-id="0cd72-186">Composición de funciones y canalización</span><span class="sxs-lookup"><span data-stu-id="0cd72-186">Function Composition and Pipelining</span></span>

<span data-ttu-id="0cd72-187">En F#, las funciones se pueden componer a partir de otras funciones.</span><span class="sxs-lookup"><span data-stu-id="0cd72-187">Functions in F# can be composed from other functions.</span></span> <span data-ttu-id="0cd72-188">La composición de dos funciones **función1** y **función2** es otra función que representa la aplicación de **función1** seguida de la aplicación de **función2**:</span><span class="sxs-lookup"><span data-stu-id="0cd72-188">The composition of two functions **function1** and **function2** is another function that represents the application of **function1** followed the application of **function2**:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet113.fs)]

<span data-ttu-id="0cd72-189">El resultado es 202.</span><span class="sxs-lookup"><span data-stu-id="0cd72-189">The result is 202.</span></span>

<span data-ttu-id="0cd72-190">La canalización permite encadenar llamadas a funciones como operaciones sucesivas.</span><span class="sxs-lookup"><span data-stu-id="0cd72-190">Pipelining enables function calls to be chained together as successive operations.</span></span> <span data-ttu-id="0cd72-191">La canalización funciona de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="0cd72-191">Pipelining works as follows:</span></span>

```fsharp
let result = 100 |> function1 |> function2
```

<span data-ttu-id="0cd72-192">El resultado es 202 de nuevo.</span><span class="sxs-lookup"><span data-stu-id="0cd72-192">The result is again 202.</span></span>

<span data-ttu-id="0cd72-193">Los operadores de composición toman dos funciones y devuelven una función. Por el contrario, los operadores de canalización toman una función y un argumento, y devuelven un valor.</span><span class="sxs-lookup"><span data-stu-id="0cd72-193">The composition operators take two functions and return a function; by contrast, the pipeline operators take a function and an argument and return a value.</span></span> <span data-ttu-id="0cd72-194">En el ejemplo de código siguiente se muestra la diferencia entre los operadores de canalización y composición mostrando las diferencias en las firmas de función y el uso.</span><span class="sxs-lookup"><span data-stu-id="0cd72-194">The following code example shows the difference between the pipeline and composition operators by showing the differences in the function signatures and usage.</span></span>

```fsharp
// Function composition and pipeline operators compared.

let addOne x = x + 1
let timesTwo x = 2 * x

// Composition operator
// ( >> ) : ('T1 -> 'T2) -> ('T2 -> 'T3) -> 'T1 -> 'T3
let Compose2 = addOne >> timesTwo

// Backward composition operator
// ( << ) : ('T2 -> 'T3) -> ('T1 -> 'T2) -> 'T1 -> 'T3
let Compose1 = addOne << timesTwo

// Result is 5
let result1 = Compose1 2

// Result is 6
let result2 = Compose2 2

// Pipelining
// Pipeline operator
// ( |> ) : 'T1 -> ('T1 -> 'U) -> 'U
let Pipeline2 x = addOne x |> timesTwo

// Backward pipeline operator
// ( <| ) : ('T -> 'U) -> 'T -> 'U
let Pipeline1 x = addOne <| timesTwo x

// Result is 5
let result3 = Pipeline1 2

// Result is 6
let result4 = Pipeline2 2
```

## <a name="overloading-functions"></a><span data-ttu-id="0cd72-195">Sobrecargar funciones</span><span class="sxs-lookup"><span data-stu-id="0cd72-195">Overloading Functions</span></span>

<span data-ttu-id="0cd72-196">Los métodos de un tipo se pueden sobrecargar, pero no las funciones.</span><span class="sxs-lookup"><span data-stu-id="0cd72-196">You can overload methods of a type but not functions.</span></span> <span data-ttu-id="0cd72-197">Para más información, vea [Métodos](../members/methods.md).</span><span class="sxs-lookup"><span data-stu-id="0cd72-197">For more information, see [Methods](../members/methods.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0cd72-198">Vea también</span><span class="sxs-lookup"><span data-stu-id="0cd72-198">See also</span></span>

- [<span data-ttu-id="0cd72-199">Valores</span><span class="sxs-lookup"><span data-stu-id="0cd72-199">Values</span></span>](../values/index.md)
- [<span data-ttu-id="0cd72-200">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="0cd72-200">F# Language Reference</span></span>](../index.md)
