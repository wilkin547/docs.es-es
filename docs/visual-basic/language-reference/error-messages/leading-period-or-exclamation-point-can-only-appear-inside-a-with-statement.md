---
title: "Iniciales &#39;. &#39; o &#39;! &#39; solo puede aparecer dentro de un &#39; Con &#39; instrucción"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30157
- bc30157
helpviewer_keywords: BC30157
ms.assetid: 70daaee1-14f9-45b7-9f30-53794310b95e
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 961f2d737123ab68b200d5fc7658cb81291a5de6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="leading-3939-or-3939-can-only-appear-inside-a-39with39-statement"></a><span data-ttu-id="6d58b-102">Iniciales &#39;. &#39; o &#39;! &#39; solo puede aparecer dentro de un &#39; Con &#39; instrucción</span><span class="sxs-lookup"><span data-stu-id="6d58b-102">Leading &#39;.&#39; or &#39;!&#39; can only appear inside a &#39;With&#39; statement</span></span>
<span data-ttu-id="6d58b-103">Un punto (.) o un signo de exclamación (!) que no está dentro un `With` bloqueo se produce sin una expresión de la izquierda.</span><span class="sxs-lookup"><span data-stu-id="6d58b-103">A period (.) or exclamation point (!) that is not inside a `With` block occurs without an expression on the left.</span></span> <span data-ttu-id="6d58b-104">Acceso a miembros (`.`) y acceso a miembros de diccionario (`!`) requieren una expresión que especifica el elemento que contiene el miembro.</span><span class="sxs-lookup"><span data-stu-id="6d58b-104">Member access (`.`) and dictionary member access (`!`) require an expression specifying the element that contains the member.</span></span> <span data-ttu-id="6d58b-105">Esto debe aparecer inmediatamente a la izquierda del descriptor de acceso o como destino de una `With` bloque que contiene el acceso a miembros.</span><span class="sxs-lookup"><span data-stu-id="6d58b-105">This must appear immediately to the left of the accessor or as the target of a `With` block containing the member access.</span></span>  
  
 <span data-ttu-id="6d58b-106">**Id. de error:** BC30157</span><span class="sxs-lookup"><span data-stu-id="6d58b-106">**Error ID:** BC30157</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6d58b-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="6d58b-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="6d58b-108">Asegúrese de que el `With` bloque tiene el formato correcto.</span><span class="sxs-lookup"><span data-stu-id="6d58b-108">Ensure that the `With` block is correctly formatted.</span></span>  
  
2.  <span data-ttu-id="6d58b-109">Si no hay ningún `With` bloquear, agregue una expresión a la izquierda del descriptor de acceso que se evalúa como un elemento definido que contiene el miembro.</span><span class="sxs-lookup"><span data-stu-id="6d58b-109">If there is no `With` block, add an expression to the left of the accessor that evaluates to a defined element containing the member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d58b-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="6d58b-110">See Also</span></span>  
 [<span data-ttu-id="6d58b-111">Caracteres especiales en el código</span><span class="sxs-lookup"><span data-stu-id="6d58b-111">Special Characters in Code</span></span>](../../../visual-basic/programming-guide/program-structure/special-characters-in-code.md)  
 [<span data-ttu-id="6d58b-112">With...End With (instrucción)</span><span class="sxs-lookup"><span data-stu-id="6d58b-112">With...End With Statement</span></span>](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
