---
title: Expresiones de cálculo
description: 'Aprenda a crear una sintaxis adecuada para escribir cálculos en F # que se pueden secuenciar y combinar mediante construcciones y enlaces de flujo de control.'
ms.date: 08/15/2020
f1_keywords:
- let!_FS
ms.openlocfilehash: a0a71533ea1bc87b75f028ad0d416326f627672a
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "96739313"
---
# <a name="computation-expressions"></a>Expresiones de cálculo

Las expresiones de cálculo de F # proporcionan una sintaxis adecuada para escribir cálculos que se pueden secuenciar y combinar mediante construcciones y enlaces de flujo de control. En función del tipo de expresión de cálculo, se pueden considerar como una manera de expresar las funciones de Monoids, los transformadores de Monad y los procesos de ejecución. Sin embargo, a diferencia de otros lenguajes (como *la notación* de realización en Haskell), no están asociados a una abstracción única y no se basan en macros u otras formas de metaprogramaciones para lograr una sintaxis adecuada y sensible al contexto.

## <a name="overview"></a>Información general

Los cálculos pueden adoptar muchas formas. La forma más común de cálculo es la ejecución de un solo subproceso, que es fácil de entender y modificar. Sin embargo, no todas las formas de cálculo son tan sencillas como la ejecución de un solo subproceso. Estos son algunos ejemplos:

- Cálculos no deterministas
- Cálculos asincrónicos
- Cálculos con efecto
- Cálculos generativos

En general, hay cálculos *contextuales* que debe realizar en determinadas partes de una aplicación. La escritura de código dependiente del contexto puede ser desafiante, ya que es fácil "perder" los cálculos fuera de un contexto determinado sin abstracciones para evitar que lo haga. A menudo, estas abstracciones son difíciles de escribir por sí mismo, por lo que F # tiene una manera generalizada de hacerlo denominada **expresiones de cálculo**.

Las expresiones de cálculo ofrecen un modelo de abstracción y sintaxis uniformes para codificar cálculos contextuales.

Cada expresión de cálculo está respaldada por un tipo de *generador* . El tipo de generador define las operaciones que están disponibles para la expresión de cálculo. Vea [crear un nuevo tipo de expresión de cálculo](computation-expressions.md#creating-a-new-type-of-computation-expression), que muestra cómo crear una expresión de cálculo personalizada.

### <a name="syntax-overview"></a>Información general sobre la sintaxis

Todas las expresiones de cálculo tienen el formato siguiente:

```fsharp
builder-expr { cexper }
```

donde `builder-expr` es el nombre de un tipo de generador que define la expresión de cálculo y `cexper` es el cuerpo de la expresión de la expresión de cálculo. Por ejemplo, `async` el código de la expresión de cálculo puede tener el siguiente aspecto:

```fsharp
let fetchAndDownload url =
    async {
        let! data = downloadData url

        let processedData = processData data

        return processedData
    }
```

Hay una sintaxis especial adicional disponible en una expresión de cálculo, tal como se muestra en el ejemplo anterior. Las siguientes formas de expresión son posibles con las expresiones de cálculo:

```fsharp
expr { let! ... }
expr { do! ... }
expr { yield ... }
expr { yield! ... }
expr { return ... }
expr { return! ... }
expr { match! ... }
```

Cada una de estas palabras clave y otras palabras clave de F # estándar solo están disponibles en una expresión de cálculo si se han definido en el tipo de generador de respaldo. La única excepción a esto es `match!` que, a su vez, es el azúcar sintáctico para el uso de `let!` seguido de una coincidencia de patrones en el resultado.

El tipo de generador es un objeto que define métodos especiales que rigen la manera en que se combinan los fragmentos de la expresión de cálculo; es decir, sus métodos controlan el comportamiento de la expresión de cálculo. Otra manera de describir una clase de generador es decir que le permite personalizar el funcionamiento de muchas construcciones de F #, como bucles y enlaces.

### `let!`

La `let!` palabra clave enlaza el resultado de una llamada a otra expresión de cálculo con un nombre:

```fsharp
let doThingsAsync url =
    async {
        let! data = getDataAsync url
        ...
    }
```

Si enlaza la llamada a una expresión de cálculo con `let` , no obtendrá el resultado de la expresión de cálculo. En su lugar, habrá enlazado el valor de la llamada no *realizada* a esa expresión de cálculo. Use `let!` para enlazar con el resultado.

`let!` lo define el `Bind(x, f)` miembro en el tipo de generador.

### `do!`

La `do!` palabra clave es para llamar a una expresión de cálculo que devuelve un `unit` tipo similar (definido por el `Zero` miembro en el generador):

```fsharp
let doThingsAsync data url =
    async {
        do! submitData data url
        ...
    }
```

En el [flujo de trabajo asincrónico](asynchronous-workflows.md), este tipo es `Async<unit>` . En el caso de otras expresiones de cálculo, es probable que el tipo sea `CExpType<unit>` .

`do!` lo define el `Bind(x, f)` miembro en el tipo de generador, donde `f` produce una `unit` .

### `yield`

La `yield` palabra clave es para devolver un valor de la expresión de cálculo para que se pueda consumir como <xref:System.Collections.Generic.IEnumerable%601> :

```fsharp
let squares =
    seq {
        for i in 1..10 do
            yield i * i
    }

for sq in squares do
    printfn $"%d{sq}"
```

En la mayoría de los casos, se puede omitir mediante llamadores. La forma más común de omitir `yield` es con el `->` operador:

```fsharp
let squares =
    seq {
        for i in 1..10 -> i * i
    }

for sq in squares do
    printfn $"%d{sq}"
```

En el caso de expresiones más complejas que pueden dar lugar a muchos valores diferentes, y quizás condicionalmente, basta con omitir la palabra clave:

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

Como con la [palabra clave yield en C#](../../csharp/language-reference/keywords/yield.md), cada elemento de la expresión de cálculo se devuelve tal y como se recorre en iteración.

`yield` lo define el `Yield(x)` miembro en el tipo de generador, donde `x` es el elemento que se va a devolver.

### `yield!`

La `yield!` palabra clave es para aplanar una colección de valores de una expresión de cálculo:

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

printfn $"{squaresAndCubes}"  // Prints - 1; 4; 9; 1; 8; 27
```

Cuando se evalúa, la expresión de cálculo llamada por `yield!` tendrá sus elementos devueltos uno por uno y aplanando el resultado.

`yield!` lo define el `YieldFrom(x)` miembro en el tipo de generador, donde `x` es una colección de valores.

A diferencia `yield` de, `yield!` se debe especificar explícitamente. Su comportamiento no es implícito en las expresiones de cálculo.

### `return`

La `return` palabra clave ajusta un valor en el tipo correspondiente a la expresión de cálculo. Además de las expresiones de cálculo mediante `yield` , se usa para "completar" una expresión de cálculo:

```fsharp
let req = // 'req' is of type 'Async<data>'
    async {
        let! data = fetch url
        return data
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

`return` lo define el `Return(x)` miembro en el tipo de generador, donde `x` es el elemento que se va a ajustar.

### `return!`

La `return!` palabra clave obtiene el valor de una expresión de cálculo y ajusta el resultado en el tipo correspondiente a la expresión de cálculo:

```fsharp
let req = // 'req' is of type 'Async<data>'
    async {
        return! fetch url
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

`return!` lo define el `ReturnFrom(x)` miembro en el tipo de generador, donde `x` es otra expresión de cálculo.

### `match!`

La `match!` palabra clave permite alinear una llamada a otra expresión de cálculo y a la coincidencia de patrones en su resultado:

```fsharp
let doThingsAsync url =
    async {
        match! callService url with
        | Some data -> ...
        | None -> ...
    }
```

Al llamar a una expresión de cálculo con `match!` , se obtendrá el resultado de la llamada como `let!` . Esto se utiliza a menudo cuando se llama a una expresión de cálculo en la que el resultado es [opcional](options.md).

## <a name="built-in-computation-expressions"></a>Expresiones de cálculo integradas

La biblioteca básica de F # define tres expresiones de cálculo integradas: [expresiones de secuencia](sequences.md), [flujos de trabajo asincrónicos](asynchronous-workflows.md)y [expresiones de consulta](query-expressions.md).

## <a name="creating-a-new-type-of-computation-expression"></a>Crear un nuevo tipo de expresión de cálculo

Puede definir las características de sus propias expresiones de cálculo creando una clase de generador y definiendo ciertos métodos especiales en la clase. La clase de generador puede definir opcionalmente los métodos que se muestran en la tabla siguiente.

En la tabla siguiente se describen los métodos que se pueden utilizar en una clase de generador de flujo de trabajo.

|**Método**|**Firmas típicas**|**Descripción**|
|----|----|----|
|`Bind`|`M<'T> * ('T -> M<'U>) -> M<'U>`|Se llama para `let!` y `do!` en las expresiones de cálculo.|
|`Delay`|`(unit -> M<'T>) -> M<'T>`|Ajusta una expresión de cálculo como una función.|
|`Return`|`'T -> M<'T>`|Se llama para `return` en expresiones de cálculo.|
|`ReturnFrom`|`M<'T> -> M<'T>`|Se llama para `return!` en expresiones de cálculo.|
|`Run`|`M<'T> -> M<'T>` o<br /><br />`M<'T> -> 'T`|Ejecuta una expresión de cálculo.|
|`Combine`|`M<'T> * M<'T> -> M<'T>` o<br /><br />`M<unit> * M<'T> -> M<'T>`|Se llama para la secuenciación en expresiones de cálculo.|
|`For`|`seq<'T> * ('T -> M<'U>) -> M<'U>` o<br /><br />`seq<'T> * ('T -> M<'U>) -> seq<M<'U>>`|Se llama para `for...do` expresiones en expresiones de cálculo.|
|`TryFinally`|`M<'T> * (unit -> unit) -> M<'T>`|Se llama para `try...finally` expresiones en expresiones de cálculo.|
|`TryWith`|`M<'T> * (exn -> M<'T>) -> M<'T>`|Se llama para `try...with` expresiones en expresiones de cálculo.|
|`Using`|`'T * ('T -> M<'U>) -> M<'U> when 'T :> IDisposable`|Se llama para los `use` enlaces en expresiones de cálculo.|
|`While`|`(unit -> bool) * M<'T> -> M<'T>`|Se llama para `while...do` expresiones en expresiones de cálculo.|
|`Yield`|`'T -> M<'T>`|Se llama para `yield` expresiones en expresiones de cálculo.|
|`YieldFrom`|`M<'T> -> M<'T>`|Se llama para `yield!` expresiones en expresiones de cálculo.|
|`Zero`|`unit -> M<'T>`|Se llama para `else` ramas vacías de `if...then` expresiones en expresiones de cálculo.|
|`Quote`|`Quotations.Expr<'T> -> Quotations.Expr<'T>`|Indica que la expresión de cálculo se pasa al `Run` miembro como una expresión de código delimitada. Convierte todas las instancias de un cálculo en una expresión de código delimitada.|

Muchos de los métodos de una clase de generador usan y devuelven una `M<'T>` construcción, que suele ser un tipo definido por separado que caracteriza el tipo de cálculo que se combina, por ejemplo, `Async<'T>` para flujos de trabajo asincrónicos y `Seq<'T>` para flujos de trabajo de secuencia. Las firmas de estos métodos permiten que se combinen y se aniden entre sí, de modo que el objeto de flujo de trabajo devuelto de una construcción se pueda pasar al siguiente. El compilador, cuando analiza una expresión de cálculo, convierte la expresión en una serie de llamadas de función anidadas mediante los métodos de la tabla anterior y el código de la expresión de cálculo.

La expresión anidada tiene el formato siguiente:

```fsharp
builder.Run(builder.Delay(fun () -> {| cexpr |}))
```

En el código anterior, las llamadas a `Run` y `Delay` se omiten si no están definidas en la clase generador de expresiones de cálculo. El cuerpo de la expresión de cálculo, que se indica a continuación como `{| cexpr |}` , se traduce en llamadas que implican los métodos de la clase de generador mediante las traducciones descritas en la tabla siguiente. La expresión de cálculo `{| cexpr |}` se define de forma recursiva según estas traducciones `expr` , donde es una expresión de F # y `cexpr` es una expresión de cálculo.

|Expression|Traducción|
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

En la tabla anterior, `other-expr` describe una expresión que no se muestra en la tabla. No es necesario que una clase de generador implemente todos los métodos y admita todas las traducciones enumeradas en la tabla anterior. Las construcciones que no se implementan no están disponibles en las expresiones de cálculo de ese tipo. Por ejemplo, si no desea admitir la `use` palabra clave en las expresiones de cálculo, puede omitir la definición de `Use` en la clase de generador.

En el ejemplo de código siguiente se muestra una expresión de cálculo que encapsula un cálculo como una serie de pasos que se pueden evaluar un paso cada vez. Un tipo de Unión discriminada, `OkOrException` , codifica el estado de error de la expresión como evaluada hasta el momento. Este código muestra varios patrones típicos que puede usar en las expresiones de cálculo, como las implementaciones reutilizables de algunos de los métodos del generador.

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
        printfn $" x = %d{x}"
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

Una expresión de cálculo tiene un tipo subyacente, que devuelve la expresión. El tipo subyacente puede representar un resultado calculado o un cálculo retrasado que se puede realizar, o puede proporcionar una manera de recorrer en iteración algún tipo de colección. En el ejemplo anterior, el tipo subyacente era **finalmente**. En el caso de una expresión de secuencia, el tipo subyacente es <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> . En el caso de una expresión de consulta, el tipo subyacente es <xref:System.Linq.IQueryable?displayProperty=nameWithType> . Para un flujo de trabajo asincrónico, el tipo subyacente es [`Async`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-fsharpasync-1.html) . El `Async` objeto representa el trabajo que se va a realizar para calcular el resultado. Por ejemplo, se llama [`Async.RunSynchronously`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-fsharpasync.html#RunSynchronously) a para ejecutar un cálculo y devolver el resultado.

## <a name="custom-operations"></a>Operaciones personalizadas

Puede definir una operación personalizada en una expresión de cálculo y usar una operación personalizada como operador en una expresión de cálculo. Por ejemplo, puede incluir un operador de consulta en una expresión de consulta. Al definir una operación personalizada, debe definir los métodos Yield y for en la expresión de cálculo. Para definir una operación personalizada, colóquela en una clase de generador para la expresión de cálculo y, a continuación, aplique [`CustomOperationAttribute`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-customoperationattribute.html) . Este atributo toma una cadena como argumento, que es el nombre que se va a utilizar en una operación personalizada. Este nombre entra en el ámbito al principio de la llave de apertura de la expresión de cálculo. Por lo tanto, no debe usar identificadores que tengan el mismo nombre que una operación personalizada en este bloque. Por ejemplo, evite el uso de identificadores como `all` o `last` en expresiones de consulta.

### <a name="extending-existing-builders-with-new-custom-operations"></a>Extender los generadores existentes con nuevas operaciones personalizadas

Si ya tiene una clase de generador, sus operaciones personalizadas se pueden extender desde fuera de esta clase de generador. Las extensiones se deben declarar en los módulos. Los espacios de nombres no pueden contener miembros de extensión excepto en el mismo archivo y el mismo grupo de declaraciones de espacio de nombres en el que se define el tipo.

En el ejemplo siguiente se muestra la extensión de la `FSharp.Linq.QueryBuilder` clase existente.

```fsharp
type FSharp.Linq.QueryBuilder with

    [<CustomOperation("existsNot")>]
    member _.ExistsNot (source: QuerySource<'T, 'Q>, predicate) =
        Enumerable.Any (source.Source, Func<_,_>(predicate)) |> not
```

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
- [Flujos de trabajo asincrónicos](asynchronous-workflows.md)
- [Secuencias](sequences.md)
- [Expresiones de consulta](query-expressions.md)
