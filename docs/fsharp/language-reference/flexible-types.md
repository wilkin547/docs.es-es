---
title: Tipos flexibles
description: 'Obtenga información sobre cómo usar la anotación de tipo flexible de F #, que indica que un parámetro, una variable o un valor tiene un tipo que es compatible con un tipo especificado.'
ms.date: 08/15/2020
ms.openlocfilehash: 44241ad082cd7f3de9e0cc6a48b8a8946e7b33d3
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/18/2020
ms.locfileid: "88557755"
---
# <a name="flexible-types"></a><span data-ttu-id="3e2f6-103">Tipos flexibles</span><span class="sxs-lookup"><span data-stu-id="3e2f6-103">Flexible Types</span></span>

<span data-ttu-id="3e2f6-104">Una *anotación de tipo flexible* indica que un parámetro, una variable o un valor tiene un tipo que es compatible con un tipo especificado, donde la compatibilidad se determina por posición en una jerarquía orientada a objetos de clases o interfaces.</span><span class="sxs-lookup"><span data-stu-id="3e2f6-104">A *flexible type annotation* indicates that a parameter, variable, or value has a type that is compatible with a specified type, where compatibility is determined by position in an object-oriented hierarchy of classes or interfaces.</span></span> <span data-ttu-id="3e2f6-105">Los tipos flexibles son especialmente útiles cuando la conversión automática en tipos situados más arriba en la jerarquía de tipos no se produce, pero aún desea habilitar la funcionalidad para trabajar con cualquier tipo de la jerarquía o con cualquier tipo que implemente una interfaz.</span><span class="sxs-lookup"><span data-stu-id="3e2f6-105">Flexible types are useful specifically when the automatic conversion to types higher in the type hierarchy does not occur but you still want to enable your functionality to work with any type in the hierarchy or any type that implements an interface.</span></span>

## <a name="syntax"></a><span data-ttu-id="3e2f6-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3e2f6-106">Syntax</span></span>

```fsharp
#type
```

## <a name="remarks"></a><span data-ttu-id="3e2f6-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3e2f6-107">Remarks</span></span>

<span data-ttu-id="3e2f6-108">En la sintaxis anterior, *Type* representa un tipo base o una interfaz.</span><span class="sxs-lookup"><span data-stu-id="3e2f6-108">In the previous syntax, *type* represents a base type or an interface.</span></span>

<span data-ttu-id="3e2f6-109">Un tipo flexible es equivalente a un tipo genérico que tiene una restricción que limita los tipos permitidos a tipos que son compatibles con la base o el tipo de interfaz.</span><span class="sxs-lookup"><span data-stu-id="3e2f6-109">A flexible type is equivalent to a generic type that has a constraint that limits the allowed types to types that are compatible with the base or interface type.</span></span> <span data-ttu-id="3e2f6-110">Es decir, las dos líneas de código siguientes son equivalentes.</span><span class="sxs-lookup"><span data-stu-id="3e2f6-110">That is, the following two lines of code are equivalent.</span></span>

```fsharp
#SomeType

'T when 'T :> SomeType
```

<span data-ttu-id="3e2f6-111">Los tipos flexibles son útiles en varios tipos de situaciones.</span><span class="sxs-lookup"><span data-stu-id="3e2f6-111">Flexible types are useful in several types of situations.</span></span> <span data-ttu-id="3e2f6-112">Por ejemplo, si tiene una función de orden superior (una función que toma una función como argumento), a menudo resulta útil que la función devuelva un tipo flexible.</span><span class="sxs-lookup"><span data-stu-id="3e2f6-112">For example, when you have a higher order function (a function that takes a function as an argument), it is often useful to have the function return a flexible type.</span></span> <span data-ttu-id="3e2f6-113">En el ejemplo siguiente, el uso de un tipo flexible con un argumento de secuencia en `iterate2` permite que la función de orden superior funcione con funciones que generan secuencias, matrices, listas y cualquier otro tipo Enumerable.</span><span class="sxs-lookup"><span data-stu-id="3e2f6-113">In the following example, the use of a flexible type with a sequence argument in `iterate2` enables the higher order function to work with functions that generate sequences, arrays, lists, and any other enumerable type.</span></span>

<span data-ttu-id="3e2f6-114">Tenga en cuenta las dos funciones siguientes, una de las cuales devuelve una secuencia, la otra devuelve un tipo flexible.</span><span class="sxs-lookup"><span data-stu-id="3e2f6-114">Consider the following two functions, one of which returns a sequence, the other of which returns a flexible type.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4101.fs)]

<span data-ttu-id="3e2f6-115">Como otro ejemplo, considere la función de biblioteca [Seq. concat](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#concat) :</span><span class="sxs-lookup"><span data-stu-id="3e2f6-115">As another example, consider the [Seq.concat](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#concat) library function:</span></span>

```fsharp
val concat: sequences:seq<#seq<'T>> -> seq<'T>
```

<span data-ttu-id="3e2f6-116">Puede pasar cualquiera de las secuencias enumerables siguientes a esta función:</span><span class="sxs-lookup"><span data-stu-id="3e2f6-116">You can pass any of the following enumerable sequences to this function:</span></span>

- <span data-ttu-id="3e2f6-117">Una lista de listas</span><span class="sxs-lookup"><span data-stu-id="3e2f6-117">A list of lists</span></span>
- <span data-ttu-id="3e2f6-118">Una lista de matrices</span><span class="sxs-lookup"><span data-stu-id="3e2f6-118">A list of arrays</span></span>
- <span data-ttu-id="3e2f6-119">Una matriz de listas</span><span class="sxs-lookup"><span data-stu-id="3e2f6-119">An array of lists</span></span>
- <span data-ttu-id="3e2f6-120">Una matriz de secuencias</span><span class="sxs-lookup"><span data-stu-id="3e2f6-120">An array of sequences</span></span>
- <span data-ttu-id="3e2f6-121">Cualquier otra combinación de secuencias enumerables</span><span class="sxs-lookup"><span data-stu-id="3e2f6-121">Any other combination of enumerable sequences</span></span>

<span data-ttu-id="3e2f6-122">En el código siguiente se usa `Seq.concat` para mostrar los escenarios que se pueden admitir mediante el uso de tipos flexibles.</span><span class="sxs-lookup"><span data-stu-id="3e2f6-122">The following code uses `Seq.concat` to demonstrate the scenarios that you can support by using flexible types.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4102.fs)]

<span data-ttu-id="3e2f6-123">La salida es la siguiente.</span><span class="sxs-lookup"><span data-stu-id="3e2f6-123">The output is as follows.</span></span>

```console
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
```

<span data-ttu-id="3e2f6-124">En F #, como en otros lenguajes orientados a objetos, hay contextos en los que los tipos derivados o tipos que implementan interfaces se convierten automáticamente en un tipo base o de interfaz.</span><span class="sxs-lookup"><span data-stu-id="3e2f6-124">In F#, as in other object-oriented languages, there are contexts in which derived types or types that implement interfaces are automatically converted to a base type or interface type.</span></span> <span data-ttu-id="3e2f6-125">Estas conversiones automáticas se producen en argumentos directos, pero no cuando el tipo está en una posición subordinada, como parte de un tipo más complejo, como un tipo de valor devuelto de un tipo de función, o como un argumento de tipo.</span><span class="sxs-lookup"><span data-stu-id="3e2f6-125">These automatic conversions occur in direct arguments, but not when the type is in a subordinate position, as part of a more complex type such as a return type of a function type, or as a type argument.</span></span> <span data-ttu-id="3e2f6-126">Por lo tanto, la notación de tipos flexibles es principalmente útil cuando el tipo al que se aplica es parte de un tipo más complejo.</span><span class="sxs-lookup"><span data-stu-id="3e2f6-126">Thus, the flexible type notation is primarily useful when the type you are applying it to is part of a more complex type.</span></span>

## <a name="see-also"></a><span data-ttu-id="3e2f6-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="3e2f6-127">See also</span></span>

- [<span data-ttu-id="3e2f6-128">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="3e2f6-128">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="3e2f6-129">Genéricos</span><span class="sxs-lookup"><span data-stu-id="3e2f6-129">Generics</span></span>](./generics/index.md)
