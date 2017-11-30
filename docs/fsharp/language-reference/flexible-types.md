---
title: Tipos flexibles (F#)
description: "Obtenga información acerca de cómo usar F # anotación de tipo flexible, lo que indica que un parámetro, una variable o un valor tiene un tipo que sea compatible con un tipo especificado."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: c8b510f2-3405-4cc9-b55b-e47b35e2b15b
ms.openlocfilehash: 7c5e4eb97791b9c6c56fe2847755866e8240e038
ms.sourcegitcommit: a19548e5167cbe7e9e58df4ffd8c3b23f17d5c7a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2017
---
# <a name="flexible-types"></a><span data-ttu-id="e7b7a-104">Tipos flexibles</span><span class="sxs-lookup"><span data-stu-id="e7b7a-104">Flexible Types</span></span>

<span data-ttu-id="e7b7a-105">A *anotación de tipo flexible* indica que un parámetro, una variable o un valor tiene un tipo que sea compatible con un tipo especificado, donde se determina la compatibilidad por posición en una jerarquía orientada a objetos de clases o interfaces.</span><span class="sxs-lookup"><span data-stu-id="e7b7a-105">A *flexible type annotation* indicates that a parameter, variable, or value has a type that is compatible with a specified type, where compatibility is determined by position in an object-oriented hierarchy of classes or interfaces.</span></span> <span data-ttu-id="e7b7a-106">Tipos flexibles resultan útiles específicamente cuando no se produce la conversión automática a los tipos más arriba en la jerarquía de tipos, pero desea habilitar la funcionalidad para trabajar con cualquier tipo de la jerarquía o cualquier tipo que implementa una interfaz.</span><span class="sxs-lookup"><span data-stu-id="e7b7a-106">Flexible types are useful specifically when the automatic conversion to types higher in the type hierarchy does not occur but you still want to enable your functionality to work with any type in the hierarchy or any type that implements an interface.</span></span>

## <a name="syntax"></a><span data-ttu-id="e7b7a-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e7b7a-107">Syntax</span></span>

```fsharp
#type
```

## <a name="remarks"></a><span data-ttu-id="e7b7a-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e7b7a-108">Remarks</span></span>

<span data-ttu-id="e7b7a-109">En la sintaxis anterior, *tipo* representa un tipo base o una interfaz.</span><span class="sxs-lookup"><span data-stu-id="e7b7a-109">In the previous syntax, *type* represents a base type or an interface.</span></span>

<span data-ttu-id="e7b7a-110">Un tipo flexible equivale a un tipo genérico que tiene una restricción que limita los tipos permitidos a los tipos que son compatibles con el tipo base o interfaz.</span><span class="sxs-lookup"><span data-stu-id="e7b7a-110">A flexible type is equivalent to a generic type that has a constraint that limits the allowed types to types that are compatible with the base or interface type.</span></span> <span data-ttu-id="e7b7a-111">Es decir, las dos líneas de código siguientes son equivalentes.</span><span class="sxs-lookup"><span data-stu-id="e7b7a-111">That is, the following two lines of code are equivalent.</span></span>

```fsharp
#SomeType

'T when 'T :> SomeType
```

<span data-ttu-id="e7b7a-112">Tipos flexibles son útiles en varios tipos de situaciones.</span><span class="sxs-lookup"><span data-stu-id="e7b7a-112">Flexible types are useful in several types of situations.</span></span> <span data-ttu-id="e7b7a-113">Por ejemplo, si tiene una función de orden superior (es decir, una función que toma una función como argumento), suele ser útil para que la función devuelva un tipo flexible.</span><span class="sxs-lookup"><span data-stu-id="e7b7a-113">For example, when you have a higher order function (a function that takes a function as an argument), it is often useful to have the function return a flexible type.</span></span> <span data-ttu-id="e7b7a-114">En el ejemplo siguiente, el uso de un tipo flexible con un argumento de secuencia en `iterate2` permite que la función de orden superior trabajar con funciones que generan secuencias, matrices, listas y cualquier otro tipo enumerable.</span><span class="sxs-lookup"><span data-stu-id="e7b7a-114">In the following example, the use of a flexible type with a sequence argument in `iterate2` enables the higher order function to work with functions that generate sequences, arrays, lists, and any other enumerable type.</span></span>

<span data-ttu-id="e7b7a-115">Tenga en cuenta las siguientes funciones de dos, uno de los que devuelve una secuencia, el otro de los cuales devuelve un tipo flexible.</span><span class="sxs-lookup"><span data-stu-id="e7b7a-115">Consider the following two functions, one of which returns a sequence, the other of which returns a flexible type.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4101.fs)]

<span data-ttu-id="e7b7a-116">Como otro ejemplo, considere la [Seq.concat](https://msdn.microsoft.com/library/2eeb69a9-fc2f-4b7d-8dee-101fa2b00712) función de biblioteca:</span><span class="sxs-lookup"><span data-stu-id="e7b7a-116">As another example, consider the [Seq.concat](https://msdn.microsoft.com/library/2eeb69a9-fc2f-4b7d-8dee-101fa2b00712) library function:</span></span>

```fsharp
val concat: sequences:seq<#seq<'T>> -> seq<'T>
```

<span data-ttu-id="e7b7a-117">Puede pasar cualquiera de las secuencias enumerables siguientes a esta función:</span><span class="sxs-lookup"><span data-stu-id="e7b7a-117">You can pass any of the following enumerable sequences to this function:</span></span>

- <span data-ttu-id="e7b7a-118">Una lista de listas</span><span class="sxs-lookup"><span data-stu-id="e7b7a-118">A list of lists</span></span>
- <span data-ttu-id="e7b7a-119">Una lista de matrices</span><span class="sxs-lookup"><span data-stu-id="e7b7a-119">A list of arrays</span></span>
- <span data-ttu-id="e7b7a-120">Una matriz de listas</span><span class="sxs-lookup"><span data-stu-id="e7b7a-120">An array of lists</span></span>
- <span data-ttu-id="e7b7a-121">Una matriz de secuencias</span><span class="sxs-lookup"><span data-stu-id="e7b7a-121">An array of sequences</span></span>
- <span data-ttu-id="e7b7a-122">Cualquier otra combinación de secuencias enumerables</span><span class="sxs-lookup"><span data-stu-id="e7b7a-122">Any other combination of enumerable sequences</span></span>

<span data-ttu-id="e7b7a-123">El siguiente código utiliza `Seq.concat` para mostrar los escenarios que se pueden admitir mediante el uso de tipos flexibles.</span><span class="sxs-lookup"><span data-stu-id="e7b7a-123">The following code uses `Seq.concat` to demonstrate the scenarios that you can support by using flexible types.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4102.fs)]

<span data-ttu-id="e7b7a-124">La salida es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="e7b7a-124">The output is as follows.</span></span>

```
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
```

<span data-ttu-id="e7b7a-125">En F #, como en otros lenguajes orientados a objetos, hay contextos en los que los tipos derivados o tipos que implementan interfaces se convierten automáticamente en un tipo base o interfaz.</span><span class="sxs-lookup"><span data-stu-id="e7b7a-125">In F#, as in other object-oriented languages, there are contexts in which derived types or types that implement interfaces are automatically converted to a base type or interface type.</span></span> <span data-ttu-id="e7b7a-126">Estas conversiones automáticas se producen en argumentos directos, pero no cuando el tipo está en una posición subordinada, como parte de un tipo más complejo, como un tipo de valor devuelto de un tipo de función, o como un argumento de tipo.</span><span class="sxs-lookup"><span data-stu-id="e7b7a-126">These automatic conversions occur in direct arguments, but not when the type is in a subordinate position, as part of a more complex type such as a return type of a function type, or as a type argument.</span></span> <span data-ttu-id="e7b7a-127">Por lo tanto, la notación de tipo flexible es especialmente útil cuando el tipo que aplica a es parte de un tipo más complejo.</span><span class="sxs-lookup"><span data-stu-id="e7b7a-127">Thus, the flexible type notation is primarily useful when the type you are applying it to is part of a more complex type.</span></span>

## <a name="see-also"></a><span data-ttu-id="e7b7a-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="e7b7a-128">See Also</span></span>

[<span data-ttu-id="e7b7a-129">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="e7b7a-129">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="e7b7a-130">Genéricos</span><span class="sxs-lookup"><span data-stu-id="e7b7a-130">Generics</span></span>](generics/index.md)
