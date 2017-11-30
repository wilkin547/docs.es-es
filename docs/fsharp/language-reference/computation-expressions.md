---
title: "Expresiones de cálculo (F#)"
description: "Obtenga información acerca de cómo crear la sintaxis adecuada para escribir cálculos en F # que se pueden secuenciar y combinar mediante enlaces y construcciones de flujo de control."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: acabbf5d-fbb8-479f-894c-7251bf16c8c3
ms.openlocfilehash: 15ba2e167efc1d295d81439dcf85bc7272e05265
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="computation-expressions"></a>Expresiones de cálculo

Expresiones de cálculo en F # proporcionan una sintaxis adecuada para escribir cálculos que se pueden secuenciar y combinar mediante enlaces y construcciones de flujo de control. Pueden usarse para proporcionar una sintaxis adecuada para *monads*, una característica de programación funcional que puede usarse para administrar datos, control y efectos secundarios en programas funcionales.


## <a name="built-in-workflows"></a>Flujos de trabajo integrados
Expresiones de secuencia son un ejemplo de una expresión de cálculo, como flujos de trabajo asincrónicos y las expresiones de consulta. Para obtener más información, consulte [secuencias](sequences.md), [flujos de trabajo asincrónicos](asynchronous-workflows.md), y [expresiones de consulta](query-expressions.md).

Ciertas características comunes a las expresiones de secuencia y flujos de trabajo asincrónicos y muestran la sintaxis básica para una expresión de cálculo:

```fsharp
builder-name { expression }
```

La sintaxis anterior especifica que la expresión dada es una expresión de cálculo de un tipo especificado por *nombre de generador*. La expresión de cálculo puede ser un flujo de trabajo integrada, como `seq` o `async`, o puede ser algo que defina. El *nombre de generador* es el identificador de una instancia de un tipo especial conocida como el *tipo de generador*. El tipo de generador es un tipo de clase que define los métodos especiales que rigen la forma en que se combinan los fragmentos de la expresión de cálculo, es decir, código que controla cómo se ejecuta la expresión. Otra manera de describir una clase de generador consiste en indicar que permite personalizar la operación de muchas construcciones de F #, tales como bucles y enlaces.

En las expresiones de cálculo, dos formas están disponibles para algunas construcciones de lenguaje común. Puede invocar las construcciones variantes mediante una! (bang) como el sufijo en ciertas palabras clave, `let!`, `do!`, y así sucesivamente. Estos formatos especiales hacer que determinadas funciones definidas en la clase de generador para reemplazar el comportamiento integrado normal de estas operaciones. Estos formatos son similares a los `yield!` formada por el `yield` palabra clave que se utiliza en expresiones de secuencia. Para obtener más información, consulte [secuencias](sequences.md).


## <a name="creating-a-new-type-of-computation-expression"></a>Crear un nuevo tipo de expresión de cálculo
Puede definir las características de sus propias expresiones de cálculo mediante la creación de una clase de generador y definir ciertos métodos especiales en la clase. La clase de generador, opcionalmente, puede definir los métodos que se muestran en la tabla siguiente.

En la tabla siguiente se describe los métodos que pueden usarse en una clase de generador de flujo de trabajo.


|**Método**|**Signaturas típicas**|**Descripción**|
|----|----|----|
|`Bind`|`M<'T> * ('T -> M<'U>) -> M<'U>`|Piden `let!` y `do!` en expresiones de cálculo.|
|`Delay`|`(unit -> M<'T>) -> M<'T>`|Contiene una expresión de cálculo como una función.|
|`Return`|`'T -> M<'T>`|Piden `return` en expresiones de cálculo.|
|`ReturnFrom`|`M<'T> -> M<'T>`|Piden `return!` en expresiones de cálculo.|
|`Run`|`M<'T> -> M<'T>` o<br /><br />`M<'T> -> 'T`|Ejecuta una expresión de cálculo.|
|`Combine`|`M<'T> * M<'T> -> M<'T>` o<br /><br />`M<unit> * M<'T> -> M<'T>`|Se llama para las secuencias en las expresiones de cálculo.|
|`For`|`seq<'T> * ('T -> M<'U>) -> M<'U>` o<br /><br />`seq<'T> * ('T -> M<'U>) -> seq<M<'U>>`|Piden `for...do` expresiones en expresiones de cálculo.|
|`TryFinally`|`M<'T> * (unit -> unit) -> M<'T>`|Piden `try...finally` expresiones en expresiones de cálculo.|
|`TryWith`|`M<'T> * (exn -> M<'T>) -> M<'T>`|Piden `try...with` expresiones en expresiones de cálculo.|
|`Using`|`'T * ('T -> M<'U>) -> M<'U> when 'U :> IDisposable`|Piden `use` enlaces en expresiones de cálculo.|
|`While`|`(unit -> bool) * M<'T> -> M<'T>`|Piden `while...do` expresiones en expresiones de cálculo.|
|`Yield`|`'T -> M<'T>`|Piden `yield` expresiones en expresiones de cálculo.|
|`YieldFrom`|`M<'T> -> M<'T>`|Piden `yield!` expresiones en expresiones de cálculo.|
|`Zero`|`unit -> M<'T>`|Piden vacío `else` bifurcaciones de `if...then` expresiones en expresiones de cálculo.|
Muchos de los métodos de una clase de generador de usar y devolver un `M<'T>` construcción, que normalmente es un tipo definido por separado que caracteriza el tipo de cálculos que se combinan, por ejemplo, `Async<'T>` para flujos de trabajo asincrónicos y `Seq<'T>` para los flujos de trabajo de secuencia. Las firmas de estos métodos que puedan combinarse y anidarse entre sí, para que el objeto de flujo de trabajo devuelto por una construcción puede pasarse a la siguiente. El compilador, cuando analiza una expresión de cálculo, convierte la expresión en una serie de llamadas a funciones anidadas mediante los métodos de la tabla anterior y el código de la expresión de cálculo.

La expresión anidada es la forma siguiente:

```fsharp
builder.Run(builder.Delay(fun () -> {| cexpr |}))
```

En el código anterior, las llamadas a `Run` y `Delay` se omiten si no se definen en la clase de generador de expresiones de cálculo. El cuerpo de la expresión de cálculo, aquí se denomina `{| cexpr |}`, se convierten en llamadas relacionadas con los métodos de la clase de generador por las traducciones que se describe en la tabla siguiente. La expresión de cálculo `{| cexpr |}` está definido de forma recursiva según estas traducciones donde `expr` es una expresión de F # y `cexpr` es una expresión de cálculo.



|Expresión|Conversión|
|----------|-----------|
|<code>{&#124; let binding in cexpr &#124;}</code>|<code>let binding in {&#124; cexpr &#124;}</code>|
|<code>{&#124; let! pattern = expr in cexpr &#124;}</code>|<code>builder.Bind(expr, (fun pattern -> {&#124; cexpr &#124;}))</code>|
|<code>{&#124; do! expr in cexpr &#124;}</code>|<code>builder.Bind(expr, (fun () -> {&#124; cexpr &#124;}))</code>|
|<code>{&#124; yield expr &#124;}</code>|`builder.Yield(expr)`|
|<code>{&#124; yield! expr &#124;}</code>|`builder.YieldFrom(expr)`|
|<code>{&#124; return expr &#124;}<code>|`builder.Return(expr)`|
|<code>{&#124; return! expr &#124;}</code>|`builder.ReturnFrom(expr)`|
|<code>{&#124; use pattern = expr in cexpr &#124;}</code>|<code>builder.Using(expr, (fun pattern -> {&#124; cexpr &#124;}))</code>|
|<code>{&#124; use! value = expr in cexpr &#124;}</code>|<code>builder.Bind(expr, (fun value -> builder.Using(value, (fun value -> {&#124; cexpr &#124;}))))</code>|
|<code>{&#124; if expr then cexpr0 &#124;}</code>|<code>if expr then {&#124; cexpr0 &#124;} else binder.Zero()</code>|
|<code>{&#124; if expr then cexpr0 else cexpr1 &#124;}</code>|<code>if expr then {&#124; cexpr0 &#124;} else {&#124; cexpr1 &#124;}</code>|
|<code>{&#124; match expr with &#124; pattern_i -> cexpr_i &#124;}</code>|<code>match expr with &#124; pattern_i -> {&#124; cexpr_i &#124;}</code>|
|<code>{&#124; for pattern in expr do cexpr &#124;}</code>|<code>builder.For(enumeration, (fun pattern -> {&#124; cexpr &#124;}))</code>|
|<code>{&#124; for identifier = expr1 to expr2 do cexpr &#124;}<code>|<code>builder.For(enumeration, (fun identifier -> {&#124; cexpr &#124;}))</code>|
|<code>{&#124; while expr do cexpr &#124;}</code>|<code>builder.While(fun () -> expr), builder.Delay({&#124;cexpr &#124;})</code>|
|<code>{&#124; try cexpr with &#124; pattern_i -> expr_i &#124;}</code>|<code>builder.TryWith(builder.Delay({&#124; cexpr &#124;}), (fun value -> match value with &#124; pattern_i -> expr_i &#124; exn -> reraise exn)))</code>|
|<code>{&#124; try cexpr finally expr &#124;}</code>|<code>builder.TryFinally(builder.Delay( {&#124; cexpr &#124;}), (fun () -> expr))</code>|
|<code>{&#124; cexpr1; cexpr2 &#124;}</code>|<code>builder.Combine({&#124;cexpr1 &#124;}, {&#124; cexpr2 &#124;})</code>|
|<code>{&#124; other-expr; cexpr &#124;}</code>|<code>expr; {&#124; cexpr &#124;}</code>|
|<code>{&#124; other-expr &#124;}</code>|`expr; builder.Zero()`|
En la tabla anterior, `other-expr` describe una expresión que de lo contrario no se muestra en la tabla. Una clase de generador no es necesario implementar todos los métodos y admite todas las traducciones que se muestran en la tabla anterior. Las construcciones que no se implementan no están disponibles en las expresiones de cálculo de ese tipo. Por ejemplo, si no desea admitir la `use` palabra clave en las expresiones de cálculo, puede omitir la definición de `Use` en la clase de generador.

En el ejemplo de código siguiente se muestra una expresión de cálculo que encapsula un cálculo con una serie de pasos que se puede evaluar un paso a la vez. Discriminada de un tipo de unión, `OkOrException`, codifica el estado de error de la expresión, según se ha evaluado hasta ahora. Este código muestran varios patrones típicos que pueden usar en las expresiones de cálculo, como las implementaciones de reutilizable de algunos de los métodos de generador.

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

Una expresión de cálculo tiene un tipo subyacente, que devuelve la expresión. El tipo subyacente puede representar un resultado calculado o un cálculo diferido que se pueden realizar, o puede proporcionar una manera para recorrer en iteración algún tipo de colección. En el ejemplo anterior, el tipo subyacente era **finalmente**. Para una expresión de secuencia, el tipo subyacente es <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>. Para una expresión de consulta, el tipo subyacente es <xref:System.Linq.IQueryable?displayProperty=nameWithType>. Un flujo de trabajo asincrónico, el tipo subyacente es [ `Async` ](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7). La `Async` objeto representa el trabajo que se va a llevar a cabo para calcular el resultado. Por ejemplo, se llama a [ `Async.RunSynchronously` ](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) para ejecutar un cálculo y devolver el resultado.

## <a name="custom-operations"></a>Operaciones personalizadas
Puede definir una operación personalizada en una expresión de cálculo y usar una operación personalizada como un operador en una expresión de cálculo. Por ejemplo, puede incluir un operador de consulta en una expresión de consulta. Cuando se define una operación personalizada, debe definir el rendimiento y para los métodos de la expresión de cálculo. Para definir una operación personalizada, póngalo en una clase de generador para la expresión de cálculo y, a continuación, aplique la [ `CustomOperationAttribute` ](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19). Este atributo toma una cadena como argumento, que es el nombre que se usará en una operación personalizada. Este nombre se incluye en el ámbito en el inicio de la llave de apertura de la expresión de cálculo. Por lo tanto, no debe usar identificadores que tienen el mismo nombre que una operación personalizada en este bloque. Por ejemplo, evite el uso de identificadores como `all` o `last` en expresiones de consulta.

## <a name="see-also"></a>Vea también
[Referencia del lenguaje F#](index.md)

[Flujos de trabajo asincrónicos](asynchronous-workflows.md)

[Secuencias](https://msdn.microsoft.com/library/6b773b6b-9c9a-4af8-bd9e-d96585c166db)

[Expresiones de consulta](query-expressions.md)
