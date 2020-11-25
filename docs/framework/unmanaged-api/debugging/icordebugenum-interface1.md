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
ms.openlocfilehash: b208444de3b427329988f27b9d252b54143b7240
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95698798"
---
# <a name="icordebugenum-interface"></a><span data-ttu-id="63a93-102">Interfaz ICorDebugEnum</span><span class="sxs-lookup"><span data-stu-id="63a93-102">ICorDebugEnum Interface</span></span>

<span data-ttu-id="63a93-103">Actúa como la interfaz base abstracta para los enumeradores que se usan en una aplicación de depuración.</span><span class="sxs-lookup"><span data-stu-id="63a93-103">Serves as the abstract base interface for the enumerators that are used by a debugging application.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="63a93-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="63a93-104">Methods</span></span>  
  
|<span data-ttu-id="63a93-105">Método</span><span class="sxs-lookup"><span data-stu-id="63a93-105">Method</span></span>|<span data-ttu-id="63a93-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="63a93-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="63a93-107">Clone (Método)</span><span class="sxs-lookup"><span data-stu-id="63a93-107">Clone Method</span></span>](icordebugenum-clone-method.md)|<span data-ttu-id="63a93-108">Crea una copia de este objeto `ICorDebugEnum`.</span><span class="sxs-lookup"><span data-stu-id="63a93-108">Creates a copy of this `ICorDebugEnum` object.</span></span>|  
|[<span data-ttu-id="63a93-109">GetCount (Método)</span><span class="sxs-lookup"><span data-stu-id="63a93-109">GetCount Method</span></span>](icordebugenum-getcount-method.md)|<span data-ttu-id="63a93-110">Obtiene el número de elementos de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="63a93-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="63a93-111">Reset (Método)</span><span class="sxs-lookup"><span data-stu-id="63a93-111">Reset Method</span></span>](icordebugenum-reset-method.md)|<span data-ttu-id="63a93-112">Mueve el cursor al principio de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="63a93-112">Moves the cursor to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="63a93-113">Skip (Método)</span><span class="sxs-lookup"><span data-stu-id="63a93-113">Skip Method</span></span>](icordebugenum-skip-method.md)|<span data-ttu-id="63a93-114">Mueve el cursor hacia delante en la enumeración el número de elementos especificado.</span><span class="sxs-lookup"><span data-stu-id="63a93-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="63a93-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="63a93-115">Remarks</span></span>  

 <span data-ttu-id="63a93-116">Los enumeradores siguientes derivan de `ICorDebugEnum` :</span><span class="sxs-lookup"><span data-stu-id="63a93-116">The following enumerators derive from `ICorDebugEnum`:</span></span>  
  
- <span data-ttu-id="63a93-117">ICorDebugAppDomainEnum (</span><span class="sxs-lookup"><span data-stu-id="63a93-117">"ICorDebugAppDomainEnum"</span></span>  
  
- <span data-ttu-id="63a93-118">ICorDebugAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="63a93-118">"ICorDebugAssemblyEnum"</span></span>  
  
- [<span data-ttu-id="63a93-119">ICorDebugBlockingObjectEnum</span><span class="sxs-lookup"><span data-stu-id="63a93-119">ICorDebugBlockingObjectEnum</span></span>](icordebugblockingobjectenum-interface.md)  
  
- <span data-ttu-id="63a93-120">ICorDebugBreakpointEnum (</span><span class="sxs-lookup"><span data-stu-id="63a93-120">"ICorDebugBreakpointEnum"</span></span>  
  
- <span data-ttu-id="63a93-121">ICorDebugChainEnum (</span><span class="sxs-lookup"><span data-stu-id="63a93-121">"ICorDebugChainEnum"</span></span>  
  
- <span data-ttu-id="63a93-122">ICorDebugCodeEnum (</span><span class="sxs-lookup"><span data-stu-id="63a93-122">"ICorDebugCodeEnum"</span></span>  
  
- <span data-ttu-id="63a93-123">Icordebugerrorinfoenum (</span><span class="sxs-lookup"><span data-stu-id="63a93-123">"ICorDebugErrorInfoEnum"</span></span>  
  
- [<span data-ttu-id="63a93-124">Icordebugexceptionobjectcallstackenum (</span><span class="sxs-lookup"><span data-stu-id="63a93-124">ICorDebugExceptionObjectCallStackEnum</span></span>](icordebugexceptionobjectcallstackenum-interface.md)  
  
- <span data-ttu-id="63a93-125">ICorDebugFrameEnum (</span><span class="sxs-lookup"><span data-stu-id="63a93-125">"ICorDebugFrameEnum"</span></span>  
  
- [<span data-ttu-id="63a93-126">Icordebuggcreferenceenum (</span><span class="sxs-lookup"><span data-stu-id="63a93-126">ICorDebugGCReferenceEnum</span></span>](icordebuggcreferenceenum-interface.md)  
  
- [<span data-ttu-id="63a93-127">Icordebugguidtotypeenum (</span><span class="sxs-lookup"><span data-stu-id="63a93-127">ICorDebugGuidToTypeEnum</span></span>](icordebugguidtotypeenum-interface.md)  
  
- [<span data-ttu-id="63a93-128">Icordebugheapenum (</span><span class="sxs-lookup"><span data-stu-id="63a93-128">ICorDebugHeapEnum</span></span>](icordebugheapenum-interface.md)  
  
- [<span data-ttu-id="63a93-129">Icordebugheapsegmentenum (</span><span class="sxs-lookup"><span data-stu-id="63a93-129">ICorDebugHeapSegmentEnum</span></span>](icordebugheapsegmentenum-interface.md)  
  
- <span data-ttu-id="63a93-130">ICorDebugModuleEnum (</span><span class="sxs-lookup"><span data-stu-id="63a93-130">"ICorDebugModuleEnum"</span></span>  
  
- <span data-ttu-id="63a93-131">ICorDebugObjectEnum (</span><span class="sxs-lookup"><span data-stu-id="63a93-131">"ICorDebugObjectEnum"</span></span>  
  
- <span data-ttu-id="63a93-132">Icordebugprocessenum (</span><span class="sxs-lookup"><span data-stu-id="63a93-132">"ICorDebugProcessEnum"</span></span>  
  
- <span data-ttu-id="63a93-133">ICorDebugStepperEnum (</span><span class="sxs-lookup"><span data-stu-id="63a93-133">"ICorDebugStepperEnum"</span></span>  
  
- <span data-ttu-id="63a93-134">ICorDebugThreadEnum (</span><span class="sxs-lookup"><span data-stu-id="63a93-134">"ICorDebugThreadEnum"</span></span>  
  
- <span data-ttu-id="63a93-135">ICorDebugTypeEnum</span><span class="sxs-lookup"><span data-stu-id="63a93-135">"ICorDebugTypeEnum"</span></span>  
  
- <span data-ttu-id="63a93-136">ICorDebugValueEnum</span><span class="sxs-lookup"><span data-stu-id="63a93-136">"ICorDebugValueEnum"</span></span>  
  
- [<span data-ttu-id="63a93-137">ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="63a93-137">ICorDebugVariableHomeEnum</span></span>](icordebugvariablehomeenum-interface.md)  
  
> [!NOTE]
> <span data-ttu-id="63a93-138">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="63a93-138">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63a93-139">Requisitos</span><span class="sxs-lookup"><span data-stu-id="63a93-139">Requirements</span></span>  

 <span data-ttu-id="63a93-140">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63a93-140">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63a93-141">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="63a93-141">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="63a93-142">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="63a93-142">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="63a93-143">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63a93-143">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63a93-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="63a93-144">See also</span></span>

- [<span data-ttu-id="63a93-145">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="63a93-145">Debugging Interfaces</span></span>](debugging-interfaces.md)
