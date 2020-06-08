---
title: ICorProfilerCallback3::ProfilerAttachComplete (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback3.ProfilerAttachComplete Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback3::ProfilerAttachComplete
helpviewer_keywords:
- ProfilerAttachComplete method [.NET Framework profiling]
- ICorProfilerCallback3::ProfilerAttachComplete method [.NET Framework profiling]
ms.assetid: 257d6076-06e0-4d93-bb33-651fbb2b92d7
topic_type:
- apiref
ms.openlocfilehash: bcc938ff9322fca4f45366fdc695e0c3901484b5
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499667"
---
# <a name="icorprofilercallback3profilerattachcomplete-method"></a><span data-ttu-id="916e2-102">ICorProfilerCallback3::ProfilerAttachComplete (Método)</span><span class="sxs-lookup"><span data-stu-id="916e2-102">ICorProfilerCallback3::ProfilerAttachComplete Method</span></span>
<span data-ttu-id="916e2-103">Lo llama el Common Language Runtime (CLR) para indicar que el generador de perfiles ahora puede llamar a los métodos de puesta al día de [ICorProfilerInfo3:: EnumJITedFunctions (](icorprofilerinfo3-enumjitedfunctions-method.md) y [Icorprofilerinfo3:: EnumModules (](icorprofilerinfo3-enummodules-method.md) .</span><span class="sxs-lookup"><span data-stu-id="916e2-103">Called by the common language runtime (CLR) to indicate that the profiler can now call the [ICorProfilerInfo3::EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md) and [ICorProfilerInfo3::EnumModules](icorprofilerinfo3-enummodules-method.md) catch-up methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="916e2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="916e2-104">Syntax</span></span>  
  
```cpp  
HRESULT ProfilerAttachComplete ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="916e2-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="916e2-105">Remarks</span></span>  
 <span data-ttu-id="916e2-106">La `ProfilerAttachComplete` devolución de llamada se emite después de llamar al método [ICorProfilerCallback3:: InitializeForAttach](icorprofilercallback3-initializeforattach-method.md) .</span><span class="sxs-lookup"><span data-stu-id="916e2-106">The `ProfilerAttachComplete` callback is issued after the [ICorProfilerCallback3::InitializeForAttach](icorprofilercallback3-initializeforattach-method.md) method is called.</span></span> <span data-ttu-id="916e2-107">Indica que:</span><span class="sxs-lookup"><span data-stu-id="916e2-107">It indicates the following:</span></span>  
  
- <span data-ttu-id="916e2-108">Las devoluciones de llamada que solicitó el generador de perfiles en `InitializeForAttach` se han activado.</span><span class="sxs-lookup"><span data-stu-id="916e2-108">The callbacks that were requested by the profiler in `InitializeForAttach` have been activated.</span></span>  
  
- <span data-ttu-id="916e2-109">El generador de perfiles ya puede poner al día los identificadores asociados sin preocuparse sobre las notificaciones que faltan.</span><span class="sxs-lookup"><span data-stu-id="916e2-109">The profiler can now perform catch-up on the associated IDs without being concerned about missing notifications.</span></span>  
  
 <span data-ttu-id="916e2-110">CLR pasa por alto el valor devuelto por esta devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="916e2-110">The CLR ignores the return value from this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="916e2-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="916e2-111">Requirements</span></span>  
 <span data-ttu-id="916e2-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="916e2-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="916e2-113">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="916e2-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="916e2-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="916e2-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="916e2-115">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="916e2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="916e2-116">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="916e2-116">See also</span></span>

- [<span data-ttu-id="916e2-117">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="916e2-117">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="916e2-118">ICorProfilerInfo3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="916e2-118">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="916e2-119">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="916e2-119">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="916e2-120">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="916e2-120">Profiling</span></span>](index.md)
