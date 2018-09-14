---
title: Tipos flexibles (F#)
description: 'Obtenga información sobre cómo usar F # anotación de tipo flexible, que indica que un parámetro, una variable o un valor tiene un tipo que es compatible con un tipo especificado.'
ms.date: 05/16/2016
ms.openlocfilehash: b6c97c3cc19f15b2c8db74b2c55660a16b2858f7
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2018
ms.locfileid: "45568818"
---
# <a name="flexible-types"></a>Tipos flexibles

Un *anotación de tipo flexible* indica que un parámetro, una variable o un valor tiene un tipo que es compatible con un tipo especificado, donde compatibilidad viene determinada por la posición en una jerarquía orientada a objetos de clases o interfaces. Tipos flexibles son útiles en concreto cuando no se produce la conversión automática a tipos más arriba en la jerarquía de tipos, pero desea habilitar la funcionalidad para trabajar con cualquier tipo de la jerarquía o cualquier tipo que implementa una interfaz.

## <a name="syntax"></a>Sintaxis

```fsharp
#type
```

## <a name="remarks"></a>Comentarios

En la sintaxis anterior, *tipo* representa un tipo base o una interfaz.

Un tipo flexible es equivalente a un tipo genérico que tiene una restricción que limita los tipos permitidos para los tipos que son compatibles con el tipo base o interfaz. Es decir, las dos líneas de código siguientes son equivalentes.

```fsharp
#SomeType

'T when 'T :> SomeType
```

Tipos flexibles son útiles en varios tipos de situaciones. Por ejemplo, si tiene una función de orden superior (es decir, una función que toma una función como argumento), a menudo es útil para que la función devuelva un tipo flexible. En el ejemplo siguiente, el uso de un tipo flexible con un argumento sequence en `iterate2` permite que la función de orden superior trabajar con funciones que generan secuencias, matrices, listas y cualquier otro tipo enumerable.

Tenga en cuenta las siguientes dos funciones, uno de los que devuelve una secuencia, el otro devuelve un tipo flexible.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4101.fs)]

Como otro ejemplo, considere la [Seq.concat](https://msdn.microsoft.com/library/2eeb69a9-fc2f-4b7d-8dee-101fa2b00712) función de biblioteca:

```fsharp
val concat: sequences:seq<#seq<'T>> -> seq<'T>
```

Puede pasar cualquiera de las siguientes secuencias enumerables a esta función:

- Una lista de listas
- Una lista de matrices
- Una matriz de listas
- Una matriz de secuencias
- Cualquier otra combinación de secuencias enumerables

El siguiente código utiliza `Seq.concat` para demostrar los escenarios que se pueden admitir mediante el uso de tipos flexibles.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4102.fs)]

La salida es la siguiente.

```
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
```

En F #, como en otros lenguajes orientados a objetos, hay contextos en los que los tipos derivados o tipos que implementan interfaces se convierten automáticamente en un tipo base o interfaz. Estas conversiones automáticas se producen en argumentos directos, pero no cuando el tipo está en una posición subordinada, como parte de un tipo más complejo, como un tipo de valor devuelto de un tipo de función, o como un argumento de tipo. Por lo tanto, la notación de tipo flexible es especialmente útil cuando el tipo que aplica a forma parte de un tipo más complejo.

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
- [Genéricos](generics/index.md)
