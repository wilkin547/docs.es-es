---
title: La instrucción no puede terminar un bloque fuera de una línea &#39;si&#39; instrucción
ms.date: 07/20/2015
f1_keywords:
- vbc32005
- bc32005
helpviewer_keywords:
- BC32005
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
ms.openlocfilehash: af3006ddc35dfcaa52a54229881baa48cfb7809a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="statement-cannot-end-a-block-outside-of-a-line-39if39-statement"></a>La instrucción no puede terminar un bloque fuera de una línea &#39;si&#39; instrucción
Una sola línea `If` instrucción contiene varias instrucciones separadas por dos puntos (:), uno de los cuales es un `End` declaración de un bloque de control fuera de la línea `If`. Línea `If` instrucciones no utilizan el `End If` instrucción.  
  
 **Id. de error:** BC32005  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Mover la línea `If` instrucción fuera del bloque de control que contiene el `End If` instrucción.  
  
## <a name="see-also"></a>Vea también  
 [If...Then...Else (instrucción)](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
