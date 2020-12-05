---
title: Byrefs
description: 'Obtenga información sobre los tipos byref y tipo ByRef en F #, que se usan para la programación de bajo nivel.'
ms.date: 11/04/2019
ms.openlocfilehash: ff2c06d8940f7341d5d8b1d942be264bfac586c5
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "96740320"
---
# <a name="byrefs"></a>Byrefs

F # tiene dos áreas de características principales que se ocupan del espacio de programación de bajo nivel:

* Los `byref` / `inref` / `outref` tipos, que son punteros administrados. Tienen restricciones de uso para que no pueda compilar un programa que no sea válido en tiempo de ejecución.
* Un `byref` struct similar a, que es una [estructura](structures.md) que tiene una semántica similar y las mismas restricciones en tiempo de compilación que `byref<'T>` . Un ejemplo es <xref:System.Span%601> .

## <a name="syntax"></a>Syntax

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

## <a name="byref-inref-and-outref"></a>ByRef, inref y outref

Hay tres formas de `byref` :

* `inref<'T>`, un puntero administrado para leer el valor subyacente.
* `outref<'T>`, un puntero administrado para escribir en el valor subyacente.
* `byref<'T>`, un puntero administrado para leer y escribir el valor subyacente.

Se `byref<'T>` puede pasar una en la que `inref<'T>` se espera un. Del mismo modo, se `byref<'T>` puede pasar una en la que `outref<'T>` se espera un.

## <a name="using-byrefs"></a>Usar byrefs

Para usar un `inref<'T>` , debe obtener un valor de puntero con `&` :

```fsharp
open System

let f (dt: inref<DateTime>) =
    printfn $"Now: %O{dt}"

let usage =
    let dt = DateTime.Now
    f &dt // Pass a pointer to 'dt'
```

Para escribir en el puntero mediante `outref<'T>` o `byref<'T>` , también debe hacer el valor con el que se obtiene un puntero `mutable` .

```fsharp
open System

let f (dt: byref<DateTime>) =
    printfn $"Now: %O{dt}"
    dt <- DateTime.Now

// Make 'dt' mutable
let mutable dt = DateTime.Now

// Now you can pass the pointer to 'dt'
f &dt
```

Si solo está escribiendo el puntero en lugar de leerlo, considere la posibilidad `outref<'T>` de usar en lugar de `byref<'T>` .

### <a name="inref-semantics"></a>Semántica de Inref

Tenga en cuenta el código siguiente:

```fsharp
let f (x: inref<SomeStruct>) = x.SomeField
```

Semánticamente, esto significa lo siguiente:

* El titular del `x` puntero solo puede usarlo para leer el valor.
* Cualquier puntero adquirido a `struct` campos anidados en `SomeStruct` se proporciona de tipo `inref<_>` .

También se cumple lo siguiente:

* No hay ninguna implicación de que otros subprocesos o alias no tengan acceso de escritura a `x` .
* No hay ninguna implicación que `SomeStruct` sea inmutable en virtud de `x` ser una `inref` .

Sin embargo, para los tipos de valor de F # que **son** inmutables, el `this` puntero se deduce como `inref` .

Todas estas reglas juntas indican que el titular de un `inref` puntero no puede modificar el contenido inmediato de la memoria a la que se apunta.

### <a name="outref-semantics"></a>Semántica de Outref

El propósito de `outref<'T>` es indicar que el puntero solo debe escribirse en. De forma inesperada, `outref<'T>` permite leer el valor subyacente a pesar de su nombre. Esto es así por motivos de compatibilidad. Semánticamente, `outref<'T>` no es diferente de `byref<'T>` .

### <a name="interop-with-c"></a>Interoperabilidad con C\#

C# admite las `in ref` `out ref` palabras clave y, además de `ref` devoluciones. En la tabla siguiente se muestra cómo F # interpreta qué emite C#:

|Construcción de C#|Deduces de F #|
|------------|---------|
|`ref` valor devuelto|`outref<'T>`|
|`ref readonly` valor devuelto|`inref<'T>`|
|Parámetro `in ref`|`inref<'T>`|
|Parámetro `out ref`|`outref<'T>`|

En la tabla siguiente se muestra qué emite F #:

|Construcción de F #|Construcción emitida|
|------------|-----------------|
|Argumento `inref<'T>`|`[In]` atributo en argumento|
|`inref<'T>` devolver|`modreq` atributo en valor|
|`inref<'T>` en la ranura o la implementación abstracta|`modreq` argumento on o Return|
|Argumento `outref<'T>`|`[Out]` atributo en argumento|

### <a name="type-inference-and-overloading-rules"></a>Inferencia de tipos y reglas de sobrecarga

`inref<'T>`El compilador de F # infiere un tipo en los casos siguientes:

1. Un parámetro o tipo de valor devuelto de .NET que tiene un `IsReadOnly` atributo.
2. `this`Puntero en un tipo de estructura que no tiene campos mutables.
3. Dirección de una ubicación de memoria derivada de otro `inref<_>` puntero.

Cuando se está llevando a cabo una dirección implícita de un `inref` , se prefiere una sobrecarga con un argumento de tipo `SomeType` a una sobrecarga con un argumento de tipo `inref<SomeType>` . Por ejemplo:

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

En ambos casos, se resuelven las sobrecargas que toman en `System.DateTime` lugar de las sobrecargas que toman `inref<System.DateTime>` .

## <a name="byref-like-structs"></a>Structs similares a ByRef

Además de los `byref` / `inref` / `outref` tríos, puede definir sus propios Structs que pueden adherirse a la `byref` semántica similar. Esto se hace con el <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> atributo:

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

`IsByRefLike` no implica `Struct` . Ambos deben estar presentes en el tipo.

Un `byref` struct "similar" en F # es un tipo de valor enlazado a la pila. Nunca se asigna en el montón administrado. Un `byref` struct similar a es útil para la programación de alto rendimiento, ya que se aplica con un conjunto de comprobaciones fuertes sobre la duración y la no captura. Las reglas son:

* Se pueden usar como parámetros de función, parámetros de método, variables locales, devoluciones de métodos.
* No pueden ser miembros estáticos o de instancia de una clase o un struct normal.
* No se pueden capturar mediante ninguna construcción de cierre ( `async` métodos o expresiones lambda).
* No se pueden usar como parámetros genéricos.

Este último punto es fundamental para la programación de estilo de canalización de F #, como `|>` es una función genérica que parametriza sus tipos de entrada. Esta restricción puede ser relajada `|>` en el futuro, ya que está alineada y no realiza ninguna llamada a funciones genéricas no insertadas en su cuerpo.

Aunque estas reglas restringen el uso de forma rigurosa, lo hacen para satisfacer la promesa de la informática de alto rendimiento de una manera segura.

## <a name="byref-returns"></a>ByRef devuelve

ByRef devuelve de funciones o miembros de F # que se pueden generar y consumir. Cuando se utiliza un `byref` método que devuelve, el valor se desreferencia implícitamente. Por ejemplo:

```fsharp
let squareAndPrint (data : byref<int>) =
    let squared = data*data    // data is implicitly dereferenced
    printfn $"%d{squared}"
```

Para devolver un valor ByRef, la variable que contiene el valor debe ser más larga que el ámbito actual.
Además, para devolver ByRef, use `&value` (donde valor es una variable que reside más tiempo que el ámbito actual).

```fsharp
let mutable sum = 0
let safeSum (bytes: Span<byte>) =
    for i in 0 .. bytes.Length - 1 do
        sum <- sum + int bytes.[i]
    &sum  // sum lives longer than the scope of this function.
```

Para evitar la desreferenciación implícita, como pasar una referencia a través de varias llamadas encadenadas, use `&x` (donde `x` es el valor).

También puede asignar directamente a un valor devuelto `byref` . Considere el siguiente programa (muy imperativo):

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
    printfn $"Original sequence: %O{c}"

    let v = &c.FindLargestSmallerThan 16

    v <- v*2 // Directly assign to the byref return

    printfn $"New sequence:      %O{c}"

    0 // return an integer exit code
```

Éste es el resultado:

```console
Original sequence: 1 3 7 15 31 63 127 255 511 1023
New sequence:      1 3 7 30 31 63 127 255 511 1023
```

## <a name="scoping-for-byrefs"></a>Ámbito de byrefs

Un `let` valor enlazado a no puede tener su referencia superior al ámbito en el que se definió. Por ejemplo, no se permite lo siguiente:

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

Esto evita que se obtengan resultados diferentes en función de si se compila con optimizaciones o no.
