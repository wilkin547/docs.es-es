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
ms.assetid: 12e6a262-d9ac-49b8-9b80-1e653a2a3819
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 32e75a18645c000562cdd94478c6ef8db41a01a5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugexceptiondebugeventgetnativeip-method"></a><span data-ttu-id="64e8d-102">ICorDebugExceptionDebugEvent::GetNativeIP (método)</span><span class="sxs-lookup"><span data-stu-id="64e8d-102">ICorDebugExceptionDebugEvent::GetNativeIP Method</span></span>
<span data-ttu-id="64e8d-103">Obtiene el puntero de instrucción nativo para este evento de depuración de la excepción.</span><span class="sxs-lookup"><span data-stu-id="64e8d-103">Gets the native instruction pointer for this exception debug event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64e8d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="64e8d-104">Syntax</span></span>  
  
```  
HRESULT GetNativeIP(  
   [out]CORDB_ADDRESS *pIP  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="64e8d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="64e8d-105">Parameters</span></span>  
 `pIP`  
 <span data-ttu-id="64e8d-106">[out] Puntero al puntero de instrucción para este evento de depuración de la excepción.</span><span class="sxs-lookup"><span data-stu-id="64e8d-106">[out] A pointer to the instruction pointer for this exception debug event.</span></span> <span data-ttu-id="64e8d-107">Vea la sección Comentarios para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="64e8d-107">See the Remarks section for more information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="64e8d-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="64e8d-108">Remarks</span></span>  
 <span data-ttu-id="64e8d-109">El significado de este puntero de instrucción depende del tipo de evento, como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="64e8d-109">The meaning of this instruction pointer depends on the event type, as shown in the following table.</span></span>  
  
|<span data-ttu-id="64e8d-110">Tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="64e8d-110">Event type</span></span>|<span data-ttu-id="64e8d-111">Significado del valor `pStackPointer`</span><span class="sxs-lookup"><span data-stu-id="64e8d-111">Meaning of `pStackPointer` value</span></span>|  
|----------------|--------------------------------------|  
|[<span data-ttu-id="64e8d-112">MANAGED_EXCEPTION_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="64e8d-112">MANAGED_EXCEPTION_FIRST_CHANCE</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="64e8d-113">Dirección de la instrucción con errores.</span><span class="sxs-lookup"><span data-stu-id="64e8d-113">The address of the faulting instruction.</span></span>|  
|[<span data-ttu-id="64e8d-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span><span class="sxs-lookup"><span data-stu-id="64e8d-114">MANAGED_EXCEPTION_USER_FIRST_CHANCE</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="64e8d-115">La dirección de código en el marco indicado por la [GetStackPointer](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getstackpointer-method.md) método donde se reanudaría la ejecución si no se hubiese producida ninguna excepción.</span><span class="sxs-lookup"><span data-stu-id="64e8d-115">The code address in the frame indicated by the [GetStackPointer](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getstackpointer-method.md) method where execution would resume if no exception had been raised.</span></span> <span data-ttu-id="64e8d-116">La excepción puede o no puede causar un código diferente, por ejemplo, un bloque catch de una cláusula `try/catch/finally`, para ejecutar en este marco.</span><span class="sxs-lookup"><span data-stu-id="64e8d-116">The exception may or may not cause different code, such as the catch block of a `try/catch/finally` clause, to be executed in this frame.</span></span>|  
|[<span data-ttu-id="64e8d-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span><span class="sxs-lookup"><span data-stu-id="64e8d-117">MANAGED_EXCEPTION_CATCH_HANDLER_FOUND</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="64e8d-118">El código de dirección `catch` iniciará la ejecución de controlador en el marco indicado por la [GetStackPointer](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getstackpointer-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="64e8d-118">The code address where `catch` handler execution will start in the frame indicated by the [GetStackPointer](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-getstackpointer-method.md) method.</span></span>|  
|[<span data-ttu-id="64e8d-119">MANAGED_EXCEPTION_UNHANDLED</span><span class="sxs-lookup"><span data-stu-id="64e8d-119">MANAGED_EXCEPTION_UNHANDLED</span></span>](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md)|<span data-ttu-id="64e8d-120">`pIP` es 0.</span><span class="sxs-lookup"><span data-stu-id="64e8d-120">`pIP` is 0.</span></span>|  
  
 <span data-ttu-id="64e8d-121">El tipo de evento está disponible en la [icordebugdebugevent::](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) (método).</span><span class="sxs-lookup"><span data-stu-id="64e8d-121">The event type is available from the [ICorDebugDebugEvent::GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="64e8d-122">Este método solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="64e8d-122">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64e8d-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="64e8d-123">Requirements</span></span>  
 <span data-ttu-id="64e8d-124">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64e8d-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64e8d-125">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="64e8d-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="64e8d-126">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="64e8d-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="64e8d-127">**Versiones de .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64e8d-127">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64e8d-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="64e8d-128">See Also</span></span>  
 [<span data-ttu-id="64e8d-129">ICorDebugExceptionDebugEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="64e8d-129">ICorDebugExceptionDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)  
 [<span data-ttu-id="64e8d-130">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="64e8d-130">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
