---
title: Tipos flexibles (F#)
description: "Obtenga información acerca de cómo usar F # anotación de tipo flexible, lo que indica que un parámetro, una variable o un valor tiene un tipo que sea compatible con un tipo especificado."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: c8b510f2-3405-4cc9-b55b-e47b35e2b15b
ms.openlocfilehash: 7c5e4eb97791b9c6c56fe2847755866e8240e038
ms.sourcegitcommit: a19548e5167cbe7e9e58df4ffd8c3b23f17d5c7a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2017
---
# <a name="flexible-types"></a>Tipos flexibles

A *anotación de tipo flexible* indica que un parámetro, una variable o un valor tiene un tipo que sea compatible con un tipo especificado, donde se determina la compatibilidad por posición en una jerarquía orientada a objetos de clases o interfaces. Tipos flexibles resultan útiles específicamente cuando no se produce la conversión automática a los tipos más arriba en la jerarquía de tipos, pero desea habilitar la funcionalidad para trabajar con cualquier tipo de la jerarquía o cualquier tipo que implementa una interfaz.

## <a name="syntax"></a>Sintaxis

```fsharp
#type
```

## <a name="remarks"></a>Comentarios

En la sintaxis anterior, *tipo* representa un tipo base o una interfaz.

Un tipo flexible equivale a un tipo genérico que tiene una restricción que limita los tipos permitidos a los tipos que son compatibles con el tipo base o interfaz. Es decir, las dos líneas de código siguientes son equivalentes.

```fsharp
#SomeType

'T when 'T :> SomeType
```

Tipos flexibles son útiles en varios tipos de situaciones. Por ejemplo, si tiene una función de orden superior (es decir, una función que toma una función como argumento), suele ser útil para que la función devuelva un tipo flexible. En el ejemplo siguiente, el uso de un tipo flexible con un argumento de secuencia en `iterate2` permite que la función de orden superior trabajar con funciones que generan secuencias, matrices, listas y cualquier otro tipo enumerable.

Tenga en cuenta las siguientes funciones de dos, uno de los que devuelve una secuencia, el otro de los cuales devuelve un tipo flexible.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4101.fs)]

Como otro ejemplo, considere la [Seq.concat](https://msdn.microsoft.com/library/2eeb69a9-fc2f-4b7d-8dee-101fa2b00712) función de biblioteca:

```fsharp
val concat: sequences:seq<#seq<'T>> -> seq<'T>
```

Puede pasar cualquiera de las secuencias enumerables siguientes a esta función:

- Una lista de listas
- Una lista de matrices
- Una matriz de listas
- Una matriz de secuencias
- Cualquier otra combinación de secuencias enumerables

El siguiente código utiliza `Seq.concat` para mostrar los escenarios que se pueden admitir mediante el uso de tipos flexibles.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4102.fs)]

La salida es la siguiente.

```
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
```

En F #, como en otros lenguajes orientados a objetos, hay contextos en los que los tipos derivados o tipos que implementan interfaces se convierten automáticamente en un tipo base o interfaz. Estas conversiones automáticas se producen en argumentos directos, pero no cuando el tipo está en una posición subordinada, como parte de un tipo más complejo, como un tipo de valor devuelto de un tipo de función, o como un argumento de tipo. Por lo tanto, la notación de tipo flexible es especialmente útil cuando el tipo que aplica a es parte de un tipo más complejo.

## <a name="see-also"></a>Vea también

[Referencia del lenguaje F#](index.md)

[Genéricos](generics/index.md)
