---
title: Parámetros y argumentos
description: Obtenga información sobre F# compatibilidad con lenguajes para definir parámetros y pasar argumentos a funciones, métodos y propiedades.
ms.date: 05/16/2016
ms.openlocfilehash: 08332ad9ab1c1a05f68ba27b2f1513ad0fe7c4d5
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2018
ms.locfileid: "53612483"
---
# <a name="parameters-and-arguments"></a><span data-ttu-id="2087f-103">Parámetros y argumentos</span><span class="sxs-lookup"><span data-stu-id="2087f-103">Parameters and Arguments</span></span>

<span data-ttu-id="2087f-104">Este tema describe la compatibilidad con lenguajes para definir parámetros y pasar argumentos a funciones, métodos y propiedades.</span><span class="sxs-lookup"><span data-stu-id="2087f-104">This topic describes language support for defining parameters and passing arguments to functions, methods, and properties.</span></span> <span data-ttu-id="2087f-105">Incluye información acerca de cómo pasar por referencia y cómo definir y usar los métodos que pueden tomar un número variable de argumentos.</span><span class="sxs-lookup"><span data-stu-id="2087f-105">It includes information about how to pass by reference, and how to define and use methods that can take a variable number of arguments.</span></span>

## <a name="parameters-and-arguments"></a><span data-ttu-id="2087f-106">Parámetros y argumentos</span><span class="sxs-lookup"><span data-stu-id="2087f-106">Parameters and Arguments</span></span>

<span data-ttu-id="2087f-107">El término *parámetro* se usa para describir los nombres de los valores que se esperan que se proporcione.</span><span class="sxs-lookup"><span data-stu-id="2087f-107">The term *parameter* is used to describe the names for values that are expected to be supplied.</span></span> <span data-ttu-id="2087f-108">El término *argumento* se usa para los valores proporcionados para cada parámetro.</span><span class="sxs-lookup"><span data-stu-id="2087f-108">The term *argument* is used for the values provided for each parameter.</span></span>

<span data-ttu-id="2087f-109">Los parámetros pueden especificarse en la tupla o currificada, o en alguna combinación de ambos.</span><span class="sxs-lookup"><span data-stu-id="2087f-109">Parameters can be specified in tuple or curried form, or in some combination of the two.</span></span> <span data-ttu-id="2087f-110">Puede pasar argumentos mediante el uso de un nombre de parámetro explícito.</span><span class="sxs-lookup"><span data-stu-id="2087f-110">You can pass arguments by using an explicit parameter name.</span></span> <span data-ttu-id="2087f-111">Parámetros de métodos pueden especificarse como opcionales y proporcionado un valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="2087f-111">Parameters of methods can be specified as optional and given a default value.</span></span>

## <a name="parameter-patterns"></a><span data-ttu-id="2087f-112">Patrones de parámetros</span><span class="sxs-lookup"><span data-stu-id="2087f-112">Parameter Patterns</span></span>

<span data-ttu-id="2087f-113">En general, los parámetros proporcionados a las funciones y métodos son patrones separados por espacios.</span><span class="sxs-lookup"><span data-stu-id="2087f-113">Parameters supplied to functions and methods are, in general, patterns separated by spaces.</span></span> <span data-ttu-id="2087f-114">Esto significa que, en principio, cualquiera de los patrones descritos en [expresiones de coincidencia](match-expressions.md) puede usarse en una lista de parámetros para una función o miembro.</span><span class="sxs-lookup"><span data-stu-id="2087f-114">This means that, in principle, any of the patterns described in [Match Expressions](match-expressions.md) can be used in a parameter list for a function or member.</span></span>

<span data-ttu-id="2087f-115">Métodos usan normalmente la forma de pasar argumentos de tupla.</span><span class="sxs-lookup"><span data-stu-id="2087f-115">Methods usually use the tuple form of passing arguments.</span></span> <span data-ttu-id="2087f-116">Dado que la forma de tupla coincide con la forma en que se pasan argumentos en los métodos de .NET se consigue un resultado más claro desde la perspectiva de otros lenguajes. NET.</span><span class="sxs-lookup"><span data-stu-id="2087f-116">This achieves a clearer result from the perspective of other .NET languages because the tuple form matches the way arguments are passed in .NET methods.</span></span>

<span data-ttu-id="2087f-117">Currificada más a menudo se usa con funciones creadas con `let` enlaces.</span><span class="sxs-lookup"><span data-stu-id="2087f-117">The curried form is most often used with functions created by using `let` bindings.</span></span>

<span data-ttu-id="2087f-118">El pseudocódigo siguiente muestra ejemplos de tupla y argumentos currificados.</span><span class="sxs-lookup"><span data-stu-id="2087f-118">The following pseudocode shows examples of tuple and curried arguments.</span></span>

```fsharp
// Tuple form.
member this.SomeMethod(param1, param2) = ...
// Curried form.
let function1 param1 param2 = ...
```

<span data-ttu-id="2087f-119">Combinar ambas formas son posibles cuando algunos argumentos están en tuplas y otros no.</span><span class="sxs-lookup"><span data-stu-id="2087f-119">Combined forms are possible when some arguments are in tuples and some are not.</span></span>

```fsharp
let function2 param1 (param2a, param2b) param3 = ...
```

<span data-ttu-id="2087f-120">Otros patrones también pueden usarse en las listas de parámetros, pero si el modelo de parámetro no coincide con todas las entradas posibles, podría haber una coincidencia incompleta en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="2087f-120">Other patterns can also be used in parameter lists, but if the parameter pattern does not match all possible inputs, there might be an incomplete match at run time.</span></span> <span data-ttu-id="2087f-121">La excepción `MatchFailureException` se genera cuando el valor de un argumento no coincide con los patrones especificados en la lista de parámetros.</span><span class="sxs-lookup"><span data-stu-id="2087f-121">The exception `MatchFailureException` is generated when the value of an argument does not match the patterns specified in the parameter list.</span></span> <span data-ttu-id="2087f-122">El compilador emite una advertencia cuando un modelo de parámetro permite coincidencias incompletas.</span><span class="sxs-lookup"><span data-stu-id="2087f-122">The compiler issues a warning when a parameter pattern allows for incomplete matches.</span></span> <span data-ttu-id="2087f-123">Al menos otro patrón es suele resultar útil para las listas de parámetros, y ese es el patrón de carácter comodín.</span><span class="sxs-lookup"><span data-stu-id="2087f-123">At least one other pattern is commonly useful for parameter lists, and that is the wildcard pattern.</span></span> <span data-ttu-id="2087f-124">Utilice el patrón de caracteres comodín en una lista de parámetros si desea omitir todos los argumentos que se proporcionan.</span><span class="sxs-lookup"><span data-stu-id="2087f-124">You use the wildcard pattern in a parameter list when you simply want to ignore any arguments that are supplied.</span></span> <span data-ttu-id="2087f-125">El código siguiente muestra el uso del patrón de carácter comodín en una lista de argumentos.</span><span class="sxs-lookup"><span data-stu-id="2087f-125">The following code illustrates the use of the wildcard pattern in an argument list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3801.fs)]

<span data-ttu-id="2087f-126">El carácter comodín puede ser útil cuando no necesite los argumentos pasados, como en el punto de entrada principal a un programa, cuando no esté interesado en los argumentos de línea de comandos que normalmente se proporcionan como una matriz de cadenas, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="2087f-126">The wildcard pattern can be useful whenever you do not need the arguments passed in, such as in the main entry point to a program, when you are not interested in the command-line arguments that are normally supplied as a string array, as in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3802.fs)]

<span data-ttu-id="2087f-127">Otros patrones que a veces se usan argumentos de entrada son el `as` patrón y patrones de identificador asociados a las uniones discriminadas y los patrones activos.</span><span class="sxs-lookup"><span data-stu-id="2087f-127">Other patterns that are sometimes used in arguments are the `as` pattern, and identifier patterns associated with discriminated unions and active patterns.</span></span> <span data-ttu-id="2087f-128">Puede usar el modelo de unión discriminada de caso único como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="2087f-128">You can use the single-case discriminated union pattern as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3803.fs)]

<span data-ttu-id="2087f-129">La salida es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="2087f-129">The output is as follows.</span></span>

```
Data begins at 0 and ends at 4 in string Et tu, Brute?
Et tu
```

<span data-ttu-id="2087f-130">Modelos activos pueden resultar útiles como parámetros, por ejemplo, cuando se transforma un argumento en un formato deseado, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2087f-130">Active patterns can be useful as parameters, for example, when transforming an argument into a desired format, as in the following example:</span></span>

```fsharp
type Point = { x : float; y : float }

let (| Polar |) { x = x; y = y} =
    ( sqrt (x*x + y*y), System.Math.Atan (y/ x) )

let radius (Polar(r, _)) = r
let angle (Polar(_, theta)) = theta
```

<span data-ttu-id="2087f-131">Puede usar el `as` patrón para almacenar un valor coincidente como un valor local, como se muestra en la siguiente línea de código.</span><span class="sxs-lookup"><span data-stu-id="2087f-131">You can use the `as` pattern to store a matched value as a local value, as is shown in the following line of code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3805.fs)]

<span data-ttu-id="2087f-132">Otro patrón que se usa ocasionalmente es una función que deja el último argumento sin nombre proporcionando, como el cuerpo de la función, una expresión lambda que inmediatamente se realiza una coincidencia de patrones en el argumento implícito.</span><span class="sxs-lookup"><span data-stu-id="2087f-132">Another pattern that is used occasionally is a function that leaves the last argument unnamed by providing, as the body of the function, a lambda expression that immediately performs a pattern match on the implicit argument.</span></span> <span data-ttu-id="2087f-133">Un ejemplo de esto es la siguiente línea de código.</span><span class="sxs-lookup"><span data-stu-id="2087f-133">An example of this is the following line of code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3804.fs)]

<span data-ttu-id="2087f-134">Este código define una función que toma una lista genérica y devuelve `true` si la lista está vacía, y `false` en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="2087f-134">This code defines a function that takes a generic list and returns `true` if the list is empty, and `false` otherwise.</span></span> <span data-ttu-id="2087f-135">El uso de dichas técnicas puede hacer que el código más difícil de leer.</span><span class="sxs-lookup"><span data-stu-id="2087f-135">The use of such techniques can make code more difficult to read.</span></span>

<span data-ttu-id="2087f-136">En ocasiones, los patrones que implican coincidencias incompletas son útiles, por ejemplo, si sabe que las listas en el programa tienen solo tres elementos, podría usar un patrón similar al siguiente en una lista de parámetros.</span><span class="sxs-lookup"><span data-stu-id="2087f-136">Occasionally, patterns that involve incomplete matches are useful, for example, if you know that the lists in your program have only three elements, you might use a pattern like the following in a parameter list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3806.fs)]

<span data-ttu-id="2087f-137">El uso de patrones que tienen coincidencias incompletas mejor está reservado para el desarrollo rápido de prototipos y otros usos temporales.</span><span class="sxs-lookup"><span data-stu-id="2087f-137">The use of patterns that have incomplete matches is best reserved for quick prototyping and other temporary uses.</span></span> <span data-ttu-id="2087f-138">El compilador emitirá una advertencia para dicho código.</span><span class="sxs-lookup"><span data-stu-id="2087f-138">The compiler will issue a warning for such code.</span></span> <span data-ttu-id="2087f-139">Estos patrones no pueden cubrir el caso general de todas las entradas posibles y, por tanto, no son adecuados para las API de componentes.</span><span class="sxs-lookup"><span data-stu-id="2087f-139">Such patterns cannot cover the general case of all possible inputs and therefore are not suitable for component APIs.</span></span>

## <a name="named-arguments"></a><span data-ttu-id="2087f-140">Argumentos con nombre</span><span class="sxs-lookup"><span data-stu-id="2087f-140">Named Arguments</span></span>

<span data-ttu-id="2087f-141">Posición en una lista de argumentos separados por comas se pueden especificar argumentos de métodos o se pueden pasar a un método explícitamente proporcionando el nombre, seguido por un signo igual y el valor que se pasarán en.</span><span class="sxs-lookup"><span data-stu-id="2087f-141">Arguments for methods can be specified by position in a comma-separated argument list, or they can be passed to a method explicitly by providing the name, followed by an equal sign and the value to be passed in.</span></span> <span data-ttu-id="2087f-142">Si se especifica al proporcionar el nombre, pueden aparecer en un orden diferente del que se utiliza en la declaración.</span><span class="sxs-lookup"><span data-stu-id="2087f-142">If specified by providing the name, they can appear in a different order from that used in the declaration.</span></span>

<span data-ttu-id="2087f-143">Argumentos con nombre pueden que el código sea más legible y más adaptable para ciertos tipos de cambios en la API, como la reordenación de parámetros del método.</span><span class="sxs-lookup"><span data-stu-id="2087f-143">Named arguments can make code more readable and more adaptable to certain types of changes in the API, such as a reordering of method parameters.</span></span>

<span data-ttu-id="2087f-144">Argumentos con nombre solo se permiten para los métodos, no para `let`-enlazado funciones, los valores de función o las expresiones lambda.</span><span class="sxs-lookup"><span data-stu-id="2087f-144">Named arguments are allowed only for methods, not for `let`-bound functions, function values, or lambda expressions.</span></span>

<span data-ttu-id="2087f-145">En el ejemplo de código siguiente se muestra el uso de argumentos con nombre.</span><span class="sxs-lookup"><span data-stu-id="2087f-145">The following code example demonstrates the use of named arguments.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3807.fs)]

<span data-ttu-id="2087f-146">En una llamada a un constructor de clase, puede establecer los valores de propiedades de la clase utilizando una sintaxis similar a la de argumentos con nombre.</span><span class="sxs-lookup"><span data-stu-id="2087f-146">In a call to a class constructor, you can set the values of properties of the class by using a syntax similar to that of named arguments.</span></span> <span data-ttu-id="2087f-147">El ejemplo siguiente muestra esta sintaxis.</span><span class="sxs-lookup"><span data-stu-id="2087f-147">The following example shows this syntax.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

<span data-ttu-id="2087f-148">Para obtener más información, consulte [constructores (F#)](https://msdn.microsoft.com/library/2cd0ed07-d214-4125-8317-4f288af99f05).</span><span class="sxs-lookup"><span data-stu-id="2087f-148">For more information, see [Constructors (F#)](https://msdn.microsoft.com/library/2cd0ed07-d214-4125-8317-4f288af99f05).</span></span>

## <a name="optional-parameters"></a><span data-ttu-id="2087f-149">Parámetros opcionales</span><span class="sxs-lookup"><span data-stu-id="2087f-149">Optional Parameters</span></span>

<span data-ttu-id="2087f-150">Puede especificar un parámetro opcional para un método mediante un signo de interrogación junto al nombre del parámetro.</span><span class="sxs-lookup"><span data-stu-id="2087f-150">You can specify an optional parameter for a method by using a question mark in front of the parameter name.</span></span> <span data-ttu-id="2087f-151">Los parámetros opcionales se interpretan como el F# opción tipo, por lo que puede consultar en la que se consultan los tipos de opciones mediante el uso de manera regular un `match` expresión con `Some` y `None`.</span><span class="sxs-lookup"><span data-stu-id="2087f-151">Optional parameters are interpreted as the F# option type, so you can query them in the regular way that option types are queried, by using a `match` expression with `Some` and `None`.</span></span> <span data-ttu-id="2087f-152">Los parámetros opcionales solo se permiten en los miembros, no en las funciones creadas mediante `let` enlaces.</span><span class="sxs-lookup"><span data-stu-id="2087f-152">Optional parameters are permitted only on members, not on functions created by using `let` bindings.</span></span>

<span data-ttu-id="2087f-153">Puede pasar valores opcionales existentes al método por nombre de parámetro, como `?arg=None` o `?arg=Some(3)` o `?arg=arg`.</span><span class="sxs-lookup"><span data-stu-id="2087f-153">You can pass existing optional values to method by parameter name, such as `?arg=None` or `?arg=Some(3)` or `?arg=arg`.</span></span> <span data-ttu-id="2087f-154">Esto puede ser útil al crear un método que pasa argumentos opcionales a otro método.</span><span class="sxs-lookup"><span data-stu-id="2087f-154">This can be useful when building a method that passes optional arguments to another method.</span></span>

<span data-ttu-id="2087f-155">También puede usar una función `defaultArg`, que establece un valor predeterminado de un argumento opcional.</span><span class="sxs-lookup"><span data-stu-id="2087f-155">You can also use a function `defaultArg`, which sets a default value of an optional argument.</span></span> <span data-ttu-id="2087f-156">El `defaultArg` función toma el parámetro opcional como el primer argumento y el valor predeterminado como el segundo.</span><span class="sxs-lookup"><span data-stu-id="2087f-156">The `defaultArg` function takes the optional parameter as the first argument and the default value as the second.</span></span>

<span data-ttu-id="2087f-157">El ejemplo siguiente muestra el uso de los parámetros opcionales.</span><span class="sxs-lookup"><span data-stu-id="2087f-157">The following example illustrates the use of optional parameters.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3808.fs)]

<span data-ttu-id="2087f-158">La salida es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="2087f-158">The output is as follows.</span></span>

```
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 4800 Duplex: Half Parity: false
Baud Rate: 300 Duplex: Half Parity: true
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 4800 Duplex: Half Parity: false
```

<span data-ttu-id="2087f-159">Para los fines de C# e interoperabilidad de Visual Basic puede utilizar los atributos `[<Optional; DefaultParameterValue<(...)>]` en F#, de modo que los llamadores verán un argumento como opcional.</span><span class="sxs-lookup"><span data-stu-id="2087f-159">For the purposes of C# and Visual Basic interop you can use the attributes `[<Optional; DefaultParameterValue<(...)>]` in F#, so that callers will see an argument as optional.</span></span> <span data-ttu-id="2087f-160">Esto es equivalente a definir el argumento como opcionales en C# como en `MyMethod(int i = 3)`.</span><span class="sxs-lookup"><span data-stu-id="2087f-160">This is equivalent to defining the argument as optional in C# as in `MyMethod(int i = 3)`.</span></span>

```fsharp
open System
open System.Runtime.InteropServices
type C = 
    static member Foo([<Optional; DefaultParameterValue("Hello world")>] message) =
        printfn "%s" message
```

<span data-ttu-id="2087f-161">El valor dado como argumento de `DefaultParameterValue` debe coincidir con el tipo del parámetro, es decir, la siguiente no se permite:</span><span class="sxs-lookup"><span data-stu-id="2087f-161">The value given as argument to `DefaultParameterValue` must match the type of the parameter, i.e. the following is not allowed:</span></span>

```fsharp
type C =
    static member Wrong([<Optional; DefaultParameterValue("string")>] i:int) = ()
```

<span data-ttu-id="2087f-162">En este caso, el compilador genera una advertencia y pasará por alto los dos atributos por completo.</span><span class="sxs-lookup"><span data-stu-id="2087f-162">In this case, the compiler generates a warning and will ignore both attributes altogether.</span></span> <span data-ttu-id="2087f-163">Tenga en cuenta que el valor predeterminado `null` debe ser la anotación de tipo, como en caso contrario, el compilador infiere un tipo incorrecto, es decir, `[<Optional; DefaultParameterValue(null:obj)>] o:obj`.</span><span class="sxs-lookup"><span data-stu-id="2087f-163">Note that the default value `null` needs to be type-annotated, as otherwise the compiler infers the wrong type, i.e. `[<Optional; DefaultParameterValue(null:obj)>] o:obj`.</span></span>

## <a name="passing-by-reference"></a><span data-ttu-id="2087f-164">Pasar por referencia</span><span class="sxs-lookup"><span data-stu-id="2087f-164">Passing by Reference</span></span>

<span data-ttu-id="2087f-165">Pasar un F# valor por referencia implica [zkratka](byrefs.md), que son tipos de puntero administrado.</span><span class="sxs-lookup"><span data-stu-id="2087f-165">Passing an F# value by reference involves [byrefs](byrefs.md), which are managed pointer types.</span></span> <span data-ttu-id="2087f-166">Guía para que el tipo debe usar es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="2087f-166">Guidance for which type to use is as follows:</span></span>

* <span data-ttu-id="2087f-167">Use `inref<'T>` si solo necesita leer el puntero.</span><span class="sxs-lookup"><span data-stu-id="2087f-167">Use `inref<'T>` if you only need to read the pointer.</span></span>
* <span data-ttu-id="2087f-168">Use `outref<'T>` si solo tiene que escribir en el puntero.</span><span class="sxs-lookup"><span data-stu-id="2087f-168">Use `outref<'T>` if you only need to write to the pointer.</span></span>
* <span data-ttu-id="2087f-169">Use `byref<'T>` si necesita leer de y escribir en el puntero.</span><span class="sxs-lookup"><span data-stu-id="2087f-169">Use `byref<'T>` if you need to both read from and write to the pointer.</span></span>

```fsharp
let example1 (x: inref<int>) = printfn "It's %d" x

let example2 (x: outref<int>) = x <- x + 1

let example3 (x: byref<int>) =
    printfn "It'd %d" x
    x <- x + 1

// No need to make it mutable, since it's read-only
let x = 1
example1 &x

// Needs to be mutable, since we write to it
let mutable y = 2
example2 &y
example3 &y // Now 'y' is 3
```

<span data-ttu-id="2087f-170">Dado que el parámetro es un puntero y el valor es mutable, cualquier cambio en el valor se conserva después de la ejecución de la función.</span><span class="sxs-lookup"><span data-stu-id="2087f-170">Because the parameter is a pointer and the value is mutable, any changes to the value are retained after the execution of the function.</span></span>

<span data-ttu-id="2087f-171">Puede utilizar una tupla como valor devuelto para almacenarlas `out` parámetros en métodos de la biblioteca. NET.</span><span class="sxs-lookup"><span data-stu-id="2087f-171">You can use a tuple as a return value to store any `out` parameters in .NET library methods.</span></span> <span data-ttu-id="2087f-172">Como alternativa, puede tratar el `out` parámetro como un `byref` parámetro.</span><span class="sxs-lookup"><span data-stu-id="2087f-172">Alternatively, you can treat the `out` parameter as a `byref` parameter.</span></span> <span data-ttu-id="2087f-173">El ejemplo de código siguiente muestra ambas maneras.</span><span class="sxs-lookup"><span data-stu-id="2087f-173">The following code example illustrates both ways.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3810.fs)]

## <a name="parameter-arrays"></a><span data-ttu-id="2087f-174">Matrices de parámetros</span><span class="sxs-lookup"><span data-stu-id="2087f-174">Parameter Arrays</span></span>

<span data-ttu-id="2087f-175">En ocasiones, es necesario definir una función que toma un número arbitrario de parámetros de tipo heterogéneo.</span><span class="sxs-lookup"><span data-stu-id="2087f-175">Occasionally it is necessary to define a function that takes an arbitrary number of parameters of heterogeneous type.</span></span> <span data-ttu-id="2087f-176">No sería práctico volver a crear todos los métodos sobrecargados posible para tener en cuenta para todos los tipos que se pueda usar.</span><span class="sxs-lookup"><span data-stu-id="2087f-176">It would not be practical to create all the possible overloaded methods to account for all the types that could be used.</span></span> <span data-ttu-id="2087f-177">Las implementaciones de .NET proporcionan compatibilidad para dichos métodos a través de la característica de la matriz de parámetros.</span><span class="sxs-lookup"><span data-stu-id="2087f-177">The .NET implementations provide support for such methods through the parameter array feature.</span></span> <span data-ttu-id="2087f-178">Con un número arbitrario de parámetros se puede proporcionar un método que toma una matriz de parámetros en la firma.</span><span class="sxs-lookup"><span data-stu-id="2087f-178">A method that takes a parameter array in its signature can be provided with an arbitrary number of parameters.</span></span> <span data-ttu-id="2087f-179">Los parámetros se colocan en una matriz.</span><span class="sxs-lookup"><span data-stu-id="2087f-179">The parameters are put into an array.</span></span> <span data-ttu-id="2087f-180">El tipo de elementos de la matriz determina los tipos de parámetro que se pueden pasar a la función.</span><span class="sxs-lookup"><span data-stu-id="2087f-180">The type of the array elements determines the parameter types that can be passed to the function.</span></span> <span data-ttu-id="2087f-181">Si define la matriz de parámetros con `System.Object` como el tipo de elemento, a continuación, el código de cliente puede pasar valores de cualquier tipo.</span><span class="sxs-lookup"><span data-stu-id="2087f-181">If you define the parameter array with `System.Object` as the element type, then client code can pass values of any type.</span></span>

<span data-ttu-id="2087f-182">En F#, solo se pueden definir matrices de parámetros en métodos.</span><span class="sxs-lookup"><span data-stu-id="2087f-182">In F#, parameter arrays can only be defined in methods.</span></span> <span data-ttu-id="2087f-183">No se usaron en las funciones que se definen en módulos o funciones independientes.</span><span class="sxs-lookup"><span data-stu-id="2087f-183">They cannot be used in standalone functions or functions that are defined in modules.</span></span>

<span data-ttu-id="2087f-184">Definir una matriz de parámetros mediante el `ParamArray` atributo.</span><span class="sxs-lookup"><span data-stu-id="2087f-184">You define a parameter array by using the `ParamArray` attribute.</span></span> <span data-ttu-id="2087f-185">El `ParamArray` atributo solo se puede aplicar al último parámetro.</span><span class="sxs-lookup"><span data-stu-id="2087f-185">The `ParamArray` attribute can only be applied to the last parameter.</span></span>

<span data-ttu-id="2087f-186">El código siguiente ilustra la llamada a un método de .NET que toma una matriz de parámetros y la definición de un tipo en F# que tiene un método que toma una matriz de parámetros.</span><span class="sxs-lookup"><span data-stu-id="2087f-186">The following code illustrates both calling a .NET method that takes a parameter array and the definition of a type in F# that has a method that takes a parameter array.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-2/snippet3811.fs)]

<span data-ttu-id="2087f-187">Cuando se ejecuta en un proyecto, el resultado del código anterior es como sigue:</span><span class="sxs-lookup"><span data-stu-id="2087f-187">When run in a project, the output of the previous code is as follows:</span></span>

```console
a 1 10 Hello world 1 True
"a"
1
10.0
"Hello world"
1u
true
```

## <a name="see-also"></a><span data-ttu-id="2087f-188">Vea también</span><span class="sxs-lookup"><span data-stu-id="2087f-188">See also</span></span>

- [<span data-ttu-id="2087f-189">Miembros</span><span class="sxs-lookup"><span data-stu-id="2087f-189">Members</span></span>](members/index.md)