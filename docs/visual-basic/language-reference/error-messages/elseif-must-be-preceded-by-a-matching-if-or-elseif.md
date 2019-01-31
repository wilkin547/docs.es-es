---
title: "'#ElseIf' debe ir precedida de la instrucción '#If' o '#ElseIf' correspondiente"
ms.date: 07/20/2015
f1_keywords:
- vbc30014
- bc30014
helpviewer_keywords:
- BC30014
ms.assetid: 5215585e-2efa-485a-9efe-9833a1cc83a0
ms.openlocfilehash: d6fa76b2aba45e3455cef6ceafc0f737ef56225d
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55271556"
---
# <a name="elseif-must-be-preceded-by-a-matching-if-or-elseif"></a><span data-ttu-id="0f6fd-102">'#ElseIf' debe ir precedida de la instrucción '#If' o '#ElseIf' correspondiente</span><span class="sxs-lookup"><span data-stu-id="0f6fd-102">'#ElseIf' must be preceded by a matching '#If' or '#ElseIf'</span></span>
<span data-ttu-id="0f6fd-103">`#ElseIf` es una directiva de compilación condicional.</span><span class="sxs-lookup"><span data-stu-id="0f6fd-103">`#ElseIf` is a conditional compilation directive.</span></span> <span data-ttu-id="0f6fd-104">Un `#ElseIf` cláusula debe ir precedida por una coincidencia `#If` o `#ElseIf` cláusula.</span><span class="sxs-lookup"><span data-stu-id="0f6fd-104">An `#ElseIf` clause must be preceded by a matching `#If` or `#ElseIf` clause.</span></span>  
  
 <span data-ttu-id="0f6fd-105">**Identificador de error:** BC30014</span><span class="sxs-lookup"><span data-stu-id="0f6fd-105">**Error ID:** BC30014</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0f6fd-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="0f6fd-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="0f6fd-107">Compruebe que un carácter `#If` o `#ElseIf` no se ha separado de esto `#ElseIf` por un bloque de compilación condicional intermedio o colocada incorrectamente `#End If`.</span><span class="sxs-lookup"><span data-stu-id="0f6fd-107">Check that a preceding `#If` or `#ElseIf` has not been separated from this `#ElseIf` by an intervening conditional compilation block or an incorrectly placed `#End If`.</span></span>  
  
2.  <span data-ttu-id="0f6fd-108">Si el `#ElseIf` está precedido por un `#Else` directiva, quite el `#Else` o cámbielo por un `#ElseIf`.</span><span class="sxs-lookup"><span data-stu-id="0f6fd-108">If the `#ElseIf` is preceded by a `#Else` directive, either remove the `#Else` or change it to an `#ElseIf`.</span></span>  
  
3.  <span data-ttu-id="0f6fd-109">Si todo lo demás es correcto, agregue una directiva `#If` al principio del bloque de compilación condicional.</span><span class="sxs-lookup"><span data-stu-id="0f6fd-109">If everything else is in order, add an `#If` directive to the beginning of the conditional compilation block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f6fd-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f6fd-110">See also</span></span>
- [<span data-ttu-id="0f6fd-111">#If...Then...#Else (directivas)</span><span class="sxs-lookup"><span data-stu-id="0f6fd-111">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
