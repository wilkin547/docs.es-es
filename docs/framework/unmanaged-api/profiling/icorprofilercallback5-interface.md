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
ms.openlocfilehash: 8e94aebc489fff1c81593e54b17c471e7228d810
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689295"
---
# <a name="icorprofilercallback5-interface"></a><span data-ttu-id="23173-102">ICorProfilerCallback5 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="23173-102">ICorProfilerCallback5 Interface</span></span>

<span data-ttu-id="23173-103">Complementa la información para ayudar a un generador de perfiles a identificar el cierre completo de los objetos activos, cuando se usa con el método [ICorProfilerCallback:: RootReferences](icorprofilercallback-rootreferences-method.md) o [ICorProfilerCallback2:: RootReferences2 (](icorprofilercallback2-rootreferences2-method.md) junto con los métodos [ICorProfilerCallback:: ObjectReferences](icorprofilercallback-objectreferences-method.md) y [conditionalweaktableelementreferences (](icorprofilercallback5-conditionalweaktableelementreferences-method.md) .</span><span class="sxs-lookup"><span data-stu-id="23173-103">Supplements information to help a profiler identify the full closure of live objects, when used with either the [ICorProfilerCallback::RootReferences](icorprofilercallback-rootreferences-method.md) or [ICorProfilerCallback2::RootReferences2](icorprofilercallback2-rootreferences2-method.md) method together with the [ICorProfilerCallback::ObjectReferences](icorprofilercallback-objectreferences-method.md) and [ConditionalWeakTableElementReferences](icorprofilercallback5-conditionalweaktableelementreferences-method.md) methods.</span></span>  
  
 <span data-ttu-id="23173-104">Un generador de perfiles de memoria administrado debe implementar `ICorProfilerCallback5` para suscribirse a las notificaciones relativas a los controladores de dependencia.</span><span class="sxs-lookup"><span data-stu-id="23173-104">`ICorProfilerCallback5` must be implemented by a managed memory profiler to subscribe to notifications related to dependent handles.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="23173-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="23173-105">Remarks</span></span>  
  
## <a name="methods"></a><span data-ttu-id="23173-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="23173-106">Methods</span></span>  
  
|<span data-ttu-id="23173-107">Método</span><span class="sxs-lookup"><span data-stu-id="23173-107">Method</span></span>|<span data-ttu-id="23173-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="23173-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="23173-109">Método ConditionalWeakTableElementReferences</span><span class="sxs-lookup"><span data-stu-id="23173-109">ConditionalWeakTableElementReferences Method</span></span>](icorprofilercallback5-conditionalweaktableelementreferences-method.md)|<span data-ttu-id="23173-110">Identifica el cierre transitivo de los objetos a los que esas raíces hacen referencia mediante referencias directas de campo de miembro y mediante dependencias `ConditionalWeakTable`.</span><span class="sxs-lookup"><span data-stu-id="23173-110">Identifies the transitive closure of objects referenced by those roots through both direct member field references and through `ConditionalWeakTable` dependencies.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="23173-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="23173-111">Requirements</span></span>  

 <span data-ttu-id="23173-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23173-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23173-113">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="23173-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="23173-114">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23173-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23173-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="23173-115">See also</span></span>

- [<span data-ttu-id="23173-116">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="23173-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="23173-117">ICorProfilerCallback2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="23173-117">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
