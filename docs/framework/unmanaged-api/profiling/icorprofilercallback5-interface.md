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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 114d97e02b0a6b80c46f971ed74a24dc3c397f1b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59072654"
---
# <a name="icorprofilercallback5-interface"></a><span data-ttu-id="0b5d1-102">ICorProfilerCallback5 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0b5d1-102">ICorProfilerCallback5 Interface</span></span>
<span data-ttu-id="0b5d1-103">Proporciona información para ayudar a un generador de perfiles a identificar la clausura completa de los objetos activos, cuando se usa con el [ICorProfilerCallback:: RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) o [ICorProfilerCallback2:: Rootreferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md)método junto con el [ICorProfilerCallback:: ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md) y [ConditionalWeakTableElementReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md) métodos.</span><span class="sxs-lookup"><span data-stu-id="0b5d1-103">Supplements information to help a profiler identify the full closure of live objects, when used with either the [ICorProfilerCallback::RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) or [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) method together with the [ICorProfilerCallback::ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md) and [ConditionalWeakTableElementReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md) methods.</span></span>  
  
 `ICorProfilerCallback5` <span data-ttu-id="0b5d1-104">debe implementarse mediante un generador de perfiles de memoria administrada para suscribirse a los identificadores de las notificaciones relacionadas con dependientes.</span><span class="sxs-lookup"><span data-stu-id="0b5d1-104">must be implemented by a managed memory profiler to subscribe to notifications related to dependent handles.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0b5d1-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0b5d1-105">Remarks</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0b5d1-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="0b5d1-106">Methods</span></span>  
  
|<span data-ttu-id="0b5d1-107">Método</span><span class="sxs-lookup"><span data-stu-id="0b5d1-107">Method</span></span>|<span data-ttu-id="0b5d1-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="0b5d1-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0b5d1-109">Método ConditionalWeakTableElementReferences</span><span class="sxs-lookup"><span data-stu-id="0b5d1-109">ConditionalWeakTableElementReferences Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md)|<span data-ttu-id="0b5d1-110">Identifica el cierre transitivo de los objetos a los que esas raíces hacen referencia mediante referencias directas de campo de miembro y mediante dependencias `ConditionalWeakTable`.</span><span class="sxs-lookup"><span data-stu-id="0b5d1-110">Identifies the transitive closure of objects referenced by those roots through both direct member field references and through `ConditionalWeakTable` dependencies.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0b5d1-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0b5d1-111">Requirements</span></span>  
 <span data-ttu-id="0b5d1-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b5d1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b5d1-113">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0b5d1-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 **<span data-ttu-id="0b5d1-114">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="0b5d1-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0b5d1-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="0b5d1-115">See also</span></span>

- [<span data-ttu-id="0b5d1-116">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="0b5d1-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="0b5d1-117">ICorProfilerCallback2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0b5d1-117">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
