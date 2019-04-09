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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8fda98c20b42355b9f52595929bbf5b980b5b857
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59077243"
---
# <a name="icorprofilercallback6-interface"></a><span data-ttu-id="de7ff-102">ICorProfilerCallback6 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="de7ff-102">ICorProfilerCallback6 Interface</span></span>
<span data-ttu-id="de7ff-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="de7ff-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="de7ff-104">Una subclase de [ICorProfilerCallback5](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md) que proporciona un método de devolución de llamada que common language runtime utiliza para notificar a un generador de perfiles que se está cargando un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="de7ff-104">A subclass of [ICorProfilerCallback5](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md) that provides a callback method that the common language runtime uses to notify a profiler that an assembly is loading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="de7ff-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="de7ff-105">Methods</span></span>  
  
|<span data-ttu-id="de7ff-106">Método</span><span class="sxs-lookup"><span data-stu-id="de7ff-106">Method</span></span>|<span data-ttu-id="de7ff-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="de7ff-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="de7ff-108">Método GetAssemblyReferences</span><span class="sxs-lookup"><span data-stu-id="de7ff-108">GetAssemblyReferences Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)|<span data-ttu-id="de7ff-109">Notifica al generador de perfiles que un ensamblado está en una etapa de carga muy temprana, cuando Common Language Runtime realiza un rastreo de cierre de referencias de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="de7ff-109">Notifies the profiler that an assembly is in a very early loading stage, when the common language runtime performs an assembly reference closure walk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="de7ff-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="de7ff-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de7ff-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="de7ff-111">Requirements</span></span>  
 <span data-ttu-id="de7ff-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de7ff-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de7ff-113">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="de7ff-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 **<span data-ttu-id="de7ff-114">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="de7ff-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="de7ff-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="de7ff-115">See also</span></span>

- [<span data-ttu-id="de7ff-116">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="de7ff-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
