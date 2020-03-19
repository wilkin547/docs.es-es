---
title: Novedades de la Guía de F 4.5 - F
description: Obtenga una visión general de las nuevas características disponibles en F 4.5.
ms.date: 11/27/2019
ms.openlocfilehash: 560e3dd941f79b76d3b864ba0f6560be154ebc1a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186132"
---
# <a name="whats-new-in-f-45"></a>Novedades de la versión 4.5

F 4.5 agrega varias mejoras al lenguaje f. Muchas de estas características se agregaron juntas para permitirle escribir código eficaz en F , a la vez que garantiza que este código es seguro. Hacerlo significa agregar algunos conceptos al lenguaje y una cantidad significativa de análisis del compilador al usar estas construcciones.

## <a name="get-started"></a>Introducción

F 4.5 está disponible en todas las distribuciones de .NET Core y las herramientas de Visual Studio. [Empiece a utilizar F](../get-started/index.md) para obtener más información.

## <a name="span-and-byref-like-structs"></a>Estructuras similares a Span y byref

El <xref:System.Span%601> tipo introducido en .NET Core le permite representar los búferes en la memoria de una manera fuertemente tipada, que ahora se permite en F a partir de F 4.5. En el ejemplo siguiente se muestra cómo se <xref:System.Span%601> puede reutilizar una función que funciona en una con diferentes representaciones de búfer:

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

Un aspecto importante de esto es que Span y otras [estructuras byref-like](../language-reference/structures.md#byreflike-structs) tienen un análisis estático muy rígido realizado por el compilador que restringe su uso de maneras que pueda resultar inesperadas. Este es el equilibrio fundamental entre el rendimiento, la expresividad y la seguridad que se introduce en f 4.5.

## <a name="revamped-byrefs"></a>Retorciendo byrefs

Antes de f 4.5, [Byrefs](../language-reference/byrefs.md) en F - eran inseguros y no son sólidos para numerosas aplicaciones. Los problemas de solidez en torno a las referencias externas se han abordado en F 4.5 y también se aplicó el mismo análisis estático realizado para estructuras similares a span y byref.

### <a name="inreft-and-outreft"></a>inref<'T> y outref<'T>

Para representar la noción de un puntero administrado de solo lectura, de solo escritura `inref<'T>` `outref<'T>` y de lectura y escritura, F- 4.5 presenta los tipos , para representar punteros de solo lectura y de solo escritura, respectivamente. Cada uno tiene una semántica diferente. Por ejemplo, no se `inref<'T>`puede escribir en un :

```fsharp
let f (dt: inref<DateTime>) =
    dt <- DateTime.Now // ERROR - cannot write to an inref!
```

De forma predeterminada, la inferencia de `inref<'T>` tipos inferirá los punteros administrados como para estar en línea con la naturaleza inmutable del código de F, a menos que algo ya se haya declarado como mutable. Para hacer que algo se pueda escribir, deberá `mutable` declarar un tipo como antes de pasar su dirección a una función o miembro que lo manipula. Para obtener más información, consulte [Byrefs](../language-reference/byrefs.md).

## <a name="readonly-structs"></a>Estructuras Readonly

A partir de F 4.5, puede <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute> anotar una estructura con como tal:

```fsharp
[<IsReadOnly; Struct>]
type S(count1: int, count2: int) =
    member x.Count1 = count1
    member x.Count2 = count2
```

Esto no le permite declarar un miembro mutable en la estructura y emite metadatos que permiten que F- y C- para tratarlo como de solo lectura cuando se consume desde un ensamblado. Para obtener más información, consulte [Estructuras ReadOnly](../language-reference/structures.md#readonly-structs).

## <a name="void-pointers"></a>Punteros vacíos

El `voidptr` tipo se agrega a F 4.5, al igual que las siguientes funciones:

* `NativePtr.ofVoidPtr`para convertir un puntero void en un puntero int nativo
* `NativePtr.toVoidPtr`para convertir un puntero int nativo en un puntero void

Esto resulta útil cuando se interopera con un componente nativo que hace uso de punteros void.

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

Esto le permite acortar el código que a menudo implica opciones de mezcla (u otros tipos) con expresiones de cálculo como async. Para obtener más información, consulte [match!](../language-reference/computation-expressions.md#match).

## <a name="relaxed-upcasting-requirements-in-array-list-and-sequence-expressions"></a>Requisitos de upcasting relajados en expresiones de matriz, lista y secuencia

La mezcla de tipos en los que uno puede heredar de otro dentro de las expresiones `:>` de `upcast`matriz, lista y secuencia ha requerido tradicionalmente que se convierta cualquier tipo derivado a su tipo primario con o . Esto ahora es relajado, demostrado de la siguiente manera:

```fsharp
let x0 : obj list  = [ "a" ] // ok pre-F# 4.5
let x1 : obj list  = [ "a"; "b" ] // ok pre-F# 4.5
let x2 : obj list  = [ yield "a" :> obj ] // ok pre-F# 4.5

let x3 : obj list  = [ yield "a" ] // Now ok for F# 4.5, and can replace x2
```

## <a name="indentation-relaxation-for-array-and-list-expressions"></a>Relajación de sangría para expresiones de matriz y lista

Antes de F 4.5, era necesario aplicar sangría excesiva a las expresiones de matriz y lista cuando se pasaban como argumentos a las llamadas a métodos. Esto ya no es necesario:

```fsharp
module NoExcessiveIndenting =
    System.Console.WriteLine(format="{0}", arg = [|
        "hello"
    |])
    System.Console.WriteLine([|
        "hello"
    |])
```
