---
title: "'#ElseIf' debe ir precedida de la instrucción '#If' o '#ElseIf' correspondiente"
ms.date: 07/20/2015
f1_keywords:
- vbc30014
- bc30014
helpviewer_keywords:
- BC30014
ms.assetid: 5215585e-2efa-485a-9efe-9833a1cc83a0
ms.openlocfilehash: fbb8ce974a618349bd4b5e7a2a25a165d91787a7
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58832260"
---
# <a name="elseif-must-be-preceded-by-a-matching-if-or-elseif"></a>'#ElseIf' debe ir precedida de la instrucción '#If' o '#ElseIf' correspondiente
`#ElseIf` es una directiva de compilación condicional. Un `#ElseIf` cláusula debe ir precedida por una coincidencia `#If` o `#ElseIf` cláusula.  
  
 **Identificador de error:** BC30014  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Compruebe que un carácter `#If` o `#ElseIf` no se ha separado de esto `#ElseIf` por un bloque de compilación condicional intermedio o colocada incorrectamente `#End If`.  
  
2.  Si el `#ElseIf` está precedido por un `#Else` directiva, quite el `#Else` o cámbielo por un `#ElseIf`.  
  
3.  Si todo lo demás es correcto, agregue una directiva `#If` al principio del bloque de compilación condicional.  
  
## <a name="see-also"></a>Vea también

- [#If...Then...#Else (directivas)](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
