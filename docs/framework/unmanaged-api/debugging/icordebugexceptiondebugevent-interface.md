---
description: 'Más información acerca de: interfaz ICorDebugExceptionDebugEvent'
title: Interfaz ICorDebugExceptionDebugEvent
ms.date: 03/30/2017
ms.assetid: f9ba60d8-b54d-417e-bb3e-fde4b41ca44c
ms.openlocfilehash: eacaa344763fb77faef5f66282809d741f017b37
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99693426"
---
# <a name="icordebugexceptiondebugevent-interface"></a><span data-ttu-id="acbb9-103">Interfaz ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="acbb9-103">ICorDebugExceptionDebugEvent Interface</span></span>

<span data-ttu-id="acbb9-104">Extiende la interfaz [ICorDebugDebugEvent](icordebugdebugevent-interface.md) para admitir eventos de excepción.</span><span class="sxs-lookup"><span data-stu-id="acbb9-104">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support exception events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="acbb9-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="acbb9-105">Methods</span></span>  
  
|<span data-ttu-id="acbb9-106">Método</span><span class="sxs-lookup"><span data-stu-id="acbb9-106">Method</span></span>|<span data-ttu-id="acbb9-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="acbb9-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="acbb9-108">Método GetFlags</span><span class="sxs-lookup"><span data-stu-id="acbb9-108">GetFlags Method</span></span>](icordebugexceptiondebugevent-getflags-method.md)|<span data-ttu-id="acbb9-109">Obtiene una marca que indica si se puede interceptar la excepción.</span><span class="sxs-lookup"><span data-stu-id="acbb9-109">Gets a flag that indicates whether the exception is can be intercepted.</span></span>|  
|[<span data-ttu-id="acbb9-110">Método GetNativeIP</span><span class="sxs-lookup"><span data-stu-id="acbb9-110">GetNativeIP Method</span></span>](icordebugexceptiondebugevent-getnativeip-method.md)|<span data-ttu-id="acbb9-111">Obtiene el puntero de interfaz nativo para este evento de depuración de la excepción.</span><span class="sxs-lookup"><span data-stu-id="acbb9-111">Gets the native interface pointer for this exception debug event.</span></span>|  
|[<span data-ttu-id="acbb9-112">Método GetStackPointer</span><span class="sxs-lookup"><span data-stu-id="acbb9-112">GetStackPointer Method</span></span>](icordebugexceptiondebugevent-getstackpointer-method.md)|<span data-ttu-id="acbb9-113">Obtiene el puntero de pila para este evento de depuración de la excepción.</span><span class="sxs-lookup"><span data-stu-id="acbb9-113">Gets the stack pointer for this exception debug event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="acbb9-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="acbb9-114">Remarks</span></span>  

 <span data-ttu-id="acbb9-115">La interfaz `ICorDebugExceptionDebugEvent` se implementa mediante los siguientes tipos de eventos:</span><span class="sxs-lookup"><span data-stu-id="acbb9-115">The `ICorDebugExceptionDebugEvent` interface is implemented by the following event types:</span></span>  
  
- [<span data-ttu-id="acbb9-116">MANAGED_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="acbb9-116">MANAGED_EXCEPTION_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)  
  
- [<span data-ttu-id="acbb9-117">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="acbb9-117">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)  
  
- [<span data-ttu-id="acbb9-118">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="acbb9-118">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span></span>](cordebugrecordformat-enumeration.md)  
  
- [<span data-ttu-id="acbb9-119">MANAGED_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="acbb9-119">MANAGED_EXCEPTION_UNHANDLED</span></span>](cordebugrecordformat-enumeration.md)  
  
> [!NOTE]
> <span data-ttu-id="acbb9-120">La interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="acbb9-120">The interface is available with .NET Native only.</span></span> <span data-ttu-id="acbb9-121">Al intentar llamar a `QueryInterface` para recuperar un puntero a interfaz, devuelve `E_NOINTERFACE` para escenarios de ICorDebug fuera de .NET nativo.</span><span class="sxs-lookup"><span data-stu-id="acbb9-121">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="acbb9-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="acbb9-122">Requirements</span></span>  

 <span data-ttu-id="acbb9-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="acbb9-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="acbb9-124">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="acbb9-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="acbb9-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="acbb9-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="acbb9-126">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="acbb9-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acbb9-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="acbb9-127">See also</span></span>

- [<span data-ttu-id="acbb9-128">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="acbb9-128">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="acbb9-129">Depuración</span><span class="sxs-lookup"><span data-stu-id="acbb9-129">Debugging</span></span>](index.md)
