---
title: Tipos de excepción
description: Obtenga información sobre cómo definir y usar F# tipos de excepción.
ms.date: 05/16/2016
ms.openlocfilehash: ed721dd0dc46a486fafeac2fa4c096800995ccb7
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2018
ms.locfileid: "53612834"
---
# <a name="exception-types"></a>Tipos de excepción

Existen dos categorías de excepciones en F#: tipos de excepción de .NET y F# tipos de excepción. Este tema describe cómo definir y usar F# tipos de excepción.

## <a name="syntax"></a>Sintaxis

```fsharp
exception exception-type of argument-type
```

## <a name="remarks"></a>Comentarios

En la sintaxis anterior, *tipo de excepción* es el nombre de un nuevo F# tipo de excepción, y *tipos de argumento* representa el tipo de argumento que se puede proporcionar al generar una excepción de este tipo. Puede especificar varios argumentos utilizando un tipo de tupla para *tipos de argumento*.

Una definición típica para un F# excepción es similar al siguiente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5501.fs)]

Puede generar una excepción de este tipo mediante el `raise` funcione, como se indica a continuación.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5502.fs)]

Puede usar un F# tipo de excepción directamente en los filtros en un `try...with` expresión, tal como se muestra en el ejemplo siguiente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5503.fs)]

El tipo de excepción que se define con la `exception` palabra clave en F# es un nuevo tipo que hereda de `System.Exception`.

## <a name="see-also"></a>Vea también

- [Control de excepciones](index.md)
- [Exceptions: the `raise` Function](the-raise-function.md) (Excepciones: la función `raise`)
- [Jerarquía de excepciones](https://msdn.microsoft.com/library/z4c5tckx.aspx)