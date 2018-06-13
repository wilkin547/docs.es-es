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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 488af069e7798fde650abb1473df256eed2d692f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452382"
---
# <a name="icorprofilercallback9-interface"></a><span data-ttu-id="b6387-102">Interfaz ICorProfilerCallback9</span><span class="sxs-lookup"><span data-stu-id="b6387-102">ICorProfilerCallback9 Interface</span></span>
<span data-ttu-id="b6387-103">[Compatible con .NET Framework 4.7.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="b6387-103">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  

 <span data-ttu-id="b6387-104">Una subclase de [ICorProfilerCallback8](icorprofilercallback8-interface.md) que proporciona un método de devolución de llamada utilizado por common language runtime para notificar al generador de perfiles que un método dinámico ha sido recolectado y descargando posteriormente.</span><span class="sxs-lookup"><span data-stu-id="b6387-104">A subclass of [ICorProfilerCallback8](icorprofilercallback8-interface.md) that provides a callback method used by the common language runtime to notify the profiler that a dynamic method has been garbage collected and subsequently unloaded.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b6387-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="b6387-105">Methods</span></span>  
  
|<span data-ttu-id="b6387-106">Método</span><span class="sxs-lookup"><span data-stu-id="b6387-106">Method</span></span>|<span data-ttu-id="b6387-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="b6387-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b6387-108">DynamicMethodUnloaded (método)</span><span class="sxs-lookup"><span data-stu-id="b6387-108">DynamicMethodUnloaded Method</span></span>](ICorProfilerCallback9-dynamicmethodunloaded-method.md)|<span data-ttu-id="b6387-109">Notifica al generador de perfiles que un método dinámico se ha recolectado y descargando posteriormente.</span><span class="sxs-lookup"><span data-stu-id="b6387-109">Notifies the profiler that a dynamic method has been garbage collected and subsequently unloaded.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b6387-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b6387-110">Requirements</span></span>  
 <span data-ttu-id="b6387-111">**Plataformas:** vea [requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6387-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6387-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b6387-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="b6387-113">**Versiones de .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b6387-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="b6387-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="b6387-114">See Also</span></span>  
<span data-ttu-id="b6387-115">[Interfaces de generación de perfiles](profiling-interfaces.md) </span><span class="sxs-lookup"><span data-stu-id="b6387-115">[Profiling Interfaces](profiling-interfaces.md) </span></span>  
<span data-ttu-id="b6387-116">[Interfaz ICorProfilerCallback8](icorprofilercallback9-interface.md) </span><span class="sxs-lookup"><span data-stu-id="b6387-116">[ICorProfilerCallback8 Interface](icorprofilercallback9-interface.md) </span></span>  
<span data-ttu-id="b6387-117">[ICorProfilerCallback8.DynamicMethodJITCompilationStarted (método)](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md) </span><span class="sxs-lookup"><span data-stu-id="b6387-117">[ICorProfilerCallback8.DynamicMethodJITCompilationStarted method](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md) </span></span>  
[<span data-ttu-id="b6387-118">ICorProfilerCallback8.DynamicMethodJITCompilationFinished (método)</span><span class="sxs-lookup"><span data-stu-id="b6387-118">ICorProfilerCallback8.DynamicMethodJITCompilationFinished method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)   
