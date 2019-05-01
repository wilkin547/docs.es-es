---
title: Interfaz ICorDebugExceptionDebugEvent
ms.date: 03/30/2017
ms.assetid: f9ba60d8-b54d-417e-bb3e-fde4b41ca44c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2e2a147d46412eb4feb192070ff8420cab842a6c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995896"
---
# <a name="icordebugexceptiondebugevent-interface"></a><span data-ttu-id="a6d2a-102">Interfaz ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="a6d2a-102">ICorDebugExceptionDebugEvent Interface</span></span>
<span data-ttu-id="a6d2a-103">Extiende la [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interfaz para admitir eventos de excepción.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-103">Extends the [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) interface to support exception events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a6d2a-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="a6d2a-104">Methods</span></span>  
  
|<span data-ttu-id="a6d2a-105">Método</span><span class="sxs-lookup"><span data-stu-id="a6d2a-105">Method</span></span>|<span data-ttu-id="a6d2a-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="a6d2a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a6d2a-107">GetFlags (método)</span><span class="sxs-lookup"><span data-stu-id="a6d2a-107">GetFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getflags-method.md)|<span data-ttu-id="a6d2a-108">Obtiene una marca que indica si se puede interceptar la excepción.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-108">Gets a flag that indicates whether the exception is can be intercepted.</span></span>|  
|[<span data-ttu-id="a6d2a-109">GetNativeIP (método)</span><span class="sxs-lookup"><span data-stu-id="a6d2a-109">GetNativeIP Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getnativeip-method.md)|<span data-ttu-id="a6d2a-110">Obtiene el puntero de interfaz nativo para este evento de depuración de la excepción.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-110">Gets the native interface pointer for this exception debug event.</span></span>|  
|[<span data-ttu-id="a6d2a-111">GetStackPointer (método)</span><span class="sxs-lookup"><span data-stu-id="a6d2a-111">GetStackPointer Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getstackpointer-method.md)|<span data-ttu-id="a6d2a-112">Obtiene el puntero de pila para este evento de depuración de la excepción.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-112">Gets the stack pointer for this exception debug event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a6d2a-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a6d2a-113">Remarks</span></span>  
 <span data-ttu-id="a6d2a-114">La interfaz `ICorDebugExceptionDebugEvent` se implementa mediante los siguientes tipos de eventos:</span><span class="sxs-lookup"><span data-stu-id="a6d2a-114">The `ICorDebugExceptionDebugEvent` interface is implemented by the following event types:</span></span>  
  
- [<span data-ttu-id="a6d2a-115">MANAGED_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="a6d2a-115">MANAGED_EXCEPTION_FIRST_CHANCE</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)  
  
- [<span data-ttu-id="a6d2a-116">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="a6d2a-116">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)  
  
- [<span data-ttu-id="a6d2a-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="a6d2a-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)  
  
- [<span data-ttu-id="a6d2a-118">MANAGED_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="a6d2a-118">MANAGED_EXCEPTION_UNHANDLED</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)  
  
> [!NOTE]
>  <span data-ttu-id="a6d2a-119">La interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-119">The interface is available with .NET Native only.</span></span> <span data-ttu-id="a6d2a-120">Al intentar llamar a `QueryInterface` para recuperar un puntero a interfaz, devuelve `E_NOINTERFACE` para escenarios de ICorDebug fuera de .NET nativo.</span><span class="sxs-lookup"><span data-stu-id="a6d2a-120">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6d2a-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a6d2a-121">Requirements</span></span>  
 <span data-ttu-id="a6d2a-122">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6d2a-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6d2a-123">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a6d2a-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a6d2a-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a6d2a-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a6d2a-125">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6d2a-125">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6d2a-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="a6d2a-126">See also</span></span>

- [<span data-ttu-id="a6d2a-127">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="a6d2a-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="a6d2a-128">Depuración</span><span class="sxs-lookup"><span data-stu-id="a6d2a-128">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
