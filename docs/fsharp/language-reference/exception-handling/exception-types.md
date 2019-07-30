---
title: Tipos de excepción
description: Obtenga información sobre cómo definir y F# usar tipos de excepción.
ms.date: 05/16/2016
ms.openlocfilehash: 8545fab50ff6338d1f1621710a838a200f9ac705
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630316"
---
# <a name="exception-types"></a>Tipos de excepción

Existen dos categorías de excepciones en: F#los tipos de excepción de F# .net y los tipos de excepción. En este tema se describe cómo definir y F# usar tipos de excepciones.

## <a name="syntax"></a>Sintaxis

```fsharp
exception exception-type of argument-type
```

## <a name="remarks"></a>Comentarios

En la sintaxis anterior, *Exception-Type* es el nombre de un nuevo F# tipo de excepción y *argument-Type* representa el tipo de un argumento que se puede proporcionar cuando se produce una excepción de este tipo. Puede especificar varios argumentos mediante un tipo de tupla para *el tipo de argumento*.

Una definición típica para una F# excepción es similar a la siguiente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5501.fs)]

Puede generar una excepción de este tipo mediante la `raise` función, como se indica a continuación.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5502.fs)]

Puede usar un F# tipo de excepción directamente en los filtros de una `try...with` expresión, como se muestra en el ejemplo siguiente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5503.fs)]

El tipo de excepción que se define con `exception` la palabra F# clave en es un nuevo tipo que hereda `System.Exception`de.

## <a name="see-also"></a>Vea también

- [Control de excepciones](index.md)
- [Exceptions: the `raise` Function](the-raise-function.md) (Excepciones: la función `raise`)
- [Jerarquía de excepciones](https://msdn.microsoft.com/library/z4c5tckx.aspx)
