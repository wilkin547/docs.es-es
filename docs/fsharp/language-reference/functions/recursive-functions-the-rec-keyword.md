---
title: 'Funciones recursivas: La palabra clave REC'
description: Obtenga información sobre F# cómo se usa la palabra clave ' Rec ' con la palabra clave ' Let ' para definir una función recursiva.
ms.date: 05/16/2016
ms.openlocfilehash: 7edaa7206b2109c7b1a405624b9b2330968f9c52
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630657"
---
# <a name="recursive-functions-the-rec-keyword"></a>Funciones recursivas: La palabra clave REC

La `rec` palabra clave se usa junto con `let` la palabra clave para definir una función recursiva.

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

Las funciones recursivas, las funciones que se llaman a sí mismas, F# se identifican explícitamente en el lenguaje. Esto hace que el identificador que se está definiendo esté disponible en el ámbito de la función.

En el código siguiente se muestra una función recursiva que calcula el número<sup>de Fibonacci</sup> n.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet4001.fs)]

> [!NOTE]
> En la práctica, el código como el anterior es una pérdida de memoria y tiempo de procesador porque implica el recálculo de valores calculados previamente.

Los métodos son implícitamente recursivos dentro del tipo; no es necesario agregar la `rec` palabra clave. Los enlaces Let dentro de las clases no son implícitamente recursivos.

## <a name="mutually-recursive-functions"></a>Funciones mutuamente recursivas

A veces,las funciones son mutuamente recursivas, lo que significa que las llamadas forman un círculo, donde una función llama a otra que, a su vez, llama a la primera, con cualquier número de llamadas entre. Debe definir estas funciones juntas en un `let` enlace, utilizando la `and` palabra clave para vincularlas.

En el ejemplo siguiente se muestran dos funciones mutuamente recursivas.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet4002.fs)]

## <a name="see-also"></a>Vea también

- [Funciones](index.md)
