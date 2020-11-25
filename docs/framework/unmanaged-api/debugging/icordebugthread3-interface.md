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
ms.openlocfilehash: 015d0061e5be5bbc212243ca06f1d165abe4496a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729309"
---
# <a name="icordebugthread3-interface"></a><span data-ttu-id="8cdcb-102">ICorDebugThread3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8cdcb-102">ICorDebugThread3 Interface</span></span>

<span data-ttu-id="8cdcb-103">Proporciona el punto de entrada a [ICorDebugStackWalk](icordebugstackwalk-interface.md) y las interfaces correspondientes.</span><span class="sxs-lookup"><span data-stu-id="8cdcb-103">Provides the entry point to the [ICorDebugStackWalk](icordebugstackwalk-interface.md) and corresponding interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8cdcb-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="8cdcb-104">Methods</span></span>  
  
|<span data-ttu-id="8cdcb-105">Método</span><span class="sxs-lookup"><span data-stu-id="8cdcb-105">Method</span></span>|<span data-ttu-id="8cdcb-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="8cdcb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8cdcb-107">Método CreateStackWalk</span><span class="sxs-lookup"><span data-stu-id="8cdcb-107">CreateStackWalk Method</span></span>](icordebugthread3-createstackwalk-method.md)|<span data-ttu-id="8cdcb-108">Crea un objeto [ICorDebugStackWalk](icordebugstackwalk-interface.md) para el subproceso cuya pila desea desenredar.</span><span class="sxs-lookup"><span data-stu-id="8cdcb-108">Creates an [ICorDebugStackWalk](icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>|  
|[<span data-ttu-id="8cdcb-109">Método GetActiveInternalFrames</span><span class="sxs-lookup"><span data-stu-id="8cdcb-109">GetActiveInternalFrames Method</span></span>](icordebugthread3-getactiveinternalframes-method.md)|<span data-ttu-id="8cdcb-110">Devuelve una matriz de Marcos internos (objetos[ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) ) en la pila.</span><span class="sxs-lookup"><span data-stu-id="8cdcb-110">Returns an array of internal frames ([ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) objects) on the stack.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8cdcb-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8cdcb-111">Remarks</span></span>  

 <span data-ttu-id="8cdcb-112">`ICorDebugThread3` es una extensión lógica de la interfaz ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="8cdcb-112">`ICorDebugThread3` is a logical extension to the ICorDebugThread interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8cdcb-113">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="8cdcb-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8cdcb-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8cdcb-114">Requirements</span></span>  

 <span data-ttu-id="8cdcb-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8cdcb-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8cdcb-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8cdcb-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8cdcb-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8cdcb-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8cdcb-118">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8cdcb-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cdcb-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8cdcb-119">See also</span></span>

- [<span data-ttu-id="8cdcb-120">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="8cdcb-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="8cdcb-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="8cdcb-121">Debugging</span></span>](index.md)
