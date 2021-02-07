---
description: 'Más información sobre: ICorDebugEnum (interfaz)'
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
ms.openlocfilehash: 20d2bb14bddcaf40802567ec78a8e318ac1db380
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99694479"
---
# <a name="icordebugenum-interface"></a><span data-ttu-id="afe7e-103">Interfaz ICorDebugEnum</span><span class="sxs-lookup"><span data-stu-id="afe7e-103">ICorDebugEnum Interface</span></span>

<span data-ttu-id="afe7e-104">Actúa como la interfaz base abstracta para los enumeradores que se usan en una aplicación de depuración.</span><span class="sxs-lookup"><span data-stu-id="afe7e-104">Serves as the abstract base interface for the enumerators that are used by a debugging application.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="afe7e-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="afe7e-105">Methods</span></span>  
  
|<span data-ttu-id="afe7e-106">Método</span><span class="sxs-lookup"><span data-stu-id="afe7e-106">Method</span></span>|<span data-ttu-id="afe7e-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="afe7e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="afe7e-108">Método Clone</span><span class="sxs-lookup"><span data-stu-id="afe7e-108">Clone Method</span></span>](icordebugenum-clone-method.md)|<span data-ttu-id="afe7e-109">Crea una copia de este objeto `ICorDebugEnum`.</span><span class="sxs-lookup"><span data-stu-id="afe7e-109">Creates a copy of this `ICorDebugEnum` object.</span></span>|  
|[<span data-ttu-id="afe7e-110">Método GetCount</span><span class="sxs-lookup"><span data-stu-id="afe7e-110">GetCount Method</span></span>](icordebugenum-getcount-method.md)|<span data-ttu-id="afe7e-111">Obtiene el número de elementos de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="afe7e-111">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="afe7e-112">Reset (Método)</span><span class="sxs-lookup"><span data-stu-id="afe7e-112">Reset Method</span></span>](icordebugenum-reset-method.md)|<span data-ttu-id="afe7e-113">Mueve el cursor al principio de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="afe7e-113">Moves the cursor to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="afe7e-114">Método Skip</span><span class="sxs-lookup"><span data-stu-id="afe7e-114">Skip Method</span></span>](icordebugenum-skip-method.md)|<span data-ttu-id="afe7e-115">Mueve el cursor hacia delante en la enumeración el número de elementos especificado.</span><span class="sxs-lookup"><span data-stu-id="afe7e-115">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="afe7e-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="afe7e-116">Remarks</span></span>  

 <span data-ttu-id="afe7e-117">Los enumeradores siguientes derivan de `ICorDebugEnum` :</span><span class="sxs-lookup"><span data-stu-id="afe7e-117">The following enumerators derive from `ICorDebugEnum`:</span></span>  
  
- <span data-ttu-id="afe7e-118">ICorDebugAppDomainEnum (</span><span class="sxs-lookup"><span data-stu-id="afe7e-118">"ICorDebugAppDomainEnum"</span></span>  
  
- <span data-ttu-id="afe7e-119">ICorDebugAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="afe7e-119">"ICorDebugAssemblyEnum"</span></span>  
  
- [<span data-ttu-id="afe7e-120">ICorDebugBlockingObjectEnum</span><span class="sxs-lookup"><span data-stu-id="afe7e-120">ICorDebugBlockingObjectEnum</span></span>](icordebugblockingobjectenum-interface.md)  
  
- <span data-ttu-id="afe7e-121">ICorDebugBreakpointEnum (</span><span class="sxs-lookup"><span data-stu-id="afe7e-121">"ICorDebugBreakpointEnum"</span></span>  
  
- <span data-ttu-id="afe7e-122">ICorDebugChainEnum (</span><span class="sxs-lookup"><span data-stu-id="afe7e-122">"ICorDebugChainEnum"</span></span>  
  
- <span data-ttu-id="afe7e-123">ICorDebugCodeEnum (</span><span class="sxs-lookup"><span data-stu-id="afe7e-123">"ICorDebugCodeEnum"</span></span>  
  
- <span data-ttu-id="afe7e-124">Icordebugerrorinfoenum (</span><span class="sxs-lookup"><span data-stu-id="afe7e-124">"ICorDebugErrorInfoEnum"</span></span>  
  
- [<span data-ttu-id="afe7e-125">Icordebugexceptionobjectcallstackenum (</span><span class="sxs-lookup"><span data-stu-id="afe7e-125">ICorDebugExceptionObjectCallStackEnum</span></span>](icordebugexceptionobjectcallstackenum-interface.md)  
  
- <span data-ttu-id="afe7e-126">ICorDebugFrameEnum (</span><span class="sxs-lookup"><span data-stu-id="afe7e-126">"ICorDebugFrameEnum"</span></span>  
  
- [<span data-ttu-id="afe7e-127">Icordebuggcreferenceenum (</span><span class="sxs-lookup"><span data-stu-id="afe7e-127">ICorDebugGCReferenceEnum</span></span>](icordebuggcreferenceenum-interface.md)  
  
- [<span data-ttu-id="afe7e-128">Icordebugguidtotypeenum (</span><span class="sxs-lookup"><span data-stu-id="afe7e-128">ICorDebugGuidToTypeEnum</span></span>](icordebugguidtotypeenum-interface.md)  
  
- [<span data-ttu-id="afe7e-129">Icordebugheapenum (</span><span class="sxs-lookup"><span data-stu-id="afe7e-129">ICorDebugHeapEnum</span></span>](icordebugheapenum-interface.md)  
  
- [<span data-ttu-id="afe7e-130">Icordebugheapsegmentenum (</span><span class="sxs-lookup"><span data-stu-id="afe7e-130">ICorDebugHeapSegmentEnum</span></span>](icordebugheapsegmentenum-interface.md)  
  
- <span data-ttu-id="afe7e-131">ICorDebugModuleEnum (</span><span class="sxs-lookup"><span data-stu-id="afe7e-131">"ICorDebugModuleEnum"</span></span>  
  
- <span data-ttu-id="afe7e-132">ICorDebugObjectEnum (</span><span class="sxs-lookup"><span data-stu-id="afe7e-132">"ICorDebugObjectEnum"</span></span>  
  
- <span data-ttu-id="afe7e-133">Icordebugprocessenum (</span><span class="sxs-lookup"><span data-stu-id="afe7e-133">"ICorDebugProcessEnum"</span></span>  
  
- <span data-ttu-id="afe7e-134">ICorDebugStepperEnum (</span><span class="sxs-lookup"><span data-stu-id="afe7e-134">"ICorDebugStepperEnum"</span></span>  
  
- <span data-ttu-id="afe7e-135">ICorDebugThreadEnum (</span><span class="sxs-lookup"><span data-stu-id="afe7e-135">"ICorDebugThreadEnum"</span></span>  
  
- <span data-ttu-id="afe7e-136">ICorDebugTypeEnum</span><span class="sxs-lookup"><span data-stu-id="afe7e-136">"ICorDebugTypeEnum"</span></span>  
  
- <span data-ttu-id="afe7e-137">ICorDebugValueEnum</span><span class="sxs-lookup"><span data-stu-id="afe7e-137">"ICorDebugValueEnum"</span></span>  
  
- [<span data-ttu-id="afe7e-138">ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="afe7e-138">ICorDebugVariableHomeEnum</span></span>](icordebugvariablehomeenum-interface.md)  
  
> [!NOTE]
> <span data-ttu-id="afe7e-139">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="afe7e-139">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="afe7e-140">Requisitos</span><span class="sxs-lookup"><span data-stu-id="afe7e-140">Requirements</span></span>  

 <span data-ttu-id="afe7e-141">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="afe7e-141">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="afe7e-142">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="afe7e-142">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="afe7e-143">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="afe7e-143">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="afe7e-144">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="afe7e-144">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afe7e-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="afe7e-145">See also</span></span>

- [<span data-ttu-id="afe7e-146">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="afe7e-146">Debugging Interfaces</span></span>](debugging-interfaces.md)
