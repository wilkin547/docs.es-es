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
ms.openlocfilehash: 7cddf860f044e8493a0fdf6023b2853ac16c5b14
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137504"
---
# <a name="icordebugthread3-interface"></a><span data-ttu-id="c424b-102">ICorDebugThread3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c424b-102">ICorDebugThread3 Interface</span></span>
<span data-ttu-id="c424b-103">Proporciona el punto de entrada a [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) y las interfaces correspondientes.</span><span class="sxs-lookup"><span data-stu-id="c424b-103">Provides the entry point to the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) and corresponding interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c424b-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="c424b-104">Methods</span></span>  
  
|<span data-ttu-id="c424b-105">Método</span><span class="sxs-lookup"><span data-stu-id="c424b-105">Method</span></span>|<span data-ttu-id="c424b-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="c424b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c424b-107">CreateStackWalk (método)</span><span class="sxs-lookup"><span data-stu-id="c424b-107">CreateStackWalk Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-createstackwalk-method.md)|<span data-ttu-id="c424b-108">Crea un objeto [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) para el subproceso cuya pila desea desenredar.</span><span class="sxs-lookup"><span data-stu-id="c424b-108">Creates an [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>|  
|[<span data-ttu-id="c424b-109">GetActiveInternalFrames (método)</span><span class="sxs-lookup"><span data-stu-id="c424b-109">GetActiveInternalFrames Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md)|<span data-ttu-id="c424b-110">Devuelve una matriz de Marcos internos (objetos[ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) ) en la pila.</span><span class="sxs-lookup"><span data-stu-id="c424b-110">Returns an array of internal frames ([ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) objects) on the stack.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c424b-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c424b-111">Remarks</span></span>  
 <span data-ttu-id="c424b-112">`ICorDebugThread3` es una extensión lógica de la interfaz ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="c424b-112">`ICorDebugThread3` is a logical extension to the ICorDebugThread interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c424b-113">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="c424b-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c424b-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c424b-114">Requirements</span></span>  
 <span data-ttu-id="c424b-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c424b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c424b-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c424b-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c424b-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c424b-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c424b-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c424b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c424b-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="c424b-119">See also</span></span>

- [<span data-ttu-id="c424b-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="c424b-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="c424b-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="c424b-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
