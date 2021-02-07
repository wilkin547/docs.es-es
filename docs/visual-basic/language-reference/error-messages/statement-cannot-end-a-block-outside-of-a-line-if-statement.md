---
description: "Más información sobre: BC32005: la instrucción no puede terminar un bloque fuera de una línea de la instrucción ' if '"
title: La instrucción no puede terminar un bloque fuera de una línea de la instrucción 'If'
ms.date: 07/20/2015
f1_keywords:
- vbc32005
- bc32005
helpviewer_keywords:
- BC32005
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
ms.openlocfilehash: afe856b2c2ea3fa1db029d35c5b876f5d67da411
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99731160"
---
# <a name="bc32005-statement-cannot-end-a-block-outside-of-a-line-if-statement"></a>BC32005: la instrucción no puede terminar un bloque fuera de una línea de la instrucción ' if '

Una instrucción de una sola línea `If` contiene varias instrucciones separadas por dos puntos (:), una de las cuales es una `End` instrucción para un bloque de control fuera de la línea única `If` . Las instrucciones de una línea `If` no utilizan la `End If` instrucción.

 **Identificador de error:** BC32005

## <a name="to-correct-this-error"></a>Para corregir este error

- Mueva la instrucción de una sola línea `If` fuera del bloque de control que contiene la `End If` instrucción.

## <a name="see-also"></a>Vea también

- [Instrucción If...Then...Else](../statements/if-then-else-statement.md)
