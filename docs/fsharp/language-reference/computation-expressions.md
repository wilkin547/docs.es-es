---
title: Expresiones de cálculo (F#)
description: Obtenga información sobre cómo crear una sintaxis adecuada para escribir cálculos en F# que se pueden secuenciar y combinar mediante enlaces y construcciones de flujo de control.
ms.date: 07/27/2018
ms.openlocfilehash: 148d1a661fb7630782c6dc48507a66e7bdc1d56b
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2018
ms.locfileid: "48839874"
---
# <a name="computation-expressions"></a><span data-ttu-id="0280c-103">Expresiones de cálculo</span><span class="sxs-lookup"><span data-stu-id="0280c-103">Computation Expressions</span></span>

<span data-ttu-id="0280c-104">Las expresiones de cálculo en F# proporcionan una sintaxis adecuada para escribir cálculos que se pueden secuenciar y combinar mediante enlaces y construcciones de flujo de control.</span><span class="sxs-lookup"><span data-stu-id="0280c-104">Computation expressions in F# provide a convenient syntax for writing computations that can be sequenced and combined using control flow constructs and bindings.</span></span> <span data-ttu-id="0280c-105">Según el tipo de expresión de cálculo, puede considerarse como una forma de expresar monads, monoids, transformadores monad y functors desplazados.</span><span class="sxs-lookup"><span data-stu-id="0280c-105">Depending on the kind of computation expression, they can be thought of as a way to express monads, monoids, monad transformers, and applicative functors.</span></span> <span data-ttu-id="0280c-106">Sin embargo, a diferencia de otros lenguajes (como *notación* en Haskell), que no están asociados a una sola abstracción y no confíe en las macros u otras formas de metaprogramación para lograr una sintaxis adecuada y contextual.</span><span class="sxs-lookup"><span data-stu-id="0280c-106">However, unlike other languages (such as *do-notation* in Haskell), they are not tied to a single abstraction, and do not rely on macros or other forms of metaprogramming to accomplish a convenient and context-sensitive syntax.</span></span>

## <a name="overview"></a><span data-ttu-id="0280c-107">Información general</span><span class="sxs-lookup"><span data-stu-id="0280c-107">Overview</span></span>

<span data-ttu-id="0280c-108">Los cálculos pueden adoptar muchas formas.</span><span class="sxs-lookup"><span data-stu-id="0280c-108">Computations can take many forms.</span></span> <span data-ttu-id="0280c-109">La forma más común de cálculo es un único subproceso de ejecución, que es fácil de entender y modificar.</span><span class="sxs-lookup"><span data-stu-id="0280c-109">The most common form of computation is single-threaded execution, which is easy to understand and modify.</span></span> <span data-ttu-id="0280c-110">Sin embargo, no todas las formas de cálculo son tan sencillas como la ejecución de subproceso único.</span><span class="sxs-lookup"><span data-stu-id="0280c-110">However, not all forms of computation are as straightforward as single-threaded execution.</span></span> <span data-ttu-id="0280c-111">Estos son algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="0280c-111">Some examples include:</span></span>

* <span data-ttu-id="0280c-112">Cálculos no deterministas</span><span class="sxs-lookup"><span data-stu-id="0280c-112">Non-deterministic computations</span></span>
* <span data-ttu-id="0280c-113">Cálculos asincrónicos</span><span class="sxs-lookup"><span data-stu-id="0280c-113">Asynchronous computations</span></span>
* <span data-ttu-id="0280c-114">Cálculos effectful</span><span class="sxs-lookup"><span data-stu-id="0280c-114">Effectful computations</span></span>
* <span data-ttu-id="0280c-115">Cálculos generativas</span><span class="sxs-lookup"><span data-stu-id="0280c-115">Generative computations</span></span>

<span data-ttu-id="0280c-116">Por lo general, hay *contextual* cálculos que se deben realizar en determinadas partes de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="0280c-116">More generally, there are *context-sensitive* computations that you must perform in certain parts of an application.</span></span> <span data-ttu-id="0280c-117">Puede resultar complicado la escritura de código contextual, puesto que es fácil para los cálculos de "pérdida" fuera de un contexto determinado sin abstracciones para evitar que lo hagan.</span><span class="sxs-lookup"><span data-stu-id="0280c-117">Writing context-sensitive code can be challenging, as it is easy to "leak" computations outside of a given context without abstractions to prevent you from doing so.</span></span> <span data-ttu-id="0280c-118">Estas abstracciones a menudo son difíciles de escribir por sí mismo, motivo por el cual F# tiene de forma generalizada llamados **expresiones de cálculo**.</span><span class="sxs-lookup"><span data-stu-id="0280c-118">These abstractions are often challenging to write by yourself, which is why F# has a generalized way to do so called **computation expressions**.</span></span>

<span data-ttu-id="0280c-119">Las expresiones de cálculo ofrecen un modelo de sintaxis y abstracción uniforme para codificación cálculos contextuales.</span><span class="sxs-lookup"><span data-stu-id="0280c-119">Computation expressions offer a uniform syntax and abstraction model for encoding context-sensitive computations.</span></span>

<span data-ttu-id="0280c-120">Cada expresión de cálculo está respaldado por un *generador* tipo.</span><span class="sxs-lookup"><span data-stu-id="0280c-120">Every computation expression is backed by a *builder* type.</span></span> <span data-ttu-id="0280c-121">El tipo de generador define las operaciones que están disponibles para la expresión de cálculo.</span><span class="sxs-lookup"><span data-stu-id="0280c-121">The builder type defines the operations that are available for the computation expression.</span></span> <span data-ttu-id="0280c-122">Consulte [creación de un tipo de expresión de cálculo nueva](computation-expressions.md#creating-a-new-type-of-computation-expression), que muestra cómo crear una expresión de cálculo personalizado.</span><span class="sxs-lookup"><span data-stu-id="0280c-122">See [Creating a New Type of Computation Expression](computation-expressions.md#creating-a-new-type-of-computation-expression), which shows how to create a custom computation expression.</span></span>

### <a name="syntax-overview"></a><span data-ttu-id="0280c-123">Información general de sintaxis</span><span class="sxs-lookup"><span data-stu-id="0280c-123">Syntax overview</span></span>

<span data-ttu-id="0280c-124">Todas las expresiones de cálculo tienen el formato siguiente:</span><span class="sxs-lookup"><span data-stu-id="0280c-124">All computation expressions have the following form:</span></span>

```
builder-expr { cexper }
```

<span data-ttu-id="0280c-125">donde `builder-expr` es el nombre de un tipo de generador que define la expresión de cálculo y `cexper` es el cuerpo de expresión de la expresión de cálculo.</span><span class="sxs-lookup"><span data-stu-id="0280c-125">where `builder-expr` is the name of a builder type that defines the computation expression, and `cexper` is the expression body of the computation expression.</span></span> <span data-ttu-id="0280c-126">Por ejemplo, `async` código de la expresión de cálculo puede tener este aspecto:</span><span class="sxs-lookup"><span data-stu-id="0280c-126">For example, `async` computation expression code can look like this:</span></span>

```fsharp
let fetchAndDownload url =
    async {
        let! data = downloadData url

        let processedData = processData data

        return processedData
    }
```

<span data-ttu-id="0280c-127">Hay una sintaxis especial y adicional disponibles dentro de una expresión de cálculo, como se muestra en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="0280c-127">There is a special, additional syntax available within a computation expression, as shown in the previous example.</span></span> <span data-ttu-id="0280c-128">Los siguientes formatos de expresión son posibles con las expresiones de cálculo:</span><span class="sxs-lookup"><span data-stu-id="0280c-128">The following expression forms are possible with computation expressions:</span></span>

```fsharp
expr { let! ... }
expr { do! ... }
expr { yield ... }
expr { yield! ... }
expr { return ... }
expr { return! ... }
expr { match! ... }
```

<span data-ttu-id="0280c-129">Cada una de estas palabras clave y otras palabras clave de F# estándar solo están disponibles en una expresión de cálculo si se han definido en el tipo de generador de respaldo.</span><span class="sxs-lookup"><span data-stu-id="0280c-129">Each of these keywords, and other standard F# keywords are only available in a computation expression if they have been defined in the backing builder type.</span></span> <span data-ttu-id="0280c-130">La única excepción a esto es `match!`, que es en sí mismo azúcar sintáctica para el uso de `let!` seguida por una coincidencia de patrones en el resultado.</span><span class="sxs-lookup"><span data-stu-id="0280c-130">The only exception to this is `match!`, which is itself syntactic sugar for the use of `let!` followed by a pattern match on the result.</span></span>

<span data-ttu-id="0280c-131">El tipo de generador es un objeto que define los métodos especiales que rigen la manera en que se combinan los fragmentos de la expresión de cálculo; es decir, sus métodos controlan cómo se comporta la expresión de cálculo.</span><span class="sxs-lookup"><span data-stu-id="0280c-131">The builder type is an object that defines special methods that govern the way the fragments of the computation expression are combined; that is, its methods control how the computation expression behaves.</span></span> <span data-ttu-id="0280c-132">Es decir que permite personalizar la operación de muchas construcciones de F#, como bucles y enlaces de otra manera de describir una clase de generador.</span><span class="sxs-lookup"><span data-stu-id="0280c-132">Another way to describe a builder class is to say that it enables you to customize the operation of many F# constructs, such as loops and bindings.</span></span>

### `let!`

<span data-ttu-id="0280c-133">El `let!` palabra clave enlaza el resultado de una llamada a otra expresión de cálculo a un nombre:</span><span class="sxs-lookup"><span data-stu-id="0280c-133">The `let!` keyword binds the result of a call to another computation expression to a name:</span></span>

```fsharp
let doThingsAsync url =
    async {
        let! data = getDataAsync url
        ...
    }
```

<span data-ttu-id="0280c-134">Si enlaza la llamada a una expresión de cálculo con `let`, no obtendrá el resultado de la expresión de cálculo.</span><span class="sxs-lookup"><span data-stu-id="0280c-134">If you bind the call to a computation expression with `let`, you will not get the result of the computation expression.</span></span> <span data-ttu-id="0280c-135">En su lugar, habrá enlazado el valor de la *no realizado* la llamada a esa expresión de cálculo.</span><span class="sxs-lookup"><span data-stu-id="0280c-135">Instead, you will have bound the value of the *unrealized* call to that computation expression.</span></span> <span data-ttu-id="0280c-136">Use `let!` para enlazar con el resultado.</span><span class="sxs-lookup"><span data-stu-id="0280c-136">Use `let!` to bind to the result.</span></span>

<span data-ttu-id="0280c-137">`let!` se define mediante el `Bind(x, f)` miembro en el tipo de generador.</span><span class="sxs-lookup"><span data-stu-id="0280c-137">`let!` is defined by the `Bind(x, f)` member on the builder type.</span></span>

### `do!`

<span data-ttu-id="0280c-138">El `do!` palabra clave es para llamar a una expresión de cálculo que devuelve un `unit`-como tipo (definido por el `Zero` miembro en el generador de):</span><span class="sxs-lookup"><span data-stu-id="0280c-138">The `do!` keyword is for calling a computation expression that returns a `unit`-like type (defined by the `Zero` member on the builder):</span></span>

```fsharp
let doThingsAsync data url =
    async {
        do! submitData data url
        ...
    }
```

<span data-ttu-id="0280c-139">Para el [flujo de trabajo asincrónico](asynchronous-workflows.md), este tipo es `Async<unit>`.</span><span class="sxs-lookup"><span data-stu-id="0280c-139">For the [async workflow](asynchronous-workflows.md), this type is `Async<unit>`.</span></span> <span data-ttu-id="0280c-140">Para otras expresiones de cálculo, es probable que sea el tipo `CExpType<unit>`.</span><span class="sxs-lookup"><span data-stu-id="0280c-140">For other computation expressions, the type is likely to be `CExpType<unit>`.</span></span>

<span data-ttu-id="0280c-141">`do!` se define mediante el `Bind(x, f)` miembro en el tipo de generador donde `f` genera un `unit`.</span><span class="sxs-lookup"><span data-stu-id="0280c-141">`do!` is defined by the `Bind(x, f)` member on the builder type, where `f` produces a `unit`.</span></span>

### `yield`

<span data-ttu-id="0280c-142">El `yield` palabra clave es para devolver un valor de la expresión de cálculo para que se puede consumir como un <xref:System.Collections.Generic.IEnumerable%601>:</span><span class="sxs-lookup"><span data-stu-id="0280c-142">The `yield` keyword is for returning a value from the computation expression so that it can be consumed as an <xref:System.Collections.Generic.IEnumerable%601>:</span></span>

```fsharp
let squares =
    seq {
        for i in 1..10 do
            yield i * i
    }

for sq in squares do
    printfn "%d" sq
```

<span data-ttu-id="0280c-143">Igual que con el [producen la palabra clave en C#](../../csharp/language-reference/keywords/yield.md), cada elemento de la expresión de cálculo se cede a medida que se recorre en iteración.</span><span class="sxs-lookup"><span data-stu-id="0280c-143">As with the [yield keyword in C#](../../csharp/language-reference/keywords/yield.md), each element in the computation expression is yielded back as it is iterated.</span></span>

<span data-ttu-id="0280c-144">`yield` se define mediante el `Yield(x)` miembro en el tipo de generador, donde `x` es el elemento para producir de nuevo.</span><span class="sxs-lookup"><span data-stu-id="0280c-144">`yield` is defined by the `Yield(x)` member on the builder type, where `x` is the item to yield back.</span></span>

### `yield!`

<span data-ttu-id="0280c-145">El `yield!` palabra clave es para acoplar una colección de valores de una expresión de cálculo:</span><span class="sxs-lookup"><span data-stu-id="0280c-145">The `yield!` keyword is for flattening a collection of values from a computation expression:</span></span>

```fsharp
let squares =
    seq {
        for i in 1..3 -> i * i
    }

let cubes =
    seq {
        for i in 1..3 -> i * i * i
    }

let squaresAndCubes =
    seq {
        yield! squares
        yield! cubes
    }

printfn "%A" squaresAndCubes // Prints - 1; 4; 9; 1; 8; 27
```

<span data-ttu-id="0280c-146">Cuando se evalúa, llama la expresión de cálculo `yield!` habrá sus elementos produjo espera uno por uno, acoplar el resultado.</span><span class="sxs-lookup"><span data-stu-id="0280c-146">When evaluated, the computation expression called by `yield!` will have its items yielded back one-by-one, flattening the result.</span></span>

<span data-ttu-id="0280c-147">`yield!` se define mediante el `YieldFrom(x)` miembro en el tipo de generador, donde `x` es una colección de valores.</span><span class="sxs-lookup"><span data-stu-id="0280c-147">`yield!` is defined by the `YieldFrom(x)` member on the builder type, where `x` is a collection of values.</span></span>

### `return`

<span data-ttu-id="0280c-148">El `return` palabra clave incluye un valor en el tipo correspondiente a la expresión de cálculo.</span><span class="sxs-lookup"><span data-stu-id="0280c-148">The `return` keyword wraps a value in the type corresponding to the computation expression.</span></span> <span data-ttu-id="0280c-149">Aparte de las expresiones de cálculo mediante `yield`, se usa para "completar" una expresión de cálculo:</span><span class="sxs-lookup"><span data-stu-id="0280c-149">Aside from computation expressions using `yield`, it is used to "complete" a computation expression:</span></span>

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        let! data = fetch url
        return data
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

<span data-ttu-id="0280c-150">`return` se define mediante el `Return(x)` miembro en el tipo de generador, donde `x` es el elemento que se va a ajustar.</span><span class="sxs-lookup"><span data-stu-id="0280c-150">`return` is defined by the `Return(x)` member on the builder type, where `x` is the item to wrap.</span></span>

### `return!`

<span data-ttu-id="0280c-151">El `return!` palabra clave, el valor de una expresión de cálculo de realización y ajusta ese resultado en el tipo correspondiente a la expresión de cálculo:</span><span class="sxs-lookup"><span data-stu-id="0280c-151">The `return!` keyword realizes the value of a computation expression and wraps that result in the type corresponding to the computation expression:</span></span>

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        return! fetch url
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

<span data-ttu-id="0280c-152">`return!` se define mediante el `ReturnFrom(x)` miembro en el tipo de generador, donde `x` es otra expresión de cálculo.</span><span class="sxs-lookup"><span data-stu-id="0280c-152">`return!` is defined by the `ReturnFrom(x)` member on the builder type, where `x` is another computation expression.</span></span>

### `match!`

<span data-ttu-id="0280c-153">A partir de F# 4.5, el `match!` palabra clave permite a en línea una llamada a otra coincidencia de expresión y el patrón de cálculo con su resultado:</span><span class="sxs-lookup"><span data-stu-id="0280c-153">Starting with F# 4.5, the `match!` keyword allows you to inline a call to another computation expression and pattern match on its result:</span></span>

```fsharp
let doThingsAsync url =
    async {
        match! callService url with
        | Some data -> ...
        | None -> ...
    }
```

<span data-ttu-id="0280c-154">Al llamar a una expresión de cálculo con `match!`, obtendrá el resultado de la llamada como `let!`.</span><span class="sxs-lookup"><span data-stu-id="0280c-154">When calling a computation expression with `match!`, it will realize the result of the call like `let!`.</span></span> <span data-ttu-id="0280c-155">Esto se suele usar cuando se llama a una expresión de cálculo donde el resultado es un [opcional](options.md).</span><span class="sxs-lookup"><span data-stu-id="0280c-155">This is often used when calling a computation expression where the result is an [optional](options.md).</span></span>

## <a name="built-in-computation-expressions"></a><span data-ttu-id="0280c-156">Expresiones de cálculo integradas</span><span class="sxs-lookup"><span data-stu-id="0280c-156">Built-in computation expressions</span></span>

<span data-ttu-id="0280c-157">La biblioteca básica de F# define tres expresiones de cálculo integradas: [las expresiones de secuencia](sequences.md), [flujos de trabajo asincrónicos](asynchronous-workflows.md), y [las expresiones de consulta](query-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="0280c-157">The F# core library defines three built-in computation expressions: [Sequence Expressions](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Query Expressions](query-expressions.md).</span></span>

## <a name="creating-a-new-type-of-computation-expression"></a><span data-ttu-id="0280c-158">Crear un nuevo tipo de expresión de cálculo</span><span class="sxs-lookup"><span data-stu-id="0280c-158">Creating a New Type of Computation Expression</span></span>

<span data-ttu-id="0280c-159">Puede definir las características de sus propias expresiones de cálculo mediante la creación de una clase de generador y define algunos métodos especiales en la clase.</span><span class="sxs-lookup"><span data-stu-id="0280c-159">You can define the characteristics of your own computation expressions by creating a builder class and defining certain special methods on the class.</span></span> <span data-ttu-id="0280c-160">La clase de generador, opcionalmente, puede definir los métodos, como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="0280c-160">The builder class can optionally define the methods as listed in the following table.</span></span>

<span data-ttu-id="0280c-161">En la tabla siguiente se describe los métodos que pueden usarse en una clase de generador de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0280c-161">The following table describes methods that can be used in a workflow builder class.</span></span>

|<span data-ttu-id="0280c-162">**Método**</span><span class="sxs-lookup"><span data-stu-id="0280c-162">**Method**</span></span>|<span data-ttu-id="0280c-163">**Signaturas típicas**</span><span class="sxs-lookup"><span data-stu-id="0280c-163">**Typical signature(s)**</span></span>|<span data-ttu-id="0280c-164">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="0280c-164">**Description**</span></span>|
|----|----|----|
|`Bind`|`M<'T> * ('T -> M<'U>) -> M<'U>`|<span data-ttu-id="0280c-165">Llamado para `let!` y `do!` en expresiones de cálculo.</span><span class="sxs-lookup"><span data-stu-id="0280c-165">Called for `let!` and `do!` in computation expressions.</span></span>|
|`Delay`|`(unit -> M<'T>) -> M<'T>`|<span data-ttu-id="0280c-166">Contiene una expresión de cálculo como una función.</span><span class="sxs-lookup"><span data-stu-id="0280c-166">Wraps a computation expression as a function.</span></span>|
|`Return`|`'T -> M<'T>`|<span data-ttu-id="0280c-167">Llamado para `return` en expresiones de cálculo.</span><span class="sxs-lookup"><span data-stu-id="0280c-167">Called for `return` in computation expressions.</span></span>|
|`ReturnFrom`|`M<'T> -> M<'T>`|<span data-ttu-id="0280c-168">Llamado para `return!` en expresiones de cálculo.</span><span class="sxs-lookup"><span data-stu-id="0280c-168">Called for `return!` in computation expressions.</span></span>|
|`Run`|<span data-ttu-id="0280c-169">`M<'T> -> M<'T>`, o bien</span><span class="sxs-lookup"><span data-stu-id="0280c-169">`M<'T> -> M<'T>` or</span></span><br /><br />`M<'T> -> 'T`|<span data-ttu-id="0280c-170">Ejecuta una expresión de cálculo.</span><span class="sxs-lookup"><span data-stu-id="0280c-170">Executes a computation expression.</span></span>|
|`Combine`|<span data-ttu-id="0280c-171">`M<'T> * M<'T> -> M<'T>`, o bien</span><span class="sxs-lookup"><span data-stu-id="0280c-171">`M<'T> * M<'T> -> M<'T>` or</span></span><br /><br />`M<unit> * M<'T> -> M<'T>`|<span data-ttu-id="0280c-172">Se llama para la secuenciación en expresiones de cálculo.</span><span class="sxs-lookup"><span data-stu-id="0280c-172">Called for sequencing in computation expressions.</span></span>|
|`For`|<span data-ttu-id="0280c-173">`seq<'T> * ('T -> M<'U>) -> M<'U>`, o bien</span><span class="sxs-lookup"><span data-stu-id="0280c-173">`seq<'T> * ('T -> M<'U>) -> M<'U>` or</span></span><br /><br />`seq<'T> * ('T -> M<'U>) -> seq<M<'U>>`|<span data-ttu-id="0280c-174">Llamado para `for...do` expresiones en expresiones de cálculo.</span><span class="sxs-lookup"><span data-stu-id="0280c-174">Called for `for...do` expressions in computation expressions.</span></span>|
|`TryFinally`|`M<'T> * (unit -> unit) -> M<'T>`|<span data-ttu-id="0280c-175">Llamado para `try...finally` expresiones en expresiones de cálculo.</span><span class="sxs-lookup"><span data-stu-id="0280c-175">Called for `try...finally` expressions in computation expressions.</span></span>|
|`TryWith`|`M<'T> * (exn -> M<'T>) -> M<'T>`|<span data-ttu-id="0280c-176">Llamado para `try...with` expresiones en expresiones de cálculo.</span><span class="sxs-lookup"><span data-stu-id="0280c-176">Called for `try...with` expressions in computation expressions.</span></span>|
|`Using`|`'T * ('T -> M<'U>) -> M<'U> when 'U :> IDisposable`|<span data-ttu-id="0280c-177">Llamado para `use` enlaces en expresiones de cálculo.</span><span class="sxs-lookup"><span data-stu-id="0280c-177">Called for `use` bindings in computation expressions.</span></span>|
|`While`|`(unit -> bool) * M<'T> -> M<'T>`|<span data-ttu-id="0280c-178">Llamado para `while...do` expresiones en expresiones de cálculo.</span><span class="sxs-lookup"><span data-stu-id="0280c-178">Called for `while...do` expressions in computation expressions.</span></span>|
|`Yield`|`'T -> M<'T>`|<span data-ttu-id="0280c-179">Llamado para `yield` expresiones en expresiones de cálculo.</span><span class="sxs-lookup"><span data-stu-id="0280c-179">Called for `yield` expressions in computation expressions.</span></span>|
|`YieldFrom`|`M<'T> -> M<'T>`|<span data-ttu-id="0280c-180">Llamado para `yield!` expresiones en expresiones de cálculo.</span><span class="sxs-lookup"><span data-stu-id="0280c-180">Called for `yield!` expressions in computation expressions.</span></span>|
|`Zero`|`unit -> M<'T>`|<span data-ttu-id="0280c-181">Llamado para vacío `else` ramas de `if...then` expresiones en expresiones de cálculo.</span><span class="sxs-lookup"><span data-stu-id="0280c-181">Called for empty `else` branches of `if...then` expressions in computation expressions.</span></span>|

<span data-ttu-id="0280c-182">Muchos de los métodos en una clase de generador usan y devuelven un `M<'T>` construcción, que normalmente es un tipo definido por separado que caracteriza el tipo de cálculos que se va a combinar, por ejemplo, `Async<'T>` para flujos de trabajo asincrónicos y `Seq<'T>` para los flujos de trabajo de secuencia.</span><span class="sxs-lookup"><span data-stu-id="0280c-182">Many of the methods in a builder class use and return an `M<'T>` construct, which is typically a separately defined type that characterizes the kind of computations being combined, for example, `Async<'T>` for asynchronous workflows and `Seq<'T>` for sequence workflows.</span></span> <span data-ttu-id="0280c-183">Las firmas de estos métodos que puedan combinarse y anidarse entre sí, para que el objeto de flujo de trabajo devuelto por una construcción puede pasarse a la siguiente.</span><span class="sxs-lookup"><span data-stu-id="0280c-183">The signatures of these methods enable them to be combined and nested with each other, so that the workflow object returned from one construct can be passed to the next.</span></span> <span data-ttu-id="0280c-184">El compilador, cuando analiza una expresión de cálculo, convierte la expresión en una serie de llamadas de función anidada utilizando los métodos en la tabla anterior y el código de la expresión de cálculo.</span><span class="sxs-lookup"><span data-stu-id="0280c-184">The compiler, when it parses a computation expression, converts the expression into a series of nested function calls by using the methods in the preceding table and the code in the computation expression.</span></span>

<span data-ttu-id="0280c-185">La expresión anidada tiene el formato siguiente:</span><span class="sxs-lookup"><span data-stu-id="0280c-185">The nested expression is of the following form:</span></span>

```fsharp
builder.Run(builder.Delay(fun () -> {| cexpr |}))
```

<span data-ttu-id="0280c-186">En el código anterior, las llamadas a `Run` y `Delay` se omite si no están definidos en la clase de generador de expresiones de cálculo.</span><span class="sxs-lookup"><span data-stu-id="0280c-186">In the above code, the calls to `Run` and `Delay` are omitted if they are not defined in the computation expression builder class.</span></span> <span data-ttu-id="0280c-187">El cuerpo de la expresión de cálculo, aquí se indica como `{| cexpr |}`, se convierten en llamadas que implican los métodos de la clase de generador por las traducciones se describe en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="0280c-187">The body of the computation expression, here denoted as `{| cexpr |}`, is translated into calls involving the methods of the builder class by the translations described in the following table.</span></span> <span data-ttu-id="0280c-188">La expresión de cálculo `{| cexpr |}` está definido de forma recursiva según estas traducciones donde `expr` es una expresión de F# y `cexpr` es una expresión de cálculo.</span><span class="sxs-lookup"><span data-stu-id="0280c-188">The computation expression `{| cexpr |}` is defined recursively according to these translations where `expr` is an F# expression and `cexpr` is a computation expression.</span></span>

|<span data-ttu-id="0280c-189">Expresión</span><span class="sxs-lookup"><span data-stu-id="0280c-189">Expression</span></span>|<span data-ttu-id="0280c-190">Conversión</span><span class="sxs-lookup"><span data-stu-id="0280c-190">Translation</span></span>|
|----------|-----------|
|<code>{&#124; let binding in cexpr &#124;}</code>|<code>let binding in {&#124; cexpr &#124;}</code>|
|<code>{&#124; let! pattern = expr in cexpr &#124;}</code>|<code>builder.Bind(expr, (fun pattern -> {&#124; cexpr &#124;}))</code>|
|<code>{&#124; do! expr in cexpr &#124;}</code>|<code>builder.Bind(expr, (fun () -> {&#124; cexpr &#124;}))</code>|
|<code>{&#124; yield expr &#124;}</code>|`builder.Yield(expr)`|
|<code>{&#124; yield! expr &#124;}</code>|`builder.YieldFrom(expr)`|
|<code>{&#124; return expr &#124;}</code>|`builder.Return(expr)`|
|<code>{&#124; return! expr &#124;}</code>|`builder.ReturnFrom(expr)`|
|<code>{&#124; use pattern = expr in cexpr &#124;}</code>|<code>builder.Using(expr, (fun pattern -> {&#124; cexpr &#124;}))</code>|
|<code>{&#124; use! value = expr in cexpr &#124;}</code>|<code>builder.Bind(expr, (fun value -> builder.Using(value, (fun value -> {&#124; cexpr &#124;}))))</code>|
|<code>{&#124; if expr then cexpr0 &#124;}</code>|<code>if expr then {&#124; cexpr0 &#124;} else binder.Zero()</code>|
|<code>{&#124; if expr then cexpr0 else cexpr1 &#124;}</code>|<code>if expr then {&#124; cexpr0 &#124;} else {&#124; cexpr1 &#124;}</code>|
|<code>{&#124; match expr with &#124; pattern_i -> cexpr_i &#124;}</code>|<code>match expr with &#124; pattern_i -> {&#124; cexpr_i &#124;}</code>|
|<code>{&#124; for pattern in expr do cexpr &#124;}</code>|<code>builder.For(enumeration, (fun pattern -> {&#124; cexpr &#124;}))</code>|
|<code>{&#124; for identifier = expr1 to expr2 do cexpr &#124;}</code>|<code>builder.For(enumeration, (fun identifier -> {&#124; cexpr &#124;}))</code>|
|<code>{&#124; while expr do cexpr &#124;}</code>|<code>builder.While(fun () -> expr), builder.Delay({&#124;cexpr &#124;})</code>|
|<code>{&#124; try cexpr with &#124; pattern_i -> expr_i &#124;}</code>|<code>builder.TryWith(builder.Delay({&#124; cexpr &#124;}), (fun value -> match value with &#124; pattern_i -> expr_i &#124; exn -> reraise exn)))</code>|
|<code>{&#124; try cexpr finally expr &#124;}</code>|<code>builder.TryFinally(builder.Delay( {&#124; cexpr &#124;}), (fun () -> expr))</code>|
|<code>{&#124; cexpr1; cexpr2 &#124;}</code>|<code>builder.Combine({&#124;cexpr1 &#124;}, {&#124; cexpr2 &#124;})</code>|
|<code>{&#124; other-expr; cexpr &#124;}</code>|<code>expr; {&#124; cexpr &#124;}</code>|
|<code>{&#124; other-expr &#124;}</code>|`expr; builder.Zero()`|
<span data-ttu-id="0280c-191">En la tabla anterior, `other-expr` describe una expresión que en caso contrario, no se muestra en la tabla.</span><span class="sxs-lookup"><span data-stu-id="0280c-191">In the previous table, `other-expr` describes an expression that is not otherwise listed in the table.</span></span> <span data-ttu-id="0280c-192">Una clase de generador no es necesario implementar todos los métodos y admite todas las traducciones que se muestran en la tabla anterior.</span><span class="sxs-lookup"><span data-stu-id="0280c-192">A builder class does not need to implement all of the methods and support all of the translations listed in the previous table.</span></span> <span data-ttu-id="0280c-193">Las construcciones que no se implementan no están disponibles en las expresiones de cálculo de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="0280c-193">Those constructs that are not implemented are not available in computation expressions of that type.</span></span> <span data-ttu-id="0280c-194">Por ejemplo, si no desea admitir la `use` palabra clave en las expresiones de cálculo, puede omitir la definición de `Use` en la clase de generador.</span><span class="sxs-lookup"><span data-stu-id="0280c-194">For example, if you do not want to support the `use` keyword in your computation expressions, you can omit the definition of `Use` in your builder class.</span></span>

<span data-ttu-id="0280c-195">El ejemplo de código siguiente muestra una expresión de cálculo que encapsula un cálculo con una serie de pasos que se puede evaluar un paso a la vez.</span><span class="sxs-lookup"><span data-stu-id="0280c-195">The following code example shows a computation expression that encapsulates a computation as a series of steps that can be evaluated one step at a time.</span></span> <span data-ttu-id="0280c-196">Un tipo de unión, de discriminadas `OkOrException`, codifica el estado de error de la expresión evalúa hasta ahora.</span><span class="sxs-lookup"><span data-stu-id="0280c-196">A discriminated union type, `OkOrException`, encodes the error state of the expression as evaluated so far.</span></span> <span data-ttu-id="0280c-197">Este código muestra varios patrones típicos que puede usar en las expresiones de cálculo, como son implementaciones reutilizables de algunos de los métodos del generador.</span><span class="sxs-lookup"><span data-stu-id="0280c-197">This code demonstrates several typical patterns that you can use in your computation expressions, such as boilerplate implementations of some of the builder methods.</span></span>

```fsharp
// Computations that can be run step by step
type Eventually<'T> =
    | Done of 'T
    | NotYetDone of (unit -> Eventually<'T>)

module Eventually =
    // The bind for the computations. Append 'func' to the
    // computation.
    let rec bind func expr =
        match expr with
        | Done value -> NotYetDone (fun () -> func value)
        | NotYetDone work -> NotYetDone (fun () -> bind func (work()))

    // Return the final value wrapped in the Eventually type.
    let result value = Done value

    type OkOrException<'T> =
        | Ok of 'T
        | Exception of System.Exception

    // The catch for the computations. Stitch try/with throughout
    // the computation, and return the overall result as an OkOrException.
    let rec catch expr =
        match expr with
        | Done value -> result (Ok value)
        | NotYetDone work ->
            NotYetDone (fun () ->
                let res = try Ok(work()) with | exn -> Exception exn
                match res with
                | Ok cont -> catch cont // note, a tailcall
                | Exception exn -> result (Exception exn))

    // The delay operator.
    let delay func = NotYetDone (fun () -> func())

    // The stepping action for the computations.
    let step expr =
        match expr with
        | Done _ -> expr
        | NotYetDone func -> func ()

    // The rest of the operations are boilerplate.
    // The tryFinally operator.
    // This is boilerplate in terms of "result", "catch", and "bind".
    let tryFinally expr compensation =
        catch (expr)
        |> bind (fun res -> 
            compensation();
            match res with
            | Ok value -> result value
            | Exception exn -> raise exn)

    // The tryWith operator.
    // This is boilerplate in terms of "result", "catch", and "bind".
    let tryWith exn handler =
        catch exn
        |> bind (function Ok value -> result value | Exception exn -> handler exn)

    // The whileLoop operator.
    // This is boilerplate in terms of "result" and "bind".
    let rec whileLoop pred body =
        if pred() then body |> bind (fun _ -> whileLoop pred body)
        else result ()

    // The sequential composition operator.
    // This is boilerplate in terms of "result" and "bind".
    let combine expr1 expr2 =
        expr1 |> bind (fun () -> expr2)

    // The using operator.
    let using (resource: #System.IDisposable) func =
        tryFinally (func resource) (fun () -> resource.Dispose())

    // The forLoop operator.
    // This is boilerplate in terms of "catch", "result", and "bind".
    let forLoop (collection:seq<_>) func =
        let ie = collection.GetEnumerator()
        tryFinally 
            (whileLoop 
                (fun () -> ie.MoveNext()) 
                (delay (fun () -> let value = ie.Current in func value)))
            (fun () -> ie.Dispose())

// The builder class.
type EventuallyBuilder() =
    member x.Bind(comp, func) = Eventually.bind func comp
    member x.Return(value) = Eventually.result value
    member x.ReturnFrom(value) = value
    member x.Combine(expr1, expr2) = Eventually.combine expr1 expr2
    member x.Delay(func) = Eventually.delay func
    member x.Zero() = Eventually.result ()
    member x.TryWith(expr, handler) = Eventually.tryWith expr handler
    member x.TryFinally(expr, compensation) = Eventually.tryFinally expr compensation
    member x.For(coll:seq<_>, func) = Eventually.forLoop coll func
    member x.Using(resource, expr) = Eventually.using resource expr

let eventually = new EventuallyBuilder()

let comp = eventually {
    for x in 1..2 do
        printfn " x = %d" x
    return 3 + 4 }

// Try the remaining lines in F# interactive to see how this
// computation expression works in practice.
let step x = Eventually.step x

// returns "NotYetDone <closure>"
comp |> step

// prints "x = 1"
// returns "NotYetDone <closure>"
comp |> step |> step

// prints "x = 1"
// prints "x = 2"
// returns "NotYetDone <closure>"
comp |> step |> step |> step |> step |> step |> step

// prints "x = 1"
// prints "x = 2"
// returns "Done 7"
comp |> step |> step |> step |> step |> step |> step |> step |> step
```

<span data-ttu-id="0280c-198">Una expresión de cálculo tiene un tipo subyacente, que devuelve la expresión.</span><span class="sxs-lookup"><span data-stu-id="0280c-198">A computation expression has an underlying type, which the expression returns.</span></span> <span data-ttu-id="0280c-199">El tipo subyacente puede representar un resultado calculado o un cálculo diferido que se puede realizar, o puede proporcionar una manera de recorrer en iteración a través de algún tipo de colección.</span><span class="sxs-lookup"><span data-stu-id="0280c-199">The underlying type may represent a computed result or a delayed computation that can be performed, or it may provide a way to iterate through some type of collection.</span></span> <span data-ttu-id="0280c-200">En el ejemplo anterior, el tipo subyacente era **finalmente**.</span><span class="sxs-lookup"><span data-stu-id="0280c-200">In the previous example, the underlying type was **Eventually**.</span></span> <span data-ttu-id="0280c-201">Una expresión de secuencia, el tipo subyacente es <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0280c-201">For a sequence expression, the underlying type is <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.</span></span> <span data-ttu-id="0280c-202">Una expresión de consulta, el tipo subyacente es <xref:System.Linq.IQueryable?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0280c-202">For a query expression, the underlying type is <xref:System.Linq.IQueryable?displayProperty=nameWithType>.</span></span> <span data-ttu-id="0280c-203">Para un flujo de trabajo asincrónico, el tipo subyacente es [ `Async` ](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7).</span><span class="sxs-lookup"><span data-stu-id="0280c-203">For an asynchronous workflow, the underlying type is [`Async`](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7).</span></span> <span data-ttu-id="0280c-204">La `Async` objeto representa el trabajo que se realizará para calcular el resultado.</span><span class="sxs-lookup"><span data-stu-id="0280c-204">The `Async` object represents the work to be performed to compute the result.</span></span> <span data-ttu-id="0280c-205">Por ejemplo, se llama [ `Async.RunSynchronously` ](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) para ejecutar un cálculo y devolver el resultado.</span><span class="sxs-lookup"><span data-stu-id="0280c-205">For example, you call [`Async.RunSynchronously`](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) to execute a computation and return the result.</span></span>

## <a name="custom-operations"></a><span data-ttu-id="0280c-206">Operaciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="0280c-206">Custom Operations</span></span>

<span data-ttu-id="0280c-207">Puede definir una operación personalizada en una expresión de cálculo y utilizar una operación personalizada como un operador en una expresión de cálculo.</span><span class="sxs-lookup"><span data-stu-id="0280c-207">You can define a custom operation on a computation expression and use a custom operation as an operator in a computation expression.</span></span> <span data-ttu-id="0280c-208">Por ejemplo, puede incluir un operador de consulta en una expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="0280c-208">For example, you can include a query operator in a query expression.</span></span> <span data-ttu-id="0280c-209">Al definir una operación personalizada, debe definir el rendimiento y para los métodos en la expresión de cálculo.</span><span class="sxs-lookup"><span data-stu-id="0280c-209">When you define a custom operation, you must define the Yield and For methods in the computation expression.</span></span> <span data-ttu-id="0280c-210">Para definir una operación personalizada, colocarlo en una clase de generador para la expresión de cálculo y, a continuación, aplique el [ `CustomOperationAttribute` ](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19).</span><span class="sxs-lookup"><span data-stu-id="0280c-210">To define a custom operation, put it in a builder class for the computation expression, and then apply the [`CustomOperationAttribute`](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19).</span></span> <span data-ttu-id="0280c-211">Este atributo toma una cadena como argumento, que es el nombre que se usará en una operación personalizada.</span><span class="sxs-lookup"><span data-stu-id="0280c-211">This attribute takes a string as an argument, which is the name to be used in a custom operation.</span></span> <span data-ttu-id="0280c-212">Este nombre entra en el ámbito del principio de la llave de apertura de la expresión de cálculo.</span><span class="sxs-lookup"><span data-stu-id="0280c-212">This name comes into scope at the start of the opening curly brace of the computation expression.</span></span> <span data-ttu-id="0280c-213">Por lo tanto, no debería utilizar identificadores que tienen el mismo nombre que una operación personalizada de este bloque.</span><span class="sxs-lookup"><span data-stu-id="0280c-213">Therefore, you shouldn’t use identifiers that have the same name as a custom operation in this block.</span></span> <span data-ttu-id="0280c-214">Por ejemplo, evite el uso de identificadores como `all` o `last` en expresiones de consulta.</span><span class="sxs-lookup"><span data-stu-id="0280c-214">For example, avoid the use of identifiers such as `all` or `last` in query expressions.</span></span>

### <a name="extending-existing-builders-with-new-custom-operations"></a><span data-ttu-id="0280c-215">Extender los generadores de existentes con nuevas operaciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="0280c-215">Extending existing Builders with new Custom Operations</span></span>

<span data-ttu-id="0280c-216">Si ya tiene una clase de generador, se pueden ampliar sus operaciones personalizadas desde fuera de esta clase de generador.</span><span class="sxs-lookup"><span data-stu-id="0280c-216">If you already have a builder class, its custom operations can be extended from outside of this builder class.</span></span> <span data-ttu-id="0280c-217">Las extensiones se deben declarar en módulos.</span><span class="sxs-lookup"><span data-stu-id="0280c-217">Extensions must be declared in modules.</span></span> <span data-ttu-id="0280c-218">Los espacios de nombres no pueden contener a miembros de extensión, excepto en el mismo archivo y el mismo grupo de declaración de espacio de nombres donde se define el tipo.</span><span class="sxs-lookup"><span data-stu-id="0280c-218">Namespaces cannot contain extension members except in the same file and the same namespace declaration group where the type is defined.</span></span>

<span data-ttu-id="0280c-219">El ejemplo siguiente muestra la extensión de la existente `Microsoft.FSharp.Linq.QueryBuilder` clase.</span><span class="sxs-lookup"><span data-stu-id="0280c-219">The following example shows the extension of the existing `Microsoft.FSharp.Linq.QueryBuilder` class.</span></span>

```fsharp
type Microsoft.FSharp.Linq.QueryBuilder with

    [<CustomOperation("existsNot")>]
    member __.ExistsNot (source: QuerySource<'T, 'Q>, predicate) =
        Enumerable.Any (source.Source, Func<_,_>(predicate)) |> not
```

## <a name="see-also"></a><span data-ttu-id="0280c-220">Vea también</span><span class="sxs-lookup"><span data-stu-id="0280c-220">See also</span></span>

- [<span data-ttu-id="0280c-221">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="0280c-221">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="0280c-222">Flujos de trabajo asincrónicos</span><span class="sxs-lookup"><span data-stu-id="0280c-222">Asynchronous Workflows</span></span>](asynchronous-workflows.md)
- [<span data-ttu-id="0280c-223">Secuencias</span><span class="sxs-lookup"><span data-stu-id="0280c-223">Sequences</span></span>](https://msdn.microsoft.com/library/6b773b6b-9c9a-4af8-bd9e-d96585c166db)
- [<span data-ttu-id="0280c-224">Expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="0280c-224">Query Expressions</span></span>](query-expressions.md)
