---
title: 'Excepciones: Expresión failwith'
description: Obtenga información sobre cómo la función ' failwith ' F# genera una excepción.
ms.date: 05/16/2016
ms.openlocfilehash: f2c86362d5bdde7bab55751f019965a5f4ca6236
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630329"
---
# <a name="exceptions-the-failwith-function"></a>Excepciones: Expresión failwith

La `failwith` función genera una F# excepción.

## <a name="syntax"></a>Sintaxis

```fsharp
failwith error-message-string
```

## <a name="remarks"></a>Comentarios

La *cadena de mensaje de error* en la sintaxis anterior es una cadena literal o un valor de tipo `string`. Se convierte en `Message` la propiedad de la excepción.

La `failwith` excepción generada por es una `System.Exception` excepción, que es una referencia que tiene el nombre `Failure` en F# el código. En el código siguiente se muestra el uso `failwith` de para producir una excepción.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6001.fs)]

## <a name="see-also"></a>Vea también

- [Control de excepciones](index.md)
- [Tipos de excepción](exception-types.md)
- [Excepciones: La `try...with` expresión](the-try-with-expression.md)
- [Excepciones: La `try...finally` expresión](the-try-finally-expression.md)
- [Exceptions: the `raise` Function](the-raise-function.md) (Excepciones: la función `raise`)
