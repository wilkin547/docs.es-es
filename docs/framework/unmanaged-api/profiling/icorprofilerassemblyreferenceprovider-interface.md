---
title: ICorProfilerAssemblyReferenceProvider (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorProfilerAssemblyReferenceProvider
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 17205116-66e1-4acc-8f01-532fb3867028
topic_type:
- apiref
ms.openlocfilehash: 17fb3de830d1aed2214631bbe8254a7f58030025
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500525"
---
# <a name="icorprofilerassemblyreferenceprovider-interface"></a><span data-ttu-id="e0c13-102">ICorProfilerAssemblyReferenceProvider (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e0c13-102">ICorProfilerAssemblyReferenceProvider Interface</span></span>
<span data-ttu-id="e0c13-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="e0c13-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="e0c13-104">Permite al generador de perfiles informar al Common Language Runtime (CLR) de las referencias de ensamblado que el generador de perfiles agregará en la devolución de llamada [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e0c13-104">Enables the profiler to inform the common language runtime (CLR) of assembly references that the profiler will add in the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e0c13-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="e0c13-105">Methods</span></span>  
  
|<span data-ttu-id="e0c13-106">Método</span><span class="sxs-lookup"><span data-stu-id="e0c13-106">Method</span></span>|<span data-ttu-id="e0c13-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="e0c13-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e0c13-108">Método AddAssemblyReference</span><span class="sxs-lookup"><span data-stu-id="e0c13-108">AddAssemblyReference Method</span></span>](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)|<span data-ttu-id="e0c13-109">Informa al CLR de una referencia de ensamblado que el generador de perfiles tiene previsto agregar en la devolución de llamada [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e0c13-109">Informs the CLR of an assembly reference that the profiler plans to add in the [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e0c13-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e0c13-110">Remarks</span></span>  
 <span data-ttu-id="e0c13-111">El CLR pasa el generador de perfiles a un `ICorProfilerAssemblyReferenceProvider` objeto de interfaz en la devolución de llamada [ICorProfilerCallback6:: GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e0c13-111">The CLR passes the profiler an `ICorProfilerAssemblyReferenceProvider` interface object in the [ICorProfilerCallback6::GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) callback.</span></span> <span data-ttu-id="e0c13-112">Esto permite al generador de perfiles informar a CLR de las referencias de ensamblado que el generador de perfiles planea agregar posteriormente en [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md).</span><span class="sxs-lookup"><span data-stu-id="e0c13-112">This enables the profiler to inform the CLR of assembly references that the profiler plans to add later in the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md).</span></span> <span data-ttu-id="e0c13-113">.</span><span class="sxs-lookup"><span data-stu-id="e0c13-113">callback.</span></span> <span data-ttu-id="e0c13-114">Mejora la precisión del rastreador de cierres de referencia de ensamblado de CLR y de sus algoritmos para determinar si los ensamblados se pueden compartir.</span><span class="sxs-lookup"><span data-stu-id="e0c13-114">This improves the accuracy of the CLR's assembly reference closure walker and its algorithms for determining whether assemblies may be shared.</span></span>  
  
 <span data-ttu-id="e0c13-115">Esta interfaz solo se puede usar en la devolución de llamada [ICorProfilerCallback6:: GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) que pasa este objeto de interfaz al generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="e0c13-115">This interface can be used only in the [ICorProfilerCallback6::GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) callback that passes this interface object to the profiler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0c13-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e0c13-116">Requirements</span></span>  
 <span data-ttu-id="e0c13-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0c13-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0c13-118">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e0c13-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e0c13-119">**.NET Framework versiones:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0c13-119">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0c13-120">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="e0c13-120">See also</span></span>

- [<span data-ttu-id="e0c13-121">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="e0c13-121">Profiling Interfaces</span></span>](profiling-interfaces.md)
