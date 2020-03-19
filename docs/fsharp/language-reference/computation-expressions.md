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
# <a name="computation-expressions"></a>Expresiones de cálculo

Las expresiones de cálculo en F- proporcionan una sintaxis conveniente para escribir cálculos que se pueden secuenciar y combinar mediante construcciones de flujo de control y enlaces. Dependiendo del tipo de expresión de cálculo, se pueden considerar como una forma de expresar monads, monoides, transformadores de monad y functores aplicativos. Sin embargo, a diferencia de otros lenguajes (como la notación de *doente* en Haskell), no están vinculados a una sola abstracción y no se basan en macros u otras formas de metaprogramación para lograr una sintaxis conveniente y sensible al contexto.

## <a name="overview"></a>Información general

Los cálculos pueden tomar muchas formas. La forma más común de cálculo es la ejecución de un solo subproceso, que es fácil de entender y modificar. Sin embargo, no todas las formas de cálculo son tan sencillas como la ejecución de un solo subproceso. Estos son algunos ejemplos:

- Cálculos no deterministas
- Cálculos asincrónicos
- Cálculos eficaces
- Cálculos generativos

De forma más general, hay cálculos *contextuales* que debe realizar en determinadas partes de una aplicación. Escribir código sensible al contexto puede ser difícil, ya que es fácil "filtrar" cálculos fuera de un contexto determinado sin abstracciones para evitar que lo haga. Estas abstracciones a menudo son difíciles de escribir por sí mismo, razón por la cual F tiene una forma generalizada de hacerlo **llamadas expresiones**de cálculo.

Las expresiones de cálculo ofrecen un modelo uniforme de sintaxis y abstracción para codificar cálculos contextuales.

Cada expresión de cálculo está respaldada por un tipo *de generador.* El tipo de generador define las operaciones que están disponibles para la expresión de cálculo. Consulte Creación de [un nuevo tipo de expresión de cálculo](computation-expressions.md#creating-a-new-type-of-computation-expression), que muestra cómo crear una expresión de cálculo personalizada.

### <a name="syntax-overview"></a>Información general sobre la sintaxis

Todas las expresiones de cálculo tienen la siguiente forma:

```fsharp
builder-expr { cexper }
```

donde `builder-expr` es el nombre de un tipo de `cexper` generador que define la expresión de cálculo y es el cuerpo de expresión de la expresión de cálculo. Por ejemplo, `async` el código de expresión de cálculo puede tener este aspecto:

```fsharp
let fetchAndDownload url =
    async {
        let! data = downloadData url

        let processedData = processData data

        return processedData
    }
```

Hay una sintaxis especial y adicional disponible dentro de una expresión de cálculo, como se muestra en el ejemplo anterior. Los siguientes formularios de expresión son posibles con expresiones de cálculo:

```fsharp
expr { let! ... }
expr { do! ... }
expr { yield ... }
expr { yield! ... }
expr { return ... }
expr { return! ... }
expr { match! ... }
```

Cada una de estas palabras clave y otras palabras clave estándar de F- solo están disponibles en una expresión de cálculo si se han definido en el tipo de generador de respaldo. La única excepción `match!`a esto es , que es `let!` en sí mismo azúcar sintáctico para el uso de seguido de una coincidencia de patrón en el resultado.

El tipo de generador es un objeto que define métodos especiales que rigen la forma en que se combinan los fragmentos de la expresión de cálculo; es decir, sus métodos controlan cómo se comporta la expresión de cálculo. Otra forma de describir una clase de generador es decir que permite personalizar el funcionamiento de muchas construcciones de F, como bucles y enlaces.

### `let!`

La `let!` palabra clave enlaza el resultado de una llamada a otra expresión de cálculo a un nombre:

```fsharp
let doThingsAsync url =
    async {
        let! data = getDataAsync url
        ...
    }
```

Si enlaza la llamada a `let`una expresión de cálculo con , no obtendrá el resultado de la expresión de cálculo. En su lugar, habrá enlazado el valor de la llamada *no realizada* a esa expresión de cálculo. Se `let!` usa para enlazar al resultado.

`let!`se define `Bind(x, f)` por el miembro en el tipo de generador.

### `do!`

La `do!` palabra clave es para llamar `unit`a una expresión `Zero` de cálculo que devuelve un tipo -like (definido por el miembro en el generador):

```fsharp
let doThingsAsync data url =
    async {
        do! submitData data url
        ...
    }
```

Para el flujo de `Async<unit>`trabajo [asincrónico,](asynchronous-workflows.md)este tipo es . Para otras expresiones de cálculo, `CExpType<unit>`es probable que el tipo sea .

`do!`se define `Bind(x, f)` por el miembro en `f` el `unit`tipo de generador, donde produce un archivo .

### `yield`

La `yield` palabra clave es para devolver un valor de la expresión <xref:System.Collections.Generic.IEnumerable%601>de cálculo para que se pueda consumir como:

```fsharp
let squares =
    seq {
        for i in 1..10 do
            yield i * i
    }

for sq in squares do
    printfn "%d" sq
```

En la mayoría de los casos, puede ser omitido por los llamadores. La forma más `yield` común de `->` omitir es con el operador:

```fsharp
let squares =
    seq {
        for i in 1..10 -> i * i
    }

for sq in squares do
    printfn "%d" sq
```

Para expresiones más complejas que pueden producir muchos valores diferentes, y tal vez condicionalmente, simplemente omitir la palabra clave puede hacer:

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

Al igual que con la [palabra clave yield en C,](../../csharp/language-reference/keywords/yield.md)cada elemento de la expresión de cálculo se devuelve a medida que se itera.

`yield`se define `Yield(x)` por el miembro en `x` el tipo de generador, donde está el elemento para devolver.

### `yield!`

La `yield!` palabra clave es para acoplar una colección de valores de una expresión de cálculo:

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

Cuando se evalúa, la `yield!` expresión de cálculo llamada por hará que sus elementos se retraen uno por uno, aplanando el resultado.

`yield!`se define `YieldFrom(x)` por el miembro en `x` el tipo de generador, donde hay una colección de valores.

A `yield` `yield!` diferencia de , debe especificarse explícitamente. Su comportamiento no está implícito en las expresiones de cálculo.

### `return`

La `return` palabra clave ajusta un valor en el tipo correspondiente a la expresión de cálculo. Aparte de `yield`las expresiones de cálculo que utilizan , se utiliza para "completar" una expresión de cálculo:

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        let! data = fetch url
        return data
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

`return`se define `Return(x)` por el miembro en `x` el tipo de generador, donde está el elemento que se va a ajustar.

### `return!`

La `return!` palabra clave realiza el valor de una expresión de cálculo y ajusta el tipo correspondiente a la expresión de cálculo:

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        return! fetch url
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

`return!`se define `ReturnFrom(x)` por el miembro en `x` el tipo de generador, donde hay otra expresión de cálculo.

### `match!`

La `match!` palabra clave le permite inlinear una llamada a otra expresión de cálculo y coincidencia de patrón en su resultado:

```fsharp
let doThingsAsync url =
    async {
        match! callService url with
        | Some data -> ...
        | None -> ...
    }
```

Al llamar a `match!`una expresión de cálculo con `let!`, se dará cuenta del resultado de la llamada como . Esto se utiliza a menudo cuando se llama a una expresión de cálculo donde el resultado es un [archivo .](options.md)

## <a name="built-in-computation-expressions"></a>Expresiones de cálculo integradas

La biblioteca principal de F - define tres expresiones de cálculo integradas: [Expresiones](sequences.md)de secuencia , Flujos de [trabajo asincrónicos](asynchronous-workflows.md)y [Expresiones](query-expressions.md)de consulta .

## <a name="creating-a-new-type-of-computation-expression"></a>Creación de un nuevo tipo de expresión de cálculo

Puede definir las características de sus propias expresiones de cálculo creando una clase de generador y definiendo ciertos métodos especiales en la clase. La clase de generador puede definir opcionalmente los métodos enumerados en la tabla siguiente.

En la tabla siguiente se describen los métodos que se pueden usar en una clase de generador de flujo de trabajo.

|**Método**|**Firma(s) típica(s)**|**Descripción**|
|----|----|----|
|`Bind`|`M<'T> * ('T -> M<'U>) -> M<'U>`|Llamado `let!` para `do!` y en expresiones de cálculo.|
|`Delay`|`(unit -> M<'T>) -> M<'T>`|Ajusta una expresión de cálculo como una función.|
|`Return`|`'T -> M<'T>`|Se `return` llama en expresiones de cálculo.|
|`ReturnFrom`|`M<'T> -> M<'T>`|Se `return!` llama en expresiones de cálculo.|
|`Run`|`M<'T> -> M<'T>` o<br /><br />`M<'T> -> 'T`|Ejecuta una expresión de cálculo.|
|`Combine`|`M<'T> * M<'T> -> M<'T>` o<br /><br />`M<unit> * M<'T> -> M<'T>`|Se ha llamado para la secuenciación en expresiones de cálculo.|
|`For`|`seq<'T> * ('T -> M<'U>) -> M<'U>` o<br /><br />`seq<'T> * ('T -> M<'U>) -> seq<M<'U>>`|Se `for...do` ha llamado a expresiones en expresiones de cálculo.|
|`TryFinally`|`M<'T> * (unit -> unit) -> M<'T>`|Se `try...finally` ha llamado a expresiones en expresiones de cálculo.|
|`TryWith`|`M<'T> * (exn -> M<'T>) -> M<'T>`|Se `try...with` ha llamado a expresiones en expresiones de cálculo.|
|`Using`|`'T * ('T -> M<'U>) -> M<'U> when 'T :> IDisposable`|Se `use` llama para enlaces en expresiones de cálculo.|
|`While`|`(unit -> bool) * M<'T> -> M<'T>`|Se `while...do` ha llamado a expresiones en expresiones de cálculo.|
|`Yield`|`'T -> M<'T>`|Se `yield` ha llamado a expresiones en expresiones de cálculo.|
|`YieldFrom`|`M<'T> -> M<'T>`|Se `yield!` ha llamado a expresiones en expresiones de cálculo.|
|`Zero`|`unit -> M<'T>`|Se llama `else` a `if...then` ramas vacías de expresiones en expresiones de cálculo.|
|`Quote`|`Quotations.Expr<'T> -> Quotations.Expr<'T>`|Indica que la expresión de `Run` cálculo se pasa al miembro como una cita. Traduce todas las instancias de un cálculo en una cita.|

Muchos de los métodos de una `M<'T>` clase de generador usan y devuelven una construcción, que suele ser `Async<'T>` un tipo `Seq<'T>` definido por separado que caracteriza el tipo de cálculos que se combinan, por ejemplo, para flujos de trabajo asincrónicos y para flujos de trabajo de secuencia. Las firmas de estos métodos permiten combinarlas y anidarlas entre sí, de modo que el objeto de flujo de trabajo devuelto por una construcción se puede pasar a la siguiente. El compilador, cuando analiza una expresión de cálculo, convierte la expresión en una serie de llamadas a funciones anidadas mediante los métodos de la tabla anterior y el código de la expresión de cálculo.

La expresión anidada tiene la siguiente forma:

```fsharp
builder.Run(builder.Delay(fun () -> {| cexpr |}))
```

En el código anterior, `Run` `Delay` las llamadas y se omiten si no están definidas en la clase del generador de expresiones de cálculo. El cuerpo de la expresión de `{| cexpr |}`cálculo, aquí denotado como , se traduce en llamadas que implican los métodos de la clase de generador por las traducciones descritas en la tabla siguiente. La expresión `{| cexpr |}` de cálculo se define de `expr` forma recursiva según estas traducciones, donde es una expresión de F y `cexpr` es una expresión de cálculo.

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

En la tabla `other-expr` anterior, se describe una expresión que no aparece de otro modo en la tabla. Una clase de generador no necesita implementar todos los métodos y admitir todas las traducciones enumeradas en la tabla anterior. Las construcciones que no se implementan no están disponibles en expresiones de cálculo de ese tipo. Por ejemplo, si no desea `use` admitir la palabra clave en las `Use` expresiones de cálculo, puede omitir la definición de en la clase de generador.

En el ejemplo de código siguiente se muestra una expresión de cálculo que encapsula un cálculo como una serie de pasos que se pueden evaluar paso a paso. Un tipo de `OkOrException`unión discriminado, , codifica el estado de error de la expresión tal como se ha evaluado hasta ahora. Este código muestra varios patrones típicos que puede usar en las expresiones de cálculo, como las implementaciones reutilizables de algunos de los métodos del generador.

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

Una expresión de cálculo tiene un tipo subyacente, que devuelve la expresión. El tipo subyacente puede representar un resultado calculado o un cálculo retrasado que se puede realizar, o puede proporcionar una manera de recorrer en iteración algún tipo de colección. En el ejemplo anterior, el tipo subyacente era **Eventually**. Para una expresión de secuencia, <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>el tipo subyacente es . Para una expresión de consulta, <xref:System.Linq.IQueryable?displayProperty=nameWithType>el tipo subyacente es . Para un flujo de trabajo [`Async`](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7)asincrónico, el tipo subyacente es . El `Async` objeto representa el trabajo que se va a realizar para calcular el resultado. Por ejemplo, [`Async.RunSynchronously`](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) se llama para ejecutar un cálculo y devolver el resultado.

## <a name="custom-operations"></a>Operaciones personalizadas

Puede definir una operación personalizada en una expresión de cálculo y utilizar una operación personalizada como operador en una expresión de cálculo. Por ejemplo, puede incluir un operador de consulta en una expresión de consulta. Al definir una operación personalizada, debe definir los métodos Yield y For en la expresión de cálculo. Para definir una operación personalizada, colóquela en una [`CustomOperationAttribute`](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19)clase de generador para la expresión de cálculo y, a continuación, aplique el archivo . Este atributo toma una cadena como argumento, que es el nombre que se usará en una operación personalizada. Este nombre entra en el ámbito al principio de la llave de apertura de la expresión de cálculo. Por lo tanto, no debe usar identificadores que tengan el mismo nombre que una operación personalizada en este bloque. Por ejemplo, evite el uso `all` de `last` identificadores como o en expresiones de consulta.

### <a name="extending-existing-builders-with-new-custom-operations"></a>Ampliación de los constructores existentes con nuevas operaciones personalizadas

Si ya tiene una clase de generador, sus operaciones personalizadas se pueden extender desde fuera de esta clase de generador. Las extensiones deben declararse en módulos. Los espacios de nombres no pueden contener miembros de extensión excepto en el mismo archivo y el mismo grupo de declaración de espacio de nombres donde se define el tipo.

En el ejemplo siguiente se `Microsoft.FSharp.Linq.QueryBuilder` muestra la extensión de la clase existente.

```fsharp
type Microsoft.FSharp.Linq.QueryBuilder with

    [<CustomOperation("existsNot")>]
    member _.ExistsNot (source: QuerySource<'T, 'Q>, predicate) =
        Enumerable.Any (source.Source, Func<_,_>(predicate)) |> not
```

## <a name="see-also"></a>Consulte también

- [Referencia del lenguaje f](index.md)
- [Flujos de trabajo asincrónicos](asynchronous-workflows.md)
- [Secuencias](https://msdn.microsoft.com/library/6b773b6b-9c9a-4af8-bd9e-d96585c166db)
- [Expresiones de consulta](query-expressions.md)
