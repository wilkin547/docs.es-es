---
title: Funciones de primera clase
description: 'Obtenga información sobre las funciones de primera clase y cómo son importantes para la programación funcional en F #.'
ms.date: 10/29/2018
ms.openlocfilehash: 1dc8eae1655187282f05bf4e9501ecc8a17deba8
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/25/2020
ms.locfileid: "88810916"
---
# <a name="first-class-functions"></a><span data-ttu-id="72530-103">Funciones de primera clase</span><span class="sxs-lookup"><span data-stu-id="72530-103">First-class functions</span></span>

<span data-ttu-id="72530-104">Los lenguajes de programación funcional se caracterizan principalmente por tratar las funciones como valores de primera clase.</span><span class="sxs-lookup"><span data-stu-id="72530-104">A defining characteristic of functional programming languages is the elevation of functions to first-class status.</span></span> <span data-ttu-id="72530-105">El usuario podrá hacer con las funciones todo lo que se puede hacer con los valores de los otros tipos integrados y, además, con un esfuerzo comparable.</span><span class="sxs-lookup"><span data-stu-id="72530-105">You should be able to do with a function whatever you can do with values of the other built-in types, and be able to do so with a comparable degree of effort.</span></span>

<span data-ttu-id="72530-106">Entre los criterios más comunes para determinar si los valores son de primera clase se encuentran los siguientes:</span><span class="sxs-lookup"><span data-stu-id="72530-106">Typical measures of first-class status include the following:</span></span>

- <span data-ttu-id="72530-107">¿Puede enlazar funciones a los identificadores?</span><span class="sxs-lookup"><span data-stu-id="72530-107">Can you bind functions to identifiers?</span></span> <span data-ttu-id="72530-108">Es decir, ¿puede asignarles nombres?</span><span class="sxs-lookup"><span data-stu-id="72530-108">That is, can you give them names?</span></span>

- <span data-ttu-id="72530-109">¿Se pueden almacenar funciones en estructuras de datos, como en una lista?</span><span class="sxs-lookup"><span data-stu-id="72530-109">Can you store functions in data structures, such as in a list?</span></span>

- <span data-ttu-id="72530-110">¿Se puede pasar una función como argumento en una llamada de función?</span><span class="sxs-lookup"><span data-stu-id="72530-110">Can you pass a function as an argument in a function call?</span></span>

- <span data-ttu-id="72530-111">¿Se puede devolver una función desde una llamada de función?</span><span class="sxs-lookup"><span data-stu-id="72530-111">Can you return a function from a function call?</span></span>

<span data-ttu-id="72530-112">Las dos últimas medidas definen lo que se conoce como *operaciones de orden superior* o *funciones de orden superior*.</span><span class="sxs-lookup"><span data-stu-id="72530-112">The last two measures define what are known as *higher-order operations* or *higher-order functions*.</span></span> <span data-ttu-id="72530-113">Las funciones de orden superior aceptan otras funciones como argumentos y devuelven funciones como valores de llamadas de función.</span><span class="sxs-lookup"><span data-stu-id="72530-113">Higher-order functions accept functions as arguments and return functions as the value of function calls.</span></span> <span data-ttu-id="72530-114">Estas operaciones son compatibles con los principales pilares de la programación funcional, a saber, las funciones de asignación y la composición de funciones.</span><span class="sxs-lookup"><span data-stu-id="72530-114">These operations support such mainstays of functional programming as mapping functions and composition of functions.</span></span>

## <a name="give-the-value-a-name"></a><span data-ttu-id="72530-115">Asignar un nombre al valor</span><span class="sxs-lookup"><span data-stu-id="72530-115">Give the Value a Name</span></span>

<span data-ttu-id="72530-116">Si una función es un valor de primera clase, debe ser posible asignarle un nombre al igual que en el caso de enteros, cadenas y otros tipos integrados.</span><span class="sxs-lookup"><span data-stu-id="72530-116">If a function is a first-class value, you must be able to name it, just as you can name integers, strings, and other built-in types.</span></span> <span data-ttu-id="72530-117">En la programación funcional, esto se denomina "enlazar un identificador a un valor".</span><span class="sxs-lookup"><span data-stu-id="72530-117">This is referred to in functional programming literature as binding an identifier to a value.</span></span> <span data-ttu-id="72530-118">F # utiliza [ `let` enlaces](../language-reference/functions/let-bindings.md) para enlazar nombres a valores: `let <identifier> = <value>` .</span><span class="sxs-lookup"><span data-stu-id="72530-118">F# uses [`let` bindings](../language-reference/functions/let-bindings.md) to bind names to values: `let <identifier> = <value>`.</span></span> <span data-ttu-id="72530-119">En el código siguiente, se muestran dos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="72530-119">The following code shows two examples.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet20.fs)]

<span data-ttu-id="72530-120">La asignación de un nombre a una función es así de sencilla.</span><span class="sxs-lookup"><span data-stu-id="72530-120">You can name a function just as easily.</span></span> <span data-ttu-id="72530-121">En el ejemplo siguiente se define una función denominada `squareIt` enlazando el identificador `squareIt` a la [expresión lambda](../language-reference/functions/lambda-expressions-the-fun-keyword.md) `fun n -> n * n` .</span><span class="sxs-lookup"><span data-stu-id="72530-121">The following example defines a function named `squareIt` by binding the identifier `squareIt` to the [lambda expression](../language-reference/functions/lambda-expressions-the-fun-keyword.md) `fun n -> n * n`.</span></span> <span data-ttu-id="72530-122">La función `squareIt` tiene un parámetro, `n`, y devuelve el cuadrado de ese parámetro.</span><span class="sxs-lookup"><span data-stu-id="72530-122">Function `squareIt` has one parameter, `n`, and it returns the square of that parameter.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet21.fs)]

<span data-ttu-id="72530-123">F# proporciona la siguiente sintaxis más concisa para lograr el mismo resultado.</span><span class="sxs-lookup"><span data-stu-id="72530-123">F# provides the following more concise syntax to achieve the same result with less typing.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet22.fs)]

<span data-ttu-id="72530-124">En los siguientes ejemplos, se usa principalmente el primer estilo, `let <function-name> = <lambda-expression>`, para recalcar las similitudes entre la declaración de funciones y la declaración de otros tipos de valores.</span><span class="sxs-lookup"><span data-stu-id="72530-124">The examples that follow mostly use the first style, `let <function-name> = <lambda-expression>`, to emphasize the similarities between the declaration of functions and the declaration of other types of values.</span></span> <span data-ttu-id="72530-125">Sin embargo, todas las funciones con nombre también se pueden escribir mediante la sintaxis concisa.</span><span class="sxs-lookup"><span data-stu-id="72530-125">However, all the named functions can also be written with the concise syntax.</span></span> <span data-ttu-id="72530-126">Algunos de los ejemplos se han escrito de ambas formas.</span><span class="sxs-lookup"><span data-stu-id="72530-126">Some of the examples are written in both ways.</span></span>

## <a name="store-the-value-in-a-data-structure"></a><span data-ttu-id="72530-127">Almacenar el valor en una estructura de datos</span><span class="sxs-lookup"><span data-stu-id="72530-127">Store the Value in a Data Structure</span></span>

<span data-ttu-id="72530-128">Un valor de primera clase puede almacenarse en una estructura de datos.</span><span class="sxs-lookup"><span data-stu-id="72530-128">A first-class value can be stored in a data structure.</span></span> <span data-ttu-id="72530-129">En el siguiente código, se muestran ejemplos en los se almacenan los valores en listas y tuplas.</span><span class="sxs-lookup"><span data-stu-id="72530-129">The following code shows examples that store values in lists and in tuples.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet23.fs)]

<span data-ttu-id="72530-130">Para comprobar que un nombre de función almacenado en una tupla se evalúa realmente como una función, en el siguiente ejemplo se usan los operadores `fst` y `snd` para extraer los dos primeros elementos de la tupla `funAndArgTuple`.</span><span class="sxs-lookup"><span data-stu-id="72530-130">To verify that a function name stored in a tuple does in fact evaluate to a function, the following example uses the `fst` and `snd` operators to extract the first and second elements from tuple `funAndArgTuple`.</span></span> <span data-ttu-id="72530-131">El primer elemento de la tupla es `squareIt` y el segundo elemento es `num`.</span><span class="sxs-lookup"><span data-stu-id="72530-131">The first element in the tuple is `squareIt` and the second element is `num`.</span></span> <span data-ttu-id="72530-132">En un ejemplo anterior, se ha enlazado el identificador `num` al entero 10, un argumento válido para la función `squareIt`.</span><span class="sxs-lookup"><span data-stu-id="72530-132">Identifier `num` is bound in a previous example to integer 10, a valid argument for the `squareIt` function.</span></span> <span data-ttu-id="72530-133">La segunda expresión aplica el primer elemento de la tupla al segundo elemento de la tupla: `squareIt num`.</span><span class="sxs-lookup"><span data-stu-id="72530-133">The second expression applies the first element in the tuple to the second element in the tuple: `squareIt num`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet24.fs)]

<span data-ttu-id="72530-134">De forma similar, al igual que en el caso del identificador `num` y el entero 10, el identificador `squareIt` y la expresión lambda `fun n -> n * n` puede usarse indistintamente.</span><span class="sxs-lookup"><span data-stu-id="72530-134">Similarly, just as identifier `num` and integer 10 can be used interchangeably, so can identifier `squareIt` and lambda expression `fun n -> n * n`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet25.fs)]

## <a name="pass-the-value-as-an-argument"></a><span data-ttu-id="72530-135">Pasar el valor como un argumento</span><span class="sxs-lookup"><span data-stu-id="72530-135">Pass the Value as an Argument</span></span>

<span data-ttu-id="72530-136">Si un lenguaje trata un valor como un valor de primera clase, se puede pasar dicho valor como argumento de una función.</span><span class="sxs-lookup"><span data-stu-id="72530-136">If a value has first-class status in a language, you can pass it as an argument to a function.</span></span> <span data-ttu-id="72530-137">Por ejemplo, los enteros y cadenas se suelen pasar como argumentos.</span><span class="sxs-lookup"><span data-stu-id="72530-137">For example, it is common to pass integers and strings as arguments.</span></span> <span data-ttu-id="72530-138">En el siguiente código, se muestran enteros y cadenas que se pasan como argumentos en F#.</span><span class="sxs-lookup"><span data-stu-id="72530-138">The following code shows integers and strings passed as arguments in F#.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet26.fs)]

<span data-ttu-id="72530-139">Si una función es un valor de primera clase, dicha función también debe poder pasarse como un argumento.</span><span class="sxs-lookup"><span data-stu-id="72530-139">If functions have first-class status, you must be able to pass them as arguments in the same way.</span></span> <span data-ttu-id="72530-140">Recuerde que esta es la primera característica de las funciones de orden superior.</span><span class="sxs-lookup"><span data-stu-id="72530-140">Remember that this is the first characteristic of higher-order functions.</span></span>

<span data-ttu-id="72530-141">En el siguiente ejemplo, la función `applyIt` tiene dos parámetros, `op` y `arg`.</span><span class="sxs-lookup"><span data-stu-id="72530-141">In the following example, function `applyIt` has two parameters, `op` and `arg`.</span></span> <span data-ttu-id="72530-142">Si envía una función con un parámetro a `op` y un argumento apropiado para la función a `arg`, la función devolverá el resultado de aplicar `op` a `arg`.</span><span class="sxs-lookup"><span data-stu-id="72530-142">If you send in a function that has one parameter for `op` and an appropriate argument for the function to `arg`, the function returns the result of applying `op` to `arg`.</span></span> <span data-ttu-id="72530-143">En el siguiente ejemplo, el argumento de función y el argumento entero se envían de la misma manera: por su nombre.</span><span class="sxs-lookup"><span data-stu-id="72530-143">In the following example, both the function argument and the integer argument are sent in the same way, by using their names.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet27.fs)]

<span data-ttu-id="72530-144">La capacidad para enviar una función como un argumento a otra función subyace a las abstracciones comunes en los lenguajes de programación funcional, como las operaciones de asignación o de filtrado.</span><span class="sxs-lookup"><span data-stu-id="72530-144">The ability to send a function as an argument to another function underlies common abstractions in functional programming languages, such as map or filter operations.</span></span> <span data-ttu-id="72530-145">Por ejemplo, una operación de asignación es una función de orden superior que captura el cálculo compartido por funciones que recorren una lista, realizan alguna operación con cada elemento y, a continuación, devuelven una lista con los resultados.</span><span class="sxs-lookup"><span data-stu-id="72530-145">A map operation, for example, is a higher-order function that captures the computation shared by functions that step through a list, do something to each element, and then return a list of the results.</span></span> <span data-ttu-id="72530-146">Quizás se desee incrementar cada elemento de una lista de enteros, elevar cada elemento al cuadrado o cambiar a mayúsculas cada uno de los elementos de una lista de cadenas.</span><span class="sxs-lookup"><span data-stu-id="72530-146">You might want to increment each element in a list of integers, or to square each element, or to change each element in a list of strings to uppercase.</span></span> <span data-ttu-id="72530-147">La parte del cálculo propensa a errores es el proceso recursivo que recorre la lista y compila una lista de los resultados que se van a devolver.</span><span class="sxs-lookup"><span data-stu-id="72530-147">The error-prone part of the computation is the recursive process that steps through the list and builds a list of the results to return.</span></span> <span data-ttu-id="72530-148">Dicha parte se captura en la función de asignación.</span><span class="sxs-lookup"><span data-stu-id="72530-148">That part is captured in the mapping function.</span></span> <span data-ttu-id="72530-149">Lo único que hay que escribir para una aplicación concreta es la función que se desea aplicar a cada uno de los elementos de la lista (sumar, elevar al cuadrado, cambiar mayúscula a minúscula o viceversa).</span><span class="sxs-lookup"><span data-stu-id="72530-149">All you have to write for a particular application is the function that you want to apply to each list element individually (adding, squaring, changing case).</span></span> <span data-ttu-id="72530-150">Dicha función se envía como argumento a la función de asignación, de la misma manera que se envía `squareIt` a `applyIt` en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="72530-150">That function is sent as an argument to the mapping function, just as `squareIt` is sent to `applyIt` in the previous example.</span></span>

<span data-ttu-id="72530-151">F # proporciona métodos de asignación para la mayoría de los tipos de colección, como [listas](../language-reference/lists.md), [matrices](../language-reference/arrays.md)y [secuencias](../language-reference/sequences.md).</span><span class="sxs-lookup"><span data-stu-id="72530-151">F# provides map methods for most collection types, including [lists](../language-reference/lists.md), [arrays](../language-reference/arrays.md), and [sequences](../language-reference/sequences.md).</span></span> <span data-ttu-id="72530-152">En los siguientes ejemplos, se utilizan listas.</span><span class="sxs-lookup"><span data-stu-id="72530-152">The following examples use lists.</span></span> <span data-ttu-id="72530-153">La sintaxis es `List.map <the function> <the list>`.</span><span class="sxs-lookup"><span data-stu-id="72530-153">The syntax is `List.map <the function> <the list>`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet28.fs)]

<span data-ttu-id="72530-154">Para obtener más información, vea [listas](../language-reference/lists.md).</span><span class="sxs-lookup"><span data-stu-id="72530-154">For more information, see [Lists](../language-reference/lists.md).</span></span>

## <a name="return-the-value-from-a-function-call"></a><span data-ttu-id="72530-155">Devolver el valor de una llamada de función</span><span class="sxs-lookup"><span data-stu-id="72530-155">Return the Value from a Function Call</span></span>

<span data-ttu-id="72530-156">Por último, si un lenguaje trata una función como valor de primera clase, dicha función debe poder devolverse como valor de una llamada de función, al igual que en el caso de otros tipos como enteros y cadenas.</span><span class="sxs-lookup"><span data-stu-id="72530-156">Finally, if a function has first-class status in a language, you must be able to return it as the value of a function call, just as you return other types, such as integers and strings.</span></span>

<span data-ttu-id="72530-157">Las siguientes llamadas de función devuelven enteros y los muestran.</span><span class="sxs-lookup"><span data-stu-id="72530-157">The following function calls return integers and display them.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet29.fs)]

<span data-ttu-id="72530-158">La siguiente llamada de función devuelve una cadena.</span><span class="sxs-lookup"><span data-stu-id="72530-158">The following function call returns a string.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet30.fs)]

<span data-ttu-id="72530-159">La siguiente llamada de función, declarada en el propio código, devuelve un valor booleano.</span><span class="sxs-lookup"><span data-stu-id="72530-159">The following function call, declared inline, returns a Boolean value.</span></span> <span data-ttu-id="72530-160">El valor mostrado es `True`.</span><span class="sxs-lookup"><span data-stu-id="72530-160">The value displayed is `True`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet31.fs)]

<span data-ttu-id="72530-161">La capacidad para devolver una función como valor de una llamada de función es la segunda característica de las funciones de orden superior.</span><span class="sxs-lookup"><span data-stu-id="72530-161">The ability to return a function as the value of a function call is the second characteristic of higher-order functions.</span></span> <span data-ttu-id="72530-162">En el siguiente ejemplo, `checkFor` se define como una función que toma un argumento, `item`, y devuelve una nueva función como su valor.</span><span class="sxs-lookup"><span data-stu-id="72530-162">In the following example, `checkFor` is defined to be a function that takes one argument, `item`, and returns a new function as its value.</span></span> <span data-ttu-id="72530-163">La función devuelta toma una lista como argumento, `lst`, y busca `item` en `lst`.</span><span class="sxs-lookup"><span data-stu-id="72530-163">The returned function takes a list as its argument, `lst`, and searches for `item` in `lst`.</span></span> <span data-ttu-id="72530-164">Si encuentra `item`, la función devuelve `true`.</span><span class="sxs-lookup"><span data-stu-id="72530-164">If `item` is present, the function returns `true`.</span></span> <span data-ttu-id="72530-165">Si no encuentra `item`, la función devuelve `false`.</span><span class="sxs-lookup"><span data-stu-id="72530-165">If `item` is not present, the function returns `false`.</span></span> <span data-ttu-id="72530-166">Como en la sección anterior, el código siguiente usa una función de lista proporcionada [List. exists](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#exists)para buscar en la lista.</span><span class="sxs-lookup"><span data-stu-id="72530-166">As in the previous section, the following code uses a provided list function, [List.exists](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#exists), to search the list.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet32.fs)]

<span data-ttu-id="72530-167">En el siguiente código, se utiliza `checkFor` para crear una función que toma un argumento (una lista) y busca el número 7 en la lista.</span><span class="sxs-lookup"><span data-stu-id="72530-167">The following code uses `checkFor` to create a new function that takes one argument, a list, and searches for 7 in the list.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet33.fs)]

<span data-ttu-id="72530-168">En el siguiente ejemplo, se utiliza el estatus de primera clase de las funciones en F# para declarar una función, `compose`, que devuelve una composición de dos argumentos de función.</span><span class="sxs-lookup"><span data-stu-id="72530-168">The following example uses the first-class status of functions in F# to declare a function, `compose`, that returns a composition of two function arguments.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet34.fs)]

> [!NOTE]
> <span data-ttu-id="72530-169">Para obtener una versión más corta, vea la siguiente sección, "Funciones currificadas".</span><span class="sxs-lookup"><span data-stu-id="72530-169">For an even shorter version, see the following section, "Curried Functions."</span></span>

<span data-ttu-id="72530-170">En el siguiente código, se envían dos funciones como argumentos a `compose` y las dos toman un solo argumento del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="72530-170">The following code sends two functions as arguments to `compose`, both of which take a single argument of the same type.</span></span> <span data-ttu-id="72530-171">El valor devuelto es una nueva función que es una composición de los dos argumentos de función.</span><span class="sxs-lookup"><span data-stu-id="72530-171">The return value is a new function that is a composition of the two function arguments.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet35.fs)]

> [!NOTE]
> <span data-ttu-id="72530-172">F# proporciona dos operadores, `<<` y `>>`, que realizan la composición de funciones.</span><span class="sxs-lookup"><span data-stu-id="72530-172">F# provides two operators, `<<` and `>>`, that compose functions.</span></span> <span data-ttu-id="72530-173">Por ejemplo, `let squareAndDouble2 = doubleIt << squareIt` equivale a `let squareAndDouble = compose doubleIt squareIt` del ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="72530-173">For example, `let squareAndDouble2 = doubleIt << squareIt` is equivalent to `let squareAndDouble = compose doubleIt squareIt` in the previous example.</span></span>

<span data-ttu-id="72530-174">En el siguiente ejemplo de cómo devolver una función como valor de una llamada de función, se crea un simple juego de adivinanzas.</span><span class="sxs-lookup"><span data-stu-id="72530-174">The following example of returning a function as the value of a function call creates a simple guessing game.</span></span> <span data-ttu-id="72530-175">Para crear un juego, llame a `makeGame` y envíe para `target` el valor que el usuario debe adivinar.</span><span class="sxs-lookup"><span data-stu-id="72530-175">To create a game, call `makeGame` with the value that you want someone to guess sent in for `target`.</span></span> <span data-ttu-id="72530-176">El valor devuelto de la función `makeGame` es una función que toma un argumento (la adivinanza) y notifica si el usuario ha respondido correctamente a la adivinanza.</span><span class="sxs-lookup"><span data-stu-id="72530-176">The return value from function `makeGame` is a function that takes one argument (the guess) and reports whether the guess is correct.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet36.fs)]

<span data-ttu-id="72530-177">El siguiente código llama a `makeGame`, enviando el valor `7` para `target`.</span><span class="sxs-lookup"><span data-stu-id="72530-177">The following code calls `makeGame`, sending the value `7` for `target`.</span></span> <span data-ttu-id="72530-178">El identificador `playGame` está enlazado a la expresión lambda devuelta.</span><span class="sxs-lookup"><span data-stu-id="72530-178">Identifier `playGame` is bound to the returned lambda expression.</span></span> <span data-ttu-id="72530-179">Por consiguiente, `playGame` es una función que toma como único argumento un valor de `guess`.</span><span class="sxs-lookup"><span data-stu-id="72530-179">Therefore, `playGame` is a function that takes as its one argument a value for `guess`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet37.fs)]

## <a name="curried-functions"></a><span data-ttu-id="72530-180">Funciones currificadas</span><span class="sxs-lookup"><span data-stu-id="72530-180">Curried Functions</span></span>

<span data-ttu-id="72530-181">Muchos de los ejemplos de la sección anterior se pueden escribir de forma más concisa aprovechando el *currificación* implícito en las declaraciones de función de F #.</span><span class="sxs-lookup"><span data-stu-id="72530-181">Many of the examples in the previous section can be written more concisely by taking advantage of the implicit *currying* in F# function declarations.</span></span> <span data-ttu-id="72530-182">La currificación es un proceso que consiste en transformar una función con varios parámetros en una serie de funciones incrustadas, cada una de las cuales tiene un solo parámetro.</span><span class="sxs-lookup"><span data-stu-id="72530-182">Currying is a process that transforms a function that has more than one parameter into a series of embedded functions, each of which has a single parameter.</span></span> <span data-ttu-id="72530-183">En F#, las funciones con más de un parámetro se currifican de manera inherente.</span><span class="sxs-lookup"><span data-stu-id="72530-183">In F#, functions that have more than one parameter are inherently curried.</span></span> <span data-ttu-id="72530-184">Por ejemplo, la función `compose` que aparece en la sección anterior se puede escribir de manera concisa con tres parámetros, tal y como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="72530-184">For example, `compose` from the previous section can be written as shown in the following concise style, with three parameters.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet38.fs)]

<span data-ttu-id="72530-185">Sin embargo, el resultado es una función con un parámetro que devuelve una función con un parámetro que, a su vez, devuelve otra función con un parámetro, tal y como se muestra en `compose4curried`.</span><span class="sxs-lookup"><span data-stu-id="72530-185">However, the result is a function of one parameter that returns a function of one parameter that in turn returns another function of one parameter, as shown in `compose4curried`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet39.fs)]

<span data-ttu-id="72530-186">El acceso a esta función puede realizarse de varias maneras.</span><span class="sxs-lookup"><span data-stu-id="72530-186">You can access this function in several ways.</span></span> <span data-ttu-id="72530-187">En cada uno de los siguientes ejemplos, se devuelve y se muestra el número 18.</span><span class="sxs-lookup"><span data-stu-id="72530-187">Each of the following examples returns and displays 18.</span></span> <span data-ttu-id="72530-188">Se puede reemplazar `compose4` con `compose4curried` en cualquiera de los ejemplos.</span><span class="sxs-lookup"><span data-stu-id="72530-188">You can replace `compose4` with `compose4curried` in any of the examples.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet40.fs)]

<span data-ttu-id="72530-189">Para comprobar que la función se ejecuta igual que antes, recurre de nuevo a los casos de prueba originales.</span><span class="sxs-lookup"><span data-stu-id="72530-189">To verify that the function still works as it did before, try the original test cases again.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet41.fs)]

> [!NOTE]
> <span data-ttu-id="72530-190">La currificación se puede restringir agrupando los parámetros en tuplas.</span><span class="sxs-lookup"><span data-stu-id="72530-190">You can restrict currying by enclosing parameters in tuples.</span></span> <span data-ttu-id="72530-191">Para obtener más información, vea "patrones de parámetro" en [parámetros y argumentos](../language-reference/parameters-and-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="72530-191">For more information, see "Parameter Patterns" in [Parameters and Arguments](../language-reference/parameters-and-arguments.md).</span></span>

<span data-ttu-id="72530-192">En el siguiente ejemplo, se utiliza la currificación implícita para escribir una versión más corta de `makeGame`.</span><span class="sxs-lookup"><span data-stu-id="72530-192">The following example uses implicit currying to write a shorter version of `makeGame`.</span></span> <span data-ttu-id="72530-193">Los detalles referentes a cómo `makeGame` construye y devuelve la función `game` son menos explícitos en este formato, pero se pueden usar los casos de prueba originales para comprobar que el resultado es el mismo.</span><span class="sxs-lookup"><span data-stu-id="72530-193">The details of how `makeGame` constructs and returns the `game` function are less explicit in this format, but you can verify by using the original test cases that the result is the same.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet42.fs)]

<span data-ttu-id="72530-194">Para obtener más información sobre currificación, vea "aplicación parcial de argumentos" en [funciones](../language-reference/functions/index.md).</span><span class="sxs-lookup"><span data-stu-id="72530-194">For more information about currying, see "Partial Application of Arguments" in [Functions](../language-reference/functions/index.md).</span></span>

## <a name="identifier-and-function-definition-are-interchangeable"></a><span data-ttu-id="72530-195">El identificador y la definición de función pueden usarse indistintamente</span><span class="sxs-lookup"><span data-stu-id="72530-195">Identifier and Function Definition Are Interchangeable</span></span>

<span data-ttu-id="72530-196">El nombre de variable `num` de los ejemplos anteriores se evalúa como el entero 10, y no es de extrañar que el entero 10 sea también válido en los casos en los que `num` es válido.</span><span class="sxs-lookup"><span data-stu-id="72530-196">The variable name `num` in the previous examples evaluates to the integer 10, and it is no surprise that where `num` is valid, 10 is also valid.</span></span> <span data-ttu-id="72530-197">Lo mismo se aplica a los identificadores de las funciones y sus valores: siempre que se pueda usar el nombre de la función, se podrá usar la expresión lambda enlazada al mismo.</span><span class="sxs-lookup"><span data-stu-id="72530-197">The same is true of function identifiers and their values: anywhere the name of the function can be used, the lambda expression to which it is bound can be used.</span></span>

<span data-ttu-id="72530-198">En el siguiente ejemplo, se define una función `Boolean` denominada `isNegative` y, a continuación, se usan indistintamente el nombre y la definición de la función.</span><span class="sxs-lookup"><span data-stu-id="72530-198">The following example defines a `Boolean` function called `isNegative`, and then uses the name of the function and the definition of the function interchangeably.</span></span> <span data-ttu-id="72530-199">En los tres ejemplos siguientes, se devuelve y se muestra `False`.</span><span class="sxs-lookup"><span data-stu-id="72530-199">The next three examples all return and display `False`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet43.fs)]

<span data-ttu-id="72530-200">Para ir incluso un poco más lejos, reemplace `applyIt` por el valor al que está enlazada la función `applyIt`.</span><span class="sxs-lookup"><span data-stu-id="72530-200">To take it one step further, substitute the value that `applyIt` is bound to for `applyIt`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet44.fs)]

## <a name="functions-are-first-class-values-in-f"></a><span data-ttu-id="72530-201">Las funciones son valores de primera clase en F\#</span><span class="sxs-lookup"><span data-stu-id="72530-201">Functions Are First-Class Values in F\#</span></span>

<span data-ttu-id="72530-202">En los ejemplos que figuran en las secciones anteriores, se muestra que las funciones en F# cumplen los criterios de valores de primera clase:</span><span class="sxs-lookup"><span data-stu-id="72530-202">The examples in the previous sections demonstrate that functions in F# satisfy the criteria for being first-class values in F#:</span></span>

- <span data-ttu-id="72530-203">Se puede enlazar un identificador a una definición de función.</span><span class="sxs-lookup"><span data-stu-id="72530-203">You can bind an identifier to a function definition.</span></span>
[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet21.fs)]

- <span data-ttu-id="72530-204">Se puede almacenar una función en una estructura de datos.</span><span class="sxs-lookup"><span data-stu-id="72530-204">You can store a function in a data structure.</span></span>
[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet45.fs)]

- <span data-ttu-id="72530-205">Se puede pasar una función como argumento.</span><span class="sxs-lookup"><span data-stu-id="72530-205">You can pass a function as an argument.</span></span>
[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet46.fs)]

- <span data-ttu-id="72530-206">Se puede devolver una función como valor de una llamada de función.</span><span class="sxs-lookup"><span data-stu-id="72530-206">You can return a function as the value of a function call.</span></span>
[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet32.fs)]

<span data-ttu-id="72530-207">Para obtener más información sobre F #, vea la [Referencia del lenguaje f #](../language-reference/index.md).</span><span class="sxs-lookup"><span data-stu-id="72530-207">For more information about F#, see the [F# Language Reference](../language-reference/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="72530-208">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="72530-208">Example</span></span>

### <a name="description"></a><span data-ttu-id="72530-209">Descripción</span><span class="sxs-lookup"><span data-stu-id="72530-209">Description</span></span>

<span data-ttu-id="72530-210">El código siguiente contiene todos los ejemplos de este tema.</span><span class="sxs-lookup"><span data-stu-id="72530-210">The following code contains all the examples in this topic.</span></span>

### <a name="code"></a><span data-ttu-id="72530-211">Código</span><span class="sxs-lookup"><span data-stu-id="72530-211">Code</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet47.fs)]

## <a name="see-also"></a><span data-ttu-id="72530-212">Consulte también</span><span class="sxs-lookup"><span data-stu-id="72530-212">See also</span></span>

- [<span data-ttu-id="72530-213">Listas</span><span class="sxs-lookup"><span data-stu-id="72530-213">Lists</span></span>](../language-reference/lists.md)
- [<span data-ttu-id="72530-214">Tuplas</span><span class="sxs-lookup"><span data-stu-id="72530-214">Tuples</span></span>](../language-reference/tuples.md)
- [<span data-ttu-id="72530-215">Funciones</span><span class="sxs-lookup"><span data-stu-id="72530-215">Functions</span></span>](../language-reference/functions/index.md)
- [<span data-ttu-id="72530-216">`let` Enlaces</span><span class="sxs-lookup"><span data-stu-id="72530-216">`let` Bindings</span></span>](../language-reference/functions/let-bindings.md)
- [<span data-ttu-id="72530-217">Expresiones lambda: `fun` palabra clave</span><span class="sxs-lookup"><span data-stu-id="72530-217">Lambda Expressions: The `fun` Keyword</span></span>](../language-reference/functions/lambda-expressions-the-fun-keyword.md)
