---
title: ICorDebugValue Interfaz1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c3464b4ad963b2fe764cefc5868440b7748f8c4d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugvalue-interface1"></a><span data-ttu-id="6806b-102">ICorDebugValue Interfaz1</span><span class="sxs-lookup"><span data-stu-id="6806b-102">ICorDebugValue Interface1</span></span>
<span data-ttu-id="6806b-103">Representa un valor en el proceso que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="6806b-103">Represents a value in the process being debugged.</span></span> <span data-ttu-id="6806b-104">El valor puede ser un valor de escritura o lectura.</span><span class="sxs-lookup"><span data-stu-id="6806b-104">The value can be a read or a write value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6806b-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="6806b-105">Methods</span></span>  
  
|<span data-ttu-id="6806b-106">Método</span><span class="sxs-lookup"><span data-stu-id="6806b-106">Method</span></span>|<span data-ttu-id="6806b-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="6806b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6806b-108">CreateBreakpoint (método)</span><span class="sxs-lookup"><span data-stu-id="6806b-108">CreateBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-createbreakpoint-method.md)|<span data-ttu-id="6806b-109">Este método no está implementado actualmente.</span><span class="sxs-lookup"><span data-stu-id="6806b-109">This method is not currently implemented.</span></span>|  
|[<span data-ttu-id="6806b-110">GetAddress (método)</span><span class="sxs-lookup"><span data-stu-id="6806b-110">GetAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md)|<span data-ttu-id="6806b-111">Obtiene la dirección de este `ICorDebugValue` objeto, que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="6806b-111">Gets the address of this `ICorDebugValue` object, which is in the process of being debugged.</span></span>|  
|[<span data-ttu-id="6806b-112">GetSize (método)</span><span class="sxs-lookup"><span data-stu-id="6806b-112">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md)|<span data-ttu-id="6806b-113">Obtiene el tamaño, en bytes, de este `ICorDebugValue` objeto.</span><span class="sxs-lookup"><span data-stu-id="6806b-113">Gets the size, in bytes, of this `ICorDebugValue` object.</span></span>|  
|[<span data-ttu-id="6806b-114">GetType (método)</span><span class="sxs-lookup"><span data-stu-id="6806b-114">GetType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md)|<span data-ttu-id="6806b-115">Obtiene el tipo primitivo de este `ICorDebugValue` objeto.</span><span class="sxs-lookup"><span data-stu-id="6806b-115">Gets the primitive type of this `ICorDebugValue` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6806b-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6806b-116">Remarks</span></span>  
 <span data-ttu-id="6806b-117">En general, la propiedad de un objeto de valor se pasa cuando se devuelve.</span><span class="sxs-lookup"><span data-stu-id="6806b-117">In general, ownership of a value object is passed when it is returned.</span></span> <span data-ttu-id="6806b-118">El destinatario es responsable de quitar una referencia del objeto cuando haya terminado con el objeto.</span><span class="sxs-lookup"><span data-stu-id="6806b-118">The recipient is responsible for removing a reference from the object when it is finished with the object.</span></span>  
  
 <span data-ttu-id="6806b-119">Dependiendo de dónde se recupera el valor de, el valor puede no sigue siendo válido después de que se reanude el proceso.</span><span class="sxs-lookup"><span data-stu-id="6806b-119">Depending on where the value was retrieved from, the value may not remain valid after the process is resumed.</span></span> <span data-ttu-id="6806b-120">Por lo tanto, en general, el valor no debe ser mantenido a lo largo de una llamada de la [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="6806b-120">So, in general, the value shouldn't be held across a call of the [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6806b-121">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="6806b-121">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6806b-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6806b-122">Requirements</span></span>  
 <span data-ttu-id="6806b-123">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6806b-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6806b-124">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6806b-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6806b-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6806b-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6806b-126">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6806b-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6806b-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="6806b-127">See Also</span></span>  
    
    
    
    
 [<span data-ttu-id="6806b-128">ICorDebugValue3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6806b-128">ICorDebugValue3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)  
 [<span data-ttu-id="6806b-129">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="6806b-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
