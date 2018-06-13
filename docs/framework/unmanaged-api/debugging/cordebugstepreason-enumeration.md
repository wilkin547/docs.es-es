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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 71dcc34fd3489fc71cec4050b168548927833082
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404536"
---
# <a name="cordebugstepreason-enumeration"></a><span data-ttu-id="9e73e-102">CorDebugStepReason (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="9e73e-102">CorDebugStepReason Enumeration</span></span>
<span data-ttu-id="9e73e-103">Indica el resultado de un paso individual.</span><span class="sxs-lookup"><span data-stu-id="9e73e-103">Indicates the outcome of an individual step.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e73e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9e73e-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="9e73e-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="9e73e-105">Members</span></span>  
  
|<span data-ttu-id="9e73e-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="9e73e-106">Member</span></span>|<span data-ttu-id="9e73e-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="9e73e-107">Description</span></span>|  
|------------|-----------------|  
|`STEP_NORMAL`|<span data-ttu-id="9e73e-108">Ejecución paso a paso ha finalizado normalmente, dentro de la misma función.</span><span class="sxs-lookup"><span data-stu-id="9e73e-108">Stepping completed normally, within the same function.</span></span>|  
|`STEP_RETURN`|<span data-ttu-id="9e73e-109">Ejecución paso a paso ha continuado normalmente, después de que devuelva la función.</span><span class="sxs-lookup"><span data-stu-id="9e73e-109">Stepping continued normally, after the function returned.</span></span>|  
|`STEP_CALL`|<span data-ttu-id="9e73e-110">Ejecución paso a paso ha continuado normalmente, al principio de una función llamada recientemente.</span><span class="sxs-lookup"><span data-stu-id="9e73e-110">Stepping continued normally, at the beginning of a newly called function.</span></span>|  
|`STEP_EXCEPTION_FILTER`|<span data-ttu-id="9e73e-111">Se generó una excepción y el control se ha pasado a un filtro de excepción.</span><span class="sxs-lookup"><span data-stu-id="9e73e-111">An exception was generated and control was passed to an exception filter.</span></span>|  
|`STEP_EXCEPTION_HANDLER`|<span data-ttu-id="9e73e-112">Se generó una excepción y el control se ha pasado a un controlador de excepciones.</span><span class="sxs-lookup"><span data-stu-id="9e73e-112">An exception was generated and control was passed to an exception handler.</span></span>|  
|`STEP_INTERCEPT`|<span data-ttu-id="9e73e-113">Control se ha pasado a un interceptor.</span><span class="sxs-lookup"><span data-stu-id="9e73e-113">Control was passed to an interceptor.</span></span>|  
|`STEP_EXIT`|<span data-ttu-id="9e73e-114">El subproceso se cerró antes de que se complete el paso.</span><span class="sxs-lookup"><span data-stu-id="9e73e-114">The thread exited before the step was completed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9e73e-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9e73e-115">Requirements</span></span>  
 <span data-ttu-id="9e73e-116">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e73e-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e73e-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9e73e-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9e73e-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9e73e-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9e73e-119">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e73e-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e73e-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="9e73e-120">See Also</span></span>  
 [<span data-ttu-id="9e73e-121">StepComplete (método)</span><span class="sxs-lookup"><span data-stu-id="9e73e-121">StepComplete Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md)  
 [<span data-ttu-id="9e73e-122">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="9e73e-122">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
