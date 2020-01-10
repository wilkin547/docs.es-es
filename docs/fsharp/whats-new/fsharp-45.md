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
# <a name="whats-new-in-f-45"></a><span data-ttu-id="6dad9-103">Novedades de F# 4,5</span><span class="sxs-lookup"><span data-stu-id="6dad9-103">What's new in F# 4.5</span></span>

<span data-ttu-id="6dad9-104">F#4,5 agrega varias mejoras en el F# lenguaje.</span><span class="sxs-lookup"><span data-stu-id="6dad9-104">F# 4.5 adds multiple improvements to the F# language.</span></span> <span data-ttu-id="6dad9-105">Muchas de estas características se agregaron juntas para que pueda escribir código eficaz en F# y, al mismo tiempo, garantizar la seguridad de este código.</span><span class="sxs-lookup"><span data-stu-id="6dad9-105">Many of these features were added together to enable you to write efficient code in F# while also ensuring this code is safe.</span></span> <span data-ttu-id="6dad9-106">Esto significa agregar algunos conceptos al lenguaje y una cantidad significativa de análisis del compilador cuando se usan estas construcciones.</span><span class="sxs-lookup"><span data-stu-id="6dad9-106">Doing so means adding a few concepts to the language and a significant amount of compiler analysis when using these constructs.</span></span>

## <a name="get-started"></a><span data-ttu-id="6dad9-107">Primeros pasos</span><span class="sxs-lookup"><span data-stu-id="6dad9-107">Get started</span></span>

<span data-ttu-id="6dad9-108">F#4,5 está disponible en todas las distribuciones de .NET Core y las herramientas de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6dad9-108">F# 4.5 is available in all .NET Core distributions and Visual Studio tooling.</span></span> <span data-ttu-id="6dad9-109">Comience a usar para obtener más información. [ F# ](../get-started/index.md)</span><span class="sxs-lookup"><span data-stu-id="6dad9-109">[Get started with F#](../get-started/index.md) to learn more.</span></span>

## <a name="span-and-byref-like-structs"></a><span data-ttu-id="6dad9-110">Structs de intervalo y de tipo ByRef</span><span class="sxs-lookup"><span data-stu-id="6dad9-110">Span and byref-like structs</span></span>

<span data-ttu-id="6dad9-111">El tipo de <xref:System.Span%601> introducido en .NET Core le permite representar búferes en memoria de forma fuertemente tipada, que ahora se permite a F# partir de F# 4,5.</span><span class="sxs-lookup"><span data-stu-id="6dad9-111">The <xref:System.Span%601> type introduced in .NET Core allows you to represent buffers in memory in a strongly-typed manner, which is now allowed in F# starting with F# 4.5.</span></span> <span data-ttu-id="6dad9-112">En el ejemplo siguiente se muestra cómo se puede volver a usar una función que funciona en un <xref:System.Span%601> con representaciones de búfer diferentes:</span><span class="sxs-lookup"><span data-stu-id="6dad9-112">The following example shows how you can re-use a function operating on a <xref:System.Span%601> with different buffer representations:</span></span>

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

<span data-ttu-id="6dad9-113">Un aspecto importante es que el intervalo y otros [Structs similares a ByRef](../language-reference/structures.md#byreflike-structs) tienen un análisis estático muy rígido realizado por el compilador que restringen su uso de maneras que podría encontrar inesperado.</span><span class="sxs-lookup"><span data-stu-id="6dad9-113">An important aspect to this is that Span and other [byref-like structs](../language-reference/structures.md#byreflike-structs) have very rigid static analysis performed by the compiler that restrict their usage in ways you might find to be unexpected.</span></span> <span data-ttu-id="6dad9-114">Este es el equilibrio fundamental entre rendimiento, expresividad y seguridad que se introduce en F# 4,5.</span><span class="sxs-lookup"><span data-stu-id="6dad9-114">This is the fundamental tradeoff between performance, expressiveness, and safety that is introduced in F# 4.5.</span></span>

## <a name="revamped-byrefs"></a><span data-ttu-id="6dad9-115">Byrefs renovado</span><span class="sxs-lookup"><span data-stu-id="6dad9-115">Revamped byrefs</span></span>

<span data-ttu-id="6dad9-116">Antes de F# 4,5, [Byrefs](../language-reference/byrefs.md) en F# eran no seguros y desapareceban para numerosas aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="6dad9-116">Prior to F# 4.5, [Byrefs](../language-reference/byrefs.md) in F# were unsafe and unsound for numerous applications.</span></span> <span data-ttu-id="6dad9-117">Los problemas de sonido en torno a byrefs se F# han solucionado en 4,5 y el mismo análisis estático realizado para las estructuras span y tipo ByRef también se ha aplicado.</span><span class="sxs-lookup"><span data-stu-id="6dad9-117">Soundness issues around byrefs have been addressed in F# 4.5 and the same static analysis done for span and byref-like structs was also applied.</span></span>

### <a name="inreft-and-outreft"></a><span data-ttu-id="6dad9-118">inref < ' t > y outref < ' t ></span><span class="sxs-lookup"><span data-stu-id="6dad9-118">inref<'T> and outref<'T></span></span>

<span data-ttu-id="6dad9-119">Para representar la noción de un puntero administrado de solo lectura, de solo escritura y de lectura/escritura, F# 4,5 presenta el `inref<'T>`, `outref<'T>` tipos para representar punteros de solo lectura y de solo escritura, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="6dad9-119">To represent the notion of a read-only, write-only, and read/write managed pointer, F# 4.5 introduces the `inref<'T>`, `outref<'T>` types to represent read-only and write-only pointers, respectively.</span></span> <span data-ttu-id="6dad9-120">Cada una tiene una semántica diferente.</span><span class="sxs-lookup"><span data-stu-id="6dad9-120">Each have different semantics.</span></span> <span data-ttu-id="6dad9-121">Por ejemplo, no puede escribir en una `inref<'T>`:</span><span class="sxs-lookup"><span data-stu-id="6dad9-121">For example, you cannot write to an `inref<'T>`:</span></span>

```fsharp
let f (dt: inref<DateTime>) =
    dt <- DateTime.Now // ERROR - cannot write to an inref!
```

<span data-ttu-id="6dad9-122">De forma predeterminada, la inferencia de tipos inferirá los punteros administrados como `inref<'T>` para que estén en línea con F# la naturaleza inmutable del código, a menos que ya se haya declarado como mutable.</span><span class="sxs-lookup"><span data-stu-id="6dad9-122">By default, type inference will infer managed pointers as `inref<'T>` to be in line with the immutable nature of F# code, unless something has already been declared as mutable.</span></span> <span data-ttu-id="6dad9-123">Para hacer que se pueda escribir en algo, debe declarar un tipo como `mutable` antes de pasar su dirección a una función o miembro que lo manipule.</span><span class="sxs-lookup"><span data-stu-id="6dad9-123">To make something writable, you'll need to declare a type as `mutable` before passing its address to a function or member that manipulates it.</span></span> <span data-ttu-id="6dad9-124">Para obtener más información, consulte [Byrefs](../language-reference/byrefs.md).</span><span class="sxs-lookup"><span data-stu-id="6dad9-124">To learn more, see [Byrefs](../language-reference/byrefs.md).</span></span>

## <a name="readonly-structs"></a><span data-ttu-id="6dad9-125">Structs de solo lectura</span><span class="sxs-lookup"><span data-stu-id="6dad9-125">Readonly structs</span></span>

<span data-ttu-id="6dad9-126">A partir F# de 4,5, puede anotar un struct con <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute> de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="6dad9-126">Starting with F# 4.5, you can annotate a struct with <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute> as such:</span></span>

```fsharp
[<IsReadOnly; Struct>]
type S(count1: int, count2: int) =
    member x.Count1 = count1
    member x.Count2 = count2
```

<span data-ttu-id="6dad9-127">Esto no le permite declarar un miembro mutable en el struct y emite metadatos que permiten F# y C# lo tratan como de solo lectura cuando se consumen de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6dad9-127">This disallows you from declaring a mutable member in the struct and emits metadata that allows F# and C# to treat it as readonly when consumed from an assembly.</span></span> <span data-ttu-id="6dad9-128">Para obtener más información, vea [Structs de solo lectura](../language-reference/structures.md#readonly-structs).</span><span class="sxs-lookup"><span data-stu-id="6dad9-128">To learn more, see [ReadOnly structs](../language-reference/structures.md#readonly-structs).</span></span>

## <a name="void-pointers"></a><span data-ttu-id="6dad9-129">Punteros void</span><span class="sxs-lookup"><span data-stu-id="6dad9-129">Void pointers</span></span>

<span data-ttu-id="6dad9-130">El tipo de `voidptr` se agrega F# a 4,5, al igual que las siguientes funciones:</span><span class="sxs-lookup"><span data-stu-id="6dad9-130">The `voidptr` type is added to F# 4.5, as are the following functions:</span></span>

* <span data-ttu-id="6dad9-131">`NativePtr.ofVoidPtr` para convertir un puntero void en un puntero int nativo</span><span class="sxs-lookup"><span data-stu-id="6dad9-131">`NativePtr.ofVoidPtr` to convert a void pointer into a native int pointer</span></span>
* <span data-ttu-id="6dad9-132">`NativePtr.toVoidPtr` para convertir un puntero int nativo en un puntero void</span><span class="sxs-lookup"><span data-stu-id="6dad9-132">`NativePtr.toVoidPtr` to convert a native int pointer to a void pointer</span></span>

<span data-ttu-id="6dad9-133">Esto resulta útil al interoperar con un componente nativo que hace uso de punteros void.</span><span class="sxs-lookup"><span data-stu-id="6dad9-133">This is helpful when interoperating with a native component that makes use of void pointers.</span></span>

## <a name="the-match-keyword"></a><span data-ttu-id="6dad9-134">La palabra clave `match!`.</span><span class="sxs-lookup"><span data-stu-id="6dad9-134">The `match!` keyword</span></span>

<span data-ttu-id="6dad9-135">La palabra clave `match!` mejora la coincidencia de patrones cuando se encuentra dentro de una expresión de cálculo:</span><span class="sxs-lookup"><span data-stu-id="6dad9-135">The `match!` keyword enhances pattern matching when inside a computation expression:</span></span>

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

<span data-ttu-id="6dad9-136">Esto permite acortar el código que suele implicar opciones de combinación (u otros tipos) con expresiones de cálculo como Async.</span><span class="sxs-lookup"><span data-stu-id="6dad9-136">This allows you to shorten code that often involves mixing options (or other types) with computation expressions such as async.</span></span> <span data-ttu-id="6dad9-137">Para obtener más información, vea [Match!](../language-reference/computation-expressions.md#match).</span><span class="sxs-lookup"><span data-stu-id="6dad9-137">To learn more, see [match!](../language-reference/computation-expressions.md#match).</span></span>

## <a name="relaxed-upcasting-requirements-in-array-list-and-sequence-expressions"></a><span data-ttu-id="6dad9-138">Requisitos de conversión relajada en las expresiones de matriz, lista y secuencia</span><span class="sxs-lookup"><span data-stu-id="6dad9-138">Relaxed upcasting requirements in array, list, and sequence expressions</span></span>

<span data-ttu-id="6dad9-139">La combinación de tipos en los que uno puede heredar de otro dentro de las expresiones de matriz, lista y secuencia solía haber requerido la conversión de cualquier tipo derivado a su tipo primario con `:>` o `upcast`.</span><span class="sxs-lookup"><span data-stu-id="6dad9-139">Mixing types where one may inherit from another inside of array, list, and sequence expressions has traditionally required you to upcast any derived type to its parent type with `:>` or `upcast`.</span></span> <span data-ttu-id="6dad9-140">Esto ahora es relajado, como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="6dad9-140">This is now relaxed, demonstrated as follows:</span></span>

```fsharp
let x0 : obj list  = [ "a" ] // ok pre-F# 4.5
let x1 : obj list  = [ "a"; "b" ] // ok pre-F# 4.5
let x2 : obj list  = [ yield "a" :> obj ] // ok pre-F# 4.5

let x3 : obj list  = [ yield "a" ] // Now ok for F# 4.5, and can replace x2
```

## <a name="indentation-relaxation-for-array-and-list-expressions"></a><span data-ttu-id="6dad9-141">Flexibilización de la sangría para las expresiones de matriz y lista</span><span class="sxs-lookup"><span data-stu-id="6dad9-141">Indentation relaxation for array and list expressions</span></span>

<span data-ttu-id="6dad9-142">Antes de F# 4,5, necesitaba aplicar sangría excesiva a las expresiones de matriz y lista cuando se pasaban como argumentos a las llamadas a métodos.</span><span class="sxs-lookup"><span data-stu-id="6dad9-142">Prior to F# 4.5, you needed to excessively indent array and list expressions when passed as arguments to method calls.</span></span> <span data-ttu-id="6dad9-143">Esto ya no es necesario:</span><span class="sxs-lookup"><span data-stu-id="6dad9-143">This is no longer required:</span></span>

```fsharp
module NoExcessiveIndenting = 
    System.Console.WriteLine(format="{0}", arg = [| 
        "hello"
    |])
    System.Console.WriteLine([|
        "hello"
    |])
```
