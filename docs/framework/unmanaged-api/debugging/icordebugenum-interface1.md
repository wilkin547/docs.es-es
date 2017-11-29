---
title: ICorDebugEnum Interfaz1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEnum
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEnum
helpviewer_keywords: ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: 80be7efe-2c32-4b9f-8c52-40c6f6268219
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7f6596918819294f0ab68735cec12f9eab8bf83e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugenum-interface1"></a><span data-ttu-id="e06d9-102">ICorDebugEnum Interfaz1</span><span class="sxs-lookup"><span data-stu-id="e06d9-102">ICorDebugEnum Interface1</span></span>
<span data-ttu-id="e06d9-103">Actúa como la interfaz base abstracta para los enumeradores utilizados por una aplicación de depuración.</span><span class="sxs-lookup"><span data-stu-id="e06d9-103">Serves as the abstract base interface for the enumerators that are used by a debugging application.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e06d9-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="e06d9-104">Methods</span></span>  
  
|<span data-ttu-id="e06d9-105">Método</span><span class="sxs-lookup"><span data-stu-id="e06d9-105">Method</span></span>|<span data-ttu-id="e06d9-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="e06d9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e06d9-107">Clone (método)</span><span class="sxs-lookup"><span data-stu-id="e06d9-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-clone-method.md)|<span data-ttu-id="e06d9-108">Crea una copia de esta `ICorDebugEnum` objeto.</span><span class="sxs-lookup"><span data-stu-id="e06d9-108">Creates a copy of this `ICorDebugEnum` object.</span></span>|  
|[<span data-ttu-id="e06d9-109">GetCount (método)</span><span class="sxs-lookup"><span data-stu-id="e06d9-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-getcount-method.md)|<span data-ttu-id="e06d9-110">Obtiene el número de elementos de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="e06d9-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="e06d9-111">Reset (método)</span><span class="sxs-lookup"><span data-stu-id="e06d9-111">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-reset-method.md)|<span data-ttu-id="e06d9-112">Mueve el cursor al principio de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="e06d9-112">Moves the cursor to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="e06d9-113">Skip (método)</span><span class="sxs-lookup"><span data-stu-id="e06d9-113">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-skip-method.md)|<span data-ttu-id="e06d9-114">Mueve el cursor hacia delante en la enumeración el número especificado de elementos.</span><span class="sxs-lookup"><span data-stu-id="e06d9-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e06d9-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e06d9-115">Remarks</span></span>  
 <span data-ttu-id="e06d9-116">Los enumeradores siguientes derivan de `ICorDebugEnum`:</span><span class="sxs-lookup"><span data-stu-id="e06d9-116">The following enumerators derive from `ICorDebugEnum`:</span></span>  
  
-   <span data-ttu-id="e06d9-117">"ICorDebugAppDomainEnum"</span><span class="sxs-lookup"><span data-stu-id="e06d9-117">"ICorDebugAppDomainEnum"</span></span>  
  
-   <span data-ttu-id="e06d9-118">"ICorDebugAssemblyEnum"</span><span class="sxs-lookup"><span data-stu-id="e06d9-118">"ICorDebugAssemblyEnum"</span></span>  
  
-   [<span data-ttu-id="e06d9-119">ICorDebugBlockingObjectEnum</span><span class="sxs-lookup"><span data-stu-id="e06d9-119">ICorDebugBlockingObjectEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-interface.md)  
  
-   <span data-ttu-id="e06d9-120">"ICorDebugBreakpointEnum"</span><span class="sxs-lookup"><span data-stu-id="e06d9-120">"ICorDebugBreakpointEnum"</span></span>  
  
-   <span data-ttu-id="e06d9-121">"ICorDebugChainEnum"</span><span class="sxs-lookup"><span data-stu-id="e06d9-121">"ICorDebugChainEnum"</span></span>  
  
-   <span data-ttu-id="e06d9-122">"ICorDebugCodeEnum"</span><span class="sxs-lookup"><span data-stu-id="e06d9-122">"ICorDebugCodeEnum"</span></span>  
  
-   <span data-ttu-id="e06d9-123">"ICorDebugErrorInfoEnum"</span><span class="sxs-lookup"><span data-stu-id="e06d9-123">"ICorDebugErrorInfoEnum"</span></span>  
  
-   [<span data-ttu-id="e06d9-124">ICorDebugExceptionObjectCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="e06d9-124">ICorDebugExceptionObjectCallStackEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)  
  
-   <span data-ttu-id="e06d9-125">"ICorDebugFrameEnum"</span><span class="sxs-lookup"><span data-stu-id="e06d9-125">"ICorDebugFrameEnum"</span></span>  
  
-   [<span data-ttu-id="e06d9-126">ICorDebugGCReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="e06d9-126">ICorDebugGCReferenceEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)  
  
-   [<span data-ttu-id="e06d9-127">ICorDebugGuidToTypeEnum</span><span class="sxs-lookup"><span data-stu-id="e06d9-127">ICorDebugGuidToTypeEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)  
  
-   [<span data-ttu-id="e06d9-128">ICorDebugHeapEnum</span><span class="sxs-lookup"><span data-stu-id="e06d9-128">ICorDebugHeapEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)  
  
-   [<span data-ttu-id="e06d9-129">ICorDebugHeapSegmentEnum</span><span class="sxs-lookup"><span data-stu-id="e06d9-129">ICorDebugHeapSegmentEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)  
  
-   <span data-ttu-id="e06d9-130">"ICorDebugModuleEnum"</span><span class="sxs-lookup"><span data-stu-id="e06d9-130">"ICorDebugModuleEnum"</span></span>  
  
-   <span data-ttu-id="e06d9-131">"ICorDebugObjectEnum"</span><span class="sxs-lookup"><span data-stu-id="e06d9-131">"ICorDebugObjectEnum"</span></span>  
  
-   <span data-ttu-id="e06d9-132">"ICorDebugProcessEnum"</span><span class="sxs-lookup"><span data-stu-id="e06d9-132">"ICorDebugProcessEnum"</span></span>  
  
-   <span data-ttu-id="e06d9-133">"ICorDebugStepperEnum"</span><span class="sxs-lookup"><span data-stu-id="e06d9-133">"ICorDebugStepperEnum"</span></span>  
  
-   <span data-ttu-id="e06d9-134">"ICorDebugThreadEnum"</span><span class="sxs-lookup"><span data-stu-id="e06d9-134">"ICorDebugThreadEnum"</span></span>  
  
-   <span data-ttu-id="e06d9-135">"ICorDebugTypeEnum"</span><span class="sxs-lookup"><span data-stu-id="e06d9-135">"ICorDebugTypeEnum"</span></span>  
  
-   <span data-ttu-id="e06d9-136">"ICorDebugValueEnum"</span><span class="sxs-lookup"><span data-stu-id="e06d9-136">"ICorDebugValueEnum"</span></span>  
  
-   [<span data-ttu-id="e06d9-137">ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="e06d9-137">ICorDebugVariableHomeEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)  
  
> [!NOTE]
>  <span data-ttu-id="e06d9-138">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="e06d9-138">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e06d9-139">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e06d9-139">Requirements</span></span>  
 <span data-ttu-id="e06d9-140">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e06d9-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e06d9-141">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e06d9-141">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e06d9-142">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e06d9-142">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e06d9-143">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e06d9-143">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e06d9-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="e06d9-144">See Also</span></span>  
 [<span data-ttu-id="e06d9-145">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="e06d9-145">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
