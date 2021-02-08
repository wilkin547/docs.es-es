---
description: "Más información acerca de: BC30481: la instrucción ' Class ' debe terminar con la instrucción ' End Class ' correspondiente"
title: La instrucción 'Class' debe terminar con la instrucción 'End Class' correspondiente
ms.date: 07/20/2015
f1_keywords:
- vbc30481
- bc30481
helpviewer_keywords:
- BC30481
ms.assetid: 583f3029-bc3a-4e06-866f-92dbecc46f19
ms.openlocfilehash: b0d2d89e9e3549b24f9c923e271b15b3b02026b3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796786"
---
# <a name="bc30481-class-statement-must-end-with-a-matching-end-class"></a><span data-ttu-id="97ef6-103">BC30481: la instrucción ' Class ' debe terminar con la instrucción ' End Class ' correspondiente</span><span class="sxs-lookup"><span data-stu-id="97ef6-103">BC30481: 'Class' statement must end with a matching 'End Class'</span></span>

<span data-ttu-id="97ef6-104">`Class` se usa para iniciar un `Class` bloque; por lo tanto, solo puede aparecer al principio del bloque, con una instrucción coincidente que `End Class` finaliza el bloque.</span><span class="sxs-lookup"><span data-stu-id="97ef6-104">`Class` is used to initiate a `Class` block; hence it can only appear at the beginning of the block, with a matching `End Class` statement ending the block.</span></span> <span data-ttu-id="97ef6-105">O bien tiene una instrucción redundante `Class` o no ha finalizado el `Class` bloque con `End Class` .</span><span class="sxs-lookup"><span data-stu-id="97ef6-105">Either you have a redundant `Class` statement, or you have not ended your `Class` block with `End Class`.</span></span>

 <span data-ttu-id="97ef6-106">**Identificador de error:** BC30481</span><span class="sxs-lookup"><span data-stu-id="97ef6-106">**Error ID:** BC30481</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="97ef6-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="97ef6-107">To correct this error</span></span>

- <span data-ttu-id="97ef6-108">Busque y quite la instrucción `Class` innecesaria.</span><span class="sxs-lookup"><span data-stu-id="97ef6-108">Locate and remove the unnecessary `Class` statement.</span></span>

- <span data-ttu-id="97ef6-109">Concluye el `Class` bloque con una coincidencia `End Class` .</span><span class="sxs-lookup"><span data-stu-id="97ef6-109">Conclude the `Class` block with a matching `End Class`.</span></span>

## <a name="see-also"></a><span data-ttu-id="97ef6-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="97ef6-110">See also</span></span>

- [<span data-ttu-id="97ef6-111">End ( \<keyword> instrucción)</span><span class="sxs-lookup"><span data-stu-id="97ef6-111">End \<keyword> Statement</span></span>](../statements/end-keyword-statement.md)
- [<span data-ttu-id="97ef6-112">Instrucción Class</span><span class="sxs-lookup"><span data-stu-id="97ef6-112">Class Statement</span></span>](../statements/class-statement.md)
