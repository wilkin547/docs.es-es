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
ms.openlocfilehash: eb3aca0713b8b11bdfaa23bf33c8e1a0b302e272
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64606539"
---
# <a name="icordebugenum-interface"></a><span data-ttu-id="f21de-102">Interfaz ICorDebugEnum</span><span class="sxs-lookup"><span data-stu-id="f21de-102">ICorDebugEnum Interface</span></span>

<span data-ttu-id="f21de-103">Sirve como la interfaz base abstracta para los enumeradores utilizados por una aplicación de depuración.</span><span class="sxs-lookup"><span data-stu-id="f21de-103">Serves as the abstract base interface for the enumerators that are used by a debugging application.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f21de-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="f21de-104">Methods</span></span>  
  
|<span data-ttu-id="f21de-105">Método</span><span class="sxs-lookup"><span data-stu-id="f21de-105">Method</span></span>|<span data-ttu-id="f21de-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="f21de-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f21de-107">Clone (método)</span><span class="sxs-lookup"><span data-stu-id="f21de-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-clone-method.md)|<span data-ttu-id="f21de-108">Crea una copia de este `ICorDebugEnum` objeto.</span><span class="sxs-lookup"><span data-stu-id="f21de-108">Creates a copy of this `ICorDebugEnum` object.</span></span>|  
|[<span data-ttu-id="f21de-109">GetCount (método)</span><span class="sxs-lookup"><span data-stu-id="f21de-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-getcount-method.md)|<span data-ttu-id="f21de-110">Obtiene el número de elementos de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="f21de-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="f21de-111">Reset (método)</span><span class="sxs-lookup"><span data-stu-id="f21de-111">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-reset-method.md)|<span data-ttu-id="f21de-112">Mueve el cursor al principio de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="f21de-112">Moves the cursor to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="f21de-113">Skip (método)</span><span class="sxs-lookup"><span data-stu-id="f21de-113">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-skip-method.md)|<span data-ttu-id="f21de-114">Mueve el cursor hacia delante en la enumeración por el número especificado de elementos.</span><span class="sxs-lookup"><span data-stu-id="f21de-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f21de-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f21de-115">Remarks</span></span>  
 <span data-ttu-id="f21de-116">Los enumeradores siguientes derivan de `ICorDebugEnum`:</span><span class="sxs-lookup"><span data-stu-id="f21de-116">The following enumerators derive from `ICorDebugEnum`:</span></span>  
  
- <span data-ttu-id="f21de-117">"ICorDebugAppDomainEnum"</span><span class="sxs-lookup"><span data-stu-id="f21de-117">"ICorDebugAppDomainEnum"</span></span>  
  
- <span data-ttu-id="f21de-118">"ICorDebugAssemblyEnum"</span><span class="sxs-lookup"><span data-stu-id="f21de-118">"ICorDebugAssemblyEnum"</span></span>  
  
- [<span data-ttu-id="f21de-119">ICorDebugBlockingObjectEnum</span><span class="sxs-lookup"><span data-stu-id="f21de-119">ICorDebugBlockingObjectEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-interface.md)  
  
- <span data-ttu-id="f21de-120">"ICorDebugBreakpointEnum"</span><span class="sxs-lookup"><span data-stu-id="f21de-120">"ICorDebugBreakpointEnum"</span></span>  
  
- <span data-ttu-id="f21de-121">"ICorDebugChainEnum"</span><span class="sxs-lookup"><span data-stu-id="f21de-121">"ICorDebugChainEnum"</span></span>  
  
- <span data-ttu-id="f21de-122">"ICorDebugCodeEnum"</span><span class="sxs-lookup"><span data-stu-id="f21de-122">"ICorDebugCodeEnum"</span></span>  
  
- <span data-ttu-id="f21de-123">"ICorDebugErrorInfoEnum"</span><span class="sxs-lookup"><span data-stu-id="f21de-123">"ICorDebugErrorInfoEnum"</span></span>  
  
- [<span data-ttu-id="f21de-124">ICorDebugExceptionObjectCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="f21de-124">ICorDebugExceptionObjectCallStackEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)  
  
- <span data-ttu-id="f21de-125">"ICorDebugFrameEnum"</span><span class="sxs-lookup"><span data-stu-id="f21de-125">"ICorDebugFrameEnum"</span></span>  
  
- [<span data-ttu-id="f21de-126">ICorDebugGCReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="f21de-126">ICorDebugGCReferenceEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)  
  
- [<span data-ttu-id="f21de-127">ICorDebugGuidToTypeEnum</span><span class="sxs-lookup"><span data-stu-id="f21de-127">ICorDebugGuidToTypeEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)  
  
- [<span data-ttu-id="f21de-128">ICorDebugHeapEnum</span><span class="sxs-lookup"><span data-stu-id="f21de-128">ICorDebugHeapEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)  
  
- [<span data-ttu-id="f21de-129">ICorDebugHeapSegmentEnum</span><span class="sxs-lookup"><span data-stu-id="f21de-129">ICorDebugHeapSegmentEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)  
  
- <span data-ttu-id="f21de-130">"ICorDebugModuleEnum"</span><span class="sxs-lookup"><span data-stu-id="f21de-130">"ICorDebugModuleEnum"</span></span>  
  
- <span data-ttu-id="f21de-131">"ICorDebugObjectEnum"</span><span class="sxs-lookup"><span data-stu-id="f21de-131">"ICorDebugObjectEnum"</span></span>  
  
- <span data-ttu-id="f21de-132">"ICorDebugProcessEnum"</span><span class="sxs-lookup"><span data-stu-id="f21de-132">"ICorDebugProcessEnum"</span></span>  
  
- <span data-ttu-id="f21de-133">"ICorDebugStepperEnum"</span><span class="sxs-lookup"><span data-stu-id="f21de-133">"ICorDebugStepperEnum"</span></span>  
  
- <span data-ttu-id="f21de-134">"ICorDebugThreadEnum"</span><span class="sxs-lookup"><span data-stu-id="f21de-134">"ICorDebugThreadEnum"</span></span>  
  
- <span data-ttu-id="f21de-135">"ICorDebugTypeEnum"</span><span class="sxs-lookup"><span data-stu-id="f21de-135">"ICorDebugTypeEnum"</span></span>  
  
- <span data-ttu-id="f21de-136">"ICorDebugValueEnum"</span><span class="sxs-lookup"><span data-stu-id="f21de-136">"ICorDebugValueEnum"</span></span>  
  
- [<span data-ttu-id="f21de-137">ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="f21de-137">ICorDebugVariableHomeEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)  
  
> [!NOTE]
>  <span data-ttu-id="f21de-138">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="f21de-138">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f21de-139">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f21de-139">Requirements</span></span>  
 <span data-ttu-id="f21de-140">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f21de-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f21de-141">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f21de-141">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f21de-142">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f21de-142">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f21de-143">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f21de-143">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f21de-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="f21de-144">See also</span></span>

- [<span data-ttu-id="f21de-145">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="f21de-145">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
