---
title: Byrefs
description: Obtenga información sobre los tipos byref y tipo ByRef F#en, que se usan para la programación de bajo nivel.
ms.date: 09/02/2018
ms.openlocfilehash: 453de2a5f30dc532dcd7f873b7f5defefdc814cd
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424772"
---
# <a name="byrefs"></a><span data-ttu-id="0595e-103">Byrefs</span><span class="sxs-lookup"><span data-stu-id="0595e-103">Byrefs</span></span>

<span data-ttu-id="0595e-104">F#tiene dos áreas de características principales que se ocupan del espacio de programación de bajo nivel:</span><span class="sxs-lookup"><span data-stu-id="0595e-104">F# has two major feature areas that deal in the space of low-level programming:</span></span>

* <span data-ttu-id="0595e-105">El /de `byref``inref`/tipos de `outref`, que son punteros administrados.</span><span class="sxs-lookup"><span data-stu-id="0595e-105">The `byref`/`inref`/`outref` types, which are a managed pointers.</span></span> <span data-ttu-id="0595e-106">Tienen restricciones de uso para que no pueda compilar un programa que no sea válido en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="0595e-106">They have restrictions on usage so that you cannot compile a program that is invalid at runtime.</span></span>
* <span data-ttu-id="0595e-107">Struct de tipo `byref`, que es una [estructura](structures.md) que tiene una semántica similar y las mismas restricciones en tiempo de compilación que `byref<'T>`.</span><span class="sxs-lookup"><span data-stu-id="0595e-107">A `byref`-like struct, which is a [structure](structures.md) that has similar semantics and the same compile-time restrictions as `byref<'T>`.</span></span> <span data-ttu-id="0595e-108">Un ejemplo es <xref:System.Span%601>.</span><span class="sxs-lookup"><span data-stu-id="0595e-108">One example is <xref:System.Span%601>.</span></span>

## <a name="syntax"></a><span data-ttu-id="0595e-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0595e-109">Syntax</span></span>

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

## <a name="byref-inref-and-outref"></a><span data-ttu-id="0595e-110">ByRef, inref y outref</span><span class="sxs-lookup"><span data-stu-id="0595e-110">Byref, inref, and outref</span></span>

<span data-ttu-id="0595e-111">Hay tres formas de `byref`:</span><span class="sxs-lookup"><span data-stu-id="0595e-111">There are three forms of `byref`:</span></span>

* <span data-ttu-id="0595e-112">`inref<'T>`, un puntero administrado para leer el valor subyacente.</span><span class="sxs-lookup"><span data-stu-id="0595e-112">`inref<'T>`, a managed pointer for reading the underlying value.</span></span>
* <span data-ttu-id="0595e-113">`outref<'T>`, un puntero administrado para escribir en el valor subyacente.</span><span class="sxs-lookup"><span data-stu-id="0595e-113">`outref<'T>`, a managed pointer for writing to the underlying value.</span></span>
* <span data-ttu-id="0595e-114">`byref<'T>`, un puntero administrado para leer y escribir el valor subyacente.</span><span class="sxs-lookup"><span data-stu-id="0595e-114">`byref<'T>`, a managed pointer for reading and writing the underlying value.</span></span>

<span data-ttu-id="0595e-115">Se puede pasar una `byref<'T>` en la que se espera un `inref<'T>`.</span><span class="sxs-lookup"><span data-stu-id="0595e-115">A `byref<'T>` can be passed where an `inref<'T>` is expected.</span></span> <span data-ttu-id="0595e-116">De forma similar, se puede pasar una `byref<'T>` en la que se espera un `outref<'T>`.</span><span class="sxs-lookup"><span data-stu-id="0595e-116">Similarly, a `byref<'T>` can be passed where an `outref<'T>` is expected.</span></span>

## <a name="using-byrefs"></a><span data-ttu-id="0595e-117">Usar byrefs</span><span class="sxs-lookup"><span data-stu-id="0595e-117">Using byrefs</span></span>

<span data-ttu-id="0595e-118">Para usar un `inref<'T>`, debe obtener un valor de puntero con `&`:</span><span class="sxs-lookup"><span data-stu-id="0595e-118">To use a `inref<'T>`, you need to get a pointer value with `&`:</span></span>

```fsharp
open System

let f (dt: inref<DateTime>) =
    printfn "Now: %s" (dt.ToString())

let usage =
    let dt = DateTime.Now
    f &dt // Pass a pointer to 'dt'
```

<span data-ttu-id="0595e-119">Para escribir en el puntero mediante un `outref<'T>` o `byref<'T>`, también debe hacer el valor que obtiene un puntero a `mutable`.</span><span class="sxs-lookup"><span data-stu-id="0595e-119">To write to the pointer by using an `outref<'T>` or `byref<'T>`, you must also make the value you grab a pointer to `mutable`.</span></span>

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

<span data-ttu-id="0595e-120">Si solo está escribiendo el puntero en lugar de leerlo, considere la posibilidad de usar `outref<'T>` en lugar de `byref<'T>`.</span><span class="sxs-lookup"><span data-stu-id="0595e-120">If you are only writing the pointer instead of reading it, consider using `outref<'T>` instead of `byref<'T>`.</span></span>

### <a name="inref-semantics"></a><span data-ttu-id="0595e-121">Semántica de Inref</span><span class="sxs-lookup"><span data-stu-id="0595e-121">Inref semantics</span></span>

<span data-ttu-id="0595e-122">Observe el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="0595e-122">Consider the following code:</span></span>

```fsharp
let f (x: inref<SomeStruct>) = x.SomeField
```

<span data-ttu-id="0595e-123">Semánticamente, esto significa lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0595e-123">Semantically, this means the following:</span></span>

* <span data-ttu-id="0595e-124">El titular del puntero `x` solo puede usarlo para leer el valor.</span><span class="sxs-lookup"><span data-stu-id="0595e-124">The holder of the `x` pointer may only use it to read the value.</span></span>
* <span data-ttu-id="0595e-125">Cualquier puntero adquirido a `struct` campos anidados en `SomeStruct` tiene un tipo `inref<_>`.</span><span class="sxs-lookup"><span data-stu-id="0595e-125">Any pointer acquired to `struct` fields nested within `SomeStruct` are given type `inref<_>`.</span></span>

<span data-ttu-id="0595e-126">También se cumple lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0595e-126">The following is also true:</span></span>

* <span data-ttu-id="0595e-127">No hay ninguna implicación de que otros subprocesos o alias no tengan acceso de escritura a `x`.</span><span class="sxs-lookup"><span data-stu-id="0595e-127">There is no implication that other threads or aliases do not have write access to `x`.</span></span>
* <span data-ttu-id="0595e-128">No hay ninguna implicación de que `SomeStruct` sea inmutable en virtud de `x` ser una `inref`.</span><span class="sxs-lookup"><span data-stu-id="0595e-128">There is no implication that `SomeStruct` is immutable by virtue of `x` being an `inref`.</span></span>

<span data-ttu-id="0595e-129">Sin embargo, F# en el caso de los tipos de valor que **son** inmutables, el puntero de `this` se deduce como `inref`.</span><span class="sxs-lookup"><span data-stu-id="0595e-129">However, for F# value types that **are** immutable, the `this` pointer is inferred to be an `inref`.</span></span>

<span data-ttu-id="0595e-130">Todas estas reglas juntas indican que el titular de un puntero `inref` no puede modificar el contenido inmediato de la memoria a la que se apunta.</span><span class="sxs-lookup"><span data-stu-id="0595e-130">All of these rules together mean that the holder of an `inref` pointer may not modify the immediate contents of the memory being pointed to.</span></span>

### <a name="outref-semantics"></a><span data-ttu-id="0595e-131">Semántica de Outref</span><span class="sxs-lookup"><span data-stu-id="0595e-131">Outref semantics</span></span>

<span data-ttu-id="0595e-132">El propósito de `outref<'T>` es indicar que el puntero solo se debe leer desde.</span><span class="sxs-lookup"><span data-stu-id="0595e-132">The purpose of `outref<'T>` is to indicate that the pointer should only be read from.</span></span> <span data-ttu-id="0595e-133">De forma inesperada, `outref<'T>` permite leer el valor subyacente a pesar de su nombre.</span><span class="sxs-lookup"><span data-stu-id="0595e-133">Unexpectedly, `outref<'T>` permits reading the underlying value despite its name.</span></span> <span data-ttu-id="0595e-134">Esto es así por motivos de compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="0595e-134">This is for compatibility purposes.</span></span> <span data-ttu-id="0595e-135">Semánticamente, `outref<'T>` no es diferente de `byref<'T>`.</span><span class="sxs-lookup"><span data-stu-id="0595e-135">Semantically, `outref<'T>` is no different than `byref<'T>`.</span></span>

### <a name="interop-with-c"></a><span data-ttu-id="0595e-136">Interoperabilidad con C\#</span><span class="sxs-lookup"><span data-stu-id="0595e-136">Interop with C\#</span></span>

<span data-ttu-id="0595e-137">C#admite las palabras clave `in ref` y `out ref`, además de `ref` devuelve.</span><span class="sxs-lookup"><span data-stu-id="0595e-137">C# supports the `in ref` and `out ref` keywords, in addition to `ref` returns.</span></span> <span data-ttu-id="0595e-138">En la tabla siguiente se F# muestra cómo interpreta C# lo que emite:</span><span class="sxs-lookup"><span data-stu-id="0595e-138">The following table shows how F# interprets what C# emits:</span></span>

|<span data-ttu-id="0595e-139">C#construir</span><span class="sxs-lookup"><span data-stu-id="0595e-139">C# construct</span></span>|<span data-ttu-id="0595e-140">F#deduce</span><span class="sxs-lookup"><span data-stu-id="0595e-140">F# infers</span></span>|
|------------|---------|
|<span data-ttu-id="0595e-141">`ref` valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0595e-141">`ref` return value</span></span>|`outref<'T>`|
|<span data-ttu-id="0595e-142">`ref readonly` valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0595e-142">`ref readonly` return value</span></span>|`inref<'T>`|
|<span data-ttu-id="0595e-143">`in ref` parámetro</span><span class="sxs-lookup"><span data-stu-id="0595e-143">`in ref` parameter</span></span>|`inref<'T>`|
|<span data-ttu-id="0595e-144">`out ref` parámetro</span><span class="sxs-lookup"><span data-stu-id="0595e-144">`out ref` parameter</span></span>|`outref<'T>`|

<span data-ttu-id="0595e-145">En la tabla siguiente se F# muestra lo que emite:</span><span class="sxs-lookup"><span data-stu-id="0595e-145">The following table shows what F# emits:</span></span>

|<span data-ttu-id="0595e-146">F#construir</span><span class="sxs-lookup"><span data-stu-id="0595e-146">F# construct</span></span>|<span data-ttu-id="0595e-147">Construcción emitida</span><span class="sxs-lookup"><span data-stu-id="0595e-147">Emitted construct</span></span>|
|------------|-----------------|
|<span data-ttu-id="0595e-148">`inref<'T>` argumento</span><span class="sxs-lookup"><span data-stu-id="0595e-148">`inref<'T>` argument</span></span>|<span data-ttu-id="0595e-149">`[In]` atributo en el argumento</span><span class="sxs-lookup"><span data-stu-id="0595e-149">`[In]` attribute on argument</span></span>|
|<span data-ttu-id="0595e-150">`inref<'T>` devolver</span><span class="sxs-lookup"><span data-stu-id="0595e-150">`inref<'T>` return</span></span>|<span data-ttu-id="0595e-151">`modreq` atributo en el valor</span><span class="sxs-lookup"><span data-stu-id="0595e-151">`modreq` attribute on value</span></span>|
|<span data-ttu-id="0595e-152">`inref<'T>` en la ranura o la implementación abstracta</span><span class="sxs-lookup"><span data-stu-id="0595e-152">`inref<'T>` in abstract slot or implementation</span></span>|<span data-ttu-id="0595e-153">`modreq` argumento on o Return</span><span class="sxs-lookup"><span data-stu-id="0595e-153">`modreq` on argument or return</span></span>|
|<span data-ttu-id="0595e-154">`outref<'T>` argumento</span><span class="sxs-lookup"><span data-stu-id="0595e-154">`outref<'T>` argument</span></span>|<span data-ttu-id="0595e-155">`[Out]` atributo en el argumento</span><span class="sxs-lookup"><span data-stu-id="0595e-155">`[Out]` attribute on argument</span></span>|

### <a name="type-inference-and-overloading-rules"></a><span data-ttu-id="0595e-156">Inferencia de tipos y reglas de sobrecarga</span><span class="sxs-lookup"><span data-stu-id="0595e-156">Type inference and overloading rules</span></span>

<span data-ttu-id="0595e-157">El F# compilador deduce un tipo `inref<'T>` en los casos siguientes:</span><span class="sxs-lookup"><span data-stu-id="0595e-157">An `inref<'T>` type is inferred by the F# compiler in the following cases:</span></span>

1. <span data-ttu-id="0595e-158">Un parámetro o tipo de valor devuelto de .NET que tiene un atributo `IsReadOnly`.</span><span class="sxs-lookup"><span data-stu-id="0595e-158">A .NET parameter or return type that has an `IsReadOnly` attribute.</span></span>
2. <span data-ttu-id="0595e-159">`this` puntero en un tipo de estructura que no tiene ningún campo mutable.</span><span class="sxs-lookup"><span data-stu-id="0595e-159">The `this` pointer on a struct type that has no mutable fields.</span></span>
3. <span data-ttu-id="0595e-160">Dirección de una ubicación de memoria derivada de otro puntero `inref<_>`.</span><span class="sxs-lookup"><span data-stu-id="0595e-160">The address of a memory location derived from another `inref<_>` pointer.</span></span>

<span data-ttu-id="0595e-161">Cuando se está llevando a cabo una dirección implícita de un `inref`, se prefiere una sobrecarga con un argumento de tipo `SomeType` a una sobrecarga con un argumento de tipo `inref<SomeType>`.</span><span class="sxs-lookup"><span data-stu-id="0595e-161">When an implicit address of an `inref` is being taken, an overload with an argument of type `SomeType` is preferred to an overload with an argument of type `inref<SomeType>`.</span></span> <span data-ttu-id="0595e-162">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0595e-162">For example:</span></span>

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

<span data-ttu-id="0595e-163">En ambos casos, las sobrecargas que toman `System.DateTime` se resuelven en lugar de las sobrecargas que toman `inref<System.DateTime>`.</span><span class="sxs-lookup"><span data-stu-id="0595e-163">In both cases, the overloads taking `System.DateTime` are resolved rather than the overloads taking `inref<System.DateTime>`.</span></span>

## <a name="byref-like-structs"></a><span data-ttu-id="0595e-164">Structs similares a ByRef</span><span class="sxs-lookup"><span data-stu-id="0595e-164">Byref-like structs</span></span>

<span data-ttu-id="0595e-165">Además de la `byref`/`inref`/de `outref` trío, puede definir sus propios Structs que pueden adherirse a la semántica similar a la de `byref`.</span><span class="sxs-lookup"><span data-stu-id="0595e-165">In addition to the `byref`/`inref`/`outref` trio, you can define your own structs that can adhere to `byref`-like semantics.</span></span> <span data-ttu-id="0595e-166">Esto se hace con el atributo <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute>:</span><span class="sxs-lookup"><span data-stu-id="0595e-166">This is done with the <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> attribute:</span></span>

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

<span data-ttu-id="0595e-167">`IsByRefLike` no implica `Struct`.</span><span class="sxs-lookup"><span data-stu-id="0595e-167">`IsByRefLike` does not imply `Struct`.</span></span> <span data-ttu-id="0595e-168">Ambos deben estar presentes en el tipo.</span><span class="sxs-lookup"><span data-stu-id="0595e-168">Both must be present on the type.</span></span>

<span data-ttu-id="0595e-169">Un struct "`byref`" en F# es un tipo de valor enlazado a la pila.</span><span class="sxs-lookup"><span data-stu-id="0595e-169">A "`byref`-like" struct in F# is a stack-bound value type.</span></span> <span data-ttu-id="0595e-170">Nunca se asigna en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="0595e-170">It is never allocated on the managed heap.</span></span> <span data-ttu-id="0595e-171">Una estructura de tipo `byref`es útil para la programación de alto rendimiento, ya que se aplica con un conjunto de comprobaciones fuertes sobre la duración y la no captura.</span><span class="sxs-lookup"><span data-stu-id="0595e-171">A `byref`-like struct is useful for high-performance programming, as it is enforced with set of strong checks about lifetime and non-capture.</span></span> <span data-ttu-id="0595e-172">Las reglas son:</span><span class="sxs-lookup"><span data-stu-id="0595e-172">The rules are:</span></span>

* <span data-ttu-id="0595e-173">Se pueden usar como parámetros de función, parámetros de método, variables locales, devoluciones de métodos.</span><span class="sxs-lookup"><span data-stu-id="0595e-173">They can be used as function parameters, method parameters, local variables, method returns.</span></span>
* <span data-ttu-id="0595e-174">No pueden ser miembros estáticos o de instancia de una clase o un struct normal.</span><span class="sxs-lookup"><span data-stu-id="0595e-174">They cannot be static or instance members of a class or normal struct.</span></span>
* <span data-ttu-id="0595e-175">No se pueden capturar con ninguna construcción de cierre (métodos`async` o expresiones lambda).</span><span class="sxs-lookup"><span data-stu-id="0595e-175">They cannot be captured by any closure construct (`async` methods or lambda expressions).</span></span>
* <span data-ttu-id="0595e-176">No se pueden usar como parámetros genéricos.</span><span class="sxs-lookup"><span data-stu-id="0595e-176">They cannot be used as a generic parameter.</span></span>

<span data-ttu-id="0595e-177">Este último punto es fundamental para F# la programación de estilo de canalización, dado que `|>` es una función genérica que parametriza sus tipos de entrada.</span><span class="sxs-lookup"><span data-stu-id="0595e-177">This last point is crucial for F# pipeline-style programming, as `|>` is a generic function that parameterizes its input types.</span></span> <span data-ttu-id="0595e-178">Esta restricción puede ser relajada para `|>` en el futuro, ya que está alineada y no realiza ninguna llamada a funciones genéricas no insertadas en su cuerpo.</span><span class="sxs-lookup"><span data-stu-id="0595e-178">This restriction may be relaxed for `|>` in the future, as it is inline and does not make any calls to non-inlined generic functions in its body.</span></span>

<span data-ttu-id="0595e-179">Aunque estas reglas restringen considerablemente el uso, lo hacen para satisfacer la promesa de la informática de alto rendimiento de una manera segura.</span><span class="sxs-lookup"><span data-stu-id="0595e-179">Although these rules very strongly restrict usage, they do so to fulfill the promise of high-performance computing in a safe manner.</span></span>

## <a name="byref-returns"></a><span data-ttu-id="0595e-180">ByRef devuelve</span><span class="sxs-lookup"><span data-stu-id="0595e-180">Byref returns</span></span>

<span data-ttu-id="0595e-181">ByRef devuelve de F# funciones o miembros que se pueden generar y consumir.</span><span class="sxs-lookup"><span data-stu-id="0595e-181">Byref returns from F# functions or members can be produced and consumed.</span></span> <span data-ttu-id="0595e-182">Cuando se utiliza un método de devolución de `byref`, el valor se desreferencia implícitamente.</span><span class="sxs-lookup"><span data-stu-id="0595e-182">When consuming a `byref`-returning method, the value is implicitly dereferenced.</span></span> <span data-ttu-id="0595e-183">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0595e-183">For example:</span></span>

```fsharp
let safeSum(bytes: Span<byte>) =
    let mutable sum = 0
    for i in 0 .. bytes.Length - 1 do
        sum <- sum + int bytes.[i]
    sum

let sum = safeSum(mySpanOfBytes)
printfn "%d" sum // 'sum' is of type 'int'
```

<span data-ttu-id="0595e-184">Para evitar la desreferenciación implícita, como pasar una referencia a través de varias llamadas encadenadas, use `&x` (donde `x` es el valor).</span><span class="sxs-lookup"><span data-stu-id="0595e-184">To avoid the implicit dereference, such as passing a reference through multiple chained calls, use `&x` (where `x` is the value).</span></span>

<span data-ttu-id="0595e-185">También puede asignar directamente a un `byref`devuelto.</span><span class="sxs-lookup"><span data-stu-id="0595e-185">You can also directly assign to a return `byref`.</span></span> <span data-ttu-id="0595e-186">Considere el siguiente programa (muy imperativo):</span><span class="sxs-lookup"><span data-stu-id="0595e-186">Consider the following (highly imperative) program:</span></span>

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

<span data-ttu-id="0595e-187">Éste es el resultado:</span><span class="sxs-lookup"><span data-stu-id="0595e-187">This is the output:</span></span>

```console
Original sequence: 1 3 7 15 31 63 127 255 511 1023
New sequence:      1 3 7 30 31 63 127 255 511 1023
```

## <a name="scoping-for-byrefs"></a><span data-ttu-id="0595e-188">Ámbito de byrefs</span><span class="sxs-lookup"><span data-stu-id="0595e-188">Scoping for byrefs</span></span>

<span data-ttu-id="0595e-189">Un valor enlazado a `let`no puede tener su referencia superior al ámbito en el que se definió.</span><span class="sxs-lookup"><span data-stu-id="0595e-189">A `let`-bound value cannot have its reference exceed the scope in which it was defined.</span></span> <span data-ttu-id="0595e-190">Por ejemplo, no se permite lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0595e-190">For example, the following is disallowed:</span></span>

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

<span data-ttu-id="0595e-191">Esto evita que se obtengan resultados diferentes en función de si se compila con las optimizaciones activadas o desactivadas.</span><span class="sxs-lookup"><span data-stu-id="0595e-191">This prevents you from getting different results depending on if you compile with optimizations on or off.</span></span>
