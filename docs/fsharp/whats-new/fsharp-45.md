---
title: Novedades de F# 4,5- F# guía
description: Obtenga información general sobre las nuevas características disponibles en F# 4,5.
ms.date: 11/27/2019
ms.openlocfilehash: b699165125d345ad783b24da8a0a994cba72d4ba
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715689"
---
# <a name="whats-new-in-f-45"></a>Novedades de F# 4,5

F#4,5 agrega varias mejoras en el F# lenguaje. Muchas de estas características se agregaron juntas para que pueda escribir código eficaz en F# y, al mismo tiempo, garantizar la seguridad de este código. Esto significa agregar algunos conceptos al lenguaje y una cantidad significativa de análisis del compilador cuando se usan estas construcciones.

## <a name="get-started"></a>Primeros pasos

F#4,5 está disponible en todas las distribuciones de .NET Core y las herramientas de Visual Studio. Comience a usar para obtener más información. [ F# ](../get-started/index.md)

## <a name="span-and-byref-like-structs"></a>Structs de intervalo y de tipo ByRef

El tipo de <xref:System.Span%601> introducido en .NET Core le permite representar búferes en memoria de forma fuertemente tipada, que ahora se permite a F# partir de F# 4,5. En el ejemplo siguiente se muestra cómo se puede volver a usar una función que funciona en un <xref:System.Span%601> con representaciones de búfer diferentes:

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

Un aspecto importante es que el intervalo y otros [Structs similares a ByRef](../language-reference/structures.md#byreflike-structs) tienen un análisis estático muy rígido realizado por el compilador que restringen su uso de maneras que podría encontrar inesperado. Este es el equilibrio fundamental entre rendimiento, expresividad y seguridad que se introduce en F# 4,5.

## <a name="revamped-byrefs"></a>Byrefs renovado

Antes de F# 4,5, [Byrefs](../language-reference/byrefs.md) en F# eran no seguros y desapareceban para numerosas aplicaciones. Los problemas de sonido en torno a byrefs se F# han solucionado en 4,5 y el mismo análisis estático realizado para las estructuras span y tipo ByRef también se ha aplicado.

### <a name="inreft-and-outreft"></a>inref < ' t > y outref < ' t >

Para representar la noción de un puntero administrado de solo lectura, de solo escritura y de lectura/escritura, F# 4,5 presenta el `inref<'T>`, `outref<'T>` tipos para representar punteros de solo lectura y de solo escritura, respectivamente. Cada una tiene una semántica diferente. Por ejemplo, no puede escribir en una `inref<'T>`:

```fsharp
let f (dt: inref<DateTime>) =
    dt <- DateTime.Now // ERROR - cannot write to an inref!
```

De forma predeterminada, la inferencia de tipos inferirá los punteros administrados como `inref<'T>` para que estén en línea con F# la naturaleza inmutable del código, a menos que ya se haya declarado como mutable. Para hacer que se pueda escribir en algo, debe declarar un tipo como `mutable` antes de pasar su dirección a una función o miembro que lo manipule. Para obtener más información, consulte [Byrefs](../language-reference/byrefs.md).

## <a name="readonly-structs"></a>Structs de solo lectura

A partir F# de 4,5, puede anotar un struct con <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute> de la manera siguiente:

```fsharp
[<IsReadOnly; Struct>]
type S(count1: int, count2: int) =
    member x.Count1 = count1
    member x.Count2 = count2
```

Esto no le permite declarar un miembro mutable en el struct y emite metadatos que permiten F# y C# lo tratan como de solo lectura cuando se consumen de un ensamblado. Para obtener más información, vea [Structs de solo lectura](../language-reference/structures.md#readonly-structs).

## <a name="void-pointers"></a>Punteros void

El tipo de `voidptr` se agrega F# a 4,5, al igual que las siguientes funciones:

* `NativePtr.ofVoidPtr` para convertir un puntero void en un puntero int nativo
* `NativePtr.toVoidPtr` para convertir un puntero int nativo en un puntero void

Esto resulta útil al interoperar con un componente nativo que hace uso de punteros void.

## <a name="the-match-keyword"></a>La palabra clave `match!`.

La palabra clave `match!` mejora la coincidencia de patrones cuando se encuentra dentro de una expresión de cálculo:

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

La combinación de tipos en los que uno puede heredar de otro dentro de las expresiones de matriz, lista y secuencia solía haber requerido la conversión de cualquier tipo derivado a su tipo primario con `:>` o `upcast`. Esto ahora es relajado, como se muestra a continuación:

```fsharp
let x0 : obj list  = [ "a" ] // ok pre-F# 4.5
let x1 : obj list  = [ "a"; "b" ] // ok pre-F# 4.5
let x2 : obj list  = [ yield "a" :> obj ] // ok pre-F# 4.5

let x3 : obj list  = [ yield "a" ] // Now ok for F# 4.5, and can replace x2
```

## <a name="indentation-relaxation-for-array-and-list-expressions"></a>Flexibilización de la sangría para las expresiones de matriz y lista

Antes de F# 4,5, necesitaba aplicar sangría excesiva a las expresiones de matriz y lista cuando se pasaban como argumentos a las llamadas a métodos. Esto ya no es necesario:

```fsharp
module NoExcessiveIndenting = 
    System.Console.WriteLine(format="{0}", arg = [| 
        "hello"
    |])
    System.Console.WriteLine([|
        "hello"
    |])
```
