---
title: '&#39;#ElseIf&#39; debe ir precedida de una coincidencia &#39;#If&#39; o &#39;#ElseIf&#39;'
ms.date: 07/20/2015
f1_keywords:
- vbc30014
- bc30014
helpviewer_keywords:
- BC30014
ms.assetid: 5215585e-2efa-485a-9efe-9833a1cc83a0
ms.openlocfilehash: ef904173b1791309f6c2722bd959cabdad1d71da
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588153"
---
# <a name="39elseif39-must-be-preceded-by-a-matching-39if39-or-39elseif39"></a><span data-ttu-id="c70a5-102">&#39;#ElseIf&#39; debe ir precedida de una coincidencia &#39;#If&#39; o &#39;#ElseIf&#39;</span><span class="sxs-lookup"><span data-stu-id="c70a5-102">&#39;#ElseIf&#39; must be preceded by a matching &#39;#If&#39; or &#39;#ElseIf&#39;</span></span>
<span data-ttu-id="c70a5-103">`#ElseIf` es una directiva de compilación condicional.</span><span class="sxs-lookup"><span data-stu-id="c70a5-103">`#ElseIf` is a conditional compilation directive.</span></span> <span data-ttu-id="c70a5-104">Un `#ElseIf` cláusula debe ir precedida de una coincidencia `#If` o `#ElseIf` cláusula.</span><span class="sxs-lookup"><span data-stu-id="c70a5-104">An `#ElseIf` clause must be preceded by a matching `#If` or `#ElseIf` clause.</span></span>  
  
 <span data-ttu-id="c70a5-105">**Id. de error:** BC30014</span><span class="sxs-lookup"><span data-stu-id="c70a5-105">**Error ID:** BC30014</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c70a5-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="c70a5-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="c70a5-107">Compruebe que anterior `#If` o `#ElseIf` no se ha separado de esto `#ElseIf` por un bloque de compilación condicional intermedio o colocada incorrectamente `#End If`.</span><span class="sxs-lookup"><span data-stu-id="c70a5-107">Check that a preceding `#If` or `#ElseIf` has not been separated from this `#ElseIf` by an intervening conditional compilation block or an incorrectly placed `#End If`.</span></span>  
  
2.  <span data-ttu-id="c70a5-108">Si el `#ElseIf` está precedido por un `#Else` directiva, quite el `#Else` o cámbielo por un `#ElseIf`.</span><span class="sxs-lookup"><span data-stu-id="c70a5-108">If the `#ElseIf` is preceded by a `#Else` directive, either remove the `#Else` or change it to an `#ElseIf`.</span></span>  
  
3.  <span data-ttu-id="c70a5-109">Si todo lo demás es correcto, agregue una directiva `#If` al principio del bloque de compilación condicional.</span><span class="sxs-lookup"><span data-stu-id="c70a5-109">If everything else is in order, add an `#If` directive to the beginning of the conditional compilation block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c70a5-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="c70a5-110">See Also</span></span>  
 [<span data-ttu-id="c70a5-111">#If...Then...#Else (directivas)</span><span class="sxs-lookup"><span data-stu-id="c70a5-111">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
