---
title: ICorProfilerCallback5 (interfaz)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback5
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback5
helpviewer_keywords:
- ICorProfilerCallback5 interface [.NET Framework profiling]
ms.assetid: 61d2e9ef-5f1f-4771-8847-239616e35d84
topic_type:
- apiref
ms.openlocfilehash: 7981e7d2d2a4588e56d3c30d0ede2d003fdcd32e
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865030"
---
# <a name="icorprofilercallback5-interface"></a><span data-ttu-id="3094d-102">ICorProfilerCallback5 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3094d-102">ICorProfilerCallback5 Interface</span></span>
<span data-ttu-id="3094d-103">Complementa la información para ayudar a un generador de perfiles a identificar el cierre completo de los objetos activos, cuando se usa con el método [ICorProfilerCallback:: RootReferences](icorprofilercallback-rootreferences-method.md) o [ICorProfilerCallback2:: RootReferences2 (](icorprofilercallback2-rootreferences2-method.md) junto con los métodos [ICorProfilerCallback:: ObjectReferences](icorprofilercallback-objectreferences-method.md) y [conditionalweaktableelementreferences (](icorprofilercallback5-conditionalweaktableelementreferences-method.md) .</span><span class="sxs-lookup"><span data-stu-id="3094d-103">Supplements information to help a profiler identify the full closure of live objects, when used with either the [ICorProfilerCallback::RootReferences](icorprofilercallback-rootreferences-method.md) or [ICorProfilerCallback2::RootReferences2](icorprofilercallback2-rootreferences2-method.md) method together with the [ICorProfilerCallback::ObjectReferences](icorprofilercallback-objectreferences-method.md) and [ConditionalWeakTableElementReferences](icorprofilercallback5-conditionalweaktableelementreferences-method.md) methods.</span></span>  
  
 <span data-ttu-id="3094d-104">Un generador de perfiles de memoria administrado debe implementar `ICorProfilerCallback5` para suscribirse a las notificaciones relativas a los controladores de dependencia.</span><span class="sxs-lookup"><span data-stu-id="3094d-104">`ICorProfilerCallback5` must be implemented by a managed memory profiler to subscribe to notifications related to dependent handles.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3094d-105">Notas</span><span class="sxs-lookup"><span data-stu-id="3094d-105">Remarks</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3094d-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="3094d-106">Methods</span></span>  
  
|<span data-ttu-id="3094d-107">Método</span><span class="sxs-lookup"><span data-stu-id="3094d-107">Method</span></span>|<span data-ttu-id="3094d-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="3094d-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3094d-109">ConditionalWeakTableElementReferences (método)</span><span class="sxs-lookup"><span data-stu-id="3094d-109">ConditionalWeakTableElementReferences Method</span></span>](icorprofilercallback5-conditionalweaktableelementreferences-method.md)|<span data-ttu-id="3094d-110">Identifica el cierre transitivo de los objetos a los que esas raíces hacen referencia mediante referencias directas de campo de miembro y mediante dependencias `ConditionalWeakTable`.</span><span class="sxs-lookup"><span data-stu-id="3094d-110">Identifies the transitive closure of objects referenced by those roots through both direct member field references and through `ConditionalWeakTable` dependencies.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3094d-111">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="3094d-111">Requirements</span></span>  
 <span data-ttu-id="3094d-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3094d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3094d-113">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3094d-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3094d-114">**.NET Framework versiones:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3094d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3094d-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="3094d-115">See also</span></span>

- [<span data-ttu-id="3094d-116">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="3094d-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="3094d-117">ICorProfilerCallback2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3094d-117">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
