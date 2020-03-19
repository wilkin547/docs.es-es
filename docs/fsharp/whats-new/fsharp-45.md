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
# <a name="whats-new-in-f-45"></a><span data-ttu-id="3aa97-103">Novedades de la versión 4.5</span><span class="sxs-lookup"><span data-stu-id="3aa97-103">What's new in F# 4.5</span></span>

<span data-ttu-id="3aa97-104">F 4.5 agrega varias mejoras al lenguaje f.</span><span class="sxs-lookup"><span data-stu-id="3aa97-104">F# 4.5 adds multiple improvements to the F# language.</span></span> <span data-ttu-id="3aa97-105">Muchas de estas características se agregaron juntas para permitirle escribir código eficaz en F , a la vez que garantiza que este código es seguro.</span><span class="sxs-lookup"><span data-stu-id="3aa97-105">Many of these features were added together to enable you to write efficient code in F# while also ensuring this code is safe.</span></span> <span data-ttu-id="3aa97-106">Hacerlo significa agregar algunos conceptos al lenguaje y una cantidad significativa de análisis del compilador al usar estas construcciones.</span><span class="sxs-lookup"><span data-stu-id="3aa97-106">Doing so means adding a few concepts to the language and a significant amount of compiler analysis when using these constructs.</span></span>

## <a name="get-started"></a><span data-ttu-id="3aa97-107">Introducción</span><span class="sxs-lookup"><span data-stu-id="3aa97-107">Get started</span></span>

<span data-ttu-id="3aa97-108">F 4.5 está disponible en todas las distribuciones de .NET Core y las herramientas de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3aa97-108">F# 4.5 is available in all .NET Core distributions and Visual Studio tooling.</span></span> <span data-ttu-id="3aa97-109">[Empiece a utilizar F](../get-started/index.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="3aa97-109">[Get started with F#](../get-started/index.md) to learn more.</span></span>

## <a name="span-and-byref-like-structs"></a><span data-ttu-id="3aa97-110">Estructuras similares a Span y byref</span><span class="sxs-lookup"><span data-stu-id="3aa97-110">Span and byref-like structs</span></span>

<span data-ttu-id="3aa97-111">El <xref:System.Span%601> tipo introducido en .NET Core le permite representar los búferes en la memoria de una manera fuertemente tipada, que ahora se permite en F a partir de F 4.5.</span><span class="sxs-lookup"><span data-stu-id="3aa97-111">The <xref:System.Span%601> type introduced in .NET Core allows you to represent buffers in memory in a strongly-typed manner, which is now allowed in F# starting with F# 4.5.</span></span> <span data-ttu-id="3aa97-112">En el ejemplo siguiente se muestra cómo se <xref:System.Span%601> puede reutilizar una función que funciona en una con diferentes representaciones de búfer:</span><span class="sxs-lookup"><span data-stu-id="3aa97-112">The following example shows how you can re-use a function operating on a <xref:System.Span%601> with different buffer representations:</span></span>

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

<span data-ttu-id="3aa97-113">Un aspecto importante de esto es que Span y otras [estructuras byref-like](../language-reference/structures.md#byreflike-structs) tienen un análisis estático muy rígido realizado por el compilador que restringe su uso de maneras que pueda resultar inesperadas.</span><span class="sxs-lookup"><span data-stu-id="3aa97-113">An important aspect to this is that Span and other [byref-like structs](../language-reference/structures.md#byreflike-structs) have very rigid static analysis performed by the compiler that restrict their usage in ways you might find to be unexpected.</span></span> <span data-ttu-id="3aa97-114">Este es el equilibrio fundamental entre el rendimiento, la expresividad y la seguridad que se introduce en f 4.5.</span><span class="sxs-lookup"><span data-stu-id="3aa97-114">This is the fundamental tradeoff between performance, expressiveness, and safety that is introduced in F# 4.5.</span></span>

## <a name="revamped-byrefs"></a><span data-ttu-id="3aa97-115">Retorciendo byrefs</span><span class="sxs-lookup"><span data-stu-id="3aa97-115">Revamped byrefs</span></span>

<span data-ttu-id="3aa97-116">Antes de f 4.5, [Byrefs](../language-reference/byrefs.md) en F - eran inseguros y no son sólidos para numerosas aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="3aa97-116">Prior to F# 4.5, [Byrefs](../language-reference/byrefs.md) in F# were unsafe and unsound for numerous applications.</span></span> <span data-ttu-id="3aa97-117">Los problemas de solidez en torno a las referencias externas se han abordado en F 4.5 y también se aplicó el mismo análisis estático realizado para estructuras similares a span y byref.</span><span class="sxs-lookup"><span data-stu-id="3aa97-117">Soundness issues around byrefs have been addressed in F# 4.5 and the same static analysis done for span and byref-like structs was also applied.</span></span>

### <a name="inreft-and-outreft"></a><span data-ttu-id="3aa97-118">inref<'T> y outref<'T></span><span class="sxs-lookup"><span data-stu-id="3aa97-118">inref<'T> and outref<'T></span></span>

<span data-ttu-id="3aa97-119">Para representar la noción de un puntero administrado de solo lectura, de solo escritura `inref<'T>` `outref<'T>` y de lectura y escritura, F- 4.5 presenta los tipos , para representar punteros de solo lectura y de solo escritura, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="3aa97-119">To represent the notion of a read-only, write-only, and read/write managed pointer, F# 4.5 introduces the `inref<'T>`, `outref<'T>` types to represent read-only and write-only pointers, respectively.</span></span> <span data-ttu-id="3aa97-120">Cada uno tiene una semántica diferente.</span><span class="sxs-lookup"><span data-stu-id="3aa97-120">Each have different semantics.</span></span> <span data-ttu-id="3aa97-121">Por ejemplo, no se `inref<'T>`puede escribir en un :</span><span class="sxs-lookup"><span data-stu-id="3aa97-121">For example, you cannot write to an `inref<'T>`:</span></span>

```fsharp
let f (dt: inref<DateTime>) =
    dt <- DateTime.Now // ERROR - cannot write to an inref!
```

<span data-ttu-id="3aa97-122">De forma predeterminada, la inferencia de `inref<'T>` tipos inferirá los punteros administrados como para estar en línea con la naturaleza inmutable del código de F, a menos que algo ya se haya declarado como mutable.</span><span class="sxs-lookup"><span data-stu-id="3aa97-122">By default, type inference will infer managed pointers as `inref<'T>` to be in line with the immutable nature of F# code, unless something has already been declared as mutable.</span></span> <span data-ttu-id="3aa97-123">Para hacer que algo se pueda escribir, deberá `mutable` declarar un tipo como antes de pasar su dirección a una función o miembro que lo manipula.</span><span class="sxs-lookup"><span data-stu-id="3aa97-123">To make something writable, you'll need to declare a type as `mutable` before passing its address to a function or member that manipulates it.</span></span> <span data-ttu-id="3aa97-124">Para obtener más información, consulte [Byrefs](../language-reference/byrefs.md).</span><span class="sxs-lookup"><span data-stu-id="3aa97-124">To learn more, see [Byrefs](../language-reference/byrefs.md).</span></span>

## <a name="readonly-structs"></a><span data-ttu-id="3aa97-125">Estructuras Readonly</span><span class="sxs-lookup"><span data-stu-id="3aa97-125">Readonly structs</span></span>

<span data-ttu-id="3aa97-126">A partir de F 4.5, puede <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute> anotar una estructura con como tal:</span><span class="sxs-lookup"><span data-stu-id="3aa97-126">Starting with F# 4.5, you can annotate a struct with <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute> as such:</span></span>

```fsharp
[<IsReadOnly; Struct>]
type S(count1: int, count2: int) =
    member x.Count1 = count1
    member x.Count2 = count2
```

<span data-ttu-id="3aa97-127">Esto no le permite declarar un miembro mutable en la estructura y emite metadatos que permiten que F- y C- para tratarlo como de solo lectura cuando se consume desde un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3aa97-127">This disallows you from declaring a mutable member in the struct and emits metadata that allows F# and C# to treat it as readonly when consumed from an assembly.</span></span> <span data-ttu-id="3aa97-128">Para obtener más información, consulte [Estructuras ReadOnly](../language-reference/structures.md#readonly-structs).</span><span class="sxs-lookup"><span data-stu-id="3aa97-128">To learn more, see [ReadOnly structs](../language-reference/structures.md#readonly-structs).</span></span>

## <a name="void-pointers"></a><span data-ttu-id="3aa97-129">Punteros vacíos</span><span class="sxs-lookup"><span data-stu-id="3aa97-129">Void pointers</span></span>

<span data-ttu-id="3aa97-130">El `voidptr` tipo se agrega a F 4.5, al igual que las siguientes funciones:</span><span class="sxs-lookup"><span data-stu-id="3aa97-130">The `voidptr` type is added to F# 4.5, as are the following functions:</span></span>

* <span data-ttu-id="3aa97-131">`NativePtr.ofVoidPtr`para convertir un puntero void en un puntero int nativo</span><span class="sxs-lookup"><span data-stu-id="3aa97-131">`NativePtr.ofVoidPtr` to convert a void pointer into a native int pointer</span></span>
* <span data-ttu-id="3aa97-132">`NativePtr.toVoidPtr`para convertir un puntero int nativo en un puntero void</span><span class="sxs-lookup"><span data-stu-id="3aa97-132">`NativePtr.toVoidPtr` to convert a native int pointer to a void pointer</span></span>

<span data-ttu-id="3aa97-133">Esto resulta útil cuando se interopera con un componente nativo que hace uso de punteros void.</span><span class="sxs-lookup"><span data-stu-id="3aa97-133">This is helpful when interoperating with a native component that makes use of void pointers.</span></span>

## <a name="the-match-keyword"></a><span data-ttu-id="3aa97-134">La palabra clave `match!`.</span><span class="sxs-lookup"><span data-stu-id="3aa97-134">The `match!` keyword</span></span>

<span data-ttu-id="3aa97-135">La `match!` palabra clave mejora la coincidencia de patrones cuando se encuentra dentro de una expresión de cálculo:</span><span class="sxs-lookup"><span data-stu-id="3aa97-135">The `match!` keyword enhances pattern matching when inside a computation expression:</span></span>

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

<span data-ttu-id="3aa97-136">Esto le permite acortar el código que a menudo implica opciones de mezcla (u otros tipos) con expresiones de cálculo como async.</span><span class="sxs-lookup"><span data-stu-id="3aa97-136">This allows you to shorten code that often involves mixing options (or other types) with computation expressions such as async.</span></span> <span data-ttu-id="3aa97-137">Para obtener más información, consulte [match!](../language-reference/computation-expressions.md#match).</span><span class="sxs-lookup"><span data-stu-id="3aa97-137">To learn more, see [match!](../language-reference/computation-expressions.md#match).</span></span>

## <a name="relaxed-upcasting-requirements-in-array-list-and-sequence-expressions"></a><span data-ttu-id="3aa97-138">Requisitos de upcasting relajados en expresiones de matriz, lista y secuencia</span><span class="sxs-lookup"><span data-stu-id="3aa97-138">Relaxed upcasting requirements in array, list, and sequence expressions</span></span>

<span data-ttu-id="3aa97-139">La mezcla de tipos en los que uno puede heredar de otro dentro de las expresiones `:>` de `upcast`matriz, lista y secuencia ha requerido tradicionalmente que se convierta cualquier tipo derivado a su tipo primario con o .</span><span class="sxs-lookup"><span data-stu-id="3aa97-139">Mixing types where one may inherit from another inside of array, list, and sequence expressions has traditionally required you to upcast any derived type to its parent type with `:>` or `upcast`.</span></span> <span data-ttu-id="3aa97-140">Esto ahora es relajado, demostrado de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="3aa97-140">This is now relaxed, demonstrated as follows:</span></span>

```fsharp
let x0 : obj list  = [ "a" ] // ok pre-F# 4.5
let x1 : obj list  = [ "a"; "b" ] // ok pre-F# 4.5
let x2 : obj list  = [ yield "a" :> obj ] // ok pre-F# 4.5

let x3 : obj list  = [ yield "a" ] // Now ok for F# 4.5, and can replace x2
```

## <a name="indentation-relaxation-for-array-and-list-expressions"></a><span data-ttu-id="3aa97-141">Relajación de sangría para expresiones de matriz y lista</span><span class="sxs-lookup"><span data-stu-id="3aa97-141">Indentation relaxation for array and list expressions</span></span>

<span data-ttu-id="3aa97-142">Antes de F 4.5, era necesario aplicar sangría excesiva a las expresiones de matriz y lista cuando se pasaban como argumentos a las llamadas a métodos.</span><span class="sxs-lookup"><span data-stu-id="3aa97-142">Prior to F# 4.5, you needed to excessively indent array and list expressions when passed as arguments to method calls.</span></span> <span data-ttu-id="3aa97-143">Esto ya no es necesario:</span><span class="sxs-lookup"><span data-stu-id="3aa97-143">This is no longer required:</span></span>

```fsharp
module NoExcessiveIndenting =
    System.Console.WriteLine(format="{0}", arg = [|
        "hello"
    |])
    System.Console.WriteLine([|
        "hello"
    |])
```
