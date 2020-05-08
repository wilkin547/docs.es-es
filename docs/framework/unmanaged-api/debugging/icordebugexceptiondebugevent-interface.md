---
title: Interfaz ICorDebugExceptionDebugEvent
ms.date: 03/30/2017
ms.assetid: f9ba60d8-b54d-417e-bb3e-fde4b41ca44c
ms.openlocfilehash: dfa65aa1b63c996068e75ff1165111d5fcfe77eb
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976010"
---
# <a name="icordebugexceptiondebugevent-interface"></a><span data-ttu-id="de159-102">Interfaz ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="de159-102">ICorDebugExceptionDebugEvent Interface</span></span>
<span data-ttu-id="de159-103">Extiende la interfaz [ICorDebugDebugEvent](icordebugdebugevent-interface.md) para admitir eventos de excepción.</span><span class="sxs-lookup"><span data-stu-id="de159-103">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support exception events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="de159-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="de159-104">Methods</span></span>  
  
|<span data-ttu-id="de159-105">Método</span><span class="sxs-lookup"><span data-stu-id="de159-105">Method</span></span>|<span data-ttu-id="de159-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="de159-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="de159-107">Método GetFlags</span><span class="sxs-lookup"><span data-stu-id="de159-107">GetFlags Method</span></span>](icordebugexceptiondebugevent-getflags-method.md)|<span data-ttu-id="de159-108">Obtiene una marca que indica si se puede interceptar la excepción.</span><span class="sxs-lookup"><span data-stu-id="de159-108">Gets a flag that indicates whether the exception is can be intercepted.</span></span>|  
|[<span data-ttu-id="de159-109">Método GetNativeIP</span><span class="sxs-lookup"><span data-stu-id="de159-109">GetNativeIP Method</span></span>](icordebugexceptiondebugevent-getnativeip-method.md)|<span data-ttu-id="de159-110">Obtiene el puntero de interfaz nativo para este evento de depuración de la excepción.</span><span class="sxs-lookup"><span data-stu-id="de159-110">Gets the native interface pointer for this exception debug event.</span></span>|  
|[<span data-ttu-id="de159-111">Método GetStackPointer</span><span class="sxs-lookup"><span data-stu-id="de159-111">GetStackPointer Method</span></span>](icordebugexceptiondebugevent-getstackpointer-method.md)|<span data-ttu-id="de159-112">Obtiene el puntero de pila para este evento de depuración de la excepción.</span><span class="sxs-lookup"><span data-stu-id="de159-112">Gets the stack pointer for this exception debug event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="de159-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="de159-113">Remarks</span></span>  
 <span data-ttu-id="de159-114">La interfaz `ICorDebugExceptionDebugEvent` se implementa mediante los siguientes tipos de eventos:</span><span class="sxs-lookup"><span data-stu-id="de159-114">The `ICorDebugExceptionDebugEvent` interface is implemented by the following event types:</span></span>  
  
- [<span data-ttu-id="de159-115">MANAGED_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="de159-115">MANAGED_EXCEPTION_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)  
  
- [<span data-ttu-id="de159-116">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="de159-116">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span></span>](cordebugrecordformat-enumeration.md)  
  
- [<span data-ttu-id="de159-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="de159-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span></span>](cordebugrecordformat-enumeration.md)  
  
- [<span data-ttu-id="de159-118">MANAGED_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="de159-118">MANAGED_EXCEPTION_UNHANDLED</span></span>](cordebugrecordformat-enumeration.md)  
  
> [!NOTE]
> <span data-ttu-id="de159-119">La interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="de159-119">The interface is available with .NET Native only.</span></span> <span data-ttu-id="de159-120">Al intentar llamar a `QueryInterface` para recuperar un puntero a interfaz, devuelve `E_NOINTERFACE` para escenarios de ICorDebug fuera de .NET nativo.</span><span class="sxs-lookup"><span data-stu-id="de159-120">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de159-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="de159-121">Requirements</span></span>  
 <span data-ttu-id="de159-122">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de159-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de159-123">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="de159-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="de159-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="de159-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="de159-125">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de159-125">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de159-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="de159-126">See also</span></span>

- [<span data-ttu-id="de159-127">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="de159-127">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="de159-128">Depuración</span><span class="sxs-lookup"><span data-stu-id="de159-128">Debugging</span></span>](index.md)
