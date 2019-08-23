---
title: Interfaz ICorDebugExceptionDebugEvent
ms.date: 03/30/2017
ms.assetid: f9ba60d8-b54d-417e-bb3e-fde4b41ca44c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 522bccb4a424da620063995d02ae15d09ecbf2fe
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929879"
---
# <a name="icordebugexceptiondebugevent-interface"></a><span data-ttu-id="03ba6-102">Interfaz ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="03ba6-102">ICorDebugExceptionDebugEvent Interface</span></span>
<span data-ttu-id="03ba6-103">Extiende la interfaz [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) para admitir eventos de excepción.</span><span class="sxs-lookup"><span data-stu-id="03ba6-103">Extends the [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interface to support exception events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="03ba6-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="03ba6-104">Methods</span></span>  
  
|<span data-ttu-id="03ba6-105">Método</span><span class="sxs-lookup"><span data-stu-id="03ba6-105">Method</span></span>|<span data-ttu-id="03ba6-106">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="03ba6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="03ba6-107">GetFlags (método)</span><span class="sxs-lookup"><span data-stu-id="03ba6-107">GetFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getflags-method.md)|<span data-ttu-id="03ba6-108">Obtiene una marca que indica si se puede interceptar la excepción.</span><span class="sxs-lookup"><span data-stu-id="03ba6-108">Gets a flag that indicates whether the exception is can be intercepted.</span></span>|  
|[<span data-ttu-id="03ba6-109">GetNativeIP (método)</span><span class="sxs-lookup"><span data-stu-id="03ba6-109">GetNativeIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getnativeip-method.md)|<span data-ttu-id="03ba6-110">Obtiene el puntero de interfaz nativo para este evento de depuración de la excepción.</span><span class="sxs-lookup"><span data-stu-id="03ba6-110">Gets the native interface pointer for this exception debug event.</span></span>|  
|[<span data-ttu-id="03ba6-111">GetStackPointer (método)</span><span class="sxs-lookup"><span data-stu-id="03ba6-111">GetStackPointer Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getstackpointer-method.md)|<span data-ttu-id="03ba6-112">Obtiene el puntero de pila para este evento de depuración de la excepción.</span><span class="sxs-lookup"><span data-stu-id="03ba6-112">Gets the stack pointer for this exception debug event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="03ba6-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="03ba6-113">Remarks</span></span>  
 <span data-ttu-id="03ba6-114">La interfaz `ICorDebugExceptionDebugEvent` se implementa mediante los siguientes tipos de eventos:</span><span class="sxs-lookup"><span data-stu-id="03ba6-114">The `ICorDebugExceptionDebugEvent` interface is implemented by the following event types:</span></span>  
  
- [<span data-ttu-id="03ba6-115">MANAGED_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="03ba6-115">MANAGED_EXCEPTION_FIRST_CHANCE</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)  
  
- [<span data-ttu-id="03ba6-116">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="03ba6-116">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)  
  
- [<span data-ttu-id="03ba6-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="03ba6-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)  
  
- [<span data-ttu-id="03ba6-118">MANAGED_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="03ba6-118">MANAGED_EXCEPTION_UNHANDLED</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)  
  
> [!NOTE]
> <span data-ttu-id="03ba6-119">La interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="03ba6-119">The interface is available with .NET Native only.</span></span> <span data-ttu-id="03ba6-120">Al intentar llamar a `QueryInterface` para recuperar un puntero a interfaz, devuelve `E_NOINTERFACE` para escenarios de ICorDebug fuera de .NET nativo.</span><span class="sxs-lookup"><span data-stu-id="03ba6-120">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03ba6-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="03ba6-121">Requirements</span></span>  
 <span data-ttu-id="03ba6-122">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03ba6-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03ba6-123">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="03ba6-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="03ba6-124">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="03ba6-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="03ba6-125">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03ba6-125">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03ba6-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="03ba6-126">See also</span></span>

- [<span data-ttu-id="03ba6-127">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="03ba6-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="03ba6-128">Depuración</span><span class="sxs-lookup"><span data-stu-id="03ba6-128">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
