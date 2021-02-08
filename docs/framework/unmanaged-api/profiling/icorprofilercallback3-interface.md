---
description: 'Más información acerca de: ICorProfilerCallback3 (interfaz)'
title: ICorProfilerCallback3 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback3
helpviewer_keywords:
- ICorProfilerCallback3 interface [.NET Framework profiling]
ms.assetid: be83af41-3dec-4c77-8529-9dd6b8042af6
topic_type:
- apiref
ms.openlocfilehash: 70fba8768fef5da411b566d918308989a3f6e863
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99788805"
---
# <a name="icorprofilercallback3-interface"></a><span data-ttu-id="efa5e-103">ICorProfilerCallback3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="efa5e-103">ICorProfilerCallback3 Interface</span></span>

<span data-ttu-id="efa5e-104">Proporciona métodos de devolución de llamada que el Common Language Runtime (CLR) utiliza para comunicar la información de estado de asociación y desasociación al generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="efa5e-104">Provides callback methods that the common language runtime (CLR) uses to communicate attach and detach state information to the profiler.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="efa5e-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="efa5e-105">Methods</span></span>  
  
|<span data-ttu-id="efa5e-106">Método</span><span class="sxs-lookup"><span data-stu-id="efa5e-106">Method</span></span>|<span data-ttu-id="efa5e-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="efa5e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="efa5e-108">Método InitializeForAttach</span><span class="sxs-lookup"><span data-stu-id="efa5e-108">InitializeForAttach Method</span></span>](icorprofilercallback3-initializeforattach-method.md)|<span data-ttu-id="efa5e-109">Lo llama el CLR para dar al generador de perfiles una oportunidad de inicializar su estado después de una operación de adjuntar.</span><span class="sxs-lookup"><span data-stu-id="efa5e-109">Called by the CLR to give the profiler an opportunity to initialize its state after an attach operation.</span></span>|  
|[<span data-ttu-id="efa5e-110">Método ProfilerAttachComplete</span><span class="sxs-lookup"><span data-stu-id="efa5e-110">ProfilerAttachComplete Method</span></span>](icorprofilercallback3-profilerattachcomplete-method.md)|<span data-ttu-id="efa5e-111">Lo llama el CLR para indicar que el generador de perfiles ahora puede llamar a los métodos de puesta al día.</span><span class="sxs-lookup"><span data-stu-id="efa5e-111">Called by the CLR to indicate that the profiler can now call the catch-up methods.</span></span>|  
|[<span data-ttu-id="efa5e-112">Método ProfilerDetachSucceeded</span><span class="sxs-lookup"><span data-stu-id="efa5e-112">ProfilerDetachSucceeded Method</span></span>](icorprofilercallback3-profilerdetachsucceeded-method.md)|<span data-ttu-id="efa5e-113">Notifica al generador de perfiles que Common Language Runtime (CLR) está a punto de descargar el archivo DLL del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="efa5e-113">Notifies the profiler that the common language runtime (CLR) is about to unload the profiler DLL.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="efa5e-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="efa5e-114">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="efa5e-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="efa5e-115">Requirements</span></span>  

 <span data-ttu-id="efa5e-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="efa5e-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="efa5e-117">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="efa5e-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="efa5e-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="efa5e-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="efa5e-119">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="efa5e-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efa5e-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="efa5e-120">See also</span></span>

- [<span data-ttu-id="efa5e-121">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="efa5e-121">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="efa5e-122">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="efa5e-122">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="efa5e-123">ICorProfilerCallback2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="efa5e-123">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
- [<span data-ttu-id="efa5e-124">ICorProfilerCallback4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="efa5e-124">ICorProfilerCallback4 Interface</span></span>](icorprofilercallback4-interface.md)
