---
title: "'.' o '!' inicial sólo puede aparecer dentro de una instrucción 'With'"
ms.date: 07/20/2015
f1_keywords:
- vbc30157
- bc30157
helpviewer_keywords:
- BC30157
ms.assetid: 70daaee1-14f9-45b7-9f30-53794310b95e
ms.openlocfilehash: 15390fb506fe9bca10f6917f5b26451a5569bece
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59322854"
---
# <a name="leading--or--can-only-appear-inside-a-with-statement"></a><span data-ttu-id="29fe0-102">'.' o '!' inicial sólo puede aparecer dentro de una instrucción 'With'</span><span class="sxs-lookup"><span data-stu-id="29fe0-102">Leading '.' or '!' can only appear inside a 'With' statement</span></span>
<span data-ttu-id="29fe0-103">Un punto (.) o signo de exclamación (!) que no está dentro un `With` bloque aparece sin una expresión de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="29fe0-103">A period (.) or exclamation point (!) that is not inside a `With` block occurs without an expression on the left.</span></span> <span data-ttu-id="29fe0-104">Acceso a miembros (`.`) y acceso a miembros de diccionario (`!`) requieren una expresión que especifica el elemento que contiene el miembro.</span><span class="sxs-lookup"><span data-stu-id="29fe0-104">Member access (`.`) and dictionary member access (`!`) require an expression specifying the element that contains the member.</span></span> <span data-ttu-id="29fe0-105">Esto debe aparecer inmediatamente a la izquierda del descriptor de acceso o como destino de una `With` bloque que contiene el acceso a miembros.</span><span class="sxs-lookup"><span data-stu-id="29fe0-105">This must appear immediately to the left of the accessor or as the target of a `With` block containing the member access.</span></span>  
  
 <span data-ttu-id="29fe0-106">**Identificador de error:** BC30157</span><span class="sxs-lookup"><span data-stu-id="29fe0-106">**Error ID:** BC30157</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="29fe0-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="29fe0-107">To correct this error</span></span>  
  
1. <span data-ttu-id="29fe0-108">Asegúrese de que el `With` bloque tiene el formato correcto.</span><span class="sxs-lookup"><span data-stu-id="29fe0-108">Ensure that the `With` block is correctly formatted.</span></span>  
  
2. <span data-ttu-id="29fe0-109">Si no hay ningún `With` bloquear, agregue una expresión a la izquierda del descriptor de acceso que se evalúa como un elemento definido que contiene el miembro.</span><span class="sxs-lookup"><span data-stu-id="29fe0-109">If there is no `With` block, add an expression to the left of the accessor that evaluates to a defined element containing the member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29fe0-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="29fe0-110">See also</span></span>

- [<span data-ttu-id="29fe0-111">Caracteres especiales en el código</span><span class="sxs-lookup"><span data-stu-id="29fe0-111">Special Characters in Code</span></span>](../../../visual-basic/programming-guide/program-structure/special-characters-in-code.md)
- [<span data-ttu-id="29fe0-112">With...End With (instrucción)</span><span class="sxs-lookup"><span data-stu-id="29fe0-112">With...End With Statement</span></span>](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
