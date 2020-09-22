---
title: La instrucción 'Class' debe terminar con la instrucción 'End Class' correspondiente
ms.date: 07/20/2015
f1_keywords:
- vbc30481
- bc30481
helpviewer_keywords:
- BC30481
ms.assetid: 583f3029-bc3a-4e06-866f-92dbecc46f19
ms.openlocfilehash: d67f0e71dbdbf97420ec5b5ba4b6f06acfba1bd9
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874611"
---
# <a name="class-statement-must-end-with-a-matching-end-class"></a><span data-ttu-id="55209-102">La instrucción 'Class' debe terminar con la instrucción 'End Class' correspondiente</span><span class="sxs-lookup"><span data-stu-id="55209-102">'Class' statement must end with a matching 'End Class'</span></span>

<span data-ttu-id="55209-103">`Class` se usa para iniciar un `Class` bloque; por lo tanto, solo puede aparecer al principio del bloque, con una instrucción coincidente que `End Class` finaliza el bloque.</span><span class="sxs-lookup"><span data-stu-id="55209-103">`Class` is used to initiate a `Class` block; hence it can only appear at the beginning of the block, with a matching `End Class` statement ending the block.</span></span> <span data-ttu-id="55209-104">O bien tiene una instrucción redundante `Class` o no ha finalizado el `Class` bloque con `End Class` .</span><span class="sxs-lookup"><span data-stu-id="55209-104">Either you have a redundant `Class` statement, or you have not ended your `Class` block with `End Class`.</span></span>  
  
 <span data-ttu-id="55209-105">**Identificador de error:** BC30481</span><span class="sxs-lookup"><span data-stu-id="55209-105">**Error ID:** BC30481</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="55209-106">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="55209-106">To correct this error</span></span>  
  
- <span data-ttu-id="55209-107">Busque y quite la instrucción `Class` innecesaria.</span><span class="sxs-lookup"><span data-stu-id="55209-107">Locate and remove the unnecessary `Class` statement.</span></span>  
  
- <span data-ttu-id="55209-108">Concluye el `Class` bloque con una coincidencia `End Class` .</span><span class="sxs-lookup"><span data-stu-id="55209-108">Conclude the `Class` block with a matching `End Class`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55209-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="55209-109">See also</span></span>

- [<span data-ttu-id="55209-110">End ( \<keyword> instrucción)</span><span class="sxs-lookup"><span data-stu-id="55209-110">End \<keyword> Statement</span></span>](../statements/end-keyword-statement.md)
- [<span data-ttu-id="55209-111">Instrucción Class</span><span class="sxs-lookup"><span data-stu-id="55209-111">Class Statement</span></span>](../statements/class-statement.md)
