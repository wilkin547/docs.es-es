---
title: ICorDebugEnum (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEnum
helpviewer_keywords:
- ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: 80be7efe-2c32-4b9f-8c52-40c6f6268219
topic_type:
- apiref
ms.openlocfilehash: 59dcb7ae6f27f8d049cd4dc2d313f7f1130fc503
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73085257"
---
# <a name="icordebugenum-interface"></a><span data-ttu-id="ced6d-102">ICorDebugEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ced6d-102">ICorDebugEnum Interface</span></span>

<span data-ttu-id="ced6d-103">Actúa como la interfaz base abstracta para los enumeradores que se usan en una aplicación de depuración.</span><span class="sxs-lookup"><span data-stu-id="ced6d-103">Serves as the abstract base interface for the enumerators that are used by a debugging application.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ced6d-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="ced6d-104">Methods</span></span>  
  
|<span data-ttu-id="ced6d-105">Método</span><span class="sxs-lookup"><span data-stu-id="ced6d-105">Method</span></span>|<span data-ttu-id="ced6d-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="ced6d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ced6d-107">Clone (método)</span><span class="sxs-lookup"><span data-stu-id="ced6d-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-clone-method.md)|<span data-ttu-id="ced6d-108">Crea una copia de este objeto `ICorDebugEnum`.</span><span class="sxs-lookup"><span data-stu-id="ced6d-108">Creates a copy of this `ICorDebugEnum` object.</span></span>|  
|[<span data-ttu-id="ced6d-109">GetCount (método)</span><span class="sxs-lookup"><span data-stu-id="ced6d-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-getcount-method.md)|<span data-ttu-id="ced6d-110">Obtiene el número de elementos de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="ced6d-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="ced6d-111">Reset (método)</span><span class="sxs-lookup"><span data-stu-id="ced6d-111">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-reset-method.md)|<span data-ttu-id="ced6d-112">Mueve el cursor al principio de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="ced6d-112">Moves the cursor to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="ced6d-113">Skip (método)</span><span class="sxs-lookup"><span data-stu-id="ced6d-113">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-skip-method.md)|<span data-ttu-id="ced6d-114">Mueve el cursor hacia delante en la enumeración el número de elementos especificado.</span><span class="sxs-lookup"><span data-stu-id="ced6d-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ced6d-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ced6d-115">Remarks</span></span>  
 <span data-ttu-id="ced6d-116">Los enumeradores siguientes derivan de `ICorDebugEnum`:</span><span class="sxs-lookup"><span data-stu-id="ced6d-116">The following enumerators derive from `ICorDebugEnum`:</span></span>  
  
- <span data-ttu-id="ced6d-117">ICorDebugAppDomainEnum (</span><span class="sxs-lookup"><span data-stu-id="ced6d-117">"ICorDebugAppDomainEnum"</span></span>  
  
- <span data-ttu-id="ced6d-118">ICorDebugAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="ced6d-118">"ICorDebugAssemblyEnum"</span></span>  
  
- [<span data-ttu-id="ced6d-119">ICorDebugBlockingObjectEnum</span><span class="sxs-lookup"><span data-stu-id="ced6d-119">ICorDebugBlockingObjectEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-interface.md)  
  
- <span data-ttu-id="ced6d-120">ICorDebugBreakpointEnum (</span><span class="sxs-lookup"><span data-stu-id="ced6d-120">"ICorDebugBreakpointEnum"</span></span>  
  
- <span data-ttu-id="ced6d-121">ICorDebugChainEnum (</span><span class="sxs-lookup"><span data-stu-id="ced6d-121">"ICorDebugChainEnum"</span></span>  
  
- <span data-ttu-id="ced6d-122">ICorDebugCodeEnum (</span><span class="sxs-lookup"><span data-stu-id="ced6d-122">"ICorDebugCodeEnum"</span></span>  
  
- <span data-ttu-id="ced6d-123">Icordebugerrorinfoenum (</span><span class="sxs-lookup"><span data-stu-id="ced6d-123">"ICorDebugErrorInfoEnum"</span></span>  
  
- [<span data-ttu-id="ced6d-124">Icordebugexceptionobjectcallstackenum (</span><span class="sxs-lookup"><span data-stu-id="ced6d-124">ICorDebugExceptionObjectCallStackEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)  
  
- <span data-ttu-id="ced6d-125">ICorDebugFrameEnum (</span><span class="sxs-lookup"><span data-stu-id="ced6d-125">"ICorDebugFrameEnum"</span></span>  
  
- [<span data-ttu-id="ced6d-126">Icordebuggcreferenceenum (</span><span class="sxs-lookup"><span data-stu-id="ced6d-126">ICorDebugGCReferenceEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)  
  
- [<span data-ttu-id="ced6d-127">Icordebugguidtotypeenum (</span><span class="sxs-lookup"><span data-stu-id="ced6d-127">ICorDebugGuidToTypeEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)  
  
- [<span data-ttu-id="ced6d-128">Icordebugheapenum (</span><span class="sxs-lookup"><span data-stu-id="ced6d-128">ICorDebugHeapEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)  
  
- [<span data-ttu-id="ced6d-129">Icordebugheapsegmentenum (</span><span class="sxs-lookup"><span data-stu-id="ced6d-129">ICorDebugHeapSegmentEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)  
  
- <span data-ttu-id="ced6d-130">ICorDebugModuleEnum (</span><span class="sxs-lookup"><span data-stu-id="ced6d-130">"ICorDebugModuleEnum"</span></span>  
  
- <span data-ttu-id="ced6d-131">ICorDebugObjectEnum (</span><span class="sxs-lookup"><span data-stu-id="ced6d-131">"ICorDebugObjectEnum"</span></span>  
  
- <span data-ttu-id="ced6d-132">Icordebugprocessenum (</span><span class="sxs-lookup"><span data-stu-id="ced6d-132">"ICorDebugProcessEnum"</span></span>  
  
- <span data-ttu-id="ced6d-133">ICorDebugStepperEnum (</span><span class="sxs-lookup"><span data-stu-id="ced6d-133">"ICorDebugStepperEnum"</span></span>  
  
- <span data-ttu-id="ced6d-134">ICorDebugThreadEnum (</span><span class="sxs-lookup"><span data-stu-id="ced6d-134">"ICorDebugThreadEnum"</span></span>  
  
- <span data-ttu-id="ced6d-135">ICorDebugTypeEnum</span><span class="sxs-lookup"><span data-stu-id="ced6d-135">"ICorDebugTypeEnum"</span></span>  
  
- <span data-ttu-id="ced6d-136">ICorDebugValueEnum</span><span class="sxs-lookup"><span data-stu-id="ced6d-136">"ICorDebugValueEnum"</span></span>  
  
- [<span data-ttu-id="ced6d-137">ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="ced6d-137">ICorDebugVariableHomeEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)  
  
> [!NOTE]
> <span data-ttu-id="ced6d-138">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="ced6d-138">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ced6d-139">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ced6d-139">Requirements</span></span>  
 <span data-ttu-id="ced6d-140">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ced6d-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ced6d-141">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ced6d-141">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ced6d-142">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ced6d-142">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ced6d-143">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ced6d-143">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ced6d-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="ced6d-144">See also</span></span>

- [<span data-ttu-id="ced6d-145">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="ced6d-145">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
