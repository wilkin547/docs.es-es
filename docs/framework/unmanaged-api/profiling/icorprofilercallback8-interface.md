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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b92120cc5948efca696d922448da215601f9e6b3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455288"
---
# <a name="icorprofilercallback8-interface"></a><span data-ttu-id="22093-102">Interfaz ICorProfilerCallback8</span><span class="sxs-lookup"><span data-stu-id="22093-102">ICorProfilerCallback8 Interface</span></span>
<span data-ttu-id="22093-103">[Compatible con .NET Framework 4.7 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="22093-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  

 <span data-ttu-id="22093-104">Una subclase de [ICorProfilerCallback7](icorprofilercallback7-interface.md) que proporciona métodos de devolución de llamada que common language runtime utilizados para notificar al generador de perfiles que se ha iniciado y finalizado la compilación JIT de un método dinámico.</span><span class="sxs-lookup"><span data-stu-id="22093-104">A subclass of [ICorProfilerCallback7](icorprofilercallback7-interface.md) that provides callback methods used by the common language runtime to notify the profiler that JIT compilation of a dynamic method has started and finished.</span></span> 
  
## <a name="methods"></a><span data-ttu-id="22093-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="22093-105">Methods</span></span>  
  
|<span data-ttu-id="22093-106">Método</span><span class="sxs-lookup"><span data-stu-id="22093-106">Method</span></span>|<span data-ttu-id="22093-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="22093-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="22093-108">DynamicMethodJITCompilationStarted (método)</span><span class="sxs-lookup"><span data-stu-id="22093-108">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)|<span data-ttu-id="22093-109">Notifica al generador de perfiles que se ha iniciado la compilación JIT de un método dinámico.</span><span class="sxs-lookup"><span data-stu-id="22093-109">Notifies the profiler that JIT compilation of a dynamic method has started.</span></span>|  
|[<span data-ttu-id="22093-110">DynamicMethodJITCompilationFinished (método)</span><span class="sxs-lookup"><span data-stu-id="22093-110">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)|<span data-ttu-id="22093-111">Notifica al generador de perfiles que ha finalizado la compilación JIT de un método dinámico.</span><span class="sxs-lookup"><span data-stu-id="22093-111">Notifies the profiler that JIT compilation of a dynamic method has finished.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="22093-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="22093-112">Requirements</span></span>  
 <span data-ttu-id="22093-113">**Plataformas:** vea [requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22093-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22093-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="22093-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="22093-115">**Versiones de .NET framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="22093-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="22093-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="22093-116">See Also</span></span>  
<span data-ttu-id="22093-117">[Interfaces de generación de perfiles](profiling-interfaces.md) </span><span class="sxs-lookup"><span data-stu-id="22093-117">[Profiling Interfaces](profiling-interfaces.md) </span></span>  
[<span data-ttu-id="22093-118">Interfaz ICorProfilerCallback9</span><span class="sxs-lookup"><span data-stu-id="22093-118">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
