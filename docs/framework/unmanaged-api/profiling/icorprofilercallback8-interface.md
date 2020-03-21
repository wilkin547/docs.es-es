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
ms.openlocfilehash: 617b27923e96d9abc62ccbf158b076c6e45b20a8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175101"
---
# <a name="icorprofilercallback8-interface"></a><span data-ttu-id="151e5-102">Interfaz ICorProfilerCallback8</span><span class="sxs-lookup"><span data-stu-id="151e5-102">ICorProfilerCallback8 Interface</span></span>
<span data-ttu-id="151e5-103">[Soportado en .NET Framework 4.7 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="151e5-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  

 <span data-ttu-id="151e5-104">Subclase de [ICorProfilerCallback7](icorprofilercallback7-interface.md) que proporciona métodos de devolución de llamada utilizados por Common Language Runtime para notificar al generador de perfiles que la compilación JIT de un método dinámico se ha iniciado y finalizado.</span><span class="sxs-lookup"><span data-stu-id="151e5-104">A subclass of [ICorProfilerCallback7](icorprofilercallback7-interface.md) that provides callback methods used by the common language runtime to notify the profiler that JIT compilation of a dynamic method has started and finished.</span></span>
  
## <a name="methods"></a><span data-ttu-id="151e5-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="151e5-105">Methods</span></span>  
  
|<span data-ttu-id="151e5-106">Método</span><span class="sxs-lookup"><span data-stu-id="151e5-106">Method</span></span>|<span data-ttu-id="151e5-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="151e5-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="151e5-108">DynamicMethodJITCompilationStarted (método)</span><span class="sxs-lookup"><span data-stu-id="151e5-108">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)|<span data-ttu-id="151e5-109">Notifica al generador de perfiles que se ha iniciado la compilación JIT de un método dinámico.</span><span class="sxs-lookup"><span data-stu-id="151e5-109">Notifies the profiler that JIT compilation of a dynamic method has started.</span></span>|  
|[<span data-ttu-id="151e5-110">DynamicMethodJITCompilationFinished (método)</span><span class="sxs-lookup"><span data-stu-id="151e5-110">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)|<span data-ttu-id="151e5-111">Notifica al generador de perfiles que la compilación JIT de un método dinámico ha finalizado.</span><span class="sxs-lookup"><span data-stu-id="151e5-111">Notifies the profiler that JIT compilation of a dynamic method has finished.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="151e5-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="151e5-112">Requirements</span></span>  
 <span data-ttu-id="151e5-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="151e5-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="151e5-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="151e5-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="151e5-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="151e5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="151e5-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="151e5-116">See also</span></span>

- [<span data-ttu-id="151e5-117">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="151e5-117">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="151e5-118">ICorProfilerCallback9 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="151e5-118">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
