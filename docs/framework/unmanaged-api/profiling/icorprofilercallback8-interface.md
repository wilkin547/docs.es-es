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
ms.openlocfilehash: e536e61a8d812e442e1e54188c99d6a1d4586757
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59125572"
---
# <a name="icorprofilercallback8-interface"></a><span data-ttu-id="68c42-102">Interfaz ICorProfilerCallback8</span><span class="sxs-lookup"><span data-stu-id="68c42-102">ICorProfilerCallback8 Interface</span></span>
<span data-ttu-id="68c42-103">[Se admite en .NET Framework 4.7 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="68c42-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  

 <span data-ttu-id="68c42-104">Una subclase de [ICorProfilerCallback7](icorprofilercallback7-interface.md) que proporciona métodos de devolución de llamada que common language runtime utilizados para notificar al generador de perfiles que se ha iniciado y finalizado la compilación JIT de un método dinámico.</span><span class="sxs-lookup"><span data-stu-id="68c42-104">A subclass of [ICorProfilerCallback7](icorprofilercallback7-interface.md) that provides callback methods used by the common language runtime to notify the profiler that JIT compilation of a dynamic method has started and finished.</span></span> 
  
## <a name="methods"></a><span data-ttu-id="68c42-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="68c42-105">Methods</span></span>  
  
|<span data-ttu-id="68c42-106">Método</span><span class="sxs-lookup"><span data-stu-id="68c42-106">Method</span></span>|<span data-ttu-id="68c42-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="68c42-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="68c42-108">Método DynamicMethodJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="68c42-108">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)|<span data-ttu-id="68c42-109">Notifica al generador de perfiles que se ha iniciado la compilación JIT de un método dinámico.</span><span class="sxs-lookup"><span data-stu-id="68c42-109">Notifies the profiler that JIT compilation of a dynamic method has started.</span></span>|  
|[<span data-ttu-id="68c42-110">Método DynamicMethodJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="68c42-110">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)|<span data-ttu-id="68c42-111">Notifica al generador de perfiles que ha finalizado la compilación JIT de un método dinámico.</span><span class="sxs-lookup"><span data-stu-id="68c42-111">Notifies the profiler that JIT compilation of a dynamic method has finished.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="68c42-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="68c42-112">Requirements</span></span>  
 <span data-ttu-id="68c42-113">**Plataformas:** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="68c42-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68c42-114">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="68c42-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
**<span data-ttu-id="68c42-115">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="68c42-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a><span data-ttu-id="68c42-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="68c42-116">See also</span></span>

- [<span data-ttu-id="68c42-117">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="68c42-117">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="68c42-118">Interfaz ICorProfilerCallback9</span><span class="sxs-lookup"><span data-stu-id="68c42-118">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
