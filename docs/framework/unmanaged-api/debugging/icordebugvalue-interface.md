---
title: Interfaz ICorDebugValue
ms.date: 03/30/2017
api_name:
- ICorDebugValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue
helpviewer_keywords:
- ICorDebugValue interface [.NET Framework debugging]
ms.assetid: b2f7007f-c446-4b18-aed1-a25cff8aee31
topic_type:
- apiref
ms.openlocfilehash: 7d3c35ed6cda637e3b885afe089ddfa590d51076
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683620"
---
# <a name="icordebugvalue-interface"></a><span data-ttu-id="7fb40-102">Interfaz ICorDebugValue</span><span class="sxs-lookup"><span data-stu-id="7fb40-102">ICorDebugValue Interface</span></span>

<span data-ttu-id="7fb40-103">Representa un valor en el proceso que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="7fb40-103">Represents a value in the process being debugged.</span></span> <span data-ttu-id="7fb40-104">El valor puede ser un valor de lectura o de escritura.</span><span class="sxs-lookup"><span data-stu-id="7fb40-104">The value can be a read or a write value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7fb40-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="7fb40-105">Methods</span></span>  
  
|<span data-ttu-id="7fb40-106">Método</span><span class="sxs-lookup"><span data-stu-id="7fb40-106">Method</span></span>|<span data-ttu-id="7fb40-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="7fb40-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7fb40-108">Método CreateBreakpoint</span><span class="sxs-lookup"><span data-stu-id="7fb40-108">CreateBreakpoint Method</span></span>](icordebugvalue-createbreakpoint-method.md)|<span data-ttu-id="7fb40-109">Este método no se encuentra implementado actualmente.</span><span class="sxs-lookup"><span data-stu-id="7fb40-109">This method is not currently implemented.</span></span>|  
|[<span data-ttu-id="7fb40-110">Método GetAddress</span><span class="sxs-lookup"><span data-stu-id="7fb40-110">GetAddress Method</span></span>](icordebugvalue-getaddress-method.md)|<span data-ttu-id="7fb40-111">Obtiene la dirección de este `ICorDebugValue` objeto, que se encuentra en el proceso de depuración.</span><span class="sxs-lookup"><span data-stu-id="7fb40-111">Gets the address of this `ICorDebugValue` object, which is in the process of being debugged.</span></span>|  
|[<span data-ttu-id="7fb40-112">Método GetSize</span><span class="sxs-lookup"><span data-stu-id="7fb40-112">GetSize Method</span></span>](icordebugvalue-getsize-method.md)|<span data-ttu-id="7fb40-113">Obtiene el tamaño, en bytes, de este `ICorDebugValue` objeto.</span><span class="sxs-lookup"><span data-stu-id="7fb40-113">Gets the size, in bytes, of this `ICorDebugValue` object.</span></span>|  
|[<span data-ttu-id="7fb40-114">Método GetType</span><span class="sxs-lookup"><span data-stu-id="7fb40-114">GetType Method</span></span>](icordebugvalue-gettype-method.md)|<span data-ttu-id="7fb40-115">Obtiene el tipo primitivo de este `ICorDebugValue` objeto.</span><span class="sxs-lookup"><span data-stu-id="7fb40-115">Gets the primitive type of this `ICorDebugValue` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7fb40-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7fb40-116">Remarks</span></span>  

 <span data-ttu-id="7fb40-117">En general, la propiedad de un objeto de valor se pasa cuando se devuelve.</span><span class="sxs-lookup"><span data-stu-id="7fb40-117">In general, ownership of a value object is passed when it is returned.</span></span> <span data-ttu-id="7fb40-118">El destinatario es responsable de quitar una referencia del objeto cuando ha terminado con el objeto.</span><span class="sxs-lookup"><span data-stu-id="7fb40-118">The recipient is responsible for removing a reference from the object when it is finished with the object.</span></span>  
  
 <span data-ttu-id="7fb40-119">Dependiendo de dónde se haya recuperado el valor, es posible que el valor no siga siendo válido después de que se reanude el proceso.</span><span class="sxs-lookup"><span data-stu-id="7fb40-119">Depending on where the value was retrieved from, the value may not remain valid after the process is resumed.</span></span> <span data-ttu-id="7fb40-120">Por lo tanto, en general, el valor no se debe mantener en una llamada del método [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) .</span><span class="sxs-lookup"><span data-stu-id="7fb40-120">So, in general, the value shouldn't be held across a call of the [ICorDebugController::Continue](icordebugcontroller-continue-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7fb40-121">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="7fb40-121">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7fb40-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7fb40-122">Requirements</span></span>  

 <span data-ttu-id="7fb40-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7fb40-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7fb40-124">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7fb40-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7fb40-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7fb40-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7fb40-126">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7fb40-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fb40-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7fb40-127">See also</span></span>

- [<span data-ttu-id="7fb40-128">ICorDebugValue3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7fb40-128">ICorDebugValue3 Interface</span></span>](icordebugvalue3-interface.md)
- [<span data-ttu-id="7fb40-129">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="7fb40-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
