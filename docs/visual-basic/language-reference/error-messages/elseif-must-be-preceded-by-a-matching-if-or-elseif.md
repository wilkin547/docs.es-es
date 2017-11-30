---
title: '&#39; #ElseIf &#39; debe ir precedida de una coincidencia &#39; #If &#39; o &#39; #ElseIf &#39;'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30014
- bc30014
helpviewer_keywords: BC30014
ms.assetid: 5215585e-2efa-485a-9efe-9833a1cc83a0
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4b3a4e809e1108fcd6e116538a1947057e9548ce
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="39elseif39-must-be-preceded-by-a-matching-39if39-or-39elseif39"></a><span data-ttu-id="371f0-102">&#39; #ElseIf &#39; debe ir precedida de una coincidencia &#39; #If &#39; o &#39; #ElseIf &#39;</span><span class="sxs-lookup"><span data-stu-id="371f0-102">&#39;#ElseIf&#39; must be preceded by a matching &#39;#If&#39; or &#39;#ElseIf&#39;</span></span>
<span data-ttu-id="371f0-103">`#ElseIf`es una directiva de compilación condicional.</span><span class="sxs-lookup"><span data-stu-id="371f0-103">`#ElseIf` is a conditional compilation directive.</span></span> <span data-ttu-id="371f0-104">Un `#ElseIf` cláusula debe ir precedida de una coincidencia `#If` o `#ElseIf` cláusula.</span><span class="sxs-lookup"><span data-stu-id="371f0-104">An `#ElseIf` clause must be preceded by a matching `#If` or `#ElseIf` clause.</span></span>  
  
 <span data-ttu-id="371f0-105">**Id. de error:** BC30014</span><span class="sxs-lookup"><span data-stu-id="371f0-105">**Error ID:** BC30014</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="371f0-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="371f0-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="371f0-107">Compruebe que anterior `#If` o `#ElseIf` no se ha separado de esto `#ElseIf` por un bloque de compilación condicional intermedio o colocada incorrectamente `#End If`.</span><span class="sxs-lookup"><span data-stu-id="371f0-107">Check that a preceding `#If` or `#ElseIf` has not been separated from this `#ElseIf` by an intervening conditional compilation block or an incorrectly placed `#End If`.</span></span>  
  
2.  <span data-ttu-id="371f0-108">Si el `#ElseIf` está precedido por un `#Else` directiva, quite el `#Else` o cámbielo por un `#ElseIf`.</span><span class="sxs-lookup"><span data-stu-id="371f0-108">If the `#ElseIf` is preceded by a `#Else` directive, either remove the `#Else` or change it to an `#ElseIf`.</span></span>  
  
3.  <span data-ttu-id="371f0-109">Si todo lo demás es correcto, agregue una directiva `#If` al principio del bloque de compilación condicional.</span><span class="sxs-lookup"><span data-stu-id="371f0-109">If everything else is in order, add an `#If` directive to the beginning of the conditional compilation block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="371f0-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="371f0-110">See Also</span></span>  
 [<span data-ttu-id="371f0-111">#If...Then...#Else (directivas)</span><span class="sxs-lookup"><span data-stu-id="371f0-111">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
