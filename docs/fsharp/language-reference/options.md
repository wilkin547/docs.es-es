---
title: Opciones (F#)
description: 'Obtener información sobre cómo usar F # opción no podrían existir tipos cuando un valor real para un valor con nombre o una variable.'
ms.date: 05/16/2016
ms.openlocfilehash: c813c377af1db758a40efa2bd73de22cbb4c66f5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="options"></a>Opciones

El tipo de opción en F # se usa cuando no exista un valor real para un valor con nombre o una variable. Una opción tiene un tipo subyacente y puede contener un valor de ese tipo, o quizás no tenga un valor.

## <a name="remarks"></a>Comentarios
El código siguiente muestra una función que genera un tipo de opción.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1404.fs)]

Como puede ver, si la entrada `a` es mayor que 0, `Some(a)` se genera.  En caso contrario, `None` se genera.

El valor `None` se usa cuando una opción no tiene un valor real. En caso contrario, la expresión `Some( ... )` da un valor de la opción. Los valores `Some` y `None` son útiles en la coincidencia de patrones, como se muestra en la siguiente función `exists`, que devuelve `true` si la opción tiene un valor y `false` si no es así.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1401.fs)]

## <a name="using-options"></a>Uso de opciones
Opciones se usan normalmente cuando una búsqueda no devuelve un resultado de búsqueda de coincidencias, tal como se muestra en el código siguiente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1403.fs)]

En el código anterior, una lista es buscada de forma recursiva. La función `tryFindMatch` toma una función de predicado `pred` que devuelve un valor booleano y una lista para buscar. Si se encuentra un elemento que cumple el predicado, finaliza la recursión y la función devuelve el valor como una opción en la expresión `Some(head)`. La recursión finaliza cuando se compara la lista vacía. En ese momento el valor `head` no se ha encontrado, y `None` se devuelve.

Muchas funciones F # biblioteca que búsqueda de una colección para un valor que puede no existir o devolver el `option` tipo. Por convención, estas funciones comienzan con la `try` prefijo, por ejemplo, [ `Seq.tryFindIndex` ](https://msdn.microsoft.com/library/c357b221-edf6-4f68-bf40-82a3156d945a).

Opciones también pueden ser útiles cuando un valor no exista, por ejemplo, si es posible que se produzca una excepción al intentar construir un valor. En el siguiente ejemplo código se muestra cómo hacerlo.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1402.fs)]

El `openFile` función en el ejemplo anterior tiene un tipo `string -> File option` porque devuelve un `File` objeto si el archivo se abre correctamente y `None` si se produce una excepción. Según la situación, no puede ser una opción de diseño adecuado para detectar una excepción en lugar de permitir que se propaguen.


## <a name="option-properties-and-methods"></a>Métodos y propiedades de la opción
El tipo de opción es compatible con las siguientes propiedades y métodos.



|Propiedad o método|Tipo|Descripción|
|------------------|----|-----------|
|[Ninguno](https://msdn.microsoft.com/library/83ef260a-aa33-4e6f-aee6-b9bf0a461476)|`'T option`|Una propiedad estática que le permite crear un valor de opción que tiene la `None` valor.|
|[IsNone](https://msdn.microsoft.com/library/f08532ca-1716-4f60-ae59-8ef6256df234)|`bool`|Devuelve `true` si la opción tiene la `None` valor.|
|[IsSome](https://msdn.microsoft.com/library/c5088d51-c5d7-425f-a77f-12c379bb356f)|`bool`|Devuelve `true` si la opción tiene un valor que no es `None`.|
|[Algunos](https://msdn.microsoft.com/library/12f048d2-e293-4596-accb-de036ecd63fc)|`'T option`|Un miembro estático que crea una opción que tiene un valor que no es `None`.|
|[Valor](https://msdn.microsoft.com/library/c79f68e8-11fd-45b1-a053-e8fc38b56df7)|`'T`|Devuelve el valor subyacente o produce una `System.NullReferenceException` si el valor es `None`.|

## <a name="option-module"></a>Option (módulo)
Hay un módulo, [opción](https://msdn.microsoft.com/library/e615e4d3-bbbb-49ba-addc-6061ea2e2f4c), que contiene funciones útiles que realizan operaciones en Opciones. Algunas funciones repiten la funcionalidad de las propiedades, pero son útiles en contextos donde se necesita una función. [Option.isSome](https://msdn.microsoft.com/library/41ad0857-5672-4326-84b5-c33dc43dcf79) y [Option.isNone](https://msdn.microsoft.com/library/73db6a53-15e7-40a6-94f9-a0049e5f4819) son funciones de módulo que prueben si una opción contiene un valor. [Option.Get](https://msdn.microsoft.com/library/803e9fcb-6edd-4910-808c-25f08cbc55ea) Obtiene el valor, si lo hay. Si no hay ningún valor, inicia `System.ArgumentException`.

El [Option.bind](https://msdn.microsoft.com/library/c3406192-24ac-49b5-bc3b-8f805187f1c0) función ejecuta una función en el valor, si hay un valor. La función debe tomar exactamente un argumento y su parámetro de tipo debe ser del tipo de opción. El valor devuelto de la función es otro tipo de opción.

El módulo de opción también incluye funciones que corresponden a las funciones que están disponibles para las listas, matrices, secuencias y otros tipos de colección. Estas funciones se incluyen [ `Option.map` ](https://msdn.microsoft.com/library/91a20385-7e73-40c2-9adc-635e86d6a622), [ `Option.iter` ](https://msdn.microsoft.com/library/83389eef-3dff-4074-b4cc-f69581c25191), [ `Option.forall` ](https://msdn.microsoft.com/library/ba884586-5eae-49c5-9e36-05481c1c3428), [ `Option.exists` ](https://msdn.microsoft.com/library/a606d2d4-fddc-4eab-ab37-c6138fb7ad99), [ `Option.foldBack` ](https://msdn.microsoft.com/library/a882fbaf-c019-46f0-b4f5-b8c2b8b90ffb), [ `Option.fold` ](https://msdn.microsoft.com/library/af896794-3d53-406c-9411-316cd5c33ad8), y [ `Option.count` ](https://msdn.microsoft.com/library/2dac83a9-684e-4d0f-b50e-ff722a8bb876). Estas funciones permiten opciones que se utilizarán como una colección de cero o un elemento. Para obtener más información y ejemplos, vea la explicación de las funciones de colección en [muestra](lists.md).


## <a name="converting-to-other-types"></a>Convertir en otros tipos
Opciones se pueden convertir en listas o matrices. Cuando se convierte una opción en cualquiera de estas estructuras de datos, la estructura de datos resultante tiene cero o un elemento. Para convertir una opción en una matriz, use [ `Option.toArray` ](https://msdn.microsoft.com/library/c8044873-ba17-4b52-8231-eb1a28318c64). Para convertir una opción en una lista, utilice [ `Option.toList` ](https://msdn.microsoft.com/library/5f1af295-9fa9-40ad-b4a1-3578d94d44e1).


## <a name="see-also"></a>Vea también
[Referencia del lenguaje F#](index.md)

[Tipos en F#](fsharp-types.md)
