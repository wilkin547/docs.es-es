---
title: Propiedades indizadas (F#)
description: 'Obtenga información acerca de las propiedades indizadas en F #, que son propiedades que proporcionan acceso a datos ordenados.'
ms.date: 05/16/2016
ms.openlocfilehash: e56e4e2ea3f35df4c8ec46012357242cb6ce69f3
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2018
ms.locfileid: "45583429"
---
# <a name="indexed-properties"></a>Propiedades indizadas

*Las propiedades indizadas* se ordenan de propiedades que proporcionan acceso a datos. Vienen en tres formas:

* `Item`
* `Ordinal`
* `Cardinal`

Un miembro de F # debe tener nombres uno de estos tres nombres para proporcionar acceso de tipo matriz. `IndexerName` se utiliza para representar cualquiera de las tres opciones siguientes:

## <a name="syntax"></a>Sintaxis

```fsharp
// Indexed property that has both get and set defined.
member self-identifier.IndexerName
    with get(index-variable) =
        get-function-body
    and set index-variablesvalue-variables =
        set-function-body

// Indexed property that has get only.
member self-identifier.IndexerName(index-variable) =
    get-function-body

// Alternative syntax for indexed property with get only
member self-identifier.IndexerName
    with get(index-variables) =
        get-function-body

// Indexed property that has set only.
member self-identifier.IndexerName
    with set index-variablesvalue-variables = 
        set-function-body
```

## <a name="remarks"></a>Comentarios

Los formularios de la sintaxis anterior muestran cómo definir las propiedades indizadas con las dos un `get` y un `set` método, tiene un `get` solo, método o tiene un `set` solo método. También puede combinar la sintaxis que se muestra para solo get y la sintaxis mostrada para el conjunto solo y generar una propiedad que tiene get y set. Esta última forma permite colocar los atributos y modificadores de accesibilidad diferente en la operación get y establecer los métodos.

Cuando el *IndexerName* es `Item`, el compilador trata la propiedad como una propiedad indizada predeterminada. Un *propiedad indizada predeterminada* es una propiedad que puede tener acceso utilizando la sintaxis de matriz en la instancia del objeto. Por ejemplo, si `obj` es un objeto del tipo que define esta propiedad, la sintaxis `obj.[index]` se usa para acceder a la propiedad.

La sintaxis para tener acceso a una propiedad indizada no predeterminada consiste en proporcionar el nombre de la propiedad y el índice entre paréntesis. Por ejemplo, si la propiedad es `Ordinal`, escribe `obj.Ordinal(index)` para acceder a él.

Independientemente del formulario que utilice, debe usar siempre la currificada. para el `set` método en una propiedad indizada. Para obtener información acerca de las funciones currificadas, vea [funciones](../functions/index.md).

## <a name="example"></a>Ejemplo

El ejemplo de código siguiente muestra la definición y uso de predeterminado y las propiedades indizadas no predeterminado que tienen get y establecer los métodos.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3301.fs)]

## <a name="output"></a>Salida

```
ONE two three four five six seven eight nine ten
ONE first two second three third four fourth five fifth six 6th
seven seventh eight eighth nine ninth ten tenth
```

## <a name="indexed-properties-with-multiple-index-variables"></a>Propiedades indizadas con varias Variables de índice

Las propiedades indizadas pueden tener más de una variable de índice. En ese caso, las variables están separadas por comas, cuando se usa la propiedad. El método set de esta propiedad debe tener dos argumentos currificados, el primero de los cuales es una tupla que contiene las claves y el segundo de los cuales es el valor que se va a establecer.

El código siguiente muestra el uso de una propiedad indizada con varias variables de índice.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3302.fs)]

## <a name="see-also"></a>Vea también

- [Miembros](index.md)
