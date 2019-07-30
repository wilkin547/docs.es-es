---
title: 'Expresiones lambda: Palabra clave Fun'
description: Obtenga información sobre cómo usar F# la palabra clave "Fun" para definir una expresión lambda, que es una función anónima.
ms.date: 05/16/2016
ms.openlocfilehash: 9818724686dd83a7e352fb36819289fa19b002df
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630665"
---
# <a name="lambda-expressions-the-fun-keyword-f"></a>Expresiones lambda: Palabra clave Fun (F#)

La `fun` palabra clave se usa para definir una expresión lambda, es decir, una función anónima.

## <a name="syntax"></a>Sintaxis

```fsharp
fun parameter-list -> expression
```

## <a name="remarks"></a>Comentarios

La *lista de parámetros* consta normalmente de nombres y, opcionalmente, tipos de parámetros. En general, la *lista de parámetros* puede estar formada por F# patrones. Para obtener una lista completa de los posibles patrones, consulte [coincidencia](../pattern-matching.md)de patrones. Entre las listas de parámetros válidos se incluyen los ejemplos siguientes.

```fsharp
// Lambda expressions with parameter lists.
fun a b c -> ...
fun (a: int) b c -> ...
fun (a : int) (b : string) (c:float) -> ...

// A lambda expression with a tuple pattern.
fun (a, b) -> …

// A lambda expression with a list pattern.
fun head :: tail -> …
```

La *expresión* es el cuerpo de la función, la última expresión de la que genera un valor devuelto. Entre los ejemplos de expresiones lambda válidas se incluyen los siguientes:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet301.fs)]

## <a name="using-lambda-expressions"></a>Uso de expresiones lambda

Las expresiones lambda son especialmente útiles cuando se desea realizar operaciones en una lista o en otra colección y se desea evitar el trabajo adicional de definir una función. Muchas F# funciones de la biblioteca toman los valores de función como argumentos y puede ser especialmente conveniente usar una expresión lambda en esos casos. En el código siguiente se aplica una expresión lambda a los elementos de una lista. En este caso, la función anónima agrega 1 a todos los elementos de una lista.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet302.fs)]

## <a name="see-also"></a>Vea también

- [Funciones](index.md)
