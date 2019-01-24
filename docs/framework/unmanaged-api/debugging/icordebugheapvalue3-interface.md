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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 08a9bc8aa4aa70ad6b01c58abccd145ae43d8a52
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54568303"
---
# <a name="icordebugheapvalue3-interface"></a><span data-ttu-id="44c53-102">ICorDebugHeapValue3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="44c53-102">ICorDebugHeapValue3 Interface</span></span>
<span data-ttu-id="44c53-103">Expone las propiedades de bloqueo de monitor de objetos.</span><span class="sxs-lookup"><span data-stu-id="44c53-103">Exposes the monitor lock properties of objects.</span></span> <span data-ttu-id="44c53-104">Esta interfaz extiende las interfaces del ICorDebugHeapValue y ICorDebugHeapValue2.</span><span class="sxs-lookup"><span data-stu-id="44c53-104">This interface extends the ICorDebugHeapValue and ICorDebugHeapValue2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="44c53-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="44c53-105">Methods</span></span>  
  
|<span data-ttu-id="44c53-106">Método</span><span class="sxs-lookup"><span data-stu-id="44c53-106">Method</span></span>|<span data-ttu-id="44c53-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="44c53-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="44c53-108">GetThreadOwningMonitorLock (método)</span><span class="sxs-lookup"><span data-stu-id="44c53-108">GetThreadOwningMonitorLock Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-getthreadowningmonitorlock-method.md)|<span data-ttu-id="44c53-109">Devuelve el subproceso administrado que posee el bloqueo de monitor en este objeto.</span><span class="sxs-lookup"><span data-stu-id="44c53-109">Returns the managed thread that owns the monitor lock on this object.</span></span>|  
|[<span data-ttu-id="44c53-110">GetMonitorEventWaitList (método)</span><span class="sxs-lookup"><span data-stu-id="44c53-110">GetMonitorEventWaitList Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-getmonitoreventwaitlist-method.md)|<span data-ttu-id="44c53-111">Proporciona una lista ordenada de subprocesos que se ponen en cola en el evento que está asociado a un bloqueo de monitor.</span><span class="sxs-lookup"><span data-stu-id="44c53-111">Provides an ordered list of threads that are queued on the event that is associated with a monitor lock.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="44c53-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="44c53-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="44c53-113">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="44c53-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44c53-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="44c53-114">Requirements</span></span>  
 <span data-ttu-id="44c53-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44c53-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44c53-116">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="44c53-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="44c53-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="44c53-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="44c53-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44c53-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44c53-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="44c53-119">See also</span></span>
- [<span data-ttu-id="44c53-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="44c53-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="44c53-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="44c53-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
