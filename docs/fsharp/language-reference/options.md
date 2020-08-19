---
title: Opciones
description: 'Obtenga información sobre cómo usar los tipos de opción de F # cuando es posible que no exista un valor real para una variable o un valor con nombre.'
ms.date: 08/13/2020
ms.openlocfilehash: 0618590c10f6ecac51a23483ca0ab6cd66f2df4f
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/18/2020
ms.locfileid: "88557573"
---
# <a name="options"></a>Opciones

El tipo de opción en F # se utiliza cuando es posible que no exista un valor real para una variable o valor con nombre. Una opción tiene un tipo subyacente y puede contener un valor de ese tipo, o puede que no tenga un valor.

## <a name="remarks"></a>Comentarios

En el código siguiente se muestra una función que genera un tipo de opción.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1404.fs)]

Como puede ver, si la entrada `a` es mayor que 0, `Some(a)` se genera.  De lo contrario, `None` se genera.

El valor `None` se utiliza cuando una opción no tiene un valor real. De lo contrario, la expresión `Some( ... )` proporciona a la opción un valor. Los valores `Some` y `None` son útiles en la coincidencia de patrones, como en la función siguiente `exists` , que devuelve `true` si la opción tiene un valor y `false` si no lo hace.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1401.fs)]

## <a name="using-options"></a>Usar Opciones

Las opciones se usan normalmente cuando una búsqueda no devuelve un resultado de coincidencia, como se muestra en el código siguiente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1403.fs)]

En el código anterior, se busca una lista de forma recursiva. La función `tryFindMatch` toma una función de predicado `pred` que devuelve un valor booleano y una lista que se va a buscar. Si se encuentra un elemento que satisface el predicado, la recursividad finaliza y la función devuelve el valor como una opción en la expresión `Some(head)` . La recursividad finaliza cuando se encuentra una coincidencia con la lista vacía. En ese momento, no se ha encontrado el valor `head` y `None` se devuelve.

Muchas funciones de la biblioteca de F # que buscan en una colección un valor que puede o no existir devuelven el `option` tipo. Por Convención, estas funciones comienzan con el `try` prefijo, por ejemplo, [`Seq.tryFindIndex`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#tryFindIndex) .

Las opciones también pueden ser útiles cuando es posible que un valor no exista, por ejemplo, si es posible que se produzca una excepción al intentar construir un valor. En el siguiente ejemplo código se muestra cómo hacerlo.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1402.fs)]

La `openFile` función del ejemplo anterior tiene el tipo `string -> File option` porque devuelve un `File` objeto si el archivo se abre correctamente y `None` si se produce una excepción. Dependiendo de la situación, puede que no sea una opción de diseño adecuada para detectar una excepción en lugar de permitir que se propague.

Además, sigue siendo posible pasar `null` o un valor que sea NULL a las `Some` mayúsculas y minúsculas de una opción. Por lo general, esto se debe evitar y, normalmente, está en programación con la rutina de F #, pero es posible debido a la naturaleza de los tipos de referencia en .NET.

## <a name="option-properties-and-methods"></a>Propiedades y métodos de la opción

El tipo de opción admite las siguientes propiedades y métodos.

|Propiedad o método|Tipo|Descripción|
|------------------|----|-----------|
|[None](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-fsharpoption-1.html#None)|`'T option`|Propiedad estática que permite crear un valor de opción que tiene el `None` valor.|
|[Isnone (](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-fsharpoption-1.html#IsNone)|`bool`|Devuelve `true` si la opción tiene el `None` valor.|
|[IsSome (](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-fsharpoption-1.html#IsSome)|`bool`|Devuelve `true` si la opción tiene un valor que no es `None` .|
|[Existen](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-fsharpoption-1.html#Some)|`'T option`|Miembro estático que crea una opción que tiene un valor que no es `None` .|
|[Valor](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-fsharpoption-1.html#Value)|`'T`|Devuelve el valor subyacente o produce una excepción `System.NullReferenceException` si el valor de es `None` .|

## <a name="option-module"></a>Módulo de opción

Hay un módulo, [opción](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html), que contiene funciones útiles que realizan operaciones en las opciones. Algunas funciones repiten la funcionalidad de las propiedades pero son útiles en contextos en los que se necesita una función. [Option. IsSome (](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#isSome) y [Option. isnone (](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#isNone) son dos funciones de módulo que prueban si una opción contiene un valor. [Option. Get](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#get) obtiene el valor, si lo hay. Si no hay ningún valor, se produce una excepción `System.ArgumentException` .

La función [Option. bind](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#bind) ejecuta una función en el valor, si hay un valor. La función debe tomar exactamente un argumento y su tipo de parámetro debe ser el tipo de opción. El valor devuelto de la función es otro tipo de opción.

El módulo de opciones también incluye funciones que corresponden a las funciones que están disponibles para las listas, matrices, secuencias y otros tipos de colección. Estas funciones incluyen [`Option.map`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#map) , [`Option.iter`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#iter) , [`Option.forall`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#forall) , [`Option.exists`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#exists) , [`Option.foldBack`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#foldBack) , [`Option.fold`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#fold) y [`Option.count`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#count) . Estas funciones permiten usar opciones como una colección de cero o un elemento. Para obtener más información y ejemplos, vea la explicación de las funciones de colección en [las listas](lists.md).

## <a name="converting-to-other-types"></a>Convertir a otros tipos

Las opciones se pueden convertir en listas o matrices. Cuando una opción se convierte en cualquiera de estas estructuras de datos, la estructura de datos resultante tiene cero o un elemento. Para convertir una opción en una matriz, use [`Option.toArray`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#toArray) . Para convertir una opción en una lista, use [`Option.toList`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-optionmodule.html#toList) .

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
- [Tipos en F#](fsharp-types.md)
