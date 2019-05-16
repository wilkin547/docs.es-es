---
title: 'Excepciones: Función failwith'
description: Obtenga información sobre cómo la función 'failwith' genera un F# excepción.
ms.date: 05/16/2016
ms.openlocfilehash: 08107966ddc2f55625347deb92d224b286df7761
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641948"
---
# <a name="exceptions-the-failwith-function"></a>Excepciones: Función failwith

El `failwith` función genera una F# excepción.

## <a name="syntax"></a>Sintaxis

```fsharp
failwith error-message-string
```

## <a name="remarks"></a>Comentarios

El *cadena de mensaje de error* en la sintaxis anterior es una cadena literal o un valor de tipo `string`. Se convierte en el `Message` propiedad de la excepción.

La excepción generada por `failwith` es un `System.Exception` excepción, que es una referencia que tiene el nombre `Failure` en F# código. El código siguiente muestra el uso de `failwith` para producir una excepción.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet6001.fs)]

## <a name="see-also"></a>Vea también

- [Control de excepciones](index.md)
- [Tipos de excepción](exception-types.md)
- [Excepciones: El `try...with` expresión](the-try-with-expression.md)
- [Excepciones: El `try...finally` expresión](the-try-finally-expression.md)
- [Exceptions: the `raise` Function](the-raise-function.md) (Excepciones: la función `raise`)
