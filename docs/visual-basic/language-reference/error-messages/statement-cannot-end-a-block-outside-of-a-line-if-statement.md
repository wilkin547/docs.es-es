---
title: La instrucción no puede terminar un bloque fuera de una línea de la instrucción 'If'
ms.date: 07/20/2015
f1_keywords:
- vbc32005
- bc32005
helpviewer_keywords:
- BC32005
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
ms.openlocfilehash: 0cee52f0ca00395d93c469aae6498fd3793f1085
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55266326"
---
# <a name="statement-cannot-end-a-block-outside-of-a-line-if-statement"></a>La instrucción no puede terminar un bloque fuera de una línea de la instrucción 'If'
Una sola línea `If` instrucción contiene varias instrucciones separadas por dos puntos (:), uno de los cuales es un `End` declaración de un bloque de control fuera de la línea `If`. Línea `If` instrucciones no utilizan el `End If` instrucción.  
  
 **Identificador de error:** BC32005  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Mover la línea `If` instrucción fuera del bloque de control que contiene el `End If` instrucción.  
  
## <a name="see-also"></a>Vea también
- [If...Then...Else (instrucción)](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
