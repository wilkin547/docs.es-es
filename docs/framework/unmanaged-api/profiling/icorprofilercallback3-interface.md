---
title: ICorProfilerCallback3 (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1419dfff7005b33fd1f8a545d168a410e7a88a76
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback3-interface"></a><span data-ttu-id="5e41b-102">ICorProfilerCallback3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5e41b-102">ICorProfilerCallback3 Interface</span></span>
<span data-ttu-id="5e41b-103">Proporciona métodos de devolución de llamada que common language runtime (CLR) usa para comunicarse de adjuntar y separar la información de estado para el generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="5e41b-103">Provides callback methods that the common language runtime (CLR) uses to communicate attach and detach state information to the profiler.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5e41b-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="5e41b-104">Methods</span></span>  
  
|<span data-ttu-id="5e41b-105">Método</span><span class="sxs-lookup"><span data-stu-id="5e41b-105">Method</span></span>|<span data-ttu-id="5e41b-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="5e41b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5e41b-107">InitializeForAttach (método)</span><span class="sxs-lookup"><span data-stu-id="5e41b-107">InitializeForAttach Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-initializeforattach-method.md)|<span data-ttu-id="5e41b-108">Lo llama el CLR para dar al generador de perfiles una oportunidad de inicializar su estado después de una operación de adjuntar.</span><span class="sxs-lookup"><span data-stu-id="5e41b-108">Called by the CLR to give the profiler an opportunity to initialize its state after an attach operation.</span></span>|  
|[<span data-ttu-id="5e41b-109">ProfilerAttachComplete (método)</span><span class="sxs-lookup"><span data-stu-id="5e41b-109">ProfilerAttachComplete Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-profilerattachcomplete-method.md)|<span data-ttu-id="5e41b-110">Lo llama el CLR para indicar que el generador de perfiles puede llamar ahora a los métodos de puesta al día.</span><span class="sxs-lookup"><span data-stu-id="5e41b-110">Called by the CLR to indicate that the profiler can now call the catch-up methods.</span></span>|  
|[<span data-ttu-id="5e41b-111">ProfilerDetachSucceeded (método)</span><span class="sxs-lookup"><span data-stu-id="5e41b-111">ProfilerDetachSucceeded Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-profilerdetachsucceeded-method.md)|<span data-ttu-id="5e41b-112">Notifica al generador de perfiles que Common Language Runtime (CLR) está a punto de descargar el archivo DLL del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="5e41b-112">Notifies the profiler that the common language runtime (CLR) is about to unload the profiler DLL.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5e41b-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5e41b-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e41b-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5e41b-114">Requirements</span></span>  
 <span data-ttu-id="5e41b-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e41b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e41b-116">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5e41b-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5e41b-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5e41b-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5e41b-118">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e41b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e41b-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e41b-119">See Also</span></span>  
 [<span data-ttu-id="5e41b-120">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="5e41b-120">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="5e41b-121">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5e41b-121">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="5e41b-122">ICorProfilerCallback2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5e41b-122">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)  
 [<span data-ttu-id="5e41b-123">ICorProfilerCallback4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5e41b-123">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
