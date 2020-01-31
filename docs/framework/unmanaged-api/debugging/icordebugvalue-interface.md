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
ms.openlocfilehash: e1044386bd6251132703c4e98a0cf2ed267d34e0
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791138"
---
# <a name="icordebugvalue-interface"></a><span data-ttu-id="7242d-102">Interfaz ICorDebugValue</span><span class="sxs-lookup"><span data-stu-id="7242d-102">ICorDebugValue Interface</span></span>
<span data-ttu-id="7242d-103">Representa un valor en el proceso que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="7242d-103">Represents a value in the process being debugged.</span></span> <span data-ttu-id="7242d-104">El valor puede ser un valor de lectura o de escritura.</span><span class="sxs-lookup"><span data-stu-id="7242d-104">The value can be a read or a write value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7242d-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="7242d-105">Methods</span></span>  
  
|<span data-ttu-id="7242d-106">Método</span><span class="sxs-lookup"><span data-stu-id="7242d-106">Method</span></span>|<span data-ttu-id="7242d-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="7242d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7242d-108">CreateBreakpoint (método)</span><span class="sxs-lookup"><span data-stu-id="7242d-108">CreateBreakpoint Method</span></span>](icordebugvalue-createbreakpoint-method.md)|<span data-ttu-id="7242d-109">Este método no se encuentra implementado actualmente.</span><span class="sxs-lookup"><span data-stu-id="7242d-109">This method is not currently implemented.</span></span>|  
|[<span data-ttu-id="7242d-110">GetAddress (método)</span><span class="sxs-lookup"><span data-stu-id="7242d-110">GetAddress Method</span></span>](icordebugvalue-getaddress-method.md)|<span data-ttu-id="7242d-111">Obtiene la dirección de este objeto `ICorDebugValue`, que se encuentra en el proceso de depuración.</span><span class="sxs-lookup"><span data-stu-id="7242d-111">Gets the address of this `ICorDebugValue` object, which is in the process of being debugged.</span></span>|  
|[<span data-ttu-id="7242d-112">GetSize (método)</span><span class="sxs-lookup"><span data-stu-id="7242d-112">GetSize Method</span></span>](icordebugvalue-getsize-method.md)|<span data-ttu-id="7242d-113">Obtiene el tamaño, en bytes, de este objeto `ICorDebugValue`.</span><span class="sxs-lookup"><span data-stu-id="7242d-113">Gets the size, in bytes, of this `ICorDebugValue` object.</span></span>|  
|[<span data-ttu-id="7242d-114">GetType (método)</span><span class="sxs-lookup"><span data-stu-id="7242d-114">GetType Method</span></span>](icordebugvalue-gettype-method.md)|<span data-ttu-id="7242d-115">Obtiene el tipo primitivo de este objeto `ICorDebugValue`.</span><span class="sxs-lookup"><span data-stu-id="7242d-115">Gets the primitive type of this `ICorDebugValue` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7242d-116">Notas</span><span class="sxs-lookup"><span data-stu-id="7242d-116">Remarks</span></span>  
 <span data-ttu-id="7242d-117">En general, la propiedad de un objeto de valor se pasa cuando se devuelve.</span><span class="sxs-lookup"><span data-stu-id="7242d-117">In general, ownership of a value object is passed when it is returned.</span></span> <span data-ttu-id="7242d-118">El destinatario es responsable de quitar una referencia del objeto cuando ha terminado con el objeto.</span><span class="sxs-lookup"><span data-stu-id="7242d-118">The recipient is responsible for removing a reference from the object when it is finished with the object.</span></span>  
  
 <span data-ttu-id="7242d-119">Dependiendo de dónde se haya recuperado el valor, es posible que el valor no siga siendo válido después de que se reanude el proceso.</span><span class="sxs-lookup"><span data-stu-id="7242d-119">Depending on where the value was retrieved from, the value may not remain valid after the process is resumed.</span></span> <span data-ttu-id="7242d-120">Por lo tanto, en general, el valor no se debe mantener en una llamada del método [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) .</span><span class="sxs-lookup"><span data-stu-id="7242d-120">So, in general, the value shouldn't be held across a call of the [ICorDebugController::Continue](icordebugcontroller-continue-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7242d-121">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="7242d-121">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7242d-122">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="7242d-122">Requirements</span></span>  
 <span data-ttu-id="7242d-123">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7242d-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7242d-124">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7242d-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7242d-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7242d-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7242d-126">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7242d-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7242d-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="7242d-127">See also</span></span>

- [<span data-ttu-id="7242d-128">ICorDebugValue3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7242d-128">ICorDebugValue3 Interface</span></span>](icordebugvalue3-interface.md)
- [<span data-ttu-id="7242d-129">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="7242d-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
