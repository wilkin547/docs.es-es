---
title: 'Funciones recursivas: palabra clave rec (F#)'
description: "Obtenga información acerca de cómo se utiliza la palabra clave 'rec' de F # con la palabra clave 'let' para definir una función recursiva."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 1a95639f-9bfe-4f1d-a5e2-246d1d37776e
ms.openlocfilehash: b837d2c0f8e2b1d28980620103097ccc8345c098
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="recursive-functions-the-rec-keyword"></a>Funciones recursivas: palabra clave rec

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
Funciones recursivas, las funciones que llaman a sí mismos, se identifican explícitamente en el lenguaje F #. Esto hace que el identificador que se está definiendo estén disponibles en el ámbito de la función.

El código siguiente muestra una función recursiva que calcula el  *n* número de Fibonacci.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet4001.fs)]

>[!NOTE]
En la práctica, código similar anterior es desperdicia memoria y tiempo de procesador, ya que implica el cálculo de valores previamente calculados.


Los métodos son implícitamente recursivos dentro del tipo; no es necesario agregar el `rec` palabra clave. Enlaces let en clases no son implícitamente recursivos.


## <a name="mutually-recursive-functions"></a>Funciones mutuamente recursivas
A veces, las funciones son *mutuamente recursivas*, lo que significa que las llamadas forman un círculo, donde una función llama a otro que a su vez llama a la primera, con cualquier número de llamadas en medio. Debe definir estas funciones juntas en el `let` enlace, usando la `and` palabra clave que se va a vincular todos estos elementos.

En el ejemplo siguiente se muestra dos mutuamente las funciones recursivas.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet4002.fs)]

## <a name="see-also"></a>Vea también
[Funciones](index.md)
