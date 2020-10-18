---
title: La instrucción no puede terminar un bloque fuera de una línea de la instrucción 'If'
ms.date: 07/20/2015
f1_keywords:
- vbc32005
- bc32005
helpviewer_keywords:
- BC32005
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
ms.openlocfilehash: 4fd7577accd0b312ee1e3d2d990d256514d5f5f6
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161340"
---
# <a name="bc32005-statement-cannot-end-a-block-outside-of-a-line-if-statement"></a>BC32005: la instrucción no puede terminar un bloque fuera de una línea de la instrucción ' if '

Una instrucción de una sola línea `If` contiene varias instrucciones separadas por dos puntos (:), una de las cuales es una `End` instrucción para un bloque de control fuera de la línea única `If` . Las instrucciones de una línea `If` no utilizan la `End If` instrucción.

 **Identificador de error:** BC32005

## <a name="to-correct-this-error"></a>Para corregir este error

- Mueva la instrucción de una sola línea `If` fuera del bloque de control que contiene la `End If` instrucción.

## <a name="see-also"></a>Vea también

- [Instrucción If...Then...Else](../statements/if-then-else-statement.md)
