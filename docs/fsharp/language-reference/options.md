---
title: Opciones
description: Obtenga información sobre cómo F# usar los tipos de opciones cuando puede que no exista un valor real para una variable o un valor con nombre.
ms.date: 05/16/2016
ms.openlocfilehash: 9326cf04f53adac7422c09a49a59c4eecd49486d
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627351"
---
# <a name="options"></a>Opciones

El tipo de opción F# en se utiliza cuando es posible que no exista un valor real para una variable o valor con nombre. Una opción tiene un tipo subyacente y puede contener un valor de ese tipo, o puede que no tenga un valor.

## <a name="remarks"></a>Comentarios

En el código siguiente se muestra una función que genera un tipo de opción.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1404.fs)]

Como puede ver, si la entrada `a` es mayor que 0, `Some(a)` se genera.  De lo `None` contrario, se genera.

El valor `None` se utiliza cuando una opción no tiene un valor real. De lo contrario, `Some( ... )` la expresión proporciona a la opción un valor. Los valores `Some` y `None` son útiles en la coincidencia de patrones, como en la `exists`función siguiente, `true` que devuelve si la opción tiene un `false` valor y si no lo hace.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1401.fs)]

## <a name="using-options"></a>Usar opciones

Las opciones se usan normalmente cuando una búsqueda no devuelve un resultado de coincidencia, como se muestra en el código siguiente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1403.fs)]

En el código anterior, se busca una lista de forma recursiva. La función `tryFindMatch` toma una función `pred` de predicado que devuelve un valor booleano y una lista que se va a buscar. Si se encuentra un elemento que satisface el predicado, la recursividad finaliza y la función devuelve el valor como una opción en la `Some(head)`expresión. La recursividad finaliza cuando se encuentra una coincidencia con la lista vacía. En ese momento, no `head` se ha encontrado el valor y `None` se devuelve.

Muchas F# funciones de la biblioteca que buscan en una colección un valor que puede o no existir devuelven el `option` tipo. Por Convención, estas funciones comienzan con el `try` prefijo, por ejemplo [`Seq.tryFindIndex`](https://msdn.microsoft.com/library/c357b221-edf6-4f68-bf40-82a3156d945a),.

Las opciones también pueden ser útiles cuando es posible que un valor no exista, por ejemplo, si es posible que se produzca una excepción al intentar construir un valor. En el siguiente ejemplo código se muestra cómo hacerlo.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1402.fs)]

La `openFile` función del ejemplo anterior tiene el tipo `string -> File option` porque devuelve un `File` objeto si el archivo se abre correctamente y `None` si se produce una excepción. Dependiendo de la situación, puede que no sea una opción de diseño adecuada para detectar una excepción en lugar de permitir que se propague.

Además, sigue siendo posible pasar `null` o un valor que sea NULL a las `Some` mayúsculas y minúsculas de una opción. Por lo general, esto se evita y, normalmente, está F# en programación rutinaria, pero es posible debido a la naturaleza de los tipos de referencia en .net.

## <a name="option-properties-and-methods"></a>Propiedades y métodos de la opción

El tipo de opción admite las siguientes propiedades y métodos.

|Propiedad o método|Type|DESCRIPCIÓN|
|------------------|----|-----------|
|[None](https://msdn.microsoft.com/library/83ef260a-aa33-4e6f-aee6-b9bf0a461476)|`'T option`|Propiedad estática que permite crear un valor de opción que tiene el `None` valor.|
|[Isnone (](https://msdn.microsoft.com/library/f08532ca-1716-4f60-ae59-8ef6256df234)|`bool`|Devuelve `true` si la opción tiene el `None` valor.|
|[IsSome](https://msdn.microsoft.com/library/c5088d51-c5d7-425f-a77f-12c379bb356f)|`bool`|Devuelve `true` si la opción tiene un valor que no `None`es.|
|[Existen](https://msdn.microsoft.com/library/12f048d2-e293-4596-accb-de036ecd63fc)|`'T option`|Miembro estático que crea una opción que tiene un valor que no `None`es.|
|[Valor](https://msdn.microsoft.com/library/c79f68e8-11fd-45b1-a053-e8fc38b56df7)|`'T`|Devuelve el valor subyacente o produce una `System.NullReferenceException` excepción si el valor de es. `None`|

## <a name="option-module"></a>Módulo de opción

Hay un módulo, [opción](https://msdn.microsoft.com/library/e615e4d3-bbbb-49ba-addc-6061ea2e2f4c), que contiene funciones útiles que realizan operaciones en las opciones. Algunas funciones repiten la funcionalidad de las propiedades pero son útiles en contextos en los que se necesita una función. [Option. IsSome (](https://msdn.microsoft.com/library/41ad0857-5672-4326-84b5-c33dc43dcf79) y [Option. isnone (](https://msdn.microsoft.com/library/73db6a53-15e7-40a6-94f9-a0049e5f4819) son dos funciones de módulo que prueban si una opción contiene un valor. [Option. Get](https://msdn.microsoft.com/library/803e9fcb-6edd-4910-808c-25f08cbc55ea) obtiene el valor, si lo hay. Si no hay ningún valor, se produce una `System.ArgumentException`excepción.

La función [Option. bind](https://msdn.microsoft.com/library/c3406192-24ac-49b5-bc3b-8f805187f1c0) ejecuta una función en el valor, si hay un valor. La función debe tomar exactamente un argumento y su tipo de parámetro debe ser el tipo de opción. El valor devuelto de la función es otro tipo de opción.

El módulo de opciones también incluye funciones que corresponden a las funciones que están disponibles para las listas, matrices, secuencias y otros tipos de colección. Estas funciones incluyen [`Option.map`](https://msdn.microsoft.com/library/91a20385-7e73-40c2-9adc-635e86d6a622), [`Option.iter`](https://msdn.microsoft.com/library/83389eef-3dff-4074-b4cc-f69581c25191), [`Option.forall`](https://msdn.microsoft.com/library/ba884586-5eae-49c5-9e36-05481c1c3428), [`Option.exists`](https://msdn.microsoft.com/library/a606d2d4-fddc-4eab-ab37-c6138fb7ad99), [,`Option.foldBack`](https://msdn.microsoft.com/library/a882fbaf-c019-46f0-b4f5-b8c2b8b90ffb) [y`Option.count`](https://msdn.microsoft.com/library/2dac83a9-684e-4d0f-b50e-ff722a8bb876). [`Option.fold`](https://msdn.microsoft.com/library/af896794-3d53-406c-9411-316cd5c33ad8) Estas funciones permiten usar opciones como una colección de cero o un elemento. Para obtener más información y ejemplos, vea la explicación de las funciones de colección en [las listas](lists.md).

## <a name="converting-to-other-types"></a>Convertir a otros tipos

Las opciones se pueden convertir en listas o matrices. Cuando una opción se convierte en cualquiera de estas estructuras de datos, la estructura de datos resultante tiene cero o un elemento. Para convertir una opción en una matriz, use [`Option.toArray`](https://msdn.microsoft.com/library/c8044873-ba17-4b52-8231-eb1a28318c64). Para convertir una opción en una lista, use [`Option.toList`](https://msdn.microsoft.com/library/5f1af295-9fa9-40ad-b4a1-3578d94d44e1).

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
- [Tipos en F#](fsharp-types.md)
