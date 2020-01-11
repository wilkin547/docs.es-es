---
title: Byrefs
description: Obtenga información sobre los tipos byref y tipo ByRef F#en, que se usan para la programación de bajo nivel.
ms.date: 11/04/2019
ms.openlocfilehash: 5aaee1e4eac9ce0d7e9ba89a2ab5f745d31367a0
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901311"
---
# <a name="byrefs"></a>Byrefs

F#tiene dos áreas de características principales que se ocupan del espacio de programación de bajo nivel:

* El /de `byref``inref`/tipos de `outref`, que son punteros administrados. Tienen restricciones de uso para que no pueda compilar un programa que no sea válido en tiempo de ejecución.
* Struct de tipo `byref`, que es una [estructura](structures.md) que tiene una semántica similar y las mismas restricciones en tiempo de compilación que `byref<'T>`. Un ejemplo es <xref:System.Span%601>.

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

## <a name="byref-inref-and-outref"></a>ByRef, inref y outref

Hay tres formas de `byref`:

* `inref<'T>`, un puntero administrado para leer el valor subyacente.
* `outref<'T>`, un puntero administrado para escribir en el valor subyacente.
* `byref<'T>`, un puntero administrado para leer y escribir el valor subyacente.

Se puede pasar una `byref<'T>` en la que se espera un `inref<'T>`. De forma similar, se puede pasar una `byref<'T>` en la que se espera un `outref<'T>`.

## <a name="using-byrefs"></a>Usar byrefs

Para usar un `inref<'T>`, debe obtener un valor de puntero con `&`:

```fsharp
open System

let f (dt: inref<DateTime>) =
    printfn "Now: %s" (dt.ToString())

let usage =
    let dt = DateTime.Now
    f &dt // Pass a pointer to 'dt'
```

Para escribir en el puntero mediante un `outref<'T>` o `byref<'T>`, también debe hacer el valor que obtiene un puntero a `mutable`.

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

Si solo está escribiendo el puntero en lugar de leerlo, considere la posibilidad de usar `outref<'T>` en lugar de `byref<'T>`.

### <a name="inref-semantics"></a>Semántica de Inref

Observe el código siguiente:

```fsharp
let f (x: inref<SomeStruct>) = x.SomeField
```

Semánticamente, esto significa lo siguiente:

* El titular del puntero `x` solo puede usarlo para leer el valor.
* Cualquier puntero adquirido a `struct` campos anidados en `SomeStruct` tiene un tipo `inref<_>`.

También se cumple lo siguiente:

* No hay ninguna implicación de que otros subprocesos o alias no tengan acceso de escritura a `x`.
* No hay ninguna implicación de que `SomeStruct` sea inmutable en virtud de `x` ser una `inref`.

Sin embargo, F# en el caso de los tipos de valor que **son** inmutables, el puntero de `this` se deduce como `inref`.

Todas estas reglas juntas indican que el titular de un puntero `inref` no puede modificar el contenido inmediato de la memoria a la que se apunta.

### <a name="outref-semantics"></a>Semántica de Outref

El propósito de `outref<'T>` es indicar que el puntero solo debe escribirse en. De forma inesperada, `outref<'T>` permite leer el valor subyacente a pesar de su nombre. Esto es así por motivos de compatibilidad. Semánticamente, `outref<'T>` no es diferente de `byref<'T>`.

### <a name="interop-with-c"></a>Interoperabilidad con C\#

C#admite las palabras clave `in ref` y `out ref`, además de `ref` devuelve. En la tabla siguiente se F# muestra cómo interpreta C# lo que emite:

|C#construir|F#deduce|
|------------|---------|
|`ref` valor devuelto|`outref<'T>`|
|`ref readonly` valor devuelto|`inref<'T>`|
|Parámetro `in ref`|`inref<'T>`|
|Parámetro `out ref`|`outref<'T>`|

En la tabla siguiente se F# muestra lo que emite:

|F#construir|Construcción emitida|
|------------|-----------------|
|Argumento `inref<'T>`|`[In]` atributo en el argumento|
|`inref<'T>` devolver|`modreq` atributo en el valor|
|`inref<'T>` en la ranura o la implementación abstracta|`modreq` argumento on o Return|
|Argumento `outref<'T>`|`[Out]` atributo en el argumento|

### <a name="type-inference-and-overloading-rules"></a>Inferencia de tipos y reglas de sobrecarga

El F# compilador deduce un tipo `inref<'T>` en los casos siguientes:

1. Un parámetro o tipo de valor devuelto de .NET que tiene un atributo `IsReadOnly`.
2. `this` puntero en un tipo de estructura que no tiene ningún campo mutable.
3. Dirección de una ubicación de memoria derivada de otro puntero `inref<_>`.

Cuando se está llevando a cabo una dirección implícita de un `inref`, se prefiere una sobrecarga con un argumento de tipo `SomeType` a una sobrecarga con un argumento de tipo `inref<SomeType>`. Por ejemplo:

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

En ambos casos, las sobrecargas que toman `System.DateTime` se resuelven en lugar de las sobrecargas que toman `inref<System.DateTime>`.

## <a name="byref-like-structs"></a>Structs similares a ByRef

Además de la `byref`/`inref`/de `outref` trío, puede definir sus propios Structs que pueden adherirse a la semántica similar a la de `byref`. Esto se hace con el atributo <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute>:

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

`IsByRefLike` no implica `Struct`. Ambos deben estar presentes en el tipo.

Un struct "`byref`" en F# es un tipo de valor enlazado a la pila. Nunca se asigna en el montón administrado. Una estructura de tipo `byref`es útil para la programación de alto rendimiento, ya que se aplica con un conjunto de comprobaciones fuertes sobre la duración y la no captura. Las reglas son las siguientes:

* Se pueden usar como parámetros de función, parámetros de método, variables locales, devoluciones de métodos.
* No pueden ser miembros estáticos o de instancia de una clase o un struct normal.
* No se pueden capturar con ninguna construcción de cierre (métodos`async` o expresiones lambda).
* No se pueden usar como parámetros genéricos.

Este último punto es fundamental para F# la programación de estilo de canalización, dado que `|>` es una función genérica que parametriza sus tipos de entrada. Esta restricción puede ser relajada para `|>` en el futuro, ya que está alineada y no realiza ninguna llamada a funciones genéricas no insertadas en su cuerpo.

Aunque estas reglas restringen el uso de forma rigurosa, lo hacen para satisfacer la promesa de la informática de alto rendimiento de una manera segura.

## <a name="byref-returns"></a>ByRef devuelve

ByRef devuelve de F# funciones o miembros que se pueden generar y consumir. Cuando se utiliza un método de devolución de `byref`, el valor se desreferencia implícitamente. Por ejemplo:

```fsharp
let safeSum(bytes: Span<byte>) =
    let mutable sum = 0
    for i in 0 .. bytes.Length - 1 do
        sum <- sum + int bytes.[i]
    sum

let sum = safeSum(mySpanOfBytes)
printfn "%d" sum // 'sum' is of type 'int'
```

Para evitar la desreferenciación implícita, como pasar una referencia a través de varias llamadas encadenadas, use `&x` (donde `x` es el valor).

También puede asignar directamente a un `byref`devuelto. Considere el siguiente programa (muy imperativo):

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

## <a name="scoping-for-byrefs"></a>Ámbito de byrefs

Un valor enlazado a `let`no puede tener su referencia superior al ámbito en el que se definió. Por ejemplo, no se permite lo siguiente:

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

Esto evita que se obtengan resultados diferentes en función de si se compila con las optimizaciones activadas o desactivadas.
