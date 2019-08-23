---
title: Interfaz ICorDebugEnum
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b25c47e101ad0fb8e8cbdbb2718a41c9be6c0c22
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931981"
---
# <a name="icordebugenum-interface"></a><span data-ttu-id="0e1a2-102">Interfaz ICorDebugEnum</span><span class="sxs-lookup"><span data-stu-id="0e1a2-102">ICorDebugEnum Interface</span></span>

<span data-ttu-id="0e1a2-103">Actúa como la interfaz base abstracta para los enumeradores que se usan en una aplicación de depuración.</span><span class="sxs-lookup"><span data-stu-id="0e1a2-103">Serves as the abstract base interface for the enumerators that are used by a debugging application.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0e1a2-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="0e1a2-104">Methods</span></span>  
  
|<span data-ttu-id="0e1a2-105">Método</span><span class="sxs-lookup"><span data-stu-id="0e1a2-105">Method</span></span>|<span data-ttu-id="0e1a2-106">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="0e1a2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0e1a2-107">Clone (método)</span><span class="sxs-lookup"><span data-stu-id="0e1a2-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-clone-method.md)|<span data-ttu-id="0e1a2-108">Crea una copia de este `ICorDebugEnum` objeto.</span><span class="sxs-lookup"><span data-stu-id="0e1a2-108">Creates a copy of this `ICorDebugEnum` object.</span></span>|  
|[<span data-ttu-id="0e1a2-109">GetCount (método)</span><span class="sxs-lookup"><span data-stu-id="0e1a2-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-getcount-method.md)|<span data-ttu-id="0e1a2-110">Obtiene el número de elementos de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="0e1a2-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="0e1a2-111">Reset (método)</span><span class="sxs-lookup"><span data-stu-id="0e1a2-111">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-reset-method.md)|<span data-ttu-id="0e1a2-112">Mueve el cursor al principio de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="0e1a2-112">Moves the cursor to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="0e1a2-113">Skip (método)</span><span class="sxs-lookup"><span data-stu-id="0e1a2-113">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-skip-method.md)|<span data-ttu-id="0e1a2-114">Mueve el cursor hacia delante en la enumeración el número de elementos especificado.</span><span class="sxs-lookup"><span data-stu-id="0e1a2-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0e1a2-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0e1a2-115">Remarks</span></span>  
 <span data-ttu-id="0e1a2-116">Los enumeradores siguientes derivan `ICorDebugEnum`de:</span><span class="sxs-lookup"><span data-stu-id="0e1a2-116">The following enumerators derive from `ICorDebugEnum`:</span></span>  
  
- <span data-ttu-id="0e1a2-117">ICorDebugAppDomainEnum (</span><span class="sxs-lookup"><span data-stu-id="0e1a2-117">"ICorDebugAppDomainEnum"</span></span>  
  
- <span data-ttu-id="0e1a2-118">ICorDebugAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="0e1a2-118">"ICorDebugAssemblyEnum"</span></span>  
  
- [<span data-ttu-id="0e1a2-119">ICorDebugBlockingObjectEnum</span><span class="sxs-lookup"><span data-stu-id="0e1a2-119">ICorDebugBlockingObjectEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-interface.md)  
  
- <span data-ttu-id="0e1a2-120">ICorDebugBreakpointEnum (</span><span class="sxs-lookup"><span data-stu-id="0e1a2-120">"ICorDebugBreakpointEnum"</span></span>  
  
- <span data-ttu-id="0e1a2-121">ICorDebugChainEnum (</span><span class="sxs-lookup"><span data-stu-id="0e1a2-121">"ICorDebugChainEnum"</span></span>  
  
- <span data-ttu-id="0e1a2-122">ICorDebugCodeEnum (</span><span class="sxs-lookup"><span data-stu-id="0e1a2-122">"ICorDebugCodeEnum"</span></span>  
  
- <span data-ttu-id="0e1a2-123">Icordebugerrorinfoenum (</span><span class="sxs-lookup"><span data-stu-id="0e1a2-123">"ICorDebugErrorInfoEnum"</span></span>  
  
- [<span data-ttu-id="0e1a2-124">ICorDebugExceptionObjectCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="0e1a2-124">ICorDebugExceptionObjectCallStackEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)  
  
- <span data-ttu-id="0e1a2-125">ICorDebugFrameEnum (</span><span class="sxs-lookup"><span data-stu-id="0e1a2-125">"ICorDebugFrameEnum"</span></span>  
  
- [<span data-ttu-id="0e1a2-126">ICorDebugGCReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="0e1a2-126">ICorDebugGCReferenceEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)  
  
- [<span data-ttu-id="0e1a2-127">ICorDebugGuidToTypeEnum</span><span class="sxs-lookup"><span data-stu-id="0e1a2-127">ICorDebugGuidToTypeEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)  
  
- [<span data-ttu-id="0e1a2-128">ICorDebugHeapEnum</span><span class="sxs-lookup"><span data-stu-id="0e1a2-128">ICorDebugHeapEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)  
  
- [<span data-ttu-id="0e1a2-129">ICorDebugHeapSegmentEnum</span><span class="sxs-lookup"><span data-stu-id="0e1a2-129">ICorDebugHeapSegmentEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)  
  
- <span data-ttu-id="0e1a2-130">ICorDebugModuleEnum (</span><span class="sxs-lookup"><span data-stu-id="0e1a2-130">"ICorDebugModuleEnum"</span></span>  
  
- <span data-ttu-id="0e1a2-131">ICorDebugObjectEnum (</span><span class="sxs-lookup"><span data-stu-id="0e1a2-131">"ICorDebugObjectEnum"</span></span>  
  
- <span data-ttu-id="0e1a2-132">Icordebugprocessenum (</span><span class="sxs-lookup"><span data-stu-id="0e1a2-132">"ICorDebugProcessEnum"</span></span>  
  
- <span data-ttu-id="0e1a2-133">ICorDebugStepperEnum (</span><span class="sxs-lookup"><span data-stu-id="0e1a2-133">"ICorDebugStepperEnum"</span></span>  
  
- <span data-ttu-id="0e1a2-134">ICorDebugThreadEnum (</span><span class="sxs-lookup"><span data-stu-id="0e1a2-134">"ICorDebugThreadEnum"</span></span>  
  
- <span data-ttu-id="0e1a2-135">ICorDebugTypeEnum</span><span class="sxs-lookup"><span data-stu-id="0e1a2-135">"ICorDebugTypeEnum"</span></span>  
  
- <span data-ttu-id="0e1a2-136">ICorDebugValueEnum</span><span class="sxs-lookup"><span data-stu-id="0e1a2-136">"ICorDebugValueEnum"</span></span>  
  
- [<span data-ttu-id="0e1a2-137">ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="0e1a2-137">ICorDebugVariableHomeEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)  
  
> [!NOTE]
> <span data-ttu-id="0e1a2-138">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="0e1a2-138">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e1a2-139">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0e1a2-139">Requirements</span></span>  
 <span data-ttu-id="0e1a2-140">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e1a2-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e1a2-141">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="0e1a2-141">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0e1a2-142">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0e1a2-142">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0e1a2-143">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e1a2-143">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e1a2-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="0e1a2-144">See also</span></span>

- [<span data-ttu-id="0e1a2-145">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="0e1a2-145">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
