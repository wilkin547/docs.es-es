---
title: ICorProfilerCallback8 (interfaz)
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
ms.openlocfilehash: a3bdf79582619777a22c80caac5b4e90d603f3a8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54675020"
---
# <a name="icorprofilercallback8-interface"></a><span data-ttu-id="da6f7-102">ICorProfilerCallback8 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="da6f7-102">ICorProfilerCallback8 Interface</span></span>
<span data-ttu-id="da6f7-103">[Se admite en .NET Framework 4.7 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="da6f7-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  

 <span data-ttu-id="da6f7-104">Una subclase de [ICorProfilerCallback7](icorprofilercallback7-interface.md) que proporciona métodos de devolución de llamada que common language runtime utilizados para notificar al generador de perfiles que se ha iniciado y finalizado la compilación JIT de un método dinámico.</span><span class="sxs-lookup"><span data-stu-id="da6f7-104">A subclass of [ICorProfilerCallback7](icorprofilercallback7-interface.md) that provides callback methods used by the common language runtime to notify the profiler that JIT compilation of a dynamic method has started and finished.</span></span> 
  
## <a name="methods"></a><span data-ttu-id="da6f7-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="da6f7-105">Methods</span></span>  
  
|<span data-ttu-id="da6f7-106">Método</span><span class="sxs-lookup"><span data-stu-id="da6f7-106">Method</span></span>|<span data-ttu-id="da6f7-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="da6f7-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="da6f7-108">DynamicMethodJITCompilationStarted (método)</span><span class="sxs-lookup"><span data-stu-id="da6f7-108">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)|<span data-ttu-id="da6f7-109">Notifica al generador de perfiles que se ha iniciado la compilación JIT de un método dinámico.</span><span class="sxs-lookup"><span data-stu-id="da6f7-109">Notifies the profiler that JIT compilation of a dynamic method has started.</span></span>|  
|[<span data-ttu-id="da6f7-110">DynamicMethodJITCompilationFinished (método)</span><span class="sxs-lookup"><span data-stu-id="da6f7-110">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)|<span data-ttu-id="da6f7-111">Notifica al generador de perfiles que ha finalizado la compilación JIT de un método dinámico.</span><span class="sxs-lookup"><span data-stu-id="da6f7-111">Notifies the profiler that JIT compilation of a dynamic method has finished.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="da6f7-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="da6f7-112">Requirements</span></span>  
 <span data-ttu-id="da6f7-113">**Plataformas:** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da6f7-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da6f7-114">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="da6f7-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="da6f7-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="da6f7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="da6f7-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="da6f7-116">See also</span></span>
- [<span data-ttu-id="da6f7-117">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="da6f7-117">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="da6f7-118">ICorProfilerCallback9 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="da6f7-118">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
