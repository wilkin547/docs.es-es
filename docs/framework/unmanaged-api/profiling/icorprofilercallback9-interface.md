---
title: ICorProfilerCallback9 Interface
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
ms.openlocfilehash: a6c480af921fb0259ef85beec8d8f65bdd430522
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54689324"
---
# <a name="icorprofilercallback9-interface"></a><span data-ttu-id="b0d46-102">ICorProfilerCallback9 Interface</span><span class="sxs-lookup"><span data-stu-id="b0d46-102">ICorProfilerCallback9 Interface</span></span>
<span data-ttu-id="b0d46-103">[Compatible con .NET Framework 4.7.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="b0d46-103">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  

 <span data-ttu-id="b0d46-104">Una subclase de [ICorProfilerCallback8](icorprofilercallback8-interface.md) que proporciona un método de devolución de llamada que common language runtime utilizado para notificar al generador de perfiles que un método dinámico ha sido recolectado y posteriormente descargan.</span><span class="sxs-lookup"><span data-stu-id="b0d46-104">A subclass of [ICorProfilerCallback8](icorprofilercallback8-interface.md) that provides a callback method used by the common language runtime to notify the profiler that a dynamic method has been garbage collected and subsequently unloaded.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b0d46-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="b0d46-105">Methods</span></span>  
  
|<span data-ttu-id="b0d46-106">Método</span><span class="sxs-lookup"><span data-stu-id="b0d46-106">Method</span></span>|<span data-ttu-id="b0d46-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="b0d46-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b0d46-108">DynamicMethodUnloaded (método)</span><span class="sxs-lookup"><span data-stu-id="b0d46-108">DynamicMethodUnloaded Method</span></span>](ICorProfilerCallback9-dynamicmethodunloaded-method.md)|<span data-ttu-id="b0d46-109">Notifica al generador de perfiles que un método dinámico se ha recolectado y posteriormente descargan.</span><span class="sxs-lookup"><span data-stu-id="b0d46-109">Notifies the profiler that a dynamic method has been garbage collected and subsequently unloaded.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b0d46-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b0d46-110">Requirements</span></span>  
 <span data-ttu-id="b0d46-111">**Plataformas:** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0d46-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0d46-112">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b0d46-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="b0d46-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b0d46-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="b0d46-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="b0d46-114">See also</span></span>
- [<span data-ttu-id="b0d46-115">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="b0d46-115">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="b0d46-116">ICorProfilerCallback8 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b0d46-116">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback9-interface.md)
- [<span data-ttu-id="b0d46-117">Método ICorProfilerCallback8.DynamicMethodJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="b0d46-117">ICorProfilerCallback8.DynamicMethodJITCompilationStarted method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="b0d46-118">Método ICorProfilerCallback8.DynamicMethodJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="b0d46-118">ICorProfilerCallback8.DynamicMethodJITCompilationFinished method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
