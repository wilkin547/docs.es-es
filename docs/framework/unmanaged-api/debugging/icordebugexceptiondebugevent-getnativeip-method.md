---
title: ICorDebugExceptionDebugEvent::GetNativeIP (método)
ms.date: 03/30/2017
ms.assetid: 12e6a262-d9ac-49b8-9b80-1e653a2a3819
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aaa1a160bb316831540f68713647dbdc4b0f6895
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69951846"
---
# <a name="icordebugexceptiondebugeventgetnativeip-method"></a><span data-ttu-id="2386c-102">ICorDebugExceptionDebugEvent::GetNativeIP (método)</span><span class="sxs-lookup"><span data-stu-id="2386c-102">ICorDebugExceptionDebugEvent::GetNativeIP Method</span></span>
<span data-ttu-id="2386c-103">Obtiene el puntero de instrucción nativo para este evento de depuración de la excepción.</span><span class="sxs-lookup"><span data-stu-id="2386c-103">Gets the native instruction pointer for this exception debug event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2386c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2386c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNativeIP(  
   [out]CORDB_ADDRESS *pIP  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2386c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2386c-105">Parameters</span></span>  
 `pIP`  
 <span data-ttu-id="2386c-106">[out] Puntero al puntero de instrucción para este evento de depuración de la excepción.</span><span class="sxs-lookup"><span data-stu-id="2386c-106">[out] A pointer to the instruction pointer for this exception debug event.</span></span> <span data-ttu-id="2386c-107">Vea la sección Comentarios para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="2386c-107">See the Remarks section for more information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2386c-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2386c-108">Remarks</span></span>  
 <span data-ttu-id="2386c-109">El significado de este puntero de instrucción depende del tipo de evento, como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="2386c-109">The meaning of this instruction pointer depends on the event type, as shown in the following table.</span></span>  
  
|<span data-ttu-id="2386c-110">Tipo de evento</span><span class="sxs-lookup"><span data-stu-id="2386c-110">Event type</span></span>|<span data-ttu-id="2386c-111">Significado del valor `pStackPointer`</span><span class="sxs-lookup"><span data-stu-id="2386c-111">Meaning of `pStackPointer` value</span></span>|  
|----------------|--------------------------------------|  
|[<span data-ttu-id="2386c-112">MANAGED_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="2386c-112">MANAGED_EXCEPTION_FIRST_CHANCE</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="2386c-113">Dirección de la instrucción con errores.</span><span class="sxs-lookup"><span data-stu-id="2386c-113">The address of the faulting instruction.</span></span>|  
|[<span data-ttu-id="2386c-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="2386c-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="2386c-115">Dirección del código en el marco indicado por el método [GetStackPointer](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getstackpointer-method.md) donde se reanudaría la ejecución si no se hubiera producido ninguna excepción.</span><span class="sxs-lookup"><span data-stu-id="2386c-115">The code address in the frame indicated by the [GetStackPointer](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getstackpointer-method.md) method where execution would resume if no exception had been raised.</span></span> <span data-ttu-id="2386c-116">La excepción puede o no puede causar un código diferente, por ejemplo, un bloque catch de una cláusula `try/catch/finally`, para ejecutar en este marco.</span><span class="sxs-lookup"><span data-stu-id="2386c-116">The exception may or may not cause different code, such as the catch block of a `try/catch/finally` clause, to be executed in this frame.</span></span>|  
|[<span data-ttu-id="2386c-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="2386c-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="2386c-118">Dirección del código donde `catch` se iniciará la ejecución del controlador en el marco indicado por el método [GetStackPointer](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getstackpointer-method.md) .</span><span class="sxs-lookup"><span data-stu-id="2386c-118">The code address where `catch` handler execution will start in the frame indicated by the [GetStackPointer](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getstackpointer-method.md) method.</span></span>|  
|[<span data-ttu-id="2386c-119">MANAGED_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="2386c-119">MANAGED_EXCEPTION_UNHANDLED</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="2386c-120">`pIP` es 0.</span><span class="sxs-lookup"><span data-stu-id="2386c-120">`pIP` is 0.</span></span>|  
  
 <span data-ttu-id="2386c-121">El tipo de evento está disponible en el método [ICorDebugDebugEvent:: GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) .</span><span class="sxs-lookup"><span data-stu-id="2386c-121">The event type is available from the [ICorDebugDebugEvent::GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2386c-122">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="2386c-122">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2386c-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2386c-123">Requirements</span></span>  
 <span data-ttu-id="2386c-124">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2386c-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2386c-125">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="2386c-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2386c-126">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2386c-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2386c-127">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2386c-127">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2386c-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="2386c-128">See also</span></span>

- [<span data-ttu-id="2386c-129">ICorDebugExceptionDebugEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2386c-129">ICorDebugExceptionDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="2386c-130">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="2386c-130">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
