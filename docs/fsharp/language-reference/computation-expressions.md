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
# <a name="computation-expressions"></a>Expresiones de cálculo

Las expresiones de cálculo en F# proporcionan una sintaxis adecuada para escribir cálculos que se pueden secuenciar y combinar mediante enlaces y construcciones de flujo de control. Según el tipo de expresión de cálculo, puede considerarse como una forma de expresar monads, monoids, transformadores monad y functors desplazados. Sin embargo, a diferencia de otros lenguajes (como *notación* en Haskell), que no están asociados a una sola abstracción y no confíe en las macros u otras formas de metaprogramación para lograr una sintaxis adecuada y contextual.

## <a name="overview"></a>Información general

Los cálculos pueden adoptar muchas formas. La forma más común de cálculo es un único subproceso de ejecución, que es fácil de entender y modificar. Sin embargo, no todas las formas de cálculo son tan sencillas como la ejecución de subproceso único. Estos son algunos ejemplos:

* Cálculos no deterministas
* Cálculos asincrónicos
* Cálculos effectful
* Cálculos generativas

Por lo general, hay *contextual* cálculos que se deben realizar en determinadas partes de una aplicación. Puede resultar complicado la escritura de código contextual, puesto que es fácil para los cálculos de "pérdida" fuera de un contexto determinado sin abstracciones para evitar que lo hagan. Estas abstracciones a menudo son difíciles de escribir por sí mismo, motivo por el cual F# tiene de forma generalizada llamados **expresiones de cálculo**.

Las expresiones de cálculo ofrecen un modelo de sintaxis y abstracción uniforme para codificación cálculos contextuales.

Cada expresión de cálculo está respaldado por un *generador* tipo. El tipo de generador define las operaciones que están disponibles para la expresión de cálculo. Consulte [creación de un tipo de expresión de cálculo nueva](computation-expressions.md#creating-a-new-type-of-computation-expression), que muestra cómo crear una expresión de cálculo personalizado.

### <a name="syntax-overview"></a>Información general de sintaxis

Todas las expresiones de cálculo tienen el formato siguiente:

```
builder-expr { cexper }
```

donde `builder-expr` es el nombre de un tipo de generador que define la expresión de cálculo y `cexper` es el cuerpo de expresión de la expresión de cálculo. Por ejemplo, `async` código de la expresión de cálculo puede tener este aspecto:

```fsharp
let fetchAndDownload url =
    async {
        let! data = downloadData url

        let processedData = processData data

        return processedData
    }
```

Hay una sintaxis especial y adicional disponibles dentro de una expresión de cálculo, como se muestra en el ejemplo anterior. Los siguientes formatos de expresión son posibles con las expresiones de cálculo:

```fsharp
expr { let! ... }
expr { do! ... }
expr { yield ... }
expr { yield! ... }
expr { return ... }
expr { return! ... }
expr { match! ... }
```

Cada una de estas palabras clave y otras palabras clave de F# estándar solo están disponibles en una expresión de cálculo si se han definido en el tipo de generador de respaldo. La única excepción a esto es `match!`, que es en sí mismo azúcar sintáctica para el uso de `let!` seguida por una coincidencia de patrones en el resultado.

El tipo de generador es un objeto que define los métodos especiales que rigen la manera en que se combinan los fragmentos de la expresión de cálculo; es decir, sus métodos controlan cómo se comporta la expresión de cálculo. Es decir que permite personalizar la operación de muchas construcciones de F#, como bucles y enlaces de otra manera de describir una clase de generador.

### `let!`

El `let!` palabra clave enlaza el resultado de una llamada a otra expresión de cálculo a un nombre:

```fsharp
let doThingsAsync url =
    async {
        let! data = getDataAsync url
        ...
    }
```

Si enlaza la llamada a una expresión de cálculo con `let`, no obtendrá el resultado de la expresión de cálculo. En su lugar, habrá enlazado el valor de la *no realizado* la llamada a esa expresión de cálculo. Use `let!` para enlazar con el resultado.

`let!` se define mediante el `Bind(x, f)` miembro en el tipo de generador.

### `do!`

El `do!` palabra clave es para llamar a una expresión de cálculo que devuelve un `unit`-como tipo (definido por el `Zero` miembro en el generador de):

```fsharp
let doThingsAsync data url =
    async {
        do! submitData data url
        ...
    }
```

Para el [flujo de trabajo asincrónico](asynchronous-workflows.md), este tipo es `Async<unit>`. Para otras expresiones de cálculo, es probable que sea el tipo `CExpType<unit>`.

`do!` se define mediante el `Bind(x, f)` miembro en el tipo de generador donde `f` genera un `unit`.

### `yield`

El `yield` palabra clave es para devolver un valor de la expresión de cálculo para que se puede consumir como un <xref:System.Collections.Generic.IEnumerable%601>:

```fsharp
let squares =
    seq {
        for i in 1..10 do
            yield i * i
    }

for sq in squares do
    printfn "%d" sq
```

Igual que con el [producen la palabra clave en C#](../../csharp/language-reference/keywords/yield.md), cada elemento de la expresión de cálculo se cede a medida que se recorre en iteración.

`yield` se define mediante el `Yield(x)` miembro en el tipo de generador, donde `x` es el elemento para producir de nuevo.

### `yield!`

El `yield!` palabra clave es para acoplar una colección de valores de una expresión de cálculo:

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

Cuando se evalúa, llama la expresión de cálculo `yield!` habrá sus elementos produjo espera uno por uno, acoplar el resultado.

`yield!` se define mediante el `YieldFrom(x)` miembro en el tipo de generador, donde `x` es una colección de valores.

### `return`

El `return` palabra clave incluye un valor en el tipo correspondiente a la expresión de cálculo. Aparte de las expresiones de cálculo mediante `yield`, se usa para "completar" una expresión de cálculo:

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        let! data = fetch url
        return data
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

`return` se define mediante el `Return(x)` miembro en el tipo de generador, donde `x` es el elemento que se va a ajustar.

### `return!`

El `return!` palabra clave, el valor de una expresión de cálculo de realización y ajusta ese resultado en el tipo correspondiente a la expresión de cálculo:

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        return! fetch url
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

`return!` se define mediante el `ReturnFrom(x)` miembro en el tipo de generador, donde `x` es otra expresión de cálculo.

### `match!`

A partir de F# 4.5, el `match!` palabra clave permite a en línea una llamada a otra coincidencia de expresión y el patrón de cálculo con su resultado:

```fsharp
let doThingsAsync url =
    async {
        match! callService url with
        | Some data -> ...
        | None -> ...
    }
```

Al llamar a una expresión de cálculo con `match!`, obtendrá el resultado de la llamada como `let!`. Esto se suele usar cuando se llama a una expresión de cálculo donde el resultado es un [opcional](options.md).

## <a name="built-in-computation-expressions"></a>Expresiones de cálculo integradas

La biblioteca básica de F# define tres expresiones de cálculo integradas: [las expresiones de secuencia](sequences.md), [flujos de trabajo asincrónicos](asynchronous-workflows.md), y [las expresiones de consulta](query-expressions.md).

## <a name="creating-a-new-type-of-computation-expression"></a>Crear un nuevo tipo de expresión de cálculo

Puede definir las características de sus propias expresiones de cálculo mediante la creación de una clase de generador y define algunos métodos especiales en la clase. La clase de generador, opcionalmente, puede definir los métodos, como se muestra en la tabla siguiente.

En la tabla siguiente se describe los métodos que pueden usarse en una clase de generador de flujo de trabajo.

|**Método**|**Signaturas típicas**|**Descripción**|
|----|----|----|
|`Bind`|`M<'T> * ('T -> M<'U>) -> M<'U>`|Llamado para `let!` y `do!` en expresiones de cálculo.|
|`Delay`|`(unit -> M<'T>) -> M<'T>`|Contiene una expresión de cálculo como una función.|
|`Return`|`'T -> M<'T>`|Llamado para `return` en expresiones de cálculo.|
|`ReturnFrom`|`M<'T> -> M<'T>`|Llamado para `return!` en expresiones de cálculo.|
|`Run`|`M<'T> -> M<'T>`, o bien<br /><br />`M<'T> -> 'T`|Ejecuta una expresión de cálculo.|
|`Combine`|`M<'T> * M<'T> -> M<'T>`, o bien<br /><br />`M<unit> * M<'T> -> M<'T>`|Se llama para la secuenciación en expresiones de cálculo.|
|`For`|`seq<'T> * ('T -> M<'U>) -> M<'U>`, o bien<br /><br />`seq<'T> * ('T -> M<'U>) -> seq<M<'U>>`|Llamado para `for...do` expresiones en expresiones de cálculo.|
|`TryFinally`|`M<'T> * (unit -> unit) -> M<'T>`|Llamado para `try...finally` expresiones en expresiones de cálculo.|
|`TryWith`|`M<'T> * (exn -> M<'T>) -> M<'T>`|Llamado para `try...with` expresiones en expresiones de cálculo.|
|`Using`|`'T * ('T -> M<'U>) -> M<'U> when 'U :> IDisposable`|Llamado para `use` enlaces en expresiones de cálculo.|
|`While`|`(unit -> bool) * M<'T> -> M<'T>`|Llamado para `while...do` expresiones en expresiones de cálculo.|
|`Yield`|`'T -> M<'T>`|Llamado para `yield` expresiones en expresiones de cálculo.|
|`YieldFrom`|`M<'T> -> M<'T>`|Llamado para `yield!` expresiones en expresiones de cálculo.|
|`Zero`|`unit -> M<'T>`|Llamado para vacío `else` ramas de `if...then` expresiones en expresiones de cálculo.|

Muchos de los métodos en una clase de generador usan y devuelven un `M<'T>` construcción, que normalmente es un tipo definido por separado que caracteriza el tipo de cálculos que se va a combinar, por ejemplo, `Async<'T>` para flujos de trabajo asincrónicos y `Seq<'T>` para los flujos de trabajo de secuencia. Las firmas de estos métodos que puedan combinarse y anidarse entre sí, para que el objeto de flujo de trabajo devuelto por una construcción puede pasarse a la siguiente. El compilador, cuando analiza una expresión de cálculo, convierte la expresión en una serie de llamadas de función anidada utilizando los métodos en la tabla anterior y el código de la expresión de cálculo.

La expresión anidada tiene el formato siguiente:

```fsharp
builder.Run(builder.Delay(fun () -> {| cexpr |}))
```

En el código anterior, las llamadas a `Run` y `Delay` se omite si no están definidos en la clase de generador de expresiones de cálculo. El cuerpo de la expresión de cálculo, aquí se indica como `{| cexpr |}`, se convierten en llamadas que implican los métodos de la clase de generador por las traducciones se describe en la tabla siguiente. La expresión de cálculo `{| cexpr |}` está definido de forma recursiva según estas traducciones donde `expr` es una expresión de F# y `cexpr` es una expresión de cálculo.

|Expresión|Conversión|
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
En la tabla anterior, `other-expr` describe una expresión que en caso contrario, no se muestra en la tabla. Una clase de generador no es necesario implementar todos los métodos y admite todas las traducciones que se muestran en la tabla anterior. Las construcciones que no se implementan no están disponibles en las expresiones de cálculo de ese tipo. Por ejemplo, si no desea admitir la `use` palabra clave en las expresiones de cálculo, puede omitir la definición de `Use` en la clase de generador.

El ejemplo de código siguiente muestra una expresión de cálculo que encapsula un cálculo con una serie de pasos que se puede evaluar un paso a la vez. Un tipo de unión, de discriminadas `OkOrException`, codifica el estado de error de la expresión evalúa hasta ahora. Este código muestra varios patrones típicos que puede usar en las expresiones de cálculo, como son implementaciones reutilizables de algunos de los métodos del generador.

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

Una expresión de cálculo tiene un tipo subyacente, que devuelve la expresión. El tipo subyacente puede representar un resultado calculado o un cálculo diferido que se puede realizar, o puede proporcionar una manera de recorrer en iteración a través de algún tipo de colección. En el ejemplo anterior, el tipo subyacente era **finalmente**. Una expresión de secuencia, el tipo subyacente es <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>. Una expresión de consulta, el tipo subyacente es <xref:System.Linq.IQueryable?displayProperty=nameWithType>. Para un flujo de trabajo asincrónico, el tipo subyacente es [ `Async` ](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7). La `Async` objeto representa el trabajo que se realizará para calcular el resultado. Por ejemplo, se llama [ `Async.RunSynchronously` ](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) para ejecutar un cálculo y devolver el resultado.

## <a name="custom-operations"></a>Operaciones personalizadas

Puede definir una operación personalizada en una expresión de cálculo y utilizar una operación personalizada como un operador en una expresión de cálculo. Por ejemplo, puede incluir un operador de consulta en una expresión de consulta. Al definir una operación personalizada, debe definir el rendimiento y para los métodos en la expresión de cálculo. Para definir una operación personalizada, colocarlo en una clase de generador para la expresión de cálculo y, a continuación, aplique el [ `CustomOperationAttribute` ](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19). Este atributo toma una cadena como argumento, que es el nombre que se usará en una operación personalizada. Este nombre entra en el ámbito del principio de la llave de apertura de la expresión de cálculo. Por lo tanto, no debería utilizar identificadores que tienen el mismo nombre que una operación personalizada de este bloque. Por ejemplo, evite el uso de identificadores como `all` o `last` en expresiones de consulta.

### <a name="extending-existing-builders-with-new-custom-operations"></a>Extender los generadores de existentes con nuevas operaciones personalizadas

Si ya tiene una clase de generador, se pueden ampliar sus operaciones personalizadas desde fuera de esta clase de generador. Las extensiones se deben declarar en módulos. Los espacios de nombres no pueden contener a miembros de extensión, excepto en el mismo archivo y el mismo grupo de declaración de espacio de nombres donde se define el tipo.

El ejemplo siguiente muestra la extensión de la existente `Microsoft.FSharp.Linq.QueryBuilder` clase.

```fsharp
type Microsoft.FSharp.Linq.QueryBuilder with

    [<CustomOperation("existsNot")>]
    member __.ExistsNot (source: QuerySource<'T, 'Q>, predicate) =
        Enumerable.Any (source.Source, Func<_,_>(predicate)) |> not
```

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
- [Flujos de trabajo asincrónicos](asynchronous-workflows.md)
- [Secuencias](https://msdn.microsoft.com/library/6b773b6b-9c9a-4af8-bd9e-d96585c166db)
- [Expresiones de consulta](query-expressions.md)
