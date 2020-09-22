---
title: "'.' o '!' inicial sólo puede aparecer dentro de una instrucción 'With'"
ms.date: 07/20/2015
f1_keywords:
- vbc30157
- bc30157
helpviewer_keywords:
- BC30157
ms.assetid: 70daaee1-14f9-45b7-9f30-53794310b95e
ms.openlocfilehash: c39339a49c4aad4ba643facc2372333e7379ffa7
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873843"
---
# <a name="leading--or--can-only-appear-inside-a-with-statement"></a><span data-ttu-id="e9d17-102">'.' o '!' inicial sólo puede aparecer dentro de una instrucción 'With'</span><span class="sxs-lookup"><span data-stu-id="e9d17-102">Leading '.' or '!' can only appear inside a 'With' statement</span></span>

<span data-ttu-id="e9d17-103">Un punto (.) o un signo de exclamación (!) que no está dentro de un `With` bloque se produce sin una expresión a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="e9d17-103">A period (.) or exclamation point (!) that is not inside a `With` block occurs without an expression on the left.</span></span> <span data-ttu-id="e9d17-104">El acceso a miembros ( `.` ) y el acceso a miembros de diccionario ( `!` ) requieren una expresión que especifique el elemento que contiene el miembro.</span><span class="sxs-lookup"><span data-stu-id="e9d17-104">Member access (`.`) and dictionary member access (`!`) require an expression specifying the element that contains the member.</span></span> <span data-ttu-id="e9d17-105">Debe aparecer inmediatamente a la izquierda del descriptor de acceso o como destino de un `With` bloque que contiene el acceso a miembros.</span><span class="sxs-lookup"><span data-stu-id="e9d17-105">This must appear immediately to the left of the accessor or as the target of a `With` block containing the member access.</span></span>  
  
 <span data-ttu-id="e9d17-106">**Identificador de error:** BC30157</span><span class="sxs-lookup"><span data-stu-id="e9d17-106">**Error ID:** BC30157</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e9d17-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="e9d17-107">To correct this error</span></span>  
  
1. <span data-ttu-id="e9d17-108">Asegúrese de que el `With` bloque tenga el formato correcto.</span><span class="sxs-lookup"><span data-stu-id="e9d17-108">Ensure that the `With` block is correctly formatted.</span></span>  
  
2. <span data-ttu-id="e9d17-109">Si no hay ningún `With` bloque, agregue una expresión a la izquierda del descriptor de acceso que se evalúe como un elemento definido que contiene el miembro.</span><span class="sxs-lookup"><span data-stu-id="e9d17-109">If there is no `With` block, add an expression to the left of the accessor that evaluates to a defined element containing the member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9d17-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e9d17-110">See also</span></span>

- [<span data-ttu-id="e9d17-111">Caracteres especiales en el código</span><span class="sxs-lookup"><span data-stu-id="e9d17-111">Special Characters in Code</span></span>](../../programming-guide/program-structure/special-characters-in-code.md)
- [<span data-ttu-id="e9d17-112">Instrucción With...End With</span><span class="sxs-lookup"><span data-stu-id="e9d17-112">With...End With Statement</span></span>](../statements/with-end-with-statement.md)
