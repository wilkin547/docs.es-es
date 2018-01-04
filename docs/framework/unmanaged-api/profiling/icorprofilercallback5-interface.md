---
title: ICorProfilerCallback5 (interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback5
api_location: Mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback5
helpviewer_keywords: ICorProfilerCallback5 interface [.NET Framework profiling]
ms.assetid: 61d2e9ef-5f1f-4771-8847-239616e35d84
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0406b537f6f20d7194a0115020245ade101bd498
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback5-interface"></a><span data-ttu-id="730c9-102">ICorProfilerCallback5 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="730c9-102">ICorProfilerCallback5 Interface</span></span>
<span data-ttu-id="730c9-103">Proporciona información para ayudar a un generador de perfiles a identificar el cierre completo de objetos activos, cuando se usa con la [ICorProfilerCallback:: RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) o [ICorProfilerCallback2:: Rootreferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md)método junto con el [ICorProfilerCallback:: ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md) y [ConditionalWeakTableElementReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md) métodos.</span><span class="sxs-lookup"><span data-stu-id="730c9-103">Supplements information to help a profiler identify the full closure of live objects, when used with either the [ICorProfilerCallback::RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) or [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) method together with the [ICorProfilerCallback::ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md) and [ConditionalWeakTableElementReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md) methods.</span></span>  
  
 <span data-ttu-id="730c9-104">Un generador de perfiles de memoria administrado debe implementar `ICorProfilerCallback5` para suscribirse a las notificaciones relativas a los controladores de dependencia.</span><span class="sxs-lookup"><span data-stu-id="730c9-104">`ICorProfilerCallback5` must be implemented by a managed memory profiler to subscribe to notifications related to dependent handles.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="730c9-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="730c9-105">Remarks</span></span>  
  
## <a name="methods"></a><span data-ttu-id="730c9-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="730c9-106">Methods</span></span>  
  
|<span data-ttu-id="730c9-107">Método</span><span class="sxs-lookup"><span data-stu-id="730c9-107">Method</span></span>|<span data-ttu-id="730c9-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="730c9-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="730c9-109">ConditionalWeakTableElementReferences (método)</span><span class="sxs-lookup"><span data-stu-id="730c9-109">ConditionalWeakTableElementReferences Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md)|<span data-ttu-id="730c9-110">Identifica el cierre transitivo de los objetos a los que esas raíces hacen referencia mediante referencias directas de campo de miembro y mediante dependencias `ConditionalWeakTable`.</span><span class="sxs-lookup"><span data-stu-id="730c9-110">Identifies the transitive closure of objects referenced by those roots through both direct member field references and through `ConditionalWeakTable` dependencies.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="730c9-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="730c9-111">Requirements</span></span>  
 <span data-ttu-id="730c9-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="730c9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="730c9-113">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="730c9-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="730c9-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="730c9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="730c9-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="730c9-115">See Also</span></span>  
 [<span data-ttu-id="730c9-116">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="730c9-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="730c9-117">ICorProfilerCallback2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="730c9-117">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
