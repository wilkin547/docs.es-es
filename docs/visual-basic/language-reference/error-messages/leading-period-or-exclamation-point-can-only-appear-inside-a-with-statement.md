---
title: A la izquierda &#39;. &#39; o &#39;! &#39; solo puede aparecer dentro de un &#39;con&#39; instrucción
ms.date: 07/20/2015
f1_keywords:
- vbc30157
- bc30157
helpviewer_keywords:
- BC30157
ms.assetid: 70daaee1-14f9-45b7-9f30-53794310b95e
ms.openlocfilehash: 7802b8e0aaf3dff83d5bfbe11f0b8bb1b5bb46cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33589452"
---
# <a name="leading-3939-or-3939-can-only-appear-inside-a-39with39-statement"></a><span data-ttu-id="4deb7-102">A la izquierda &#39;. &#39; o &#39;! &#39; solo puede aparecer dentro de un &#39;con&#39; instrucción</span><span class="sxs-lookup"><span data-stu-id="4deb7-102">Leading &#39;.&#39; or &#39;!&#39; can only appear inside a &#39;With&#39; statement</span></span>
<span data-ttu-id="4deb7-103">Un punto (.) o un signo de exclamación (!) que no está dentro un `With` bloqueo se produce sin una expresión de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="4deb7-103">A period (.) or exclamation point (!) that is not inside a `With` block occurs without an expression on the left.</span></span> <span data-ttu-id="4deb7-104">Acceso a miembros (`.`) y acceso a miembros de diccionario (`!`) requieren una expresión que especifica el elemento que contiene el miembro.</span><span class="sxs-lookup"><span data-stu-id="4deb7-104">Member access (`.`) and dictionary member access (`!`) require an expression specifying the element that contains the member.</span></span> <span data-ttu-id="4deb7-105">Esto debe aparecer inmediatamente a la izquierda del descriptor de acceso o como destino de una `With` bloque que contiene el acceso a miembros.</span><span class="sxs-lookup"><span data-stu-id="4deb7-105">This must appear immediately to the left of the accessor or as the target of a `With` block containing the member access.</span></span>  
  
 <span data-ttu-id="4deb7-106">**Id. de error:** BC30157</span><span class="sxs-lookup"><span data-stu-id="4deb7-106">**Error ID:** BC30157</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4deb7-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="4deb7-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="4deb7-108">Asegúrese de que el `With` bloque tiene el formato correcto.</span><span class="sxs-lookup"><span data-stu-id="4deb7-108">Ensure that the `With` block is correctly formatted.</span></span>  
  
2.  <span data-ttu-id="4deb7-109">Si no hay ningún `With` bloquear, agregue una expresión a la izquierda del descriptor de acceso que se evalúa como un elemento definido que contiene el miembro.</span><span class="sxs-lookup"><span data-stu-id="4deb7-109">If there is no `With` block, add an expression to the left of the accessor that evaluates to a defined element containing the member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4deb7-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="4deb7-110">See Also</span></span>  
 [<span data-ttu-id="4deb7-111">Caracteres especiales en el código</span><span class="sxs-lookup"><span data-stu-id="4deb7-111">Special Characters in Code</span></span>](../../../visual-basic/programming-guide/program-structure/special-characters-in-code.md)  
 [<span data-ttu-id="4deb7-112">With...End With (instrucción)</span><span class="sxs-lookup"><span data-stu-id="4deb7-112">With...End With Statement</span></span>](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
