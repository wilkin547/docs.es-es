---
title: Tipos flexibles (F#)
description: 'Obtenga información sobre cómo usar F # anotación de tipo flexible, que indica que un parámetro, una variable o un valor tiene un tipo que es compatible con un tipo especificado.'
ms.date: 05/16/2016
ms.openlocfilehash: b6c97c3cc19f15b2c8db74b2c55660a16b2858f7
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2018
ms.locfileid: "47210050"
---
# <a name="flexible-types"></a><span data-ttu-id="8be8b-103">Tipos flexibles</span><span class="sxs-lookup"><span data-stu-id="8be8b-103">Flexible Types</span></span>

<span data-ttu-id="8be8b-104">Un *anotación de tipo flexible* indica que un parámetro, una variable o un valor tiene un tipo que es compatible con un tipo especificado, donde compatibilidad viene determinada por la posición en una jerarquía orientada a objetos de clases o interfaces.</span><span class="sxs-lookup"><span data-stu-id="8be8b-104">A *flexible type annotation* indicates that a parameter, variable, or value has a type that is compatible with a specified type, where compatibility is determined by position in an object-oriented hierarchy of classes or interfaces.</span></span> <span data-ttu-id="8be8b-105">Tipos flexibles son útiles en concreto cuando no se produce la conversión automática a tipos más arriba en la jerarquía de tipos, pero desea habilitar la funcionalidad para trabajar con cualquier tipo de la jerarquía o cualquier tipo que implementa una interfaz.</span><span class="sxs-lookup"><span data-stu-id="8be8b-105">Flexible types are useful specifically when the automatic conversion to types higher in the type hierarchy does not occur but you still want to enable your functionality to work with any type in the hierarchy or any type that implements an interface.</span></span>

## <a name="syntax"></a><span data-ttu-id="8be8b-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8be8b-106">Syntax</span></span>

```fsharp
#type
```

## <a name="remarks"></a><span data-ttu-id="8be8b-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8be8b-107">Remarks</span></span>

<span data-ttu-id="8be8b-108">En la sintaxis anterior, *tipo* representa un tipo base o una interfaz.</span><span class="sxs-lookup"><span data-stu-id="8be8b-108">In the previous syntax, *type* represents a base type or an interface.</span></span>

<span data-ttu-id="8be8b-109">Un tipo flexible es equivalente a un tipo genérico que tiene una restricción que limita los tipos permitidos para los tipos que son compatibles con el tipo base o interfaz.</span><span class="sxs-lookup"><span data-stu-id="8be8b-109">A flexible type is equivalent to a generic type that has a constraint that limits the allowed types to types that are compatible with the base or interface type.</span></span> <span data-ttu-id="8be8b-110">Es decir, las dos líneas de código siguientes son equivalentes.</span><span class="sxs-lookup"><span data-stu-id="8be8b-110">That is, the following two lines of code are equivalent.</span></span>

```fsharp
#SomeType

'T when 'T :> SomeType
```

<span data-ttu-id="8be8b-111">Tipos flexibles son útiles en varios tipos de situaciones.</span><span class="sxs-lookup"><span data-stu-id="8be8b-111">Flexible types are useful in several types of situations.</span></span> <span data-ttu-id="8be8b-112">Por ejemplo, si tiene una función de orden superior (es decir, una función que toma una función como argumento), a menudo es útil para que la función devuelva un tipo flexible.</span><span class="sxs-lookup"><span data-stu-id="8be8b-112">For example, when you have a higher order function (a function that takes a function as an argument), it is often useful to have the function return a flexible type.</span></span> <span data-ttu-id="8be8b-113">En el ejemplo siguiente, el uso de un tipo flexible con un argumento sequence en `iterate2` permite que la función de orden superior trabajar con funciones que generan secuencias, matrices, listas y cualquier otro tipo enumerable.</span><span class="sxs-lookup"><span data-stu-id="8be8b-113">In the following example, the use of a flexible type with a sequence argument in `iterate2` enables the higher order function to work with functions that generate sequences, arrays, lists, and any other enumerable type.</span></span>

<span data-ttu-id="8be8b-114">Tenga en cuenta las siguientes dos funciones, uno de los que devuelve una secuencia, el otro devuelve un tipo flexible.</span><span class="sxs-lookup"><span data-stu-id="8be8b-114">Consider the following two functions, one of which returns a sequence, the other of which returns a flexible type.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4101.fs)]

<span data-ttu-id="8be8b-115">Como otro ejemplo, considere la [Seq.concat](https://msdn.microsoft.com/library/2eeb69a9-fc2f-4b7d-8dee-101fa2b00712) función de biblioteca:</span><span class="sxs-lookup"><span data-stu-id="8be8b-115">As another example, consider the [Seq.concat](https://msdn.microsoft.com/library/2eeb69a9-fc2f-4b7d-8dee-101fa2b00712) library function:</span></span>

```fsharp
val concat: sequences:seq<#seq<'T>> -> seq<'T>
```

<span data-ttu-id="8be8b-116">Puede pasar cualquiera de las siguientes secuencias enumerables a esta función:</span><span class="sxs-lookup"><span data-stu-id="8be8b-116">You can pass any of the following enumerable sequences to this function:</span></span>

- <span data-ttu-id="8be8b-117">Una lista de listas</span><span class="sxs-lookup"><span data-stu-id="8be8b-117">A list of lists</span></span>
- <span data-ttu-id="8be8b-118">Una lista de matrices</span><span class="sxs-lookup"><span data-stu-id="8be8b-118">A list of arrays</span></span>
- <span data-ttu-id="8be8b-119">Una matriz de listas</span><span class="sxs-lookup"><span data-stu-id="8be8b-119">An array of lists</span></span>
- <span data-ttu-id="8be8b-120">Una matriz de secuencias</span><span class="sxs-lookup"><span data-stu-id="8be8b-120">An array of sequences</span></span>
- <span data-ttu-id="8be8b-121">Cualquier otra combinación de secuencias enumerables</span><span class="sxs-lookup"><span data-stu-id="8be8b-121">Any other combination of enumerable sequences</span></span>

<span data-ttu-id="8be8b-122">El siguiente código utiliza `Seq.concat` para demostrar los escenarios que se pueden admitir mediante el uso de tipos flexibles.</span><span class="sxs-lookup"><span data-stu-id="8be8b-122">The following code uses `Seq.concat` to demonstrate the scenarios that you can support by using flexible types.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4102.fs)]

<span data-ttu-id="8be8b-123">La salida es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="8be8b-123">The output is as follows.</span></span>

```
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
```

<span data-ttu-id="8be8b-124">En F #, como en otros lenguajes orientados a objetos, hay contextos en los que los tipos derivados o tipos que implementan interfaces se convierten automáticamente en un tipo base o interfaz.</span><span class="sxs-lookup"><span data-stu-id="8be8b-124">In F#, as in other object-oriented languages, there are contexts in which derived types or types that implement interfaces are automatically converted to a base type or interface type.</span></span> <span data-ttu-id="8be8b-125">Estas conversiones automáticas se producen en argumentos directos, pero no cuando el tipo está en una posición subordinada, como parte de un tipo más complejo, como un tipo de valor devuelto de un tipo de función, o como un argumento de tipo.</span><span class="sxs-lookup"><span data-stu-id="8be8b-125">These automatic conversions occur in direct arguments, but not when the type is in a subordinate position, as part of a more complex type such as a return type of a function type, or as a type argument.</span></span> <span data-ttu-id="8be8b-126">Por lo tanto, la notación de tipo flexible es especialmente útil cuando el tipo que aplica a forma parte de un tipo más complejo.</span><span class="sxs-lookup"><span data-stu-id="8be8b-126">Thus, the flexible type notation is primarily useful when the type you are applying it to is part of a more complex type.</span></span>

## <a name="see-also"></a><span data-ttu-id="8be8b-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="8be8b-127">See also</span></span>

- [<span data-ttu-id="8be8b-128">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="8be8b-128">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="8be8b-129">Genéricos</span><span class="sxs-lookup"><span data-stu-id="8be8b-129">Generics</span></span>](generics/index.md)
