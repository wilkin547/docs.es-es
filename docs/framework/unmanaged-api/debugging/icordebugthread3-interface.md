---
description: 'Más información acerca de: interfaz ICorDebugThread3'
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
ms.openlocfilehash: 88c668f1e08d0843f26d231937c85d80e03bee6e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800973"
---
# <a name="icordebugthread3-interface"></a><span data-ttu-id="1f561-103">ICorDebugThread3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1f561-103">ICorDebugThread3 Interface</span></span>

<span data-ttu-id="1f561-104">Proporciona el punto de entrada a [ICorDebugStackWalk](icordebugstackwalk-interface.md) y las interfaces correspondientes.</span><span class="sxs-lookup"><span data-stu-id="1f561-104">Provides the entry point to the [ICorDebugStackWalk](icordebugstackwalk-interface.md) and corresponding interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1f561-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="1f561-105">Methods</span></span>  
  
|<span data-ttu-id="1f561-106">Método</span><span class="sxs-lookup"><span data-stu-id="1f561-106">Method</span></span>|<span data-ttu-id="1f561-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="1f561-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1f561-108">Método CreateStackWalk</span><span class="sxs-lookup"><span data-stu-id="1f561-108">CreateStackWalk Method</span></span>](icordebugthread3-createstackwalk-method.md)|<span data-ttu-id="1f561-109">Crea un objeto [ICorDebugStackWalk](icordebugstackwalk-interface.md) para el subproceso cuya pila desea desenredar.</span><span class="sxs-lookup"><span data-stu-id="1f561-109">Creates an [ICorDebugStackWalk](icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>|  
|[<span data-ttu-id="1f561-110">Método GetActiveInternalFrames</span><span class="sxs-lookup"><span data-stu-id="1f561-110">GetActiveInternalFrames Method</span></span>](icordebugthread3-getactiveinternalframes-method.md)|<span data-ttu-id="1f561-111">Devuelve una matriz de Marcos internos (objetos[ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) ) en la pila.</span><span class="sxs-lookup"><span data-stu-id="1f561-111">Returns an array of internal frames ([ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) objects) on the stack.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1f561-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1f561-112">Remarks</span></span>  

 <span data-ttu-id="1f561-113">`ICorDebugThread3` es una extensión lógica de la interfaz ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="1f561-113">`ICorDebugThread3` is a logical extension to the ICorDebugThread interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1f561-114">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="1f561-114">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f561-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1f561-115">Requirements</span></span>  

 <span data-ttu-id="1f561-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1f561-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f561-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1f561-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1f561-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1f561-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1f561-119">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f561-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f561-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="1f561-120">See also</span></span>

- [<span data-ttu-id="1f561-121">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="1f561-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="1f561-122">Depuración</span><span class="sxs-lookup"><span data-stu-id="1f561-122">Debugging</span></span>](index.md)
