---
title: Propiedades indizadas
description: Obtenga información sobre las propiedades indizadas en F#, que permiten obtener acceso a la forma de matriz a los datos ordenados.
ms.date: 10/17/2018
ms.openlocfilehash: bc330641c451973ddefa0a34fe6e757a808f6cb7
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2019
ms.locfileid: "57678622"
---
# <a name="indexed-properties"></a>Propiedades indizadas

Al definir una clase que abstrae los datos ordenados, en ocasiones puede ser útil proporcionar acceso indizado a los datos sin exponer la implementación subyacente. Esto se realiza con el `Index` miembro.

## <a name="syntax"></a>Sintaxis

```fsharp
// Indexed property that has both get and set defined.
member self-identifier.Index
    with get(index-values) =
        get-member-body
    and set index-values values-to-set =
        set-member-body

// Indexed property with get only
member self-identifier.Index
    with get(index-values) =
        get-member-body

// Indexed property that has set only.
member self-identifier.Index
    with set index-values values-to-set =
        set-member-body
```

## <a name="remarks"></a>Comentarios

Los formularios de la sintaxis anterior muestran cómo definir las propiedades indizadas con las dos un `get` y un `set` método, tiene un `get` solo, método o tiene un `set` solo método. También puede combinar la sintaxis que se muestra para solo get y la sintaxis mostrada para el conjunto solo y generar una propiedad que tiene get y set. Esta última forma permite colocar los atributos y modificadores de accesibilidad diferente en la operación get y establecer los métodos.

Con el nombre `Item`, el compilador trata la propiedad como una propiedad indizada predeterminada. Un *propiedad indizada predeterminada* es una propiedad que puede tener acceso utilizando la sintaxis de matriz en la instancia del objeto. Por ejemplo, si `o` es un objeto del tipo que define esta propiedad, la sintaxis `o.[index]` se usa para acceder a la propiedad.

La sintaxis para tener acceso a una propiedad indizada predeterminada no es proporcionar el nombre de la propiedad y el índice entre paréntesis, al igual que un miembro regular. Por ejemplo, si la propiedad `o` se denomina `Ordinal`, escribe `o.Ordinal(index)` para acceder a él.

Independientemente del formulario que utilice, debe usar siempre la currificada para el método set en una propiedad indizada. Para obtener información acerca de las funciones currificadas, vea [funciones](../functions/index.md).

## <a name="example"></a>Ejemplo

El ejemplo de código siguiente muestra la definición y uso de predeterminado y las propiedades indizadas no predeterminado que tienen get y establecer los métodos.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3301.fs)]

## <a name="output"></a>Salida

```console
ONE two three four five six seven eight nine ten
ONE first two second three third four fourth five fifth six 6th
seven seventh eight eighth nine ninth ten tenth
```

## <a name="indexed-properties-with-multiple-index-values"></a>Propiedades indizadas con varios valores de índice

Las propiedades indizadas pueden tener más de un valor de índice. En ese caso, los valores están separados por comas cuando se usa la propiedad. El método set de esta propiedad debe tener dos argumentos currificados, el primero de los cuales es una tupla que contiene las claves y el segundo de los cuales es el valor que se va a establecer.

El código siguiente muestra el uso de una propiedad indizada con varios valores de índice.

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

## <a name="see-also"></a>Vea también

- [Miembros](index.md)
