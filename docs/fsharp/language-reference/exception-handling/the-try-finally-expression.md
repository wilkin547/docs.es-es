---
title: 'Excepciones: Expresión try...finally'
description: Obtenga información sobre F# cómo la instrucción "Try... Finalmente, la expresión permite ejecutar código de limpieza incluso si un bloque de código produce una excepción.
ms.date: 05/16/2016
ms.openlocfilehash: 0ddb64ac13b307404864ec5b54f26fd8a7a3d7d8
ms.sourcegitcommit: a2d0e1f66367367065bc8dc0dde488ab536da73f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2019
ms.locfileid: "71083006"
---
# <a name="exceptions-the-tryfinally-expression"></a>Excepciones: Expresión try...finally

La `try...finally` expresión permite ejecutar código de limpieza incluso si un bloque de código produce una excepción.

## <a name="syntax"></a>Sintaxis

```fsharp
try
    expression1
finally
    expression2
```

## <a name="remarks"></a>Comentarios

La `try...finally` expresión se puede utilizar para ejecutar el código de *expresión2* en la sintaxis anterior, independientemente de si se genera una excepción durante la ejecución de *expression1*.

El tipo de *expresión2* no contribuye al valor de la expresión completa; el tipo devuelto cuando una excepción no se produce es el último valor de *expression1*. Cuando se produce una excepción, no se devuelve ningún valor y el flujo de control se transfiere al siguiente controlador de excepción coincidente en la pila de llamadas. Si no se encuentra ningún controlador de excepciones, el programa finaliza. Antes de que se ejecute el código de un controlador coincidente o finalice el programa, se ejecuta el `finally` código de la bifurcación.

En el código siguiente se muestra el uso `try...finally` de la expresión.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5701.fs)]

La salida a la consola es la siguiente.

```console
Closing stream
Exception handled.
```

Como puede ver en la salida, la secuencia se cerró antes de que se administrara la excepción externa y el `test.txt` archivo contiene el `test1`texto, lo que indica que los búferes se vaciaron y escribieron en el disco aunque la excepción se haya transferido. control al controlador de excepciones externo.

Tenga en cuenta `try...with` que la construcción es una construcción independiente `try...finally` de la construcción. Por lo tanto, si el código requiere `with` un bloque y `finally` un bloque, debe anidar las dos construcciones, como en el ejemplo de código siguiente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5702.fs)]

En el contexto de las expresiones de cálculo, incluidas las expresiones de secuencia y los flujos de trabajo asincrónicos, **pruebe... las expresiones Finally** pueden tener una implementación personalizada. Para obtener más información, vea [expresiones de cálculo](../computation-expressions.md).

## <a name="see-also"></a>Vea también

- [Control de excepciones](index.md)
- [Excepciones: La `try...with` expresión](the-try-with-expression.md)
