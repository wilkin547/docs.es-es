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
ms.openlocfilehash: dc556dfb59e999ed9b7fc5f35c603dc26c35f314
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378705"
---
# <a name="icordebugthread3-interface"></a><span data-ttu-id="141c3-102">ICorDebugThread3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="141c3-102">ICorDebugThread3 Interface</span></span>
<span data-ttu-id="141c3-103">Proporciona el punto de entrada a [ICorDebugStackWalk](icordebugstackwalk-interface.md) y las interfaces correspondientes.</span><span class="sxs-lookup"><span data-stu-id="141c3-103">Provides the entry point to the [ICorDebugStackWalk](icordebugstackwalk-interface.md) and corresponding interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="141c3-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="141c3-104">Methods</span></span>  
  
|<span data-ttu-id="141c3-105">Método</span><span class="sxs-lookup"><span data-stu-id="141c3-105">Method</span></span>|<span data-ttu-id="141c3-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="141c3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="141c3-107">Método CreateStackWalk</span><span class="sxs-lookup"><span data-stu-id="141c3-107">CreateStackWalk Method</span></span>](icordebugthread3-createstackwalk-method.md)|<span data-ttu-id="141c3-108">Crea un objeto [ICorDebugStackWalk](icordebugstackwalk-interface.md) para el subproceso cuya pila desea desenredar.</span><span class="sxs-lookup"><span data-stu-id="141c3-108">Creates an [ICorDebugStackWalk](icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>|  
|[<span data-ttu-id="141c3-109">Método GetActiveInternalFrames</span><span class="sxs-lookup"><span data-stu-id="141c3-109">GetActiveInternalFrames Method</span></span>](icordebugthread3-getactiveinternalframes-method.md)|<span data-ttu-id="141c3-110">Devuelve una matriz de Marcos internos (objetos[ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) ) en la pila.</span><span class="sxs-lookup"><span data-stu-id="141c3-110">Returns an array of internal frames ([ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) objects) on the stack.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="141c3-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="141c3-111">Remarks</span></span>  
 <span data-ttu-id="141c3-112">`ICorDebugThread3`es una extensión lógica de la interfaz ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="141c3-112">`ICorDebugThread3` is a logical extension to the ICorDebugThread interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="141c3-113">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="141c3-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="141c3-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="141c3-114">Requirements</span></span>  
 <span data-ttu-id="141c3-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="141c3-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="141c3-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="141c3-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="141c3-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="141c3-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="141c3-118">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="141c3-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="141c3-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="141c3-119">See also</span></span>

- [<span data-ttu-id="141c3-120">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="141c3-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="141c3-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="141c3-121">Debugging</span></span>](index.md)
