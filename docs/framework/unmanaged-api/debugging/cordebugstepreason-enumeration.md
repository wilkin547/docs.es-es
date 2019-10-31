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
ms.openlocfilehash: 6c73afb00cbd104cff3d310d1369097b459c131e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133687"
---
# <a name="cordebugstepreason-enumeration"></a><span data-ttu-id="0f864-102">CorDebugStepReason (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="0f864-102">CorDebugStepReason Enumeration</span></span>
<span data-ttu-id="0f864-103">Indica el resultado de un paso individual.</span><span class="sxs-lookup"><span data-stu-id="0f864-103">Indicates the outcome of an individual step.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f864-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0f864-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="0f864-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="0f864-105">Members</span></span>  
  
|<span data-ttu-id="0f864-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="0f864-106">Member</span></span>|<span data-ttu-id="0f864-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="0f864-107">Description</span></span>|  
|------------|-----------------|  
|`STEP_NORMAL`|<span data-ttu-id="0f864-108">La ejecución paso a paso se completó normalmente, dentro de la misma función.</span><span class="sxs-lookup"><span data-stu-id="0f864-108">Stepping completed normally, within the same function.</span></span>|  
|`STEP_RETURN`|<span data-ttu-id="0f864-109">La ejecución continuará normalmente, después de que se devuelva la función.</span><span class="sxs-lookup"><span data-stu-id="0f864-109">Stepping continued normally, after the function returned.</span></span>|  
|`STEP_CALL`|<span data-ttu-id="0f864-110">El paso continuó normalmente, al principio de una función recién llamada.</span><span class="sxs-lookup"><span data-stu-id="0f864-110">Stepping continued normally, at the beginning of a newly called function.</span></span>|  
|`STEP_EXCEPTION_FILTER`|<span data-ttu-id="0f864-111">Se generó una excepción y se pasó el control a un filtro de excepciones.</span><span class="sxs-lookup"><span data-stu-id="0f864-111">An exception was generated and control was passed to an exception filter.</span></span>|  
|`STEP_EXCEPTION_HANDLER`|<span data-ttu-id="0f864-112">Se generó una excepción y se pasó el control a un controlador de excepciones.</span><span class="sxs-lookup"><span data-stu-id="0f864-112">An exception was generated and control was passed to an exception handler.</span></span>|  
|`STEP_INTERCEPT`|<span data-ttu-id="0f864-113">El control se pasó a un interceptor.</span><span class="sxs-lookup"><span data-stu-id="0f864-113">Control was passed to an interceptor.</span></span>|  
|`STEP_EXIT`|<span data-ttu-id="0f864-114">El subproceso se cerró antes de que se completara el paso.</span><span class="sxs-lookup"><span data-stu-id="0f864-114">The thread exited before the step was completed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0f864-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0f864-115">Requirements</span></span>  
 <span data-ttu-id="0f864-116">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f864-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f864-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0f864-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0f864-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0f864-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0f864-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f864-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f864-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f864-120">See also</span></span>

- [<span data-ttu-id="0f864-121">StepComplete (método)</span><span class="sxs-lookup"><span data-stu-id="0f864-121">StepComplete Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md)
- [<span data-ttu-id="0f864-122">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="0f864-122">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
