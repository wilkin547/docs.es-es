---
description: "Más información sobre: BC30014: ' #ElseIf ' debe ir precedida de la ' #If ' o ' #ElseIf ' correspondiente"
title: "'#ElseIf' debe ir precedida de la instrucción '#If' o '#ElseIf' correspondiente"
ms.date: 07/20/2015
f1_keywords:
- vbc30014
- bc30014
helpviewer_keywords:
- BC30014
ms.assetid: 5215585e-2efa-485a-9efe-9833a1cc83a0
ms.openlocfilehash: 5eeb9c2fc0fd7267d95a8713a7071cd08788e48b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796566"
---
# <a name="bc30014-elseif-must-be-preceded-by-a-matching-if-or-elseif"></a>BC30014: ' #ElseIf ' debe ir precedida de la ' #If ' o ' #ElseIf ' correspondiente

`#ElseIf` es una directiva de compilación condicional. Una `#ElseIf` cláusula debe ir precedida de una `#If` cláusula o coincidente `#ElseIf` .

 **Identificador de error:** BC30014

## <a name="to-correct-this-error"></a>Para corregir este error

1. Compruebe que un `#If` `#ElseIf` bloque de compilación condicional intermedio o que no ha sido separado de esto es un `#ElseIf` bloque de compilación condicional intermedio o que no se ha colocado correctamente `#End If` .

2. Si `#ElseIf` está precedido por una `#Else` Directiva, quite `#Else` o cámbielo a `#ElseIf` .

3. Si todo lo demás es correcto, agregue una directiva `#If` al principio del bloque de compilación condicional.

## <a name="see-also"></a>Vea también

- [#If...Then...#Else (directivas)](../directives/if-then-else-directives.md)
