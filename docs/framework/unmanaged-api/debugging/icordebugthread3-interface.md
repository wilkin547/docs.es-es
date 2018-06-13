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
ms.openlocfilehash: c9cb9217282af53d9788190844e4e52d5405ee2a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422781"
---
# <a name="icordebugthread3-interface"></a><span data-ttu-id="1c6c2-102">ICorDebugThread3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1c6c2-102">ICorDebugThread3 Interface</span></span>
<span data-ttu-id="1c6c2-103">Proporciona el punto de entrada a la [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) y las interfaces correspondientes.</span><span class="sxs-lookup"><span data-stu-id="1c6c2-103">Provides the entry point to the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) and corresponding interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1c6c2-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="1c6c2-104">Methods</span></span>  
  
|<span data-ttu-id="1c6c2-105">Método</span><span class="sxs-lookup"><span data-stu-id="1c6c2-105">Method</span></span>|<span data-ttu-id="1c6c2-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="1c6c2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1c6c2-107">CreateStackWalk (método)</span><span class="sxs-lookup"><span data-stu-id="1c6c2-107">CreateStackWalk Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-createstackwalk-method.md)|<span data-ttu-id="1c6c2-108">Crea un [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) objeto para el subproceso cuya pila desea desenredar.</span><span class="sxs-lookup"><span data-stu-id="1c6c2-108">Creates an [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>|  
|[<span data-ttu-id="1c6c2-109">GetActiveInternalFrames (método)</span><span class="sxs-lookup"><span data-stu-id="1c6c2-109">GetActiveInternalFrames Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md)|<span data-ttu-id="1c6c2-110">Devuelve una matriz de marcos internos ([ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) objetos) en la pila.</span><span class="sxs-lookup"><span data-stu-id="1c6c2-110">Returns an array of internal frames ([ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) objects) on the stack.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1c6c2-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1c6c2-111">Remarks</span></span>  
 <span data-ttu-id="1c6c2-112">`ICorDebugThread3` es una extensión lógica ICorDebugThread (interfaz).</span><span class="sxs-lookup"><span data-stu-id="1c6c2-112">`ICorDebugThread3` is a logical extension to the ICorDebugThread interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1c6c2-113">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="1c6c2-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c6c2-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1c6c2-114">Requirements</span></span>  
 <span data-ttu-id="1c6c2-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c6c2-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c6c2-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1c6c2-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1c6c2-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1c6c2-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1c6c2-118">**Versiones de .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c6c2-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c6c2-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="1c6c2-119">See Also</span></span>  
 [<span data-ttu-id="1c6c2-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="1c6c2-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="1c6c2-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="1c6c2-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
