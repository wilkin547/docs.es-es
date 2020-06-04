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
# <a name="elseif-must-be-preceded-by-a-matching-if-or-elseif"></a><span data-ttu-id="a9039-102">'#ElseIf' debe ir precedida de la instrucción '#If' o '#ElseIf' correspondiente</span><span class="sxs-lookup"><span data-stu-id="a9039-102">'#ElseIf' must be preceded by a matching '#If' or '#ElseIf'</span></span>
<span data-ttu-id="a9039-103">`#ElseIf` es una directiva de compilación condicional.</span><span class="sxs-lookup"><span data-stu-id="a9039-103">`#ElseIf` is a conditional compilation directive.</span></span> <span data-ttu-id="a9039-104">Una `#ElseIf` cláusula debe ir precedida de una `#If` cláusula o coincidente `#ElseIf` .</span><span class="sxs-lookup"><span data-stu-id="a9039-104">An `#ElseIf` clause must be preceded by a matching `#If` or `#ElseIf` clause.</span></span>  
  
 <span data-ttu-id="a9039-105">**Identificador de error:** BC30014</span><span class="sxs-lookup"><span data-stu-id="a9039-105">**Error ID:** BC30014</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a9039-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="a9039-106">To correct this error</span></span>  
  
1. <span data-ttu-id="a9039-107">Compruebe que un `#If` `#ElseIf` bloque de compilación condicional intermedio o que no ha sido separado de esto es un `#ElseIf` bloque de compilación condicional intermedio o que no se ha colocado correctamente `#End If` .</span><span class="sxs-lookup"><span data-stu-id="a9039-107">Check that a preceding `#If` or `#ElseIf` has not been separated from this `#ElseIf` by an intervening conditional compilation block or an incorrectly placed `#End If`.</span></span>  
  
2. <span data-ttu-id="a9039-108">Si `#ElseIf` está precedido por una `#Else` Directiva, quite `#Else` o cámbielo a `#ElseIf` .</span><span class="sxs-lookup"><span data-stu-id="a9039-108">If the `#ElseIf` is preceded by a `#Else` directive, either remove the `#Else` or change it to an `#ElseIf`.</span></span>  
  
3. <span data-ttu-id="a9039-109">Si todo lo demás es correcto, agregue una directiva `#If` al principio del bloque de compilación condicional.</span><span class="sxs-lookup"><span data-stu-id="a9039-109">If everything else is in order, add an `#If` directive to the beginning of the conditional compilation block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9039-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a9039-110">See also</span></span>

- [<span data-ttu-id="a9039-111">#If...Then...#Else (directivas)</span><span class="sxs-lookup"><span data-stu-id="a9039-111">#If...Then...#Else Directives</span></span>](../directives/if-then-else-directives.md)
