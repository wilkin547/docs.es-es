---
title: 'Excepciones: Función invalidArg'
description: Obtenga información sobre cómo el F# 'invalidArg' función genera una excepción de argumento.
ms.date: 05/16/2016
ms.openlocfilehash: 1f0cbc9b7e805822544d6d54bc1fc69adf82967a
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645493"
---
# <a name="exceptions-the-invalidarg-function"></a>Excepciones: Función invalidArg

El `invalidArg` función genera una excepción de argumento.

## <a name="syntax"></a>Sintaxis

```fsharp
invalidArg parameter-name error-message-string
```

## <a name="remarks"></a>Comentarios

El nombre del parámetro en la sintaxis anterior es una cadena con el nombre del parámetro cuyo argumento no era válido. El *cadena de mensaje de error* es una cadena literal o un valor de tipo `string`. Se convierte en el `Message` propiedad del objeto de excepción.

La excepción generada por `invalidArg` es un `System.ArgumentException` excepción. El código siguiente muestra el uso de `invalidArg` para producir una excepción.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet6101.fs)]

El resultado es el siguiente, seguido de un seguimiento de pila (no mostrado).

```
December
January
System.ArgumentException: Month parameter out of range.
```

## <a name="see-also"></a>Vea también

- [Control de excepciones](index.md)
- [Tipos de excepción](exception-types.md)
- [Excepciones: El `try...with` expresión](the-try-with-expression.md)
- [Excepciones: El `try...finally` expresión](the-try-finally-expression.md)
- [Exceptions: the `raise` Function](the-raise-function.md) (Excepciones: la función `raise`)
- [Excepciones: El `failwith` (función)](the-failwith-function.md)
