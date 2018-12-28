---
title: 'Excepciones: función raise'
description: Obtenga información sobre cómo el F# 'raise' función se utiliza para indicar que se ha producido un error o una condición excepcional.
ms.date: 05/16/2016
ms.openlocfilehash: 87773ead7773c62a325c7e7ff105c729e10dd69c
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2018
ms.locfileid: "53610156"
---
# <a name="exceptions-the-raise-function"></a>Excepciones: función raise

El `raise` función se utiliza para indicar que se ha producido un error o una condición excepcional. Información sobre el error se captura en un objeto de excepción.

## <a name="syntax"></a>Sintaxis

```fsharp
raise (expression)
```

## <a name="remarks"></a>Comentarios

El `raise` función genera un objeto de excepción e inicia una proceso de desenredo de pila. El proceso de desenredo de pila es administrado por common language runtime (CLR), por lo que el comportamiento de este proceso es el mismo, como en cualquier otro lenguaje. NET. El proceso de desenredo de pila es una búsqueda de un controlador de excepciones que coincida con la excepción generada. La búsqueda comienza en el actual `try...with` expresión, si hay alguno. Cada patrón en el `with` se activa el bloque, en orden. Cuando se encuentra un controlador de excepción coincidente, la excepción se considera controlado; en caso contrario, se desenreda la pila y `with` se comprueban los bloques de la cadena de llamada hasta que se encuentra un controlador coincidente. Cualquier `finally` bloques que se encuentran en la cadena de llamadas también se ejecutan en secuencia desenreda la pila.

El `raise` función es el equivalente de `throw` en C# o C++. Use `reraise` en un controlador catch para propagar la misma excepción de la cadena de llamada.

Ejemplos de código siguientes ilustran el uso de la `raise` función para generar una excepción.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5801.fs)]

El `raise` función también se puede utilizar para generar excepciones de. NET, como se muestra en el ejemplo siguiente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5802.fs)]

## <a name="see-also"></a>Vea también

- [Control de excepciones](index.md)
- [Tipos de excepción](exception-types.md)
- [Excepciones: El `try...with` expresión](the-try-with-expression.md)
- [Excepciones: El `try...finally` expresión](the-try-finally-expression.md)
- [Excepciones: El `failwith` (función)](the-failwith-function.md)
- [Excepciones: El `invalidArg` (función)](the-invalidArg-function.md)