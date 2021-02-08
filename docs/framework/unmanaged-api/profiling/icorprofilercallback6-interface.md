---
description: 'Más información acerca de: interfaz ICorProfilerCallback6'
title: ICorProfilerCallback6 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback6
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: edc420b7-96d1-4dec-ace0-36d907f644bc
topic_type:
- apiref
ms.openlocfilehash: 12eaafff8bd9ab8d4d58eac8f2d62415531bc898
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781758"
---
# <a name="icorprofilercallback6-interface"></a><span data-ttu-id="e2bc4-103">ICorProfilerCallback6 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e2bc4-103">ICorProfilerCallback6 Interface</span></span>

<span data-ttu-id="e2bc4-104">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="e2bc4-104">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="e2bc4-105">Una subclase de [ICorProfilerCallback5](icorprofilercallback5-interface.md) que proporciona un método de devolución de llamada que el Common Language Runtime utiliza para notificar a un generador de perfiles que se está cargando un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e2bc4-105">A subclass of [ICorProfilerCallback5](icorprofilercallback5-interface.md) that provides a callback method that the common language runtime uses to notify a profiler that an assembly is loading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e2bc4-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="e2bc4-106">Methods</span></span>  
  
|<span data-ttu-id="e2bc4-107">Método</span><span class="sxs-lookup"><span data-stu-id="e2bc4-107">Method</span></span>|<span data-ttu-id="e2bc4-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="e2bc4-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e2bc4-109">GetAssemblyReferences (método)</span><span class="sxs-lookup"><span data-stu-id="e2bc4-109">GetAssemblyReferences Method</span></span>](icorprofilercallback6-getassemblyreferences-method.md)|<span data-ttu-id="e2bc4-110">Notifica al generador de perfiles que un ensamblado está en una etapa de carga muy temprana, cuando Common Language Runtime realiza un rastreo de cierre de referencias de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="e2bc4-110">Notifies the profiler that an assembly is in a very early loading stage, when the common language runtime performs an assembly reference closure walk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e2bc4-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e2bc4-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2bc4-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e2bc4-112">Requirements</span></span>  

 <span data-ttu-id="e2bc4-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2bc4-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2bc4-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e2bc4-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e2bc4-115">**.NET Framework versiones:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2bc4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2bc4-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2bc4-116">See also</span></span>

- [<span data-ttu-id="e2bc4-117">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="e2bc4-117">Profiling Interfaces</span></span>](profiling-interfaces.md)
