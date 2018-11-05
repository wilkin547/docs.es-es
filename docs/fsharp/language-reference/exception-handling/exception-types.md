---
title: Tipos de excepción (F#)
description: Obtenga información sobre cómo definir y usar los tipos de excepción de F#.
ms.date: 05/16/2016
ms.openlocfilehash: b8d648a3649153a3604856deb61ce41db8c40bf2
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2018
ms.locfileid: "43858826"
---
# <a name="exception-types"></a>Tipos de excepción

Existen dos categorías de excepciones en F#: tipos de excepción de .NET y los tipos de excepción de F#. Este tema describe cómo definir y usar los tipos de excepción de F#.

## <a name="syntax"></a>Sintaxis

```fsharp
exception exception-type of argument-type
```

## <a name="remarks"></a>Comentarios

En la sintaxis anterior, *tipo de excepción* es el nombre de un nuevo tipo F# excepción, y *tipos de argumento* representa el tipo de argumento que se puede proporcionar al generar una excepción de este tipo. Puede especificar varios argumentos utilizando un tipo de tupla para *tipos de argumento*.

Una definición típica para una excepción de F# es similar al siguiente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5501.fs)]

Puede generar una excepción de este tipo mediante el `raise` funcione, como se indica a continuación.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5502.fs)]

Puede usar un tipo de excepción de F# directamente en los filtros de un `try...with` expresión, tal como se muestra en el ejemplo siguiente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5503.fs)]

El tipo de excepción que se define con la `exception` palabra clave en F# es un nuevo tipo que hereda de `System.Exception`.

## <a name="see-also"></a>Vea también

- [Control de excepciones](index.md)
- [Exceptions: the `raise` Function](the-raise-function.md) (Excepciones: la función `raise`)
- [Jerarquía de excepciones](https://msdn.microsoft.com/library/z4c5tckx.aspx)
