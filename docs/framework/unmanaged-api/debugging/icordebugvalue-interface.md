---
title: ICorDebugValue (Interfaz)
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
ms.openlocfilehash: 77d28d8eef97a934c15ac29725f856f4bf39e6ce
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140159"
---
# <a name="icordebugvalue-interface"></a><span data-ttu-id="17fc2-102">ICorDebugValue (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="17fc2-102">ICorDebugValue Interface</span></span>
<span data-ttu-id="17fc2-103">Representa un valor en el proceso que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="17fc2-103">Represents a value in the process being debugged.</span></span> <span data-ttu-id="17fc2-104">El valor puede ser un valor de lectura o de escritura.</span><span class="sxs-lookup"><span data-stu-id="17fc2-104">The value can be a read or a write value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="17fc2-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="17fc2-105">Methods</span></span>  
  
|<span data-ttu-id="17fc2-106">Método</span><span class="sxs-lookup"><span data-stu-id="17fc2-106">Method</span></span>|<span data-ttu-id="17fc2-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="17fc2-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="17fc2-108">CreateBreakpoint (método)</span><span class="sxs-lookup"><span data-stu-id="17fc2-108">CreateBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-createbreakpoint-method.md)|<span data-ttu-id="17fc2-109">Este método no está implementado actualmente.</span><span class="sxs-lookup"><span data-stu-id="17fc2-109">This method is not currently implemented.</span></span>|  
|[<span data-ttu-id="17fc2-110">GetAddress (método)</span><span class="sxs-lookup"><span data-stu-id="17fc2-110">GetAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md)|<span data-ttu-id="17fc2-111">Obtiene la dirección de este objeto `ICorDebugValue`, que se encuentra en el proceso de depuración.</span><span class="sxs-lookup"><span data-stu-id="17fc2-111">Gets the address of this `ICorDebugValue` object, which is in the process of being debugged.</span></span>|  
|[<span data-ttu-id="17fc2-112">GetSize (método)</span><span class="sxs-lookup"><span data-stu-id="17fc2-112">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md)|<span data-ttu-id="17fc2-113">Obtiene el tamaño, en bytes, de este objeto `ICorDebugValue`.</span><span class="sxs-lookup"><span data-stu-id="17fc2-113">Gets the size, in bytes, of this `ICorDebugValue` object.</span></span>|  
|[<span data-ttu-id="17fc2-114">GetType (método)</span><span class="sxs-lookup"><span data-stu-id="17fc2-114">GetType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md)|<span data-ttu-id="17fc2-115">Obtiene el tipo primitivo de este objeto `ICorDebugValue`.</span><span class="sxs-lookup"><span data-stu-id="17fc2-115">Gets the primitive type of this `ICorDebugValue` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="17fc2-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="17fc2-116">Remarks</span></span>  
 <span data-ttu-id="17fc2-117">En general, la propiedad de un objeto de valor se pasa cuando se devuelve.</span><span class="sxs-lookup"><span data-stu-id="17fc2-117">In general, ownership of a value object is passed when it is returned.</span></span> <span data-ttu-id="17fc2-118">El destinatario es responsable de quitar una referencia del objeto cuando ha terminado con el objeto.</span><span class="sxs-lookup"><span data-stu-id="17fc2-118">The recipient is responsible for removing a reference from the object when it is finished with the object.</span></span>  
  
 <span data-ttu-id="17fc2-119">Dependiendo de dónde se haya recuperado el valor, es posible que el valor no siga siendo válido después de que se reanude el proceso.</span><span class="sxs-lookup"><span data-stu-id="17fc2-119">Depending on where the value was retrieved from, the value may not remain valid after the process is resumed.</span></span> <span data-ttu-id="17fc2-120">Por lo tanto, en general, el valor no se debe mantener en una llamada del método [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) .</span><span class="sxs-lookup"><span data-stu-id="17fc2-120">So, in general, the value shouldn't be held across a call of the [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="17fc2-121">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="17fc2-121">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17fc2-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="17fc2-122">Requirements</span></span>  
 <span data-ttu-id="17fc2-123">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17fc2-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17fc2-124">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="17fc2-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="17fc2-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="17fc2-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="17fc2-126">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17fc2-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17fc2-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="17fc2-127">See also</span></span>

- [<span data-ttu-id="17fc2-128">ICorDebugValue3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="17fc2-128">ICorDebugValue3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)
- [<span data-ttu-id="17fc2-129">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="17fc2-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
