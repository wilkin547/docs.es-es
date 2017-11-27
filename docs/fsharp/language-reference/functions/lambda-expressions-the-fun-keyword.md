---
title: 'Expresiones lambda: la palabra clave fun (F#)'
description: "Obtenga información acerca de cómo utilizar la palabra clave 'fun' de F # para definir una expresión lambda, que es una función anónima."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: e5d3565c-d7cc-433f-a619-886ed92523a7
ms.openlocfilehash: 09f1c1787bbb4b86ec40f9e973e08104919631aa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="lambda-expressions-the-fun-keyword-f"></a>Expresiones lambda: la palabra clave fun (F#)

El `fun` palabra clave se utiliza para definir una expresión lambda, es decir, una función anónima.


## <a name="syntax"></a>Sintaxis

```fsharp
fun parameter-list -> expression
```

## <a name="remarks"></a>Comentarios
El *lista de parámetros* normalmente consta de nombres y, opcionalmente, tipos de parámetros. Por lo general, el *lista de parámetros* puede estar formada por cualquier patrón de F #. Para obtener una lista completa de los modelos posibles, consulte [coincidencia de patrones](../pattern-matching.md). Las listas de parámetros válidos incluyen los siguientes ejemplos.

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

El *expresión* es el cuerpo de la función, la última expresión que genera un valor devuelto. A continuación se indican algunos ejemplos de expresiones lambda válidas:

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet301.fs)]
    
## <a name="using-lambda-expressions"></a>Uso de expresiones lambda
Las expresiones lambda son especialmente útiles cuando desea realizar operaciones en una lista o en otra colección y desea ahorrarse el trabajo de la definición de una función. Muchas funciones de biblioteca de F # toman valores de las funciones como argumentos, y puede ser especialmente útil usar una expresión lambda en esos casos. El código siguiente aplica una expresión lambda a los elementos de una lista. En este caso, la función anónima suma 1 a cada elemento de una lista.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet302.fs)]
    
## <a name="see-also"></a>Vea también
[Funciones](index.md)
