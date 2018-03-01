---
title: ICorProfilerAssemblyReferenceProvider (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerAssemblyReferenceProvider
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 17205116-66e1-4acc-8f01-532fb3867028
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 203362d2780d372236b05f753bedc0d59565d2b5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerassemblyreferenceprovider-interface"></a><span data-ttu-id="b6076-102">ICorProfilerAssemblyReferenceProvider (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b6076-102">ICorProfilerAssemblyReferenceProvider Interface</span></span>
<span data-ttu-id="b6076-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="b6076-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="b6076-104">Permite al generador de perfiles informar a common language runtime (CLR) de las referencias de ensamblado que el generador de perfiles agregará en el [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="b6076-104">Enables the profiler to inform the common language runtime (CLR) of assembly references that the profiler will add in the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b6076-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="b6076-105">Methods</span></span>  
  
|<span data-ttu-id="b6076-106">Método</span><span class="sxs-lookup"><span data-stu-id="b6076-106">Method</span></span>|<span data-ttu-id="b6076-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="b6076-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b6076-108">Método AddAssemblyReference</span><span class="sxs-lookup"><span data-stu-id="b6076-108">AddAssemblyReference Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)|<span data-ttu-id="b6076-109">Informa a CLR de una referencia de ensamblado que el generador de perfiles planea agregar en el [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="b6076-109">Informs the CLR of an assembly reference that the profiler plans to add in the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b6076-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b6076-110">Remarks</span></span>  
 <span data-ttu-id="b6076-111">El CLR pasa el generador de perfiles una `ICorProfilerAssemblyReferenceProvider` objeto de interfaz en el [icorprofilercallback6:: Getassemblyreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="b6076-111">The CLR passes the profiler an `ICorProfilerAssemblyReferenceProvider` interface object in the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback.</span></span> <span data-ttu-id="b6076-112">Esto permite al generador de perfiles informar a CLR de referencias de ensamblado que el generador de perfiles planea agregar más adelante en el [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md).</span><span class="sxs-lookup"><span data-stu-id="b6076-112">This enables the profiler to inform the CLR of assembly references that the profiler plans to add later in the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md).</span></span> <span data-ttu-id="b6076-113">.</span><span class="sxs-lookup"><span data-stu-id="b6076-113">callback.</span></span> <span data-ttu-id="b6076-114">Mejora la precisión del rastreador de cierres de referencia de ensamblado de CLR y de sus algoritmos para determinar si los ensamblados se pueden compartir.</span><span class="sxs-lookup"><span data-stu-id="b6076-114">This improves the accuracy of the CLR's assembly reference closure walker and its algorithms for determining whether assemblies may be shared.</span></span>  
  
 <span data-ttu-id="b6076-115">Esta interfaz se puede usar solo en el [icorprofilercallback6:: Getassemblyreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) devolución de llamada que se pasa este objeto de interfaz al generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="b6076-115">This interface can be used only in the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback that passes this interface object to the profiler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6076-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b6076-116">Requirements</span></span>  
 <span data-ttu-id="b6076-117">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6076-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6076-118">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b6076-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b6076-119">**Versiones de .NET framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6076-119">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6076-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="b6076-120">See Also</span></span>  
 [<span data-ttu-id="b6076-121">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="b6076-121">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
