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
# <a name="indexed-properties"></a>Propiedades indizadas

Al definir una clase que resume los datos ordenados, a veces puede resultar útil proporcionar un acceso indizado a esos datos sin exponer la implementación subyacente. Esto se hace con el miembro `Item`.

## <a name="syntax"></a>Sintaxis

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

## <a name="remarks"></a>Comentarios

Las formas de la sintaxis anterior muestran cómo definir las propiedades indizadas que tienen un método `get` y un `set`, tienen un método `get` solamente o tienen un método `set` solo. También puede combinar la sintaxis que se muestra para Get only y la sintaxis que se muestra solo para Set, y generar una propiedad que tenga get y set. Este último formulario le permite colocar distintos modificadores y atributos de accesibilidad en los métodos GET y set.

Con el nombre `Item`, el compilador trata la propiedad como una propiedad indizada predeterminada. Una *propiedad indizada predeterminada* es una propiedad a la que se puede tener acceso mediante una sintaxis similar a la de la matriz en la instancia del objeto. Por ejemplo, si `o` es un objeto del tipo que define esta propiedad, se utiliza la sintaxis `o.[index]` para tener acceso a la propiedad.

La sintaxis para tener acceso a una propiedad indizada no predeterminada consiste en proporcionar el nombre de la propiedad y el índice entre paréntesis, al igual que un miembro normal. Por ejemplo, si se llama a la propiedad en `o` `Ordinal`, se escribe `o.Ordinal(index)` para tener acceso a ella.

Independientemente de la forma que use, siempre debe usar la forma currificada para el método Set en una propiedad indizada. Para obtener información sobre las funciones currificadas, vea [funciones](../functions/index.md).

## <a name="example"></a>Ejemplo

En el ejemplo de código siguiente se muestra la definición y el uso de las propiedades indizadas predeterminadas y no predeterminadas que tienen los métodos GET y set.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3301.fs)]

## <a name="output"></a>Resultados

```console
ONE two three four five six seven eight nine ten
ONE first two second three third four fourth five fifth six 6th
seven seventh eight eighth nine ninth ten tenth
```

## <a name="indexed-properties-with-multiple-index-values"></a>Propiedades indizadas con varios valores de índice

Las propiedades indizadas pueden tener más de un valor de índice. En ese caso, los valores se separan mediante comas cuando se usa la propiedad. El método Set de esta propiedad debe tener dos argumentos currificados, el primero es una tupla que contiene las claves y el segundo es el valor que se va a establecer.

En el código siguiente se muestra el uso de una propiedad indizada con varios valores de índice.

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

## <a name="see-also"></a>Vea también

- [Miembros](index.md)
