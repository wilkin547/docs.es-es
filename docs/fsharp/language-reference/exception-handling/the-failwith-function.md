---
title: 'Excepciones: función failwith (F#)'
description: Obtenga información sobre cómo la función 'failwith' genera una excepción de F#.
ms.date: 05/16/2016
ms.openlocfilehash: 69a2eb69e0157d3bde8cb8884cb0ae960634dddc
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2018
ms.locfileid: "43863434"
---
# <a name="exceptions-the-failwith-function"></a>Excepciones: función failwith

El `failwith` función genera una excepción de F#.

## <a name="syntax"></a>Sintaxis

```fsharp
failwith error-message-string
```

## <a name="remarks"></a>Comentarios

El *cadena de mensaje de error* en la sintaxis anterior es una cadena literal o un valor de tipo `string`. Se convierte en el `Message` propiedad de la excepción.

La excepción generada por `failwith` es un `System.Exception` excepción, que es una referencia que tiene el nombre `Failure` en código de F#. El código siguiente muestra el uso de `failwith` para producir una excepción.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet6001.fs)]

## <a name="see-also"></a>Vea también

- [Control de excepciones](index.md)
- [Tipos de excepción](exception-types.md)
- [Exceptions: The `try...with` Expression](the-try-with-expression.md) (Excepciones: la expresión `try...with`)
- [Exceptions: The `try...finally` Expression](the-try-finally-expression.md) (Excepciones: la expresión `try...finally`)
- [Exceptions: the `raise` Function](the-raise-function.md) (Excepciones: la función `raise`)
