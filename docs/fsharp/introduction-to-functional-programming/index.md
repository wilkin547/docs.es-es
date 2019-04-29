---
title: Introducción a la programación funcional en F#
description: Conozca los aspectos básicos de la programación funcional en F#.
ms.date: 10/29/2018
ms.openlocfilehash: 84022e58c0f17b9e9875402c653c31e494e940da
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772793"
---
# <a name="introduction-to-functional-programming-in-f"></a><span data-ttu-id="80f88-103">Introducción a la programación funcional en F\#</span><span class="sxs-lookup"><span data-stu-id="80f88-103">Introduction to Functional Programming in F\#</span></span>

<span data-ttu-id="80f88-104">Programación funcional es un estilo de programación que resalta el uso de funciones y datos inmutables.</span><span class="sxs-lookup"><span data-stu-id="80f88-104">Functional programming is a style of programming that emphasizes the use of functions and immutable data.</span></span> <span data-ttu-id="80f88-105">Programación funcional con tipo es cuando se combina la programación funcional con tipos estáticos, como con F#.</span><span class="sxs-lookup"><span data-stu-id="80f88-105">Typed functional programming is when functional programming is combined with static types, such as with F#.</span></span> <span data-ttu-id="80f88-106">En general, se destacan los siguientes conceptos de programación funcional:</span><span class="sxs-lookup"><span data-stu-id="80f88-106">In general, the following concepts are emphasized in functional programming:</span></span>

* <span data-ttu-id="80f88-107">Funciones como las construcciones principales que usar</span><span class="sxs-lookup"><span data-stu-id="80f88-107">Functions as the primary constructs you use</span></span>
* <span data-ttu-id="80f88-108">Expresiones en lugar de instrucciones</span><span class="sxs-lookup"><span data-stu-id="80f88-108">Expressions instead of statements</span></span>
* <span data-ttu-id="80f88-109">Valores inmutables sobre las variables</span><span class="sxs-lookup"><span data-stu-id="80f88-109">Immutable values over variables</span></span>
* <span data-ttu-id="80f88-110">Programación declarativa a través de la programación imperativa</span><span class="sxs-lookup"><span data-stu-id="80f88-110">Declarative programming over imperative programming</span></span>

<span data-ttu-id="80f88-111">A lo largo de esta serie, exploraremos los conceptos y patrones de programación funcional mediante F#.</span><span class="sxs-lookup"><span data-stu-id="80f88-111">Throughout this series, you'll explore concepts and patterns in functional programming using F#.</span></span> <span data-ttu-id="80f88-112">En el camino, obtendrá información sobre algunos F# demasiado.</span><span class="sxs-lookup"><span data-stu-id="80f88-112">Along the way, you'll learn some F# too.</span></span>

## <a name="terminology"></a><span data-ttu-id="80f88-113">Terminología</span><span class="sxs-lookup"><span data-stu-id="80f88-113">Terminology</span></span>

<span data-ttu-id="80f88-114">Incluye un vocabulario que finalmente deberá aprender programación funcional, al igual que otros paradigmas de programación.</span><span class="sxs-lookup"><span data-stu-id="80f88-114">Functional programming, like other programming paradigms, comes with a vocabulary that you will eventually need to learn.</span></span> <span data-ttu-id="80f88-115">Estos son algunos términos comunes que verá todo el tiempo:</span><span class="sxs-lookup"><span data-stu-id="80f88-115">Here are some common terms you'll see all of the time:</span></span>

* <span data-ttu-id="80f88-116">**Función** -una función es una construcción que generará un resultado cuando se especifica una entrada.</span><span class="sxs-lookup"><span data-stu-id="80f88-116">**Function** - A function is a construct that will produce an output when given an input.</span></span> <span data-ttu-id="80f88-117">Más formalmente, lo _asigna_ establece un elemento de uno a otro conjunto.</span><span class="sxs-lookup"><span data-stu-id="80f88-117">More formally, it _maps_ an item from one set to another set.</span></span> <span data-ttu-id="80f88-118">Este formalismo se levanta en lo concreto en muchos sentidos, especialmente cuando se usa funciones que operan en colecciones de datos.</span><span class="sxs-lookup"><span data-stu-id="80f88-118">This formalism is lifted into the concrete in many ways, especially when using functions that operate on collections of data.</span></span> <span data-ttu-id="80f88-119">Es un concepto más básico (e importante) en la programación funcional.</span><span class="sxs-lookup"><span data-stu-id="80f88-119">It is the most basic (and important) concept in functional programming.</span></span> 
* <span data-ttu-id="80f88-120">**Expresión** : una expresión es una construcción de código que genera un valor.</span><span class="sxs-lookup"><span data-stu-id="80f88-120">**Expression** - An expression is a construct in code that produces a value.</span></span> <span data-ttu-id="80f88-121">En F#, este valor debe ser enlazada o explícitamente se omiten.</span><span class="sxs-lookup"><span data-stu-id="80f88-121">In F#, this value must be bound or explicitly ignored.</span></span> <span data-ttu-id="80f88-122">Una expresión se puede reemplazar de forma trivial mediante una llamada de función.</span><span class="sxs-lookup"><span data-stu-id="80f88-122">An expression can be trivially replaced by a function call.</span></span>
* <span data-ttu-id="80f88-123">**Pureza** -pureza es una propiedad de una función de modo que su valor devuelto siempre es el mismo para los mismos argumentos, y que su evaluación tiene efectos secundarios.</span><span class="sxs-lookup"><span data-stu-id="80f88-123">**Purity** - Purity is a property of a function such that its return value is always the same for the same arguments, and that its evaluation has no side effects.</span></span> <span data-ttu-id="80f88-124">Una función pura depende por completo sus argumentos.</span><span class="sxs-lookup"><span data-stu-id="80f88-124">A pure function depends entirely on its arguments.</span></span>
* <span data-ttu-id="80f88-125">**Transparencia referencial** -transparencia referencial es una propiedad de las expresiones de modo que puedan reemplazarse con sus resultados sin afectar al comportamiento de un programa.</span><span class="sxs-lookup"><span data-stu-id="80f88-125">**Referential Transparency** - Referential Transparency is a property of expressions such that they can be replaced with their output without affecting a program's behavior.</span></span>
* <span data-ttu-id="80f88-126">**La inmutabilidad** -significa de inmutabilidad que no puede ser un valor cambiado en contexto.</span><span class="sxs-lookup"><span data-stu-id="80f88-126">**Immutability** - Immutability means that a value cannot be changed in-place.</span></span> <span data-ttu-id="80f88-127">Se trata a diferencia de las variables, que pueden cambiar en su lugar.</span><span class="sxs-lookup"><span data-stu-id="80f88-127">This is in contrast with variables, which can change in place.</span></span>

## <a name="examples"></a><span data-ttu-id="80f88-128">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="80f88-128">Examples</span></span>

<span data-ttu-id="80f88-129">Los ejemplos siguientes muestran estos conceptos básicos.</span><span class="sxs-lookup"><span data-stu-id="80f88-129">The following examples demonstrate these core concepts.</span></span>

### <a name="functions"></a><span data-ttu-id="80f88-130">Funciones</span><span class="sxs-lookup"><span data-stu-id="80f88-130">Functions</span></span>

<span data-ttu-id="80f88-131">Una construcción más comunes y fundamental en la programación funcional es la función.</span><span class="sxs-lookup"><span data-stu-id="80f88-131">The most common and fundamental construct in functional programming is the function.</span></span> <span data-ttu-id="80f88-132">Esta es una función sencilla que suma 1 a un entero:</span><span class="sxs-lookup"><span data-stu-id="80f88-132">Here's a simple function that adds 1 to an integer:</span></span>

```fsharp
let addOne x = x + 1
```

<span data-ttu-id="80f88-133">La firma de su tipo es como sigue:</span><span class="sxs-lookup"><span data-stu-id="80f88-133">Its type signature is as follows:</span></span>

```fsharp
val addOne: x:int -> int
```

<span data-ttu-id="80f88-134">La firma se puede leer como, "`addOne` acepta un `int` denominado `x` y generará una `int`".</span><span class="sxs-lookup"><span data-stu-id="80f88-134">The signature can be read as, "`addOne` accepts an `int` named `x` and will produce an `int`".</span></span> <span data-ttu-id="80f88-135">Más formalmente, `addOne` es _asignación_ un valor del conjunto de enteros para el conjunto de enteros.</span><span class="sxs-lookup"><span data-stu-id="80f88-135">More formally, `addOne` is _mapping_ a value from the set of integers to the set of integers.</span></span> <span data-ttu-id="80f88-136">El `->` token significa que esta asignación.</span><span class="sxs-lookup"><span data-stu-id="80f88-136">The `->` token signifies this mapping.</span></span> <span data-ttu-id="80f88-137">En F#, normalmente puede mirar la firma de función para hacerse una idea de lo que hace.</span><span class="sxs-lookup"><span data-stu-id="80f88-137">In F#, you can usually look at the function signature to get a sense for what it does.</span></span>

<span data-ttu-id="80f88-138">Por lo tanto, ¿por qué la firma es importante?</span><span class="sxs-lookup"><span data-stu-id="80f88-138">So, why is the signature important?</span></span> <span data-ttu-id="80f88-139">En la programación funcional con tipo, la implementación de una función suele ser más importante que la firma del tipo real.</span><span class="sxs-lookup"><span data-stu-id="80f88-139">In typed functional programming, the implementation of a function is often less important than the actual type signature!</span></span> <span data-ttu-id="80f88-140">El hecho de que `addOne` agrega el valor 1 en un entero es interesante en tiempo de ejecución, pero cuando se construye un programa, el hecho de que acepte y devuelva un `int` es lo que le informa de cómo lo utilizará esta función.</span><span class="sxs-lookup"><span data-stu-id="80f88-140">The fact that `addOne` adds the value 1 to an integer is interesting at runtime, but when you are constructing a program, the fact that it accepts and returns an `int` is what informs how you will actually use this function.</span></span> <span data-ttu-id="80f88-141">Además, una vez que use esta función correctamente (con respecto a su signatura de tipo), diagnosticar problemas puede realizarse solo dentro del cuerpo de la `addOne` función.</span><span class="sxs-lookup"><span data-stu-id="80f88-141">Furthermore, once you use this function correctly (with respect to its type signature), diagnosing any problems can be done only within the body of the `addOne` function.</span></span> <span data-ttu-id="80f88-142">Este es el impulso que hay detrás de la programación funcional con tipo.</span><span class="sxs-lookup"><span data-stu-id="80f88-142">This is the impetus behind typed functional programming.</span></span>

### <a name="expressions"></a><span data-ttu-id="80f88-143">Expresiones</span><span class="sxs-lookup"><span data-stu-id="80f88-143">Expressions</span></span>

<span data-ttu-id="80f88-144">Las expresiones son construcciones que se evalúan como un valor.</span><span class="sxs-lookup"><span data-stu-id="80f88-144">Expressions are constructs that evaluate to a value.</span></span> <span data-ttu-id="80f88-145">A diferencia de las instrucciones, que realizan una acción, se pueden considerar las expresiones de llevar a cabo una acción que devuelve un valor.</span><span class="sxs-lookup"><span data-stu-id="80f88-145">In contrast to statements, which perform an action, expressions can be thought of performing an action that gives back a value.</span></span> <span data-ttu-id="80f88-146">Las expresiones se usan casi siempre en favor de las instrucciones en la programación funcional.</span><span class="sxs-lookup"><span data-stu-id="80f88-146">Expressions are almost always used in favor of statements in functional programming.</span></span>

<span data-ttu-id="80f88-147">Considere la función anterior, `addOne`.</span><span class="sxs-lookup"><span data-stu-id="80f88-147">Consider the previous function, `addOne`.</span></span> <span data-ttu-id="80f88-148">El cuerpo de `addOne` es una expresión:</span><span class="sxs-lookup"><span data-stu-id="80f88-148">The body of `addOne` is an expression:</span></span>

```fsharp
// 'x + 1' is an expression!
let addOne x = x + 1
```

<span data-ttu-id="80f88-149">Es el resultado de esta expresión que define el tipo de resultado de la `addOne` función.</span><span class="sxs-lookup"><span data-stu-id="80f88-149">It is the result of this expression that defines the result type of the `addOne` function.</span></span> <span data-ttu-id="80f88-150">Por ejemplo, se pudo cambiar la expresión que constituye esta función para que sea un tipo diferente, como un `string`:</span><span class="sxs-lookup"><span data-stu-id="80f88-150">For example, the expression that makes up this function could be changed to be a different type, such as a `string`:</span></span>

```fsharp
let addOne x = x.ToString() + "1"
```

<span data-ttu-id="80f88-151">La firma de la función ahora es:</span><span class="sxs-lookup"><span data-stu-id="80f88-151">The signature of the function is now:</span></span>

```fsharp
val addOne: x:'a -> string
```

<span data-ttu-id="80f88-152">Desde cualquier tipo de F# puede tener `ToString()` llamado en ella, el tipo de `x` se ha realizado genérico (llamado [generalización automática](../language-reference/generics/automatic-generalization.md)), y el tipo resultante es un `string`.</span><span class="sxs-lookup"><span data-stu-id="80f88-152">Since any type in F# can have `ToString()` called on it, the type of `x` has been made generic (called [Automatic Generalization](../language-reference/generics/automatic-generalization.md)), and the resultant type is a `string`.</span></span>

<span data-ttu-id="80f88-153">Las expresiones no son simplemente los cuerpos de funciones.</span><span class="sxs-lookup"><span data-stu-id="80f88-153">Expressions are not just the bodies of functions.</span></span> <span data-ttu-id="80f88-154">Puede hacer que las expresiones que producen un valor que se usa en otro lugar.</span><span class="sxs-lookup"><span data-stu-id="80f88-154">You can have expressions that produce a value you use elsewhere.</span></span> <span data-ttu-id="80f88-155">Es un común `if`:</span><span class="sxs-lookup"><span data-stu-id="80f88-155">A common one is `if`:</span></span>

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

<span data-ttu-id="80f88-156">El `if` expresión genera un valor denominado `result`.</span><span class="sxs-lookup"><span data-stu-id="80f88-156">The `if` expression produces a value called `result`.</span></span> <span data-ttu-id="80f88-157">Tenga en cuenta que puede omitir `result` por completo, que hace el `if` el cuerpo de la expresión de la `addOneIfOdd` función.</span><span class="sxs-lookup"><span data-stu-id="80f88-157">Note that you could omit `result` entirely, making the `if` expression the body of the `addOneIfOdd` function.</span></span> <span data-ttu-id="80f88-158">La clave que debe recordar acerca de las expresiones es que genera un valor.</span><span class="sxs-lookup"><span data-stu-id="80f88-158">The key thing to remember about expressions is that they produce a value.</span></span>

<span data-ttu-id="80f88-159">Hay un tipo especial, `unit`, que se utiliza cuando hay que devolver nada.</span><span class="sxs-lookup"><span data-stu-id="80f88-159">There is a special type, `unit`, that is used when there is nothing to return.</span></span> <span data-ttu-id="80f88-160">Por ejemplo, considere la posibilidad de esta función simple:</span><span class="sxs-lookup"><span data-stu-id="80f88-160">For example, consider this simple function:</span></span>

```fsharp
let printString (str: string) =
    printfn "String is: %s" str
```

<span data-ttu-id="80f88-161">La firma tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="80f88-161">The signature looks like this:</span></span>

```fsharp
val printString: str:string -> unit
```

<span data-ttu-id="80f88-162">El `unit` tipo indica que no hay ningún valor real que se devuelve.</span><span class="sxs-lookup"><span data-stu-id="80f88-162">The `unit` type indicates that there is no actual value being returned.</span></span> <span data-ttu-id="80f88-163">Esto es útil cuando tiene una rutina que debe "funcione" a pesar de no tener ningún valor para devolver como resultado de ese trabajo.</span><span class="sxs-lookup"><span data-stu-id="80f88-163">This is useful when you have a routine that must "do work" despite having no value to return as a result of that work.</span></span>

<span data-ttu-id="80f88-164">Esto es en contraste con la programación imperativa, donde el equivalente `if` construcción es una instrucción y generar los valores se suele hacer con las variables de mutación.</span><span class="sxs-lookup"><span data-stu-id="80f88-164">This is in sharp contrast to imperative programming, where the equivalent `if` construct is a statement, and producing values is often done with mutating variables.</span></span> <span data-ttu-id="80f88-165">Por ejemplo, en C#, se podría escribir el código similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="80f88-165">For example, in C#, the code might be written like this:</span></span>

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

<span data-ttu-id="80f88-166">Merece la pena mencionar que C# y otros lenguajes de estilo de C admiten la [expresión ternaria](../../csharp/language-reference/operators/conditional-operator.md), lo que permite la programación condicional basada en expresión.</span><span class="sxs-lookup"><span data-stu-id="80f88-166">It's worth noting that C# and other C-style languages do support the [ternary expression](../../csharp/language-reference/operators/conditional-operator.md), which allows for expression-based conditional programming.</span></span>

<span data-ttu-id="80f88-167">En la programación funcional, es poco frecuente mutar valores con instrucciones.</span><span class="sxs-lookup"><span data-stu-id="80f88-167">In functional programming, it is rare to mutate values with statements.</span></span> <span data-ttu-id="80f88-168">Aunque algunos lenguajes funcionales son compatibles con las instrucciones y mutación, no es habitual usar estos conceptos en la programación funcional.</span><span class="sxs-lookup"><span data-stu-id="80f88-168">Although some functional languages support statements and mutation, it is not common to use these concepts in functional programming.</span></span>

### <a name="pure-functions"></a><span data-ttu-id="80f88-169">Funciones puras</span><span class="sxs-lookup"><span data-stu-id="80f88-169">Pure functions</span></span>

<span data-ttu-id="80f88-170">Como se mencionó anteriormente, puras funciones son funciones:</span><span class="sxs-lookup"><span data-stu-id="80f88-170">As previously mentioned, pure functions are functions that:</span></span>

* <span data-ttu-id="80f88-171">Evalúe siempre el mismo valor para la misma entrada.</span><span class="sxs-lookup"><span data-stu-id="80f88-171">Always evaluate to the same value for the same input.</span></span>
* <span data-ttu-id="80f88-172">No tienen efectos secundarios.</span><span class="sxs-lookup"><span data-stu-id="80f88-172">Have no side effects.</span></span>

<span data-ttu-id="80f88-173">Resulta útil pensar en las funciones matemáticas en este contexto.</span><span class="sxs-lookup"><span data-stu-id="80f88-173">It is helpful to think of mathematical functions in this context.</span></span> <span data-ttu-id="80f88-174">En matemáticas, las funciones sólo dependen de sus argumentos y no tiene efectos secundarios.</span><span class="sxs-lookup"><span data-stu-id="80f88-174">In mathematics, functions depend only on their arguments and do not have any side effects.</span></span> <span data-ttu-id="80f88-175">En la función matemática `f(x) = x + 1`, el valor de `f(x)` solo depende del valor de `x`.</span><span class="sxs-lookup"><span data-stu-id="80f88-175">In the mathematical function `f(x) = x + 1`, the value of `f(x)` depends only on the value of `x`.</span></span> <span data-ttu-id="80f88-176">Las funciones puras en la programación funcional son la misma manera.</span><span class="sxs-lookup"><span data-stu-id="80f88-176">Pure functions in functional programming are the same way.</span></span>

<span data-ttu-id="80f88-177">Al escribir una función pura, la función debe depender únicamente de sus argumentos y no realiza ninguna acción que da como resultado un efecto secundario.</span><span class="sxs-lookup"><span data-stu-id="80f88-177">When writing a pure function, the function must depend only on its arguments and not perform any action that results in a side effect.</span></span>

<span data-ttu-id="80f88-178">Este es un ejemplo de una función no pura porque depende de estado mutable global:</span><span class="sxs-lookup"><span data-stu-id="80f88-178">Here is an example of a non-pure function because it depends on global, mutable state:</span></span>

```fsharp
let mutable value = 1

let addOneToValue x = x + value
```

<span data-ttu-id="80f88-179">El `addOneToValue` función es claramente impuras, porque `value` podría cambiarse en cualquier momento para tener un valor distinto de 1.</span><span class="sxs-lookup"><span data-stu-id="80f88-179">The `addOneToValue` function is clearly impure, because `value` could be changed at any time to have a different value than 1.</span></span> <span data-ttu-id="80f88-180">Este patrón de según un valor global es que deben evitarse en la programación funcional.</span><span class="sxs-lookup"><span data-stu-id="80f88-180">This pattern of depending on a global value is to be avoided in functional programming.</span></span>

<span data-ttu-id="80f88-181">Este es otro ejemplo de una función no pura, ya que realiza un efecto secundario:</span><span class="sxs-lookup"><span data-stu-id="80f88-181">Here is another example of a non-pure function, because it performs a side effect:</span></span>

```fsharp
let addOneToValue x = 
    printfn "x is %d" x
    x + 1
```

<span data-ttu-id="80f88-182">Aunque esta función no depende de un valor global, escribe el valor de `x` a la salida del programa.</span><span class="sxs-lookup"><span data-stu-id="80f88-182">Although this function does not depend on a global value, it writes the value of `x` to the output of the program.</span></span> <span data-ttu-id="80f88-183">Aunque no hay ningún problema inherente al hacer esto, ¿significa que la función no es pura.</span><span class="sxs-lookup"><span data-stu-id="80f88-183">Although there is nothing inherently wrong with doing this, it does mean that the function is not pure.</span></span> <span data-ttu-id="80f88-184">Si otra parte del programa depende de algo externo para el programa, como el búfer de salida, a continuación, llamar a esta función puede afectar a otra parte del programa.</span><span class="sxs-lookup"><span data-stu-id="80f88-184">If another part of your program depends on something external to the program, such as the output buffer, then calling this function can affect that other part of your program.</span></span>

<span data-ttu-id="80f88-185">Quitar el `printfn` instrucción hace que la función pura:</span><span class="sxs-lookup"><span data-stu-id="80f88-185">Removing the `printfn` statement makes the function pure:</span></span>

```fsharp
let addOneToValue x = x + 1
```

<span data-ttu-id="80f88-186">Aunque esta función no es intrínsecamente _mejor_ que la versión anterior con el `printfn` instrucción, garantizar que todo lo que hace esta función es devolver un valor.</span><span class="sxs-lookup"><span data-stu-id="80f88-186">Although this function is not inherently _better_ than the previous version with the `printfn` statement, it does guarantee that all this function does is return a value.</span></span> <span data-ttu-id="80f88-187">Llamar a esta función en cualquier número de veces que produce el mismo resultado: solo genera un valor.</span><span class="sxs-lookup"><span data-stu-id="80f88-187">Calling this function any number of times produces the same result: it just produces a value.</span></span> <span data-ttu-id="80f88-188">La capacidad de predicción dado por la pureza es algo que muchos programadores funcionales se esfuerzan por lograr.</span><span class="sxs-lookup"><span data-stu-id="80f88-188">The predictability given by purity is something many functional programmers strive for.</span></span>

### <a name="immutability"></a><span data-ttu-id="80f88-189">Inmutabilidad</span><span class="sxs-lookup"><span data-stu-id="80f88-189">Immutability</span></span>

<span data-ttu-id="80f88-190">Por último, uno de los conceptos más fundamentales de la programación funcional con tipo es la inmutabilidad.</span><span class="sxs-lookup"><span data-stu-id="80f88-190">Finally, one of the most fundamental concepts of typed functional programming is immutability.</span></span> <span data-ttu-id="80f88-191">En F#, todos los valores son inmutables de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="80f88-191">In F#, all values are immutable by default.</span></span> <span data-ttu-id="80f88-192">Esto significa que no pueden ser transformarlos in situ a menos que marque explícitamente como mutables.</span><span class="sxs-lookup"><span data-stu-id="80f88-192">That means they cannot be mutated in-place unless you explicitly mark them as mutable.</span></span>

<span data-ttu-id="80f88-193">En la práctica, trabajar con valores inmutables significa que cambiar su enfoque a la programación de "Necesito cambiar algo" a "necesito generar un nuevo valor".</span><span class="sxs-lookup"><span data-stu-id="80f88-193">In practice, working with immutable values means that you change your approach to programming from, "I need to change something", to "I need to produce a new value".</span></span>

<span data-ttu-id="80f88-194">Por ejemplo, agregando 1 a un valor significa que generar un nuevo valor, no una mutación existente:</span><span class="sxs-lookup"><span data-stu-id="80f88-194">For example, adding 1 to a value means producing a new value, not mutating the existing one:</span></span>

```fsharp
let value = 1
let secondValue = value + 1
```

<span data-ttu-id="80f88-195">En F#, el código siguiente hace **no** mutar la `value` función; en su lugar, realiza una comprobación de igualdad:</span><span class="sxs-lookup"><span data-stu-id="80f88-195">In F#, the following code does **not** mutate the `value` function; instead, it performs an equality check:</span></span>

```fsharp
let value = 1
value = value + 1 // Produces a 'bool' value!
```

<span data-ttu-id="80f88-196">Algunos lenguajes de programación funcionales no admiten mutación en absoluto.</span><span class="sxs-lookup"><span data-stu-id="80f88-196">Some functional programming languages do not support mutation at all.</span></span> <span data-ttu-id="80f88-197">En F#, que es compatible, pero no es el comportamiento predeterminado para los valores.</span><span class="sxs-lookup"><span data-stu-id="80f88-197">In F#, it is supported, but it is not the default behavior for values.</span></span>

<span data-ttu-id="80f88-198">Este concepto se extiende más allá de las estructuras de datos.</span><span class="sxs-lookup"><span data-stu-id="80f88-198">This concept extends even further to data structures.</span></span> <span data-ttu-id="80f88-199">En la programación funcional, estructuras de datos inmutables como conjuntos (y muchos más) tienen una implementación diferente que inicialmente podría esperan.</span><span class="sxs-lookup"><span data-stu-id="80f88-199">In functional programming, immutable data structures such as sets (and many more) have a different implementation than you might initially expect.</span></span> <span data-ttu-id="80f88-200">Conceptualmente, algo así agregando un elemento a un conjunto no cambia el conjunto, genera un _nuevo_ establecido con el valor agregado.</span><span class="sxs-lookup"><span data-stu-id="80f88-200">Conceptually, something like adding an item to a set does not change the set, it produces a _new_ set with the added value.</span></span> <span data-ttu-id="80f88-201">En segundo plano, a menudo esto se logra mediante una estructura de datos diferentes que se permite para el seguimiento de forma eficaz un valor para que la representación apropiada de los datos puede tener como resultado.</span><span class="sxs-lookup"><span data-stu-id="80f88-201">Under the covers, this is often accomplished by a different data structure that allows for efficiently tracking a value so that the appropriate representation of the data can be given as a result.</span></span>

<span data-ttu-id="80f88-202">Este estilo de trabajar con los valores y las estructuras de datos es fundamental, tal como nos vemos obligados a tratar cualquier operación que modifique algo como si crea una nueva versión de eso.</span><span class="sxs-lookup"><span data-stu-id="80f88-202">This style of working with values and data structures is critical, as it forces you to treat any operation that modifies something as if it creates a new version of that thing.</span></span> <span data-ttu-id="80f88-203">Esto permite cosas como comprobar su igualdad y comparación para que sea coherente en los programas.</span><span class="sxs-lookup"><span data-stu-id="80f88-203">This allows for things like equality and comparability to be consistent in your programs.</span></span>

## <a name="next-steps"></a><span data-ttu-id="80f88-204">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="80f88-204">Next steps</span></span>

<span data-ttu-id="80f88-205">La siguiente sección tratará exhaustivamente las funciones, explorar maneras diferentes, puede usar en la programación funcional.</span><span class="sxs-lookup"><span data-stu-id="80f88-205">The next section will thoroughly cover functions, exploring different ways you can use them in functional programming.</span></span>

<span data-ttu-id="80f88-206">[Funciones de primera clase](first-class-functions.md) explora funciones profundamente, que muestra cómo puede usarlos en distintos contextos.</span><span class="sxs-lookup"><span data-stu-id="80f88-206">[First-class functions](first-class-functions.md) explores functions deeply, showing how you can use them in various contexts.</span></span>

## <a name="further-reading"></a><span data-ttu-id="80f88-207">Información adicional</span><span class="sxs-lookup"><span data-stu-id="80f88-207">Further reading</span></span>

<span data-ttu-id="80f88-208">El [funcionalmente pensando](https://fsharpforfunandprofit.com/posts/thinking-functionally-intro/) serie es otro excelente recurso para aprender sobre la programación funcional con F#.</span><span class="sxs-lookup"><span data-stu-id="80f88-208">The [Thinking Functionally](https://fsharpforfunandprofit.com/posts/thinking-functionally-intro/) series is another great resource to learn about functional programming with F#.</span></span> <span data-ttu-id="80f88-209">Abarca conceptos básicos de la programación funcional de forma pragmática y fácil de leer, con F# características para ilustrar los conceptos.</span><span class="sxs-lookup"><span data-stu-id="80f88-209">It covers fundamentals of functional programming in a pragmatic and easy-to-read way, using F# features to illustrate the concepts.</span></span>
