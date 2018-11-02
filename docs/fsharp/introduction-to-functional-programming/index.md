---
title: Introducción a la programación funcional en F#
description: Conozca los aspectos básicos de la programación funcional en F#.
ms.date: 10/29/2018
ms.openlocfilehash: d4a9bb0cd826b41aca96e12e2bcb5aab80c18eb4
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2018
ms.locfileid: "25724482"
---
# <a name="introduction-to-functional-programming-in-f"></a><span data-ttu-id="7aaaf-103">Introducción a la programación funcional en F#</span><span class="sxs-lookup"><span data-stu-id="7aaaf-103">Introduction to Functional Programming in F#</span></span> #

<span data-ttu-id="7aaaf-104">Programación funcional es un estilo de programación que resalta el uso de funciones y datos inmutables.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-104">Functional programming is a style of programming that emphasizes the use of functions and immutable data.</span></span> <span data-ttu-id="7aaaf-105">Programación funcional con tipo es cuando se combina la programación funcional con tipos estáticos, como con F#.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-105">Typed functional programming is when functional programming is combined with static types, such as with F#.</span></span> <span data-ttu-id="7aaaf-106">En general, se destacan los siguientes conceptos de programación funcional:</span><span class="sxs-lookup"><span data-stu-id="7aaaf-106">In general, the following concepts are emphasized in functional programming:</span></span>

* <span data-ttu-id="7aaaf-107">Funciones como las construcciones principales que usar</span><span class="sxs-lookup"><span data-stu-id="7aaaf-107">Functions as the primary constructs you use</span></span>
* <span data-ttu-id="7aaaf-108">Expresiones en lugar de instrucciones</span><span class="sxs-lookup"><span data-stu-id="7aaaf-108">Expressions instead of statements</span></span>
* <span data-ttu-id="7aaaf-109">Valores inmutables sobre las variables</span><span class="sxs-lookup"><span data-stu-id="7aaaf-109">Immutable values over variables</span></span>
* <span data-ttu-id="7aaaf-110">Programación declarativa a través de la programación imperativa</span><span class="sxs-lookup"><span data-stu-id="7aaaf-110">Declarative programming over imperative programming</span></span>

<span data-ttu-id="7aaaf-111">A lo largo de esta serie, exploraremos los conceptos y patrones de programación funcional mediante F#.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-111">Throughout this series, you'll explore concepts and patterns in functional programming using F#.</span></span> <span data-ttu-id="7aaaf-112">En el camino, obtendrá información sobre algunos F# demasiado.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-112">Along the way, you'll learn some F# too.</span></span>

## <a name="terminology"></a><span data-ttu-id="7aaaf-113">Terminología</span><span class="sxs-lookup"><span data-stu-id="7aaaf-113">Terminology</span></span>

<span data-ttu-id="7aaaf-114">Incluye un vocabulario que finalmente deberá aprender programación funcional, al igual que otros paradigmas de programación.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-114">Functional programming, like other programming paradigms, comes with a vocabulary that you will eventually need to learn.</span></span> <span data-ttu-id="7aaaf-115">Estos son algunos términos comunes que verá todo el tiempo:</span><span class="sxs-lookup"><span data-stu-id="7aaaf-115">Here are some common terms you'll see all of the time:</span></span>

* <span data-ttu-id="7aaaf-116">**Función** -una función es una construcción que generará un resultado cuando se especifica una entrada.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-116">**Function** - A function is a construct that will produce an output when given an input.</span></span> <span data-ttu-id="7aaaf-117">Más formalmente, lo _asigna_ establece un elemento de uno a otro conjunto.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-117">More formally, it _maps_ an item from one set to another set.</span></span> <span data-ttu-id="7aaaf-118">Este formalismo se levanta en lo concreto en muchos sentidos, especialmente cuando se usa funciones que operan en colecciones de datos.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-118">This formalism is lifted into the concrete in many ways, especially when using functions that operate on collections of data.</span></span> <span data-ttu-id="7aaaf-119">Es un concepto más básico (e importante) en la programación funcional.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-119">It is the most basic (and important) concept in functional programming.</span></span> 
* <span data-ttu-id="7aaaf-120">**Expresión** : una expresión es una construcción de código que genera un valor.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-120">**Expression** - An expression is a construct in code that produces a value.</span></span> <span data-ttu-id="7aaaf-121">En F#, este valor debe ser enlazada o explícitamente se omiten.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-121">In F#, this value must be bound or explicitly ignored.</span></span> <span data-ttu-id="7aaaf-122">Una expresión se puede reemplazar de forma trivial mediante una llamada de función.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-122">An expression can be trivially replaced by a function call.</span></span>
* <span data-ttu-id="7aaaf-123">**Pureza** -pureza es una propiedad de una función de modo que su valor devuelto siempre es el mismo para los mismos argumentos, y que su evaluación tiene efectos secundarios.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-123">**Purity** - Purity is a property of a function such that its return value is always the same for the same arguments, and that its evaluation has no side effects.</span></span> <span data-ttu-id="7aaaf-124">Una función pura depende por completo sus argumentos.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-124">A pure function depends entirely on its arguments.</span></span>
* <span data-ttu-id="7aaaf-125">**Transparencia referencial** -transparencia referencial es una propiedad de las expresiones de modo que puedan reemplazarse con sus resultados sin afectar al comportamiento de un programa.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-125">**Referential Transparency** - Referential Transparency is a property of expressions such that they can be replaced with their output without affecting a program's behavior.</span></span>
* <span data-ttu-id="7aaaf-126">**La inmutabilidad** -significa de inmutabilidad que no puede ser un valor cambiado en contexto.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-126">**Immutability** - Immutability means that a value cannot be changed in-place.</span></span> <span data-ttu-id="7aaaf-127">Se trata a diferencia de las variables, que pueden cambiar en su lugar.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-127">This is in contrast with variables, which can change in place.</span></span>

## <a name="examples"></a><span data-ttu-id="7aaaf-128">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="7aaaf-128">Examples</span></span>

<span data-ttu-id="7aaaf-129">Los ejemplos siguientes muestran estos conceptos básicos.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-129">The following examples demonstrate these core concepts.</span></span>

### <a name="functions"></a><span data-ttu-id="7aaaf-130">Funciones</span><span class="sxs-lookup"><span data-stu-id="7aaaf-130">Functions</span></span>

<span data-ttu-id="7aaaf-131">Una construcción más comunes y fundamental en la programación funcional es la función.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-131">The most common and fundamental construct in functional programming is the function.</span></span> <span data-ttu-id="7aaaf-132">Esta es una función sencilla que suma 1 a un entero:</span><span class="sxs-lookup"><span data-stu-id="7aaaf-132">Here's a simple function that adds 1 to an integer:</span></span>

```fsharp
let addOne x = x + 1
```

<span data-ttu-id="7aaaf-133">La firma de su tipo es como sigue:</span><span class="sxs-lookup"><span data-stu-id="7aaaf-133">Its type signature is as follows:</span></span>

```fsharp
val addOne: x:int -> int
```

<span data-ttu-id="7aaaf-134">La firma se puede leer como, "`addOne` acepta un `int` denominado `x` y generará una `int`".</span><span class="sxs-lookup"><span data-stu-id="7aaaf-134">The signature can be read as, "`addOne` accepts an `int` named `x` and will produce an `int`".</span></span> <span data-ttu-id="7aaaf-135">Más formalmente, `addOne` es _asignación_ un valor del conjunto de enteros para el conjunto de enteros.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-135">More formally, `addOne` is _mapping_ a value from the set of integers to the set of integers.</span></span> <span data-ttu-id="7aaaf-136">El `->` token significa que esta asignación.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-136">The `->` token signifies this mapping.</span></span> <span data-ttu-id="7aaaf-137">En F#, normalmente puede mirar la firma de función para hacerse una idea de lo que hace.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-137">In F#, you can usually look at the function signature to get a sense for what it does.</span></span>

<span data-ttu-id="7aaaf-138">Por lo tanto, ¿por qué la firma es importante?</span><span class="sxs-lookup"><span data-stu-id="7aaaf-138">So, why is the signature important?</span></span> <span data-ttu-id="7aaaf-139">En la programación funcional con tipo, la implementación de una función suele ser más importante que la firma del tipo real.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-139">In typed functional programming, the implementation of a function is often less important than the actual type signature!</span></span> <span data-ttu-id="7aaaf-140">El hecho de que `addOne` agrega el valor 1 en un entero es interesante en tiempo de ejecución, pero cuando se construye un programa, el hecho de que acepte y devuelva un `int` es lo que le informa de cómo lo utilizará esta función.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-140">The fact that `addOne` adds the value 1 to an integer is interesting at runtime, but when you are constructing a program, the fact that it accepts and returns an `int` is what informs how you will actually use this function.</span></span> <span data-ttu-id="7aaaf-141">Además, una vez que use esta función correctamente (con respecto a su signatura de tipo), diagnosticar problemas puede realizarse solo dentro del cuerpo de la `addOne` función.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-141">Furthermore, once you use this function correctly (with respect to its type signature), diagnosing any problems can be done only within the body of the `addOne` function.</span></span> <span data-ttu-id="7aaaf-142">Este es el impulso que hay detrás de la programación funcional con tipo.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-142">This is the impetus behind typed functional programming.</span></span>

### <a name="expressions"></a><span data-ttu-id="7aaaf-143">Expresiones</span><span class="sxs-lookup"><span data-stu-id="7aaaf-143">Expressions</span></span>

<span data-ttu-id="7aaaf-144">Las expresiones son construcciones que se evalúan como un valor.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-144">Expressions are constructs that evaluate to a value.</span></span> <span data-ttu-id="7aaaf-145">A diferencia de las instrucciones, que realizan una acción, se pueden considerar las expresiones de llevar a cabo una acción que devuelve un valor.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-145">In contrast to statements, which perform an action, expressions can be thought of performing an action that gives back a value.</span></span> <span data-ttu-id="7aaaf-146">Las expresiones se usan casi siempre en favor de las instrucciones en la programación funcional.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-146">Expressions are almost always used in favor of statements in functional programming.</span></span>

<span data-ttu-id="7aaaf-147">Considere la función anterior, `addOne`.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-147">Consider the previous function, `addOne`.</span></span> <span data-ttu-id="7aaaf-148">El cuerpo de `addOne` es una expresión:</span><span class="sxs-lookup"><span data-stu-id="7aaaf-148">The body of `addOne` is an expression:</span></span>

```fsharp
// 'x + 1' is an expression!
let addOne x = x + 1
```

<span data-ttu-id="7aaaf-149">Es el resultado de esta expresión que define el tipo de resultado de la `addOne` función.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-149">It is the result of this expression that defines the result type of the `addOne` function.</span></span> <span data-ttu-id="7aaaf-150">Por ejemplo, se pudo cambiar la expresión que constituye esta función para que sea un tipo diferente, como un `string`:</span><span class="sxs-lookup"><span data-stu-id="7aaaf-150">For example, the expression that makes up this function could be changed to be a different type, such as a `string`:</span></span>

```fsharp
let addOne x = x.ToString() + "1"
```

<span data-ttu-id="7aaaf-151">La firma de la función ahora es:</span><span class="sxs-lookup"><span data-stu-id="7aaaf-151">The signature of the function is now:</span></span>

```fsharp
val addOne: x:'a -> string
```

<span data-ttu-id="7aaaf-152">Desde cualquier tipo de F# puede tener `ToString()` llamado en ella, el tipo de `x` se ha realizado genérico (llamado [generalización automática](../language-reference/generics/automatic-generalization.md)), y el tipo resultante es un `string`.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-152">Since any type in F# can have `ToString()` called on it, the type of `x` has been made generic (called [Automatic Generalization](../language-reference/generics/automatic-generalization.md)), and the resultant type is a `string`.</span></span>

<span data-ttu-id="7aaaf-153">Las expresiones no son simplemente los cuerpos de funciones.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-153">Expressions are not just the bodies of functions.</span></span> <span data-ttu-id="7aaaf-154">Puede hacer que las expresiones que producen un valor que se usa en otro lugar.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-154">You can have expressions that produce a value you use elsewhere.</span></span> <span data-ttu-id="7aaaf-155">Es un común `if`:</span><span class="sxs-lookup"><span data-stu-id="7aaaf-155">A common one is `if`:</span></span>

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

<span data-ttu-id="7aaaf-156">El `if` expresión genera un valor denominado `result`.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-156">The `if` expression produces a value called `result`.</span></span> <span data-ttu-id="7aaaf-157">Tenga en cuenta que puede omitir `result` por completo, que hace el `if` el cuerpo de la expresión de la `addOneIfOdd` función.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-157">Note that you could omit `result` entirely, making the `if` expression the body of the `addOneIfOdd` function.</span></span> <span data-ttu-id="7aaaf-158">La clave que debe recordar acerca de las expresiones es que genera un valor.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-158">The key thing to remember about expressions is that they produce a value.</span></span>

<span data-ttu-id="7aaaf-159">Hay un tipo especial, `unit`, que se utiliza cuando hay que devolver nada.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-159">There is a special type, `unit`, that is used when there is nothing to return.</span></span> <span data-ttu-id="7aaaf-160">Por ejemplo, considere la posibilidad de esta función simple:</span><span class="sxs-lookup"><span data-stu-id="7aaaf-160">For example, consider this simple function:</span></span>

```fsharp
let printString (str: string) =
    printfn "String is: %s" s
```

<span data-ttu-id="7aaaf-161">La firma tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="7aaaf-161">The signature looks like this:</span></span>

```fsharp
val printString: str:string -> unit
```

<span data-ttu-id="7aaaf-162">El `unit` tipo indica que no hay ningún valor real que se devuelve.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-162">The `unit` type indicates that there is no actual value being returned.</span></span> <span data-ttu-id="7aaaf-163">Esto es útil cuando tiene una rutina que debe "funcione" a pesar de no tener ningún valor para devolver como resultado de ese trabajo.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-163">This is useful when you have a routine that must "do work" despite having no value to return as a result of that work.</span></span>

<span data-ttu-id="7aaaf-164">Esto es en contraste con la programación imperativa, donde el equivalente `if` construcción es una instrucción y generar los valores se suele hacer con las variables de mutación.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-164">This is in sharp contrast to imperative programming, where the equivalent `if` construct is a statement, and producing values is often done with mutating variables.</span></span> <span data-ttu-id="7aaaf-165">Por ejemplo, en C#, se podría escribir el código similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="7aaaf-165">For example, in C#, the code might be written like this:</span></span>

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

<span data-ttu-id="7aaaf-166">Merece la pena mencionar que C# y otros lenguajes de estilo de C admiten la [expresión ternaria](../../csharp/language-reference/operators/conditional-operator.md), lo que permite la programación condicional basada en expresión.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-166">It's worth noting that C# and other C-style languages do support the [ternary expression](../../csharp/language-reference/operators/conditional-operator.md), which allows for expression-based conditional programming.</span></span>

<span data-ttu-id="7aaaf-167">En la programación funcional, es poco frecuente mutar valores con instrucciones.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-167">In functional programming, it is rare to mutate values with statements.</span></span> <span data-ttu-id="7aaaf-168">Aunque algunos lenguajes funcionales son compatibles con las instrucciones y mutación, no es habitual usar estos conceptos en la programación funcional.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-168">Although some functional languages support statements and mutation, it is not common to use these concepts in functional programming.</span></span>

### <a name="pure-functions"></a><span data-ttu-id="7aaaf-169">Funciones puras</span><span class="sxs-lookup"><span data-stu-id="7aaaf-169">Pure functions</span></span>

<span data-ttu-id="7aaaf-170">Como se mencionó anteriormente, puras funciones son funciones:</span><span class="sxs-lookup"><span data-stu-id="7aaaf-170">As previously mentioned, pure functions are functions that:</span></span>

* <span data-ttu-id="7aaaf-171">Evalúe siempre el mismo valor para la misma entrada.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-171">Always evaluate to the same value for the same input.</span></span>
* <span data-ttu-id="7aaaf-172">No tienen efectos secundarios.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-172">Have no side effects.</span></span>

<span data-ttu-id="7aaaf-173">Resulta útil pensar en las funciones matemáticas en este contexto.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-173">It is helpful to think of mathematical functions in this context.</span></span> <span data-ttu-id="7aaaf-174">En matemáticas, las funciones sólo dependen de sus argumentos y no tiene efectos secundarios.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-174">In mathematics, functions depend only on their arguments and do not have any side effects.</span></span> <span data-ttu-id="7aaaf-175">En la función matemática `f(x) = x + 1`, el valor de `f(x)` solo depende del valor de `x`.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-175">In the mathematical function `f(x) = x + 1`, the value of `f(x)` depends only on the value of `x`.</span></span> <span data-ttu-id="7aaaf-176">Las funciones puras en la programación funcional son la misma manera.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-176">Pure functions in functional programming are the same way.</span></span>

<span data-ttu-id="7aaaf-177">Al escribir una función pura, la función debe depender únicamente de sus argumentos y no realiza ninguna acción que da como resultado un efecto secundario.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-177">When writing a pure function, the function must depend only on its arguments and not perform any action that results in a side effect.</span></span>

<span data-ttu-id="7aaaf-178">Este es un ejemplo de una función no pura porque depende de estado mutable global:</span><span class="sxs-lookup"><span data-stu-id="7aaaf-178">Here is an example of a non-pure function because it depends on global, mutable state:</span></span>

```fsharp
let mutable value = 1

let addOneToValue x = x + value
```

<span data-ttu-id="7aaaf-179">El `addOneToValue` función es claramente impuras, porque `value` podría cambiarse en cualquier momento para tener un valor distinto de 1.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-179">The `addOneToValue` function is clearly impure, because `value` could be changed at any time to have a different value than 1.</span></span> <span data-ttu-id="7aaaf-180">Este patrón de según un valor global es que deben evitarse en la programación funcional.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-180">This pattern of depending on a global value is to be avoided in functional programming.</span></span>

<span data-ttu-id="7aaaf-181">Este es otro ejemplo de una función no pura, ya que realiza un efecto secundario:</span><span class="sxs-lookup"><span data-stu-id="7aaaf-181">Here is another example of a non-pure function, because it performs a side effect:</span></span>

```fsharp
let addOneToValue x = 
    printfn "x is %d" x
    x + 1
```

<span data-ttu-id="7aaaf-182">Aunque esta función no depende de un valor global, escribe el valor de `x` a la salida del programa.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-182">Although this function does not depend on a global value, it writes the value of `x` to the output of the program.</span></span> <span data-ttu-id="7aaaf-183">Aunque no hay ningún problema inherente al hacer esto, ¿significa que la función no es pura.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-183">Although there is nothing inherently wrong with doing this, it does mean that the function is not pure.</span></span>

<span data-ttu-id="7aaaf-184">Quitar el `printfn` instrucción finally hace que la función pura:</span><span class="sxs-lookup"><span data-stu-id="7aaaf-184">Removing the `printfn` statement finally makes the function pure:</span></span>

```fsharp
let addOneToValue x = x + 1
```

<span data-ttu-id="7aaaf-185">Aunque esta función no es intrínsecamente _mejor_ que la versión anterior con el `printfn` instrucción, garantizar que todo lo que hace esta función es devolver un valor.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-185">Although this function is not inherently _better_ than the previous version with the `printfn` statement, it does guarantee that all this function does is return a value.</span></span> <span data-ttu-id="7aaaf-186">La llamada a esta función una vez o 1 millones de veces que el resultado sigue el mismo resultado: generar sólo un valor.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-186">Calling this function once or 1 billion times will still result in the same thing: just producing a value.</span></span> <span data-ttu-id="7aaaf-187">Esta capacidad de predicción es útil en la programación funcional, ya que significa que cualquier función pura es transparente forma referencial.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-187">This predictability is valuable in functional programming, as it means that any pure function is referentially transparent.</span></span>

### <a name="referential-transparency"></a><span data-ttu-id="7aaaf-188">Transparencia referencial</span><span class="sxs-lookup"><span data-stu-id="7aaaf-188">Referential Transparency</span></span>

<span data-ttu-id="7aaaf-189">Transparencia referencial es una propiedad de las expresiones y funciones.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-189">Referential transparency is a property of expressions and functions.</span></span> <span data-ttu-id="7aaaf-190">Para que ser transparentes de forma referencial una expresión, debe poder reemplazarse con su valor resultante sin cambiar el comportamiento del programa.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-190">For an expression to be referentially transparent, it must be able to be replaced with its resulting value without changing the program's behavior.</span></span> <span data-ttu-id="7aaaf-191">Todas las funciones puras son transparentes de forma referencial.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-191">All pure functions are referentially transparent.</span></span>

<span data-ttu-id="7aaaf-192">Al igual que con las funciones puras, puede ser útil pensar en transparencia referencial desde una perspectiva de matemática.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-192">As with pure functions, it can be helpful to think of referential transparency from a mathematical perspective.</span></span> <span data-ttu-id="7aaaf-193">En la expresión matemática `y = f(x)`, `f(x)` puede reemplazarse por el resultado de la función y todavía será igual a `y`.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-193">In the mathematical expression `y = f(x)`, `f(x)` can be replaced by the result of the function and it will still be equal to `y`.</span></span> <span data-ttu-id="7aaaf-194">Esto ocurre igualmente para la transparencia referencial en la programación funcional.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-194">This is equally true for referential transparency in functional programming.</span></span>

<span data-ttu-id="7aaaf-195">Considere la posibilidad de llamar a definidos previamente `addOneIfOdd` funcionar dos veces:</span><span class="sxs-lookup"><span data-stu-id="7aaaf-195">Consider calling the previously defined `addOneIfOdd` function twice:</span></span>

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

let res1 = addOneIffOdd 1 // Produces 2
let res2 = addOneIffOdd 2 // Produces 2
```

<span data-ttu-id="7aaaf-196">Podemos reemplazar cada llamada de función con el cuerpo de la función, sustituyendo el argumento `input` con cada valor:</span><span class="sxs-lookup"><span data-stu-id="7aaaf-196">We can replace each function call with the function body, substituting the argument `input` with each value:</span></span>

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

let res1 =
    let result =
        if isOdd 1 then
            1 + 1
        else
            1

    result
let res2 =
    let result =
        if isOdd 2 then
            2 + 1
        else
            2

    result
```

<span data-ttu-id="7aaaf-197">Ambos `res1` y `res2` tienen el mismo valor como si se llamó a la función, lo que indica que `addOneIfOdd` es transparente forma referencial!</span><span class="sxs-lookup"><span data-stu-id="7aaaf-197">Both `res1` and `res2` have the same value as if the function was called, indicating that `addOneIfOdd` is referentially transparent!</span></span>

<span data-ttu-id="7aaaf-198">Además, una función no tiene que ser puro que también sean transparentes de forma referencial.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-198">Additionally, a function doesn't have to be pure to also be referentially transparent.</span></span> <span data-ttu-id="7aaaf-199">Considere la posibilidad de una definición anterior de `addOneTovalue`:</span><span class="sxs-lookup"><span data-stu-id="7aaaf-199">Consider a previous definition of  `addOneTovalue`:</span></span>

```fsharp
let addOneToValue x = 
    printfn "x is %d" x
    x + 1
```

<span data-ttu-id="7aaaf-200">Cualquier llamada a esta función también se puede reemplazar por su cuerpo y lo mismo sucederá cada vez:</span><span class="sxs-lookup"><span data-stu-id="7aaaf-200">Any call to this function can also be replaced by its body and the same things will happen each time:</span></span>

* <span data-ttu-id="7aaaf-201">El valor antes de que se agrega, se imprime en la salida</span><span class="sxs-lookup"><span data-stu-id="7aaaf-201">The value, prior to being added to, is printed to the output</span></span>
* <span data-ttu-id="7aaaf-202">El valor tiene 1 agregado</span><span class="sxs-lookup"><span data-stu-id="7aaaf-202">The value has 1 added to it</span></span>

<span data-ttu-id="7aaaf-203">Al programar en F#, suele ser transparencia referencial que es el objetivo, en lugar de pureza.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-203">When programming in F#, it is often referential transparency that is the goal, rather than purity.</span></span> <span data-ttu-id="7aaaf-204">Sin embargo, es recomendable todavía para escribir funciones puras siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-204">However, it is still good practice to write pure functions when you can.</span></span>

### <a name="immutability"></a><span data-ttu-id="7aaaf-205">Inmutabilidad</span><span class="sxs-lookup"><span data-stu-id="7aaaf-205">Immutability</span></span>

<span data-ttu-id="7aaaf-206">Por último, uno de los conceptos más fundamentales de la programación funcional con tipo es la inmutabilidad.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-206">Finally, one of the most fundamental concepts of typed functional programming is immutability.</span></span> <span data-ttu-id="7aaaf-207">En F#, todos los valores son inmutables de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-207">In F#, all values are immutable by default.</span></span> <span data-ttu-id="7aaaf-208">Esto significa que no pueden ser transformarlos in situ a menos que marque explícitamente como mutables.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-208">That means they cannot be mutated in-place unless you explicitly mark them as mutable.</span></span>

<span data-ttu-id="7aaaf-209">En la práctica, trabajar con valores inmutables significa que cambiar su enfoque a la programación de "Necesito cambiar algo" a "necesito generar un nuevo valor".</span><span class="sxs-lookup"><span data-stu-id="7aaaf-209">In practice, working with immutable values means that you change your approach to programming from, "I need to change something", to "I need to produce a new value".</span></span>

<span data-ttu-id="7aaaf-210">Por ejemplo, agregando 1 a un valor significa que generar un nuevo valor, no una mutación existente:</span><span class="sxs-lookup"><span data-stu-id="7aaaf-210">For example, adding 1 to a value means producing a new value, not mutating the existing one:</span></span>

```fsharp
let value = 1
let secondValue = value + 1
```

<span data-ttu-id="7aaaf-211">En F#, el código siguiente hace **no** mutar la `value` función; en su lugar, realiza una comprobación de igualdad:</span><span class="sxs-lookup"><span data-stu-id="7aaaf-211">In F#, the following code does **not** mutate the `value` function; instead, it performs an equality check:</span></span>

```fsharp
let value = 1
value = value + 1 // Produces a 'bool' value!
```

<span data-ttu-id="7aaaf-212">Algunos lenguajes de programación funcionales no admiten mutación en absoluto.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-212">Some functional programming languages do not support mutation at all.</span></span> <span data-ttu-id="7aaaf-213">En F#, que es compatible, pero no es el comportamiento predeterminado para los valores.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-213">In F#, it is supported, but it is not the default behavior for values.</span></span>

<span data-ttu-id="7aaaf-214">Este concepto se extiende más allá de las estructuras de datos.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-214">This concept extends even further to data structures.</span></span> <span data-ttu-id="7aaaf-215">En la programación funcional, estructuras de datos inmutables como conjuntos (y muchos más) tienen una implementación diferente que inicialmente podría esperan.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-215">In functional programming, immutable data structures such as sets (and many more) have a different implementation than you might initially expect.</span></span> <span data-ttu-id="7aaaf-216">Conceptualmente, algo así agregando un elemento a un conjunto no cambia el conjunto, genera un _nuevo_ establecido con el valor agregado.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-216">Conceptually, something like adding an item to a set does not change the set, it produces a _new_ set with the added value.</span></span> <span data-ttu-id="7aaaf-217">En segundo plano, a menudo esto se logra mediante una estructura de datos diferentes que se permite para el seguimiento de forma eficaz un valor para que la representación apropiada de los datos puede tener como resultado.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-217">Under the covers, this is often accomplished by a different data structure that allows for efficiently tracking a value so that the appropriate representation of the data can be given as a result.</span></span>

<span data-ttu-id="7aaaf-218">Este estilo de trabajar con los valores y las estructuras de datos es fundamental, tal como nos vemos obligados a tratar cualquier operación que modifique algo como si crea una nueva versión de eso.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-218">This style of working with values and data structures is critical, as it forces you to treat any operation that modifies something as if it creates a new version of that thing.</span></span> <span data-ttu-id="7aaaf-219">Esto permite cosas como comprobar su igualdad y comparación para que sea coherente en los programas.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-219">This allows for things like equality and comparability to be consistent in your programs.</span></span>

## <a name="next-steps"></a><span data-ttu-id="7aaaf-220">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="7aaaf-220">Next steps</span></span>

<span data-ttu-id="7aaaf-221">La siguiente sección tratará exhaustivamente las funciones, explorar maneras diferentes, puede usar en la programación funcional.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-221">The next section will thoroughly cover functions, exploring different ways you can use them in functional programming.</span></span>

<span data-ttu-id="7aaaf-222">[Funciones de primera clase](first-class-functions.md) explora funciones profundamente, que muestra cómo puede usarlos en distintos contextos.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-222">[First-class functions](first-class-functions.md) explores functions deeply, showing how you can use them in various contexts.</span></span>

## <a name="further-reading"></a><span data-ttu-id="7aaaf-223">Información adicional</span><span class="sxs-lookup"><span data-stu-id="7aaaf-223">Further reading</span></span>

<span data-ttu-id="7aaaf-224">El [funcionalmente pensando](https://fsharpforfunandprofit.com/posts/thinking-functionally-intro/) serie es otro excelente recurso para aprender sobre la programación funcional con F#.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-224">The [Thinking Functionally](https://fsharpforfunandprofit.com/posts/thinking-functionally-intro/) series is another great resource to learn about functional programming with F#.</span></span> <span data-ttu-id="7aaaf-225">Abarca conceptos básicos de la programación funcional de forma pragmática y fácil de leer, con F# características para ilustrar los conceptos.</span><span class="sxs-lookup"><span data-stu-id="7aaaf-225">It covers fundamentals of functional programming in a pragmatic and easy-to-read way, using F# features to illustrate the concepts.</span></span>