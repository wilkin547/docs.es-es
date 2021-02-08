---
description: 'Más información sobre: enumeración CorDebugStepReason ('
title: CorDebugStepReason (Enumeración)
ms.date: 03/30/2017
api_name:
- CorDebugStepReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugStepReason
helpviewer_keywords:
- CorDebugStepReason enumeration [.NET Framework debugging]
ms.assetid: fe248069-b33c-48e1-a777-06ac9b239c54
topic_type:
- apiref
ms.openlocfilehash: 2a331b09709ffb6179f2e481baf4bf421d60ea99
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801545"
---
# <a name="cordebugstepreason-enumeration"></a><span data-ttu-id="fc7da-103">CorDebugStepReason (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="fc7da-103">CorDebugStepReason Enumeration</span></span>

<span data-ttu-id="fc7da-104">Indica el resultado de un paso individual.</span><span class="sxs-lookup"><span data-stu-id="fc7da-104">Indicates the outcome of an individual step.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc7da-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fc7da-105">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugStepReason {  
    STEP_NORMAL,  
    STEP_RETURN,  
    STEP_CALL,  
    STEP_EXCEPTION_FILTER,  
    STEP_EXCEPTION_HANDLER,  
    STEP_INTERCEPT,  
    STEP_EXIT  
} CorDebugStepReason;  
```  
  
## <a name="members"></a><span data-ttu-id="fc7da-106">Members</span><span class="sxs-lookup"><span data-stu-id="fc7da-106">Members</span></span>  
  
|<span data-ttu-id="fc7da-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="fc7da-107">Member</span></span>|<span data-ttu-id="fc7da-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="fc7da-108">Description</span></span>|  
|------------|-----------------|  
|`STEP_NORMAL`|<span data-ttu-id="fc7da-109">La ejecución paso a paso se completó normalmente, dentro de la misma función.</span><span class="sxs-lookup"><span data-stu-id="fc7da-109">Stepping completed normally, within the same function.</span></span>|  
|`STEP_RETURN`|<span data-ttu-id="fc7da-110">La ejecución continuará normalmente, después de que se devuelva la función.</span><span class="sxs-lookup"><span data-stu-id="fc7da-110">Stepping continued normally, after the function returned.</span></span>|  
|`STEP_CALL`|<span data-ttu-id="fc7da-111">El paso continuó normalmente, al principio de una función recién llamada.</span><span class="sxs-lookup"><span data-stu-id="fc7da-111">Stepping continued normally, at the beginning of a newly called function.</span></span>|  
|`STEP_EXCEPTION_FILTER`|<span data-ttu-id="fc7da-112">Se generó una excepción y se pasó el control a un filtro de excepciones.</span><span class="sxs-lookup"><span data-stu-id="fc7da-112">An exception was generated and control was passed to an exception filter.</span></span>|  
|`STEP_EXCEPTION_HANDLER`|<span data-ttu-id="fc7da-113">Se generó una excepción y se pasó el control a un controlador de excepciones.</span><span class="sxs-lookup"><span data-stu-id="fc7da-113">An exception was generated and control was passed to an exception handler.</span></span>|  
|`STEP_INTERCEPT`|<span data-ttu-id="fc7da-114">El control se pasó a un interceptor.</span><span class="sxs-lookup"><span data-stu-id="fc7da-114">Control was passed to an interceptor.</span></span>|  
|`STEP_EXIT`|<span data-ttu-id="fc7da-115">El subproceso se cerró antes de que se completara el paso.</span><span class="sxs-lookup"><span data-stu-id="fc7da-115">The thread exited before the step was completed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fc7da-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fc7da-116">Requirements</span></span>  

 <span data-ttu-id="fc7da-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc7da-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc7da-118">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fc7da-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fc7da-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc7da-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fc7da-120">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc7da-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc7da-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="fc7da-121">See also</span></span>

- [<span data-ttu-id="fc7da-122">Método StepComplete</span><span class="sxs-lookup"><span data-stu-id="fc7da-122">StepComplete Method</span></span>](icordebugmanagedcallback-stepcomplete-method.md)
- [<span data-ttu-id="fc7da-123">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="fc7da-123">Debugging Enumerations</span></span>](debugging-enumerations.md)
