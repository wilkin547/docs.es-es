---
title: Expresiones de cálculo (F#)
description: 'Obtenga información acerca de cómo crear la sintaxis adecuada para escribir cálculos en F # que se pueden secuenciar y combinar mediante enlaces y construcciones de flujo de control.'
ms.date: 05/16/2016
ms.openlocfilehash: 4995efc757d99a575ee9fad3abf0465a32398c44
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36207438"
---
# <a name="computation-expressions"></a><span data-ttu-id="391af-103">Expresiones de cálculo</span><span class="sxs-lookup"><span data-stu-id="391af-103">Computation Expressions</span></span>

<span data-ttu-id="391af-104">Expresiones de cálculo en F # proporcionan una sintaxis adecuada para escribir cálculos que se pueden secuenciar y combinar mediante enlaces y construcciones de flujo de control.</span><span class="sxs-lookup"><span data-stu-id="391af-104">Computation expressions in F# provide a convenient syntax for writing computations that can be sequenced and combined using control flow constructs and bindings.</span></span> <span data-ttu-id="391af-105">Pueden usarse para proporcionar una sintaxis adecuada para *monads*, una característica de programación funcional que puede usarse para administrar datos, control y efectos secundarios en programas funcionales.</span><span class="sxs-lookup"><span data-stu-id="391af-105">They can be used to provide a convenient syntax for *monads*, a functional programming feature that can be used to manage data, control, and side effects in functional programs.</span></span>


## <a name="built-in-workflows"></a><span data-ttu-id="391af-106">Flujos de trabajo integrados</span><span class="sxs-lookup"><span data-stu-id="391af-106">Built-in Workflows</span></span>

<span data-ttu-id="391af-107">Expresiones de secuencia son un ejemplo de una expresión de cálculo, como flujos de trabajo asincrónicos y las expresiones de consulta.</span><span class="sxs-lookup"><span data-stu-id="391af-107">Sequence expressions are an example of a computation expression, as are asynchronous workflows and query expressions.</span></span> <span data-ttu-id="391af-108">Para obtener más información, consulte [secuencias](sequences.md), [flujos de trabajo asincrónicos](asynchronous-workflows.md), y [expresiones de consulta](query-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="391af-108">For more information, see [Sequences](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Query Expressions](query-expressions.md).</span></span>

<span data-ttu-id="391af-109">Ciertas características comunes a las expresiones de secuencia y flujos de trabajo asincrónicos y muestran la sintaxis básica para una expresión de cálculo:</span><span class="sxs-lookup"><span data-stu-id="391af-109">Certain features are common to both sequence expressions and asynchronous workflows and illustrate the basic syntax for a computation expression:</span></span>

```fsharp
builder-name { expression }
```

<span data-ttu-id="391af-110">La sintaxis anterior especifica que la expresión dada es una expresión de cálculo de un tipo especificado por *nombre de generador*.</span><span class="sxs-lookup"><span data-stu-id="391af-110">The previous syntax specifies that the given expression is a computation expression of a type specified by *builder-name*.</span></span> <span data-ttu-id="391af-111">La expresión de cálculo puede ser un flujo de trabajo integrada, como `seq` o `async`, o puede ser algo que defina.</span><span class="sxs-lookup"><span data-stu-id="391af-111">The computation expression can be a built-in workflow, such as `seq` or `async`, or it can be something you define.</span></span> <span data-ttu-id="391af-112">El *nombre de generador* es el identificador de una instancia de un tipo especial conocida como el *tipo de generador*.</span><span class="sxs-lookup"><span data-stu-id="391af-112">The *builder-name* is the identifier for an instance of a special type known as the *builder type*.</span></span> <span data-ttu-id="391af-113">El tipo de generador es un tipo de clase que define los métodos especiales que rigen la forma en que se combinan los fragmentos de la expresión de cálculo, es decir, código que controla cómo se ejecuta la expresión.</span><span class="sxs-lookup"><span data-stu-id="391af-113">The builder type is a class type that defines special methods that govern the way the fragments of the computation expression are combined, that is, code that controls how the expression executes.</span></span> <span data-ttu-id="391af-114">Otra manera de describir una clase de generador consiste en indicar que permite personalizar la operación de muchas construcciones de F #, tales como bucles y enlaces.</span><span class="sxs-lookup"><span data-stu-id="391af-114">Another way to describe a builder class is to say that it enables you to customize the operation of many F# constructs, such as loops and bindings.</span></span>

<span data-ttu-id="391af-115">En las expresiones de cálculo, dos formas están disponibles para algunas construcciones de lenguaje común.</span><span class="sxs-lookup"><span data-stu-id="391af-115">In computation expressions, two forms are available for some common language constructs.</span></span> <span data-ttu-id="391af-116">Puede invocar las construcciones variantes mediante una!</span><span class="sxs-lookup"><span data-stu-id="391af-116">You can invoke the variant constructs by using a !</span></span> <span data-ttu-id="391af-117">(bang) como el sufijo en ciertas palabras clave, `let!`, `do!`, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="391af-117">(bang) suffix on certain keywords, such as `let!`, `do!`, and so on.</span></span> <span data-ttu-id="391af-118">Estos formatos especiales hacer que determinadas funciones definidas en la clase de generador para reemplazar el comportamiento integrado normal de estas operaciones.</span><span class="sxs-lookup"><span data-stu-id="391af-118">These special forms cause certain functions defined in the builder class to replace the ordinary built-in behavior of these operations.</span></span> <span data-ttu-id="391af-119">Estos formatos son similares a los `yield!` formada por el `yield` palabra clave que se utiliza en expresiones de secuencia.</span><span class="sxs-lookup"><span data-stu-id="391af-119">These forms resemble the `yield!` form of the `yield` keyword that is used in sequence expressions.</span></span> <span data-ttu-id="391af-120">Para obtener más información, consulte [secuencias](sequences.md).</span><span class="sxs-lookup"><span data-stu-id="391af-120">For more information, see [Sequences](sequences.md).</span></span>


## <a name="creating-a-new-type-of-computation-expression"></a><span data-ttu-id="391af-121">Crear un nuevo tipo de expresión de cálculo</span><span class="sxs-lookup"><span data-stu-id="391af-121">Creating a New Type of Computation Expression</span></span>
<span data-ttu-id="391af-122">Puede definir las características de sus propias expresiones de cálculo mediante la creación de una clase de generador y definir ciertos métodos especiales en la clase.</span><span class="sxs-lookup"><span data-stu-id="391af-122">You can define the characteristics of your own computation expressions by creating a builder class and defining certain special methods on the class.</span></span> <span data-ttu-id="391af-123">La clase de generador, opcionalmente, puede definir los métodos que se muestran en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="391af-123">The builder class can optionally define the methods as listed in the following table.</span></span>

<span data-ttu-id="391af-124">En la tabla siguiente se describe los métodos que pueden usarse en una clase de generador de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="391af-124">The following table describes methods that can be used in a workflow builder class.</span></span>


|<span data-ttu-id="391af-125">**Método**</span><span class="sxs-lookup"><span data-stu-id="391af-125">**Method**</span></span>|<span data-ttu-id="391af-126">**Signaturas típicas**</span><span class="sxs-lookup"><span data-stu-id="391af-126">**Typical signature(s)**</span></span>|<span data-ttu-id="391af-127">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="391af-127">**Description**</span></span>|
|----|----|----|
|`Bind`|`M<'T> * ('T -> M<'U>) -> M<'U>`|<span data-ttu-id="391af-128">Piden `let!` y `do!` en expresiones de cálculo.</span><span class="sxs-lookup"><span data-stu-id="391af-128">Called for `let!` and `do!` in computation expressions.</span></span>|
|`Delay`|`(unit -> M<'T>) -> M<'T>`|<span data-ttu-id="391af-129">Contiene una expresión de cálculo como una función.</span><span class="sxs-lookup"><span data-stu-id="391af-129">Wraps a computation expression as a function.</span></span>|
|`Return`|`'T -> M<'T>`|<span data-ttu-id="391af-130">Piden `return` en expresiones de cálculo.</span><span class="sxs-lookup"><span data-stu-id="391af-130">Called for `return` in computation expressions.</span></span>|
|`ReturnFrom`|`M<'T> -> M<'T>`|<span data-ttu-id="391af-131">Piden `return!` en expresiones de cálculo.</span><span class="sxs-lookup"><span data-stu-id="391af-131">Called for `return!` in computation expressions.</span></span>|
|`Run`|<span data-ttu-id="391af-132">`M<'T> -> M<'T>`, o bien</span><span class="sxs-lookup"><span data-stu-id="391af-132">`M<'T> -> M<'T>` or</span></span><br /><br />`M<'T> -> 'T`|<span data-ttu-id="391af-133">Ejecuta una expresión de cálculo.</span><span class="sxs-lookup"><span data-stu-id="391af-133">Executes a computation expression.</span></span>|
|`Combine`|<span data-ttu-id="391af-134">`M<'T> * M<'T> -> M<'T>`, o bien</span><span class="sxs-lookup"><span data-stu-id="391af-134">`M<'T> * M<'T> -> M<'T>` or</span></span><br /><br />`M<unit> * M<'T> -> M<'T>`|<span data-ttu-id="391af-135">Se llama para las secuencias en las expresiones de cálculo.</span><span class="sxs-lookup"><span data-stu-id="391af-135">Called for sequencing in computation expressions.</span></span>|
|`For`|<span data-ttu-id="391af-136">`seq<'T> * ('T -> M<'U>) -> M<'U>`, o bien</span><span class="sxs-lookup"><span data-stu-id="391af-136">`seq<'T> * ('T -> M<'U>) -> M<'U>` or</span></span><br /><br />`seq<'T> * ('T -> M<'U>) -> seq<M<'U>>`|<span data-ttu-id="391af-137">Piden `for...do` expresiones en expresiones de cálculo.</span><span class="sxs-lookup"><span data-stu-id="391af-137">Called for `for...do` expressions in computation expressions.</span></span>|
|`TryFinally`|`M<'T> * (unit -> unit) -> M<'T>`|<span data-ttu-id="391af-138">Piden `try...finally` expresiones en expresiones de cálculo.</span><span class="sxs-lookup"><span data-stu-id="391af-138">Called for `try...finally` expressions in computation expressions.</span></span>|
|`TryWith`|`M<'T> * (exn -> M<'T>) -> M<'T>`|<span data-ttu-id="391af-139">Piden `try...with` expresiones en expresiones de cálculo.</span><span class="sxs-lookup"><span data-stu-id="391af-139">Called for `try...with` expressions in computation expressions.</span></span>|
|`Using`|`'T * ('T -> M<'U>) -> M<'U> when 'U :> IDisposable`|<span data-ttu-id="391af-140">Piden `use` enlaces en expresiones de cálculo.</span><span class="sxs-lookup"><span data-stu-id="391af-140">Called for `use` bindings in computation expressions.</span></span>|
|`While`|`(unit -> bool) * M<'T> -> M<'T>`|<span data-ttu-id="391af-141">Piden `while...do` expresiones en expresiones de cálculo.</span><span class="sxs-lookup"><span data-stu-id="391af-141">Called for `while...do` expressions in computation expressions.</span></span>|
|`Yield`|`'T -> M<'T>`|<span data-ttu-id="391af-142">Piden `yield` expresiones en expresiones de cálculo.</span><span class="sxs-lookup"><span data-stu-id="391af-142">Called for `yield` expressions in computation expressions.</span></span>|
|`YieldFrom`|`M<'T> -> M<'T>`|<span data-ttu-id="391af-143">Piden `yield!` expresiones en expresiones de cálculo.</span><span class="sxs-lookup"><span data-stu-id="391af-143">Called for `yield!` expressions in computation expressions.</span></span>|
|`Zero`|`unit -> M<'T>`|<span data-ttu-id="391af-144">Piden vacío `else` bifurcaciones de `if...then` expresiones en expresiones de cálculo.</span><span class="sxs-lookup"><span data-stu-id="391af-144">Called for empty `else` branches of `if...then` expressions in computation expressions.</span></span>|
<span data-ttu-id="391af-145">Muchos de los métodos de una clase de generador de usar y devolver un `M<'T>` construcción, que normalmente es un tipo definido por separado que caracteriza el tipo de cálculos que se combinan, por ejemplo, `Async<'T>` para flujos de trabajo asincrónicos y `Seq<'T>` para los flujos de trabajo de secuencia.</span><span class="sxs-lookup"><span data-stu-id="391af-145">Many of the methods in a builder class use and return an `M<'T>` construct, which is typically a separately defined type that characterizes the kind of computations being combined, for example, `Async<'T>` for asynchronous workflows and `Seq<'T>` for sequence workflows.</span></span> <span data-ttu-id="391af-146">Las firmas de estos métodos que puedan combinarse y anidarse entre sí, para que el objeto de flujo de trabajo devuelto por una construcción puede pasarse a la siguiente.</span><span class="sxs-lookup"><span data-stu-id="391af-146">The signatures of these methods enable them to be combined and nested with each other, so that the workflow object returned from one construct can be passed to the next.</span></span> <span data-ttu-id="391af-147">El compilador, cuando analiza una expresión de cálculo, convierte la expresión en una serie de llamadas a funciones anidadas mediante los métodos de la tabla anterior y el código de la expresión de cálculo.</span><span class="sxs-lookup"><span data-stu-id="391af-147">The compiler, when it parses a computation expression, converts the expression into a series of nested function calls by using the methods in the preceding table and the code in the computation expression.</span></span>

<span data-ttu-id="391af-148">La expresión anidada es la forma siguiente:</span><span class="sxs-lookup"><span data-stu-id="391af-148">The nested expression is of the following form:</span></span>

```fsharp
builder.Run(builder.Delay(fun () -> {| cexpr |}))
```

<span data-ttu-id="391af-149">En el código anterior, las llamadas a `Run` y `Delay` se omiten si no se definen en la clase de generador de expresiones de cálculo.</span><span class="sxs-lookup"><span data-stu-id="391af-149">In the above code, the calls to `Run` and `Delay` are omitted if they are not defined in the computation expression builder class.</span></span> <span data-ttu-id="391af-150">El cuerpo de la expresión de cálculo, aquí se denomina `{| cexpr |}`, se convierten en llamadas relacionadas con los métodos de la clase de generador por las traducciones que se describe en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="391af-150">The body of the computation expression, here denoted as `{| cexpr |}`, is translated into calls involving the methods of the builder class by the translations described in the following table.</span></span> <span data-ttu-id="391af-151">La expresión de cálculo `{| cexpr |}` está definido de forma recursiva según estas traducciones donde `expr` es una expresión de F # y `cexpr` es una expresión de cálculo.</span><span class="sxs-lookup"><span data-stu-id="391af-151">The computation expression `{| cexpr |}` is defined recursively according to these translations where `expr` is an F# expression and `cexpr` is a computation expression.</span></span>



|<span data-ttu-id="391af-152">Expresión</span><span class="sxs-lookup"><span data-stu-id="391af-152">Expression</span></span>|<span data-ttu-id="391af-153">Conversión</span><span class="sxs-lookup"><span data-stu-id="391af-153">Translation</span></span>|
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
<span data-ttu-id="391af-154">En la tabla anterior, `other-expr` describe una expresión que de lo contrario no se muestra en la tabla.</span><span class="sxs-lookup"><span data-stu-id="391af-154">In the previous table, `other-expr` describes an expression that is not otherwise listed in the table.</span></span> <span data-ttu-id="391af-155">Una clase de generador no es necesario implementar todos los métodos y admite todas las traducciones que se muestran en la tabla anterior.</span><span class="sxs-lookup"><span data-stu-id="391af-155">A builder class does not need to implement all of the methods and support all of the translations listed in the previous table.</span></span> <span data-ttu-id="391af-156">Las construcciones que no se implementan no están disponibles en las expresiones de cálculo de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="391af-156">Those constructs that are not implemented are not available in computation expressions of that type.</span></span> <span data-ttu-id="391af-157">Por ejemplo, si no desea admitir la `use` palabra clave en las expresiones de cálculo, puede omitir la definición de `Use` en la clase de generador.</span><span class="sxs-lookup"><span data-stu-id="391af-157">For example, if you do not want to support the `use` keyword in your computation expressions, you can omit the definition of `Use` in your builder class.</span></span>

<span data-ttu-id="391af-158">En el ejemplo de código siguiente se muestra una expresión de cálculo que encapsula un cálculo con una serie de pasos que se puede evaluar un paso a la vez.</span><span class="sxs-lookup"><span data-stu-id="391af-158">The following code example shows a computation expression that encapsulates a computation as a series of steps that can be evaluated one step at a time.</span></span> <span data-ttu-id="391af-159">Discriminada de un tipo de unión, `OkOrException`, codifica el estado de error de la expresión, según se ha evaluado hasta ahora.</span><span class="sxs-lookup"><span data-stu-id="391af-159">A discriminated union type, `OkOrException`, encodes the error state of the expression as evaluated so far.</span></span> <span data-ttu-id="391af-160">Este código muestran varios patrones típicos que pueden usar en las expresiones de cálculo, como las implementaciones de reutilizable de algunos de los métodos de generador.</span><span class="sxs-lookup"><span data-stu-id="391af-160">This code demonstrates several typical patterns that you can use in your computation expressions, such as boilerplate implementations of some of the builder methods.</span></span>

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

<span data-ttu-id="391af-161">Una expresión de cálculo tiene un tipo subyacente, que devuelve la expresión.</span><span class="sxs-lookup"><span data-stu-id="391af-161">A computation expression has an underlying type, which the expression returns.</span></span> <span data-ttu-id="391af-162">El tipo subyacente puede representar un resultado calculado o un cálculo diferido que se pueden realizar, o puede proporcionar una manera para recorrer en iteración algún tipo de colección.</span><span class="sxs-lookup"><span data-stu-id="391af-162">The underlying type may represent a computed result or a delayed computation that can be performed, or it may provide a way to iterate through some type of collection.</span></span> <span data-ttu-id="391af-163">En el ejemplo anterior, el tipo subyacente era **finalmente**.</span><span class="sxs-lookup"><span data-stu-id="391af-163">In the previous example, the underlying type was **Eventually**.</span></span> <span data-ttu-id="391af-164">Para una expresión de secuencia, el tipo subyacente es <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="391af-164">For a sequence expression, the underlying type is <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.</span></span> <span data-ttu-id="391af-165">Para una expresión de consulta, el tipo subyacente es <xref:System.Linq.IQueryable?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="391af-165">For a query expression, the underlying type is <xref:System.Linq.IQueryable?displayProperty=nameWithType>.</span></span> <span data-ttu-id="391af-166">Un flujo de trabajo asincrónico, el tipo subyacente es [ `Async` ](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7).</span><span class="sxs-lookup"><span data-stu-id="391af-166">For an asychronous workflow, the underlying type is [`Async`](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7).</span></span> <span data-ttu-id="391af-167">La `Async` objeto representa el trabajo que se va a llevar a cabo para calcular el resultado.</span><span class="sxs-lookup"><span data-stu-id="391af-167">The `Async` object represents the work to be performed to compute the result.</span></span> <span data-ttu-id="391af-168">Por ejemplo, se llama a [ `Async.RunSynchronously` ](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) para ejecutar un cálculo y devolver el resultado.</span><span class="sxs-lookup"><span data-stu-id="391af-168">For example, you call [`Async.RunSynchronously`](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) to execute a computation and return the result.</span></span>

## <a name="custom-operations"></a><span data-ttu-id="391af-169">Operaciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="391af-169">Custom Operations</span></span>
<span data-ttu-id="391af-170">Puede definir una operación personalizada en una expresión de cálculo y usar una operación personalizada como un operador en una expresión de cálculo.</span><span class="sxs-lookup"><span data-stu-id="391af-170">You can define a custom operation on a computation expression and use a custom operation as an operator in a computation expression.</span></span> <span data-ttu-id="391af-171">Por ejemplo, puede incluir un operador de consulta en una expresión de consulta.</span><span class="sxs-lookup"><span data-stu-id="391af-171">For example, you can include a query operator in a query expression.</span></span> <span data-ttu-id="391af-172">Cuando se define una operación personalizada, debe definir el rendimiento y para los métodos de la expresión de cálculo.</span><span class="sxs-lookup"><span data-stu-id="391af-172">When you define a custom operation, you must define the Yield and For methods in the computation expression.</span></span> <span data-ttu-id="391af-173">Para definir una operación personalizada, póngalo en una clase de generador para la expresión de cálculo y, a continuación, aplique la [ `CustomOperationAttribute` ](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19).</span><span class="sxs-lookup"><span data-stu-id="391af-173">To define a custom operation, put it in a builder class for the computation expression, and then apply the [`CustomOperationAttribute`](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19).</span></span> <span data-ttu-id="391af-174">Este atributo toma una cadena como argumento, que es el nombre que se usará en una operación personalizada.</span><span class="sxs-lookup"><span data-stu-id="391af-174">This attribute takes a string as an argument, which is the name to be used in a custom operation.</span></span> <span data-ttu-id="391af-175">Este nombre se incluye en el ámbito en el inicio de la llave de apertura de la expresión de cálculo.</span><span class="sxs-lookup"><span data-stu-id="391af-175">This name comes into scope at the start of the opening curly brace of the computation expression.</span></span> <span data-ttu-id="391af-176">Por lo tanto, no debe usar identificadores que tienen el mismo nombre que una operación personalizada en este bloque.</span><span class="sxs-lookup"><span data-stu-id="391af-176">Therefore, you shouldn’t use identifiers that have the same name as a custom operation in this block.</span></span> <span data-ttu-id="391af-177">Por ejemplo, evite el uso de identificadores como `all` o `last` en expresiones de consulta.</span><span class="sxs-lookup"><span data-stu-id="391af-177">For example, avoid the use of identifiers such as `all` or `last` in query expressions.</span></span>

## <a name="see-also"></a><span data-ttu-id="391af-178">Vea también</span><span class="sxs-lookup"><span data-stu-id="391af-178">See Also</span></span>
[<span data-ttu-id="391af-179">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="391af-179">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="391af-180">Flujos de trabajo asincrónicos</span><span class="sxs-lookup"><span data-stu-id="391af-180">Asynchronous Workflows</span></span>](asynchronous-workflows.md)

[<span data-ttu-id="391af-181">Secuencias</span><span class="sxs-lookup"><span data-stu-id="391af-181">Sequences</span></span>](https://msdn.microsoft.com/library/6b773b6b-9c9a-4af8-bd9e-d96585c166db)

[<span data-ttu-id="391af-182">Expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="391af-182">Query Expressions</span></span>](query-expressions.md)
