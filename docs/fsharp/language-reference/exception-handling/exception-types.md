---
title: Tipos de excepción (F#)
description: 'Obtenga información acerca de cómo definir y utilizar tipos de excepción de F #.'
ms.date: 05/16/2016
ms.openlocfilehash: 4462dd00ddf9524d1fd376ee1e73e81fcfd5d945
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564043"
---
# <a name="exception-types"></a>Tipos de excepción

Existen dos categorías de excepciones en F #: tipos de excepción de .NET y los tipos de excepción de F #. En este tema se describe cómo definir y utilizar tipos de excepción de F #.


## <a name="syntax"></a>Sintaxis

```fsharp
exception exception-type of argument-type
```

## <a name="remarks"></a>Comentarios
En la sintaxis anterior, *tipo de excepción* es el nombre de un nuevo tipo F # excepción, y *tipos de argumento* representa el tipo de argumento que se pueden proporcionar cuando se inicia una excepción de este tipo. Puede especificar varios argumentos utilizando un tipo de tupla para *tipos de argumento*.

Una definición típica para una excepción de F # es similar al siguiente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5501.fs)]

También puede generar una excepción de este tipo mediante el `raise` funcione, como se indica a continuación.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5502.fs)]

Puede usar un tipo de excepción de F # directamente en los filtros de un `try...with` expresión, tal como se muestra en el ejemplo siguiente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5503.fs)]

El tipo de excepción que se define con el `exception` palabra clave en F # es un nuevo tipo que hereda de `System.Exception`.


## <a name="see-also"></a>Vea también
[Control de excepciones](index.md)

[Exceptions: the `raise` Function](the-raise-function.md) (Excepciones: la función `raise`)

[Jerarquía de excepciones](https://msdn.microsoft.com/library/z4c5tckx.aspx)
