---
title: 'Funciones recursivas: La palabra clave rec'
description: Obtenga información sobre cómo el F# palabra clave 'rec' se utiliza con la palabra clave 'let' para definir una función recursiva.
ms.date: 05/16/2016
ms.openlocfilehash: 9f9c7e1a4468de9551b3852d0e7b4381025b2699
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941015"
---
# <a name="recursive-functions-the-rec-keyword"></a>Funciones recursivas: La palabra clave rec

El `rec` palabra clave se utiliza junto con el `let` palabra clave para definir una función recursiva.

## <a name="syntax"></a>Sintaxis

```fsharp
// Recursive function:
let rec function-nameparameter-list =
function-body

// Mutually recursive functions:
let rec function1-nameparameter-list =
function1-body
and function2-nameparameter-list =
function2-body
...
```

## <a name="remarks"></a>Comentarios

Funciones recursivas, las funciones que llaman a sí mismos, se identifican explícitamente en el F# lenguaje. Esto hace que el identificador que se está definiendo disponibles en el ámbito de la función.

El código siguiente muestra una función recursiva que calcula el *n*<sup>th</sup> número de Fibonacci.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet4001.fs)]

> [!NOTE]
> En la práctica, el código como ese anterior es un desperdicio de tiempo de procesador y memoria, ya que implica el cálculo de valores calculados previamente.

Los métodos son implícitamente recursivos dentro del tipo; no es necesario para agregar el `rec` palabra clave. Enlaces let en clases no son implícitamente recursivos.

## <a name="mutually-recursive-functions"></a>Funciones mutuamente recursivas

A veces, las funciones son *mutuamente recursivas*, lo que significa que las llamadas forman un círculo, donde una función llama a otro que a su vez llama a la primera, con cualquier número de llamadas entre ellos. Debe definir estas funciones juntas en una `let` enlace, mediante el `and` palabra clave para vincularlas.

El ejemplo siguiente muestra dos mutuamente las funciones recursivas.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet4002.fs)]

## <a name="see-also"></a>Vea también

- [Funciones](index.md)