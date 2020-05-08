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
ms.openlocfilehash: 7575be3f5074243b251c80b8dd5bdbb12e5d50fd
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976335"
---
# <a name="icordebugenum-interface"></a><span data-ttu-id="f3c2e-102">Interfaz ICorDebugEnum</span><span class="sxs-lookup"><span data-stu-id="f3c2e-102">ICorDebugEnum Interface</span></span>

<span data-ttu-id="f3c2e-103">Actúa como la interfaz base abstracta para los enumeradores que se usan en una aplicación de depuración.</span><span class="sxs-lookup"><span data-stu-id="f3c2e-103">Serves as the abstract base interface for the enumerators that are used by a debugging application.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f3c2e-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="f3c2e-104">Methods</span></span>  
  
|<span data-ttu-id="f3c2e-105">Método</span><span class="sxs-lookup"><span data-stu-id="f3c2e-105">Method</span></span>|<span data-ttu-id="f3c2e-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="f3c2e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f3c2e-107">Método Clone</span><span class="sxs-lookup"><span data-stu-id="f3c2e-107">Clone Method</span></span>](icordebugenum-clone-method.md)|<span data-ttu-id="f3c2e-108">Crea una copia de este objeto `ICorDebugEnum`.</span><span class="sxs-lookup"><span data-stu-id="f3c2e-108">Creates a copy of this `ICorDebugEnum` object.</span></span>|  
|[<span data-ttu-id="f3c2e-109">Método GetCount</span><span class="sxs-lookup"><span data-stu-id="f3c2e-109">GetCount Method</span></span>](icordebugenum-getcount-method.md)|<span data-ttu-id="f3c2e-110">Obtiene el número de elementos de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="f3c2e-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="f3c2e-111">Reset (Método)</span><span class="sxs-lookup"><span data-stu-id="f3c2e-111">Reset Method</span></span>](icordebugenum-reset-method.md)|<span data-ttu-id="f3c2e-112">Mueve el cursor al principio de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="f3c2e-112">Moves the cursor to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="f3c2e-113">Método Skip</span><span class="sxs-lookup"><span data-stu-id="f3c2e-113">Skip Method</span></span>](icordebugenum-skip-method.md)|<span data-ttu-id="f3c2e-114">Mueve el cursor hacia delante en la enumeración el número de elementos especificado.</span><span class="sxs-lookup"><span data-stu-id="f3c2e-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f3c2e-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f3c2e-115">Remarks</span></span>  
 <span data-ttu-id="f3c2e-116">Los enumeradores siguientes derivan `ICorDebugEnum`de:</span><span class="sxs-lookup"><span data-stu-id="f3c2e-116">The following enumerators derive from `ICorDebugEnum`:</span></span>  
  
- <span data-ttu-id="f3c2e-117">ICorDebugAppDomainEnum (</span><span class="sxs-lookup"><span data-stu-id="f3c2e-117">"ICorDebugAppDomainEnum"</span></span>  
  
- <span data-ttu-id="f3c2e-118">ICorDebugAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="f3c2e-118">"ICorDebugAssemblyEnum"</span></span>  
  
- [<span data-ttu-id="f3c2e-119">ICorDebugBlockingObjectEnum</span><span class="sxs-lookup"><span data-stu-id="f3c2e-119">ICorDebugBlockingObjectEnum</span></span>](icordebugblockingobjectenum-interface.md)  
  
- <span data-ttu-id="f3c2e-120">ICorDebugBreakpointEnum (</span><span class="sxs-lookup"><span data-stu-id="f3c2e-120">"ICorDebugBreakpointEnum"</span></span>  
  
- <span data-ttu-id="f3c2e-121">ICorDebugChainEnum (</span><span class="sxs-lookup"><span data-stu-id="f3c2e-121">"ICorDebugChainEnum"</span></span>  
  
- <span data-ttu-id="f3c2e-122">ICorDebugCodeEnum (</span><span class="sxs-lookup"><span data-stu-id="f3c2e-122">"ICorDebugCodeEnum"</span></span>  
  
- <span data-ttu-id="f3c2e-123">Icordebugerrorinfoenum (</span><span class="sxs-lookup"><span data-stu-id="f3c2e-123">"ICorDebugErrorInfoEnum"</span></span>  
  
- [<span data-ttu-id="f3c2e-124">Icordebugexceptionobjectcallstackenum (</span><span class="sxs-lookup"><span data-stu-id="f3c2e-124">ICorDebugExceptionObjectCallStackEnum</span></span>](icordebugexceptionobjectcallstackenum-interface.md)  
  
- <span data-ttu-id="f3c2e-125">ICorDebugFrameEnum (</span><span class="sxs-lookup"><span data-stu-id="f3c2e-125">"ICorDebugFrameEnum"</span></span>  
  
- [<span data-ttu-id="f3c2e-126">Icordebuggcreferenceenum (</span><span class="sxs-lookup"><span data-stu-id="f3c2e-126">ICorDebugGCReferenceEnum</span></span>](icordebuggcreferenceenum-interface.md)  
  
- [<span data-ttu-id="f3c2e-127">Icordebugguidtotypeenum (</span><span class="sxs-lookup"><span data-stu-id="f3c2e-127">ICorDebugGuidToTypeEnum</span></span>](icordebugguidtotypeenum-interface.md)  
  
- [<span data-ttu-id="f3c2e-128">Icordebugheapenum (</span><span class="sxs-lookup"><span data-stu-id="f3c2e-128">ICorDebugHeapEnum</span></span>](icordebugheapenum-interface.md)  
  
- [<span data-ttu-id="f3c2e-129">Icordebugheapsegmentenum (</span><span class="sxs-lookup"><span data-stu-id="f3c2e-129">ICorDebugHeapSegmentEnum</span></span>](icordebugheapsegmentenum-interface.md)  
  
- <span data-ttu-id="f3c2e-130">ICorDebugModuleEnum (</span><span class="sxs-lookup"><span data-stu-id="f3c2e-130">"ICorDebugModuleEnum"</span></span>  
  
- <span data-ttu-id="f3c2e-131">ICorDebugObjectEnum (</span><span class="sxs-lookup"><span data-stu-id="f3c2e-131">"ICorDebugObjectEnum"</span></span>  
  
- <span data-ttu-id="f3c2e-132">Icordebugprocessenum (</span><span class="sxs-lookup"><span data-stu-id="f3c2e-132">"ICorDebugProcessEnum"</span></span>  
  
- <span data-ttu-id="f3c2e-133">ICorDebugStepperEnum (</span><span class="sxs-lookup"><span data-stu-id="f3c2e-133">"ICorDebugStepperEnum"</span></span>  
  
- <span data-ttu-id="f3c2e-134">ICorDebugThreadEnum (</span><span class="sxs-lookup"><span data-stu-id="f3c2e-134">"ICorDebugThreadEnum"</span></span>  
  
- <span data-ttu-id="f3c2e-135">ICorDebugTypeEnum</span><span class="sxs-lookup"><span data-stu-id="f3c2e-135">"ICorDebugTypeEnum"</span></span>  
  
- <span data-ttu-id="f3c2e-136">ICorDebugValueEnum</span><span class="sxs-lookup"><span data-stu-id="f3c2e-136">"ICorDebugValueEnum"</span></span>  
  
- [<span data-ttu-id="f3c2e-137">ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="f3c2e-137">ICorDebugVariableHomeEnum</span></span>](icordebugvariablehomeenum-interface.md)  
  
> [!NOTE]
> <span data-ttu-id="f3c2e-138">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="f3c2e-138">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3c2e-139">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f3c2e-139">Requirements</span></span>  
 <span data-ttu-id="f3c2e-140">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3c2e-140">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3c2e-141">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f3c2e-141">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f3c2e-142">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f3c2e-142">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f3c2e-143">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3c2e-143">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3c2e-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f3c2e-144">See also</span></span>

- [<span data-ttu-id="f3c2e-145">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="f3c2e-145">Debugging Interfaces</span></span>](debugging-interfaces.md)
