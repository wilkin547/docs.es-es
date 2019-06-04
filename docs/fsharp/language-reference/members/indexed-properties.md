---
title: Propiedades indizadas
description: Obtenga información sobre las propiedades indizadas en F#, que permiten obtener acceso a la forma de matriz a los datos ordenados.
ms.date: 10/17/2018
ms.openlocfilehash: 7fc8f46e029255c6ed985a43b92c8f7c2908c428
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2019
ms.locfileid: "66489480"
---
# <a name="indexed-properties"></a><span data-ttu-id="e2790-103">Propiedades indizadas</span><span class="sxs-lookup"><span data-stu-id="e2790-103">Indexed Properties</span></span>

<span data-ttu-id="e2790-104">Al definir una clase que abstrae los datos ordenados, en ocasiones puede ser útil proporcionar acceso indizado a los datos sin exponer la implementación subyacente.</span><span class="sxs-lookup"><span data-stu-id="e2790-104">When defining a class that abstracts over ordered data, it can sometimes be helpful to provide indexed access to that data without exposing the underlying implementation.</span></span> <span data-ttu-id="e2790-105">Esto se realiza con el `Item` miembro.</span><span class="sxs-lookup"><span data-stu-id="e2790-105">This is done with the `Item` member.</span></span>

## <a name="syntax"></a><span data-ttu-id="e2790-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e2790-106">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="e2790-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e2790-107">Remarks</span></span>

<span data-ttu-id="e2790-108">Los formularios de la sintaxis anterior muestran cómo definir las propiedades indizadas con las dos un `get` y un `set` método, tiene un `get` solo, método o tiene un `set` solo método.</span><span class="sxs-lookup"><span data-stu-id="e2790-108">The forms of the previous syntax show how to define indexed properties that have both a `get` and a `set` method, have a `get` method only, or have a `set` method only.</span></span> <span data-ttu-id="e2790-109">También puede combinar la sintaxis que se muestra para solo get y la sintaxis mostrada para el conjunto solo y generar una propiedad que tiene get y set.</span><span class="sxs-lookup"><span data-stu-id="e2790-109">You can also combine both the syntax shown for get only and the syntax shown for set only, and produce a property that has both get and set.</span></span> <span data-ttu-id="e2790-110">Esta última forma permite colocar los atributos y modificadores de accesibilidad diferente en la operación get y establecer los métodos.</span><span class="sxs-lookup"><span data-stu-id="e2790-110">This latter form allows you to put different accessibility modifiers and attributes on the get and set methods.</span></span>

<span data-ttu-id="e2790-111">Con el nombre `Item`, el compilador trata la propiedad como una propiedad indizada predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e2790-111">By using the name `Item`, the compiler treats the property as a default indexed property.</span></span> <span data-ttu-id="e2790-112">Un *propiedad indizada predeterminada* es una propiedad que puede tener acceso utilizando la sintaxis de matriz en la instancia del objeto.</span><span class="sxs-lookup"><span data-stu-id="e2790-112">A *default indexed property* is a property that you can access by using array-like syntax on the object instance.</span></span> <span data-ttu-id="e2790-113">Por ejemplo, si `o` es un objeto del tipo que define esta propiedad, la sintaxis `o.[index]` se usa para acceder a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="e2790-113">For example, if `o` is an object of the type that defines this property, the syntax `o.[index]` is used to access the property.</span></span>

<span data-ttu-id="e2790-114">La sintaxis para tener acceso a una propiedad indizada predeterminada no es proporcionar el nombre de la propiedad y el índice entre paréntesis, al igual que un miembro regular.</span><span class="sxs-lookup"><span data-stu-id="e2790-114">The syntax for accessing a non-default indexed property is to provide the name of the property and the index in parentheses, just like a regular member.</span></span> <span data-ttu-id="e2790-115">Por ejemplo, si la propiedad `o` se denomina `Ordinal`, escribe `o.Ordinal(index)` para acceder a él.</span><span class="sxs-lookup"><span data-stu-id="e2790-115">For example, if the property on `o` is called `Ordinal`, you write `o.Ordinal(index)` to access it.</span></span>

<span data-ttu-id="e2790-116">Independientemente del formulario que utilice, debe usar siempre la currificada para el método set en una propiedad indizada.</span><span class="sxs-lookup"><span data-stu-id="e2790-116">Regardless of which form you use, you should always use the curried form for the set method on an indexed property.</span></span> <span data-ttu-id="e2790-117">Para obtener información acerca de las funciones currificadas, vea [funciones](../functions/index.md).</span><span class="sxs-lookup"><span data-stu-id="e2790-117">For information about curried functions, see [Functions](../functions/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="e2790-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e2790-118">Example</span></span>

<span data-ttu-id="e2790-119">El ejemplo de código siguiente muestra la definición y uso de predeterminado y las propiedades indizadas no predeterminado que tienen get y establecer los métodos.</span><span class="sxs-lookup"><span data-stu-id="e2790-119">The following code example illustrates the definition and use of default and non-default indexed properties that have get and set methods.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3301.fs)]

## <a name="output"></a><span data-ttu-id="e2790-120">Salida</span><span class="sxs-lookup"><span data-stu-id="e2790-120">Output</span></span>

```console
ONE two three four five six seven eight nine ten
ONE first two second three third four fourth five fifth six 6th
seven seventh eight eighth nine ninth ten tenth
```

## <a name="indexed-properties-with-multiple-index-values"></a><span data-ttu-id="e2790-121">Propiedades indizadas con varios valores de índice</span><span class="sxs-lookup"><span data-stu-id="e2790-121">Indexed Properties with multiple index values</span></span>

<span data-ttu-id="e2790-122">Las propiedades indizadas pueden tener más de un valor de índice.</span><span class="sxs-lookup"><span data-stu-id="e2790-122">Indexed properties can have more than one index value.</span></span> <span data-ttu-id="e2790-123">En ese caso, los valores están separados por comas cuando se usa la propiedad.</span><span class="sxs-lookup"><span data-stu-id="e2790-123">In that case, the values are separated by commas when the property is used.</span></span> <span data-ttu-id="e2790-124">El método set de esta propiedad debe tener dos argumentos currificados, el primero de los cuales es una tupla que contiene las claves y el segundo de los cuales es el valor que se va a establecer.</span><span class="sxs-lookup"><span data-stu-id="e2790-124">The set method in such a property must have two curried arguments, the first of which is a tuple containing the keys, and the second of which is the value to set.</span></span>

<span data-ttu-id="e2790-125">El código siguiente muestra el uso de una propiedad indizada con varios valores de índice.</span><span class="sxs-lookup"><span data-stu-id="e2790-125">The following code demonstrates the use of an indexed property with multiple index values.</span></span>

```fsharp
open System.Collections.Generic

/// Basic implementation of a sparse matrix based on a dictionary
type SparseMatrix() =
    let table = new Dictionary<(int * int), float>()
    member __.Item
        // Because the key is comprised of two values, 'get' has two index values
        with get(key1, key2) = table.[(key1, key2)]

        // 'set' has two index values and a new value to place in the key's position
        and set (key1, key2) value = table.[(key1, key2)] <- value

let sm = new SparseMatrix()
for i in 1..1000 do
    sm.[i, i] <- float i * float i
```

## <a name="see-also"></a><span data-ttu-id="e2790-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2790-126">See also</span></span>

- [<span data-ttu-id="e2790-127">Miembros</span><span class="sxs-lookup"><span data-stu-id="e2790-127">Members</span></span>](index.md)
