---
title: La instrucción no puede terminar un bloque fuera de una línea de la instrucción 'If'
ms.date: 07/20/2015
f1_keywords:
- vbc32005
- bc32005
helpviewer_keywords:
- BC32005
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
ms.openlocfilehash: 3fe3faaa3637446bb6ab443ba1d6e1d1004b4d48
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400323"
---
# <a name="statement-cannot-end-a-block-outside-of-a-line-if-statement"></a>La instrucción no puede terminar un bloque fuera de una línea de la instrucción 'If'
Una instrucción de una sola línea `If` contiene varias instrucciones separadas por dos puntos (:), una de las cuales es una `End` instrucción para un bloque de control fuera de la línea única `If` . Las instrucciones de una línea `If` no utilizan la `End If` instrucción.  
  
 **Identificador de error:** BC32005  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Mueva la instrucción de una sola línea `If` fuera del bloque de control que contiene la `End If` instrucción.  
  
## <a name="see-also"></a>Consulte también

- [Instrucción If...Then...Else](../statements/if-then-else-statement.md)
