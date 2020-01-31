---
title: ICorDebugExceptionDebugEvent (Interfaz)
ms.date: 03/30/2017
ms.assetid: f9ba60d8-b54d-417e-bb3e-fde4b41ca44c
ms.openlocfilehash: 168ba2945608a5b26432c5a0f583e5d406f6ce9b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782826"
---
# <a name="icordebugexceptiondebugevent-interface"></a><span data-ttu-id="b0a9b-102">ICorDebugExceptionDebugEvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b0a9b-102">ICorDebugExceptionDebugEvent Interface</span></span>
<span data-ttu-id="b0a9b-103">Extiende la interfaz [ICorDebugDebugEvent](icordebugdebugevent-interface.md) para admitir eventos de excepción.</span><span class="sxs-lookup"><span data-stu-id="b0a9b-103">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support exception events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b0a9b-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="b0a9b-104">Methods</span></span>  
  
|<span data-ttu-id="b0a9b-105">Método</span><span class="sxs-lookup"><span data-stu-id="b0a9b-105">Method</span></span>|<span data-ttu-id="b0a9b-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="b0a9b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b0a9b-107">GetFlags (método)</span><span class="sxs-lookup"><span data-stu-id="b0a9b-107">GetFlags Method</span></span>](icordebugexceptiondebugevent-getflags-method.md)|<span data-ttu-id="b0a9b-108">Obtiene una marca que indica si se puede interceptar la excepción.</span><span class="sxs-lookup"><span data-stu-id="b0a9b-108">Gets a flag that indicates whether the exception is can be intercepted.</span></span>|  
|[<span data-ttu-id="b0a9b-109">GetNativeIP (método)</span><span class="sxs-lookup"><span data-stu-id="b0a9b-109">GetNativeIP Method</span></span>](icordebugexceptiondebugevent-getnativeip-method.md)|<span data-ttu-id="b0a9b-110">Obtiene el puntero de interfaz nativo para este evento de depuración de la excepción.</span><span class="sxs-lookup"><span data-stu-id="b0a9b-110">Gets the native interface pointer for this exception debug event.</span></span>|  
|[<span data-ttu-id="b0a9b-111">GetStackPointer (método)</span><span class="sxs-lookup"><span data-stu-id="b0a9b-111">GetStackPointer Method</span></span>](icordebugexceptiondebugevent-getstackpointer-method.md)|<span data-ttu-id="b0a9b-112">Obtiene el puntero de pila para este evento de depuración de la excepción.</span><span class="sxs-lookup"><span data-stu-id="b0a9b-112">Gets the stack pointer for this exception debug event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b0a9b-113">Notas</span><span class="sxs-lookup"><span data-stu-id="b0a9b-113">Remarks</span></span>  
 <span data-ttu-id="b0a9b-114">La interfaz `ICorDebugExceptionDebugEvent` se implementa mediante los siguientes tipos de eventos:</span><span class="sxs-lookup"><span data-stu-id="b0a9b-114">The `ICorDebugExceptionDebugEvent` interface is implemented by the following event types:</span></span>  
  
- [<span data-ttu-id="b0a9b-115">MANAGED_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="b0a9b-115">MANAGED_EXCEPTION_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)  
  
- [<span data-ttu-id="b0a9b-116">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="b0a9b-116">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)  
  
- [<span data-ttu-id="b0a9b-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="b0a9b-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span></span>](cordebugrecordformat-enumeration.md)  
  
- [<span data-ttu-id="b0a9b-118">MANAGED_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="b0a9b-118">MANAGED_EXCEPTION_UNHANDLED</span></span>](cordebugrecordformat-enumeration.md)  
  
> [!NOTE]
> <span data-ttu-id="b0a9b-119">La interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="b0a9b-119">The interface is available with .NET Native only.</span></span> <span data-ttu-id="b0a9b-120">Al intentar llamar a `QueryInterface` para recuperar un puntero a interfaz, devuelve `E_NOINTERFACE` para escenarios de ICorDebug fuera de .NET nativo.</span><span class="sxs-lookup"><span data-stu-id="b0a9b-120">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0a9b-121">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="b0a9b-121">Requirements</span></span>  
 <span data-ttu-id="b0a9b-122">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0a9b-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0a9b-123">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b0a9b-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b0a9b-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b0a9b-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b0a9b-125">**.NET Framework versiones:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0a9b-125">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0a9b-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="b0a9b-126">See also</span></span>

- [<span data-ttu-id="b0a9b-127">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="b0a9b-127">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="b0a9b-128">Depuración</span><span class="sxs-lookup"><span data-stu-id="b0a9b-128">Debugging</span></span>](index.md)
