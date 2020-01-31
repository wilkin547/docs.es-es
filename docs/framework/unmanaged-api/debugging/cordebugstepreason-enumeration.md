---
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
ms.openlocfilehash: 92aee981aca3bac32c0ef264799e486315ca5103
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789256"
---
# <a name="cordebugstepreason-enumeration"></a><span data-ttu-id="0b6e7-102">CorDebugStepReason (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="0b6e7-102">CorDebugStepReason Enumeration</span></span>
<span data-ttu-id="0b6e7-103">Indica el resultado de un paso individual.</span><span class="sxs-lookup"><span data-stu-id="0b6e7-103">Indicates the outcome of an individual step.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b6e7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0b6e7-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="0b6e7-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="0b6e7-105">Members</span></span>  
  
|<span data-ttu-id="0b6e7-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="0b6e7-106">Member</span></span>|<span data-ttu-id="0b6e7-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="0b6e7-107">Description</span></span>|  
|------------|-----------------|  
|`STEP_NORMAL`|<span data-ttu-id="0b6e7-108">La ejecución paso a paso se completó normalmente, dentro de la misma función.</span><span class="sxs-lookup"><span data-stu-id="0b6e7-108">Stepping completed normally, within the same function.</span></span>|  
|`STEP_RETURN`|<span data-ttu-id="0b6e7-109">La ejecución continuará normalmente, después de que se devuelva la función.</span><span class="sxs-lookup"><span data-stu-id="0b6e7-109">Stepping continued normally, after the function returned.</span></span>|  
|`STEP_CALL`|<span data-ttu-id="0b6e7-110">El paso continuó normalmente, al principio de una función recién llamada.</span><span class="sxs-lookup"><span data-stu-id="0b6e7-110">Stepping continued normally, at the beginning of a newly called function.</span></span>|  
|`STEP_EXCEPTION_FILTER`|<span data-ttu-id="0b6e7-111">Se generó una excepción y se pasó el control a un filtro de excepciones.</span><span class="sxs-lookup"><span data-stu-id="0b6e7-111">An exception was generated and control was passed to an exception filter.</span></span>|  
|`STEP_EXCEPTION_HANDLER`|<span data-ttu-id="0b6e7-112">Se generó una excepción y se pasó el control a un controlador de excepciones.</span><span class="sxs-lookup"><span data-stu-id="0b6e7-112">An exception was generated and control was passed to an exception handler.</span></span>|  
|`STEP_INTERCEPT`|<span data-ttu-id="0b6e7-113">El control se pasó a un interceptor.</span><span class="sxs-lookup"><span data-stu-id="0b6e7-113">Control was passed to an interceptor.</span></span>|  
|`STEP_EXIT`|<span data-ttu-id="0b6e7-114">El subproceso se cerró antes de que se completara el paso.</span><span class="sxs-lookup"><span data-stu-id="0b6e7-114">The thread exited before the step was completed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0b6e7-115">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="0b6e7-115">Requirements</span></span>  
 <span data-ttu-id="0b6e7-116">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b6e7-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b6e7-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0b6e7-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0b6e7-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0b6e7-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0b6e7-119">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b6e7-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b6e7-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="0b6e7-120">See also</span></span>

- [<span data-ttu-id="0b6e7-121">StepComplete (método)</span><span class="sxs-lookup"><span data-stu-id="0b6e7-121">StepComplete Method</span></span>](icordebugmanagedcallback-stepcomplete-method.md)
- [<span data-ttu-id="0b6e7-122">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="0b6e7-122">Debugging Enumerations</span></span>](debugging-enumerations.md)
