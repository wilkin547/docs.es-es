---
description: 'Más información acerca de: interfaz ICorProfilerCallback8'
title: Interfaz ICorProfilerCallback8
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 8dd9b8eea82f38b7598d578bd718743af826070d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781680"
---
# <a name="icorprofilercallback8-interface"></a><span data-ttu-id="98e65-103">Interfaz ICorProfilerCallback8</span><span class="sxs-lookup"><span data-stu-id="98e65-103">ICorProfilerCallback8 Interface</span></span>

<span data-ttu-id="98e65-104">[Se admite en el .NET Framework 4,7 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="98e65-104">[Supported in the .NET Framework 4.7 and later versions]</span></span>  

 <span data-ttu-id="98e65-105">Subclase de [ICorProfilerCallback7](icorprofilercallback7-interface.md) que proporciona métodos de devolución de llamada utilizados por el Common Language Runtime para notificar al generador de perfiles que la compilación JIT de un método dinámico se ha iniciado y finalizado.</span><span class="sxs-lookup"><span data-stu-id="98e65-105">A subclass of [ICorProfilerCallback7](icorprofilercallback7-interface.md) that provides callback methods used by the common language runtime to notify the profiler that JIT compilation of a dynamic method has started and finished.</span></span>
  
## <a name="methods"></a><span data-ttu-id="98e65-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="98e65-106">Methods</span></span>  
  
|<span data-ttu-id="98e65-107">Método</span><span class="sxs-lookup"><span data-stu-id="98e65-107">Method</span></span>|<span data-ttu-id="98e65-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="98e65-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="98e65-109">Método DynamicMethodJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="98e65-109">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)|<span data-ttu-id="98e65-110">Notifica al generador de perfiles que se ha iniciado la compilación JIT de un método dinámico.</span><span class="sxs-lookup"><span data-stu-id="98e65-110">Notifies the profiler that JIT compilation of a dynamic method has started.</span></span>|  
|[<span data-ttu-id="98e65-111">Método DynamicMethodJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="98e65-111">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)|<span data-ttu-id="98e65-112">Notifica al generador de perfiles que ha finalizado la compilación JIT de un método dinámico.</span><span class="sxs-lookup"><span data-stu-id="98e65-112">Notifies the profiler that JIT compilation of a dynamic method has finished.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="98e65-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="98e65-113">Requirements</span></span>  

 <span data-ttu-id="98e65-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98e65-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98e65-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="98e65-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="98e65-116">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="98e65-116">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="98e65-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="98e65-117">See also</span></span>

- [<span data-ttu-id="98e65-118">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="98e65-118">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="98e65-119">Interfaz ICorProfilerCallback9</span><span class="sxs-lookup"><span data-stu-id="98e65-119">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
