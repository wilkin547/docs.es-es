---
description: 'Más información acerca de: interfaz ICorProfilerCallback5'
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
ms.openlocfilehash: b80b27dc994ad556381228370ece92935d89d293
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99788662"
---
# <a name="icorprofilercallback5-interface"></a><span data-ttu-id="80f72-103">ICorProfilerCallback5 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="80f72-103">ICorProfilerCallback5 Interface</span></span>

<span data-ttu-id="80f72-104">Complementa la información para ayudar a un generador de perfiles a identificar el cierre completo de los objetos activos, cuando se usa con el método [ICorProfilerCallback:: RootReferences](icorprofilercallback-rootreferences-method.md) o [ICorProfilerCallback2:: RootReferences2 (](icorprofilercallback2-rootreferences2-method.md) junto con los métodos [ICorProfilerCallback:: ObjectReferences](icorprofilercallback-objectreferences-method.md) y [conditionalweaktableelementreferences (](icorprofilercallback5-conditionalweaktableelementreferences-method.md) .</span><span class="sxs-lookup"><span data-stu-id="80f72-104">Supplements information to help a profiler identify the full closure of live objects, when used with either the [ICorProfilerCallback::RootReferences](icorprofilercallback-rootreferences-method.md) or [ICorProfilerCallback2::RootReferences2](icorprofilercallback2-rootreferences2-method.md) method together with the [ICorProfilerCallback::ObjectReferences](icorprofilercallback-objectreferences-method.md) and [ConditionalWeakTableElementReferences](icorprofilercallback5-conditionalweaktableelementreferences-method.md) methods.</span></span>  
  
 <span data-ttu-id="80f72-105">Un generador de perfiles de memoria administrado debe implementar `ICorProfilerCallback5` para suscribirse a las notificaciones relativas a los controladores de dependencia.</span><span class="sxs-lookup"><span data-stu-id="80f72-105">`ICorProfilerCallback5` must be implemented by a managed memory profiler to subscribe to notifications related to dependent handles.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="80f72-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="80f72-106">Remarks</span></span>  
  
## <a name="methods"></a><span data-ttu-id="80f72-107">Métodos</span><span class="sxs-lookup"><span data-stu-id="80f72-107">Methods</span></span>  
  
|<span data-ttu-id="80f72-108">Método</span><span class="sxs-lookup"><span data-stu-id="80f72-108">Method</span></span>|<span data-ttu-id="80f72-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="80f72-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="80f72-110">Método ConditionalWeakTableElementReferences</span><span class="sxs-lookup"><span data-stu-id="80f72-110">ConditionalWeakTableElementReferences Method</span></span>](icorprofilercallback5-conditionalweaktableelementreferences-method.md)|<span data-ttu-id="80f72-111">Identifica el cierre transitivo de los objetos a los que esas raíces hacen referencia mediante referencias directas de campo de miembro y mediante dependencias `ConditionalWeakTable`.</span><span class="sxs-lookup"><span data-stu-id="80f72-111">Identifies the transitive closure of objects referenced by those roots through both direct member field references and through `ConditionalWeakTable` dependencies.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="80f72-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="80f72-112">Requirements</span></span>  

 <span data-ttu-id="80f72-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80f72-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80f72-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="80f72-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="80f72-115">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80f72-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80f72-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="80f72-116">See also</span></span>

- [<span data-ttu-id="80f72-117">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="80f72-117">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="80f72-118">ICorProfilerCallback2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="80f72-118">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
