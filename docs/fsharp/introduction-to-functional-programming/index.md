---
title: Introducción a la programación funcional en F#
description: Conozca los aspectos básicos de la programación funcional F#en.
ms.date: 10/29/2018
ms.openlocfilehash: e1a0edc61dbe13012c48e166d490e22ebc70d6a0
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424711"
---
# <a name="introduction-to-functional-programming-in-f"></a><span data-ttu-id="442f5-103">Introducción a la programación funcional en F\#</span><span class="sxs-lookup"><span data-stu-id="442f5-103">Introduction to Functional Programming in F\#</span></span>

<span data-ttu-id="442f5-104">La programación funcional es un estilo de programación que enfatiza el uso de funciones y datos inmutables.</span><span class="sxs-lookup"><span data-stu-id="442f5-104">Functional programming is a style of programming that emphasizes the use of functions and immutable data.</span></span> <span data-ttu-id="442f5-105">La programación funcional con tipo es cuando la programación funcional se combina con tipos estáticos, F#como con.</span><span class="sxs-lookup"><span data-stu-id="442f5-105">Typed functional programming is when functional programming is combined with static types, such as with F#.</span></span> <span data-ttu-id="442f5-106">En general, los conceptos siguientes se destacan en la programación funcional:</span><span class="sxs-lookup"><span data-stu-id="442f5-106">In general, the following concepts are emphasized in functional programming:</span></span>

* <span data-ttu-id="442f5-107">Funciona como construcciones principales que se usan</span><span class="sxs-lookup"><span data-stu-id="442f5-107">Functions as the primary constructs you use</span></span>
* <span data-ttu-id="442f5-108">Expresiones en lugar de instrucciones</span><span class="sxs-lookup"><span data-stu-id="442f5-108">Expressions instead of statements</span></span>
* <span data-ttu-id="442f5-109">Valores inmutables en variables</span><span class="sxs-lookup"><span data-stu-id="442f5-109">Immutable values over variables</span></span>
* <span data-ttu-id="442f5-110">Programación declarativa a través de la programación imperativa</span><span class="sxs-lookup"><span data-stu-id="442f5-110">Declarative programming over imperative programming</span></span>

<span data-ttu-id="442f5-111">A lo largo de esta serie, explorará conceptos y patrones en la F#programación funcional con.</span><span class="sxs-lookup"><span data-stu-id="442f5-111">Throughout this series, you'll explore concepts and patterns in functional programming using F#.</span></span> <span data-ttu-id="442f5-112">A lo largo del proceso, también aprenderá algunas F# .</span><span class="sxs-lookup"><span data-stu-id="442f5-112">Along the way, you'll learn some F# too.</span></span>

## <a name="terminology"></a><span data-ttu-id="442f5-113">Terminología</span><span class="sxs-lookup"><span data-stu-id="442f5-113">Terminology</span></span>

<span data-ttu-id="442f5-114">La programación funcional, al igual que otros paradigmas de programación, incluye un vocabulario que finalmente tendrá que aprender.</span><span class="sxs-lookup"><span data-stu-id="442f5-114">Functional programming, like other programming paradigms, comes with a vocabulary that you will eventually need to learn.</span></span> <span data-ttu-id="442f5-115">Estos son algunos de los términos comunes que verá todo el tiempo:</span><span class="sxs-lookup"><span data-stu-id="442f5-115">Here are some common terms you'll see all of the time:</span></span>

* <span data-ttu-id="442f5-116">**Función** : una función es una construcción que generará una salida cuando se proporcione una entrada.</span><span class="sxs-lookup"><span data-stu-id="442f5-116">**Function** - A function is a construct that will produce an output when given an input.</span></span> <span data-ttu-id="442f5-117">Más formalmente, _asigna_ un elemento de un conjunto a otro conjunto.</span><span class="sxs-lookup"><span data-stu-id="442f5-117">More formally, it _maps_ an item from one set to another set.</span></span> <span data-ttu-id="442f5-118">Este formalismo se eleva en concreto de muchas maneras, especialmente cuando se usan funciones que operan en colecciones de datos.</span><span class="sxs-lookup"><span data-stu-id="442f5-118">This formalism is lifted into the concrete in many ways, especially when using functions that operate on collections of data.</span></span> <span data-ttu-id="442f5-119">Es el concepto más básico (y importante) de la programación funcional.</span><span class="sxs-lookup"><span data-stu-id="442f5-119">It is the most basic (and important) concept in functional programming.</span></span>
* <span data-ttu-id="442f5-120">**Expresión** : una expresión es una construcción de código que genera un valor.</span><span class="sxs-lookup"><span data-stu-id="442f5-120">**Expression** - An expression is a construct in code that produces a value.</span></span> <span data-ttu-id="442f5-121">En F#, este valor debe estar enlazado o omitirse explícitamente.</span><span class="sxs-lookup"><span data-stu-id="442f5-121">In F#, this value must be bound or explicitly ignored.</span></span> <span data-ttu-id="442f5-122">Una expresión se puede reemplazar trivialmente por una llamada de función.</span><span class="sxs-lookup"><span data-stu-id="442f5-122">An expression can be trivially replaced by a function call.</span></span>
* <span data-ttu-id="442f5-123">**La pureza-pureza** es una propiedad de una función de modo que el valor devuelto sea siempre el mismo para los mismos argumentos, y que su evaluación no tenga efectos secundarios.</span><span class="sxs-lookup"><span data-stu-id="442f5-123">**Purity** - Purity is a property of a function such that its return value is always the same for the same arguments, and that its evaluation has no side effects.</span></span> <span data-ttu-id="442f5-124">Una función pura depende completamente de sus argumentos.</span><span class="sxs-lookup"><span data-stu-id="442f5-124">A pure function depends entirely on its arguments.</span></span>
* <span data-ttu-id="442f5-125">**Transparencia referencial** : la transparencia referencial es una propiedad de expresiones de modo que se pueden reemplazar por su salida sin afectar al comportamiento de un programa.</span><span class="sxs-lookup"><span data-stu-id="442f5-125">**Referential Transparency** - Referential Transparency is a property of expressions such that they can be replaced with their output without affecting a program's behavior.</span></span>
* <span data-ttu-id="442f5-126">**Inmutabilidad** : la inmutabilidad significa que un valor no se puede cambiar en contexto.</span><span class="sxs-lookup"><span data-stu-id="442f5-126">**Immutability** - Immutability means that a value cannot be changed in-place.</span></span> <span data-ttu-id="442f5-127">Esto contrasta con las variables, que pueden cambiar en su lugar.</span><span class="sxs-lookup"><span data-stu-id="442f5-127">This is in contrast with variables, which can change in place.</span></span>

## <a name="examples"></a><span data-ttu-id="442f5-128">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="442f5-128">Examples</span></span>

<span data-ttu-id="442f5-129">En los siguientes ejemplos se muestran estos conceptos básicos.</span><span class="sxs-lookup"><span data-stu-id="442f5-129">The following examples demonstrate these core concepts.</span></span>

### <a name="functions"></a><span data-ttu-id="442f5-130">Funciones</span><span class="sxs-lookup"><span data-stu-id="442f5-130">Functions</span></span>

<span data-ttu-id="442f5-131">La construcción más común y fundamental en la programación funcional es la función.</span><span class="sxs-lookup"><span data-stu-id="442f5-131">The most common and fundamental construct in functional programming is the function.</span></span> <span data-ttu-id="442f5-132">Esta es una función simple que suma 1 a un entero:</span><span class="sxs-lookup"><span data-stu-id="442f5-132">Here's a simple function that adds 1 to an integer:</span></span>

```fsharp
let addOne x = x + 1
```

<span data-ttu-id="442f5-133">Su signatura de tipo es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="442f5-133">Its type signature is as follows:</span></span>

```fsharp
val addOne: x:int -> int
```

<span data-ttu-id="442f5-134">La firma se puede leer como "`addOne` acepta un `int` denominado `x` y generará una `int`".</span><span class="sxs-lookup"><span data-stu-id="442f5-134">The signature can be read as, "`addOne` accepts an `int` named `x` and will produce an `int`".</span></span> <span data-ttu-id="442f5-135">Más formalmente, `addOne` está _asignando_ un valor del conjunto de enteros al conjunto de enteros.</span><span class="sxs-lookup"><span data-stu-id="442f5-135">More formally, `addOne` is _mapping_ a value from the set of integers to the set of integers.</span></span> <span data-ttu-id="442f5-136">El token `->` significa esta asignación.</span><span class="sxs-lookup"><span data-stu-id="442f5-136">The `->` token signifies this mapping.</span></span> <span data-ttu-id="442f5-137">En F#, normalmente puede ver la firma de la función para obtener una idea de lo que hace.</span><span class="sxs-lookup"><span data-stu-id="442f5-137">In F#, you can usually look at the function signature to get a sense for what it does.</span></span>

<span data-ttu-id="442f5-138">Por lo tanto, ¿por qué es importante la firma?</span><span class="sxs-lookup"><span data-stu-id="442f5-138">So, why is the signature important?</span></span> <span data-ttu-id="442f5-139">En la programación funcional con tipo, la implementación de una función suele ser menos importante que la firma de tipo real.</span><span class="sxs-lookup"><span data-stu-id="442f5-139">In typed functional programming, the implementation of a function is often less important than the actual type signature!</span></span> <span data-ttu-id="442f5-140">El hecho de que `addOne` agregue el valor 1 a un entero es interesante en tiempo de ejecución, pero cuando se crea un programa, el hecho de que acepte y devuelva un `int` es lo que informa de cómo se utilizará realmente esta función.</span><span class="sxs-lookup"><span data-stu-id="442f5-140">The fact that `addOne` adds the value 1 to an integer is interesting at runtime, but when you are constructing a program, the fact that it accepts and returns an `int` is what informs how you will actually use this function.</span></span> <span data-ttu-id="442f5-141">Además, una vez que use esta función correctamente (con respecto a su firma de tipo), el diagnóstico de cualquier problema solo puede realizarse dentro del cuerpo de la función `addOne`.</span><span class="sxs-lookup"><span data-stu-id="442f5-141">Furthermore, once you use this function correctly (with respect to its type signature), diagnosing any problems can be done only within the body of the `addOne` function.</span></span> <span data-ttu-id="442f5-142">Este es el estímulo detrás de la programación funcional con tipo.</span><span class="sxs-lookup"><span data-stu-id="442f5-142">This is the impetus behind typed functional programming.</span></span>

### <a name="expressions"></a><span data-ttu-id="442f5-143">Expresiones</span><span class="sxs-lookup"><span data-stu-id="442f5-143">Expressions</span></span>

<span data-ttu-id="442f5-144">Las expresiones son construcciones que se evalúan como un valor.</span><span class="sxs-lookup"><span data-stu-id="442f5-144">Expressions are constructs that evaluate to a value.</span></span> <span data-ttu-id="442f5-145">A diferencia de las instrucciones, que realizan una acción, se pueden considerar expresiones al realizar una acción que devuelve un valor.</span><span class="sxs-lookup"><span data-stu-id="442f5-145">In contrast to statements, which perform an action, expressions can be thought of performing an action that gives back a value.</span></span> <span data-ttu-id="442f5-146">Las expresiones casi siempre se usan en favor de instrucciones en la programación funcional.</span><span class="sxs-lookup"><span data-stu-id="442f5-146">Expressions are almost always used in favor of statements in functional programming.</span></span>

<span data-ttu-id="442f5-147">Considere la función anterior, `addOne`.</span><span class="sxs-lookup"><span data-stu-id="442f5-147">Consider the previous function, `addOne`.</span></span> <span data-ttu-id="442f5-148">El cuerpo de `addOne` es una expresión:</span><span class="sxs-lookup"><span data-stu-id="442f5-148">The body of `addOne` is an expression:</span></span>

```fsharp
// 'x + 1' is an expression!
let addOne x = x + 1
```

<span data-ttu-id="442f5-149">Es el resultado de esta expresión que define el tipo de resultado de la función `addOne`.</span><span class="sxs-lookup"><span data-stu-id="442f5-149">It is the result of this expression that defines the result type of the `addOne` function.</span></span> <span data-ttu-id="442f5-150">Por ejemplo, la expresión que constituye esta función podría cambiarse para ser un tipo diferente, como una `string`:</span><span class="sxs-lookup"><span data-stu-id="442f5-150">For example, the expression that makes up this function could be changed to be a different type, such as a `string`:</span></span>

```fsharp
let addOne x = x.ToString() + "1"
```

<span data-ttu-id="442f5-151">La firma de la función es ahora:</span><span class="sxs-lookup"><span data-stu-id="442f5-151">The signature of the function is now:</span></span>

```fsharp
val addOne: x:'a -> string
```

<span data-ttu-id="442f5-152">Dado que cualquier tipo F# de puede tener `ToString()` llama a en él, el tipo de `x` se ha convertido en genérico (denominado [generalización automática](../language-reference/generics/automatic-generalization.md)) y el tipo resultante es una `string`.</span><span class="sxs-lookup"><span data-stu-id="442f5-152">Since any type in F# can have `ToString()` called on it, the type of `x` has been made generic (called [Automatic Generalization](../language-reference/generics/automatic-generalization.md)), and the resultant type is a `string`.</span></span>

<span data-ttu-id="442f5-153">Las expresiones no son solo los cuerpos de las funciones.</span><span class="sxs-lookup"><span data-stu-id="442f5-153">Expressions are not just the bodies of functions.</span></span> <span data-ttu-id="442f5-154">Puede tener expresiones que generen un valor que se utilice en otro lugar.</span><span class="sxs-lookup"><span data-stu-id="442f5-154">You can have expressions that produce a value you use elsewhere.</span></span> <span data-ttu-id="442f5-155">Una común es `if`:</span><span class="sxs-lookup"><span data-stu-id="442f5-155">A common one is `if`:</span></span>

```fsharp
// Checks if 'x' is odd by using the mod operator
let isOdd x = x % 2 <> 0

let addOneIfOdd input =
    let result =
        if isOdd input then
            input + 1
        else
            input

    result
```

<span data-ttu-id="442f5-156">La expresión `if` produce un valor denominado `result`.</span><span class="sxs-lookup"><span data-stu-id="442f5-156">The `if` expression produces a value called `result`.</span></span> <span data-ttu-id="442f5-157">Tenga en cuenta que puede omitir `result` por completo, lo que hace que la expresión de `if` sea el cuerpo de la función `addOneIfOdd`.</span><span class="sxs-lookup"><span data-stu-id="442f5-157">Note that you could omit `result` entirely, making the `if` expression the body of the `addOneIfOdd` function.</span></span> <span data-ttu-id="442f5-158">Lo más importante que debe recordar sobre las expresiones es que generan un valor.</span><span class="sxs-lookup"><span data-stu-id="442f5-158">The key thing to remember about expressions is that they produce a value.</span></span>

<span data-ttu-id="442f5-159">Hay un tipo especial, `unit`, que se usa cuando no hay nada que devolver.</span><span class="sxs-lookup"><span data-stu-id="442f5-159">There is a special type, `unit`, that is used when there is nothing to return.</span></span> <span data-ttu-id="442f5-160">Por ejemplo, considere esta función simple:</span><span class="sxs-lookup"><span data-stu-id="442f5-160">For example, consider this simple function:</span></span>

```fsharp
let printString (str: string) =
    printfn "String is: %s" str
```

<span data-ttu-id="442f5-161">La firma tiene el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="442f5-161">The signature looks like this:</span></span>

```fsharp
val printString: str:string -> unit
```

<span data-ttu-id="442f5-162">El tipo de `unit` indica que no se devuelve ningún valor real.</span><span class="sxs-lookup"><span data-stu-id="442f5-162">The `unit` type indicates that there is no actual value being returned.</span></span> <span data-ttu-id="442f5-163">Esto resulta útil cuando se tiene una rutina que debe "trabajar" a pesar de no tener ningún valor para devolver como resultado de ese trabajo.</span><span class="sxs-lookup"><span data-stu-id="442f5-163">This is useful when you have a routine that must "do work" despite having no value to return as a result of that work.</span></span>

<span data-ttu-id="442f5-164">Esto está en contraste con la programación imperativa, donde la construcción de `if` equivalente es una instrucción, y la generación de valores se suele realizar con variables mutantes.</span><span class="sxs-lookup"><span data-stu-id="442f5-164">This is in sharp contrast to imperative programming, where the equivalent `if` construct is a statement, and producing values is often done with mutating variables.</span></span> <span data-ttu-id="442f5-165">Por ejemplo, en C#, el código podría escribirse de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="442f5-165">For example, in C#, the code might be written like this:</span></span>

```csharp
bool IsOdd(int x) => x % 2 != 0;

int AddOneIfOdd(int input)
{
    var result = input;

    if (IsOdd(input))
    {
        result = input + 1;
    }

    return result;
}
```

<span data-ttu-id="442f5-166">Merece la pena mencionar que C# y otros lenguajes de estilo C admiten la [expresión ternaria](../../csharp/language-reference/operators/conditional-operator.md), que permite la programación condicional basada en expresiones.</span><span class="sxs-lookup"><span data-stu-id="442f5-166">It's worth noting that C# and other C-style languages do support the [ternary expression](../../csharp/language-reference/operators/conditional-operator.md), which allows for expression-based conditional programming.</span></span>

<span data-ttu-id="442f5-167">En la programación funcional, es poco habitual mutar los valores con las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="442f5-167">In functional programming, it is rare to mutate values with statements.</span></span> <span data-ttu-id="442f5-168">Aunque algunos lenguajes funcionales admiten instrucciones y mutación, no es habitual utilizar estos conceptos en la programación funcional.</span><span class="sxs-lookup"><span data-stu-id="442f5-168">Although some functional languages support statements and mutation, it is not common to use these concepts in functional programming.</span></span>

### <a name="pure-functions"></a><span data-ttu-id="442f5-169">Funciones puras</span><span class="sxs-lookup"><span data-stu-id="442f5-169">Pure functions</span></span>

<span data-ttu-id="442f5-170">Como se mencionó anteriormente, las funciones puras son funciones que:</span><span class="sxs-lookup"><span data-stu-id="442f5-170">As previously mentioned, pure functions are functions that:</span></span>

* <span data-ttu-id="442f5-171">Siempre se evalúan con el mismo valor para la misma entrada.</span><span class="sxs-lookup"><span data-stu-id="442f5-171">Always evaluate to the same value for the same input.</span></span>
* <span data-ttu-id="442f5-172">No tener efectos secundarios.</span><span class="sxs-lookup"><span data-stu-id="442f5-172">Have no side effects.</span></span>

<span data-ttu-id="442f5-173">Resulta útil pensar en las funciones matemáticas en este contexto.</span><span class="sxs-lookup"><span data-stu-id="442f5-173">It is helpful to think of mathematical functions in this context.</span></span> <span data-ttu-id="442f5-174">En las matemáticas, las funciones dependen solo de sus argumentos y no tienen efectos secundarios.</span><span class="sxs-lookup"><span data-stu-id="442f5-174">In mathematics, functions depend only on their arguments and do not have any side effects.</span></span> <span data-ttu-id="442f5-175">En la función matemática `f(x) = x + 1`, el valor de `f(x)` depende solo del valor de `x`.</span><span class="sxs-lookup"><span data-stu-id="442f5-175">In the mathematical function `f(x) = x + 1`, the value of `f(x)` depends only on the value of `x`.</span></span> <span data-ttu-id="442f5-176">Las funciones puras en la programación funcional son la misma manera.</span><span class="sxs-lookup"><span data-stu-id="442f5-176">Pure functions in functional programming are the same way.</span></span>

<span data-ttu-id="442f5-177">Al escribir una función pura, la función debe depender solo de sus argumentos y no realizar ninguna acción que tenga como resultado un efecto secundario.</span><span class="sxs-lookup"><span data-stu-id="442f5-177">When writing a pure function, the function must depend only on its arguments and not perform any action that results in a side effect.</span></span>

<span data-ttu-id="442f5-178">Este es un ejemplo de una función no pura porque depende del estado global y mutable:</span><span class="sxs-lookup"><span data-stu-id="442f5-178">Here is an example of a non-pure function because it depends on global, mutable state:</span></span>

```fsharp
let mutable value = 1

let addOneToValue x = x + value
```

<span data-ttu-id="442f5-179">La función `addOneToValue` es claramente inpura, porque `value` podría cambiarse en cualquier momento para tener un valor distinto de 1.</span><span class="sxs-lookup"><span data-stu-id="442f5-179">The `addOneToValue` function is clearly impure, because `value` could be changed at any time to have a different value than 1.</span></span> <span data-ttu-id="442f5-180">Este patrón de en función de un valor global se debe evitar en la programación funcional.</span><span class="sxs-lookup"><span data-stu-id="442f5-180">This pattern of depending on a global value is to be avoided in functional programming.</span></span>

<span data-ttu-id="442f5-181">Este es otro ejemplo de una función no pura, ya que realiza un efecto secundario:</span><span class="sxs-lookup"><span data-stu-id="442f5-181">Here is another example of a non-pure function, because it performs a side effect:</span></span>

```fsharp
let addOneToValue x =
    printfn "x is %d" x
    x + 1
```

<span data-ttu-id="442f5-182">Aunque esta función no depende de un valor global, escribe el valor de `x` en la salida del programa.</span><span class="sxs-lookup"><span data-stu-id="442f5-182">Although this function does not depend on a global value, it writes the value of `x` to the output of the program.</span></span> <span data-ttu-id="442f5-183">Aunque no hay nada inherentemente incorrecto, esto significa que la función no es pura.</span><span class="sxs-lookup"><span data-stu-id="442f5-183">Although there is nothing inherently wrong with doing this, it does mean that the function is not pure.</span></span> <span data-ttu-id="442f5-184">Si otra parte del programa depende de algo externo al programa, como el búfer de salida, llamar a esta función puede afectar a la otra parte del programa.</span><span class="sxs-lookup"><span data-stu-id="442f5-184">If another part of your program depends on something external to the program, such as the output buffer, then calling this function can affect that other part of your program.</span></span>

<span data-ttu-id="442f5-185">La eliminación de la instrucción `printfn` hace que la función sea pura:</span><span class="sxs-lookup"><span data-stu-id="442f5-185">Removing the `printfn` statement makes the function pure:</span></span>

```fsharp
let addOneToValue x = x + 1
```

<span data-ttu-id="442f5-186">Aunque esta función no es intrínsecamente _mejor_ que la versión anterior con la instrucción `printfn`, garantiza que toda esta función devuelve un valor.</span><span class="sxs-lookup"><span data-stu-id="442f5-186">Although this function is not inherently _better_ than the previous version with the `printfn` statement, it does guarantee that all this function does is return a value.</span></span> <span data-ttu-id="442f5-187">Llamar a esta función cualquier número de veces produce el mismo resultado: simplemente genera un valor.</span><span class="sxs-lookup"><span data-stu-id="442f5-187">Calling this function any number of times produces the same result: it just produces a value.</span></span> <span data-ttu-id="442f5-188">La capacidad de previsión proporcionada por la pureza es algo que los programadores funcionales están procurando.</span><span class="sxs-lookup"><span data-stu-id="442f5-188">The predictability given by purity is something many functional programmers strive for.</span></span>

### <a name="immutability"></a><span data-ttu-id="442f5-189">Inmutabilidad</span><span class="sxs-lookup"><span data-stu-id="442f5-189">Immutability</span></span>

<span data-ttu-id="442f5-190">Por último, uno de los conceptos fundamentales de la programación funcional con tipo es la inmutabilidad.</span><span class="sxs-lookup"><span data-stu-id="442f5-190">Finally, one of the most fundamental concepts of typed functional programming is immutability.</span></span> <span data-ttu-id="442f5-191">En F#, todos los valores son inmutables de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="442f5-191">In F#, all values are immutable by default.</span></span> <span data-ttu-id="442f5-192">Esto significa que no se pueden mutar en contexto a menos que los marque explícitamente como mutables.</span><span class="sxs-lookup"><span data-stu-id="442f5-192">That means they cannot be mutated in-place unless you explicitly mark them as mutable.</span></span>

<span data-ttu-id="442f5-193">En la práctica, el trabajo con valores inmutables significa que se cambia el enfoque a la programación de, "es necesario cambiar algo", a "es necesario generar un nuevo valor".</span><span class="sxs-lookup"><span data-stu-id="442f5-193">In practice, working with immutable values means that you change your approach to programming from, "I need to change something", to "I need to produce a new value".</span></span>

<span data-ttu-id="442f5-194">Por ejemplo, si se agrega 1 a un valor, se genera un nuevo valor, no se modifica el existente:</span><span class="sxs-lookup"><span data-stu-id="442f5-194">For example, adding 1 to a value means producing a new value, not mutating the existing one:</span></span>

```fsharp
let value = 1
let secondValue = value + 1
```

<span data-ttu-id="442f5-195">En F#, el código siguiente **no** muta la función `value`; en su lugar, realiza una comprobación de igualdad:</span><span class="sxs-lookup"><span data-stu-id="442f5-195">In F#, the following code does **not** mutate the `value` function; instead, it performs an equality check:</span></span>

```fsharp
let value = 1
value = value + 1 // Produces a 'bool' value!
```

<span data-ttu-id="442f5-196">Algunos lenguajes de programación funcionales no admiten la mutación.</span><span class="sxs-lookup"><span data-stu-id="442f5-196">Some functional programming languages do not support mutation at all.</span></span> <span data-ttu-id="442f5-197">En F#, es compatible, pero no es el comportamiento predeterminado de los valores de.</span><span class="sxs-lookup"><span data-stu-id="442f5-197">In F#, it is supported, but it is not the default behavior for values.</span></span>

<span data-ttu-id="442f5-198">Este concepto se extiende aún más a las estructuras de datos.</span><span class="sxs-lookup"><span data-stu-id="442f5-198">This concept extends even further to data structures.</span></span> <span data-ttu-id="442f5-199">En la programación funcional, las estructuras de datos inmutables como los conjuntos (y muchos más) tienen una implementación diferente de la que cabría esperar inicialmente.</span><span class="sxs-lookup"><span data-stu-id="442f5-199">In functional programming, immutable data structures such as sets (and many more) have a different implementation than you might initially expect.</span></span> <span data-ttu-id="442f5-200">Conceptualmente, algo como agregar un elemento a un conjunto no cambia el conjunto, genera un _nuevo_ conjunto con el valor agregado.</span><span class="sxs-lookup"><span data-stu-id="442f5-200">Conceptually, something like adding an item to a set does not change the set, it produces a _new_ set with the added value.</span></span> <span data-ttu-id="442f5-201">En segundo plano, esto se logra con una estructura de datos diferente que permite realizar un seguimiento eficaz de un valor para que se pueda proporcionar como resultado la representación adecuada de los datos.</span><span class="sxs-lookup"><span data-stu-id="442f5-201">Under the covers, this is often accomplished by a different data structure that allows for efficiently tracking a value so that the appropriate representation of the data can be given as a result.</span></span>

<span data-ttu-id="442f5-202">Este estilo de trabajo con valores y estructuras de datos es fundamental, ya que le obliga a tratar cualquier operación que modifique algo como si creara una nueva versión de ese elemento.</span><span class="sxs-lookup"><span data-stu-id="442f5-202">This style of working with values and data structures is critical, as it forces you to treat any operation that modifies something as if it creates a new version of that thing.</span></span> <span data-ttu-id="442f5-203">Esto permite que elementos como la igualdad y la comparación sean coherentes en los programas.</span><span class="sxs-lookup"><span data-stu-id="442f5-203">This allows for things like equality and comparability to be consistent in your programs.</span></span>

## <a name="next-steps"></a><span data-ttu-id="442f5-204">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="442f5-204">Next steps</span></span>

<span data-ttu-id="442f5-205">En la siguiente sección, se tratarán detalladamente las funciones y se explorarán las distintas formas en que se pueden usar en la programación funcional.</span><span class="sxs-lookup"><span data-stu-id="442f5-205">The next section will thoroughly cover functions, exploring different ways you can use them in functional programming.</span></span>

<span data-ttu-id="442f5-206">[Las funciones de primera clase](first-class-functions.md) exploran las funciones en profundidad, lo que muestra cómo se pueden usar en varios contextos.</span><span class="sxs-lookup"><span data-stu-id="442f5-206">[First-class functions](first-class-functions.md) explores functions deeply, showing how you can use them in various contexts.</span></span>

## <a name="further-reading"></a><span data-ttu-id="442f5-207">Información adicional</span><span class="sxs-lookup"><span data-stu-id="442f5-207">Further reading</span></span>

<span data-ttu-id="442f5-208">La serie [funcionalmente](https://fsharpforfunandprofit.com/posts/thinking-functionally-intro/) es otro recurso fantástico para obtener información sobre la programación funcional F#con.</span><span class="sxs-lookup"><span data-stu-id="442f5-208">The [Thinking Functionally](https://fsharpforfunandprofit.com/posts/thinking-functionally-intro/) series is another great resource to learn about functional programming with F#.</span></span> <span data-ttu-id="442f5-209">Trata aspectos básicos de la programación funcional de forma pragmática y fácil de leer, mediante el uso F# de características para ilustrar los conceptos.</span><span class="sxs-lookup"><span data-stu-id="442f5-209">It covers fundamentals of functional programming in a pragmatic and easy-to-read way, using F# features to illustrate the concepts.</span></span>
