---
description: 'Más información acerca de: ICorDebugValue (interfaz)'
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
ms.openlocfilehash: cae8fdef5c1c49cbabc25d3d547cb5748a9eeee1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99690321"
---
# <a name="icordebugvalue-interface"></a><span data-ttu-id="5dc69-103">Interfaz ICorDebugValue</span><span class="sxs-lookup"><span data-stu-id="5dc69-103">ICorDebugValue Interface</span></span>

<span data-ttu-id="5dc69-104">Representa un valor en el proceso que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="5dc69-104">Represents a value in the process being debugged.</span></span> <span data-ttu-id="5dc69-105">El valor puede ser un valor de lectura o de escritura.</span><span class="sxs-lookup"><span data-stu-id="5dc69-105">The value can be a read or a write value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5dc69-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="5dc69-106">Methods</span></span>  
  
|<span data-ttu-id="5dc69-107">Método</span><span class="sxs-lookup"><span data-stu-id="5dc69-107">Method</span></span>|<span data-ttu-id="5dc69-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="5dc69-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5dc69-109">Método CreateBreakpoint</span><span class="sxs-lookup"><span data-stu-id="5dc69-109">CreateBreakpoint Method</span></span>](icordebugvalue-createbreakpoint-method.md)|<span data-ttu-id="5dc69-110">Este método no se encuentra implementado actualmente.</span><span class="sxs-lookup"><span data-stu-id="5dc69-110">This method is not currently implemented.</span></span>|  
|[<span data-ttu-id="5dc69-111">Método GetAddress</span><span class="sxs-lookup"><span data-stu-id="5dc69-111">GetAddress Method</span></span>](icordebugvalue-getaddress-method.md)|<span data-ttu-id="5dc69-112">Obtiene la dirección de este `ICorDebugValue` objeto, que se encuentra en el proceso de depuración.</span><span class="sxs-lookup"><span data-stu-id="5dc69-112">Gets the address of this `ICorDebugValue` object, which is in the process of being debugged.</span></span>|  
|[<span data-ttu-id="5dc69-113">Método GetSize</span><span class="sxs-lookup"><span data-stu-id="5dc69-113">GetSize Method</span></span>](icordebugvalue-getsize-method.md)|<span data-ttu-id="5dc69-114">Obtiene el tamaño, en bytes, de este `ICorDebugValue` objeto.</span><span class="sxs-lookup"><span data-stu-id="5dc69-114">Gets the size, in bytes, of this `ICorDebugValue` object.</span></span>|  
|[<span data-ttu-id="5dc69-115">Método GetType</span><span class="sxs-lookup"><span data-stu-id="5dc69-115">GetType Method</span></span>](icordebugvalue-gettype-method.md)|<span data-ttu-id="5dc69-116">Obtiene el tipo primitivo de este `ICorDebugValue` objeto.</span><span class="sxs-lookup"><span data-stu-id="5dc69-116">Gets the primitive type of this `ICorDebugValue` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5dc69-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5dc69-117">Remarks</span></span>  

 <span data-ttu-id="5dc69-118">En general, la propiedad de un objeto de valor se pasa cuando se devuelve.</span><span class="sxs-lookup"><span data-stu-id="5dc69-118">In general, ownership of a value object is passed when it is returned.</span></span> <span data-ttu-id="5dc69-119">El destinatario es responsable de quitar una referencia del objeto cuando ha terminado con el objeto.</span><span class="sxs-lookup"><span data-stu-id="5dc69-119">The recipient is responsible for removing a reference from the object when it is finished with the object.</span></span>  
  
 <span data-ttu-id="5dc69-120">Dependiendo de dónde se haya recuperado el valor, es posible que el valor no siga siendo válido después de que se reanude el proceso.</span><span class="sxs-lookup"><span data-stu-id="5dc69-120">Depending on where the value was retrieved from, the value may not remain valid after the process is resumed.</span></span> <span data-ttu-id="5dc69-121">Por lo tanto, en general, el valor no se debe mantener en una llamada del método [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) .</span><span class="sxs-lookup"><span data-stu-id="5dc69-121">So, in general, the value shouldn't be held across a call of the [ICorDebugController::Continue](icordebugcontroller-continue-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5dc69-122">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="5dc69-122">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5dc69-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5dc69-123">Requirements</span></span>  

 <span data-ttu-id="5dc69-124">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5dc69-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5dc69-125">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5dc69-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5dc69-126">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5dc69-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5dc69-127">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5dc69-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5dc69-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="5dc69-128">See also</span></span>

- [<span data-ttu-id="5dc69-129">ICorDebugValue3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5dc69-129">ICorDebugValue3 Interface</span></span>](icordebugvalue3-interface.md)
- [<span data-ttu-id="5dc69-130">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="5dc69-130">Debugging Interfaces</span></span>](debugging-interfaces.md)
