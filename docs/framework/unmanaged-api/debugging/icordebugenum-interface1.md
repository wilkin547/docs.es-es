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
ms.openlocfilehash: 9afaeebfdb98a404ea53b0b5ec147f8c8104e14d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59148816"
---
# <a name="icordebugenum-interface"></a><span data-ttu-id="44a8f-102">Interfaz ICorDebugEnum</span><span class="sxs-lookup"><span data-stu-id="44a8f-102">ICorDebugEnum Interface</span></span>

<span data-ttu-id="44a8f-103">Sirve como la interfaz base abstracta para los enumeradores utilizados por una aplicación de depuración.</span><span class="sxs-lookup"><span data-stu-id="44a8f-103">Serves as the abstract base interface for the enumerators that are used by a debugging application.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="44a8f-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="44a8f-104">Methods</span></span>  
  
|<span data-ttu-id="44a8f-105">Método</span><span class="sxs-lookup"><span data-stu-id="44a8f-105">Method</span></span>|<span data-ttu-id="44a8f-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="44a8f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="44a8f-107">Método Clone</span><span class="sxs-lookup"><span data-stu-id="44a8f-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-clone-method.md)|<span data-ttu-id="44a8f-108">Crea una copia de este `ICorDebugEnum` objeto.</span><span class="sxs-lookup"><span data-stu-id="44a8f-108">Creates a copy of this `ICorDebugEnum` object.</span></span>|  
|[<span data-ttu-id="44a8f-109">Método GetCount</span><span class="sxs-lookup"><span data-stu-id="44a8f-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-getcount-method.md)|<span data-ttu-id="44a8f-110">Obtiene el número de elementos de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="44a8f-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="44a8f-111">Método Reset</span><span class="sxs-lookup"><span data-stu-id="44a8f-111">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-reset-method.md)|<span data-ttu-id="44a8f-112">Mueve el cursor al principio de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="44a8f-112">Moves the cursor to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="44a8f-113">Método Skip</span><span class="sxs-lookup"><span data-stu-id="44a8f-113">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-skip-method.md)|<span data-ttu-id="44a8f-114">Mueve el cursor hacia delante en la enumeración por el número especificado de elementos.</span><span class="sxs-lookup"><span data-stu-id="44a8f-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="44a8f-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="44a8f-115">Remarks</span></span>  
 <span data-ttu-id="44a8f-116">Los enumeradores siguientes derivan de `ICorDebugEnum`:</span><span class="sxs-lookup"><span data-stu-id="44a8f-116">The following enumerators derive from `ICorDebugEnum`:</span></span>  
  
-   <span data-ttu-id="44a8f-117">"ICorDebugAppDomainEnum"</span><span class="sxs-lookup"><span data-stu-id="44a8f-117">"ICorDebugAppDomainEnum"</span></span>  
  
-   <span data-ttu-id="44a8f-118">"ICorDebugAssemblyEnum"</span><span class="sxs-lookup"><span data-stu-id="44a8f-118">"ICorDebugAssemblyEnum"</span></span>  
  
-   [<span data-ttu-id="44a8f-119">ICorDebugBlockingObjectEnum</span><span class="sxs-lookup"><span data-stu-id="44a8f-119">ICorDebugBlockingObjectEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-interface.md)  
  
-   <span data-ttu-id="44a8f-120">"ICorDebugBreakpointEnum"</span><span class="sxs-lookup"><span data-stu-id="44a8f-120">"ICorDebugBreakpointEnum"</span></span>  
  
-   <span data-ttu-id="44a8f-121">"ICorDebugChainEnum"</span><span class="sxs-lookup"><span data-stu-id="44a8f-121">"ICorDebugChainEnum"</span></span>  
  
-   <span data-ttu-id="44a8f-122">"ICorDebugCodeEnum"</span><span class="sxs-lookup"><span data-stu-id="44a8f-122">"ICorDebugCodeEnum"</span></span>  
  
-   <span data-ttu-id="44a8f-123">"ICorDebugErrorInfoEnum"</span><span class="sxs-lookup"><span data-stu-id="44a8f-123">"ICorDebugErrorInfoEnum"</span></span>  
  
-   [<span data-ttu-id="44a8f-124">ICorDebugExceptionObjectCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="44a8f-124">ICorDebugExceptionObjectCallStackEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)  
  
-   <span data-ttu-id="44a8f-125">"ICorDebugFrameEnum"</span><span class="sxs-lookup"><span data-stu-id="44a8f-125">"ICorDebugFrameEnum"</span></span>  
  
-   [<span data-ttu-id="44a8f-126">ICorDebugGCReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="44a8f-126">ICorDebugGCReferenceEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)  
  
-   [<span data-ttu-id="44a8f-127">ICorDebugGuidToTypeEnum</span><span class="sxs-lookup"><span data-stu-id="44a8f-127">ICorDebugGuidToTypeEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)  
  
-   [<span data-ttu-id="44a8f-128">ICorDebugHeapEnum</span><span class="sxs-lookup"><span data-stu-id="44a8f-128">ICorDebugHeapEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)  
  
-   [<span data-ttu-id="44a8f-129">ICorDebugHeapSegmentEnum</span><span class="sxs-lookup"><span data-stu-id="44a8f-129">ICorDebugHeapSegmentEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)  
  
-   <span data-ttu-id="44a8f-130">"ICorDebugModuleEnum"</span><span class="sxs-lookup"><span data-stu-id="44a8f-130">"ICorDebugModuleEnum"</span></span>  
  
-   <span data-ttu-id="44a8f-131">"ICorDebugObjectEnum"</span><span class="sxs-lookup"><span data-stu-id="44a8f-131">"ICorDebugObjectEnum"</span></span>  
  
-   <span data-ttu-id="44a8f-132">"ICorDebugProcessEnum"</span><span class="sxs-lookup"><span data-stu-id="44a8f-132">"ICorDebugProcessEnum"</span></span>  
  
-   <span data-ttu-id="44a8f-133">"ICorDebugStepperEnum"</span><span class="sxs-lookup"><span data-stu-id="44a8f-133">"ICorDebugStepperEnum"</span></span>  
  
-   <span data-ttu-id="44a8f-134">"ICorDebugThreadEnum"</span><span class="sxs-lookup"><span data-stu-id="44a8f-134">"ICorDebugThreadEnum"</span></span>  
  
-   <span data-ttu-id="44a8f-135">"ICorDebugTypeEnum"</span><span class="sxs-lookup"><span data-stu-id="44a8f-135">"ICorDebugTypeEnum"</span></span>  
  
-   <span data-ttu-id="44a8f-136">"ICorDebugValueEnum"</span><span class="sxs-lookup"><span data-stu-id="44a8f-136">"ICorDebugValueEnum"</span></span>  
  
-   [<span data-ttu-id="44a8f-137">ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="44a8f-137">ICorDebugVariableHomeEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)  
  
> [!NOTE]
>  <span data-ttu-id="44a8f-138">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="44a8f-138">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44a8f-139">Requisitos</span><span class="sxs-lookup"><span data-stu-id="44a8f-139">Requirements</span></span>  
 <span data-ttu-id="44a8f-140">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44a8f-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44a8f-141">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="44a8f-141">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="44a8f-142">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="44a8f-142">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="44a8f-143">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="44a8f-143">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="44a8f-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="44a8f-144">See also</span></span>

- [<span data-ttu-id="44a8f-145">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="44a8f-145">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
