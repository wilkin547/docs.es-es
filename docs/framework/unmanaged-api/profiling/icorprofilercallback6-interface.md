---
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
ms.openlocfilehash: 0156a7dfa2a67ce9e62b502df00fc6bc5fccf925
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499186"
---
# <a name="icorprofilercallback6-interface"></a><span data-ttu-id="50cc7-102">ICorProfilerCallback6 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="50cc7-102">ICorProfilerCallback6 Interface</span></span>
<span data-ttu-id="50cc7-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="50cc7-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="50cc7-104">Una subclase de [ICorProfilerCallback5](icorprofilercallback5-interface.md) que proporciona un método de devolución de llamada que el Common Language Runtime utiliza para notificar a un generador de perfiles que se está cargando un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="50cc7-104">A subclass of [ICorProfilerCallback5](icorprofilercallback5-interface.md) that provides a callback method that the common language runtime uses to notify a profiler that an assembly is loading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="50cc7-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="50cc7-105">Methods</span></span>  
  
|<span data-ttu-id="50cc7-106">Método</span><span class="sxs-lookup"><span data-stu-id="50cc7-106">Method</span></span>|<span data-ttu-id="50cc7-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="50cc7-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="50cc7-108">GetAssemblyReferences (método)</span><span class="sxs-lookup"><span data-stu-id="50cc7-108">GetAssemblyReferences Method</span></span>](icorprofilercallback6-getassemblyreferences-method.md)|<span data-ttu-id="50cc7-109">Notifica al generador de perfiles que un ensamblado está en una etapa de carga muy temprana, cuando Common Language Runtime realiza un rastreo de cierre de referencias de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="50cc7-109">Notifies the profiler that an assembly is in a very early loading stage, when the common language runtime performs an assembly reference closure walk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="50cc7-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="50cc7-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50cc7-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="50cc7-111">Requirements</span></span>  
 <span data-ttu-id="50cc7-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50cc7-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50cc7-113">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="50cc7-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="50cc7-114">**.NET Framework versiones:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50cc7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50cc7-115">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="50cc7-115">See also</span></span>

- [<span data-ttu-id="50cc7-116">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="50cc7-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
