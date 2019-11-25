---
title: Propiedades indizadas
description: Obtenga información sobre las propiedades F#indizadas en, que permiten el acceso de tipo matriz a los datos ordenados.
ms.date: 11/04/2019
ms.openlocfilehash: f6cf3bfa737d2bf458e379594be5884696cee3e1
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976611"
---
# <a name="indexed-properties"></a><span data-ttu-id="a59b0-103">Propiedades indizadas</span><span class="sxs-lookup"><span data-stu-id="a59b0-103">Indexed Properties</span></span>

<span data-ttu-id="a59b0-104">Al definir una clase que resume los datos ordenados, a veces puede resultar útil proporcionar un acceso indizado a esos datos sin exponer la implementación subyacente.</span><span class="sxs-lookup"><span data-stu-id="a59b0-104">When defining a class that abstracts over ordered data, it can sometimes be helpful to provide indexed access to that data without exposing the underlying implementation.</span></span> <span data-ttu-id="a59b0-105">Esto se hace con el miembro `Item`.</span><span class="sxs-lookup"><span data-stu-id="a59b0-105">This is done with the `Item` member.</span></span>

## <a name="syntax"></a><span data-ttu-id="a59b0-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a59b0-106">Syntax</span></span>

```fsharp
// Indexed property that can be read and written to
member self-identifier.Item
    with get(index-values) =
        get-member-body
    and set index-values values-to-set =
        set-member-body

// Indexed property can only be read
member self-identifier.Item
    with get(index-values) =
        get-member-body

// Indexed property that can only be set
member self-identifier.Item
    with set index-values values-to-set =
        set-member-body
```

## <a name="remarks"></a><span data-ttu-id="a59b0-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a59b0-107">Remarks</span></span>

<span data-ttu-id="a59b0-108">Las formas de la sintaxis anterior muestran cómo definir las propiedades indizadas que tienen un método `get` y un `set`, tienen un método `get` solamente o tienen un método `set` solo.</span><span class="sxs-lookup"><span data-stu-id="a59b0-108">The forms of the previous syntax show how to define indexed properties that have both a `get` and a `set` method, have a `get` method only, or have a `set` method only.</span></span> <span data-ttu-id="a59b0-109">También puede combinar la sintaxis que se muestra para Get only y la sintaxis que se muestra solo para Set, y generar una propiedad que tenga get y set.</span><span class="sxs-lookup"><span data-stu-id="a59b0-109">You can also combine both the syntax shown for get only and the syntax shown for set only, and produce a property that has both get and set.</span></span> <span data-ttu-id="a59b0-110">Este último formulario le permite colocar distintos modificadores y atributos de accesibilidad en los métodos GET y set.</span><span class="sxs-lookup"><span data-stu-id="a59b0-110">This latter form allows you to put different accessibility modifiers and attributes on the get and set methods.</span></span>

<span data-ttu-id="a59b0-111">Con el nombre `Item`, el compilador trata la propiedad como una propiedad indizada predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a59b0-111">By using the name `Item`, the compiler treats the property as a default indexed property.</span></span> <span data-ttu-id="a59b0-112">Una *propiedad indizada predeterminada* es una propiedad a la que se puede tener acceso mediante una sintaxis similar a la de la matriz en la instancia del objeto.</span><span class="sxs-lookup"><span data-stu-id="a59b0-112">A *default indexed property* is a property that you can access by using array-like syntax on the object instance.</span></span> <span data-ttu-id="a59b0-113">Por ejemplo, si `o` es un objeto del tipo que define esta propiedad, se utiliza la sintaxis `o.[index]` para tener acceso a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="a59b0-113">For example, if `o` is an object of the type that defines this property, the syntax `o.[index]` is used to access the property.</span></span>

<span data-ttu-id="a59b0-114">La sintaxis para tener acceso a una propiedad indizada no predeterminada consiste en proporcionar el nombre de la propiedad y el índice entre paréntesis, al igual que un miembro normal.</span><span class="sxs-lookup"><span data-stu-id="a59b0-114">The syntax for accessing a non-default indexed property is to provide the name of the property and the index in parentheses, just like a regular member.</span></span> <span data-ttu-id="a59b0-115">Por ejemplo, si se llama a la propiedad en `o` `Ordinal`, se escribe `o.Ordinal(index)` para tener acceso a ella.</span><span class="sxs-lookup"><span data-stu-id="a59b0-115">For example, if the property on `o` is called `Ordinal`, you write `o.Ordinal(index)` to access it.</span></span>

<span data-ttu-id="a59b0-116">Independientemente de la forma que use, siempre debe usar la forma currificada para el método Set en una propiedad indizada.</span><span class="sxs-lookup"><span data-stu-id="a59b0-116">Regardless of which form you use, you should always use the curried form for the set method on an indexed property.</span></span> <span data-ttu-id="a59b0-117">Para obtener información sobre las funciones currificadas, vea [funciones](../functions/index.md).</span><span class="sxs-lookup"><span data-stu-id="a59b0-117">For information about curried functions, see [Functions](../functions/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="a59b0-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a59b0-118">Example</span></span>

<span data-ttu-id="a59b0-119">En el ejemplo de código siguiente se muestra la definición y el uso de las propiedades indizadas predeterminadas y no predeterminadas que tienen los métodos GET y set.</span><span class="sxs-lookup"><span data-stu-id="a59b0-119">The following code example illustrates the definition and use of default and non-default indexed properties that have get and set methods.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3301.fs)]

## <a name="output"></a><span data-ttu-id="a59b0-120">Resultados</span><span class="sxs-lookup"><span data-stu-id="a59b0-120">Output</span></span>

```console
ONE two three four five six seven eight nine ten
ONE first two second three third four fourth five fifth six 6th
seven seventh eight eighth nine ninth ten tenth
```

## <a name="indexed-properties-with-multiple-index-values"></a><span data-ttu-id="a59b0-121">Propiedades indizadas con varios valores de índice</span><span class="sxs-lookup"><span data-stu-id="a59b0-121">Indexed Properties with multiple index values</span></span>

<span data-ttu-id="a59b0-122">Las propiedades indizadas pueden tener más de un valor de índice.</span><span class="sxs-lookup"><span data-stu-id="a59b0-122">Indexed properties can have more than one index value.</span></span> <span data-ttu-id="a59b0-123">En ese caso, los valores se separan mediante comas cuando se usa la propiedad.</span><span class="sxs-lookup"><span data-stu-id="a59b0-123">In that case, the values are separated by commas when the property is used.</span></span> <span data-ttu-id="a59b0-124">El método Set de esta propiedad debe tener dos argumentos currificados, el primero es una tupla que contiene las claves y el segundo es el valor que se va a establecer.</span><span class="sxs-lookup"><span data-stu-id="a59b0-124">The set method in such a property must have two curried arguments, the first of which is a tuple containing the keys, and the second of which is the value to set.</span></span>

<span data-ttu-id="a59b0-125">En el código siguiente se muestra el uso de una propiedad indizada con varios valores de índice.</span><span class="sxs-lookup"><span data-stu-id="a59b0-125">The following code demonstrates the use of an indexed property with multiple index values.</span></span>

```fsharp
open System.Collections.Generic

/// Basic implementation of a sparse matrix based on a dictionary
type SparseMatrix() =
    let table = new Dictionary<(int * int), float>()
    member _.Item
        // Because the key is comprised of two values, 'get' has two index values
        with get(key1, key2) = table.[(key1, key2)]

        // 'set' has two index values and a new value to place in the key's position
        and set (key1, key2) value = table.[(key1, key2)] <- value

let sm = new SparseMatrix()
for i in 1..1000 do
    sm.[i, i] <- float i * float i
```

## <a name="see-also"></a><span data-ttu-id="a59b0-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="a59b0-126">See also</span></span>

- [<span data-ttu-id="a59b0-127">Miembros</span><span class="sxs-lookup"><span data-stu-id="a59b0-127">Members</span></span>](index.md)
