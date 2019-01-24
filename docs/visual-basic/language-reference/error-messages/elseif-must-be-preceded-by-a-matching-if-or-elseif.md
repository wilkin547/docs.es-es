---
title: '&#39;#ElseIf&#39; debe ir precedido por una coincidencia &#39;#If&#39; o &#39;#ElseIf&#39;'
ms.date: 07/20/2015
f1_keywords:
- vbc30014
- bc30014
helpviewer_keywords:
- BC30014
ms.assetid: 5215585e-2efa-485a-9efe-9833a1cc83a0
ms.openlocfilehash: 1e63595ee573e9356f6870a02b2131897c725baf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54505788"
---
# <a name="39elseif39-must-be-preceded-by-a-matching-39if39-or-39elseif39"></a>&#39;#ElseIf&#39; debe ir precedido por una coincidencia &#39;#If&#39; o &#39;#ElseIf&#39;
`#ElseIf` es una directiva de compilación condicional. Un `#ElseIf` cláusula debe ir precedida por una coincidencia `#If` o `#ElseIf` cláusula.  
  
 **Identificador de error:** BC30014  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Compruebe que un carácter `#If` o `#ElseIf` no se ha separado de esto `#ElseIf` por un bloque de compilación condicional intermedio o colocada incorrectamente `#End If`.  
  
2.  Si el `#ElseIf` está precedido por un `#Else` directiva, quite el `#Else` o cámbielo por un `#ElseIf`.  
  
3.  Si todo lo demás es correcto, agregue una directiva `#If` al principio del bloque de compilación condicional.  
  
## <a name="see-also"></a>Vea también
- [#If...Then...#Else (directivas)](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
