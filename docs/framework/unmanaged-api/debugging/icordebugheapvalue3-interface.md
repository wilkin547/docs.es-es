---
description: 'Más información acerca de: interfaz ICorDebugHeapValue3'
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
ms.openlocfilehash: 2483f74e2cfc105fd23c37af6ada467f17b9556b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791470"
---
# <a name="icordebugheapvalue3-interface"></a><span data-ttu-id="3bb08-103">ICorDebugHeapValue3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3bb08-103">ICorDebugHeapValue3 Interface</span></span>

<span data-ttu-id="3bb08-104">Expone las propiedades de bloqueo de monitor de objetos.</span><span class="sxs-lookup"><span data-stu-id="3bb08-104">Exposes the monitor lock properties of objects.</span></span> <span data-ttu-id="3bb08-105">Esta interfaz extiende las interfaces ICorDebugHeapValue e Icordebugheapvalue2 (.</span><span class="sxs-lookup"><span data-stu-id="3bb08-105">This interface extends the ICorDebugHeapValue and ICorDebugHeapValue2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3bb08-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="3bb08-106">Methods</span></span>  
  
|<span data-ttu-id="3bb08-107">Método</span><span class="sxs-lookup"><span data-stu-id="3bb08-107">Method</span></span>|<span data-ttu-id="3bb08-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="3bb08-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3bb08-109">Método GetThreadOwningMonitorLock</span><span class="sxs-lookup"><span data-stu-id="3bb08-109">GetThreadOwningMonitorLock Method</span></span>](icordebugheapvalue3-getthreadowningmonitorlock-method.md)|<span data-ttu-id="3bb08-110">Devuelve el subproceso administrado que posee el bloqueo de monitor en este objeto.</span><span class="sxs-lookup"><span data-stu-id="3bb08-110">Returns the managed thread that owns the monitor lock on this object.</span></span>|  
|[<span data-ttu-id="3bb08-111">Método GetMonitorEventWaitList</span><span class="sxs-lookup"><span data-stu-id="3bb08-111">GetMonitorEventWaitList Method</span></span>](icordebugheapvalue3-getmonitoreventwaitlist-method.md)|<span data-ttu-id="3bb08-112">Proporciona una lista ordenada de subprocesos que se ponen en cola en el evento que está asociado a un bloqueo de monitor.</span><span class="sxs-lookup"><span data-stu-id="3bb08-112">Provides an ordered list of threads that are queued on the event that is associated with a monitor lock.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3bb08-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3bb08-113">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3bb08-114">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="3bb08-114">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3bb08-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3bb08-115">Requirements</span></span>  

 <span data-ttu-id="3bb08-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3bb08-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3bb08-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3bb08-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3bb08-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3bb08-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3bb08-119">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3bb08-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bb08-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="3bb08-120">See also</span></span>

- [<span data-ttu-id="3bb08-121">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="3bb08-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="3bb08-122">Depuración</span><span class="sxs-lookup"><span data-stu-id="3bb08-122">Debugging</span></span>](index.md)
