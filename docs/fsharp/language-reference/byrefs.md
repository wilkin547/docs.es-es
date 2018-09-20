---
title: 'Tipos de referencia (F #)'
description: 'Obtenga información sobre byref y similar a byref tipos en F #, que se usan para la programación de bajo nivel.'
ms.date: 09/02/2018
ms.openlocfilehash: 6131104e4325f77da84368c337f998c6b2b5309b
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2018
ms.locfileid: "46485488"
---
# <a name="byrefs"></a>Tipos de referencia

F # tiene dos áreas de características principales que se tratan en el espacio de la programación de bajo nivel:

* El `byref` / `inref` / `outref` tipos, que son los punteros administrados. Tienen restricciones de uso para que no se puede compilar un programa que no es válido en tiempo de ejecución.
* Un `byref`-como estructura, que es un [estructura](structures.md) que tiene una semántica similar y las mismas restricciones de tiempo de compilación que `byref<'T>`. Un ejemplo es <xref:System.Span%601>.

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

Un `byref<'T>` donde se puede pasar un `inref<'T>` se espera. De forma similar, un `byref<'T>` donde se puede pasar un `outref<'T>` se espera.

## <a name="using-byrefs"></a>Uso de tipos de referencia

Para usar un `inref<'T>`, deberá obtener un valor de puntero con `&`:

```fsharp
open System

let f (dt: inref<DateTime>) =
    printfn "Now: %s" (dt.ToString())

let dt = DateTime.Now
f &dt // Pass a pointer to 'dt'
```

Para escribir en el puntero mediante el uso de un `outref<'T>` o `byref<'T>`, también debe hacer que el valor tomar un puntero a `mutable`.

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

Si solo va a escribir el puntero en lugar de leerlo, considere el uso de `outref<'T>` en lugar de `byref<'T>`.

### <a name="inref-semantics"></a>Semántica de Inref

Observe el código siguiente:

```fsharp
let f (x: inref<SomeStruct>) = s.SomeField
```

Semánticamente, esto significa lo siguiente:

* El titular de la `x` puntero solo puede usar para leer el valor.
* Cualquier puntero adquiridos para `struct` campos anidados en `SomeStruct` tienen tipo `inref<_>`.

El siguiente también es cierto:

* No hay ninguna implicación que otros subprocesos o alias no tienen acceso de escritura a `x`.
* No hay ninguna implicación que `SomeStruct` es inmutable en virtud de `x` que se va a un `inref`.

Sin embargo, F # para tipos de valor que **son** inmutable, la `this` puntero se infiere para ser un `inref`.

Todas estas reglas juntas significan que el titular de un `inref` puntero no puede modificar el contenido de la memoria que se apunta inmediato.

### <a name="outref-semantics"></a>Semántica de Outref

El propósito de `outref<'T>` consiste en indicar que el puntero solo se debe leer desde. De forma inesperada, `outref<'T>` valor permite leer subyacente a pesar de su nombre. Esto es para fines de compatibilidad. Semánticamente, `outref<'T>` no es diferente a `byref<'T>`.

### <a name="interop-with-c"></a>Interoperabilidad con C# #

C# admite la `in ref` y `out ref` palabras clave, además de `ref` devuelve. En la tabla siguiente se muestra cómo F # interpreta qué C# emite:

|Construcción de C#|F # infiere|
|------------|---------|
|`ref` Valor devuelto|`outref<'T>`|
|`ref readonly` Valor devuelto|`inref<'T>`|
|`in ref` Parámetro|`inref<'T>`|
|`out ref` Parámetro|`outref<'T>`|

En la tabla siguiente se muestra lo que F # emite:

|Construcción de F #|Construcción emitido|
|------------|-----------------|
|`inref<'T>` argumento|`[In]` atributo de argumento|
|`inref<'T>` devolver|`modreq` atributo de valor|
|`inref<'T>` en la ranura abstracta o la implementación|`modreq` en el valor devuelto o argumento|
|`outref<'T>` argumento|`[Out]` atributo de argumento|

### <a name="type-inference-and-overloading-rules"></a>Inferencia de tipos y las reglas de sobrecarga

Un `inref<'T>` tipo se deduce el compilador de F # en los casos siguientes:

1. Un tipo de parámetro o valor devuelto de .NET que tiene un `IsReadOnly` atributo.
2. El `this` puntero en un tipo de estructura que no tiene ningún campo mutable.
3. La dirección de una ubicación de memoria que deriva de otro `inref<_>` puntero.

Cuando una dirección implícita de un `inref` se realiza, una sobrecarga con un argumento de tipo `SomeType` es preferible a una sobrecarga con un argumento de tipo `inref<SomeType>`. Por ejemplo:

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

## <a name="byref-like-structs"></a>Similar a ByRef structs

Además el `byref` / `inref` / `outref` trío, puede definir sus propias estructuras que pueden cumplir `byref`-como semántica. Esto se realiza con el <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> atributo:

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

`IsByRefLike` no implica `Struct`. Deben estar presentes en el tipo.

Un "`byref`-como" struct en F # es un tipo de valor de límite de la pila. Nunca se asigna en el montón administrado. Un `byref`-como struct es útil para la programación de alto rendimiento, ya que se aplica con el conjunto de controles sólidos sobre la duración y no captura. Las reglas son:

* Se puede usar como parámetros de función, parámetros de método, las variables locales, devuelve el método.
* Que no pueden ser estáticos o miembros de una clase o estructura normal de instancia.
* No se puede capturar cualquier construcción de cierre (`async` métodos o expresiones lambda).
* No se puede usar como un parámetro genérico.

Este último punto es fundamental para F # programación al estilo de la canalización, como `|>` es una función genérica que parametriza sus tipos de entrada. Esta restricción puede ser más flexible para `|>` en el futuro, tal como está en línea y no se realizan alguna llamada a funciones genéricas no alineada en el cuerpo.

Aunque estas reglas encarecidamente restringen el uso, lo hacen para cumplir la promesa de informática de alto rendimiento de una manera segura.

## <a name="byref-returns"></a>Devuelve ByRef

ByRef devuelve de las funciones de F # o los miembros pueden produce y consume. Al consumir un `byref`-método de devolución, el valor se ha desreferenciado implícitamente. Por ejemplo:

```fsharp
let safeSum(bytes: Span<byte>) =
    let mutable sum = 0
    for i in 0 .. bytes.Length - 1 do
        sum <- sum + int bytes.[i]
    sum

let sum = safeSum(mySpanOfBytes)
printfn "%d" sum // 'sum' is of type 'int'
```

Para evitar la desreferenciación implícito, por ejemplo, pasar una referencia a través de varias llamadas encadenadas, use `&x` (donde `x` es el valor).

Puede asignar directamente a una devolución `byref`. Considere el siguiente programa (muy imperativo):

```fsharp
type C() =
    let mutable nums = [| 1; 3; 7; 15; 31; 63; 127; 255; 511; 1023 |]

    override __.ToString() = String.Join(' ', nums)

    member __.FindLargestSmallerThan(target: int) =
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

## <a name="scoping-for-byrefs"></a>Definir el ámbito para los tipos de referencia

Un `let`-valor enlazado no puede tener su referencia superen el ámbito en el que se ha definido. Por ejemplo, se permite lo siguiente:

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

Esto evita que se obtengan resultados diferentes dependiendo de si se compila con las optimizaciones activado o desactivado.
