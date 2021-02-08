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
# <a name="bc30014-elseif-must-be-preceded-by-a-matching-if-or-elseif"></a><span data-ttu-id="50ff7-103">BC30014: ' #ElseIf ' debe ir precedida de la ' #If ' o ' #ElseIf ' correspondiente</span><span class="sxs-lookup"><span data-stu-id="50ff7-103">BC30014: '#ElseIf' must be preceded by a matching '#If' or '#ElseIf'</span></span>

<span data-ttu-id="50ff7-104">`#ElseIf` es una directiva de compilación condicional.</span><span class="sxs-lookup"><span data-stu-id="50ff7-104">`#ElseIf` is a conditional compilation directive.</span></span> <span data-ttu-id="50ff7-105">Una `#ElseIf` cláusula debe ir precedida de una `#If` cláusula o coincidente `#ElseIf` .</span><span class="sxs-lookup"><span data-stu-id="50ff7-105">An `#ElseIf` clause must be preceded by a matching `#If` or `#ElseIf` clause.</span></span>

 <span data-ttu-id="50ff7-106">**Identificador de error:** BC30014</span><span class="sxs-lookup"><span data-stu-id="50ff7-106">**Error ID:** BC30014</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="50ff7-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="50ff7-107">To correct this error</span></span>

1. <span data-ttu-id="50ff7-108">Compruebe que un `#If` `#ElseIf` bloque de compilación condicional intermedio o que no ha sido separado de esto es un `#ElseIf` bloque de compilación condicional intermedio o que no se ha colocado correctamente `#End If` .</span><span class="sxs-lookup"><span data-stu-id="50ff7-108">Check that a preceding `#If` or `#ElseIf` has not been separated from this `#ElseIf` by an intervening conditional compilation block or an incorrectly placed `#End If`.</span></span>

2. <span data-ttu-id="50ff7-109">Si `#ElseIf` está precedido por una `#Else` Directiva, quite `#Else` o cámbielo a `#ElseIf` .</span><span class="sxs-lookup"><span data-stu-id="50ff7-109">If the `#ElseIf` is preceded by a `#Else` directive, either remove the `#Else` or change it to an `#ElseIf`.</span></span>

3. <span data-ttu-id="50ff7-110">Si todo lo demás es correcto, agregue una directiva `#If` al principio del bloque de compilación condicional.</span><span class="sxs-lookup"><span data-stu-id="50ff7-110">If everything else is in order, add an `#If` directive to the beginning of the conditional compilation block.</span></span>

## <a name="see-also"></a><span data-ttu-id="50ff7-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="50ff7-111">See also</span></span>

- [<span data-ttu-id="50ff7-112">#If...Then...#Else (directivas)</span><span class="sxs-lookup"><span data-stu-id="50ff7-112">#If...Then...#Else Directives</span></span>](../directives/if-then-else-directives.md)
