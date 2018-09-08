---
title: 'Tipos de referencia (F #)'
description: 'Obtenga información sobre byref y similar a byref tipos en F #, que se usan para la programación de bajo nivel.'
ms.date: 09/02/2018
ms.openlocfilehash: 7d4138649ee39a0d342db2828ad4d32fbded978c
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44206539"
---
# <a name="byrefs"></a><span data-ttu-id="c479d-103">Tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="c479d-103">Byrefs</span></span>

<span data-ttu-id="c479d-104">F # tiene dos áreas de características principales que se tratan en el espacio de la programación de bajo nivel:</span><span class="sxs-lookup"><span data-stu-id="c479d-104">F# has two major feature areas that deal in the space of low-level programming:</span></span>

* <span data-ttu-id="c479d-105">El `byref` / `inref` / `outref` tipos, que son los punteros administrados.</span><span class="sxs-lookup"><span data-stu-id="c479d-105">The `byref`/`inref`/`outref` types, which are a managed pointers.</span></span> <span data-ttu-id="c479d-106">Tienen restricciones de uso para que no se puede compilar un programa que no es válido en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="c479d-106">They have restrictions on usage so that you cannot compile a program that is invalid at runtime.</span></span>
* <span data-ttu-id="c479d-107">Un `byref`-como estructura, que es un [estructura](structures.md) que tiene una semántica similar y las mismas restricciones de tiempo de compilación que `byref<'T>`.</span><span class="sxs-lookup"><span data-stu-id="c479d-107">A `byref`-like struct, which is a [structure](structures.md) that has similar semantics and the same compile-time restrictions as `byref<'T>`.</span></span> <span data-ttu-id="c479d-108">Un ejemplo es <xref:System.Span%601>.</span><span class="sxs-lookup"><span data-stu-id="c479d-108">One example is <xref:System.Span%601>.</span></span>

## <a name="syntax"></a><span data-ttu-id="c479d-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c479d-109">Syntax</span></span>

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

## <a name="byref-inref-and-outref"></a><span data-ttu-id="c479d-110">ByRef, inref y outref</span><span class="sxs-lookup"><span data-stu-id="c479d-110">Byref, inref, and outref</span></span>

<span data-ttu-id="c479d-111">Hay tres formas de `byref`:</span><span class="sxs-lookup"><span data-stu-id="c479d-111">There are three forms of `byref`:</span></span>

* <span data-ttu-id="c479d-112">`inref<'T>`, un puntero administrado para leer el valor subyacente.</span><span class="sxs-lookup"><span data-stu-id="c479d-112">`inref<'T>`, a managed pointer for reading the underlying value.</span></span>
* <span data-ttu-id="c479d-113">`outref<'T>`, un puntero administrado para escribir en el valor subyacente.</span><span class="sxs-lookup"><span data-stu-id="c479d-113">`outref<'T>`, a managed pointer for writing to the underlying value.</span></span>
* <span data-ttu-id="c479d-114">`byref<'T>`, un puntero administrado para leer y escribir el valor subyacente.</span><span class="sxs-lookup"><span data-stu-id="c479d-114">`byref<'T>`, a managed pointer for reading and writing the underlying value.</span></span>

<span data-ttu-id="c479d-115">Un `byref<'T>` donde se puede pasar un `inref<'T>` se espera.</span><span class="sxs-lookup"><span data-stu-id="c479d-115">A `byref<'T>` can be passed where an `inref<'T>` is expected.</span></span> <span data-ttu-id="c479d-116">De forma similar, un `byref<'T>` donde se puede pasar un `outref<'T>` se espera.</span><span class="sxs-lookup"><span data-stu-id="c479d-116">Similarly, a `byref<'T>` can be passed where an `outref<'T>` is expected.</span></span>

## <a name="using-byrefs"></a><span data-ttu-id="c479d-117">Uso de tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="c479d-117">Using byrefs</span></span>

<span data-ttu-id="c479d-118">Para usar un `inref<'T>`, deberá obtener un valor de puntero con `&`:</span><span class="sxs-lookup"><span data-stu-id="c479d-118">To use a `inref<'T>`, you need to get a pointer value with `&`:</span></span>

```fsharp
open System

let f (dt: inref<DateTime>) =
    printfn "Now: %s" (dt.ToString())

let dt = DateTime.Now
f &dt // Pass a pointer to 'dt'
```

<span data-ttu-id="c479d-119">Para escribir en el puntero mediante el uso de un `outref<'T>` o `byref<'T>`, también debe hacer que el valor tomar un puntero a `mutable`.</span><span class="sxs-lookup"><span data-stu-id="c479d-119">To write to the pointer by using an `outref<'T>` or `byref<'T>`, you must also make the value you grab a pointer to `mutable`.</span></span>

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

<span data-ttu-id="c479d-120">Si solo va a escribir el puntero en lugar de leerlo, considere el uso de `outref<'T>` en lugar de `byref<'T>`.</span><span class="sxs-lookup"><span data-stu-id="c479d-120">If you are only writing the pointer instead of reading it, consider using `outref<'T>` instead of `byref<'T>`.</span></span>

### <a name="inref-semantics"></a><span data-ttu-id="c479d-121">Semántica de Inref</span><span class="sxs-lookup"><span data-stu-id="c479d-121">Inref semantics</span></span>

<span data-ttu-id="c479d-122">Observe el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="c479d-122">Consider the following code:</span></span>

```fsharp
let f (x: inref<SomeStruct>) = s.SomeField
```

<span data-ttu-id="c479d-123">Semánticamente, esto significa lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c479d-123">Semantically, this means the following:</span></span>

* <span data-ttu-id="c479d-124">El titular de la `x` puntero solo puede usar para leer el valor.</span><span class="sxs-lookup"><span data-stu-id="c479d-124">The holder of the `x` pointer may only use it to read the value.</span></span>
* <span data-ttu-id="c479d-125">Cualquier puntero adquiridos para `struct` campos anidados en `SomeStruct` tienen tipo `inref<_>`.</span><span class="sxs-lookup"><span data-stu-id="c479d-125">Any pointer acquired to `struct` fields nested within `SomeStruct` are given type `inref<_>`.</span></span>

<span data-ttu-id="c479d-126">El siguiente también es cierto:</span><span class="sxs-lookup"><span data-stu-id="c479d-126">The following is also true:</span></span>

* <span data-ttu-id="c479d-127">No hay ninguna implicación que otros subprocesos o alias no tienen acceso de escritura a `x`.</span><span class="sxs-lookup"><span data-stu-id="c479d-127">There is no implication that other threads or aliases do not have write access to `x`.</span></span>
* <span data-ttu-id="c479d-128">No hay ninguna implicación que `SomeStruct` es inmutable en virtud de `x` que se va a un `inref`.</span><span class="sxs-lookup"><span data-stu-id="c479d-128">There is no implication that `SomeStruct` is immutable by virtue of `x` being an `inref`.</span></span>

<span data-ttu-id="c479d-129">Sin embargo, F # para tipos de valor que **son** inmutable, la `this` puntero se infiere para ser un `inref`.</span><span class="sxs-lookup"><span data-stu-id="c479d-129">However, for F# value types that **are** immutable, the `this` pointer is inferred to be an `inref`.</span></span>

<span data-ttu-id="c479d-130">Todas estas reglas juntas significan que el titular de un `inref` puntero no puede modificar el contenido de la memoria que se apunta inmediato.</span><span class="sxs-lookup"><span data-stu-id="c479d-130">All of these rules together mean that the holder of an `inref` pointer may not modify the immediate contents of the memory being pointed to.</span></span>

### <a name="outref-semantics"></a><span data-ttu-id="c479d-131">Semántica de Outref</span><span class="sxs-lookup"><span data-stu-id="c479d-131">Outref semantics</span></span>

<span data-ttu-id="c479d-132">El propósito de `outref<'T>` consiste en indicar que el puntero solo se debe leer desde.</span><span class="sxs-lookup"><span data-stu-id="c479d-132">The purpose of `outref<'T>` is to indicate that the pointer should only be read from.</span></span> <span data-ttu-id="c479d-133">De forma inesperada, `outref<'T>` valor permite leer subyacente a pesar de su nombre.</span><span class="sxs-lookup"><span data-stu-id="c479d-133">Unexpectedly, `outref<'T>` permits reading the underlying value despite its name.</span></span> <span data-ttu-id="c479d-134">Esto es para fines de compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="c479d-134">This is for compatibility purposes.</span></span> <span data-ttu-id="c479d-135">Semánticamente, `outref<'T>` no es diferente a `byref<'T>`.</span><span class="sxs-lookup"><span data-stu-id="c479d-135">Semantically, `outref<'T>` is no different than `byref<'T>`.</span></span>

### <a name="interop-with-c"></a><span data-ttu-id="c479d-136">Interoperabilidad con c#</span><span class="sxs-lookup"><span data-stu-id="c479d-136">Interop with C</span></span> #

<span data-ttu-id="c479d-137">C# admite la `in ref` y `out ref` palabras clave, además de `ref` devuelve.</span><span class="sxs-lookup"><span data-stu-id="c479d-137">C# supports the `in ref` and `out ref` keywords, in addition to `ref` returns.</span></span> <span data-ttu-id="c479d-138">En la tabla siguiente se muestra cómo F # interpreta qué C# emite:</span><span class="sxs-lookup"><span data-stu-id="c479d-138">The following table shows how F# interprets what C# emits:</span></span>

|<span data-ttu-id="c479d-139">Construcción de C#</span><span class="sxs-lookup"><span data-stu-id="c479d-139">C# construct</span></span>|<span data-ttu-id="c479d-140">F # infiere</span><span class="sxs-lookup"><span data-stu-id="c479d-140">F# infers</span></span>|
|------------|---------|
|<span data-ttu-id="c479d-141">`ref` Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c479d-141">`ref` return value</span></span>|`outref<'T>`|
|<span data-ttu-id="c479d-142">`ref readonly` Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c479d-142">`ref readonly` return value</span></span>|`inref<'T>`|
|<span data-ttu-id="c479d-143">`in ref` Parámetro</span><span class="sxs-lookup"><span data-stu-id="c479d-143">`in ref` parameter</span></span>|`inref<'T>`|
|<span data-ttu-id="c479d-144">`out ref` Parámetro</span><span class="sxs-lookup"><span data-stu-id="c479d-144">`out ref` parameter</span></span>|`outref<'T>`|

<span data-ttu-id="c479d-145">En la tabla siguiente se muestra lo que F # emite:</span><span class="sxs-lookup"><span data-stu-id="c479d-145">The following table shows what F# emits:</span></span>

|<span data-ttu-id="c479d-146">Construcción de F #</span><span class="sxs-lookup"><span data-stu-id="c479d-146">F# construct</span></span>|<span data-ttu-id="c479d-147">Construcción emitido</span><span class="sxs-lookup"><span data-stu-id="c479d-147">Emitted construct</span></span>|
|------------|-----------------|
|<span data-ttu-id="c479d-148">`inref<'T>` argumento</span><span class="sxs-lookup"><span data-stu-id="c479d-148">`inref<'T>` argument</span></span>|<span data-ttu-id="c479d-149">`[In]` atributo de argumento</span><span class="sxs-lookup"><span data-stu-id="c479d-149">`[In]` attribute on argument</span></span>|
|<span data-ttu-id="c479d-150">`inref<'T>` devolver</span><span class="sxs-lookup"><span data-stu-id="c479d-150">`inref<'T>` return</span></span>|<span data-ttu-id="c479d-151">`modreq` atributo de valor</span><span class="sxs-lookup"><span data-stu-id="c479d-151">`modreq` attribute on value</span></span>|
|<span data-ttu-id="c479d-152">`inref<'T>` en la ranura abstracta o la implementación</span><span class="sxs-lookup"><span data-stu-id="c479d-152">`inref<'T>` in abstract slot or implementation</span></span>|<span data-ttu-id="c479d-153">`modreq` en el valor devuelto o argumento</span><span class="sxs-lookup"><span data-stu-id="c479d-153">`modreq` on argument or return</span></span>|
|<span data-ttu-id="c479d-154">`outref<'T>` argumento</span><span class="sxs-lookup"><span data-stu-id="c479d-154">`outref<'T>` argument</span></span>|<span data-ttu-id="c479d-155">`[Out]` atributo de argumento</span><span class="sxs-lookup"><span data-stu-id="c479d-155">`[Out]` attribute on argument</span></span>|

### <a name="type-inference-and-overloading-rules"></a><span data-ttu-id="c479d-156">Inferencia de tipos y las reglas de sobrecarga</span><span class="sxs-lookup"><span data-stu-id="c479d-156">Type inference and overloading rules</span></span>

<span data-ttu-id="c479d-157">Un `inref<'T>` tipo se deduce el compilador de F # en los casos siguientes:</span><span class="sxs-lookup"><span data-stu-id="c479d-157">An `inref<'T>` type is inferred by the F# compiler in the following cases:</span></span>

1. <span data-ttu-id="c479d-158">Un tipo de parámetro o valor devuelto de .NET que tiene un `IsReadOnly` atributo.</span><span class="sxs-lookup"><span data-stu-id="c479d-158">A .NET parameter or return type that has an `IsReadOnly` attribute.</span></span>
2. <span data-ttu-id="c479d-159">El `this` puntero en un tipo de estructura que no tiene ningún campo mutable.</span><span class="sxs-lookup"><span data-stu-id="c479d-159">The `this` pointer on a struct type that has no mutable fields.</span></span>
3. <span data-ttu-id="c479d-160">La dirección de una ubicación de memoria que deriva de otro `inref<_>` puntero.</span><span class="sxs-lookup"><span data-stu-id="c479d-160">The address of a memory location derived from another `inref<_>` pointer.</span></span>

<span data-ttu-id="c479d-161">Cuando una dirección implícita de un `inref` se realiza, una sobrecarga con un argumento de tipo `SomeType` es preferible a una sobrecarga con un argumento de tipo `inref<SomeType>`.</span><span class="sxs-lookup"><span data-stu-id="c479d-161">When an implicit address of an `inref` is being taken, an overload with an argument of type `SomeType` is preferred to an overload with an argument of type `inref<SomeType>`.</span></span> <span data-ttu-id="c479d-162">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c479d-162">For example:</span></span>

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

<span data-ttu-id="c479d-163">En ambos casos, las sobrecargas que toman `System.DateTime` se resuelven en lugar de las sobrecargas que toman `inref<System.DateTime>`.</span><span class="sxs-lookup"><span data-stu-id="c479d-163">In both cases, the overloads taking `System.DateTime` are resolved rather than the overloads taking `inref<System.DateTime>`.</span></span>

## <a name="byref-like-structs"></a><span data-ttu-id="c479d-164">Similar a ByRef structs</span><span class="sxs-lookup"><span data-stu-id="c479d-164">Byref-like structs</span></span>

<span data-ttu-id="c479d-165">Además el `byref` / `inref` / `outref` trío, puede definir sus propias estructuras que pueden cumplir `byref`-como semántica.</span><span class="sxs-lookup"><span data-stu-id="c479d-165">In addition to the `byref`/`inref`/`outref` trio, you can define your own structs that can adhere to `byref`-like semantics.</span></span> <span data-ttu-id="c479d-166">Esto se realiza con el <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> atributo:</span><span class="sxs-lookup"><span data-stu-id="c479d-166">This is done with the <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> attribute:</span></span>

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

<span data-ttu-id="c479d-167">`IsByRefLike` no implica `Struct`.</span><span class="sxs-lookup"><span data-stu-id="c479d-167">`IsByRefLike` does not imply `Struct`.</span></span> <span data-ttu-id="c479d-168">Deben estar presentes en el tipo.</span><span class="sxs-lookup"><span data-stu-id="c479d-168">Both must be present on the type.</span></span>

<span data-ttu-id="c479d-169">Un "`byref`-como" struct en F # es un tipo de valor de límite de la pila.</span><span class="sxs-lookup"><span data-stu-id="c479d-169">A "`byref`-like" struct in F# is a stack-bound value type.</span></span> <span data-ttu-id="c479d-170">Nunca se asigna en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="c479d-170">It is never allocated on the managed heap.</span></span> <span data-ttu-id="c479d-171">Un `byref`-como struct es útil para la programación de alto rendimiento, ya que se aplica con el conjunto de controles sólidos sobre la duración y no captura.</span><span class="sxs-lookup"><span data-stu-id="c479d-171">A `byref`-like struct is useful for high-performance programming, as it is enforced with set of strong checks about lifetime and non-capture.</span></span> <span data-ttu-id="c479d-172">Las reglas son:</span><span class="sxs-lookup"><span data-stu-id="c479d-172">The rules are:</span></span>

* <span data-ttu-id="c479d-173">Se puede usar como parámetros de función, parámetros de método, las variables locales, devuelve el método.</span><span class="sxs-lookup"><span data-stu-id="c479d-173">They can be used as function parameters, method parameters, local variables, method returns.</span></span>
* <span data-ttu-id="c479d-174">Que no pueden ser estáticos o miembros de una clase o estructura normal de instancia.</span><span class="sxs-lookup"><span data-stu-id="c479d-174">They cannot be static or instance members of a class or normal struct.</span></span>
* <span data-ttu-id="c479d-175">No se puede capturar cualquier construcción de cierre (`async` métodos o expresiones lambda).</span><span class="sxs-lookup"><span data-stu-id="c479d-175">They cannot be captured by any closure construct (`async` methods or lambda expressions).</span></span>
* <span data-ttu-id="c479d-176">No se puede usar como un parámetro genérico.</span><span class="sxs-lookup"><span data-stu-id="c479d-176">They cannot be used as a generic parameter.</span></span>

<span data-ttu-id="c479d-177">Este último punto es fundamental para F # programación al estilo de la canalización, como `|>` es una función genérica que parametriza sus tipos de entrada.</span><span class="sxs-lookup"><span data-stu-id="c479d-177">This last point is crucial for F# pipeline-style programming, as `|>` is a generic function that parameterizes its input types.</span></span> <span data-ttu-id="c479d-178">Esta restricción puede ser más flexible para `|>` en el futuro, tal como está en línea y no se realizan alguna llamada a funciones genéricas no alineada en el cuerpo.</span><span class="sxs-lookup"><span data-stu-id="c479d-178">This restriction may be relaxed for `|>` in the future, as it is inline and does not make any calls to non-inlined generic functions in its body.</span></span>

<span data-ttu-id="c479d-179">Aunque estas reglas encarecidamente restringen el uso, lo hacen para cumplir la promesa de informática de alto rendimiento de una manera segura.</span><span class="sxs-lookup"><span data-stu-id="c479d-179">Although these rules very strongly restrict usage, they do so to fulfill the promise of high-performance computing in a safe manner.</span></span>

## <a name="byref-returns"></a><span data-ttu-id="c479d-180">Devuelve ByRef</span><span class="sxs-lookup"><span data-stu-id="c479d-180">Byref returns</span></span>

<span data-ttu-id="c479d-181">ByRef devuelve de las funciones de F # o los miembros pueden produce y consume.</span><span class="sxs-lookup"><span data-stu-id="c479d-181">Byref returns from F# functions or members can be produced and consumed.</span></span> <span data-ttu-id="c479d-182">Al consumir un `byref`-método de devolución, el valor se ha desreferenciado implícitamente.</span><span class="sxs-lookup"><span data-stu-id="c479d-182">When consuming a `byref`-returning method, the value is implicitly dereferenced.</span></span> <span data-ttu-id="c479d-183">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c479d-183">For example:</span></span>

```fsharp
let safeSum(bytes: Span<byte>) =
    let mutable sum = 0
    for i in 0 .. bytes.Length - 1 do
        sum <- sum + int bytes.[i]
    sum

let sum = safeSum(mySpanOfBytes)
printfn "%d" sum // 'sum' is of type 'int'
```

<span data-ttu-id="c479d-184">Para evitar la desreferenciación implícito, por ejemplo, pasar una referencia a través de varias llamadas encadenadas, use `&x` (donde `x` es el valor).</span><span class="sxs-lookup"><span data-stu-id="c479d-184">To avoid the implicit dereference, such as passing a reference through multiple chained calls, use `&x` (where `x` is the value).</span></span>

<span data-ttu-id="c479d-185">Puede asignar directamente a una devolución `byref`.</span><span class="sxs-lookup"><span data-stu-id="c479d-185">You can also directly assign to a return `byref`.</span></span> <span data-ttu-id="c479d-186">Considere el siguiente programa (muy imperativo):</span><span class="sxs-lookup"><span data-stu-id="c479d-186">Consider the following (highly imperative) program:</span></span>

```fsharp
ype C() =
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

<span data-ttu-id="c479d-187">Éste es el resultado:</span><span class="sxs-lookup"><span data-stu-id="c479d-187">This is the output:</span></span>

```console
Original sequence: 1 3 7 15 31 63 127 255 511 1023
New sequence:      1 3 7 30 31 63 127 255 511 1023
```

## <a name="scoping-for-byrefs"></a><span data-ttu-id="c479d-188">Definir el ámbito para los tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="c479d-188">Scoping for byrefs</span></span>

<span data-ttu-id="c479d-189">Un `let`-valor enlazado no puede tener su referencia superen el ámbito en el que se ha definido.</span><span class="sxs-lookup"><span data-stu-id="c479d-189">A `let`-bound value cannot have its reference exceed the scope in which it was defined.</span></span> <span data-ttu-id="c479d-190">Por ejemplo, se permite lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c479d-190">For example, the following is disallowed:</span></span>

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

<span data-ttu-id="c479d-191">Esto evita que se obtengan resultados diferentes dependiendo de si se compila con las optimizaciones activado o desactivado.</span><span class="sxs-lookup"><span data-stu-id="c479d-191">This prevents you from getting different results depending on if you compile with optimizations on or off.</span></span>