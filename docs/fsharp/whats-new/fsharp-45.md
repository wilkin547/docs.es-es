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
# <a name="whats-new-in-f-45"></a><span data-ttu-id="abbbf-103">Novedades de F # 4,5</span><span class="sxs-lookup"><span data-stu-id="abbbf-103">What's new in F# 4.5</span></span>

<span data-ttu-id="abbbf-104">F # 4,5 agrega varias mejoras en el lenguaje F #.</span><span class="sxs-lookup"><span data-stu-id="abbbf-104">F# 4.5 adds multiple improvements to the F# language.</span></span> <span data-ttu-id="abbbf-105">Muchas de estas características se agregaron juntas para que pueda escribir código eficaz en F #, al mismo tiempo que garantiza que este código es seguro.</span><span class="sxs-lookup"><span data-stu-id="abbbf-105">Many of these features were added together to enable you to write efficient code in F# while also ensuring this code is safe.</span></span> <span data-ttu-id="abbbf-106">Esto significa agregar algunos conceptos al lenguaje y una cantidad significativa de análisis del compilador cuando se usan estas construcciones.</span><span class="sxs-lookup"><span data-stu-id="abbbf-106">Doing so means adding a few concepts to the language and a significant amount of compiler analysis when using these constructs.</span></span>

## <a name="get-started"></a><span data-ttu-id="abbbf-107">Introducción</span><span class="sxs-lookup"><span data-stu-id="abbbf-107">Get started</span></span>

<span data-ttu-id="abbbf-108">F # 4,5 está disponible en todas las distribuciones de .NET Core y las herramientas de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="abbbf-108">F# 4.5 is available in all .NET Core distributions and Visual Studio tooling.</span></span> <span data-ttu-id="abbbf-109">Para obtener más información, [consulte Introducción a F #](../get-started/index.md) .</span><span class="sxs-lookup"><span data-stu-id="abbbf-109">[Get started with F#](../get-started/index.md) to learn more.</span></span>

## <a name="span-and-byref-like-structs"></a><span data-ttu-id="abbbf-110">Structs de intervalo y de tipo ByRef</span><span class="sxs-lookup"><span data-stu-id="abbbf-110">Span and byref-like structs</span></span>

<span data-ttu-id="abbbf-111">El <xref:System.Span%601> tipo introducido en .net Core le permite representar búferes en memoria de una manera fuertemente tipada, que ahora se permite en f # a partir de f # 4,5.</span><span class="sxs-lookup"><span data-stu-id="abbbf-111">The <xref:System.Span%601> type introduced in .NET Core allows you to represent buffers in memory in a strongly typed manner, which is now allowed in F# starting with F# 4.5.</span></span> <span data-ttu-id="abbbf-112">En el ejemplo siguiente se muestra cómo se puede volver a usar una función que funciona en <xref:System.Span%601> con representaciones de búfer diferentes:</span><span class="sxs-lookup"><span data-stu-id="abbbf-112">The following example shows how you can re-use a function operating on a <xref:System.Span%601> with different buffer representations:</span></span>

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

<span data-ttu-id="abbbf-113">Un aspecto importante es que el intervalo y otros [Structs similares a ByRef](../language-reference/structures.md#byreflike-structs) tienen un análisis estático muy rígido realizado por el compilador que restringen su uso de maneras que podría encontrar inesperado.</span><span class="sxs-lookup"><span data-stu-id="abbbf-113">An important aspect to this is that Span and other [byref-like structs](../language-reference/structures.md#byreflike-structs) have very rigid static analysis performed by the compiler that restrict their usage in ways you might find to be unexpected.</span></span> <span data-ttu-id="abbbf-114">Este es el equilibrio fundamental entre el rendimiento, la expresividad y la seguridad introducida en F # 4,5.</span><span class="sxs-lookup"><span data-stu-id="abbbf-114">This is the fundamental tradeoff between performance, expressiveness, and safety that is introduced in F# 4.5.</span></span>

## <a name="revamped-byrefs"></a><span data-ttu-id="abbbf-115">Byrefs renovado</span><span class="sxs-lookup"><span data-stu-id="abbbf-115">Revamped byrefs</span></span>

<span data-ttu-id="abbbf-116">Antes de F # 4,5, [Byrefs](../language-reference/byrefs.md) en f # eran inseguros y desapareceban para numerosas aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="abbbf-116">Prior to F# 4.5, [Byrefs](../language-reference/byrefs.md) in F# were unsafe and unsound for numerous applications.</span></span> <span data-ttu-id="abbbf-117">Los problemas de solidez en torno a byrefs se han solucionado en F # 4,5 y el mismo análisis estático realizado para las estructuras span y tipo ByRef también se ha aplicado.</span><span class="sxs-lookup"><span data-stu-id="abbbf-117">Soundness issues around byrefs have been addressed in F# 4.5 and the same static analysis done for span and byref-like structs was also applied.</span></span>

### <a name="inreft-and-outreft"></a><span data-ttu-id="abbbf-118">inref< ' t> y outref< ' t></span><span class="sxs-lookup"><span data-stu-id="abbbf-118">inref<'T> and outref<'T></span></span>

<span data-ttu-id="abbbf-119">Para representar la noción de un puntero administrado de solo lectura, de solo escritura y de lectura/escritura, F # 4,5 presenta los `inref<'T>` `outref<'T>` tipos, para representar los punteros de solo lectura y solo escritura, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="abbbf-119">To represent the notion of a read-only, write-only, and read/write managed pointer, F# 4.5 introduces the `inref<'T>`, `outref<'T>` types to represent read-only and write-only pointers, respectively.</span></span> <span data-ttu-id="abbbf-120">Cada una tiene una semántica diferente.</span><span class="sxs-lookup"><span data-stu-id="abbbf-120">Each have different semantics.</span></span> <span data-ttu-id="abbbf-121">Por ejemplo, no se puede escribir en un `inref<'T>` :</span><span class="sxs-lookup"><span data-stu-id="abbbf-121">For example, you cannot write to an `inref<'T>`:</span></span>

```fsharp
let f (dt: inref<DateTime>) =
    dt <- DateTime.Now // ERROR - cannot write to an inref!
```

<span data-ttu-id="abbbf-122">De forma predeterminada, la inferencia de tipos deducirá punteros administrados como si `inref<'T>` estuvieran en línea con la naturaleza inmutable del código de F #, a menos que ya se haya declarado como mutable.</span><span class="sxs-lookup"><span data-stu-id="abbbf-122">By default, type inference will infer managed pointers as `inref<'T>` to be in line with the immutable nature of F# code, unless something has already been declared as mutable.</span></span> <span data-ttu-id="abbbf-123">Para hacer que se pueda escribir en algo, debe declarar un tipo como `mutable` antes de pasar su dirección a una función o miembro que lo manipule.</span><span class="sxs-lookup"><span data-stu-id="abbbf-123">To make something writable, you'll need to declare a type as `mutable` before passing its address to a function or member that manipulates it.</span></span> <span data-ttu-id="abbbf-124">Para obtener más información, consulte [Byrefs](../language-reference/byrefs.md).</span><span class="sxs-lookup"><span data-stu-id="abbbf-124">To learn more, see [Byrefs](../language-reference/byrefs.md).</span></span>

## <a name="readonly-structs"></a><span data-ttu-id="abbbf-125">Estructuras readonly</span><span class="sxs-lookup"><span data-stu-id="abbbf-125">Readonly structs</span></span>

<span data-ttu-id="abbbf-126">A partir de F # 4,5, puede anotar un struct con <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute> como tal:</span><span class="sxs-lookup"><span data-stu-id="abbbf-126">Starting with F# 4.5, you can annotate a struct with <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute> as such:</span></span>

```fsharp
[<IsReadOnly; Struct>]
type S(count1: int, count2: int) =
    member x.Count1 = count1
    member x.Count2 = count2
```

<span data-ttu-id="abbbf-127">Esto no le permite declarar un miembro mutable en el struct y emite metadatos que permiten que F # y C# lo traten como de solo lectura cuando se consumen de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="abbbf-127">This disallows you from declaring a mutable member in the struct and emits metadata that allows F# and C# to treat it as readonly when consumed from an assembly.</span></span> <span data-ttu-id="abbbf-128">Para obtener más información, vea [Structs de solo lectura](../language-reference/structures.md#readonly-structs).</span><span class="sxs-lookup"><span data-stu-id="abbbf-128">To learn more, see [ReadOnly structs](../language-reference/structures.md#readonly-structs).</span></span>

## <a name="void-pointers"></a><span data-ttu-id="abbbf-129">Punteros void</span><span class="sxs-lookup"><span data-stu-id="abbbf-129">Void pointers</span></span>

<span data-ttu-id="abbbf-130">El `voidptr` tipo se agrega a F # 4,5, al igual que las funciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="abbbf-130">The `voidptr` type is added to F# 4.5, as are the following functions:</span></span>

* <span data-ttu-id="abbbf-131">`NativePtr.ofVoidPtr`para convertir un puntero void en un puntero int nativo</span><span class="sxs-lookup"><span data-stu-id="abbbf-131">`NativePtr.ofVoidPtr` to convert a void pointer into a native int pointer</span></span>
* <span data-ttu-id="abbbf-132">`NativePtr.toVoidPtr`para convertir un puntero int nativo en un puntero void</span><span class="sxs-lookup"><span data-stu-id="abbbf-132">`NativePtr.toVoidPtr` to convert a native int pointer to a void pointer</span></span>

<span data-ttu-id="abbbf-133">Esto resulta útil al interoperar con un componente nativo que hace uso de punteros void.</span><span class="sxs-lookup"><span data-stu-id="abbbf-133">This is helpful when interoperating with a native component that makes use of void pointers.</span></span>

## <a name="the-match-keyword"></a><span data-ttu-id="abbbf-134">La palabra clave `match!`.</span><span class="sxs-lookup"><span data-stu-id="abbbf-134">The `match!` keyword</span></span>

<span data-ttu-id="abbbf-135">La `match!` palabra clave mejora la coincidencia de patrones cuando se encuentra dentro de una expresión de cálculo:</span><span class="sxs-lookup"><span data-stu-id="abbbf-135">The `match!` keyword enhances pattern matching when inside a computation expression:</span></span>

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

<span data-ttu-id="abbbf-136">Esto permite acortar el código que suele implicar opciones de combinación (u otros tipos) con expresiones de cálculo como Async.</span><span class="sxs-lookup"><span data-stu-id="abbbf-136">This allows you to shorten code that often involves mixing options (or other types) with computation expressions such as async.</span></span> <span data-ttu-id="abbbf-137">Para obtener más información, vea [Match!](../language-reference/computation-expressions.md#match).</span><span class="sxs-lookup"><span data-stu-id="abbbf-137">To learn more, see [match!](../language-reference/computation-expressions.md#match).</span></span>

## <a name="relaxed-upcasting-requirements-in-array-list-and-sequence-expressions"></a><span data-ttu-id="abbbf-138">Requisitos de conversión relajada en las expresiones de matriz, lista y secuencia</span><span class="sxs-lookup"><span data-stu-id="abbbf-138">Relaxed upcasting requirements in array, list, and sequence expressions</span></span>

<span data-ttu-id="abbbf-139">La combinación de tipos en los que uno puede heredar de otro dentro de las expresiones de matriz, lista y secuencia solía haber requerido la conversión de cualquier tipo derivado a su tipo primario con `:>` o `upcast` .</span><span class="sxs-lookup"><span data-stu-id="abbbf-139">Mixing types where one may inherit from another inside of array, list, and sequence expressions has traditionally required you to upcast any derived type to its parent type with `:>` or `upcast`.</span></span> <span data-ttu-id="abbbf-140">Esto ahora es relajado, como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="abbbf-140">This is now relaxed, demonstrated as follows:</span></span>

```fsharp
let x0 : obj list  = [ "a" ] // ok pre-F# 4.5
let x1 : obj list  = [ "a"; "b" ] // ok pre-F# 4.5
let x2 : obj list  = [ yield "a" :> obj ] // ok pre-F# 4.5

let x3 : obj list  = [ yield "a" ] // Now ok for F# 4.5, and can replace x2
```

## <a name="indentation-relaxation-for-array-and-list-expressions"></a><span data-ttu-id="abbbf-141">Flexibilización de la sangría para las expresiones de matriz y lista</span><span class="sxs-lookup"><span data-stu-id="abbbf-141">Indentation relaxation for array and list expressions</span></span>

<span data-ttu-id="abbbf-142">Antes de F # 4,5, era necesario aplicar sangría excesiva a las expresiones de matriz y lista cuando se pasan como argumentos a las llamadas a métodos.</span><span class="sxs-lookup"><span data-stu-id="abbbf-142">Prior to F# 4.5, you needed to excessively indent array and list expressions when passed as arguments to method calls.</span></span> <span data-ttu-id="abbbf-143">Esto ya no es necesario:</span><span class="sxs-lookup"><span data-stu-id="abbbf-143">This is no longer required:</span></span>

```fsharp
module NoExcessiveIndenting =
    System.Console.WriteLine(format="{0}", arg = [|
        "hello"
    |])
    System.Console.WriteLine([|
        "hello"
    |])
```
