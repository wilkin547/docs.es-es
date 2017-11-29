---
title: "Parámetros y argumentos (F#)"
description: "Obtenga información sobre la compatibilidad de idioma de F # para definir parámetros y pasar argumentos a funciones, métodos y propiedades."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 9b37a5c4-9263-4513-822a-fbb0d1004254
ms.openlocfilehash: 50f54bacd9ba7ec20a7151794734f93200df9f2d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="parameters-and-arguments"></a><span data-ttu-id="7a042-104">Parámetros y argumentos</span><span class="sxs-lookup"><span data-stu-id="7a042-104">Parameters and Arguments</span></span>

<span data-ttu-id="7a042-105">Este tema describe la compatibilidad de idioma para definir parámetros y pasar argumentos a funciones, métodos y propiedades.</span><span class="sxs-lookup"><span data-stu-id="7a042-105">This topic describes language support for defining parameters and passing arguments to functions, methods, and properties.</span></span> <span data-ttu-id="7a042-106">Incluye información sobre cómo pasar por referencia y cómo definir y utilizar métodos que pueden tomar un número variable de argumentos.</span><span class="sxs-lookup"><span data-stu-id="7a042-106">It includes information about how to pass by reference, and how to define and use methods that can take a variable number of arguments.</span></span>


## <a name="parameters-and-arguments"></a><span data-ttu-id="7a042-107">Parámetros y argumentos</span><span class="sxs-lookup"><span data-stu-id="7a042-107">Parameters and Arguments</span></span>
<span data-ttu-id="7a042-108">El término *parámetro* se usa para describir los nombres para los valores que se esperan que se proporcionen.</span><span class="sxs-lookup"><span data-stu-id="7a042-108">The term *parameter* is used to describe the names for values that are expected to be supplied.</span></span> <span data-ttu-id="7a042-109">El término *argumento* se usa para los valores proporcionados para cada parámetro.</span><span class="sxs-lookup"><span data-stu-id="7a042-109">The term *argument* is used for the values provided for each parameter.</span></span>

<span data-ttu-id="7a042-110">Pueden especificarse los parámetros en la tupla o formulario currificada o en alguna combinación de los dos.</span><span class="sxs-lookup"><span data-stu-id="7a042-110">Parameters can be specified in tuple or curried form, or in some combination of the two.</span></span> <span data-ttu-id="7a042-111">Puede pasar argumentos mediante un nombre de parámetro explícito.</span><span class="sxs-lookup"><span data-stu-id="7a042-111">You can pass arguments by using an explicit parameter name.</span></span> <span data-ttu-id="7a042-112">Parámetros de métodos pueden especificarse como opcionales y se le asigna un valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="7a042-112">Parameters of methods can be specified as optional and given a default value.</span></span>


## <a name="parameter-patterns"></a><span data-ttu-id="7a042-113">Modelos de parámetros</span><span class="sxs-lookup"><span data-stu-id="7a042-113">Parameter Patterns</span></span>
<span data-ttu-id="7a042-114">En general, los parámetros proporcionados a las funciones y los métodos son modelos separados por espacios.</span><span class="sxs-lookup"><span data-stu-id="7a042-114">Parameters supplied to functions and methods are, in general, patterns separated by spaces.</span></span> <span data-ttu-id="7a042-115">Esto significa que, en principio, cualquiera de los modelos descritos en [expresiones de coincidencia](match-expressions.md) puede utilizarse en una lista de parámetros para una función o un miembro.</span><span class="sxs-lookup"><span data-stu-id="7a042-115">This means that, in principle, any of the patterns described in [Match Expressions](match-expressions.md) can be used in a parameter list for a function or member.</span></span>

<span data-ttu-id="7a042-116">Métodos normalmente usan la forma de pasar argumentos tupla.</span><span class="sxs-lookup"><span data-stu-id="7a042-116">Methods usually use the tuple form of passing arguments.</span></span> <span data-ttu-id="7a042-117">Dado que la forma de tupla coincide con la forma en que se pasan argumentos en los métodos de .NET se obtiene un resultado más claro desde la perspectiva de otros lenguajes. NET.</span><span class="sxs-lookup"><span data-stu-id="7a042-117">This achieves a clearer result from the perspective of other .NET languages because the tuple form matches the way arguments are passed in .NET methods.</span></span>

<span data-ttu-id="7a042-118">El formulario currificado se suele utilizar con funciones creadas con `let` enlaces.</span><span class="sxs-lookup"><span data-stu-id="7a042-118">The curried form is most often used with functions created by using `let` bindings.</span></span>

<span data-ttu-id="7a042-119">El pseudocódigo siguiente muestra ejemplos de tupla y los argumentos currificadas.</span><span class="sxs-lookup"><span data-stu-id="7a042-119">The following pseudocode shows examples of tuple and curried arguments.</span></span>

```fsharp
// Tuple form.
member this.SomeMethod(param1, param2) = ...
// Curried form.
let function1 param1 param2 = ...
```

<span data-ttu-id="7a042-120">Combinar ambas formas son posibles cuando algunos argumentos no son tuplas y otros no.</span><span class="sxs-lookup"><span data-stu-id="7a042-120">Combined forms are possible when some arguments are in tuples and some are not.</span></span>

```fsharp
let function2 param1 (param2a, param2b) param3 = ...
```

<span data-ttu-id="7a042-121">Otros modelos también se pueden utilizar en listas de parámetros, pero si el patrón de parámetro no coincide con todas las entradas posibles, puede que haya una coincidencia incompleta en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="7a042-121">Other patterns can also be used in parameter lists, but if the parameter pattern does not match all possible inputs, there might be an incomplete match at run time.</span></span> <span data-ttu-id="7a042-122">La excepción `MatchFailureException` se genera cuando el valor de un argumento no coincide con los patrones especificados en la lista de parámetros.</span><span class="sxs-lookup"><span data-stu-id="7a042-122">The exception `MatchFailureException` is generated when the value of an argument does not match the patterns specified in the parameter list.</span></span> <span data-ttu-id="7a042-123">El compilador emite una advertencia cuando un modelo de parámetro permite coincidencias incompletas.</span><span class="sxs-lookup"><span data-stu-id="7a042-123">The compiler issues a warning when a parameter pattern allows for incomplete matches.</span></span> <span data-ttu-id="7a042-124">Al menos otro modelo es suele resultar útil para listas de parámetros y se muestra el patrón de carácter comodín.</span><span class="sxs-lookup"><span data-stu-id="7a042-124">At least one other pattern is commonly useful for parameter lists, and that is the wildcard pattern.</span></span> <span data-ttu-id="7a042-125">Usar el patrón de carácter comodín en una lista de parámetros cuando desee pasar por alto los argumentos que se proporcionan.</span><span class="sxs-lookup"><span data-stu-id="7a042-125">You use the wildcard pattern in a parameter list when you simply want to ignore any arguments that are supplied.</span></span> <span data-ttu-id="7a042-126">El código siguiente muestra el uso del patrón de carácter comodín en una lista de argumentos.</span><span class="sxs-lookup"><span data-stu-id="7a042-126">The following code illustrates the use of the wildcard pattern in an argument list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3801.fs)]

<span data-ttu-id="7a042-127">El patrón de carácter comodín puede ser útil cuando no necesite los argumentos pasados, como en el punto de entrada principal a un programa, cuando no está interesado en los argumentos de línea de comandos que normalmente se proporcionan como una matriz de cadenas, como en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="7a042-127">The wildcard pattern can be useful whenever you do not need the arguments passed in, such as in the main entry point to a program, when you are not interested in the command-line arguments that are normally supplied as a string array, as in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3802.fs)]

<span data-ttu-id="7a042-128">Otros patrones que a veces se usan argumentos de entrada son el `as` patrón y patrones de identificador asociados con uniones discriminadas y modelos activos.</span><span class="sxs-lookup"><span data-stu-id="7a042-128">Other patterns that are sometimes used in arguments are the `as` pattern, and identifier patterns associated with discriminated unions and active patterns.</span></span> <span data-ttu-id="7a042-129">Puede usar el modelo de unión discriminada de caso único como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="7a042-129">You can use the single-case discriminated union pattern as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3803.fs)]

<span data-ttu-id="7a042-130">La salida es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="7a042-130">The output is as follows.</span></span>

```
Data begins at 0 and ends at 4 in string Et tu, Brute?
Et tu
```

<span data-ttu-id="7a042-131">Modelos activos pueden resultar útiles como parámetros, por ejemplo, al transformar un argumento a un formato deseado, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7a042-131">Active patterns can be useful as parameters, for example, when transforming an argument into a desired format, as in the following example:</span></span>

```fsharp
type Point = { x : float; y : float }

let (| Polar |) { x = x; y = y} =
    ( sqrt (x*x + y*y), System.Math.Atan (y/ x) )

let radius (Polar(r, _)) = r
let angle (Polar(_, theta)) = theta
```

<span data-ttu-id="7a042-132">Puede usar el `as` patrón para almacenar un valor coincidente como un valor local, como se muestra en la siguiente línea de código.</span><span class="sxs-lookup"><span data-stu-id="7a042-132">You can use the `as` pattern to store a matched value as a local value, as is shown in the following line of code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3805.fs)]

<span data-ttu-id="7a042-133">Otro modelo que se usa ocasionalmente es una función que deja el último argumento sin nombre mediante el suministro, como el cuerpo de la función, una expresión lambda que inmediatamente realiza una coincidencia de patrones en el argumento implícito.</span><span class="sxs-lookup"><span data-stu-id="7a042-133">Another pattern that is used occasionally is a function that leaves the last argument unnamed by providing, as the body of the function, a lambda expression that immediately performs a pattern match on the implicit argument.</span></span> <span data-ttu-id="7a042-134">Un ejemplo de esto es la siguiente línea de código.</span><span class="sxs-lookup"><span data-stu-id="7a042-134">An example of this is the following line of code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3804.fs)]

<span data-ttu-id="7a042-135">Este código define una función que toma una lista genérica y devuelve `true` si la lista está vacía, y `false` en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="7a042-135">This code defines a function that takes a generic list and returns `true` if the list is empty, and `false` otherwise.</span></span> <span data-ttu-id="7a042-136">El uso de estas técnicas puede hacer que el código más difícil de leer.</span><span class="sxs-lookup"><span data-stu-id="7a042-136">The use of such techniques can make code more difficult to read.</span></span>

<span data-ttu-id="7a042-137">En ocasiones, los patrones que conllevan coincidencias incompletas resultan útiles, por ejemplo, si sabe que las listas en el programa tienen solo tres elementos, podría usar un patrón similar al siguiente en una lista de parámetros.</span><span class="sxs-lookup"><span data-stu-id="7a042-137">Occasionally, patterns that involve incomplete matches are useful, for example, if you know that the lists in your program have only three elements, you might use a pattern like the following in a parameter list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3806.fs)]

<span data-ttu-id="7a042-138">El uso de patrones que tengan coincidencias incompletas mejor está reservado para la creación de prototipos rápida y otros usos temporales.</span><span class="sxs-lookup"><span data-stu-id="7a042-138">The use of patterns that have incomplete matches is best reserved for quick prototyping and other temporary uses.</span></span> <span data-ttu-id="7a042-139">El compilador emitirá una advertencia para ese código.</span><span class="sxs-lookup"><span data-stu-id="7a042-139">The compiler will issue a warning for such code.</span></span> <span data-ttu-id="7a042-140">Estos patrones no pueden cubrir el caso general de todas las entradas posibles y, por tanto, no son adecuados para las API de componentes.</span><span class="sxs-lookup"><span data-stu-id="7a042-140">Such patterns cannot cover the general case of all possible inputs and therefore are not suitable for component APIs.</span></span>

## <a name="named-arguments"></a><span data-ttu-id="7a042-141">Argumentos con nombre</span><span class="sxs-lookup"><span data-stu-id="7a042-141">Named Arguments</span></span>
<span data-ttu-id="7a042-142">Posición en una lista de argumentos separados por comas se pueden especificar argumentos para los métodos, o se puede pasar a un método explícitamente proporcionando el nombre, seguido por un signo igual y el valor que se pasará en.</span><span class="sxs-lookup"><span data-stu-id="7a042-142">Arguments for methods can be specified by position in a comma-separated argument list, or they can be passed to a method explicitly by providing the name, followed by an equal sign and the value to be passed in.</span></span> <span data-ttu-id="7a042-143">Si no especifica al proporcionar el nombre, pueden aparecer en un orden diferente del que se utiliza en la declaración.</span><span class="sxs-lookup"><span data-stu-id="7a042-143">If specified by providing the name, they can appear in a different order from that used in the declaration.</span></span>

<span data-ttu-id="7a042-144">Argumentos con nombre pueden que el código sea más legible y más adaptable para ciertos tipos de cambios en la API, como la reordenación de parámetros de método.</span><span class="sxs-lookup"><span data-stu-id="7a042-144">Named arguments can make code more readable and more adaptable to certain types of changes in the API, such as a reordering of method parameters.</span></span>

<span data-ttu-id="7a042-145">Argumentos con nombre se permiten únicamente para los métodos, no para `let`-enlaza las funciones, valores de función o expresiones lambda.</span><span class="sxs-lookup"><span data-stu-id="7a042-145">Named arguments are allowed only for methods, not for `let`-bound functions, function values, or lambda expressions.</span></span>

<span data-ttu-id="7a042-146">En el ejemplo de código siguiente se muestra el uso de argumentos con nombre.</span><span class="sxs-lookup"><span data-stu-id="7a042-146">The following code example demonstrates the use of named arguments.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3807.fs)]

<span data-ttu-id="7a042-147">En una llamada a un constructor de clase, puede establecer los valores de propiedades de la clase mediante una sintaxis similar a la de argumentos con nombre.</span><span class="sxs-lookup"><span data-stu-id="7a042-147">In a call to a class constructor, you can set the values of properties of the class by using a syntax similar to that of named arguments.</span></span> <span data-ttu-id="7a042-148">En el ejemplo siguiente se muestra esta sintaxis.</span><span class="sxs-lookup"><span data-stu-id="7a042-148">The following example shows this syntax.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

<span data-ttu-id="7a042-149">Para obtener más información, consulte [constructores (F #)](https://msdn.microsoft.com/library/2cd0ed07-d214-4125-8317-4f288af99f05).</span><span class="sxs-lookup"><span data-stu-id="7a042-149">For more information, see [Constructors (F#)](https://msdn.microsoft.com/library/2cd0ed07-d214-4125-8317-4f288af99f05).</span></span>

## <a name="optional-parameters"></a><span data-ttu-id="7a042-150">Parámetros opcionales</span><span class="sxs-lookup"><span data-stu-id="7a042-150">Optional Parameters</span></span>
<span data-ttu-id="7a042-151">Puede especificar un parámetro opcional para un método mediante un signo de interrogación delante del nombre de parámetro.</span><span class="sxs-lookup"><span data-stu-id="7a042-151">You can specify an optional parameter for a method by using a question mark in front of the parameter name.</span></span> <span data-ttu-id="7a042-152">Parámetros opcionales se interpretan como el tipo de opción de F #, por lo que puede consultar en la manera habitual que se consultan los tipos de opciones mediante el uso de un `match` expresión con `Some` y `None`.</span><span class="sxs-lookup"><span data-stu-id="7a042-152">Optional parameters are interpreted as the F# option type, so you can query them in the regular way that option types are queried, by using a `match` expression with `Some` and `None`.</span></span> <span data-ttu-id="7a042-153">Parámetros opcionales solo se permiten en los miembros, no en las funciones creadas mediante `let` enlaces.</span><span class="sxs-lookup"><span data-stu-id="7a042-153">Optional parameters are permitted only on members, not on functions created by using `let` bindings.</span></span>

<span data-ttu-id="7a042-154">También puede usar una función `defaultArg`, que establece un valor predeterminado de un argumento opcional.</span><span class="sxs-lookup"><span data-stu-id="7a042-154">You can also use a function `defaultArg`, which sets a default value of an optional argument.</span></span> <span data-ttu-id="7a042-155">El `defaultArg` función toma el parámetro opcional como primer argumento y el valor predeterminado como el segundo.</span><span class="sxs-lookup"><span data-stu-id="7a042-155">The `defaultArg` function takes the optional parameter as the first argument and the default value as the second.</span></span>

<span data-ttu-id="7a042-156">En el ejemplo siguiente se muestra el uso de los parámetros opcionales.</span><span class="sxs-lookup"><span data-stu-id="7a042-156">The following example illustrates the use of optional parameters.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3808.fs)]

<span data-ttu-id="7a042-157">La salida es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="7a042-157">The output is as follows.</span></span>

```
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 4800 Duplex: Half Parity: false
Baud Rate: 300 Duplex: Half Parity: true
```

## <a name="passing-by-reference"></a><span data-ttu-id="7a042-158">Pasar por referencia</span><span class="sxs-lookup"><span data-stu-id="7a042-158">Passing by Reference</span></span>
<span data-ttu-id="7a042-159">F # admite el `byref` palabra clave, que especifica que un parámetro se pasa por referencia.</span><span class="sxs-lookup"><span data-stu-id="7a042-159">F# supports the `byref` keyword, which specifies that a parameter is passed by reference.</span></span> <span data-ttu-id="7a042-160">Esto significa que cualquier cambio en el valor se conserva después de la ejecución de la función.</span><span class="sxs-lookup"><span data-stu-id="7a042-160">This means that any changes to the value are retained after the execution of the function.</span></span> <span data-ttu-id="7a042-161">Valores proporcionados a un `byref` parámetro debe ser mutable.</span><span class="sxs-lookup"><span data-stu-id="7a042-161">Values provided to a `byref` parameter must be mutable.</span></span> <span data-ttu-id="7a042-162">Como alternativa, puede pasar las celdas de referencia del tipo adecuado.</span><span class="sxs-lookup"><span data-stu-id="7a042-162">Alternatively, you can pass reference cells of the appropriate type.</span></span>

<span data-ttu-id="7a042-163">Pasar por referencia en los lenguajes .NET ha evolucionado como un modo para devolver más de un valor de una función.</span><span class="sxs-lookup"><span data-stu-id="7a042-163">Passing by reference in .NET languages evolved as a way to return more than one value from a function.</span></span> <span data-ttu-id="7a042-164">En F #, puede devolver una tupla con este fin, o utilizar una celda de referencia mutable como un parámetro.</span><span class="sxs-lookup"><span data-stu-id="7a042-164">In F#, you can return a tuple for this purpose, or use a mutable reference cell as a parameter.</span></span> <span data-ttu-id="7a042-165">El `byref` parámetro se proporciona principalmente para la interoperabilidad con bibliotecas de. NET.</span><span class="sxs-lookup"><span data-stu-id="7a042-165">The `byref` parameter is mainly provided for interoperability with .NET libraries.</span></span>

<span data-ttu-id="7a042-166">Los siguientes ejemplos ilustran el uso de la `byref` (palabra clave).</span><span class="sxs-lookup"><span data-stu-id="7a042-166">The following examples illustrate the use of the `byref` keyword.</span></span> <span data-ttu-id="7a042-167">Tenga en cuenta que cuando se usa una celda de referencia como un parámetro, debe crear una celda de referencia como un valor con nombre y usarlo como el parámetro, no basta con agregar el `ref` operador tal como se muestra en la primera llamada a `Increment` en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="7a042-167">Note that when you use a reference cell as a parameter, you must create a reference cell as a named value and use that as the parameter, not just add the `ref` operator as shown in the first call to `Increment` in the following code.</span></span> <span data-ttu-id="7a042-168">Porque al crear una celda de referencia, crea una copia del valor subyacente, la primera llamada se limita a incrementar un valor temporal.</span><span class="sxs-lookup"><span data-stu-id="7a042-168">Because creating a reference cell creates a copy of the underlying value, the first call just increments a temporary value.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3809.fs)]

<span data-ttu-id="7a042-169">Puede utilizar una tupla como valor devuelto para almacenarlas `out` parámetros en métodos de la biblioteca. NET.</span><span class="sxs-lookup"><span data-stu-id="7a042-169">You can use a tuple as a return value to store any `out` parameters in .NET library methods.</span></span> <span data-ttu-id="7a042-170">Como alternativa, puede tratar la `out` parámetro como un `byref` parámetro.</span><span class="sxs-lookup"><span data-stu-id="7a042-170">Alternatively, you can treat the `out` parameter as a `byref` parameter.</span></span> <span data-ttu-id="7a042-171">En el ejemplo de código siguiente se muestra ambas maneras.</span><span class="sxs-lookup"><span data-stu-id="7a042-171">The following code example illustrates both ways.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3810.fs)]

## <a name="parameter-arrays"></a><span data-ttu-id="7a042-172">Matrices de parámetros</span><span class="sxs-lookup"><span data-stu-id="7a042-172">Parameter Arrays</span></span>
<span data-ttu-id="7a042-173">En ocasiones, es necesario definir una función que toma un número arbitrario de parámetros de tipo heterogéneo.</span><span class="sxs-lookup"><span data-stu-id="7a042-173">Occasionally it is necessary to define a function that takes an arbitrary number of parameters of heterogeneous type.</span></span> <span data-ttu-id="7a042-174">No sería práctico volver a crear todos los métodos sobrecargados posible para tener en cuenta para todos los tipos que se pudieron utilizar.</span><span class="sxs-lookup"><span data-stu-id="7a042-174">It would not be practical to create all the possible overloaded methods to account for all the types that could be used.</span></span> <span data-ttu-id="7a042-175">Las implementaciones de .NET proporcionan compatibilidad para dichos métodos a través de la característica de matriz de parámetros.</span><span class="sxs-lookup"><span data-stu-id="7a042-175">The .NET implementations provide support for such methods through the parameter array feature.</span></span> <span data-ttu-id="7a042-176">Puede proporcionar un método que toma una matriz de parámetros en la firma con un número arbitrario de parámetros.</span><span class="sxs-lookup"><span data-stu-id="7a042-176">A method that takes a parameter array in its signature can be provided with an arbitrary number of parameters.</span></span> <span data-ttu-id="7a042-177">Los parámetros se colocan en una matriz.</span><span class="sxs-lookup"><span data-stu-id="7a042-177">The parameters are put into an array.</span></span> <span data-ttu-id="7a042-178">El tipo de los elementos de matriz determina los tipos de parámetro que pueden pasarse a la función.</span><span class="sxs-lookup"><span data-stu-id="7a042-178">The type of the array elements determines the parameter types that can be passed to the function.</span></span> <span data-ttu-id="7a042-179">Si define la matriz de parámetros con `System.Object` como el tipo de elemento, a continuación, el código de cliente puede pasar valores de cualquier tipo.</span><span class="sxs-lookup"><span data-stu-id="7a042-179">If you define the parameter array with `System.Object` as the element type, then client code can pass values of any type.</span></span>

<span data-ttu-id="7a042-180">En F #, las matrices de parámetros solo pueden definirse en métodos.</span><span class="sxs-lookup"><span data-stu-id="7a042-180">In F#, parameter arrays can only be defined in methods.</span></span> <span data-ttu-id="7a042-181">No se utilizaron en funciones independientes ni en funciones que se definen en módulos.</span><span class="sxs-lookup"><span data-stu-id="7a042-181">They cannot be used in standalone functions or functions that are defined in modules.</span></span>

<span data-ttu-id="7a042-182">Definir una matriz de parámetros mediante el `ParamArray` atributo.</span><span class="sxs-lookup"><span data-stu-id="7a042-182">You define a parameter array by using the `ParamArray` attribute.</span></span> <span data-ttu-id="7a042-183">El `ParamArray` atributo solo se puede aplicar al último parámetro.</span><span class="sxs-lookup"><span data-stu-id="7a042-183">The `ParamArray` attribute can only be applied to the last parameter.</span></span>

<span data-ttu-id="7a042-184">El código siguiente muestra llamando a un método de .NET que toma una matriz de parámetros y la definición de un tipo de F # que tiene un método que toma una matriz de parámetros.</span><span class="sxs-lookup"><span data-stu-id="7a042-184">The following code illustrates both calling a .NET method that takes a parameter array and the definition of a type in F# that has a method that takes a parameter array.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-2/snippet3811.fs)]

<span data-ttu-id="7a042-185">Cuando se ejecute en un proyecto, el resultado del código anterior es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="7a042-185">When run in a project, the output of the previous code is as follows:</span></span>

```
a 1 10 Hello world 1 True
"a"
1
10.0
"Hello world"
1u
true
```

## <a name="see-also"></a><span data-ttu-id="7a042-186">Vea también</span><span class="sxs-lookup"><span data-stu-id="7a042-186">See Also</span></span>
[<span data-ttu-id="7a042-187">Miembros</span><span class="sxs-lookup"><span data-stu-id="7a042-187">Members</span></span>](members/index.md)
