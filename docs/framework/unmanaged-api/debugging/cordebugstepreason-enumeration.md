---
title: "CorDebugStepReason (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugStepReason
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugStepReason
helpviewer_keywords: CorDebugStepReason enumeration [.NET Framework debugging]
ms.assetid: fe248069-b33c-48e1-a777-06ac9b239c54
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 32892a14de820e8add38654cef92aa44930aec62
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="cordebugstepreason-enumeration"></a><span data-ttu-id="fc7ca-102">CorDebugStepReason (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="fc7ca-102">CorDebugStepReason Enumeration</span></span>
<span data-ttu-id="fc7ca-103">Indica el resultado de un paso individual.</span><span class="sxs-lookup"><span data-stu-id="fc7ca-103">Indicates the outcome of an individual step.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc7ca-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fc7ca-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="fc7ca-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="fc7ca-105">Members</span></span>  
  
|<span data-ttu-id="fc7ca-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="fc7ca-106">Member</span></span>|<span data-ttu-id="fc7ca-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="fc7ca-107">Description</span></span>|  
|------------|-----------------|  
|`STEP_NORMAL`|<span data-ttu-id="fc7ca-108">Ejecución paso a paso ha finalizado normalmente, dentro de la misma función.</span><span class="sxs-lookup"><span data-stu-id="fc7ca-108">Stepping completed normally, within the same function.</span></span>|  
|`STEP_RETURN`|<span data-ttu-id="fc7ca-109">Ejecución paso a paso ha continuado normalmente, después de que devuelva la función.</span><span class="sxs-lookup"><span data-stu-id="fc7ca-109">Stepping continued normally, after the function returned.</span></span>|  
|`STEP_CALL`|<span data-ttu-id="fc7ca-110">Ejecución paso a paso ha continuado normalmente, al principio de una función llamada recientemente.</span><span class="sxs-lookup"><span data-stu-id="fc7ca-110">Stepping continued normally, at the beginning of a newly called function.</span></span>|  
|`STEP_EXCEPTION_FILTER`|<span data-ttu-id="fc7ca-111">Se generó una excepción y el control se ha pasado a un filtro de excepción.</span><span class="sxs-lookup"><span data-stu-id="fc7ca-111">An exception was generated and control was passed to an exception filter.</span></span>|  
|`STEP_EXCEPTION_HANDLER`|<span data-ttu-id="fc7ca-112">Se generó una excepción y el control se ha pasado a un controlador de excepciones.</span><span class="sxs-lookup"><span data-stu-id="fc7ca-112">An exception was generated and control was passed to an exception handler.</span></span>|  
|`STEP_INTERCEPT`|<span data-ttu-id="fc7ca-113">Control se ha pasado a un interceptor.</span><span class="sxs-lookup"><span data-stu-id="fc7ca-113">Control was passed to an interceptor.</span></span>|  
|`STEP_EXIT`|<span data-ttu-id="fc7ca-114">El subproceso se cerró antes de que se complete el paso.</span><span class="sxs-lookup"><span data-stu-id="fc7ca-114">The thread exited before the step was completed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fc7ca-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fc7ca-115">Requirements</span></span>  
 <span data-ttu-id="fc7ca-116">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc7ca-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc7ca-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fc7ca-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fc7ca-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc7ca-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fc7ca-119">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc7ca-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc7ca-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="fc7ca-120">See Also</span></span>  
 [<span data-ttu-id="fc7ca-121">StepComplete (método)</span><span class="sxs-lookup"><span data-stu-id="fc7ca-121">StepComplete Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md)  
 [<span data-ttu-id="fc7ca-122">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="fc7ca-122">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
