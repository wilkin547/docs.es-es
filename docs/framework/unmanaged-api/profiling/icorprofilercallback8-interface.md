---
title: Interfaz ICorProfilerCallback8
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 22a133d02bb69026190428905379323362943d40
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732390"
---
# <a name="icorprofilercallback8-interface"></a><span data-ttu-id="6c7d6-102">Interfaz ICorProfilerCallback8</span><span class="sxs-lookup"><span data-stu-id="6c7d6-102">ICorProfilerCallback8 Interface</span></span>

<span data-ttu-id="6c7d6-103">[Se admite en el .NET Framework 4,7 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="6c7d6-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  

 <span data-ttu-id="6c7d6-104">Subclase de [ICorProfilerCallback7](icorprofilercallback7-interface.md) que proporciona métodos de devolución de llamada utilizados por el Common Language Runtime para notificar al generador de perfiles que la compilación JIT de un método dinámico se ha iniciado y finalizado.</span><span class="sxs-lookup"><span data-stu-id="6c7d6-104">A subclass of [ICorProfilerCallback7](icorprofilercallback7-interface.md) that provides callback methods used by the common language runtime to notify the profiler that JIT compilation of a dynamic method has started and finished.</span></span>
  
## <a name="methods"></a><span data-ttu-id="6c7d6-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="6c7d6-105">Methods</span></span>  
  
|<span data-ttu-id="6c7d6-106">Método</span><span class="sxs-lookup"><span data-stu-id="6c7d6-106">Method</span></span>|<span data-ttu-id="6c7d6-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="6c7d6-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6c7d6-108">Método DynamicMethodJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="6c7d6-108">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)|<span data-ttu-id="6c7d6-109">Notifica al generador de perfiles que se ha iniciado la compilación JIT de un método dinámico.</span><span class="sxs-lookup"><span data-stu-id="6c7d6-109">Notifies the profiler that JIT compilation of a dynamic method has started.</span></span>|  
|[<span data-ttu-id="6c7d6-110">Método DynamicMethodJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="6c7d6-110">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)|<span data-ttu-id="6c7d6-111">Notifica al generador de perfiles que ha finalizado la compilación JIT de un método dinámico.</span><span class="sxs-lookup"><span data-stu-id="6c7d6-111">Notifies the profiler that JIT compilation of a dynamic method has finished.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6c7d6-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6c7d6-112">Requirements</span></span>  

 <span data-ttu-id="6c7d6-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c7d6-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c7d6-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6c7d6-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="6c7d6-115">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6c7d6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="6c7d6-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6c7d6-116">See also</span></span>

- [<span data-ttu-id="6c7d6-117">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="6c7d6-117">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="6c7d6-118">Interfaz ICorProfilerCallback9</span><span class="sxs-lookup"><span data-stu-id="6c7d6-118">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
