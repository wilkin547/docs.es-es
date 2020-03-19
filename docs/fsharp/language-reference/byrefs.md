---
title: Byrefs
description: Obtenga más información sobre los tipos byref y byref-like en F, que se utilizan para la programación de bajo nivel.
ms.date: 11/04/2019
ms.openlocfilehash: 527f465ee87fe153a2deae1306b6730531dc4123
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187049"
---
# <a name="byrefs"></a>Byrefs

F tiene dos áreas de características principales que se ocupa en el espacio de la programación de bajo nivel:

* `byref` / Los `inref` / tipos, que son punteros administrados. `outref` Tienen restricciones de uso para que no pueda compilar un programa que no sea válido en tiempo de ejecución.
* Una `byref`estructura -like, que es una [estructura](structures.md) que tiene una semántica `byref<'T>`similar y las mismas restricciones en tiempo de compilación que . Un ejemplo <xref:System.Span%601>es .

## <a name="syntax"></a>Sintaxis

```fsharp
// Byref types as parameters
let f (x: byref<'T>) = ()
let g (x: inref<'T>) = ()
let h (x: outref<'T>) = ()

// Calling a function with a byref parameter
let mutable x = 3
f &x

// Declaring a byref-like struct
open System.Runtime.CompilerServices

[<Struct; IsByRefLike>]
type S(count1: int, count2: int) =
    member x.Count1 = count1
    member x.Count2 = count2
```

## <a name="byref-inref-and-outref"></a>Byref, inref y outref

Hay tres formas `byref`de:

* `inref<'T>`, un puntero administrado para leer el valor subyacente.
* `outref<'T>`, un puntero administrado para escribir en el valor subyacente.
* `byref<'T>`, un puntero administrado para leer y escribir el valor subyacente.

A `byref<'T>` se puede `inref<'T>` pasar donde se espera un. Del mismo `byref<'T>` modo, se `outref<'T>` puede pasar a donde se espera un.

## <a name="using-byrefs"></a>Uso de byrefs

Para utilizar `inref<'T>`un , es necesario `&`obtener un valor de puntero con:

```fsharp
open System

let f (dt: inref<DateTime>) =
    printfn "Now: %s" (dt.ToString())

let usage =
    let dt = DateTime.Now
    f &dt // Pass a pointer to 'dt'
```

Para escribir en el `outref<'T>` puntero `byref<'T>`mediante un o , también debe `mutable`hacer que el valor que se captura un puntero a .

```fsharp
open System

let f (dt: byref<DateTime>) =
    printfn "Now: %s" (dt.ToString())
    dt <- DateTime.Now

// Make 'dt' mutable
let mutable dt = DateTime.Now

// Now you can pass the pointer to 'dt'
f &dt
```

Si solo está escribiendo el puntero en `outref<'T>` lugar `byref<'T>`de leerlo, considere la posibilidad de usar archivos en lugar de .

### <a name="inref-semantics"></a>Semántica inref

Observe el código siguiente:

```fsharp
let f (x: inref<SomeStruct>) = x.SomeField
```

Semánticamente, esto significa lo siguiente:

* El titular `x` del puntero solo puede usarlo para leer el valor.
* Cualquier puntero `struct` adquirido a `SomeStruct` los `inref<_>`campos anidados dentro se les da el tipo .

También se cumple lo siguiente:

* No hay ninguna implicación de que otros subprocesos o alias no tengan acceso de escritura a `x`.
* No hay implicación que `SomeStruct` sea inmutable en virtud de `x` ser un `inref`archivo .

Sin embargo, para los tipos de `this` valor de F que `inref` **son** inmutables, se deduce que el puntero es un archivo .

Todas estas reglas juntas significan que `inref` el titular de un puntero no puede modificar el contenido inmediato de la memoria que se apunta.

### <a name="outref-semantics"></a>Semántica de Outref

El propósito `outref<'T>` de es indicar que el puntero sólo debe escribirse en. Inesperadamente, `outref<'T>` permite leer el valor subyacente a pesar de su nombre. Esto es para fines de compatibilidad. Semánticamente, `outref<'T>` no es `byref<'T>`diferente de .

### <a name="interop-with-c"></a>Interoperabilidad con C\#

Además `in ref` de `out ref` las devoluciones, `ref` c. admite las palabras clave y, además de las devoluciones. En la tabla siguiente se muestra cómo f- interpreta lo que emite:

|Construcción de C-|Inferidos de F|
|------------|---------|
|`ref`valor de retorno|`outref<'T>`|
|`ref readonly`valor de retorno|`inref<'T>`|
|Parámetro `in ref`|`inref<'T>`|
|Parámetro `out ref`|`outref<'T>`|

En la tabla siguiente se muestra lo que emite F:

|Construcción de F -|Construcción emitida|
|------------|-----------------|
|Argumento `inref<'T>`|`[In]`atributo en el argumento|
|`inref<'T>`devolución|`modreq`atributo sobre el valor|
|`inref<'T>`en ranura abstracta o implementación|`modreq`sobre discusión o devolución|
|Argumento `outref<'T>`|`[Out]`atributo en el argumento|

### <a name="type-inference-and-overloading-rules"></a>Reglas de inferencia y sobrecarga de tipos

En `inref<'T>` los siguientes casos, el compilador de F - deduce un tipo:

1. Un parámetro o tipo de `IsReadOnly` valor devuelto de .NET que tiene un atributo.
2. El `this` puntero en un tipo struct que no tiene campos mutables.
3. La dirección de una ubicación `inref<_>` de memoria derivada de otro puntero.

Cuando se toma `inref` una dirección implícita de un, `SomeType` se prefiere una sobrecarga con `inref<SomeType>`un argumento de tipo a una sobrecarga con un argumento de tipo . Por ejemplo:

```fsharp
type C() =
    static member M(x: System.DateTime) = x.AddDays(1.0)
    static member M(x: inref<System.DateTime>) = x.AddDays(2.0)
    static member M2(x: System.DateTime, y: int) = x.AddDays(1.0)
    static member M2(x: inref<System.DateTime>, y: int) = x.AddDays(2.0)

let res = System.DateTime.Now
let v =  C.M(res)
let v2 =  C.M2(res, 4)
```

En ambos casos, las `System.DateTime` sobrecargas que toman `inref<System.DateTime>`se resuelven en lugar de las sobrecargas que toman .

## <a name="byref-like-structs"></a>Estructuras similares a referencias externas

Además `byref` / `inref` / `outref` del trío, puede definir sus propias estructuras que se adhieran a `byref`la semántica -como. Esto se hace <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> con el atributo:

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

`IsByRefLike`no implica `Struct`. Ambos deben estar presentes en el tipo.

Una`byref`estructura " -like" en F es un tipo de valor enlazado a la pila. Nunca se asigna en el montón administrado. Una `byref`estructura -like es útil para la programación de alto rendimiento, ya que se aplica con un conjunto de comprobaciones sólidas sobre la duración y la no captura. Las reglas son:

* Se pueden utilizar como parámetros de función, parámetros de método, variables locales, retornos de método.
* No pueden ser miembros estáticos o de instancia de una clase o estructura normal.
* No se pueden capturar mediante`async` ninguna construcción de cierre (métodos o expresiones lambda).
* No se pueden utilizar como parámetro genérico.

Este último punto es crucial para la `|>` programación de estilo de canalización de F, al igual que una función genérica que parametriza sus tipos de entrada. Esta restricción puede `|>` ser relajada para el futuro, ya que está en línea y no hace ninguna llamada a funciones genéricas no insertadas en su cuerpo.

Aunque estas reglas restringen fuertemente el uso, lo hacen para cumplir la promesa de la informática de alto rendimiento de una manera segura.

## <a name="byref-returns"></a>Devoluciones byref

Las devoluciones Byref de las funciones o miembros de F. se pueden producir y consumir. Al consumir `byref`un método -returning, el valor se desreferencia implícitamente. Por ejemplo:

```fsharp
let squareAndPrint (data : byref<int>) =
    let squared = data*data    // data is implicitly dereferenced
    printfn "%d" squared
```

Para devolver un valor byref, la variable que contiene el valor debe vivir más tiempo que el ámbito actual.
Además, para devolver `&value` byref, use (donde value es una variable que dura más que el ámbito actual).

```fsharp
let mutable sum = 0
let safeSum (bytes: Span<byte>) =
    for i in 0 .. bytes.Length - 1 do
        sum <- sum + int bytes.[i]
    &sum  // sum lives longer than the scope of this function.
```

Para evitar la desreferencia implícita, como pasar una `&x` referencia `x` a través de varias llamadas encadenadas, use (donde está el valor).

También puede asignar directamente `byref`a una devolución. Considere el siguiente programa (altamente imperativo):

```fsharp
type C() =
    let mutable nums = [| 1; 3; 7; 15; 31; 63; 127; 255; 511; 1023 |]

    override _.ToString() = String.Join(' ', nums)

    member _.FindLargestSmallerThan(target: int) =
        let mutable ctr = nums.Length - 1

        while ctr > 0 && nums.[ctr] >= target do ctr <- ctr - 1

        if ctr > 0 then &nums.[ctr] else &nums.[0]

[<EntryPoint>]
let main argv =
    let c = C()
    printfn "Original sequence: %s" (c.ToString())

    let v = &c.FindLargestSmallerThan 16

    v <- v*2 // Directly assign to the byref return

    printfn "New sequence:      %s" (c.ToString())

    0 // return an integer exit code
```

Éste es el resultado:

```console
Original sequence: 1 3 7 15 31 63 127 255 511 1023
New sequence:      1 3 7 30 31 63 127 255 511 1023
```

## <a name="scoping-for-byrefs"></a>Scoping para byrefs

Un `let`valor enlazado no puede hacer que su referencia supere el ámbito en el que se definió. Por ejemplo, no se permite lo siguiente:

```fsharp
let test2 () =
    let x = 12
    &x // Error: 'x' exceeds its defined scope!

let test () =
    let x =
        let y = 1
        &y // Error: `y` exceeds its defined scope!
    ()
```

Esto le impide obtener resultados diferentes dependiendo de si compila con optimizaciones o no.
