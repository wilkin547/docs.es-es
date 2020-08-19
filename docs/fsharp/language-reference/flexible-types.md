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
# <a name="flexible-types"></a>Tipos flexibles

Una *anotación de tipo flexible* indica que un parámetro, una variable o un valor tiene un tipo que es compatible con un tipo especificado, donde la compatibilidad se determina por posición en una jerarquía orientada a objetos de clases o interfaces. Los tipos flexibles son especialmente útiles cuando la conversión automática en tipos situados más arriba en la jerarquía de tipos no se produce, pero aún desea habilitar la funcionalidad para trabajar con cualquier tipo de la jerarquía o con cualquier tipo que implemente una interfaz.

## <a name="syntax"></a>Sintaxis

```fsharp
#type
```

## <a name="remarks"></a>Comentarios

En la sintaxis anterior, *Type* representa un tipo base o una interfaz.

Un tipo flexible es equivalente a un tipo genérico que tiene una restricción que limita los tipos permitidos a tipos que son compatibles con la base o el tipo de interfaz. Es decir, las dos líneas de código siguientes son equivalentes.

```fsharp
#SomeType

'T when 'T :> SomeType
```

Los tipos flexibles son útiles en varios tipos de situaciones. Por ejemplo, si tiene una función de orden superior (una función que toma una función como argumento), a menudo resulta útil que la función devuelva un tipo flexible. En el ejemplo siguiente, el uso de un tipo flexible con un argumento de secuencia en `iterate2` permite que la función de orden superior funcione con funciones que generan secuencias, matrices, listas y cualquier otro tipo Enumerable.

Tenga en cuenta las dos funciones siguientes, una de las cuales devuelve una secuencia, la otra devuelve un tipo flexible.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4101.fs)]

Como otro ejemplo, considere la función de biblioteca [Seq. concat](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#concat) :

```fsharp
val concat: sequences:seq<#seq<'T>> -> seq<'T>
```

Puede pasar cualquiera de las secuencias enumerables siguientes a esta función:

- Una lista de listas
- Una lista de matrices
- Una matriz de listas
- Una matriz de secuencias
- Cualquier otra combinación de secuencias enumerables

En el código siguiente se usa `Seq.concat` para mostrar los escenarios que se pueden admitir mediante el uso de tipos flexibles.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4102.fs)]

La salida es la siguiente.

```console
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
```

En F #, como en otros lenguajes orientados a objetos, hay contextos en los que los tipos derivados o tipos que implementan interfaces se convierten automáticamente en un tipo base o de interfaz. Estas conversiones automáticas se producen en argumentos directos, pero no cuando el tipo está en una posición subordinada, como parte de un tipo más complejo, como un tipo de valor devuelto de un tipo de función, o como un argumento de tipo. Por lo tanto, la notación de tipos flexibles es principalmente útil cuando el tipo al que se aplica es parte de un tipo más complejo.

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
- [Genéricos](./generics/index.md)
