---
title: 'Excepciones: Función invalidArg'
description: Obtenga información sobre F# cómo la función ' invalidArg ' genera una excepción de argumento.
ms.date: 05/16/2016
ms.openlocfilehash: 6b1c5fdb5a541da336977d3a67d471302edb36b6
ms.sourcegitcommit: a2d0e1f66367367065bc8dc0dde488ab536da73f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2019
ms.locfileid: "71083010"
---
# <a name="exceptions-the-invalidarg-function"></a>Excepciones: Función invalidArg

La `invalidArg` función genera una excepción de argumento.

## <a name="syntax"></a>Sintaxis

```fsharp
invalidArg parameter-name error-message-string
```

## <a name="remarks"></a>Comentarios

El parámetro-name de la sintaxis anterior es una cadena con el nombre del parámetro cuyo argumento no era válido. La *cadena de mensaje de error* es una cadena literal o un valor de tipo `string`. Se convierte en `Message` la propiedad del objeto de excepción.

La excepción generada `invalidArg` por es `System.ArgumentException` una excepción. En el código siguiente se muestra el uso `invalidArg` de para producir una excepción.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6101.fs)]

El resultado es el siguiente, seguido de un seguimiento de la pila (no se muestra).

```console
December
January
System.ArgumentException: Month parameter out of range.
```

## <a name="see-also"></a>Vea también

- [Control de excepciones](index.md)
- [Tipos de excepción](exception-types.md)
- [Excepciones: La `try...with` expresión](the-try-with-expression.md)
- [Excepciones: La `try...finally` expresión](the-try-finally-expression.md)
- [Exceptions: the `raise` Function](the-raise-function.md) (Excepciones: la función `raise`)
- [Excepciones: La `failwith` función](the-failwith-function.md)
