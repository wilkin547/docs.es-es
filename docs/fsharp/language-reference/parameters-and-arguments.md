---
title: Parámetros y argumentos
description: 'Obtenga información sobre la compatibilidad del lenguaje F # para definir parámetros y pasar argumentos a funciones, métodos y propiedades.'
ms.date: 08/15/2020
ms.openlocfilehash: 6564fd31105427683af8fc6280672e638737e9b5
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/25/2020
ms.locfileid: "88811527"
---
# <a name="parameters-and-arguments"></a><span data-ttu-id="59548-103">Parámetros y argumentos</span><span class="sxs-lookup"><span data-stu-id="59548-103">Parameters and Arguments</span></span>

<span data-ttu-id="59548-104">En este tema se describe la compatibilidad con lenguajes para definir parámetros y pasar argumentos a funciones, métodos y propiedades.</span><span class="sxs-lookup"><span data-stu-id="59548-104">This topic describes language support for defining parameters and passing arguments to functions, methods, and properties.</span></span> <span data-ttu-id="59548-105">Incluye información sobre cómo pasar por referencia y cómo definir y usar métodos que pueden tomar un número variable de argumentos.</span><span class="sxs-lookup"><span data-stu-id="59548-105">It includes information about how to pass by reference, and how to define and use methods that can take a variable number of arguments.</span></span>

## <a name="parameters-and-arguments"></a><span data-ttu-id="59548-106">Parámetros y argumentos</span><span class="sxs-lookup"><span data-stu-id="59548-106">Parameters and Arguments</span></span>

<span data-ttu-id="59548-107">El término *parámetro* se usa para describir los nombres de los valores que se espera que se proporcionen.</span><span class="sxs-lookup"><span data-stu-id="59548-107">The term *parameter* is used to describe the names for values that are expected to be supplied.</span></span> <span data-ttu-id="59548-108">El término *argumento* se utiliza para los valores proporcionados para cada parámetro.</span><span class="sxs-lookup"><span data-stu-id="59548-108">The term *argument* is used for the values provided for each parameter.</span></span>

<span data-ttu-id="59548-109">Los parámetros se pueden especificar en forma de tupla o en formato currificados, o en una combinación de ambos.</span><span class="sxs-lookup"><span data-stu-id="59548-109">Parameters can be specified in tuple or curried form, or in some combination of the two.</span></span> <span data-ttu-id="59548-110">Puede pasar argumentos mediante el uso de un nombre de parámetro explícito.</span><span class="sxs-lookup"><span data-stu-id="59548-110">You can pass arguments by using an explicit parameter name.</span></span> <span data-ttu-id="59548-111">Los parámetros de los métodos se pueden especificar como opcionales y se les asigna un valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="59548-111">Parameters of methods can be specified as optional and given a default value.</span></span>

## <a name="parameter-patterns"></a><span data-ttu-id="59548-112">Patrones de parámetros</span><span class="sxs-lookup"><span data-stu-id="59548-112">Parameter Patterns</span></span>

<span data-ttu-id="59548-113">Los parámetros proporcionados a funciones y métodos son, en general, modelos separados por espacios.</span><span class="sxs-lookup"><span data-stu-id="59548-113">Parameters supplied to functions and methods are, in general, patterns separated by spaces.</span></span> <span data-ttu-id="59548-114">Esto significa que, en principio, cualquiera de los modelos descritos en [expresiones de coincidencia](match-expressions.md) se puede usar en una lista de parámetros para una función o un miembro.</span><span class="sxs-lookup"><span data-stu-id="59548-114">This means that, in principle, any of the patterns described in [Match Expressions](match-expressions.md) can be used in a parameter list for a function or member.</span></span>

<span data-ttu-id="59548-115">Los métodos suelen usar la forma de tupla de pasar argumentos.</span><span class="sxs-lookup"><span data-stu-id="59548-115">Methods usually use the tuple form of passing arguments.</span></span> <span data-ttu-id="59548-116">Esto consigue un resultado más claro desde la perspectiva de otros lenguajes .NET, ya que el formato de tupla coincide con la forma en que se pasan los argumentos en los métodos de .NET.</span><span class="sxs-lookup"><span data-stu-id="59548-116">This achieves a clearer result from the perspective of other .NET languages because the tuple form matches the way arguments are passed in .NET methods.</span></span>

<span data-ttu-id="59548-117">La forma currificada se usa con más frecuencia con funciones creadas mediante `let` enlaces.</span><span class="sxs-lookup"><span data-stu-id="59548-117">The curried form is most often used with functions created by using `let` bindings.</span></span>

<span data-ttu-id="59548-118">En el siguiente pseudocódigo se muestran ejemplos de argumentos de tupla y currificados.</span><span class="sxs-lookup"><span data-stu-id="59548-118">The following pseudocode shows examples of tuple and curried arguments.</span></span>

```fsharp
// Tuple form.
member this.SomeMethod(param1, param2) = ...
// Curried form.
let function1 param1 param2 = ...
```

<span data-ttu-id="59548-119">Los formularios combinados son posibles cuando algunos argumentos están en tuplas y otros no.</span><span class="sxs-lookup"><span data-stu-id="59548-119">Combined forms are possible when some arguments are in tuples and some are not.</span></span>

```fsharp
let function2 param1 (param2a, param2b) param3 = ...
```

<span data-ttu-id="59548-120">También se pueden usar otros patrones en las listas de parámetros, pero si el patrón de parámetros no coincide con todas las entradas posibles, puede haber una coincidencia incompleta en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="59548-120">Other patterns can also be used in parameter lists, but if the parameter pattern does not match all possible inputs, there might be an incomplete match at run time.</span></span> <span data-ttu-id="59548-121">La excepción `MatchFailureException` se genera cuando el valor de un argumento no coincide con los patrones especificados en la lista de parámetros.</span><span class="sxs-lookup"><span data-stu-id="59548-121">The exception `MatchFailureException` is generated when the value of an argument does not match the patterns specified in the parameter list.</span></span> <span data-ttu-id="59548-122">El compilador emite una advertencia cuando un patrón de parámetro permite coincidencias incompletas.</span><span class="sxs-lookup"><span data-stu-id="59548-122">The compiler issues a warning when a parameter pattern allows for incomplete matches.</span></span> <span data-ttu-id="59548-123">Al menos un patrón es normalmente útil para las listas de parámetros, y es el patrón de carácter comodín.</span><span class="sxs-lookup"><span data-stu-id="59548-123">At least one other pattern is commonly useful for parameter lists, and that is the wildcard pattern.</span></span> <span data-ttu-id="59548-124">El patrón de caracteres comodín se usa en una lista de parámetros cuando simplemente se desea omitir los argumentos que se proporcionan.</span><span class="sxs-lookup"><span data-stu-id="59548-124">You use the wildcard pattern in a parameter list when you simply want to ignore any arguments that are supplied.</span></span> <span data-ttu-id="59548-125">En el código siguiente se muestra el uso del patrón de carácter comodín en una lista de argumentos.</span><span class="sxs-lookup"><span data-stu-id="59548-125">The following code illustrates the use of the wildcard pattern in an argument list.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3801.fs)]

<span data-ttu-id="59548-126">El patrón de carácter comodín puede ser útil cuando no se necesitan los argumentos pasados, como en el punto de entrada principal a un programa, cuando no está interesado en los argumentos de la línea de comandos que se proporcionan normalmente como una matriz de cadenas, como en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="59548-126">The wildcard pattern can be useful whenever you do not need the arguments passed in, such as in the main entry point to a program, when you are not interested in the command-line arguments that are normally supplied as a string array, as in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3802.fs)]

<span data-ttu-id="59548-127">Otros patrones que a veces se usan en argumentos son el `as` patrón y los patrones de identificador asociados a las uniones discriminadas y los patrones activos.</span><span class="sxs-lookup"><span data-stu-id="59548-127">Other patterns that are sometimes used in arguments are the `as` pattern, and identifier patterns associated with discriminated unions and active patterns.</span></span> <span data-ttu-id="59548-128">Puede usar el modelo de Unión discriminada de un solo caso como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="59548-128">You can use the single-case discriminated union pattern as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3803.fs)]

<span data-ttu-id="59548-129">La salida es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="59548-129">The output is as follows.</span></span>

```console
Data begins at 0 and ends at 4 in string Et tu, Brute?
Et tu
```

<span data-ttu-id="59548-130">Los modelos activos pueden ser útiles como parámetros, por ejemplo, al transformar un argumento en un formato deseado, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="59548-130">Active patterns can be useful as parameters, for example, when transforming an argument into a desired format, as in the following example:</span></span>

```fsharp
type Point = { x : float; y : float }

let (| Polar |) { x = x; y = y} =
    ( sqrt (x*x + y*y), System.Math.Atan (y/ x) )

let radius (Polar(r, _)) = r
let angle (Polar(_, theta)) = theta
```

<span data-ttu-id="59548-131">Puede usar el `as` patrón para almacenar un valor coincidente como un valor local, como se muestra en la siguiente línea de código.</span><span class="sxs-lookup"><span data-stu-id="59548-131">You can use the `as` pattern to store a matched value as a local value, as is shown in the following line of code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3805.fs)]

<span data-ttu-id="59548-132">Otro patrón que se usa ocasionalmente es una función que deja el último argumento sin nombre proporcionando, como el cuerpo de la función, una expresión lambda que realiza inmediatamente una coincidencia de patrón en el argumento implícito.</span><span class="sxs-lookup"><span data-stu-id="59548-132">Another pattern that is used occasionally is a function that leaves the last argument unnamed by providing, as the body of the function, a lambda expression that immediately performs a pattern match on the implicit argument.</span></span> <span data-ttu-id="59548-133">Un ejemplo de esto es la siguiente línea de código.</span><span class="sxs-lookup"><span data-stu-id="59548-133">An example of this is the following line of code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3804.fs)]

<span data-ttu-id="59548-134">Este código define una función que toma una lista genérica y devuelve `true` si la lista está vacía, y `false` en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="59548-134">This code defines a function that takes a generic list and returns `true` if the list is empty, and `false` otherwise.</span></span> <span data-ttu-id="59548-135">El uso de estas técnicas puede dificultar la lectura del código.</span><span class="sxs-lookup"><span data-stu-id="59548-135">The use of such techniques can make code more difficult to read.</span></span>

<span data-ttu-id="59548-136">En ocasiones, los patrones que implican coincidencias incompletas son útiles, por ejemplo, si sabe que las listas del programa tienen solo tres elementos, podría usar un patrón similar al siguiente en una lista de parámetros.</span><span class="sxs-lookup"><span data-stu-id="59548-136">Occasionally, patterns that involve incomplete matches are useful, for example, if you know that the lists in your program have only three elements, you might use a pattern like the following in a parameter list.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3806.fs)]

<span data-ttu-id="59548-137">El uso de patrones con coincidencias incompletas se reserva mejor para el prototipo rápido y otros usos temporales.</span><span class="sxs-lookup"><span data-stu-id="59548-137">The use of patterns that have incomplete matches is best reserved for quick prototyping and other temporary uses.</span></span> <span data-ttu-id="59548-138">El compilador emitirá una advertencia para este tipo de código.</span><span class="sxs-lookup"><span data-stu-id="59548-138">The compiler will issue a warning for such code.</span></span> <span data-ttu-id="59548-139">Estos patrones no pueden cubrir el caso general de todas las entradas posibles y, por lo tanto, no son adecuadas para las API de componentes.</span><span class="sxs-lookup"><span data-stu-id="59548-139">Such patterns cannot cover the general case of all possible inputs and therefore are not suitable for component APIs.</span></span>

## <a name="named-arguments"></a><span data-ttu-id="59548-140">Argumentos con nombre</span><span class="sxs-lookup"><span data-stu-id="59548-140">Named Arguments</span></span>

<span data-ttu-id="59548-141">Los argumentos para los métodos se pueden especificar por posición en una lista de argumentos separados por comas, o bien se pueden pasar explícitamente a un método proporcionando el nombre, seguido de un signo igual y del valor que se va a pasar.</span><span class="sxs-lookup"><span data-stu-id="59548-141">Arguments for methods can be specified by position in a comma-separated argument list, or they can be passed to a method explicitly by providing the name, followed by an equal sign and the value to be passed in.</span></span> <span data-ttu-id="59548-142">Si se especifica proporcionando el nombre, pueden aparecer en un orden diferente al utilizado en la declaración.</span><span class="sxs-lookup"><span data-stu-id="59548-142">If specified by providing the name, they can appear in a different order from that used in the declaration.</span></span>

<span data-ttu-id="59548-143">Los argumentos con nombre pueden hacer que el código sea más legible y más adaptable a determinados tipos de cambios en la API, como una reordenación de los parámetros de método.</span><span class="sxs-lookup"><span data-stu-id="59548-143">Named arguments can make code more readable and more adaptable to certain types of changes in the API, such as a reordering of method parameters.</span></span>

<span data-ttu-id="59548-144">Los argumentos con nombre solo se permiten para métodos, no para `let` funciones enlazadas, valores de función o expresiones lambda.</span><span class="sxs-lookup"><span data-stu-id="59548-144">Named arguments are allowed only for methods, not for `let`-bound functions, function values, or lambda expressions.</span></span>

<span data-ttu-id="59548-145">En el ejemplo de código siguiente se muestra el uso de argumentos con nombre.</span><span class="sxs-lookup"><span data-stu-id="59548-145">The following code example demonstrates the use of named arguments.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3807.fs)]

<span data-ttu-id="59548-146">En una llamada a un constructor de clase, puede establecer los valores de las propiedades de la clase mediante una sintaxis similar a la de los argumentos con nombre.</span><span class="sxs-lookup"><span data-stu-id="59548-146">In a call to a class constructor, you can set the values of properties of the class by using a syntax similar to that of named arguments.</span></span> <span data-ttu-id="59548-147">En el ejemplo siguiente se muestra esta sintaxis.</span><span class="sxs-lookup"><span data-stu-id="59548-147">The following example shows this syntax.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

<span data-ttu-id="59548-148">Para obtener más información, vea [constructores (F #)](members/constructors.md).</span><span class="sxs-lookup"><span data-stu-id="59548-148">For more information, see [Constructors (F#)](members/constructors.md).</span></span>

## <a name="optional-parameters"></a><span data-ttu-id="59548-149">Parámetros opcionales</span><span class="sxs-lookup"><span data-stu-id="59548-149">Optional Parameters</span></span>

<span data-ttu-id="59548-150">Puede especificar un parámetro opcional para un método mediante un signo de interrogación delante del nombre del parámetro.</span><span class="sxs-lookup"><span data-stu-id="59548-150">You can specify an optional parameter for a method by using a question mark in front of the parameter name.</span></span> <span data-ttu-id="59548-151">Los parámetros opcionales se interpretan como el tipo de opción de F #, por lo que puede consultarlos de la manera habitual en que se consultan los tipos de opciones, mediante el uso de una `match` expresión con `Some` y `None` .</span><span class="sxs-lookup"><span data-stu-id="59548-151">Optional parameters are interpreted as the F# option type, so you can query them in the regular way that option types are queried, by using a `match` expression with `Some` and `None`.</span></span> <span data-ttu-id="59548-152">Los parámetros opcionales solo se permiten en los miembros, no en las funciones creadas mediante `let` enlaces.</span><span class="sxs-lookup"><span data-stu-id="59548-152">Optional parameters are permitted only on members, not on functions created by using `let` bindings.</span></span>

<span data-ttu-id="59548-153">Puede pasar valores opcionales existentes al método por nombre de parámetro, como `?arg=None` o `?arg=Some(3)` `?arg=arg` .</span><span class="sxs-lookup"><span data-stu-id="59548-153">You can pass existing optional values to method by parameter name, such as `?arg=None` or `?arg=Some(3)` or `?arg=arg`.</span></span> <span data-ttu-id="59548-154">Esto puede ser útil al compilar un método que pasa argumentos opcionales a otro método.</span><span class="sxs-lookup"><span data-stu-id="59548-154">This can be useful when building a method that passes optional arguments to another method.</span></span>

<span data-ttu-id="59548-155">También puede utilizar una función `defaultArg` , que establece un valor predeterminado de un argumento opcional.</span><span class="sxs-lookup"><span data-stu-id="59548-155">You can also use a function `defaultArg`, which sets a default value of an optional argument.</span></span> <span data-ttu-id="59548-156">La `defaultArg` función toma el parámetro opcional como primer argumento y el valor predeterminado como segundo.</span><span class="sxs-lookup"><span data-stu-id="59548-156">The `defaultArg` function takes the optional parameter as the first argument and the default value as the second.</span></span>

<span data-ttu-id="59548-157">En el ejemplo siguiente se muestra el uso de parámetros opcionales.</span><span class="sxs-lookup"><span data-stu-id="59548-157">The following example illustrates the use of optional parameters.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3808.fs)]

<span data-ttu-id="59548-158">La salida es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="59548-158">The output is as follows.</span></span>

```console
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 4800 Duplex: Half Parity: false
Baud Rate: 300 Duplex: Half Parity: true
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 4800 Duplex: Half Parity: false
```

<span data-ttu-id="59548-159">Para los fines de la interoperabilidad de C# y Visual Basic, puede usar los atributos `[<Optional; DefaultParameterValue<(...)>]` de F #, de modo que los llamadores verán un argumento como opcional.</span><span class="sxs-lookup"><span data-stu-id="59548-159">For the purposes of C# and Visual Basic interop you can use the attributes `[<Optional; DefaultParameterValue<(...)>]` in F#, so that callers will see an argument as optional.</span></span> <span data-ttu-id="59548-160">Esto es equivalente a definir el argumento como opcional en C# como en `MyMethod(int i = 3)` .</span><span class="sxs-lookup"><span data-stu-id="59548-160">This is equivalent to defining the argument as optional in C# as in `MyMethod(int i = 3)`.</span></span>

```fsharp
open System
open System.Runtime.InteropServices
type C =
    static member Foo([<Optional; DefaultParameterValue("Hello world")>] message) =
        printfn "%s" message
```

<span data-ttu-id="59548-161">También puede especificar un nuevo objeto como valor de parámetro predeterminado.</span><span class="sxs-lookup"><span data-stu-id="59548-161">You can also specify a new object as a default parameter value.</span></span> <span data-ttu-id="59548-162">Por ejemplo, en `Foo` su lugar, el miembro podría tener una `CancellationToken` entrada opcional como:</span><span class="sxs-lookup"><span data-stu-id="59548-162">For example, the `Foo` member could have an optional `CancellationToken` as input instead:</span></span>

```fsharp
open System.Threading
open System.Runtime.InteropServices
type C =
    static member Foo([<Optional; DefaultParameterValue(CancellationToken())>] ct: CancellationToken) =
        printfn "%A" ct
```

<span data-ttu-id="59548-163">El valor dado como argumento para `DefaultParameterValue` debe coincidir con el tipo del parámetro.</span><span class="sxs-lookup"><span data-stu-id="59548-163">The value given as argument to `DefaultParameterValue` must match the type of the parameter.</span></span> <span data-ttu-id="59548-164">Por ejemplo, no se permite lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="59548-164">For example, the following is not allowed:</span></span>

```fsharp
type C =
    static member Wrong([<Optional; DefaultParameterValue("string")>] i:int) = ()
```

<span data-ttu-id="59548-165">En este caso, el compilador genera una advertencia y omitirá ambos atributos por completo.</span><span class="sxs-lookup"><span data-stu-id="59548-165">In this case, the compiler generates a warning and will ignore both attributes altogether.</span></span> <span data-ttu-id="59548-166">Tenga en cuenta que el valor predeterminado `null` debe anotarse de tipo, ya que, de lo contrario, el compilador deduce el tipo equivocado, es decir, `[<Optional; DefaultParameterValue(null:obj)>] o:obj` .</span><span class="sxs-lookup"><span data-stu-id="59548-166">Note that the default value `null` needs to be type-annotated, as otherwise the compiler infers the wrong type, i.e. `[<Optional; DefaultParameterValue(null:obj)>] o:obj`.</span></span>

## <a name="passing-by-reference"></a><span data-ttu-id="59548-167">Pasar por referencia</span><span class="sxs-lookup"><span data-stu-id="59548-167">Passing by Reference</span></span>

<span data-ttu-id="59548-168">Pasar un valor F # por referencia implica [byrefs](byrefs.md), que son tipos de puntero administrados.</span><span class="sxs-lookup"><span data-stu-id="59548-168">Passing an F# value by reference involves [byrefs](byrefs.md), which are managed pointer types.</span></span> <span data-ttu-id="59548-169">Instrucciones para el tipo que se va a usar es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="59548-169">Guidance for which type to use is as follows:</span></span>

- <span data-ttu-id="59548-170">Use `inref<'T>` si solo necesita leer el puntero.</span><span class="sxs-lookup"><span data-stu-id="59548-170">Use `inref<'T>` if you only need to read the pointer.</span></span>
- <span data-ttu-id="59548-171">Use `outref<'T>` si solo necesita escribir en el puntero.</span><span class="sxs-lookup"><span data-stu-id="59548-171">Use `outref<'T>` if you only need to write to the pointer.</span></span>
- <span data-ttu-id="59548-172">Use `byref<'T>` si necesita leer y escribir en el puntero.</span><span class="sxs-lookup"><span data-stu-id="59548-172">Use `byref<'T>` if you need to both read from and write to the pointer.</span></span>

```fsharp
let example1 (x: inref<int>) = printfn "It's %d" x

let example2 (x: outref<int>) = x <- x + 1

let example3 (x: byref<int>) =
    printfn "It'd %d" x
    x <- x + 1

let test () =
    // No need to make it mutable, since it's read-only
    let x = 1
    example1 &x

    // Needs to be mutable, since we write to it
    let mutable y = 2
    example2 &y
    example3 &y // Now 'y' is 3
```

<span data-ttu-id="59548-173">Dado que el parámetro es un puntero y el valor es mutable, cualquier cambio en el valor se conserva después de la ejecución de la función.</span><span class="sxs-lookup"><span data-stu-id="59548-173">Because the parameter is a pointer and the value is mutable, any changes to the value are retained after the execution of the function.</span></span>

<span data-ttu-id="59548-174">Puede usar una tupla como valor devuelto para almacenar los `out` parámetros en los métodos de la biblioteca de .net.</span><span class="sxs-lookup"><span data-stu-id="59548-174">You can use a tuple as a return value to store any `out` parameters in .NET library methods.</span></span> <span data-ttu-id="59548-175">Como alternativa, puede tratar el `out` parámetro como un `byref` parámetro.</span><span class="sxs-lookup"><span data-stu-id="59548-175">Alternatively, you can treat the `out` parameter as a `byref` parameter.</span></span> <span data-ttu-id="59548-176">En el ejemplo de código siguiente se muestran ambas maneras.</span><span class="sxs-lookup"><span data-stu-id="59548-176">The following code example illustrates both ways.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3810.fs)]

## <a name="parameter-arrays"></a><span data-ttu-id="59548-177">Matrices de parámetros</span><span class="sxs-lookup"><span data-stu-id="59548-177">Parameter Arrays</span></span>

<span data-ttu-id="59548-178">En ocasiones, es necesario definir una función que tome un número arbitrario de parámetros de tipo heterogéneo.</span><span class="sxs-lookup"><span data-stu-id="59548-178">Occasionally it is necessary to define a function that takes an arbitrary number of parameters of heterogeneous type.</span></span> <span data-ttu-id="59548-179">No sería práctico crear todos los métodos sobrecargados posibles para tener en cuenta todos los tipos que se podrían usar.</span><span class="sxs-lookup"><span data-stu-id="59548-179">It would not be practical to create all the possible overloaded methods to account for all the types that could be used.</span></span> <span data-ttu-id="59548-180">Las implementaciones de .NET proporcionan compatibilidad con estos métodos a través de la característica de matriz de parámetros.</span><span class="sxs-lookup"><span data-stu-id="59548-180">The .NET implementations provide support for such methods through the parameter array feature.</span></span> <span data-ttu-id="59548-181">Se puede proporcionar un método que toma una matriz de parámetros en su signatura con un número arbitrario de parámetros.</span><span class="sxs-lookup"><span data-stu-id="59548-181">A method that takes a parameter array in its signature can be provided with an arbitrary number of parameters.</span></span> <span data-ttu-id="59548-182">Los parámetros se colocan en una matriz.</span><span class="sxs-lookup"><span data-stu-id="59548-182">The parameters are put into an array.</span></span> <span data-ttu-id="59548-183">El tipo de los elementos de la matriz determina los tipos de parámetros que se pueden pasar a la función.</span><span class="sxs-lookup"><span data-stu-id="59548-183">The type of the array elements determines the parameter types that can be passed to the function.</span></span> <span data-ttu-id="59548-184">Si define la matriz de parámetros con `System.Object` como tipo de elemento, el código de cliente puede pasar valores de cualquier tipo.</span><span class="sxs-lookup"><span data-stu-id="59548-184">If you define the parameter array with `System.Object` as the element type, then client code can pass values of any type.</span></span>

<span data-ttu-id="59548-185">En F #, las matrices de parámetros solo se pueden definir en métodos.</span><span class="sxs-lookup"><span data-stu-id="59548-185">In F#, parameter arrays can only be defined in methods.</span></span> <span data-ttu-id="59548-186">No se pueden usar en funciones independientes o en funciones que se definen en módulos.</span><span class="sxs-lookup"><span data-stu-id="59548-186">They cannot be used in standalone functions or functions that are defined in modules.</span></span>

<span data-ttu-id="59548-187">Una matriz de parámetros se define mediante el `ParamArray` atributo.</span><span class="sxs-lookup"><span data-stu-id="59548-187">You define a parameter array by using the `ParamArray` attribute.</span></span> <span data-ttu-id="59548-188">El `ParamArray` atributo solo se puede aplicar al último parámetro.</span><span class="sxs-lookup"><span data-stu-id="59548-188">The `ParamArray` attribute can only be applied to the last parameter.</span></span>

<span data-ttu-id="59548-189">En el código siguiente se muestra cómo llamar a un método .NET que toma una matriz de parámetros y la definición de un tipo en F # que tiene un método que toma una matriz de parámetros.</span><span class="sxs-lookup"><span data-stu-id="59548-189">The following code illustrates both calling a .NET method that takes a parameter array and the definition of a type in F# that has a method that takes a parameter array.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-2/snippet3811.fs)]

<span data-ttu-id="59548-190">Cuando se ejecuta en un proyecto, la salida del código anterior es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="59548-190">When run in a project, the output of the previous code is as follows:</span></span>

```console
a 1 10 Hello world 1 True
"a"
1
10.0
"Hello world"
1u
true
```

## <a name="see-also"></a><span data-ttu-id="59548-191">Consulte también</span><span class="sxs-lookup"><span data-stu-id="59548-191">See also</span></span>

- [<span data-ttu-id="59548-192">Miembros</span><span class="sxs-lookup"><span data-stu-id="59548-192">Members</span></span>](./members/index.md)
