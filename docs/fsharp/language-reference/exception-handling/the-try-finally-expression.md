---
title: 'Excepciones: la expresión try...finally (F#)'
description: "Obtenga información acerca de cómo la F # ' try... finally' expresión le permite ejecutar código de limpieza aunque un bloque de código produce una excepción."
ms.date: 05/16/2016
ms.openlocfilehash: a5fdec7b3986fc9a85c34b08d20dc31947c92b2e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="exceptions-the-tryfinally-expression"></a>Excepciones: expresión try...finally

El `try...finally` expresión le permite ejecutar código de limpieza aunque un bloque de código produce una excepción.


## <a name="syntax"></a>Sintaxis

```fsharp
try
    expression1
finally
    expression2
```

## <a name="remarks"></a>Comentarios
El `try...finally` expresión puede utilizarse para ejecutar el código en *expression2* en la sintaxis anterior, independientemente de si se genera una excepción durante la ejecución de *expression1*.

El tipo de *expression2* no contribuyen al valor de la expresión completa; el tipo devuelto cuando no se produce una excepción es el último valor en *expression1*. Cuando se produce una excepción, se devuelve ningún valor y el flujo de control se transfiere al siguiente controlador de excepción coincidente por la pila de llamadas. Si no se encuentra ningún controlador de excepción, el programa se cierra. Antes de que se ejecuta el código en un controlador coincidente o el programa finaliza, el código en el `finally` se ejecuta la bifurcación.

El código siguiente muestra el uso de la `try...finally` expresión.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5701.fs)]

La salida en la consola es como sigue.

```
Closing stream
Exception handled.
```

Como puede ver desde la salida, la secuencia se cerró antes de que se controló la excepción exterior y el archivo `test.txt` contiene el texto `test1`, lo que indica que los búferes se vacían y escritos en el disco, aunque se transfiere de la excepción el control a controlador de excepciones exterior.

Tenga en cuenta que la `try...with` es una construcción independiente de la `try...finally` construir. Por lo tanto, si el código requiere tanto un `with` bloque y un `finally` bloque, se deben anidar las dos construcciones, como en el ejemplo de código siguiente.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5702.fs)]

En el contexto de las expresiones de cálculo, incluyendo expresiones de secuencia y flujos de trabajo asincrónicos, **try... finally** las expresiones pueden tener una implementación personalizada. Para obtener más información, consulte [expresiones de cálculo](../computation-expressions.md).


## <a name="see-also"></a>Vea también
[Control de excepciones](index.md)

[Exceptions: The `try...with` Expression](the-try-with-expression.md) (Excepciones: la expresión `try...with`)
