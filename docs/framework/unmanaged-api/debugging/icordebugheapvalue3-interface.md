---
title: ICorDebugHeapValue3 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue3
helpviewer_keywords:
- ICorDebugHeapValue3 interface [.NET Framework debugging]
ms.assetid: 9c421bb0-e647-4b2d-a986-f3d578cc7f20
topic_type:
- apiref
ms.openlocfilehash: a1f4964c89aa3b658c57946d4b5a0327797118f1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728711"
---
# <a name="icordebugheapvalue3-interface"></a><span data-ttu-id="9d1f1-102">ICorDebugHeapValue3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9d1f1-102">ICorDebugHeapValue3 Interface</span></span>

<span data-ttu-id="9d1f1-103">Expone las propiedades de bloqueo de monitor de objetos.</span><span class="sxs-lookup"><span data-stu-id="9d1f1-103">Exposes the monitor lock properties of objects.</span></span> <span data-ttu-id="9d1f1-104">Esta interfaz extiende las interfaces ICorDebugHeapValue e Icordebugheapvalue2 (.</span><span class="sxs-lookup"><span data-stu-id="9d1f1-104">This interface extends the ICorDebugHeapValue and ICorDebugHeapValue2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9d1f1-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="9d1f1-105">Methods</span></span>  
  
|<span data-ttu-id="9d1f1-106">Método</span><span class="sxs-lookup"><span data-stu-id="9d1f1-106">Method</span></span>|<span data-ttu-id="9d1f1-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="9d1f1-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9d1f1-108">Método GetThreadOwningMonitorLock</span><span class="sxs-lookup"><span data-stu-id="9d1f1-108">GetThreadOwningMonitorLock Method</span></span>](icordebugheapvalue3-getthreadowningmonitorlock-method.md)|<span data-ttu-id="9d1f1-109">Devuelve el subproceso administrado que posee el bloqueo de monitor en este objeto.</span><span class="sxs-lookup"><span data-stu-id="9d1f1-109">Returns the managed thread that owns the monitor lock on this object.</span></span>|  
|[<span data-ttu-id="9d1f1-110">Método GetMonitorEventWaitList</span><span class="sxs-lookup"><span data-stu-id="9d1f1-110">GetMonitorEventWaitList Method</span></span>](icordebugheapvalue3-getmonitoreventwaitlist-method.md)|<span data-ttu-id="9d1f1-111">Proporciona una lista ordenada de subprocesos que se ponen en cola en el evento que está asociado a un bloqueo de monitor.</span><span class="sxs-lookup"><span data-stu-id="9d1f1-111">Provides an ordered list of threads that are queued on the event that is associated with a monitor lock.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9d1f1-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9d1f1-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9d1f1-113">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="9d1f1-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d1f1-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9d1f1-114">Requirements</span></span>  

 <span data-ttu-id="9d1f1-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d1f1-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d1f1-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9d1f1-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9d1f1-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9d1f1-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9d1f1-118">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d1f1-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d1f1-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9d1f1-119">See also</span></span>

- [<span data-ttu-id="9d1f1-120">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="9d1f1-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="9d1f1-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="9d1f1-121">Debugging</span></span>](index.md)
