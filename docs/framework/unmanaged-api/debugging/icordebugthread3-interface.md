---
title: ICorDebugThread3 (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugThread3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread3
helpviewer_keywords:
- ICorDebugThread3 interface [.NET Framework debugging]
ms.assetid: eb2860ef-06cb-4968-a6c3-6d048ecda2a4
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6cfb3267637210567f3df9fa08bb75135dc585ec
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthread3-interface"></a><span data-ttu-id="f005e-102">ICorDebugThread3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f005e-102">ICorDebugThread3 Interface</span></span>
<span data-ttu-id="f005e-103">Proporciona el punto de entrada a la [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) y las interfaces correspondientes.</span><span class="sxs-lookup"><span data-stu-id="f005e-103">Provides the entry point to the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) and corresponding interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f005e-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="f005e-104">Methods</span></span>  
  
|<span data-ttu-id="f005e-105">Método</span><span class="sxs-lookup"><span data-stu-id="f005e-105">Method</span></span>|<span data-ttu-id="f005e-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="f005e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f005e-107">CreateStackWalk (método)</span><span class="sxs-lookup"><span data-stu-id="f005e-107">CreateStackWalk Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-createstackwalk-method.md)|<span data-ttu-id="f005e-108">Crea un [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) objeto para el subproceso cuya pila desea desenredar.</span><span class="sxs-lookup"><span data-stu-id="f005e-108">Creates an [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>|  
|[<span data-ttu-id="f005e-109">GetActiveInternalFrames (método)</span><span class="sxs-lookup"><span data-stu-id="f005e-109">GetActiveInternalFrames Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md)|<span data-ttu-id="f005e-110">Devuelve una matriz de marcos internos ([ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) objetos) en la pila.</span><span class="sxs-lookup"><span data-stu-id="f005e-110">Returns an array of internal frames ([ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) objects) on the stack.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f005e-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f005e-111">Remarks</span></span>  
 <span data-ttu-id="f005e-112">`ICorDebugThread3`es una extensión lógica ICorDebugThread (interfaz).</span><span class="sxs-lookup"><span data-stu-id="f005e-112">`ICorDebugThread3` is a logical extension to the ICorDebugThread interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f005e-113">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="f005e-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f005e-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f005e-114">Requirements</span></span>  
 <span data-ttu-id="f005e-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f005e-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f005e-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f005e-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f005e-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f005e-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f005e-118">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f005e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f005e-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="f005e-119">See Also</span></span>  
 [<span data-ttu-id="f005e-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="f005e-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="f005e-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="f005e-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
