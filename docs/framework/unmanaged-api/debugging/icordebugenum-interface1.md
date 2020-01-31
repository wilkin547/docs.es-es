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
ms.openlocfilehash: cc5598f9cbec4b97bb75f83fb18ccf8742904272
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783005"
---
# <a name="icordebugenum-interface"></a><span data-ttu-id="60c25-102">Interfaz ICorDebugEnum</span><span class="sxs-lookup"><span data-stu-id="60c25-102">ICorDebugEnum Interface</span></span>

<span data-ttu-id="60c25-103">Actúa como la interfaz base abstracta para los enumeradores que se usan en una aplicación de depuración.</span><span class="sxs-lookup"><span data-stu-id="60c25-103">Serves as the abstract base interface for the enumerators that are used by a debugging application.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="60c25-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="60c25-104">Methods</span></span>  
  
|<span data-ttu-id="60c25-105">Método</span><span class="sxs-lookup"><span data-stu-id="60c25-105">Method</span></span>|<span data-ttu-id="60c25-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="60c25-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="60c25-107">Clone (método)</span><span class="sxs-lookup"><span data-stu-id="60c25-107">Clone Method</span></span>](icordebugenum-clone-method.md)|<span data-ttu-id="60c25-108">Crea una copia de este objeto `ICorDebugEnum`.</span><span class="sxs-lookup"><span data-stu-id="60c25-108">Creates a copy of this `ICorDebugEnum` object.</span></span>|  
|[<span data-ttu-id="60c25-109">GetCount (método)</span><span class="sxs-lookup"><span data-stu-id="60c25-109">GetCount Method</span></span>](icordebugenum-getcount-method.md)|<span data-ttu-id="60c25-110">Obtiene el número de elementos de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="60c25-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="60c25-111">Reset (método)</span><span class="sxs-lookup"><span data-stu-id="60c25-111">Reset Method</span></span>](icordebugenum-reset-method.md)|<span data-ttu-id="60c25-112">Mueve el cursor al principio de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="60c25-112">Moves the cursor to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="60c25-113">Skip (método)</span><span class="sxs-lookup"><span data-stu-id="60c25-113">Skip Method</span></span>](icordebugenum-skip-method.md)|<span data-ttu-id="60c25-114">Mueve el cursor hacia delante en la enumeración el número de elementos especificado.</span><span class="sxs-lookup"><span data-stu-id="60c25-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="60c25-115">Notas</span><span class="sxs-lookup"><span data-stu-id="60c25-115">Remarks</span></span>  
 <span data-ttu-id="60c25-116">Los enumeradores siguientes derivan de `ICorDebugEnum`:</span><span class="sxs-lookup"><span data-stu-id="60c25-116">The following enumerators derive from `ICorDebugEnum`:</span></span>  
  
- <span data-ttu-id="60c25-117">ICorDebugAppDomainEnum (</span><span class="sxs-lookup"><span data-stu-id="60c25-117">"ICorDebugAppDomainEnum"</span></span>  
  
- <span data-ttu-id="60c25-118">ICorDebugAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="60c25-118">"ICorDebugAssemblyEnum"</span></span>  
  
- [<span data-ttu-id="60c25-119">ICorDebugBlockingObjectEnum</span><span class="sxs-lookup"><span data-stu-id="60c25-119">ICorDebugBlockingObjectEnum</span></span>](icordebugblockingobjectenum-interface.md)  
  
- <span data-ttu-id="60c25-120">ICorDebugBreakpointEnum (</span><span class="sxs-lookup"><span data-stu-id="60c25-120">"ICorDebugBreakpointEnum"</span></span>  
  
- <span data-ttu-id="60c25-121">ICorDebugChainEnum (</span><span class="sxs-lookup"><span data-stu-id="60c25-121">"ICorDebugChainEnum"</span></span>  
  
- <span data-ttu-id="60c25-122">ICorDebugCodeEnum (</span><span class="sxs-lookup"><span data-stu-id="60c25-122">"ICorDebugCodeEnum"</span></span>  
  
- <span data-ttu-id="60c25-123">Icordebugerrorinfoenum (</span><span class="sxs-lookup"><span data-stu-id="60c25-123">"ICorDebugErrorInfoEnum"</span></span>  
  
- [<span data-ttu-id="60c25-124">ICorDebugExceptionObjectCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="60c25-124">ICorDebugExceptionObjectCallStackEnum</span></span>](icordebugexceptionobjectcallstackenum-interface.md)  
  
- <span data-ttu-id="60c25-125">ICorDebugFrameEnum (</span><span class="sxs-lookup"><span data-stu-id="60c25-125">"ICorDebugFrameEnum"</span></span>  
  
- [<span data-ttu-id="60c25-126">ICorDebugGCReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="60c25-126">ICorDebugGCReferenceEnum</span></span>](icordebuggcreferenceenum-interface.md)  
  
- [<span data-ttu-id="60c25-127">ICorDebugGuidToTypeEnum</span><span class="sxs-lookup"><span data-stu-id="60c25-127">ICorDebugGuidToTypeEnum</span></span>](icordebugguidtotypeenum-interface.md)  
  
- [<span data-ttu-id="60c25-128">ICorDebugHeapEnum</span><span class="sxs-lookup"><span data-stu-id="60c25-128">ICorDebugHeapEnum</span></span>](icordebugheapenum-interface.md)  
  
- [<span data-ttu-id="60c25-129">ICorDebugHeapSegmentEnum</span><span class="sxs-lookup"><span data-stu-id="60c25-129">ICorDebugHeapSegmentEnum</span></span>](icordebugheapsegmentenum-interface.md)  
  
- <span data-ttu-id="60c25-130">ICorDebugModuleEnum (</span><span class="sxs-lookup"><span data-stu-id="60c25-130">"ICorDebugModuleEnum"</span></span>  
  
- <span data-ttu-id="60c25-131">ICorDebugObjectEnum (</span><span class="sxs-lookup"><span data-stu-id="60c25-131">"ICorDebugObjectEnum"</span></span>  
  
- <span data-ttu-id="60c25-132">Icordebugprocessenum (</span><span class="sxs-lookup"><span data-stu-id="60c25-132">"ICorDebugProcessEnum"</span></span>  
  
- <span data-ttu-id="60c25-133">ICorDebugStepperEnum (</span><span class="sxs-lookup"><span data-stu-id="60c25-133">"ICorDebugStepperEnum"</span></span>  
  
- <span data-ttu-id="60c25-134">ICorDebugThreadEnum (</span><span class="sxs-lookup"><span data-stu-id="60c25-134">"ICorDebugThreadEnum"</span></span>  
  
- <span data-ttu-id="60c25-135">ICorDebugTypeEnum</span><span class="sxs-lookup"><span data-stu-id="60c25-135">"ICorDebugTypeEnum"</span></span>  
  
- <span data-ttu-id="60c25-136">ICorDebugValueEnum</span><span class="sxs-lookup"><span data-stu-id="60c25-136">"ICorDebugValueEnum"</span></span>  
  
- [<span data-ttu-id="60c25-137">ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="60c25-137">ICorDebugVariableHomeEnum</span></span>](icordebugvariablehomeenum-interface.md)  
  
> [!NOTE]
> <span data-ttu-id="60c25-138">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="60c25-138">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60c25-139">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="60c25-139">Requirements</span></span>  
 <span data-ttu-id="60c25-140">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="60c25-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60c25-141">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="60c25-141">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="60c25-142">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="60c25-142">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="60c25-143">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60c25-143">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60c25-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="60c25-144">See also</span></span>

- [<span data-ttu-id="60c25-145">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="60c25-145">Debugging Interfaces</span></span>](debugging-interfaces.md)
