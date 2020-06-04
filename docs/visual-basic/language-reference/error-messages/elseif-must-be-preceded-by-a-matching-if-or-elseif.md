---
title: "'#ElseIf' debe ir precedida de la instrucción '#If' o '#ElseIf' correspondiente"
ms.date: 07/20/2015
f1_keywords:
- vbc30014
- bc30014
helpviewer_keywords:
- BC30014
ms.assetid: 5215585e-2efa-485a-9efe-9833a1cc83a0
ms.openlocfilehash: 808cf35fb05da092cdef560721b2f667778aa78f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409665"
---
# <a name="elseif-must-be-preceded-by-a-matching-if-or-elseif"></a>'#ElseIf' debe ir precedida de la instrucción '#If' o '#ElseIf' correspondiente
`#ElseIf` es una directiva de compilación condicional. Una `#ElseIf` cláusula debe ir precedida de una `#If` cláusula o coincidente `#ElseIf` .  
  
 **Identificador de error:** BC30014  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Compruebe que un `#If` `#ElseIf` bloque de compilación condicional intermedio o que no ha sido separado de esto es un `#ElseIf` bloque de compilación condicional intermedio o que no se ha colocado correctamente `#End If` .  
  
2. Si `#ElseIf` está precedido por una `#Else` Directiva, quite `#Else` o cámbielo a `#ElseIf` .  
  
3. Si todo lo demás es correcto, agregue una directiva `#If` al principio del bloque de compilación condicional.  
  
## <a name="see-also"></a>Consulte también

- [#If...Then...#Else (directivas)](../directives/if-then-else-directives.md)
