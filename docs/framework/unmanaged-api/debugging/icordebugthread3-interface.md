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
ms.openlocfilehash: 9622716e3a2cca7e3af0b1e1b134458a50ad1bec
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962978"
---
# <a name="icordebugthread3-interface"></a><span data-ttu-id="b98bd-102">ICorDebugThread3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b98bd-102">ICorDebugThread3 Interface</span></span>
<span data-ttu-id="b98bd-103">Proporciona el punto de entrada a [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) y las interfaces correspondientes.</span><span class="sxs-lookup"><span data-stu-id="b98bd-103">Provides the entry point to the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) and corresponding interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b98bd-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="b98bd-104">Methods</span></span>  
  
|<span data-ttu-id="b98bd-105">Método</span><span class="sxs-lookup"><span data-stu-id="b98bd-105">Method</span></span>|<span data-ttu-id="b98bd-106">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b98bd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b98bd-107">CreateStackWalk (método)</span><span class="sxs-lookup"><span data-stu-id="b98bd-107">CreateStackWalk Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-createstackwalk-method.md)|<span data-ttu-id="b98bd-108">Crea un objeto [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) para el subproceso cuya pila desea desenredar.</span><span class="sxs-lookup"><span data-stu-id="b98bd-108">Creates an [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>|  
|[<span data-ttu-id="b98bd-109">GetActiveInternalFrames (método)</span><span class="sxs-lookup"><span data-stu-id="b98bd-109">GetActiveInternalFrames Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md)|<span data-ttu-id="b98bd-110">Devuelve una matriz de Marcos internos (objetos[ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) ) en la pila.</span><span class="sxs-lookup"><span data-stu-id="b98bd-110">Returns an array of internal frames ([ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) objects) on the stack.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b98bd-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b98bd-111">Remarks</span></span>  
 <span data-ttu-id="b98bd-112">`ICorDebugThread3`es una extensión lógica de la interfaz ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="b98bd-112">`ICorDebugThread3` is a logical extension to the ICorDebugThread interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b98bd-113">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="b98bd-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b98bd-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b98bd-114">Requirements</span></span>  
 <span data-ttu-id="b98bd-115">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b98bd-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b98bd-116">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="b98bd-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b98bd-117">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b98bd-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b98bd-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b98bd-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b98bd-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="b98bd-119">See also</span></span>

- [<span data-ttu-id="b98bd-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="b98bd-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="b98bd-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="b98bd-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
