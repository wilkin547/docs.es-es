---
description: 'Más información acerca de: interfaz ICorProfilerCallback9'
title: Interfaz ICorProfilerCallback9
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback9
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 4bfcaf6f8985909ef9142ef4d08535a19facd7e7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781654"
---
# <a name="icorprofilercallback9-interface"></a><span data-ttu-id="7e417-103">Interfaz ICorProfilerCallback9</span><span class="sxs-lookup"><span data-stu-id="7e417-103">ICorProfilerCallback9 Interface</span></span>

<span data-ttu-id="7e417-104">[Se admite en el .NET Framework 4.7.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="7e417-104">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  

 <span data-ttu-id="7e417-105">Una subclase de [ICorProfilerCallback8](icorprofilercallback8-interface.md) que proporciona un método de devolución de llamada usado por el Common Language Runtime para notificar al generador de perfiles que se ha recolectado un método dinámico y que se ha descargado posteriormente.</span><span class="sxs-lookup"><span data-stu-id="7e417-105">A subclass of [ICorProfilerCallback8](icorprofilercallback8-interface.md) that provides a callback method used by the common language runtime to notify the profiler that a dynamic method has been garbage collected and subsequently unloaded.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7e417-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="7e417-106">Methods</span></span>  
  
|<span data-ttu-id="7e417-107">Método</span><span class="sxs-lookup"><span data-stu-id="7e417-107">Method</span></span>|<span data-ttu-id="7e417-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="7e417-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7e417-109">Método DynamicMethodUnloaded</span><span class="sxs-lookup"><span data-stu-id="7e417-109">DynamicMethodUnloaded Method</span></span>](ICorProfilerCallback9-dynamicmethodunloaded-method.md)|<span data-ttu-id="7e417-110">Notifica al generador de perfiles que un método dinámico se ha recolectado como elemento no utilizado y se ha descargado posteriormente.</span><span class="sxs-lookup"><span data-stu-id="7e417-110">Notifies the profiler that a dynamic method has been garbage collected and subsequently unloaded.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7e417-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7e417-111">Requirements</span></span>  

 <span data-ttu-id="7e417-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e417-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e417-113">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7e417-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="7e417-114">**.NET Framework versiones:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7e417-114">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="7e417-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="7e417-115">See also</span></span>

- [<span data-ttu-id="7e417-116">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="7e417-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="7e417-117">Interfaz ICorProfilerCallback8</span><span class="sxs-lookup"><span data-stu-id="7e417-117">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback9-interface.md)
- [<span data-ttu-id="7e417-118">ICorProfilerCallback8. DynamicMethodJITCompilationStarted, método</span><span class="sxs-lookup"><span data-stu-id="7e417-118">ICorProfilerCallback8.DynamicMethodJITCompilationStarted method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="7e417-119">ICorProfilerCallback8. DynamicMethodJITCompilationFinished, método</span><span class="sxs-lookup"><span data-stu-id="7e417-119">ICorProfilerCallback8.DynamicMethodJITCompilationFinished method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
