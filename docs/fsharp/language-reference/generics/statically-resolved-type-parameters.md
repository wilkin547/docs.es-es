---
title: Parámetros de tipo resueltos estáticamente (F#)
description: Obtenga información sobre cómo usar F# parámetro de tipo resueltos estáticamente, que se reemplaza con un tipo real en tiempo de compilación en lugar de en tiempo de ejecución.
ms.date: 05/16/2016
ms.openlocfilehash: 747917fef2746dcbf363ef4b717ace5e47229800
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2018
ms.locfileid: "48032782"
---
# <a name="statically-resolved-type-parameters"></a><span data-ttu-id="89c04-103">Parámetros de tipo resueltos estáticamente</span><span class="sxs-lookup"><span data-stu-id="89c04-103">Statically Resolved Type Parameters</span></span>

<span data-ttu-id="89c04-104">Un *parámetro de tipo resueltos estáticamente* es un parámetro de tipo que se reemplaza con un tipo real en tiempo de compilación en lugar de en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="89c04-104">A *statically resolved type parameter* is a type parameter that is replaced with an actual type at compile time instead of at run time.</span></span> <span data-ttu-id="89c04-105">Va precedido por el símbolo de intercalación (^).</span><span class="sxs-lookup"><span data-stu-id="89c04-105">They are preceded by a caret (^) symbol.</span></span>

## <a name="syntax"></a><span data-ttu-id="89c04-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="89c04-106">Syntax</span></span>

```
ˆtype-parameter
```

## <a name="remarks"></a><span data-ttu-id="89c04-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="89c04-107">Remarks</span></span>

<span data-ttu-id="89c04-108">En el lenguaje F#, hay dos clases de parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="89c04-108">In the F# language, there are two distinct kinds of type parameters.</span></span> <span data-ttu-id="89c04-109">En primer lugar está el parámetro de tipo genérico estándar.</span><span class="sxs-lookup"><span data-stu-id="89c04-109">The first kind is the standard generic type parameter.</span></span> <span data-ttu-id="89c04-110">Estos parámetros se indican mediante un apóstrofo ('), como en `'T` y `'U`.</span><span class="sxs-lookup"><span data-stu-id="89c04-110">These are indicated by an apostrophe ('), as in `'T` and `'U`.</span></span> <span data-ttu-id="89c04-111">Equivalen a los parámetros de tipo genérico de otros lenguajes .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="89c04-111">They are equivalent to generic type parameters in other .NET Framework languages.</span></span> <span data-ttu-id="89c04-112">El otro tipo de parámetro se resuelve estáticamente y se indica mediante el símbolo de intercalación, como en `^T` y `^U`.</span><span class="sxs-lookup"><span data-stu-id="89c04-112">The other kind is statically resolved and is indicated by a caret symbol, as in `^T` and `^U`.</span></span>

<span data-ttu-id="89c04-113">Los parámetros de tipo resueltos estáticamente son sobre todo útiles cuando se usan con restricciones de miembro, que son restricciones que permiten especificar que un argumento de tipo debe tener uno o varios miembros determinados.</span><span class="sxs-lookup"><span data-stu-id="89c04-113">Statically resolved type parameters are primarily useful in conjunction with member constraints, which are constraints that allow you to specify that a type argument must have a particular member or members in order to be used.</span></span> <span data-ttu-id="89c04-114">Este tipo de restricción no se puede crear mediante un parámetro de tipo genérico normal.</span><span class="sxs-lookup"><span data-stu-id="89c04-114">There is no way to create this kind of constraint by using a regular generic type parameter.</span></span>

<span data-ttu-id="89c04-115">En la siguiente tabla, se resumen las similitudes y las diferencias entre las dos clases de parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="89c04-115">The following table summarizes the similarities and differences between the two kinds of type parameters.</span></span>

|<span data-ttu-id="89c04-116">Característica</span><span class="sxs-lookup"><span data-stu-id="89c04-116">Feature</span></span>|<span data-ttu-id="89c04-117">Genérico</span><span class="sxs-lookup"><span data-stu-id="89c04-117">Generic</span></span>|<span data-ttu-id="89c04-118">Se resuelve estáticamente</span><span class="sxs-lookup"><span data-stu-id="89c04-118">Statically resolved</span></span>|
|-------|-------|-------------------|
|<span data-ttu-id="89c04-119">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="89c04-119">Syntax</span></span>|<span data-ttu-id="89c04-120">`'T`, `'U`</span><span class="sxs-lookup"><span data-stu-id="89c04-120">`'T`, `'U`</span></span>|<span data-ttu-id="89c04-121">`^T`, `^U`</span><span class="sxs-lookup"><span data-stu-id="89c04-121">`^T`, `^U`</span></span>|
|<span data-ttu-id="89c04-122">Tiempo de resolución</span><span class="sxs-lookup"><span data-stu-id="89c04-122">Resolution time</span></span>|<span data-ttu-id="89c04-123">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="89c04-123">Run time</span></span>|<span data-ttu-id="89c04-124">Tiempo de compilación</span><span class="sxs-lookup"><span data-stu-id="89c04-124">Compile time</span></span>|
|<span data-ttu-id="89c04-125">Restricciones de miembro</span><span class="sxs-lookup"><span data-stu-id="89c04-125">Member constraints</span></span>|<span data-ttu-id="89c04-126">No se puede utilizar con restricciones de miembro.</span><span class="sxs-lookup"><span data-stu-id="89c04-126">Cannot be used with member constraints.</span></span>|<span data-ttu-id="89c04-127">Se puede utilizar con restricciones de miembro.</span><span class="sxs-lookup"><span data-stu-id="89c04-127">Can be used with member constraints.</span></span>|
|<span data-ttu-id="89c04-128">Generación de código</span><span class="sxs-lookup"><span data-stu-id="89c04-128">Code generation</span></span>|<span data-ttu-id="89c04-129">Un tipo o método con parámetros de tipo genérico estándar da lugar a la generación de un solo tipo o método genérico.</span><span class="sxs-lookup"><span data-stu-id="89c04-129">A type (or method) with standard generic type parameters results in the generation of a single generic type or method.</span></span>|<span data-ttu-id="89c04-130">Se generan varias instancias de los tipos y métodos, una por cada tipo que se necesita.</span><span class="sxs-lookup"><span data-stu-id="89c04-130">Multiple instantiations of types and methods are generated, one for each type that is needed.</span></span>|
|<span data-ttu-id="89c04-131">Uso con tipos</span><span class="sxs-lookup"><span data-stu-id="89c04-131">Use with types</span></span>|<span data-ttu-id="89c04-132">Se puede utilizar con tipos.</span><span class="sxs-lookup"><span data-stu-id="89c04-132">Can be used on types.</span></span>|<span data-ttu-id="89c04-133">No se puede utilizar con tipos.</span><span class="sxs-lookup"><span data-stu-id="89c04-133">Cannot be used on types.</span></span>|
|<span data-ttu-id="89c04-134">Uso con funciones inline</span><span class="sxs-lookup"><span data-stu-id="89c04-134">Use with inline functions</span></span>|<span data-ttu-id="89c04-135">No.</span><span class="sxs-lookup"><span data-stu-id="89c04-135">No.</span></span> <span data-ttu-id="89c04-136">Una función inline no puede tener un parámetro de tipo genérico estándar.</span><span class="sxs-lookup"><span data-stu-id="89c04-136">An inline function cannot be parameterized with a standard generic type parameter.</span></span>|<span data-ttu-id="89c04-137">Sí.</span><span class="sxs-lookup"><span data-stu-id="89c04-137">Yes.</span></span> <span data-ttu-id="89c04-138">Los parámetros de tipo resueltos estáticamente no se pueden utilizar con funciones o métodos que no sean inline.</span><span class="sxs-lookup"><span data-stu-id="89c04-138">Statically resolved type parameters cannot be used on functions or methods that are not inline.</span></span>|

<span data-ttu-id="89c04-139">Muchas funciones de la biblioteca básica de F#, sobre todo los operadores, tienen parámetros de tipo que se resuelven estáticamente.</span><span class="sxs-lookup"><span data-stu-id="89c04-139">Many F# core library functions, especially operators, have statically resolved type parameters.</span></span> <span data-ttu-id="89c04-140">Se trata de funciones y operadores inline, que dan lugar a una generación de código eficaz para los cálculos numéricos.</span><span class="sxs-lookup"><span data-stu-id="89c04-140">These functions and operators are inline, and result in efficient code generation for numeric computations.</span></span>

<span data-ttu-id="89c04-141">Los métodos y funciones inline que usan operadores u otras funciones que utilicen parámetros de tipo resueltos estáticamente, también pueden emplear ellos mismos este tipo de parámetro.</span><span class="sxs-lookup"><span data-stu-id="89c04-141">Inline methods and functions that use operators, or use other functions that have statically resolved type parameters, can also use statically resolved type parameters themselves.</span></span> <span data-ttu-id="89c04-142">En muchas ocasiones, durante la inferencia de tipos, se deduce que esas funciones inline tienen parámetros de tipo que se resuelven estáticamente.</span><span class="sxs-lookup"><span data-stu-id="89c04-142">Often, type inference infers such inline functions to have statically resolved type parameters.</span></span> <span data-ttu-id="89c04-143">En el siguiente ejemplo, se muestra una definición de operador para la cual se deduce que tiene un parámetro de tipo que se resuelve estáticamente.</span><span class="sxs-lookup"><span data-stu-id="89c04-143">The following example illustrates an operator definition that is inferred to have a statically resolved type parameter.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet401.fs)]

<span data-ttu-id="89c04-144">El tipo resuelto de `(+@)` se basa en el uso de `(+)` y `(*)`, que hacen que mediante la inferencia de tipos se deduzcan las restricciones de miembro en los parámetros de tipo estáticamente resueltos.</span><span class="sxs-lookup"><span data-stu-id="89c04-144">The resolved type of `(+@)` is based on the use of both `(+)` and `(*)`, both of which cause type inference to infer member constraints on the statically resolved type parameters.</span></span> <span data-ttu-id="89c04-145">Tal y como se muestra en el intérprete de F#, el tipo resuelto es el siguiente.</span><span class="sxs-lookup"><span data-stu-id="89c04-145">The resolved type, as shown in the F# interpreter, is as follows.</span></span>

```fsharp
^a -> ^c -> ^d
when (^a or ^b) : (static member ( + ) : ^a * ^b -> ^d) and
(^a or ^c) : (static member ( * ) : ^a * ^c -> ^b)
```

<span data-ttu-id="89c04-146">La salida es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="89c04-146">The output is as follows.</span></span>

```
2
1.500000
```

<span data-ttu-id="89c04-147">A partir de F# 4.1, también puede especificar los nombres de tipo concreto en las firmas de parámetro de tipo resueltos estáticamente.</span><span class="sxs-lookup"><span data-stu-id="89c04-147">Starting with F# 4.1, you can also specify concrete type names in statically resolved type parameter signatures.</span></span>  <span data-ttu-id="89c04-148">En versiones anteriores del lenguaje, el nombre de tipo se pudo inferir realmente por el compilador, pero no se puede especificar realmente en la firma.</span><span class="sxs-lookup"><span data-stu-id="89c04-148">In previous versions of the language, the type name could actually be inferred by the compiler, but could not actually be specified in the signature.</span></span>  <span data-ttu-id="89c04-149">A partir de F# 4.1, también puede especificar los nombres de tipo concreto en las firmas de parámetro de tipo resueltos estáticamente.</span><span class="sxs-lookup"><span data-stu-id="89c04-149">As of F# 4.1, you may also specify concrete type names in statically resolved type parameter signatures.</span></span> <span data-ttu-id="89c04-150">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="89c04-150">Here's an example:</span></span>

```fsharp
let inline konst x _ = x

type CFunctor() = 
    static member inline fmap (f: ^a -> ^b, a: ^a list) = List.map f a
    static member inline fmap (f: ^a -> ^b, a: ^a option) =
        match a with
        | None -> None
        | Some x -> Some (f x)

    // default implementation of replace
    static member inline replace< ^a, ^b, ^c, ^d, ^e when ^a :> CFunctor and (^a or ^d): (static member fmap: (^b -> ^c) * ^d -> ^e) > (a, f) =
        ((^a or ^d) : (static member fmap : (^b -> ^c) * ^d -> ^e) (konst a, f))

    // call overridden replace if present
    static member inline replace< ^a, ^b, ^c when ^b: (static member replace: ^a * ^b -> ^c)>(a: ^a, f: ^b) =
        (^b : (static member replace: ^a * ^b -> ^c) (a, f))

let inline replace_instance< ^a, ^b, ^c, ^d when (^a or ^c): (static member replace: ^b * ^c -> ^d)> (a: ^b, f: ^c) =
        ((^a or ^c): (static member replace: ^b * ^c -> ^d) (a, f))

// Note the concrete type 'CFunctor' specified in the signature
let inline replace (a: ^a) (f: ^b): ^a0 when (CFunctor or  ^b): (static member replace: ^a *  ^b ->  ^a0) =
    replace_instance<CFunctor, _, _, _> (a, f)
```

## <a name="see-also"></a><span data-ttu-id="89c04-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="89c04-151">See also</span></span>

- [<span data-ttu-id="89c04-152">Genéricos</span><span class="sxs-lookup"><span data-stu-id="89c04-152">Generics</span></span>](index.md)
- [<span data-ttu-id="89c04-153">Inferencia de tipos</span><span class="sxs-lookup"><span data-stu-id="89c04-153">Type Inference</span></span>](../type-inference.md)
- [<span data-ttu-id="89c04-154">Generalización automática</span><span class="sxs-lookup"><span data-stu-id="89c04-154">Automatic Generalization</span></span>](automatic-generalization.md)
- [<span data-ttu-id="89c04-155">Restricciones</span><span class="sxs-lookup"><span data-stu-id="89c04-155">Constraints</span></span>](constraints.md)
- [<span data-ttu-id="89c04-156">Funciones insertadas</span><span class="sxs-lookup"><span data-stu-id="89c04-156">Inline Functions</span></span>](../functions/inline-functions.md)
