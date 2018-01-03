---
title: "CorDebugIntercept (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugIntercept
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugIntercept
helpviewer_keywords: CorDebugIntercept enumeration [.NET Framework debugging]
ms.assetid: 3d5b642e-7ef2-428b-a5ae-509c35ed461a
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 814ee1285780d5a3b02aa5926ad4628e339a9114
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="cordebugintercept-enumeration"></a><span data-ttu-id="1f1d8-102">CorDebugIntercept (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="1f1d8-102">CorDebugIntercept Enumeration</span></span>
<span data-ttu-id="1f1d8-103">Indica los tipos de código que se pueden interceptar, es decir, ejecutar paso a paso.</span><span class="sxs-lookup"><span data-stu-id="1f1d8-103">Indicates the types of code that can be intercepted (that is, stepped into).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f1d8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1f1d8-104">Syntax</span></span>  
  
```  
typedef enum CorDebugIntercept {  
    INTERCEPT_NONE                = 0x0,  
    INTERCEPT_CLASS_INIT          = 0x01,  
    INTERCEPT_EXCEPTION_FILTER    = 0x02,  
    INTERCEPT_SECURITY            = 0x04,  
    INTERCEPT_CONTEXT_POLICY      = 0x08,  
    INTERCEPT_INTERCEPTION        = 0x10,  
    INTERCEPT_ALL                 = 0xffff  
} CorDebugIntercept;  
```  
  
## <a name="members"></a><span data-ttu-id="1f1d8-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="1f1d8-105">Members</span></span>  
  
|<span data-ttu-id="1f1d8-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="1f1d8-106">Member</span></span>|<span data-ttu-id="1f1d8-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="1f1d8-107">Description</span></span>|  
|------------|-----------------|  
|`INTERCEPT_NONE`|<span data-ttu-id="1f1d8-108">No se puede interceptar ningún código.</span><span class="sxs-lookup"><span data-stu-id="1f1d8-108">No code can be intercepted.</span></span>|  
|`INTERCEPT_CLASS_INIT`|<span data-ttu-id="1f1d8-109">Se puede interceptar un constructor.</span><span class="sxs-lookup"><span data-stu-id="1f1d8-109">A constructor can be intercepted.</span></span>|  
|`INTERCEPT_EXCEPTION_FILTER`|<span data-ttu-id="1f1d8-110">Se puede interceptar un filtro de excepción.</span><span class="sxs-lookup"><span data-stu-id="1f1d8-110">An exception filter can be intercepted.</span></span>|  
|`INTERCEPT_SECURITY`|<span data-ttu-id="1f1d8-111">Se puede interceptar código que exija seguridad.</span><span class="sxs-lookup"><span data-stu-id="1f1d8-111">Code that enforces security can be intercepted.</span></span>|  
|`INTERCEPT_CONTEXT_POLICY`|<span data-ttu-id="1f1d8-112">Se puede interceptar una directiva de contexto.</span><span class="sxs-lookup"><span data-stu-id="1f1d8-112">A context policy can be intercepted.</span></span>|  
|`INTERCEPT_INTERCEPTION`|<span data-ttu-id="1f1d8-113">No usado.</span><span class="sxs-lookup"><span data-stu-id="1f1d8-113">Not used.</span></span>|  
|`INTERCEPT_ALL`|<span data-ttu-id="1f1d8-114">Se puede interceptar todo el código.</span><span class="sxs-lookup"><span data-stu-id="1f1d8-114">All code can be intercepted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1f1d8-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1f1d8-115">Remarks</span></span>  
 <span data-ttu-id="1f1d8-116">Use la [SetInterceptMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setinterceptmask-method.md) método para establecer los tipos de código que se pueden interceptar.</span><span class="sxs-lookup"><span data-stu-id="1f1d8-116">Use the [ICorDebugStepper::SetInterceptMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setinterceptmask-method.md) method to establish the types of code that can be intercepted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f1d8-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1f1d8-117">Requirements</span></span>  
 <span data-ttu-id="1f1d8-118">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1f1d8-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f1d8-119">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1f1d8-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1f1d8-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1f1d8-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1f1d8-121">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f1d8-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f1d8-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="1f1d8-122">See Also</span></span>  
 [<span data-ttu-id="1f1d8-123">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="1f1d8-123">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
