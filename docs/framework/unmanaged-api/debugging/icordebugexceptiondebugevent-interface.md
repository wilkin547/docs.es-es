---
title: Interfaz ICorDebugExceptionDebugEvent
ms.date: 03/30/2017
ms.assetid: f9ba60d8-b54d-417e-bb3e-fde4b41ca44c
ms.openlocfilehash: c280852d421742cf9e8c2f8dcaa9c0f588f8537b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697394"
---
# <a name="icordebugexceptiondebugevent-interface"></a><span data-ttu-id="01f1b-102">Interfaz ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="01f1b-102">ICorDebugExceptionDebugEvent Interface</span></span>

<span data-ttu-id="01f1b-103">Extiende la interfaz [ICorDebugDebugEvent](icordebugdebugevent-interface.md) para admitir eventos de excepción.</span><span class="sxs-lookup"><span data-stu-id="01f1b-103">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support exception events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="01f1b-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="01f1b-104">Methods</span></span>  
  
|<span data-ttu-id="01f1b-105">Método</span><span class="sxs-lookup"><span data-stu-id="01f1b-105">Method</span></span>|<span data-ttu-id="01f1b-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="01f1b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="01f1b-107">Método GetFlags</span><span class="sxs-lookup"><span data-stu-id="01f1b-107">GetFlags Method</span></span>](icordebugexceptiondebugevent-getflags-method.md)|<span data-ttu-id="01f1b-108">Obtiene una marca que indica si se puede interceptar la excepción.</span><span class="sxs-lookup"><span data-stu-id="01f1b-108">Gets a flag that indicates whether the exception is can be intercepted.</span></span>|  
|[<span data-ttu-id="01f1b-109">Método GetNativeIP</span><span class="sxs-lookup"><span data-stu-id="01f1b-109">GetNativeIP Method</span></span>](icordebugexceptiondebugevent-getnativeip-method.md)|<span data-ttu-id="01f1b-110">Obtiene el puntero de interfaz nativo para este evento de depuración de la excepción.</span><span class="sxs-lookup"><span data-stu-id="01f1b-110">Gets the native interface pointer for this exception debug event.</span></span>|  
|[<span data-ttu-id="01f1b-111">Método GetStackPointer</span><span class="sxs-lookup"><span data-stu-id="01f1b-111">GetStackPointer Method</span></span>](icordebugexceptiondebugevent-getstackpointer-method.md)|<span data-ttu-id="01f1b-112">Obtiene el puntero de pila para este evento de depuración de la excepción.</span><span class="sxs-lookup"><span data-stu-id="01f1b-112">Gets the stack pointer for this exception debug event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="01f1b-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="01f1b-113">Remarks</span></span>  

 <span data-ttu-id="01f1b-114">La interfaz `ICorDebugExceptionDebugEvent` se implementa mediante los siguientes tipos de eventos:</span><span class="sxs-lookup"><span data-stu-id="01f1b-114">The `ICorDebugExceptionDebugEvent` interface is implemented by the following event types:</span></span>  
  
- [<span data-ttu-id="01f1b-115">MANAGED_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="01f1b-115">MANAGED_EXCEPTION_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)  
  
- [<span data-ttu-id="01f1b-116">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="01f1b-116">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)  
  
- [<span data-ttu-id="01f1b-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="01f1b-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span></span>](cordebugrecordformat-enumeration.md)  
  
- [<span data-ttu-id="01f1b-118">MANAGED_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="01f1b-118">MANAGED_EXCEPTION_UNHANDLED</span></span>](cordebugrecordformat-enumeration.md)  
  
> [!NOTE]
> <span data-ttu-id="01f1b-119">La interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="01f1b-119">The interface is available with .NET Native only.</span></span> <span data-ttu-id="01f1b-120">Al intentar llamar a `QueryInterface` para recuperar un puntero a interfaz, devuelve `E_NOINTERFACE` para escenarios de ICorDebug fuera de .NET nativo.</span><span class="sxs-lookup"><span data-stu-id="01f1b-120">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01f1b-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="01f1b-121">Requirements</span></span>  

 <span data-ttu-id="01f1b-122">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="01f1b-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01f1b-123">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="01f1b-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="01f1b-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="01f1b-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="01f1b-125">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01f1b-125">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01f1b-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="01f1b-126">See also</span></span>

- [<span data-ttu-id="01f1b-127">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="01f1b-127">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="01f1b-128">Depuración</span><span class="sxs-lookup"><span data-stu-id="01f1b-128">Debugging</span></span>](index.md)
