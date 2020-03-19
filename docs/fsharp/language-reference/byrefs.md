---
title: Byrefs
description: Obtenga más información sobre los tipos byref y byref-like en F, que se utilizan para la programación de bajo nivel.
ms.date: 11/04/2019
ms.openlocfilehash: 527f465ee87fe153a2deae1306b6730531dc4123
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187049"
---
# <a name="byrefs"></a><span data-ttu-id="e1c50-103">Byrefs</span><span class="sxs-lookup"><span data-stu-id="e1c50-103">Byrefs</span></span>

<span data-ttu-id="e1c50-104">F tiene dos áreas de características principales que se ocupa en el espacio de la programación de bajo nivel:</span><span class="sxs-lookup"><span data-stu-id="e1c50-104">F# has two major feature areas that deal in the space of low-level programming:</span></span>

* <span data-ttu-id="e1c50-105">`byref` / Los `inref` / tipos, que son punteros administrados. `outref`</span><span class="sxs-lookup"><span data-stu-id="e1c50-105">The `byref`/`inref`/`outref` types, which are managed pointers.</span></span> <span data-ttu-id="e1c50-106">Tienen restricciones de uso para que no pueda compilar un programa que no sea válido en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="e1c50-106">They have restrictions on usage so that you cannot compile a program that is invalid at run time.</span></span>
* <span data-ttu-id="e1c50-107">Una `byref`estructura -like, que es una [estructura](structures.md) que tiene una semántica `byref<'T>`similar y las mismas restricciones en tiempo de compilación que .</span><span class="sxs-lookup"><span data-stu-id="e1c50-107">A `byref`-like struct, which is a [structure](structures.md) that has similar semantics and the same compile-time restrictions as `byref<'T>`.</span></span> <span data-ttu-id="e1c50-108">Un ejemplo <xref:System.Span%601>es .</span><span class="sxs-lookup"><span data-stu-id="e1c50-108">One example is <xref:System.Span%601>.</span></span>

## <a name="syntax"></a><span data-ttu-id="e1c50-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e1c50-109">Syntax</span></span>

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

## <a name="byref-inref-and-outref"></a><span data-ttu-id="e1c50-110">Byref, inref y outref</span><span class="sxs-lookup"><span data-stu-id="e1c50-110">Byref, inref, and outref</span></span>

<span data-ttu-id="e1c50-111">Hay tres formas `byref`de:</span><span class="sxs-lookup"><span data-stu-id="e1c50-111">There are three forms of `byref`:</span></span>

* <span data-ttu-id="e1c50-112">`inref<'T>`, un puntero administrado para leer el valor subyacente.</span><span class="sxs-lookup"><span data-stu-id="e1c50-112">`inref<'T>`, a managed pointer for reading the underlying value.</span></span>
* <span data-ttu-id="e1c50-113">`outref<'T>`, un puntero administrado para escribir en el valor subyacente.</span><span class="sxs-lookup"><span data-stu-id="e1c50-113">`outref<'T>`, a managed pointer for writing to the underlying value.</span></span>
* <span data-ttu-id="e1c50-114">`byref<'T>`, un puntero administrado para leer y escribir el valor subyacente.</span><span class="sxs-lookup"><span data-stu-id="e1c50-114">`byref<'T>`, a managed pointer for reading and writing the underlying value.</span></span>

<span data-ttu-id="e1c50-115">A `byref<'T>` se puede `inref<'T>` pasar donde se espera un.</span><span class="sxs-lookup"><span data-stu-id="e1c50-115">A `byref<'T>` can be passed where an `inref<'T>` is expected.</span></span> <span data-ttu-id="e1c50-116">Del mismo `byref<'T>` modo, se `outref<'T>` puede pasar a donde se espera un.</span><span class="sxs-lookup"><span data-stu-id="e1c50-116">Similarly, a `byref<'T>` can be passed where an `outref<'T>` is expected.</span></span>

## <a name="using-byrefs"></a><span data-ttu-id="e1c50-117">Uso de byrefs</span><span class="sxs-lookup"><span data-stu-id="e1c50-117">Using byrefs</span></span>

<span data-ttu-id="e1c50-118">Para utilizar `inref<'T>`un , es necesario `&`obtener un valor de puntero con:</span><span class="sxs-lookup"><span data-stu-id="e1c50-118">To use a `inref<'T>`, you need to get a pointer value with `&`:</span></span>

```fsharp
open System

let f (dt: inref<DateTime>) =
    printfn "Now: %s" (dt.ToString())

let usage =
    let dt = DateTime.Now
    f &dt // Pass a pointer to 'dt'
```

<span data-ttu-id="e1c50-119">Para escribir en el `outref<'T>` puntero `byref<'T>`mediante un o , también debe `mutable`hacer que el valor que se captura un puntero a .</span><span class="sxs-lookup"><span data-stu-id="e1c50-119">To write to the pointer by using an `outref<'T>` or `byref<'T>`, you must also make the value you grab a pointer to `mutable`.</span></span>

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

<span data-ttu-id="e1c50-120">Si solo está escribiendo el puntero en `outref<'T>` lugar `byref<'T>`de leerlo, considere la posibilidad de usar archivos en lugar de .</span><span class="sxs-lookup"><span data-stu-id="e1c50-120">If you are only writing the pointer instead of reading it, consider using `outref<'T>` instead of `byref<'T>`.</span></span>

### <a name="inref-semantics"></a><span data-ttu-id="e1c50-121">Semántica inref</span><span class="sxs-lookup"><span data-stu-id="e1c50-121">Inref semantics</span></span>

<span data-ttu-id="e1c50-122">Observe el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="e1c50-122">Consider the following code:</span></span>

```fsharp
let f (x: inref<SomeStruct>) = x.SomeField
```

<span data-ttu-id="e1c50-123">Semánticamente, esto significa lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e1c50-123">Semantically, this means the following:</span></span>

* <span data-ttu-id="e1c50-124">El titular `x` del puntero solo puede usarlo para leer el valor.</span><span class="sxs-lookup"><span data-stu-id="e1c50-124">The holder of the `x` pointer may only use it to read the value.</span></span>
* <span data-ttu-id="e1c50-125">Cualquier puntero `struct` adquirido a `SomeStruct` los `inref<_>`campos anidados dentro se les da el tipo .</span><span class="sxs-lookup"><span data-stu-id="e1c50-125">Any pointer acquired to `struct` fields nested within `SomeStruct` are given type `inref<_>`.</span></span>

<span data-ttu-id="e1c50-126">También se cumple lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e1c50-126">The following is also true:</span></span>

* <span data-ttu-id="e1c50-127">No hay ninguna implicación de que otros subprocesos o alias no tengan acceso de escritura a `x`.</span><span class="sxs-lookup"><span data-stu-id="e1c50-127">There is no implication that other threads or aliases do not have write access to `x`.</span></span>
* <span data-ttu-id="e1c50-128">No hay implicación que `SomeStruct` sea inmutable en virtud de `x` ser un `inref`archivo .</span><span class="sxs-lookup"><span data-stu-id="e1c50-128">There is no implication that `SomeStruct` is immutable by virtue of `x` being an `inref`.</span></span>

<span data-ttu-id="e1c50-129">Sin embargo, para los tipos de `this` valor de F que `inref` **son** inmutables, se deduce que el puntero es un archivo .</span><span class="sxs-lookup"><span data-stu-id="e1c50-129">However, for F# value types that **are** immutable, the `this` pointer is inferred to be an `inref`.</span></span>

<span data-ttu-id="e1c50-130">Todas estas reglas juntas significan que `inref` el titular de un puntero no puede modificar el contenido inmediato de la memoria que se apunta.</span><span class="sxs-lookup"><span data-stu-id="e1c50-130">All of these rules together mean that the holder of an `inref` pointer may not modify the immediate contents of the memory being pointed to.</span></span>

### <a name="outref-semantics"></a><span data-ttu-id="e1c50-131">Semántica de Outref</span><span class="sxs-lookup"><span data-stu-id="e1c50-131">Outref semantics</span></span>

<span data-ttu-id="e1c50-132">El propósito `outref<'T>` de es indicar que el puntero sólo debe escribirse en.</span><span class="sxs-lookup"><span data-stu-id="e1c50-132">The purpose of `outref<'T>` is to indicate that the pointer should only be written to.</span></span> <span data-ttu-id="e1c50-133">Inesperadamente, `outref<'T>` permite leer el valor subyacente a pesar de su nombre.</span><span class="sxs-lookup"><span data-stu-id="e1c50-133">Unexpectedly, `outref<'T>` permits reading the underlying value despite its name.</span></span> <span data-ttu-id="e1c50-134">Esto es para fines de compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="e1c50-134">This is for compatibility purposes.</span></span> <span data-ttu-id="e1c50-135">Semánticamente, `outref<'T>` no es `byref<'T>`diferente de .</span><span class="sxs-lookup"><span data-stu-id="e1c50-135">Semantically, `outref<'T>` is no different than `byref<'T>`.</span></span>

### <a name="interop-with-c"></a><span data-ttu-id="e1c50-136">Interoperabilidad con C\#</span><span class="sxs-lookup"><span data-stu-id="e1c50-136">Interop with C\#</span></span>

<span data-ttu-id="e1c50-137">Además `in ref` de `out ref` las devoluciones, `ref` c. admite las palabras clave y, además de las devoluciones.</span><span class="sxs-lookup"><span data-stu-id="e1c50-137">C# supports the `in ref` and `out ref` keywords, in addition to `ref` returns.</span></span> <span data-ttu-id="e1c50-138">En la tabla siguiente se muestra cómo f- interpreta lo que emite:</span><span class="sxs-lookup"><span data-stu-id="e1c50-138">The following table shows how F# interprets what C# emits:</span></span>

|<span data-ttu-id="e1c50-139">Construcción de C-</span><span class="sxs-lookup"><span data-stu-id="e1c50-139">C# construct</span></span>|<span data-ttu-id="e1c50-140">Inferidos de F</span><span class="sxs-lookup"><span data-stu-id="e1c50-140">F# infers</span></span>|
|------------|---------|
|<span data-ttu-id="e1c50-141">`ref`valor de retorno</span><span class="sxs-lookup"><span data-stu-id="e1c50-141">`ref` return value</span></span>|`outref<'T>`|
|<span data-ttu-id="e1c50-142">`ref readonly`valor de retorno</span><span class="sxs-lookup"><span data-stu-id="e1c50-142">`ref readonly` return value</span></span>|`inref<'T>`|
|<span data-ttu-id="e1c50-143">Parámetro `in ref`</span><span class="sxs-lookup"><span data-stu-id="e1c50-143">`in ref` parameter</span></span>|`inref<'T>`|
|<span data-ttu-id="e1c50-144">Parámetro `out ref`</span><span class="sxs-lookup"><span data-stu-id="e1c50-144">`out ref` parameter</span></span>|`outref<'T>`|

<span data-ttu-id="e1c50-145">En la tabla siguiente se muestra lo que emite F:</span><span class="sxs-lookup"><span data-stu-id="e1c50-145">The following table shows what F# emits:</span></span>

|<span data-ttu-id="e1c50-146">Construcción de F -</span><span class="sxs-lookup"><span data-stu-id="e1c50-146">F# construct</span></span>|<span data-ttu-id="e1c50-147">Construcción emitida</span><span class="sxs-lookup"><span data-stu-id="e1c50-147">Emitted construct</span></span>|
|------------|-----------------|
|<span data-ttu-id="e1c50-148">Argumento `inref<'T>`</span><span class="sxs-lookup"><span data-stu-id="e1c50-148">`inref<'T>` argument</span></span>|<span data-ttu-id="e1c50-149">`[In]`atributo en el argumento</span><span class="sxs-lookup"><span data-stu-id="e1c50-149">`[In]` attribute on argument</span></span>|
|<span data-ttu-id="e1c50-150">`inref<'T>`devolución</span><span class="sxs-lookup"><span data-stu-id="e1c50-150">`inref<'T>` return</span></span>|<span data-ttu-id="e1c50-151">`modreq`atributo sobre el valor</span><span class="sxs-lookup"><span data-stu-id="e1c50-151">`modreq` attribute on value</span></span>|
|<span data-ttu-id="e1c50-152">`inref<'T>`en ranura abstracta o implementación</span><span class="sxs-lookup"><span data-stu-id="e1c50-152">`inref<'T>` in abstract slot or implementation</span></span>|<span data-ttu-id="e1c50-153">`modreq`sobre discusión o devolución</span><span class="sxs-lookup"><span data-stu-id="e1c50-153">`modreq` on argument or return</span></span>|
|<span data-ttu-id="e1c50-154">Argumento `outref<'T>`</span><span class="sxs-lookup"><span data-stu-id="e1c50-154">`outref<'T>` argument</span></span>|<span data-ttu-id="e1c50-155">`[Out]`atributo en el argumento</span><span class="sxs-lookup"><span data-stu-id="e1c50-155">`[Out]` attribute on argument</span></span>|

### <a name="type-inference-and-overloading-rules"></a><span data-ttu-id="e1c50-156">Reglas de inferencia y sobrecarga de tipos</span><span class="sxs-lookup"><span data-stu-id="e1c50-156">Type inference and overloading rules</span></span>

<span data-ttu-id="e1c50-157">En `inref<'T>` los siguientes casos, el compilador de F - deduce un tipo:</span><span class="sxs-lookup"><span data-stu-id="e1c50-157">An `inref<'T>` type is inferred by the F# compiler in the following cases:</span></span>

1. <span data-ttu-id="e1c50-158">Un parámetro o tipo de `IsReadOnly` valor devuelto de .NET que tiene un atributo.</span><span class="sxs-lookup"><span data-stu-id="e1c50-158">A .NET parameter or return type that has an `IsReadOnly` attribute.</span></span>
2. <span data-ttu-id="e1c50-159">El `this` puntero en un tipo struct que no tiene campos mutables.</span><span class="sxs-lookup"><span data-stu-id="e1c50-159">The `this` pointer on a struct type that has no mutable fields.</span></span>
3. <span data-ttu-id="e1c50-160">La dirección de una ubicación `inref<_>` de memoria derivada de otro puntero.</span><span class="sxs-lookup"><span data-stu-id="e1c50-160">The address of a memory location derived from another `inref<_>` pointer.</span></span>

<span data-ttu-id="e1c50-161">Cuando se toma `inref` una dirección implícita de un, `SomeType` se prefiere una sobrecarga con `inref<SomeType>`un argumento de tipo a una sobrecarga con un argumento de tipo .</span><span class="sxs-lookup"><span data-stu-id="e1c50-161">When an implicit address of an `inref` is being taken, an overload with an argument of type `SomeType` is preferred to an overload with an argument of type `inref<SomeType>`.</span></span> <span data-ttu-id="e1c50-162">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e1c50-162">For example:</span></span>

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

<span data-ttu-id="e1c50-163">En ambos casos, las `System.DateTime` sobrecargas que toman `inref<System.DateTime>`se resuelven en lugar de las sobrecargas que toman .</span><span class="sxs-lookup"><span data-stu-id="e1c50-163">In both cases, the overloads taking `System.DateTime` are resolved rather than the overloads taking `inref<System.DateTime>`.</span></span>

## <a name="byref-like-structs"></a><span data-ttu-id="e1c50-164">Estructuras similares a referencias externas</span><span class="sxs-lookup"><span data-stu-id="e1c50-164">Byref-like structs</span></span>

<span data-ttu-id="e1c50-165">Además `byref` / `inref` / `outref` del trío, puede definir sus propias estructuras que se adhieran a `byref`la semántica -como.</span><span class="sxs-lookup"><span data-stu-id="e1c50-165">In addition to the `byref`/`inref`/`outref` trio, you can define your own structs that can adhere to `byref`-like semantics.</span></span> <span data-ttu-id="e1c50-166">Esto se hace <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> con el atributo:</span><span class="sxs-lookup"><span data-stu-id="e1c50-166">This is done with the <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> attribute:</span></span>

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

<span data-ttu-id="e1c50-167">`IsByRefLike`no implica `Struct`.</span><span class="sxs-lookup"><span data-stu-id="e1c50-167">`IsByRefLike` does not imply `Struct`.</span></span> <span data-ttu-id="e1c50-168">Ambos deben estar presentes en el tipo.</span><span class="sxs-lookup"><span data-stu-id="e1c50-168">Both must be present on the type.</span></span>

<span data-ttu-id="e1c50-169">Una`byref`estructura " -like" en F es un tipo de valor enlazado a la pila.</span><span class="sxs-lookup"><span data-stu-id="e1c50-169">A "`byref`-like" struct in F# is a stack-bound value type.</span></span> <span data-ttu-id="e1c50-170">Nunca se asigna en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="e1c50-170">It is never allocated on the managed heap.</span></span> <span data-ttu-id="e1c50-171">Una `byref`estructura -like es útil para la programación de alto rendimiento, ya que se aplica con un conjunto de comprobaciones sólidas sobre la duración y la no captura.</span><span class="sxs-lookup"><span data-stu-id="e1c50-171">A `byref`-like struct is useful for high-performance programming, as it is enforced with set of strong checks about lifetime and non-capture.</span></span> <span data-ttu-id="e1c50-172">Las reglas son:</span><span class="sxs-lookup"><span data-stu-id="e1c50-172">The rules are:</span></span>

* <span data-ttu-id="e1c50-173">Se pueden utilizar como parámetros de función, parámetros de método, variables locales, retornos de método.</span><span class="sxs-lookup"><span data-stu-id="e1c50-173">They can be used as function parameters, method parameters, local variables, method returns.</span></span>
* <span data-ttu-id="e1c50-174">No pueden ser miembros estáticos o de instancia de una clase o estructura normal.</span><span class="sxs-lookup"><span data-stu-id="e1c50-174">They cannot be static or instance members of a class or normal struct.</span></span>
* <span data-ttu-id="e1c50-175">No se pueden capturar mediante`async` ninguna construcción de cierre (métodos o expresiones lambda).</span><span class="sxs-lookup"><span data-stu-id="e1c50-175">They cannot be captured by any closure construct (`async` methods or lambda expressions).</span></span>
* <span data-ttu-id="e1c50-176">No se pueden utilizar como parámetro genérico.</span><span class="sxs-lookup"><span data-stu-id="e1c50-176">They cannot be used as a generic parameter.</span></span>

<span data-ttu-id="e1c50-177">Este último punto es crucial para la `|>` programación de estilo de canalización de F, al igual que una función genérica que parametriza sus tipos de entrada.</span><span class="sxs-lookup"><span data-stu-id="e1c50-177">This last point is crucial for F# pipeline-style programming, as `|>` is a generic function that parameterizes its input types.</span></span> <span data-ttu-id="e1c50-178">Esta restricción puede `|>` ser relajada para el futuro, ya que está en línea y no hace ninguna llamada a funciones genéricas no insertadas en su cuerpo.</span><span class="sxs-lookup"><span data-stu-id="e1c50-178">This restriction may be relaxed for `|>` in the future, as it is inline and does not make any calls to non-inlined generic functions in its body.</span></span>

<span data-ttu-id="e1c50-179">Aunque estas reglas restringen fuertemente el uso, lo hacen para cumplir la promesa de la informática de alto rendimiento de una manera segura.</span><span class="sxs-lookup"><span data-stu-id="e1c50-179">Although these rules strongly restrict usage, they do so to fulfill the promise of high-performance computing in a safe manner.</span></span>

## <a name="byref-returns"></a><span data-ttu-id="e1c50-180">Devoluciones byref</span><span class="sxs-lookup"><span data-stu-id="e1c50-180">Byref returns</span></span>

<span data-ttu-id="e1c50-181">Las devoluciones Byref de las funciones o miembros de F. se pueden producir y consumir.</span><span class="sxs-lookup"><span data-stu-id="e1c50-181">Byref returns from F# functions or members can be produced and consumed.</span></span> <span data-ttu-id="e1c50-182">Al consumir `byref`un método -returning, el valor se desreferencia implícitamente.</span><span class="sxs-lookup"><span data-stu-id="e1c50-182">When consuming a `byref`-returning method, the value is implicitly dereferenced.</span></span> <span data-ttu-id="e1c50-183">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e1c50-183">For example:</span></span>

```fsharp
let squareAndPrint (data : byref<int>) =
    let squared = data*data    // data is implicitly dereferenced
    printfn "%d" squared
```

<span data-ttu-id="e1c50-184">Para devolver un valor byref, la variable que contiene el valor debe vivir más tiempo que el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="e1c50-184">To return a value byref, the variable that contains the value must live longer than the current scope.</span></span>
<span data-ttu-id="e1c50-185">Además, para devolver `&value` byref, use (donde value es una variable que dura más que el ámbito actual).</span><span class="sxs-lookup"><span data-stu-id="e1c50-185">Also, to return byref, use `&value` (where value is a variable that lives longer than the current scope).</span></span>

```fsharp
let mutable sum = 0
let safeSum (bytes: Span<byte>) =
    for i in 0 .. bytes.Length - 1 do
        sum <- sum + int bytes.[i]
    &sum  // sum lives longer than the scope of this function.
```

<span data-ttu-id="e1c50-186">Para evitar la desreferencia implícita, como pasar una `&x` referencia `x` a través de varias llamadas encadenadas, use (donde está el valor).</span><span class="sxs-lookup"><span data-stu-id="e1c50-186">To avoid the implicit dereference, such as passing a reference through multiple chained calls, use `&x` (where `x` is the value).</span></span>

<span data-ttu-id="e1c50-187">También puede asignar directamente `byref`a una devolución.</span><span class="sxs-lookup"><span data-stu-id="e1c50-187">You can also directly assign to a return `byref`.</span></span> <span data-ttu-id="e1c50-188">Considere el siguiente programa (altamente imperativo):</span><span class="sxs-lookup"><span data-stu-id="e1c50-188">Consider the following (highly imperative) program:</span></span>

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
    printfn "Original sequence: %s" (c.ToString())

    let v = &c.FindLargestSmallerThan 16

    v <- v*2 // Directly assign to the byref return

    printfn "New sequence:      %s" (c.ToString())

    0 // return an integer exit code
```

<span data-ttu-id="e1c50-189">Éste es el resultado:</span><span class="sxs-lookup"><span data-stu-id="e1c50-189">This is the output:</span></span>

```console
Original sequence: 1 3 7 15 31 63 127 255 511 1023
New sequence:      1 3 7 30 31 63 127 255 511 1023
```

## <a name="scoping-for-byrefs"></a><span data-ttu-id="e1c50-190">Scoping para byrefs</span><span class="sxs-lookup"><span data-stu-id="e1c50-190">Scoping for byrefs</span></span>

<span data-ttu-id="e1c50-191">Un `let`valor enlazado no puede hacer que su referencia supere el ámbito en el que se definió.</span><span class="sxs-lookup"><span data-stu-id="e1c50-191">A `let`-bound value cannot have its reference exceed the scope in which it was defined.</span></span> <span data-ttu-id="e1c50-192">Por ejemplo, no se permite lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e1c50-192">For example, the following is disallowed:</span></span>

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

<span data-ttu-id="e1c50-193">Esto le impide obtener resultados diferentes dependiendo de si compila con optimizaciones o no.</span><span class="sxs-lookup"><span data-stu-id="e1c50-193">This prevents you from getting different results depending on if you compile with optimizations or not.</span></span>
