---
title: Byrefs
description: 'Obtenga información sobre los tipos byref y tipo ByRef en F #, que se usan para la programación de bajo nivel.'
ms.date: 11/04/2019
ms.openlocfilehash: ff2c06d8940f7341d5d8b1d942be264bfac586c5
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "96740320"
---
# <a name="byrefs"></a><span data-ttu-id="b8ea3-103">Byrefs</span><span class="sxs-lookup"><span data-stu-id="b8ea3-103">Byrefs</span></span>

<span data-ttu-id="b8ea3-104">F # tiene dos áreas de características principales que se ocupan del espacio de programación de bajo nivel:</span><span class="sxs-lookup"><span data-stu-id="b8ea3-104">F# has two major feature areas that deal in the space of low-level programming:</span></span>

* <span data-ttu-id="b8ea3-105">Los `byref` / `inref` / `outref` tipos, que son punteros administrados.</span><span class="sxs-lookup"><span data-stu-id="b8ea3-105">The `byref`/`inref`/`outref` types, which are managed pointers.</span></span> <span data-ttu-id="b8ea3-106">Tienen restricciones de uso para que no pueda compilar un programa que no sea válido en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b8ea3-106">They have restrictions on usage so that you cannot compile a program that is invalid at run time.</span></span>
* <span data-ttu-id="b8ea3-107">Un `byref` struct similar a, que es una [estructura](structures.md) que tiene una semántica similar y las mismas restricciones en tiempo de compilación que `byref<'T>` .</span><span class="sxs-lookup"><span data-stu-id="b8ea3-107">A `byref`-like struct, which is a [structure](structures.md) that has similar semantics and the same compile-time restrictions as `byref<'T>`.</span></span> <span data-ttu-id="b8ea3-108">Un ejemplo es <xref:System.Span%601> .</span><span class="sxs-lookup"><span data-stu-id="b8ea3-108">One example is <xref:System.Span%601>.</span></span>

## <a name="syntax"></a><span data-ttu-id="b8ea3-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="b8ea3-109">Syntax</span></span>

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

## <a name="byref-inref-and-outref"></a><span data-ttu-id="b8ea3-110">ByRef, inref y outref</span><span class="sxs-lookup"><span data-stu-id="b8ea3-110">Byref, inref, and outref</span></span>

<span data-ttu-id="b8ea3-111">Hay tres formas de `byref` :</span><span class="sxs-lookup"><span data-stu-id="b8ea3-111">There are three forms of `byref`:</span></span>

* <span data-ttu-id="b8ea3-112">`inref<'T>`, un puntero administrado para leer el valor subyacente.</span><span class="sxs-lookup"><span data-stu-id="b8ea3-112">`inref<'T>`, a managed pointer for reading the underlying value.</span></span>
* <span data-ttu-id="b8ea3-113">`outref<'T>`, un puntero administrado para escribir en el valor subyacente.</span><span class="sxs-lookup"><span data-stu-id="b8ea3-113">`outref<'T>`, a managed pointer for writing to the underlying value.</span></span>
* <span data-ttu-id="b8ea3-114">`byref<'T>`, un puntero administrado para leer y escribir el valor subyacente.</span><span class="sxs-lookup"><span data-stu-id="b8ea3-114">`byref<'T>`, a managed pointer for reading and writing the underlying value.</span></span>

<span data-ttu-id="b8ea3-115">Se `byref<'T>` puede pasar una en la que `inref<'T>` se espera un.</span><span class="sxs-lookup"><span data-stu-id="b8ea3-115">A `byref<'T>` can be passed where an `inref<'T>` is expected.</span></span> <span data-ttu-id="b8ea3-116">Del mismo modo, se `byref<'T>` puede pasar una en la que `outref<'T>` se espera un.</span><span class="sxs-lookup"><span data-stu-id="b8ea3-116">Similarly, a `byref<'T>` can be passed where an `outref<'T>` is expected.</span></span>

## <a name="using-byrefs"></a><span data-ttu-id="b8ea3-117">Usar byrefs</span><span class="sxs-lookup"><span data-stu-id="b8ea3-117">Using byrefs</span></span>

<span data-ttu-id="b8ea3-118">Para usar un `inref<'T>` , debe obtener un valor de puntero con `&` :</span><span class="sxs-lookup"><span data-stu-id="b8ea3-118">To use a `inref<'T>`, you need to get a pointer value with `&`:</span></span>

```fsharp
open System

let f (dt: inref<DateTime>) =
    printfn $"Now: %O{dt}"

let usage =
    let dt = DateTime.Now
    f &dt // Pass a pointer to 'dt'
```

<span data-ttu-id="b8ea3-119">Para escribir en el puntero mediante `outref<'T>` o `byref<'T>` , también debe hacer el valor con el que se obtiene un puntero `mutable` .</span><span class="sxs-lookup"><span data-stu-id="b8ea3-119">To write to the pointer by using an `outref<'T>` or `byref<'T>`, you must also make the value you grab a pointer to `mutable`.</span></span>

```fsharp
open System

let f (dt: byref<DateTime>) =
    printfn $"Now: %O{dt}"
    dt <- DateTime.Now

// Make 'dt' mutable
let mutable dt = DateTime.Now

// Now you can pass the pointer to 'dt'
f &dt
```

<span data-ttu-id="b8ea3-120">Si solo está escribiendo el puntero en lugar de leerlo, considere la posibilidad `outref<'T>` de usar en lugar de `byref<'T>` .</span><span class="sxs-lookup"><span data-stu-id="b8ea3-120">If you are only writing the pointer instead of reading it, consider using `outref<'T>` instead of `byref<'T>`.</span></span>

### <a name="inref-semantics"></a><span data-ttu-id="b8ea3-121">Semántica de Inref</span><span class="sxs-lookup"><span data-stu-id="b8ea3-121">Inref semantics</span></span>

<span data-ttu-id="b8ea3-122">Tenga en cuenta el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="b8ea3-122">Consider the following code:</span></span>

```fsharp
let f (x: inref<SomeStruct>) = x.SomeField
```

<span data-ttu-id="b8ea3-123">Semánticamente, esto significa lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b8ea3-123">Semantically, this means the following:</span></span>

* <span data-ttu-id="b8ea3-124">El titular del `x` puntero solo puede usarlo para leer el valor.</span><span class="sxs-lookup"><span data-stu-id="b8ea3-124">The holder of the `x` pointer may only use it to read the value.</span></span>
* <span data-ttu-id="b8ea3-125">Cualquier puntero adquirido a `struct` campos anidados en `SomeStruct` se proporciona de tipo `inref<_>` .</span><span class="sxs-lookup"><span data-stu-id="b8ea3-125">Any pointer acquired to `struct` fields nested within `SomeStruct` are given type `inref<_>`.</span></span>

<span data-ttu-id="b8ea3-126">También se cumple lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b8ea3-126">The following is also true:</span></span>

* <span data-ttu-id="b8ea3-127">No hay ninguna implicación de que otros subprocesos o alias no tengan acceso de escritura a `x` .</span><span class="sxs-lookup"><span data-stu-id="b8ea3-127">There is no implication that other threads or aliases do not have write access to `x`.</span></span>
* <span data-ttu-id="b8ea3-128">No hay ninguna implicación que `SomeStruct` sea inmutable en virtud de `x` ser una `inref` .</span><span class="sxs-lookup"><span data-stu-id="b8ea3-128">There is no implication that `SomeStruct` is immutable by virtue of `x` being an `inref`.</span></span>

<span data-ttu-id="b8ea3-129">Sin embargo, para los tipos de valor de F # que **son** inmutables, el `this` puntero se deduce como `inref` .</span><span class="sxs-lookup"><span data-stu-id="b8ea3-129">However, for F# value types that **are** immutable, the `this` pointer is inferred to be an `inref`.</span></span>

<span data-ttu-id="b8ea3-130">Todas estas reglas juntas indican que el titular de un `inref` puntero no puede modificar el contenido inmediato de la memoria a la que se apunta.</span><span class="sxs-lookup"><span data-stu-id="b8ea3-130">All of these rules together mean that the holder of an `inref` pointer may not modify the immediate contents of the memory being pointed to.</span></span>

### <a name="outref-semantics"></a><span data-ttu-id="b8ea3-131">Semántica de Outref</span><span class="sxs-lookup"><span data-stu-id="b8ea3-131">Outref semantics</span></span>

<span data-ttu-id="b8ea3-132">El propósito de `outref<'T>` es indicar que el puntero solo debe escribirse en.</span><span class="sxs-lookup"><span data-stu-id="b8ea3-132">The purpose of `outref<'T>` is to indicate that the pointer should only be written to.</span></span> <span data-ttu-id="b8ea3-133">De forma inesperada, `outref<'T>` permite leer el valor subyacente a pesar de su nombre.</span><span class="sxs-lookup"><span data-stu-id="b8ea3-133">Unexpectedly, `outref<'T>` permits reading the underlying value despite its name.</span></span> <span data-ttu-id="b8ea3-134">Esto es así por motivos de compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="b8ea3-134">This is for compatibility purposes.</span></span> <span data-ttu-id="b8ea3-135">Semánticamente, `outref<'T>` no es diferente de `byref<'T>` .</span><span class="sxs-lookup"><span data-stu-id="b8ea3-135">Semantically, `outref<'T>` is no different than `byref<'T>`.</span></span>

### <a name="interop-with-c"></a><span data-ttu-id="b8ea3-136">Interoperabilidad con C\#</span><span class="sxs-lookup"><span data-stu-id="b8ea3-136">Interop with C\#</span></span>

<span data-ttu-id="b8ea3-137">C# admite las `in ref` `out ref` palabras clave y, además de `ref` devoluciones.</span><span class="sxs-lookup"><span data-stu-id="b8ea3-137">C# supports the `in ref` and `out ref` keywords, in addition to `ref` returns.</span></span> <span data-ttu-id="b8ea3-138">En la tabla siguiente se muestra cómo F # interpreta qué emite C#:</span><span class="sxs-lookup"><span data-stu-id="b8ea3-138">The following table shows how F# interprets what C# emits:</span></span>

|<span data-ttu-id="b8ea3-139">Construcción de C#</span><span class="sxs-lookup"><span data-stu-id="b8ea3-139">C# construct</span></span>|<span data-ttu-id="b8ea3-140">Deduces de F #</span><span class="sxs-lookup"><span data-stu-id="b8ea3-140">F# infers</span></span>|
|------------|---------|
|<span data-ttu-id="b8ea3-141">`ref` valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b8ea3-141">`ref` return value</span></span>|`outref<'T>`|
|<span data-ttu-id="b8ea3-142">`ref readonly` valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b8ea3-142">`ref readonly` return value</span></span>|`inref<'T>`|
|<span data-ttu-id="b8ea3-143">Parámetro `in ref`</span><span class="sxs-lookup"><span data-stu-id="b8ea3-143">`in ref` parameter</span></span>|`inref<'T>`|
|<span data-ttu-id="b8ea3-144">Parámetro `out ref`</span><span class="sxs-lookup"><span data-stu-id="b8ea3-144">`out ref` parameter</span></span>|`outref<'T>`|

<span data-ttu-id="b8ea3-145">En la tabla siguiente se muestra qué emite F #:</span><span class="sxs-lookup"><span data-stu-id="b8ea3-145">The following table shows what F# emits:</span></span>

|<span data-ttu-id="b8ea3-146">Construcción de F #</span><span class="sxs-lookup"><span data-stu-id="b8ea3-146">F# construct</span></span>|<span data-ttu-id="b8ea3-147">Construcción emitida</span><span class="sxs-lookup"><span data-stu-id="b8ea3-147">Emitted construct</span></span>|
|------------|-----------------|
|<span data-ttu-id="b8ea3-148">Argumento `inref<'T>`</span><span class="sxs-lookup"><span data-stu-id="b8ea3-148">`inref<'T>` argument</span></span>|<span data-ttu-id="b8ea3-149">`[In]` atributo en argumento</span><span class="sxs-lookup"><span data-stu-id="b8ea3-149">`[In]` attribute on argument</span></span>|
|<span data-ttu-id="b8ea3-150">`inref<'T>` devolver</span><span class="sxs-lookup"><span data-stu-id="b8ea3-150">`inref<'T>` return</span></span>|<span data-ttu-id="b8ea3-151">`modreq` atributo en valor</span><span class="sxs-lookup"><span data-stu-id="b8ea3-151">`modreq` attribute on value</span></span>|
|<span data-ttu-id="b8ea3-152">`inref<'T>` en la ranura o la implementación abstracta</span><span class="sxs-lookup"><span data-stu-id="b8ea3-152">`inref<'T>` in abstract slot or implementation</span></span>|<span data-ttu-id="b8ea3-153">`modreq` argumento on o Return</span><span class="sxs-lookup"><span data-stu-id="b8ea3-153">`modreq` on argument or return</span></span>|
|<span data-ttu-id="b8ea3-154">Argumento `outref<'T>`</span><span class="sxs-lookup"><span data-stu-id="b8ea3-154">`outref<'T>` argument</span></span>|<span data-ttu-id="b8ea3-155">`[Out]` atributo en argumento</span><span class="sxs-lookup"><span data-stu-id="b8ea3-155">`[Out]` attribute on argument</span></span>|

### <a name="type-inference-and-overloading-rules"></a><span data-ttu-id="b8ea3-156">Inferencia de tipos y reglas de sobrecarga</span><span class="sxs-lookup"><span data-stu-id="b8ea3-156">Type inference and overloading rules</span></span>

<span data-ttu-id="b8ea3-157">`inref<'T>`El compilador de F # infiere un tipo en los casos siguientes:</span><span class="sxs-lookup"><span data-stu-id="b8ea3-157">An `inref<'T>` type is inferred by the F# compiler in the following cases:</span></span>

1. <span data-ttu-id="b8ea3-158">Un parámetro o tipo de valor devuelto de .NET que tiene un `IsReadOnly` atributo.</span><span class="sxs-lookup"><span data-stu-id="b8ea3-158">A .NET parameter or return type that has an `IsReadOnly` attribute.</span></span>
2. <span data-ttu-id="b8ea3-159">`this`Puntero en un tipo de estructura que no tiene campos mutables.</span><span class="sxs-lookup"><span data-stu-id="b8ea3-159">The `this` pointer on a struct type that has no mutable fields.</span></span>
3. <span data-ttu-id="b8ea3-160">Dirección de una ubicación de memoria derivada de otro `inref<_>` puntero.</span><span class="sxs-lookup"><span data-stu-id="b8ea3-160">The address of a memory location derived from another `inref<_>` pointer.</span></span>

<span data-ttu-id="b8ea3-161">Cuando se está llevando a cabo una dirección implícita de un `inref` , se prefiere una sobrecarga con un argumento de tipo `SomeType` a una sobrecarga con un argumento de tipo `inref<SomeType>` .</span><span class="sxs-lookup"><span data-stu-id="b8ea3-161">When an implicit address of an `inref` is being taken, an overload with an argument of type `SomeType` is preferred to an overload with an argument of type `inref<SomeType>`.</span></span> <span data-ttu-id="b8ea3-162">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b8ea3-162">For example:</span></span>

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

<span data-ttu-id="b8ea3-163">En ambos casos, se resuelven las sobrecargas que toman en `System.DateTime` lugar de las sobrecargas que toman `inref<System.DateTime>` .</span><span class="sxs-lookup"><span data-stu-id="b8ea3-163">In both cases, the overloads taking `System.DateTime` are resolved rather than the overloads taking `inref<System.DateTime>`.</span></span>

## <a name="byref-like-structs"></a><span data-ttu-id="b8ea3-164">Structs similares a ByRef</span><span class="sxs-lookup"><span data-stu-id="b8ea3-164">Byref-like structs</span></span>

<span data-ttu-id="b8ea3-165">Además de los `byref` / `inref` / `outref` tríos, puede definir sus propios Structs que pueden adherirse a la `byref` semántica similar.</span><span class="sxs-lookup"><span data-stu-id="b8ea3-165">In addition to the `byref`/`inref`/`outref` trio, you can define your own structs that can adhere to `byref`-like semantics.</span></span> <span data-ttu-id="b8ea3-166">Esto se hace con el <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> atributo:</span><span class="sxs-lookup"><span data-stu-id="b8ea3-166">This is done with the <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> attribute:</span></span>

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

<span data-ttu-id="b8ea3-167">`IsByRefLike` no implica `Struct` .</span><span class="sxs-lookup"><span data-stu-id="b8ea3-167">`IsByRefLike` does not imply `Struct`.</span></span> <span data-ttu-id="b8ea3-168">Ambos deben estar presentes en el tipo.</span><span class="sxs-lookup"><span data-stu-id="b8ea3-168">Both must be present on the type.</span></span>

<span data-ttu-id="b8ea3-169">Un `byref` struct "similar" en F # es un tipo de valor enlazado a la pila.</span><span class="sxs-lookup"><span data-stu-id="b8ea3-169">A "`byref`-like" struct in F# is a stack-bound value type.</span></span> <span data-ttu-id="b8ea3-170">Nunca se asigna en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="b8ea3-170">It is never allocated on the managed heap.</span></span> <span data-ttu-id="b8ea3-171">Un `byref` struct similar a es útil para la programación de alto rendimiento, ya que se aplica con un conjunto de comprobaciones fuertes sobre la duración y la no captura.</span><span class="sxs-lookup"><span data-stu-id="b8ea3-171">A `byref`-like struct is useful for high-performance programming, as it is enforced with set of strong checks about lifetime and non-capture.</span></span> <span data-ttu-id="b8ea3-172">Las reglas son:</span><span class="sxs-lookup"><span data-stu-id="b8ea3-172">The rules are:</span></span>

* <span data-ttu-id="b8ea3-173">Se pueden usar como parámetros de función, parámetros de método, variables locales, devoluciones de métodos.</span><span class="sxs-lookup"><span data-stu-id="b8ea3-173">They can be used as function parameters, method parameters, local variables, method returns.</span></span>
* <span data-ttu-id="b8ea3-174">No pueden ser miembros estáticos o de instancia de una clase o un struct normal.</span><span class="sxs-lookup"><span data-stu-id="b8ea3-174">They cannot be static or instance members of a class or normal struct.</span></span>
* <span data-ttu-id="b8ea3-175">No se pueden capturar mediante ninguna construcción de cierre ( `async` métodos o expresiones lambda).</span><span class="sxs-lookup"><span data-stu-id="b8ea3-175">They cannot be captured by any closure construct (`async` methods or lambda expressions).</span></span>
* <span data-ttu-id="b8ea3-176">No se pueden usar como parámetros genéricos.</span><span class="sxs-lookup"><span data-stu-id="b8ea3-176">They cannot be used as a generic parameter.</span></span>

<span data-ttu-id="b8ea3-177">Este último punto es fundamental para la programación de estilo de canalización de F #, como `|>` es una función genérica que parametriza sus tipos de entrada.</span><span class="sxs-lookup"><span data-stu-id="b8ea3-177">This last point is crucial for F# pipeline-style programming, as `|>` is a generic function that parameterizes its input types.</span></span> <span data-ttu-id="b8ea3-178">Esta restricción puede ser relajada `|>` en el futuro, ya que está alineada y no realiza ninguna llamada a funciones genéricas no insertadas en su cuerpo.</span><span class="sxs-lookup"><span data-stu-id="b8ea3-178">This restriction may be relaxed for `|>` in the future, as it is inline and does not make any calls to non-inlined generic functions in its body.</span></span>

<span data-ttu-id="b8ea3-179">Aunque estas reglas restringen el uso de forma rigurosa, lo hacen para satisfacer la promesa de la informática de alto rendimiento de una manera segura.</span><span class="sxs-lookup"><span data-stu-id="b8ea3-179">Although these rules strongly restrict usage, they do so to fulfill the promise of high-performance computing in a safe manner.</span></span>

## <a name="byref-returns"></a><span data-ttu-id="b8ea3-180">ByRef devuelve</span><span class="sxs-lookup"><span data-stu-id="b8ea3-180">Byref returns</span></span>

<span data-ttu-id="b8ea3-181">ByRef devuelve de funciones o miembros de F # que se pueden generar y consumir.</span><span class="sxs-lookup"><span data-stu-id="b8ea3-181">Byref returns from F# functions or members can be produced and consumed.</span></span> <span data-ttu-id="b8ea3-182">Cuando se utiliza un `byref` método que devuelve, el valor se desreferencia implícitamente.</span><span class="sxs-lookup"><span data-stu-id="b8ea3-182">When consuming a `byref`-returning method, the value is implicitly dereferenced.</span></span> <span data-ttu-id="b8ea3-183">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b8ea3-183">For example:</span></span>

```fsharp
let squareAndPrint (data : byref<int>) =
    let squared = data*data    // data is implicitly dereferenced
    printfn $"%d{squared}"
```

<span data-ttu-id="b8ea3-184">Para devolver un valor ByRef, la variable que contiene el valor debe ser más larga que el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="b8ea3-184">To return a value byref, the variable that contains the value must live longer than the current scope.</span></span>
<span data-ttu-id="b8ea3-185">Además, para devolver ByRef, use `&value` (donde valor es una variable que reside más tiempo que el ámbito actual).</span><span class="sxs-lookup"><span data-stu-id="b8ea3-185">Also, to return byref, use `&value` (where value is a variable that lives longer than the current scope).</span></span>

```fsharp
let mutable sum = 0
let safeSum (bytes: Span<byte>) =
    for i in 0 .. bytes.Length - 1 do
        sum <- sum + int bytes.[i]
    &sum  // sum lives longer than the scope of this function.
```

<span data-ttu-id="b8ea3-186">Para evitar la desreferenciación implícita, como pasar una referencia a través de varias llamadas encadenadas, use `&x` (donde `x` es el valor).</span><span class="sxs-lookup"><span data-stu-id="b8ea3-186">To avoid the implicit dereference, such as passing a reference through multiple chained calls, use `&x` (where `x` is the value).</span></span>

<span data-ttu-id="b8ea3-187">También puede asignar directamente a un valor devuelto `byref` .</span><span class="sxs-lookup"><span data-stu-id="b8ea3-187">You can also directly assign to a return `byref`.</span></span> <span data-ttu-id="b8ea3-188">Considere el siguiente programa (muy imperativo):</span><span class="sxs-lookup"><span data-stu-id="b8ea3-188">Consider the following (highly imperative) program:</span></span>

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
    printfn $"Original sequence: %O{c}"

    let v = &c.FindLargestSmallerThan 16

    v <- v*2 // Directly assign to the byref return

    printfn $"New sequence:      %O{c}"

    0 // return an integer exit code
```

<span data-ttu-id="b8ea3-189">Éste es el resultado:</span><span class="sxs-lookup"><span data-stu-id="b8ea3-189">This is the output:</span></span>

```console
Original sequence: 1 3 7 15 31 63 127 255 511 1023
New sequence:      1 3 7 30 31 63 127 255 511 1023
```

## <a name="scoping-for-byrefs"></a><span data-ttu-id="b8ea3-190">Ámbito de byrefs</span><span class="sxs-lookup"><span data-stu-id="b8ea3-190">Scoping for byrefs</span></span>

<span data-ttu-id="b8ea3-191">Un `let` valor enlazado a no puede tener su referencia superior al ámbito en el que se definió.</span><span class="sxs-lookup"><span data-stu-id="b8ea3-191">A `let`-bound value cannot have its reference exceed the scope in which it was defined.</span></span> <span data-ttu-id="b8ea3-192">Por ejemplo, no se permite lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b8ea3-192">For example, the following is disallowed:</span></span>

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

<span data-ttu-id="b8ea3-193">Esto evita que se obtengan resultados diferentes en función de si se compila con optimizaciones o no.</span><span class="sxs-lookup"><span data-stu-id="b8ea3-193">This prevents you from getting different results depending on if you compile with optimizations or not.</span></span>
