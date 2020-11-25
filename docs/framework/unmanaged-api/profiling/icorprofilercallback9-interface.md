---
title: Interfaz ICorProfilerCallback9
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback9
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 23b91a2a58c6e76b31b94e0fa3661dfbc8e18e33
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712773"
---
# <a name="icorprofilercallback9-interface"></a><span data-ttu-id="b8e32-102">Interfaz ICorProfilerCallback9</span><span class="sxs-lookup"><span data-stu-id="b8e32-102">ICorProfilerCallback9 Interface</span></span>

<span data-ttu-id="b8e32-103">[Se admite en el .NET Framework 4.7.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="b8e32-103">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  

 <span data-ttu-id="b8e32-104">Una subclase de [ICorProfilerCallback8](icorprofilercallback8-interface.md) que proporciona un método de devolución de llamada usado por el Common Language Runtime para notificar al generador de perfiles que se ha recolectado un método dinámico y que se ha descargado posteriormente.</span><span class="sxs-lookup"><span data-stu-id="b8e32-104">A subclass of [ICorProfilerCallback8](icorprofilercallback8-interface.md) that provides a callback method used by the common language runtime to notify the profiler that a dynamic method has been garbage collected and subsequently unloaded.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b8e32-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="b8e32-105">Methods</span></span>  
  
|<span data-ttu-id="b8e32-106">Método</span><span class="sxs-lookup"><span data-stu-id="b8e32-106">Method</span></span>|<span data-ttu-id="b8e32-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="b8e32-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b8e32-108">Método DynamicMethodUnloaded</span><span class="sxs-lookup"><span data-stu-id="b8e32-108">DynamicMethodUnloaded Method</span></span>](ICorProfilerCallback9-dynamicmethodunloaded-method.md)|<span data-ttu-id="b8e32-109">Notifica al generador de perfiles que un método dinámico se ha recolectado como elemento no utilizado y se ha descargado posteriormente.</span><span class="sxs-lookup"><span data-stu-id="b8e32-109">Notifies the profiler that a dynamic method has been garbage collected and subsequently unloaded.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b8e32-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b8e32-110">Requirements</span></span>  

 <span data-ttu-id="b8e32-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8e32-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8e32-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b8e32-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="b8e32-113">**.NET Framework versiones:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b8e32-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="b8e32-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b8e32-114">See also</span></span>

- [<span data-ttu-id="b8e32-115">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="b8e32-115">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="b8e32-116">Interfaz ICorProfilerCallback8</span><span class="sxs-lookup"><span data-stu-id="b8e32-116">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback9-interface.md)
- [<span data-ttu-id="b8e32-117">ICorProfilerCallback8. DynamicMethodJITCompilationStarted, método</span><span class="sxs-lookup"><span data-stu-id="b8e32-117">ICorProfilerCallback8.DynamicMethodJITCompilationStarted method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="b8e32-118">ICorProfilerCallback8. DynamicMethodJITCompilationFinished, método</span><span class="sxs-lookup"><span data-stu-id="b8e32-118">ICorProfilerCallback8.DynamicMethodJITCompilationFinished method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
