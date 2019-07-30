---
title: 'Excepciones: función raise'
description: Obtenga información sobre F# cómo se usa la función ' raise ' para indicar que se ha producido un error o una condición excepcional.
ms.date: 05/16/2016
ms.openlocfilehash: e0cc8da8310203c537b8081af8a225671bd8c6a3
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630287"
---
# <a name="exceptions-the-raise-function"></a>Excepciones: función raise

La `raise` función se usa para indicar que se ha producido un error o una condición excepcional. La información sobre el error se captura en un objeto de excepción.

## <a name="syntax"></a>Sintaxis

```fsharp
raise (expression)
```

## <a name="remarks"></a>Comentarios

La `raise` función genera un objeto de excepción e inicia un proceso de desenredado de la pila. El proceso de desenredado de la pila se administra mediante el Common Language Runtime (CLR), por lo que el comportamiento de este proceso es el mismo que en cualquier otro lenguaje de .NET. El proceso de desenredado de la pila es una búsqueda de un controlador de excepciones que coincide con la excepción generada. La búsqueda se inicia en la `try...with` expresión actual, si hay alguna. Cada patrón del `with` bloque se comprueba en orden. Cuando se encuentra un controlador de excepciones coincidente, la excepción se considera controlada; de lo contrario, la pila se desenreda `with` y se bloquea la cadena de llamadas hasta que se encuentra un controlador coincidente. Los `finally` bloques que se encuentran en la cadena de llamadas también se ejecutan en secuencia cuando se desenreda la pila.

La `raise` función es el equivalente de `throw` en C# o C++. Use `reraise` en un controlador catch para propagar la misma excepción hacia arriba en la cadena de llamadas.

En los siguientes ejemplos de código se muestra el `raise` uso de la función para generar una excepción.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5801.fs)]

La `raise` función también se puede utilizar para generar excepciones de .net, tal y como se muestra en el ejemplo siguiente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5802.fs)]

## <a name="see-also"></a>Vea también

- [Control de excepciones](index.md)
- [Tipos de excepción](exception-types.md)
- [Excepciones: La `try...with` expresión](the-try-with-expression.md)
- [Excepciones: La `try...finally` expresión](the-try-finally-expression.md)
- [Excepciones: La `failwith` función](the-failwith-function.md)
- [Excepciones: La `invalidArg` función](the-invalidArg-function.md)
