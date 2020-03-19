---
title: Expresiones de cálculo
description: Obtenga información sobre cómo crear una sintaxis conveniente para escribir cálculos en F- que se pueden secuenciar y combinar mediante construcciones de flujo de control y enlaces.
ms.date: 11/04/2019
ms.openlocfilehash: 55406cc12d9e6e890fe69d712f79486d23b84452
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401086"
---
# <a name="computation-expressions"></a><span data-ttu-id="3cc6a-103">Expresiones de cálculo</span><span class="sxs-lookup"><span data-stu-id="3cc6a-103">Computation Expressions</span></span>

<span data-ttu-id="3cc6a-104">Las expresiones de cálculo en F- proporcionan una sintaxis conveniente para escribir cálculos que se pueden secuenciar y combinar mediante construcciones de flujo de control y enlaces.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-104">Computation expressions in F# provide a convenient syntax for writing computations that can be sequenced and combined using control flow constructs and bindings.</span></span> <span data-ttu-id="3cc6a-105">Dependiendo del tipo de expresión de cálculo, se pueden considerar como una forma de expresar monads, monoides, transformadores de monad y functores aplicativos.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-105">Depending on the kind of computation expression, they can be thought of as a way to express monads, monoids, monad transformers, and applicative functors.</span></span> <span data-ttu-id="3cc6a-106">Sin embargo, a diferencia de otros lenguajes (como la notación de *doente* en Haskell), no están vinculados a una sola abstracción y no se basan en macros u otras formas de metaprogramación para lograr una sintaxis conveniente y sensible al contexto.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-106">However, unlike other languages (such as *do-notation* in Haskell), they are not tied to a single abstraction, and do not rely on macros or other forms of metaprogramming to accomplish a convenient and context-sensitive syntax.</span></span>

## <a name="overview"></a><span data-ttu-id="3cc6a-107">Información general</span><span class="sxs-lookup"><span data-stu-id="3cc6a-107">Overview</span></span>

<span data-ttu-id="3cc6a-108">Los cálculos pueden tomar muchas formas.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-108">Computations can take many forms.</span></span> <span data-ttu-id="3cc6a-109">La forma más común de cálculo es la ejecución de un solo subproceso, que es fácil de entender y modificar.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-109">The most common form of computation is single-threaded execution, which is easy to understand and modify.</span></span> <span data-ttu-id="3cc6a-110">Sin embargo, no todas las formas de cálculo son tan sencillas como la ejecución de un solo subproceso.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-110">However, not all forms of computation are as straightforward as single-threaded execution.</span></span> <span data-ttu-id="3cc6a-111">Estos son algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="3cc6a-111">Some examples include:</span></span>

- <span data-ttu-id="3cc6a-112">Cálculos no deterministas</span><span class="sxs-lookup"><span data-stu-id="3cc6a-112">Non-deterministic computations</span></span>
- <span data-ttu-id="3cc6a-113">Cálculos asincrónicos</span><span class="sxs-lookup"><span data-stu-id="3cc6a-113">Asynchronous computations</span></span>
- <span data-ttu-id="3cc6a-114">Cálculos eficaces</span><span class="sxs-lookup"><span data-stu-id="3cc6a-114">Effectful computations</span></span>
- <span data-ttu-id="3cc6a-115">Cálculos generativos</span><span class="sxs-lookup"><span data-stu-id="3cc6a-115">Generative computations</span></span>

<span data-ttu-id="3cc6a-116">De forma más general, hay cálculos *contextuales* que debe realizar en determinadas partes de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-116">More generally, there are *context-sensitive* computations that you must perform in certain parts of an application.</span></span> <span data-ttu-id="3cc6a-117">Escribir código sensible al contexto puede ser difícil, ya que es fácil "filtrar" cálculos fuera de un contexto determinado sin abstracciones para evitar que lo haga.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-117">Writing context-sensitive code can be challenging, as it is easy to "leak" computations outside of a given context without abstractions to prevent you from doing so.</span></span> <span data-ttu-id="3cc6a-118">Estas abstracciones a menudo son difíciles de escribir por sí mismo, razón por la cual F tiene una forma generalizada de hacerlo **llamadas expresiones**de cálculo.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-118">These abstractions are often challenging to write by yourself, which is why F# has a generalized way to do so called **computation expressions**.</span></span>

<span data-ttu-id="3cc6a-119">Las expresiones de cálculo ofrecen un modelo uniforme de sintaxis y abstracción para codificar cálculos contextuales.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-119">Computation expressions offer a uniform syntax and abstraction model for encoding context-sensitive computations.</span></span>

<span data-ttu-id="3cc6a-120">Cada expresión de cálculo está respaldada por un tipo *de generador.*</span><span class="sxs-lookup"><span data-stu-id="3cc6a-120">Every computation expression is backed by a *builder* type.</span></span> <span data-ttu-id="3cc6a-121">El tipo de generador define las operaciones que están disponibles para la expresión de cálculo.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-121">The builder type defines the operations that are available for the computation expression.</span></span> <span data-ttu-id="3cc6a-122">Consulte Creación de [un nuevo tipo de expresión de cálculo](computation-expressions.md#creating-a-new-type-of-computation-expression), que muestra cómo crear una expresión de cálculo personalizada.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-122">See [Creating a New Type of Computation Expression](computation-expressions.md#creating-a-new-type-of-computation-expression), which shows how to create a custom computation expression.</span></span>

### <a name="syntax-overview"></a><span data-ttu-id="3cc6a-123">Información general sobre la sintaxis</span><span class="sxs-lookup"><span data-stu-id="3cc6a-123">Syntax overview</span></span>

<span data-ttu-id="3cc6a-124">Todas las expresiones de cálculo tienen la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="3cc6a-124">All computation expressions have the following form:</span></span>

```fsharp
builder-expr { cexper }
```

<span data-ttu-id="3cc6a-125">donde `builder-expr` es el nombre de un tipo de `cexper` generador que define la expresión de cálculo y es el cuerpo de expresión de la expresión de cálculo.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-125">where `builder-expr` is the name of a builder type that defines the computation expression, and `cexper` is the expression body of the computation expression.</span></span> <span data-ttu-id="3cc6a-126">Por ejemplo, `async` el código de expresión de cálculo puede tener este aspecto:</span><span class="sxs-lookup"><span data-stu-id="3cc6a-126">For example, `async` computation expression code can look like this:</span></span>

```fsharp
let fetchAndDownload url =
    async {
        let! data = downloadData url

        let processedData = processData data

        return processedData
    }
```

<span data-ttu-id="3cc6a-127">Hay una sintaxis especial y adicional disponible dentro de una expresión de cálculo, como se muestra en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-127">There is a special, additional syntax available within a computation expression, as shown in the previous example.</span></span> <span data-ttu-id="3cc6a-128">Los siguientes formularios de expresión son posibles con expresiones de cálculo:</span><span class="sxs-lookup"><span data-stu-id="3cc6a-128">The following expression forms are possible with computation expressions:</span></span>

```fsharp
expr { let! ... }
expr { do! ... }
expr { yield ... }
expr { yield! ... }
expr { return ... }
expr { return! ... }
expr { match! ... }
```

<span data-ttu-id="3cc6a-129">Cada una de estas palabras clave y otras palabras clave estándar de F- solo están disponibles en una expresión de cálculo si se han definido en el tipo de generador de respaldo.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-129">Each of these keywords, and other standard F# keywords are only available in a computation expression if they have been defined in the backing builder type.</span></span> <span data-ttu-id="3cc6a-130">La única excepción `match!`a esto es , que es `let!` en sí mismo azúcar sintáctico para el uso de seguido de una coincidencia de patrón en el resultado.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-130">The only exception to this is `match!`, which is itself syntactic sugar for the use of `let!` followed by a pattern match on the result.</span></span>

<span data-ttu-id="3cc6a-131">El tipo de generador es un objeto que define métodos especiales que rigen la forma en que se combinan los fragmentos de la expresión de cálculo; es decir, sus métodos controlan cómo se comporta la expresión de cálculo.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-131">The builder type is an object that defines special methods that govern the way the fragments of the computation expression are combined; that is, its methods control how the computation expression behaves.</span></span> <span data-ttu-id="3cc6a-132">Otra forma de describir una clase de generador es decir que permite personalizar el funcionamiento de muchas construcciones de F, como bucles y enlaces.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-132">Another way to describe a builder class is to say that it enables you to customize the operation of many F# constructs, such as loops and bindings.</span></span>

### `let!`

<span data-ttu-id="3cc6a-133">La `let!` palabra clave enlaza el resultado de una llamada a otra expresión de cálculo a un nombre:</span><span class="sxs-lookup"><span data-stu-id="3cc6a-133">The `let!` keyword binds the result of a call to another computation expression to a name:</span></span>

```fsharp
let doThingsAsync url =
    async {
        let! data = getDataAsync url
        ...
    }
```

<span data-ttu-id="3cc6a-134">Si enlaza la llamada a `let`una expresión de cálculo con , no obtendrá el resultado de la expresión de cálculo.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-134">If you bind the call to a computation expression with `let`, you will not get the result of the computation expression.</span></span> <span data-ttu-id="3cc6a-135">En su lugar, habrá enlazado el valor de la llamada *no realizada* a esa expresión de cálculo.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-135">Instead, you will have bound the value of the *unrealized* call to that computation expression.</span></span> <span data-ttu-id="3cc6a-136">Se `let!` usa para enlazar al resultado.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-136">Use `let!` to bind to the result.</span></span>

<span data-ttu-id="3cc6a-137">`let!`se define `Bind(x, f)` por el miembro en el tipo de generador.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-137">`let!` is defined by the `Bind(x, f)` member on the builder type.</span></span>

### `do!`

<span data-ttu-id="3cc6a-138">La `do!` palabra clave es para llamar `unit`a una expresión `Zero` de cálculo que devuelve un tipo -like (definido por el miembro en el generador):</span><span class="sxs-lookup"><span data-stu-id="3cc6a-138">The `do!` keyword is for calling a computation expression that returns a `unit`-like type (defined by the `Zero` member on the builder):</span></span>

```fsharp
let doThingsAsync data url =
    async {
        do! submitData data url
        ...
    }
```

<span data-ttu-id="3cc6a-139">Para el flujo de `Async<unit>`trabajo [asincrónico,](asynchronous-workflows.md)este tipo es .</span><span class="sxs-lookup"><span data-stu-id="3cc6a-139">For the [async workflow](asynchronous-workflows.md), this type is `Async<unit>`.</span></span> <span data-ttu-id="3cc6a-140">Para otras expresiones de cálculo, `CExpType<unit>`es probable que el tipo sea .</span><span class="sxs-lookup"><span data-stu-id="3cc6a-140">For other computation expressions, the type is likely to be `CExpType<unit>`.</span></span>

<span data-ttu-id="3cc6a-141">`do!`se define `Bind(x, f)` por el miembro en `f` el `unit`tipo de generador, donde produce un archivo .</span><span class="sxs-lookup"><span data-stu-id="3cc6a-141">`do!` is defined by the `Bind(x, f)` member on the builder type, where `f` produces a `unit`.</span></span>

### `yield`

<span data-ttu-id="3cc6a-142">La `yield` palabra clave es para devolver un valor de la expresión <xref:System.Collections.Generic.IEnumerable%601>de cálculo para que se pueda consumir como:</span><span class="sxs-lookup"><span data-stu-id="3cc6a-142">The `yield` keyword is for returning a value from the computation expression so that it can be consumed as an <xref:System.Collections.Generic.IEnumerable%601>:</span></span>

```fsharp
let squares =
    seq {
        for i in 1..10 do
            yield i * i
    }

for sq in squares do
    printfn "%d" sq
```

<span data-ttu-id="3cc6a-143">En la mayoría de los casos, puede ser omitido por los llamadores.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-143">In most cases, it can be omitted by callers.</span></span> <span data-ttu-id="3cc6a-144">La forma más `yield` común de `->` omitir es con el operador:</span><span class="sxs-lookup"><span data-stu-id="3cc6a-144">The most common way to omit `yield` is with the `->` operator:</span></span>

```fsharp
let squares =
    seq {
        for i in 1..10 -> i * i
    }

for sq in squares do
    printfn "%d" sq
```

<span data-ttu-id="3cc6a-145">Para expresiones más complejas que pueden producir muchos valores diferentes, y tal vez condicionalmente, simplemente omitir la palabra clave puede hacer:</span><span class="sxs-lookup"><span data-stu-id="3cc6a-145">For more complex expressions that might yield many different values, and perhaps conditionally, simply omitting the keyword can do:</span></span>

```fsharp
let weekdays includeWeekend =
    seq {
        "Monday"
        "Tuesday"
        "Wednesday"
        "Thursday"
        "Friday"
        if includeWeekend then
            "Saturday"
            "Sunday"
    }
```

<span data-ttu-id="3cc6a-146">Al igual que con la [palabra clave yield en C,](../../csharp/language-reference/keywords/yield.md)cada elemento de la expresión de cálculo se devuelve a medida que se itera.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-146">As with the [yield keyword in C#](../../csharp/language-reference/keywords/yield.md), each element in the computation expression is yielded back as it is iterated.</span></span>

<span data-ttu-id="3cc6a-147">`yield`se define `Yield(x)` por el miembro en `x` el tipo de generador, donde está el elemento para devolver.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-147">`yield` is defined by the `Yield(x)` member on the builder type, where `x` is the item to yield back.</span></span>

### `yield!`

<span data-ttu-id="3cc6a-148">La `yield!` palabra clave es para acoplar una colección de valores de una expresión de cálculo:</span><span class="sxs-lookup"><span data-stu-id="3cc6a-148">The `yield!` keyword is for flattening a collection of values from a computation expression:</span></span>

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

<span data-ttu-id="3cc6a-149">Cuando se evalúa, la `yield!` expresión de cálculo llamada por hará que sus elementos se retraen uno por uno, aplanando el resultado.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-149">When evaluated, the computation expression called by `yield!` will have its items yielded back one-by-one, flattening the result.</span></span>

<span data-ttu-id="3cc6a-150">`yield!`se define `YieldFrom(x)` por el miembro en `x` el tipo de generador, donde hay una colección de valores.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-150">`yield!` is defined by the `YieldFrom(x)` member on the builder type, where `x` is a collection of values.</span></span>

<span data-ttu-id="3cc6a-151">A `yield` `yield!` diferencia de , debe especificarse explícitamente.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-151">Unlike `yield`, `yield!` must be explicitly specified.</span></span> <span data-ttu-id="3cc6a-152">Su comportamiento no está implícito en las expresiones de cálculo.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-152">Its behavior isn't implicit in computation expressions.</span></span>

### `return`

<span data-ttu-id="3cc6a-153">La `return` palabra clave ajusta un valor en el tipo correspondiente a la expresión de cálculo.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-153">The `return` keyword wraps a value in the type corresponding to the computation expression.</span></span> <span data-ttu-id="3cc6a-154">Aparte de `yield`las expresiones de cálculo que utilizan , se utiliza para "completar" una expresión de cálculo:</span><span class="sxs-lookup"><span data-stu-id="3cc6a-154">Aside from computation expressions using `yield`, it is used to "complete" a computation expression:</span></span>

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        let! data = fetch url
        return data
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

<span data-ttu-id="3cc6a-155">`return`se define `Return(x)` por el miembro en `x` el tipo de generador, donde está el elemento que se va a ajustar.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-155">`return` is defined by the `Return(x)` member on the builder type, where `x` is the item to wrap.</span></span>

### `return!`

<span data-ttu-id="3cc6a-156">La `return!` palabra clave realiza el valor de una expresión de cálculo y ajusta el tipo correspondiente a la expresión de cálculo:</span><span class="sxs-lookup"><span data-stu-id="3cc6a-156">The `return!` keyword realizes the value of a computation expression and wraps that result in the type corresponding to the computation expression:</span></span>

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        return! fetch url
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

<span data-ttu-id="3cc6a-157">`return!`se define `ReturnFrom(x)` por el miembro en `x` el tipo de generador, donde hay otra expresión de cálculo.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-157">`return!` is defined by the `ReturnFrom(x)` member on the builder type, where `x` is another computation expression.</span></span>

### `match!`

<span data-ttu-id="3cc6a-158">La `match!` palabra clave le permite inlinear una llamada a otra expresión de cálculo y coincidencia de patrón en su resultado:</span><span class="sxs-lookup"><span data-stu-id="3cc6a-158">The `match!` keyword allows you to inline a call to another computation expression and pattern match on its result:</span></span>

```fsharp
let doThingsAsync url =
    async {
        match! callService url with
        | Some data -> ...
        | None -> ...
    }
```

<span data-ttu-id="3cc6a-159">Al llamar a `match!`una expresión de cálculo con `let!`, se dará cuenta del resultado de la llamada como .</span><span class="sxs-lookup"><span data-stu-id="3cc6a-159">When calling a computation expression with `match!`, it will realize the result of the call like `let!`.</span></span> <span data-ttu-id="3cc6a-160">Esto se utiliza a menudo cuando se llama a una expresión de cálculo donde el resultado es un [archivo .](options.md)</span><span class="sxs-lookup"><span data-stu-id="3cc6a-160">This is often used when calling a computation expression where the result is an [optional](options.md).</span></span>

## <a name="built-in-computation-expressions"></a><span data-ttu-id="3cc6a-161">Expresiones de cálculo integradas</span><span class="sxs-lookup"><span data-stu-id="3cc6a-161">Built-in computation expressions</span></span>

<span data-ttu-id="3cc6a-162">La biblioteca principal de F - define tres expresiones de cálculo integradas: [Expresiones](sequences.md)de secuencia , Flujos de [trabajo asincrónicos](asynchronous-workflows.md)y [Expresiones](query-expressions.md)de consulta .</span><span class="sxs-lookup"><span data-stu-id="3cc6a-162">The F# core library defines three built-in computation expressions: [Sequence Expressions](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Query Expressions](query-expressions.md).</span></span>

## <a name="creating-a-new-type-of-computation-expression"></a><span data-ttu-id="3cc6a-163">Creación de un nuevo tipo de expresión de cálculo</span><span class="sxs-lookup"><span data-stu-id="3cc6a-163">Creating a New Type of Computation Expression</span></span>

<span data-ttu-id="3cc6a-164">Puede definir las características de sus propias expresiones de cálculo creando una clase de generador y definiendo ciertos métodos especiales en la clase.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-164">You can define the characteristics of your own computation expressions by creating a builder class and defining certain special methods on the class.</span></span> <span data-ttu-id="3cc6a-165">La clase de generador puede definir opcionalmente los métodos enumerados en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-165">The builder class can optionally define the methods as listed in the following table.</span></span>

<span data-ttu-id="3cc6a-166">En la tabla siguiente se describen los métodos que se pueden usar en una clase de generador de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-166">The following table describes methods that can be used in a workflow builder class.</span></span>

|<span data-ttu-id="3cc6a-167">**Método**</span><span class="sxs-lookup"><span data-stu-id="3cc6a-167">**Method**</span></span>|<span data-ttu-id="3cc6a-168">**Firma(s) típica(s)**</span><span class="sxs-lookup"><span data-stu-id="3cc6a-168">**Typical signature(s)**</span></span>|<span data-ttu-id="3cc6a-169">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="3cc6a-169">**Description**</span></span>|
|----|----|----|
|`Bind`|`M<'T> * ('T -> M<'U>) -> M<'U>`|<span data-ttu-id="3cc6a-170">Llamado `let!` para `do!` y en expresiones de cálculo.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-170">Called for `let!` and `do!` in computation expressions.</span></span>|
|`Delay`|`(unit -> M<'T>) -> M<'T>`|<span data-ttu-id="3cc6a-171">Ajusta una expresión de cálculo como una función.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-171">Wraps a computation expression as a function.</span></span>|
|`Return`|`'T -> M<'T>`|<span data-ttu-id="3cc6a-172">Se `return` llama en expresiones de cálculo.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-172">Called for `return` in computation expressions.</span></span>|
|`ReturnFrom`|`M<'T> -> M<'T>`|<span data-ttu-id="3cc6a-173">Se `return!` llama en expresiones de cálculo.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-173">Called for `return!` in computation expressions.</span></span>|
|`Run`|<span data-ttu-id="3cc6a-174">`M<'T> -> M<'T>` o</span><span class="sxs-lookup"><span data-stu-id="3cc6a-174">`M<'T> -> M<'T>` or</span></span><br /><br />`M<'T> -> 'T`|<span data-ttu-id="3cc6a-175">Ejecuta una expresión de cálculo.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-175">Executes a computation expression.</span></span>|
|`Combine`|<span data-ttu-id="3cc6a-176">`M<'T> * M<'T> -> M<'T>` o</span><span class="sxs-lookup"><span data-stu-id="3cc6a-176">`M<'T> * M<'T> -> M<'T>` or</span></span><br /><br />`M<unit> * M<'T> -> M<'T>`|<span data-ttu-id="3cc6a-177">Se ha llamado para la secuenciación en expresiones de cálculo.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-177">Called for sequencing in computation expressions.</span></span>|
|`For`|<span data-ttu-id="3cc6a-178">`seq<'T> * ('T -> M<'U>) -> M<'U>` o</span><span class="sxs-lookup"><span data-stu-id="3cc6a-178">`seq<'T> * ('T -> M<'U>) -> M<'U>` or</span></span><br /><br />`seq<'T> * ('T -> M<'U>) -> seq<M<'U>>`|<span data-ttu-id="3cc6a-179">Se `for...do` ha llamado a expresiones en expresiones de cálculo.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-179">Called for `for...do` expressions in computation expressions.</span></span>|
|`TryFinally`|`M<'T> * (unit -> unit) -> M<'T>`|<span data-ttu-id="3cc6a-180">Se `try...finally` ha llamado a expresiones en expresiones de cálculo.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-180">Called for `try...finally` expressions in computation expressions.</span></span>|
|`TryWith`|`M<'T> * (exn -> M<'T>) -> M<'T>`|<span data-ttu-id="3cc6a-181">Se `try...with` ha llamado a expresiones en expresiones de cálculo.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-181">Called for `try...with` expressions in computation expressions.</span></span>|
|`Using`|`'T * ('T -> M<'U>) -> M<'U> when 'T :> IDisposable`|<span data-ttu-id="3cc6a-182">Se `use` llama para enlaces en expresiones de cálculo.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-182">Called for `use` bindings in computation expressions.</span></span>|
|`While`|`(unit -> bool) * M<'T> -> M<'T>`|<span data-ttu-id="3cc6a-183">Se `while...do` ha llamado a expresiones en expresiones de cálculo.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-183">Called for `while...do` expressions in computation expressions.</span></span>|
|`Yield`|`'T -> M<'T>`|<span data-ttu-id="3cc6a-184">Se `yield` ha llamado a expresiones en expresiones de cálculo.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-184">Called for `yield` expressions in computation expressions.</span></span>|
|`YieldFrom`|`M<'T> -> M<'T>`|<span data-ttu-id="3cc6a-185">Se `yield!` ha llamado a expresiones en expresiones de cálculo.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-185">Called for `yield!` expressions in computation expressions.</span></span>|
|`Zero`|`unit -> M<'T>`|<span data-ttu-id="3cc6a-186">Se llama `else` a `if...then` ramas vacías de expresiones en expresiones de cálculo.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-186">Called for empty `else` branches of `if...then` expressions in computation expressions.</span></span>|
|`Quote`|`Quotations.Expr<'T> -> Quotations.Expr<'T>`|<span data-ttu-id="3cc6a-187">Indica que la expresión de `Run` cálculo se pasa al miembro como una cita.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-187">Indicates that the computation expression is passed to the `Run` member as a quotation.</span></span> <span data-ttu-id="3cc6a-188">Traduce todas las instancias de un cálculo en una cita.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-188">It translates all instances of a computation into a quotation.</span></span>|

<span data-ttu-id="3cc6a-189">Muchos de los métodos de una `M<'T>` clase de generador usan y devuelven una construcción, que suele ser `Async<'T>` un tipo `Seq<'T>` definido por separado que caracteriza el tipo de cálculos que se combinan, por ejemplo, para flujos de trabajo asincrónicos y para flujos de trabajo de secuencia.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-189">Many of the methods in a builder class use and return an `M<'T>` construct, which is typically a separately defined type that characterizes the kind of computations being combined, for example, `Async<'T>` for asynchronous workflows and `Seq<'T>` for sequence workflows.</span></span> <span data-ttu-id="3cc6a-190">Las firmas de estos métodos permiten combinarlas y anidarlas entre sí, de modo que el objeto de flujo de trabajo devuelto por una construcción se puede pasar a la siguiente.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-190">The signatures of these methods enable them to be combined and nested with each other, so that the workflow object returned from one construct can be passed to the next.</span></span> <span data-ttu-id="3cc6a-191">El compilador, cuando analiza una expresión de cálculo, convierte la expresión en una serie de llamadas a funciones anidadas mediante los métodos de la tabla anterior y el código de la expresión de cálculo.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-191">The compiler, when it parses a computation expression, converts the expression into a series of nested function calls by using the methods in the preceding table and the code in the computation expression.</span></span>

<span data-ttu-id="3cc6a-192">La expresión anidada tiene la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="3cc6a-192">The nested expression is of the following form:</span></span>

```fsharp
builder.Run(builder.Delay(fun () -> {| cexpr |}))
```

<span data-ttu-id="3cc6a-193">En el código anterior, `Run` `Delay` las llamadas y se omiten si no están definidas en la clase del generador de expresiones de cálculo.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-193">In the above code, the calls to `Run` and `Delay` are omitted if they are not defined in the computation expression builder class.</span></span> <span data-ttu-id="3cc6a-194">El cuerpo de la expresión de `{| cexpr |}`cálculo, aquí denotado como , se traduce en llamadas que implican los métodos de la clase de generador por las traducciones descritas en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-194">The body of the computation expression, here denoted as `{| cexpr |}`, is translated into calls involving the methods of the builder class by the translations described in the following table.</span></span> <span data-ttu-id="3cc6a-195">La expresión `{| cexpr |}` de cálculo se define de `expr` forma recursiva según estas traducciones, donde es una expresión de F y `cexpr` es una expresión de cálculo.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-195">The computation expression `{| cexpr |}` is defined recursively according to these translations where `expr` is an F# expression and `cexpr` is a computation expression.</span></span>

|<span data-ttu-id="3cc6a-196">Expression</span><span class="sxs-lookup"><span data-stu-id="3cc6a-196">Expression</span></span>|<span data-ttu-id="3cc6a-197">Traducción</span><span class="sxs-lookup"><span data-stu-id="3cc6a-197">Translation</span></span>|
|----------|-----------|
|<code>{ let binding in cexpr }</code>|<code>let binding in {&#124; cexpr &#124;}</code>|
|<code>{ let! pattern = expr in cexpr }</code>|<code>builder.Bind(expr, (fun pattern -> {&#124; cexpr &#124;}))</code>|
|<code>{ do! expr in cexpr }</code>|<code>builder.Bind(expr, (fun () -> {&#124; cexpr &#124;}))</code>|
|<code>{ yield expr }</code>|`builder.Yield(expr)`|
|<code>{ yield! expr }</code>|`builder.YieldFrom(expr)`|
|<code>{ return expr }</code>|`builder.Return(expr)`|
|<code>{ return! expr }</code>|`builder.ReturnFrom(expr)`|
|<code>{ use pattern = expr in cexpr }</code>|<code>builder.Using(expr, (fun pattern -> {&#124; cexpr &#124;}))</code>|
|<code>{ use! value = expr in cexpr }</code>|<code>builder.Bind(expr, (fun value -> builder.Using(value, (fun value -> { cexpr }))))</code>|
|<code>{ if expr then cexpr0 &#124;}</code>|<code>if expr then { cexpr0 } else builder.Zero()</code>|
|<code>{ if expr then cexpr0 else cexpr1 &#124;}</code>|<code>if expr then { cexpr0 } else { cexpr1 }</code>|
|<code>{ match expr with &#124; pattern_i -> cexpr_i }</code>|<code>match expr with &#124; pattern_i -> { cexpr_i }</code>|
|<code>{ for pattern in expr do cexpr }</code>|<code>builder.For(enumeration, (fun pattern -> { cexpr }))</code>|
|<code>{ for identifier = expr1 to expr2 do cexpr }</code>|<code>builder.For(enumeration, (fun identifier -> { cexpr }))</code>|
|<code>{ while expr do cexpr }</code>|<code>builder.While(fun () -> expr, builder.Delay({ cexpr }))</code>|
|<code>{ try cexpr with &#124; pattern_i -> expr_i }</code>|<code>builder.TryWith(builder.Delay({ cexpr }), (fun value -> match value with &#124; pattern_i -> expr_i &#124; exn -> reraise exn)))</code>|
|<code>{ try cexpr finally expr }</code>|<code>builder.TryFinally(builder.Delay( { cexpr }), (fun () -> expr))</code>|
|<code>{ cexpr1; cexpr2 }</code>|<code>builder.Combine({ cexpr1 }, { cexpr2 })</code>|
|<code>{ other-expr; cexpr }</code>|<code>expr; { cexpr }</code>|
|<code>{ other-expr }</code>|`expr; builder.Zero()`|

<span data-ttu-id="3cc6a-198">En la tabla `other-expr` anterior, se describe una expresión que no aparece de otro modo en la tabla.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-198">In the previous table, `other-expr` describes an expression that is not otherwise listed in the table.</span></span> <span data-ttu-id="3cc6a-199">Una clase de generador no necesita implementar todos los métodos y admitir todas las traducciones enumeradas en la tabla anterior.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-199">A builder class does not need to implement all of the methods and support all of the translations listed in the previous table.</span></span> <span data-ttu-id="3cc6a-200">Las construcciones que no se implementan no están disponibles en expresiones de cálculo de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-200">Those constructs that are not implemented are not available in computation expressions of that type.</span></span> <span data-ttu-id="3cc6a-201">Por ejemplo, si no desea `use` admitir la palabra clave en las `Use` expresiones de cálculo, puede omitir la definición de en la clase de generador.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-201">For example, if you do not want to support the `use` keyword in your computation expressions, you can omit the definition of `Use` in your builder class.</span></span>

<span data-ttu-id="3cc6a-202">En el ejemplo de código siguiente se muestra una expresión de cálculo que encapsula un cálculo como una serie de pasos que se pueden evaluar paso a paso.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-202">The following code example shows a computation expression that encapsulates a computation as a series of steps that can be evaluated one step at a time.</span></span> <span data-ttu-id="3cc6a-203">Un tipo de `OkOrException`unión discriminado, , codifica el estado de error de la expresión tal como se ha evaluado hasta ahora.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-203">A discriminated union type, `OkOrException`, encodes the error state of the expression as evaluated so far.</span></span> <span data-ttu-id="3cc6a-204">Este código muestra varios patrones típicos que puede usar en las expresiones de cálculo, como las implementaciones reutilizables de algunos de los métodos del generador.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-204">This code demonstrates several typical patterns that you can use in your computation expressions, such as boilerplate implementations of some of the builder methods.</span></span>

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
        | Done value -> func value
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
// returns "Done 7"
comp |> step |> step |> step |> step
```

<span data-ttu-id="3cc6a-205">Una expresión de cálculo tiene un tipo subyacente, que devuelve la expresión.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-205">A computation expression has an underlying type, which the expression returns.</span></span> <span data-ttu-id="3cc6a-206">El tipo subyacente puede representar un resultado calculado o un cálculo retrasado que se puede realizar, o puede proporcionar una manera de recorrer en iteración algún tipo de colección.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-206">The underlying type may represent a computed result or a delayed computation that can be performed, or it may provide a way to iterate through some type of collection.</span></span> <span data-ttu-id="3cc6a-207">En el ejemplo anterior, el tipo subyacente era **Eventually**.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-207">In the previous example, the underlying type was **Eventually**.</span></span> <span data-ttu-id="3cc6a-208">Para una expresión de secuencia, <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>el tipo subyacente es .</span><span class="sxs-lookup"><span data-stu-id="3cc6a-208">For a sequence expression, the underlying type is <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.</span></span> <span data-ttu-id="3cc6a-209">Para una expresión de consulta, <xref:System.Linq.IQueryable?displayProperty=nameWithType>el tipo subyacente es .</span><span class="sxs-lookup"><span data-stu-id="3cc6a-209">For a query expression, the underlying type is <xref:System.Linq.IQueryable?displayProperty=nameWithType>.</span></span> <span data-ttu-id="3cc6a-210">Para un flujo de trabajo [`Async`](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7)asincrónico, el tipo subyacente es .</span><span class="sxs-lookup"><span data-stu-id="3cc6a-210">For an asynchronous workflow, the underlying type is [`Async`](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7).</span></span> <span data-ttu-id="3cc6a-211">El `Async` objeto representa el trabajo que se va a realizar para calcular el resultado.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-211">The `Async` object represents the work to be performed to compute the result.</span></span> <span data-ttu-id="3cc6a-212">Por ejemplo, [`Async.RunSynchronously`](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) se llama para ejecutar un cálculo y devolver el resultado.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-212">For example, you call [`Async.RunSynchronously`](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) to execute a computation and return the result.</span></span>

## <a name="custom-operations"></a><span data-ttu-id="3cc6a-213">Operaciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="3cc6a-213">Custom Operations</span></span>

<span data-ttu-id="3cc6a-214">Puede definir una operación personalizada en una expresión de cálculo y utilizar una operación personalizada como operador en una expresión de cálculo.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-214">You can define a custom operation on a computation expression and use a custom operation as an operator in a computation expression.</span></span> <span data-ttu-id="3cc6a-215">Por ejemplo, puede incluir un operador de consulta en una expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-215">For example, you can include a query operator in a query expression.</span></span> <span data-ttu-id="3cc6a-216">Al definir una operación personalizada, debe definir los métodos Yield y For en la expresión de cálculo.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-216">When you define a custom operation, you must define the Yield and For methods in the computation expression.</span></span> <span data-ttu-id="3cc6a-217">Para definir una operación personalizada, colóquela en una [`CustomOperationAttribute`](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19)clase de generador para la expresión de cálculo y, a continuación, aplique el archivo .</span><span class="sxs-lookup"><span data-stu-id="3cc6a-217">To define a custom operation, put it in a builder class for the computation expression, and then apply the [`CustomOperationAttribute`](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19).</span></span> <span data-ttu-id="3cc6a-218">Este atributo toma una cadena como argumento, que es el nombre que se usará en una operación personalizada.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-218">This attribute takes a string as an argument, which is the name to be used in a custom operation.</span></span> <span data-ttu-id="3cc6a-219">Este nombre entra en el ámbito al principio de la llave de apertura de la expresión de cálculo.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-219">This name comes into scope at the start of the opening curly brace of the computation expression.</span></span> <span data-ttu-id="3cc6a-220">Por lo tanto, no debe usar identificadores que tengan el mismo nombre que una operación personalizada en este bloque.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-220">Therefore, you shouldn’t use identifiers that have the same name as a custom operation in this block.</span></span> <span data-ttu-id="3cc6a-221">Por ejemplo, evite el uso `all` de `last` identificadores como o en expresiones de consulta.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-221">For example, avoid the use of identifiers such as `all` or `last` in query expressions.</span></span>

### <a name="extending-existing-builders-with-new-custom-operations"></a><span data-ttu-id="3cc6a-222">Ampliación de los constructores existentes con nuevas operaciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="3cc6a-222">Extending existing Builders with new Custom Operations</span></span>

<span data-ttu-id="3cc6a-223">Si ya tiene una clase de generador, sus operaciones personalizadas se pueden extender desde fuera de esta clase de generador.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-223">If you already have a builder class, its custom operations can be extended from outside of this builder class.</span></span> <span data-ttu-id="3cc6a-224">Las extensiones deben declararse en módulos.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-224">Extensions must be declared in modules.</span></span> <span data-ttu-id="3cc6a-225">Los espacios de nombres no pueden contener miembros de extensión excepto en el mismo archivo y el mismo grupo de declaración de espacio de nombres donde se define el tipo.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-225">Namespaces cannot contain extension members except in the same file and the same namespace declaration group where the type is defined.</span></span>

<span data-ttu-id="3cc6a-226">En el ejemplo siguiente se `Microsoft.FSharp.Linq.QueryBuilder` muestra la extensión de la clase existente.</span><span class="sxs-lookup"><span data-stu-id="3cc6a-226">The following example shows the extension of the existing `Microsoft.FSharp.Linq.QueryBuilder` class.</span></span>

```fsharp
type Microsoft.FSharp.Linq.QueryBuilder with

    [<CustomOperation("existsNot")>]
    member _.ExistsNot (source: QuerySource<'T, 'Q>, predicate) =
        Enumerable.Any (source.Source, Func<_,_>(predicate)) |> not
```

## <a name="see-also"></a><span data-ttu-id="3cc6a-227">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3cc6a-227">See also</span></span>

- [<span data-ttu-id="3cc6a-228">Referencia del lenguaje f</span><span class="sxs-lookup"><span data-stu-id="3cc6a-228">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="3cc6a-229">Flujos de trabajo asincrónicos</span><span class="sxs-lookup"><span data-stu-id="3cc6a-229">Asynchronous Workflows</span></span>](asynchronous-workflows.md)
- [<span data-ttu-id="3cc6a-230">Secuencias</span><span class="sxs-lookup"><span data-stu-id="3cc6a-230">Sequences</span></span>](https://msdn.microsoft.com/library/6b773b6b-9c9a-4af8-bd9e-d96585c166db)
- [<span data-ttu-id="3cc6a-231">Expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="3cc6a-231">Query Expressions</span></span>](query-expressions.md)
