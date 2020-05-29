---
title: 'Novedades de F # 4,5-Guía de F #'
description: 'Obtenga información general sobre las nuevas características disponibles en F # 4,5.'
ms.date: 11/27/2019
ms.openlocfilehash: 2c978c66a4bf231398508cbc1cbb8839228ea8e9
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2020
ms.locfileid: "84202351"
---
# <a name="whats-new-in-f-45"></a>Novedades de F # 4,5

F # 4,5 agrega varias mejoras en el lenguaje F #. Muchas de estas características se agregaron juntas para que pueda escribir código eficaz en F #, al mismo tiempo que garantiza que este código es seguro. Esto significa agregar algunos conceptos al lenguaje y una cantidad significativa de análisis del compilador cuando se usan estas construcciones.

## <a name="get-started"></a>Introducción

F # 4,5 está disponible en todas las distribuciones de .NET Core y las herramientas de Visual Studio. Para obtener más información, [consulte Introducción a F #](../get-started/index.md) .

## <a name="span-and-byref-like-structs"></a>Structs de intervalo y de tipo ByRef

El <xref:System.Span%601> tipo introducido en .net Core le permite representar búferes en memoria de una manera fuertemente tipada, que ahora se permite en f # a partir de f # 4,5. En el ejemplo siguiente se muestra cómo se puede volver a usar una función que funciona en <xref:System.Span%601> con representaciones de búfer diferentes:

```fsharp
let safeSum (bytes: Span<byte>) =
    let mutable sum = 0
    for i in 0 .. bytes.Length - 1 do
        sum <- sum + int bytes.[i]
    sum

// managed memory
let arrayMemory = Array.zeroCreate<byte>(100)
let arraySpan = new Span<byte>(arrayMemory)

safeSum(arraySpan) |> printfn "res = %d"

// native memory
let nativeMemory = Marshal.AllocHGlobal(100);
let nativeSpan = new Span<byte>(nativeMemory.ToPointer(), 100)

safeSum(nativeSpan) |> printfn "res = %d"
Marshal.FreeHGlobal(nativeMemory)

// stack memory
let mem = NativePtr.stackalloc<byte>(100)
let mem2 = mem |> NativePtr.toVoidPtr
let stackSpan = Span<byte>(mem2, 100)

safeSum(stackSpan) |> printfn "res = %d"
```

Un aspecto importante es que el intervalo y otros [Structs similares a ByRef](../language-reference/structures.md#byreflike-structs) tienen un análisis estático muy rígido realizado por el compilador que restringen su uso de maneras que podría encontrar inesperado. Este es el equilibrio fundamental entre el rendimiento, la expresividad y la seguridad introducida en F # 4,5.

## <a name="revamped-byrefs"></a>Byrefs renovado

Antes de F # 4,5, [Byrefs](../language-reference/byrefs.md) en f # eran inseguros y desapareceban para numerosas aplicaciones. Los problemas de solidez en torno a byrefs se han solucionado en F # 4,5 y el mismo análisis estático realizado para las estructuras span y tipo ByRef también se ha aplicado.

### <a name="inreft-and-outreft"></a>inref< ' t> y outref< ' t>

Para representar la noción de un puntero administrado de solo lectura, de solo escritura y de lectura/escritura, F # 4,5 presenta los `inref<'T>` `outref<'T>` tipos, para representar los punteros de solo lectura y solo escritura, respectivamente. Cada una tiene una semántica diferente. Por ejemplo, no se puede escribir en un `inref<'T>` :

```fsharp
let f (dt: inref<DateTime>) =
    dt <- DateTime.Now // ERROR - cannot write to an inref!
```

De forma predeterminada, la inferencia de tipos deducirá punteros administrados como si `inref<'T>` estuvieran en línea con la naturaleza inmutable del código de F #, a menos que ya se haya declarado como mutable. Para hacer que se pueda escribir en algo, debe declarar un tipo como `mutable` antes de pasar su dirección a una función o miembro que lo manipule. Para obtener más información, consulte [Byrefs](../language-reference/byrefs.md).

## <a name="readonly-structs"></a>Estructuras readonly

A partir de F # 4,5, puede anotar un struct con <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute> como tal:

```fsharp
[<IsReadOnly; Struct>]
type S(count1: int, count2: int) =
    member x.Count1 = count1
    member x.Count2 = count2
```

Esto no le permite declarar un miembro mutable en el struct y emite metadatos que permiten que F # y C# lo traten como de solo lectura cuando se consumen de un ensamblado. Para obtener más información, vea [Structs de solo lectura](../language-reference/structures.md#readonly-structs).

## <a name="void-pointers"></a>Punteros void

El `voidptr` tipo se agrega a F # 4,5, al igual que las funciones siguientes:

* `NativePtr.ofVoidPtr`para convertir un puntero void en un puntero int nativo
* `NativePtr.toVoidPtr`para convertir un puntero int nativo en un puntero void

Esto resulta útil al interoperar con un componente nativo que hace uso de punteros void.

## <a name="the-match-keyword"></a>La palabra clave `match!`.

La `match!` palabra clave mejora la coincidencia de patrones cuando se encuentra dentro de una expresión de cálculo:

```fsharp
// Code that returns an asynchronous option
let checkBananaAsync (s: string) =
    async {
        if s = "banana" then
            return Some s
        else
            return None
    }

// Now you can use 'match!'
let funcWithString (s: string) =
    async {
        match! checkBananaAsync s with
        | Some bananaString -> printfn "It's banana!"
        | None -> printfn "%s" s
}
```

Esto permite acortar el código que suele implicar opciones de combinación (u otros tipos) con expresiones de cálculo como Async. Para obtener más información, vea [Match!](../language-reference/computation-expressions.md#match).

## <a name="relaxed-upcasting-requirements-in-array-list-and-sequence-expressions"></a>Requisitos de conversión relajada en las expresiones de matriz, lista y secuencia

La combinación de tipos en los que uno puede heredar de otro dentro de las expresiones de matriz, lista y secuencia solía haber requerido la conversión de cualquier tipo derivado a su tipo primario con `:>` o `upcast` . Esto ahora es relajado, como se muestra a continuación:

```fsharp
let x0 : obj list  = [ "a" ] // ok pre-F# 4.5
let x1 : obj list  = [ "a"; "b" ] // ok pre-F# 4.5
let x2 : obj list  = [ yield "a" :> obj ] // ok pre-F# 4.5

let x3 : obj list  = [ yield "a" ] // Now ok for F# 4.5, and can replace x2
```

## <a name="indentation-relaxation-for-array-and-list-expressions"></a>Flexibilización de la sangría para las expresiones de matriz y lista

Antes de F # 4,5, era necesario aplicar sangría excesiva a las expresiones de matriz y lista cuando se pasan como argumentos a las llamadas a métodos. Esto ya no es necesario:

```fsharp
module NoExcessiveIndenting =
    System.Console.WriteLine(format="{0}", arg = [|
        "hello"
    |])
    System.Console.WriteLine([|
        "hello"
    |])
```
