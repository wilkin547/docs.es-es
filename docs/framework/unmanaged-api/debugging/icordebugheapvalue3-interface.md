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
ms.openlocfilehash: 5add6da1ace372ecf6e513902bbf98f5f79c6778
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210402"
---
# <a name="icordebugheapvalue3-interface"></a><span data-ttu-id="3bb91-102">ICorDebugHeapValue3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3bb91-102">ICorDebugHeapValue3 Interface</span></span>
<span data-ttu-id="3bb91-103">Expone las propiedades de bloqueo de monitor de objetos.</span><span class="sxs-lookup"><span data-stu-id="3bb91-103">Exposes the monitor lock properties of objects.</span></span> <span data-ttu-id="3bb91-104">Esta interfaz extiende las interfaces ICorDebugHeapValue e Icordebugheapvalue2 (.</span><span class="sxs-lookup"><span data-stu-id="3bb91-104">This interface extends the ICorDebugHeapValue and ICorDebugHeapValue2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3bb91-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="3bb91-105">Methods</span></span>  
  
|<span data-ttu-id="3bb91-106">Método</span><span class="sxs-lookup"><span data-stu-id="3bb91-106">Method</span></span>|<span data-ttu-id="3bb91-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="3bb91-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3bb91-108">Método GetThreadOwningMonitorLock</span><span class="sxs-lookup"><span data-stu-id="3bb91-108">GetThreadOwningMonitorLock Method</span></span>](icordebugheapvalue3-getthreadowningmonitorlock-method.md)|<span data-ttu-id="3bb91-109">Devuelve el subproceso administrado que posee el bloqueo de monitor en este objeto.</span><span class="sxs-lookup"><span data-stu-id="3bb91-109">Returns the managed thread that owns the monitor lock on this object.</span></span>|  
|[<span data-ttu-id="3bb91-110">Método GetMonitorEventWaitList</span><span class="sxs-lookup"><span data-stu-id="3bb91-110">GetMonitorEventWaitList Method</span></span>](icordebugheapvalue3-getmonitoreventwaitlist-method.md)|<span data-ttu-id="3bb91-111">Proporciona una lista ordenada de subprocesos que se ponen en cola en el evento que está asociado a un bloqueo de monitor.</span><span class="sxs-lookup"><span data-stu-id="3bb91-111">Provides an ordered list of threads that are queued on the event that is associated with a monitor lock.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3bb91-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3bb91-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3bb91-113">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="3bb91-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3bb91-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3bb91-114">Requirements</span></span>  
 <span data-ttu-id="3bb91-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3bb91-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3bb91-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3bb91-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3bb91-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3bb91-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3bb91-118">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3bb91-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bb91-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3bb91-119">See also</span></span>

- [<span data-ttu-id="3bb91-120">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="3bb91-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="3bb91-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="3bb91-121">Debugging</span></span>](index.md)
