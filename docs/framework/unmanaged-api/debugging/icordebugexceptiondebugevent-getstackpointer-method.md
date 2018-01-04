---
title: "ICorDebugExceptionDebugEvent::GetNativeIP (método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: d8f66a1c-16be-4264-afc5-bc2dfbb4a682
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1b9096bbb494036156a528d8f9e940630f555f6a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugexceptiondebugeventgetstackpointer-method"></a><span data-ttu-id="7297a-102">ICorDebugExceptionDebugEvent::GetNativeIP (método)</span><span class="sxs-lookup"><span data-stu-id="7297a-102">ICorDebugExceptionDebugEvent::GetStackPointer Method</span></span>
<span data-ttu-id="7297a-103">Obtiene el puntero de pila para este evento de depuración de la excepción.</span><span class="sxs-lookup"><span data-stu-id="7297a-103">Gets the stack pointer for this exception debug event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7297a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7297a-104">Syntax</span></span>  
  
```  
HRESULT GetStackPointer(  
   [out]CORDB_ADDRESS *pStackPointer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7297a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7297a-105">Parameters</span></span>  
 `pStackPointer`  
 <span data-ttu-id="7297a-106">[out] Puntero a la dirección del puntero de pila para este evento de depuración de la excepción.</span><span class="sxs-lookup"><span data-stu-id="7297a-106">[out] A pointer to the address of the stack pointer for this exception debug event.</span></span> <span data-ttu-id="7297a-107">Vea la sección Comentarios para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="7297a-107">See the Remarks section for more information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7297a-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7297a-108">Remarks</span></span>  
 <span data-ttu-id="7297a-109">El significado de este puntero de pila depende del tipo de evento, como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="7297a-109">The meaning of this stack pointer depends on the event type, as shown in the following table.</span></span>  
  
|<span data-ttu-id="7297a-110">Tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="7297a-110">Event type</span></span>|<span data-ttu-id="7297a-111">Significado del valor `pStackPointer`</span><span class="sxs-lookup"><span data-stu-id="7297a-111">Meaning of `pStackPointer` value</span></span>|  
|----------------|--------------------------------------|  
|[<span data-ttu-id="7297a-112">MANAGED_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="7297a-112">MANAGED_EXCEPTION_FIRST_CHANCE</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="7297a-113">Puntero de pila para el marco que produjo la excepción.</span><span class="sxs-lookup"><span data-stu-id="7297a-113">The stack pointer for the frame that threw the exception.</span></span>|  
|[<span data-ttu-id="7297a-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="7297a-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="7297a-115">Puntero de pila para el marco de código de usuario más cercano al punto de la excepción generada.</span><span class="sxs-lookup"><span data-stu-id="7297a-115">The stack pointer for the user-code frame closest to the point of the thrown exception.</span></span>|  
|[<span data-ttu-id="7297a-116">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="7297a-116">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="7297a-117">Puntero de pila para el marco que contiene el controlador catch.</span><span class="sxs-lookup"><span data-stu-id="7297a-117">The stack pointer for the frame that contains the catch handler.</span></span>|  
|[<span data-ttu-id="7297a-118">MANAGED_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="7297a-118">MANAGED_EXCEPTION_UNHANDLED</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="7297a-119">`pStackPointer` es **NULL**.</span><span class="sxs-lookup"><span data-stu-id="7297a-119">`pStackPointer` is **null**.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="7297a-120">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="7297a-120">This method is available with .NET Native only.</span></span>  
  
 <span data-ttu-id="7297a-121">El tipo de evento está disponible en la [icordebugdebugevent::](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) (método).</span><span class="sxs-lookup"><span data-stu-id="7297a-121">The event type is available from the [ICorDebugDebugEvent::GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7297a-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7297a-122">Requirements</span></span>  
 <span data-ttu-id="7297a-123">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7297a-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7297a-124">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7297a-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7297a-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7297a-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7297a-126">**Versiones de .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7297a-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7297a-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="7297a-127">See Also</span></span>  
 [<span data-ttu-id="7297a-128">ICorDebugExceptionDebugEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7297a-128">ICorDebugExceptionDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)  
 [<span data-ttu-id="7297a-129">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="7297a-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
