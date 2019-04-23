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
ms.openlocfilehash: e1711def5e2aa41fd63912361ef8250ad160fb88
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59227761"
---
# <a name="icorprofilercallback9-interface"></a><span data-ttu-id="d9480-102">Interfaz ICorProfilerCallback9</span><span class="sxs-lookup"><span data-stu-id="d9480-102">ICorProfilerCallback9 Interface</span></span>
<span data-ttu-id="d9480-103">[Compatible con .NET Framework 4.7.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="d9480-103">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  

 <span data-ttu-id="d9480-104">Una subclase de [ICorProfilerCallback8](icorprofilercallback8-interface.md) que proporciona un método de devolución de llamada que common language runtime utilizado para notificar al generador de perfiles que un método dinámico ha sido recolectado y posteriormente descargan.</span><span class="sxs-lookup"><span data-stu-id="d9480-104">A subclass of [ICorProfilerCallback8](icorprofilercallback8-interface.md) that provides a callback method used by the common language runtime to notify the profiler that a dynamic method has been garbage collected and subsequently unloaded.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d9480-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="d9480-105">Methods</span></span>  
  
|<span data-ttu-id="d9480-106">Método</span><span class="sxs-lookup"><span data-stu-id="d9480-106">Method</span></span>|<span data-ttu-id="d9480-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="d9480-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d9480-108">DynamicMethodUnloaded (método)</span><span class="sxs-lookup"><span data-stu-id="d9480-108">DynamicMethodUnloaded Method</span></span>](ICorProfilerCallback9-dynamicmethodunloaded-method.md)|<span data-ttu-id="d9480-109">Notifica al generador de perfiles que un método dinámico se ha recolectado y posteriormente descargan.</span><span class="sxs-lookup"><span data-stu-id="d9480-109">Notifies the profiler that a dynamic method has been garbage collected and subsequently unloaded.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d9480-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d9480-110">Requirements</span></span>  
 <span data-ttu-id="d9480-111">**Plataformas:** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9480-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9480-112">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d9480-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="d9480-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d9480-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="d9480-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="d9480-114">See also</span></span>

- [<span data-ttu-id="d9480-115">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="d9480-115">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="d9480-116">ICorProfilerCallback8 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d9480-116">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback9-interface.md)
- [<span data-ttu-id="d9480-117">Método ICorProfilerCallback8.DynamicMethodJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="d9480-117">ICorProfilerCallback8.DynamicMethodJITCompilationStarted method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="d9480-118">Método ICorProfilerCallback8.DynamicMethodJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="d9480-118">ICorProfilerCallback8.DynamicMethodJITCompilationFinished method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
