---
title: "Tipos de excepción (F#)"
description: "Obtenga información acerca de cómo definir y utilizar tipos de excepción de F #."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: e850205a-b8da-459e-8f6d-cb3510f8f173
ms.openlocfilehash: a0864218841396c0ebdf26c7585e0e5bb778f83e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
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
