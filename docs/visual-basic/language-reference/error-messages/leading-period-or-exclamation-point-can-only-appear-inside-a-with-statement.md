---
title: Iniciales &#39;. &#39; o &#39;! &#39; solo puede aparecer dentro de un &#39;con&#39; instrucción
ms.date: 07/20/2015
f1_keywords:
- vbc30157
- bc30157
helpviewer_keywords:
- BC30157
ms.assetid: 70daaee1-14f9-45b7-9f30-53794310b95e
ms.openlocfilehash: e64318d4ececbd887f55a1a202cc2d58c90c8fc7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54625957"
---
# <a name="leading-3939-or-3939-can-only-appear-inside-a-39with39-statement"></a><span data-ttu-id="23a2e-102">Iniciales &#39;. &#39; o &#39;! &#39; solo puede aparecer dentro de un &#39;con&#39; instrucción</span><span class="sxs-lookup"><span data-stu-id="23a2e-102">Leading &#39;.&#39; or &#39;!&#39; can only appear inside a &#39;With&#39; statement</span></span>
<span data-ttu-id="23a2e-103">Un punto (.) o signo de exclamación (!) que no está dentro un `With` bloque aparece sin una expresión de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="23a2e-103">A period (.) or exclamation point (!) that is not inside a `With` block occurs without an expression on the left.</span></span> <span data-ttu-id="23a2e-104">Acceso a miembros (`.`) y acceso a miembros de diccionario (`!`) requieren una expresión que especifica el elemento que contiene el miembro.</span><span class="sxs-lookup"><span data-stu-id="23a2e-104">Member access (`.`) and dictionary member access (`!`) require an expression specifying the element that contains the member.</span></span> <span data-ttu-id="23a2e-105">Esto debe aparecer inmediatamente a la izquierda del descriptor de acceso o como destino de una `With` bloque que contiene el acceso a miembros.</span><span class="sxs-lookup"><span data-stu-id="23a2e-105">This must appear immediately to the left of the accessor or as the target of a `With` block containing the member access.</span></span>  
  
 <span data-ttu-id="23a2e-106">**Identificador de error:** BC30157</span><span class="sxs-lookup"><span data-stu-id="23a2e-106">**Error ID:** BC30157</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="23a2e-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="23a2e-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="23a2e-108">Asegúrese de que el `With` bloque tiene el formato correcto.</span><span class="sxs-lookup"><span data-stu-id="23a2e-108">Ensure that the `With` block is correctly formatted.</span></span>  
  
2.  <span data-ttu-id="23a2e-109">Si no hay ningún `With` bloquear, agregue una expresión a la izquierda del descriptor de acceso que se evalúa como un elemento definido que contiene el miembro.</span><span class="sxs-lookup"><span data-stu-id="23a2e-109">If there is no `With` block, add an expression to the left of the accessor that evaluates to a defined element containing the member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23a2e-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="23a2e-110">See also</span></span>
- [<span data-ttu-id="23a2e-111">Caracteres especiales en el código</span><span class="sxs-lookup"><span data-stu-id="23a2e-111">Special Characters in Code</span></span>](../../../visual-basic/programming-guide/program-structure/special-characters-in-code.md)
- [<span data-ttu-id="23a2e-112">With...End With (instrucción)</span><span class="sxs-lookup"><span data-stu-id="23a2e-112">With...End With Statement</span></span>](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
