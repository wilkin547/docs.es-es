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
ms.openlocfilehash: 50903b3737c0fc63eda2b1190e4c3d961ce3ae7b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726046"
---
# <a name="cordebugstepreason-enumeration"></a><span data-ttu-id="8ff72-102">CorDebugStepReason (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="8ff72-102">CorDebugStepReason Enumeration</span></span>

<span data-ttu-id="8ff72-103">Indica el resultado de un paso individual.</span><span class="sxs-lookup"><span data-stu-id="8ff72-103">Indicates the outcome of an individual step.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ff72-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8ff72-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="8ff72-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="8ff72-105">Members</span></span>  
  
|<span data-ttu-id="8ff72-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="8ff72-106">Member</span></span>|<span data-ttu-id="8ff72-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="8ff72-107">Description</span></span>|  
|------------|-----------------|  
|`STEP_NORMAL`|<span data-ttu-id="8ff72-108">La ejecución paso a paso se completó normalmente, dentro de la misma función.</span><span class="sxs-lookup"><span data-stu-id="8ff72-108">Stepping completed normally, within the same function.</span></span>|  
|`STEP_RETURN`|<span data-ttu-id="8ff72-109">La ejecución continuará normalmente, después de que se devuelva la función.</span><span class="sxs-lookup"><span data-stu-id="8ff72-109">Stepping continued normally, after the function returned.</span></span>|  
|`STEP_CALL`|<span data-ttu-id="8ff72-110">El paso continuó normalmente, al principio de una función recién llamada.</span><span class="sxs-lookup"><span data-stu-id="8ff72-110">Stepping continued normally, at the beginning of a newly called function.</span></span>|  
|`STEP_EXCEPTION_FILTER`|<span data-ttu-id="8ff72-111">Se generó una excepción y se pasó el control a un filtro de excepciones.</span><span class="sxs-lookup"><span data-stu-id="8ff72-111">An exception was generated and control was passed to an exception filter.</span></span>|  
|`STEP_EXCEPTION_HANDLER`|<span data-ttu-id="8ff72-112">Se generó una excepción y se pasó el control a un controlador de excepciones.</span><span class="sxs-lookup"><span data-stu-id="8ff72-112">An exception was generated and control was passed to an exception handler.</span></span>|  
|`STEP_INTERCEPT`|<span data-ttu-id="8ff72-113">El control se pasó a un interceptor.</span><span class="sxs-lookup"><span data-stu-id="8ff72-113">Control was passed to an interceptor.</span></span>|  
|`STEP_EXIT`|<span data-ttu-id="8ff72-114">El subproceso se cerró antes de que se completara el paso.</span><span class="sxs-lookup"><span data-stu-id="8ff72-114">The thread exited before the step was completed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8ff72-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8ff72-115">Requirements</span></span>  

 <span data-ttu-id="8ff72-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8ff72-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ff72-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8ff72-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8ff72-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8ff72-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8ff72-119">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ff72-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ff72-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8ff72-120">See also</span></span>

- [<span data-ttu-id="8ff72-121">Método StepComplete</span><span class="sxs-lookup"><span data-stu-id="8ff72-121">StepComplete Method</span></span>](icordebugmanagedcallback-stepcomplete-method.md)
- [<span data-ttu-id="8ff72-122">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="8ff72-122">Debugging Enumerations</span></span>](debugging-enumerations.md)
