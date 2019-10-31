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
ms.openlocfilehash: c383a2e221e61770d3c28a65c561c48f6059b6d6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136565"
---
# <a name="icorprofilercallback9-interface"></a><span data-ttu-id="c5e86-102">Interfaz ICorProfilerCallback9</span><span class="sxs-lookup"><span data-stu-id="c5e86-102">ICorProfilerCallback9 Interface</span></span>
<span data-ttu-id="c5e86-103">[Se admite en el .NET Framework 4.7.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="c5e86-103">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  

 <span data-ttu-id="c5e86-104">Una subclase de [ICorProfilerCallback8](icorprofilercallback8-interface.md) que proporciona un método de devolución de llamada usado por el Common Language Runtime para notificar al generador de perfiles que se ha recolectado un método dinámico y que se ha descargado posteriormente.</span><span class="sxs-lookup"><span data-stu-id="c5e86-104">A subclass of [ICorProfilerCallback8](icorprofilercallback8-interface.md) that provides a callback method used by the common language runtime to notify the profiler that a dynamic method has been garbage collected and subsequently unloaded.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c5e86-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="c5e86-105">Methods</span></span>  
  
|<span data-ttu-id="c5e86-106">Método</span><span class="sxs-lookup"><span data-stu-id="c5e86-106">Method</span></span>|<span data-ttu-id="c5e86-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="c5e86-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c5e86-108">DynamicMethodUnloaded (método)</span><span class="sxs-lookup"><span data-stu-id="c5e86-108">DynamicMethodUnloaded Method</span></span>](ICorProfilerCallback9-dynamicmethodunloaded-method.md)|<span data-ttu-id="c5e86-109">Notifica al generador de perfiles que un método dinámico se ha recolectado como elemento no utilizado y se ha descargado posteriormente.</span><span class="sxs-lookup"><span data-stu-id="c5e86-109">Notifies the profiler that a dynamic method has been garbage collected and subsequently unloaded.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c5e86-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c5e86-110">Requirements</span></span>  
 <span data-ttu-id="c5e86-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c5e86-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5e86-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c5e86-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="c5e86-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c5e86-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="c5e86-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="c5e86-114">See also</span></span>

- [<span data-ttu-id="c5e86-115">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="c5e86-115">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="c5e86-116">ICorProfilerCallback8 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c5e86-116">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback9-interface.md)
- [<span data-ttu-id="c5e86-117">ICorProfilerCallback8. DynamicMethodJITCompilationStarted, método</span><span class="sxs-lookup"><span data-stu-id="c5e86-117">ICorProfilerCallback8.DynamicMethodJITCompilationStarted method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="c5e86-118">ICorProfilerCallback8. DynamicMethodJITCompilationFinished, método</span><span class="sxs-lookup"><span data-stu-id="c5e86-118">ICorProfilerCallback8.DynamicMethodJITCompilationFinished method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
