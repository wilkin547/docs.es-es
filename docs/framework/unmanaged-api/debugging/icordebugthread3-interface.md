---
title: ICorDebugThread3 (Interfaz)
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1d34a3395605505ca0ebda072e33d8083d51123a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61902426"
---
# <a name="icordebugthread3-interface"></a><span data-ttu-id="63893-102">ICorDebugThread3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="63893-102">ICorDebugThread3 Interface</span></span>
<span data-ttu-id="63893-103">Proporciona el punto de entrada a la [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) y las interfaces correspondientes.</span><span class="sxs-lookup"><span data-stu-id="63893-103">Provides the entry point to the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) and corresponding interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="63893-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="63893-104">Methods</span></span>  
  
|<span data-ttu-id="63893-105">Método</span><span class="sxs-lookup"><span data-stu-id="63893-105">Method</span></span>|<span data-ttu-id="63893-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="63893-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="63893-107">CreateStackWalk (método)</span><span class="sxs-lookup"><span data-stu-id="63893-107">CreateStackWalk Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-createstackwalk-method.md)|<span data-ttu-id="63893-108">Crea un [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) objeto para el subproceso cuya pila desea desenredar.</span><span class="sxs-lookup"><span data-stu-id="63893-108">Creates an [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>|  
|[<span data-ttu-id="63893-109">GetActiveInternalFrames (método)</span><span class="sxs-lookup"><span data-stu-id="63893-109">GetActiveInternalFrames Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md)|<span data-ttu-id="63893-110">Devuelve una matriz de marcos internos ([ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) objetos) en la pila.</span><span class="sxs-lookup"><span data-stu-id="63893-110">Returns an array of internal frames ([ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) objects) on the stack.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="63893-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="63893-111">Remarks</span></span>  
 <span data-ttu-id="63893-112">`ICorDebugThread3` es una extensión lógica ICorDebugThread (interfaz).</span><span class="sxs-lookup"><span data-stu-id="63893-112">`ICorDebugThread3` is a logical extension to the ICorDebugThread interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="63893-113">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="63893-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63893-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="63893-114">Requirements</span></span>  
 <span data-ttu-id="63893-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63893-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63893-116">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="63893-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="63893-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="63893-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="63893-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63893-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63893-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="63893-119">See also</span></span>

- [<span data-ttu-id="63893-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="63893-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="63893-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="63893-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
