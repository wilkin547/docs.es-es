---
title: "Parámetros de tipo resueltos estáticamente (F#)"
description: "Obtenga información acerca de cómo usar F # parámetros de tipo resueltos estáticamente, que se sustituyan por un tipo real en tiempo de compilación en lugar de en tiempo de ejecución."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: b3797415-3e49-4f8a-a8ee-fa614c5721aa
ms.openlocfilehash: 88b4590a4323e75949c1915503b51793283792de
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="statically-resolved-type-parameters"></a><span data-ttu-id="74cca-104">Parámetros de tipo resueltos estáticamente</span><span class="sxs-lookup"><span data-stu-id="74cca-104">Statically Resolved Type Parameters</span></span>

<span data-ttu-id="74cca-105">A *parámetro de tipo resueltos estáticamente* es un parámetro de tipo que se reemplaza con un tipo real en tiempo de compilación en lugar de en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="74cca-105">A *statically resolved type parameter* is a type parameter that is replaced with an actual type at compile time instead of at run time.</span></span> <span data-ttu-id="74cca-106">Va precedido por el símbolo de intercalación (^).</span><span class="sxs-lookup"><span data-stu-id="74cca-106">They are preceded by a caret (^) symbol.</span></span>


## <a name="syntax"></a><span data-ttu-id="74cca-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="74cca-107">Syntax</span></span>

```
ˆtype-parameter
```

## <a name="remarks"></a><span data-ttu-id="74cca-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="74cca-108">Remarks</span></span>
<span data-ttu-id="74cca-109">En el lenguaje F#, hay dos clases de parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="74cca-109">In the F# language, there are two distinct kinds of type parameters.</span></span> <span data-ttu-id="74cca-110">En primer lugar está el parámetro de tipo genérico estándar.</span><span class="sxs-lookup"><span data-stu-id="74cca-110">The first kind is the standard generic type parameter.</span></span> <span data-ttu-id="74cca-111">Estos parámetros se indican mediante un apóstrofo ('), como en `'T` y `'U`.</span><span class="sxs-lookup"><span data-stu-id="74cca-111">These are indicated by an apostrophe ('), as in `'T` and `'U`.</span></span> <span data-ttu-id="74cca-112">Equivalen a los parámetros de tipo genérico de otros lenguajes .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="74cca-112">They are equivalent to generic type parameters in other .NET Framework languages.</span></span> <span data-ttu-id="74cca-113">El otro tipo de parámetro se resuelve estáticamente y se indica mediante el símbolo de intercalación, como en `^T` y `^U`.</span><span class="sxs-lookup"><span data-stu-id="74cca-113">The other kind is statically resolved and is indicated by a caret symbol, as in `^T` and `^U`.</span></span>

<span data-ttu-id="74cca-114">Los parámetros de tipo resueltos estáticamente son sobre todo útiles cuando se usan con restricciones de miembro, que son restricciones que permiten especificar que un argumento de tipo debe tener uno o varios miembros determinados.</span><span class="sxs-lookup"><span data-stu-id="74cca-114">Statically resolved type parameters are primarily useful in conjunction with member constraints, which are constraints that allow you to specify that a type argument must have a particular member or members in order to be used.</span></span> <span data-ttu-id="74cca-115">Este tipo de restricción no se puede crear mediante un parámetro de tipo genérico normal.</span><span class="sxs-lookup"><span data-stu-id="74cca-115">There is no way to create this kind of constraint by using a regular generic type parameter.</span></span>

<span data-ttu-id="74cca-116">En la siguiente tabla, se resumen las similitudes y las diferencias entre las dos clases de parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="74cca-116">The following table summarizes the similarities and differences between the two kinds of type parameters.</span></span>

|<span data-ttu-id="74cca-117">Característica</span><span class="sxs-lookup"><span data-stu-id="74cca-117">Feature</span></span>|<span data-ttu-id="74cca-118">Genérico</span><span class="sxs-lookup"><span data-stu-id="74cca-118">Generic</span></span>|<span data-ttu-id="74cca-119">Se resuelve estáticamente</span><span class="sxs-lookup"><span data-stu-id="74cca-119">Statically resolved</span></span>|
|-------|-------|-------------------|
|<span data-ttu-id="74cca-120">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="74cca-120">Syntax</span></span>|<span data-ttu-id="74cca-121">`'T`, `'U`</span><span class="sxs-lookup"><span data-stu-id="74cca-121">`'T`, `'U`</span></span>|<span data-ttu-id="74cca-122">`^T`, `^U`</span><span class="sxs-lookup"><span data-stu-id="74cca-122">`^T`, `^U`</span></span>|
|<span data-ttu-id="74cca-123">Tiempo de resolución</span><span class="sxs-lookup"><span data-stu-id="74cca-123">Resolution time</span></span>|<span data-ttu-id="74cca-124">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="74cca-124">Run time</span></span>|<span data-ttu-id="74cca-125">Tiempo de compilación</span><span class="sxs-lookup"><span data-stu-id="74cca-125">Compile time</span></span>|
|<span data-ttu-id="74cca-126">Restricciones de miembro</span><span class="sxs-lookup"><span data-stu-id="74cca-126">Member constraints</span></span>|<span data-ttu-id="74cca-127">No se puede utilizar con restricciones de miembro.</span><span class="sxs-lookup"><span data-stu-id="74cca-127">Cannot be used with member constraints.</span></span>|<span data-ttu-id="74cca-128">Se puede utilizar con restricciones de miembro.</span><span class="sxs-lookup"><span data-stu-id="74cca-128">Can be used with member constraints.</span></span>|
|<span data-ttu-id="74cca-129">Generación de código</span><span class="sxs-lookup"><span data-stu-id="74cca-129">Code generation</span></span>|<span data-ttu-id="74cca-130">Un tipo o método con parámetros de tipo genérico estándar da lugar a la generación de un solo tipo o método genérico.</span><span class="sxs-lookup"><span data-stu-id="74cca-130">A type (or method) with standard generic type parameters results in the generation of a single generic type or method.</span></span>|<span data-ttu-id="74cca-131">Se generan varias instancias de los tipos y métodos, una por cada tipo que se necesita.</span><span class="sxs-lookup"><span data-stu-id="74cca-131">Multiple instantiations of types and methods are generated, one for each type that is needed.</span></span>|
|<span data-ttu-id="74cca-132">Uso con tipos</span><span class="sxs-lookup"><span data-stu-id="74cca-132">Use with types</span></span>|<span data-ttu-id="74cca-133">Se puede utilizar con tipos.</span><span class="sxs-lookup"><span data-stu-id="74cca-133">Can be used on types.</span></span>|<span data-ttu-id="74cca-134">No se puede utilizar con tipos.</span><span class="sxs-lookup"><span data-stu-id="74cca-134">Cannot be used on types.</span></span>|
|<span data-ttu-id="74cca-135">Uso con funciones inline</span><span class="sxs-lookup"><span data-stu-id="74cca-135">Use with inline functions</span></span>|<span data-ttu-id="74cca-136">No.</span><span class="sxs-lookup"><span data-stu-id="74cca-136">No.</span></span> <span data-ttu-id="74cca-137">Una función inline no puede tener un parámetro de tipo genérico estándar.</span><span class="sxs-lookup"><span data-stu-id="74cca-137">An inline function cannot be parameterized with a standard generic type parameter.</span></span>|<span data-ttu-id="74cca-138">Sí.</span><span class="sxs-lookup"><span data-stu-id="74cca-138">Yes.</span></span> <span data-ttu-id="74cca-139">Los parámetros de tipo resueltos estáticamente no se pueden utilizar con funciones o métodos que no sean inline.</span><span class="sxs-lookup"><span data-stu-id="74cca-139">Statically resolved type parameters cannot be used on functions or methods that are not inline.</span></span>|

<span data-ttu-id="74cca-140">Muchas funciones de la biblioteca básica de F#, sobre todo los operadores, tienen parámetros de tipo que se resuelven estáticamente.</span><span class="sxs-lookup"><span data-stu-id="74cca-140">Many F# core library functions, especially operators, have statically resolved type parameters.</span></span> <span data-ttu-id="74cca-141">Se trata de funciones y operadores inline, que dan lugar a una generación de código eficaz para los cálculos numéricos.</span><span class="sxs-lookup"><span data-stu-id="74cca-141">These functions and operators are inline, and result in efficient code generation for numeric computations.</span></span>

<span data-ttu-id="74cca-142">Los métodos y funciones inline que usan operadores u otras funciones que utilicen parámetros de tipo resueltos estáticamente, también pueden emplear ellos mismos este tipo de parámetro.</span><span class="sxs-lookup"><span data-stu-id="74cca-142">Inline methods and functions that use operators, or use other functions that have statically resolved type parameters, can also use statically resolved type parameters themselves.</span></span> <span data-ttu-id="74cca-143">En muchas ocasiones, durante la inferencia de tipos, se deduce que esas funciones inline tienen parámetros de tipo que se resuelven estáticamente.</span><span class="sxs-lookup"><span data-stu-id="74cca-143">Often, type inference infers such inline functions to have statically resolved type parameters.</span></span> <span data-ttu-id="74cca-144">En el siguiente ejemplo, se muestra una definición de operador para la cual se deduce que tiene un parámetro de tipo que se resuelve estáticamente.</span><span class="sxs-lookup"><span data-stu-id="74cca-144">The following example illustrates an operator definition that is inferred to have a statically resolved type parameter.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet401.fs)]

<span data-ttu-id="74cca-145">El tipo resuelto de `(+@)` se basa en el uso de `(+)` y `(*)`, que hacen que mediante la inferencia de tipos se deduzcan las restricciones de miembro en los parámetros de tipo estáticamente resueltos.</span><span class="sxs-lookup"><span data-stu-id="74cca-145">The resolved type of `(+@)` is based on the use of both `(+)` and `(*)`, both of which cause type inference to infer member constraints on the statically resolved type parameters.</span></span> <span data-ttu-id="74cca-146">Tal y como se muestra en el intérprete de F#, el tipo resuelto es el siguiente.</span><span class="sxs-lookup"><span data-stu-id="74cca-146">The resolved type, as shown in the F# interpreter, is as follows.</span></span>

```fsharp
^a -> ^c -> ^d
when (^a or ^b) : (static member (+) : ^a * ^b -> ^d) and
(^a or ^c) : (static member (+) : ^a * ^c -> ^b)
```

<span data-ttu-id="74cca-147">La salida es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="74cca-147">The output is as follows.</span></span>

```
2
1.500000
```

<span data-ttu-id="74cca-148">A partir de F # 4.1, también puede especificar nombres de tipo concreto en firmas de parámetro de tipo resueltos estáticamente.</span><span class="sxs-lookup"><span data-stu-id="74cca-148">Starting with F# 4.1, you can also specify concrete type names in statically resolved type parameter signatures.</span></span>  <span data-ttu-id="74cca-149">En versiones anteriores del lenguaje, el nombre de tipo realmente se pudo inferir el compilador, pero no se podía realmente especificar en la firma.</span><span class="sxs-lookup"><span data-stu-id="74cca-149">In previous versions of the language, the type name could actually be inferred by the compiler, but could not actually be specified in the signature.</span></span>  <span data-ttu-id="74cca-150">A partir de F # 4.1, también puede especificar nombres de tipo concreto en firmas de parámetro de tipo resueltos estáticamente.</span><span class="sxs-lookup"><span data-stu-id="74cca-150">As of F# 4.1, you may also specify concrete type names in statically resolved type parameter signatures.</span></span> <span data-ttu-id="74cca-151">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="74cca-151">Here's an example:</span></span>

```fsharp
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

## <a name="see-also"></a><span data-ttu-id="74cca-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="74cca-152">See Also</span></span>
[<span data-ttu-id="74cca-153">Genéricos</span><span class="sxs-lookup"><span data-stu-id="74cca-153">Generics</span></span>](index.md)

[<span data-ttu-id="74cca-154">Inferencia de tipos</span><span class="sxs-lookup"><span data-stu-id="74cca-154">Type Inference</span></span>](../type-inference.md)

[<span data-ttu-id="74cca-155">Generalización automática</span><span class="sxs-lookup"><span data-stu-id="74cca-155">Automatic Generalization</span></span>](automatic-generalization.md)

[<span data-ttu-id="74cca-156">Restricciones</span><span class="sxs-lookup"><span data-stu-id="74cca-156">Constraints</span></span>](constraints.md)

[<span data-ttu-id="74cca-157">Funciones insertadas</span><span class="sxs-lookup"><span data-stu-id="74cca-157">Inline Functions</span></span>](../functions/inline-functions.md)
