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
ms.openlocfilehash: 13a298451c3e8e1c5809cc1cb222acb5ab85714b
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866694"
---
# <a name="icorprofilerassemblyreferenceprovider-interface"></a><span data-ttu-id="94031-102">ICorProfilerAssemblyReferenceProvider (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="94031-102">ICorProfilerAssemblyReferenceProvider Interface</span></span>
<span data-ttu-id="94031-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="94031-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="94031-104">Permite al generador de perfiles informar al Common Language Runtime (CLR) de las referencias de ensamblado que el generador de perfiles agregará en la devolución de llamada [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="94031-104">Enables the profiler to inform the common language runtime (CLR) of assembly references that the profiler will add in the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="94031-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="94031-105">Methods</span></span>  
  
|<span data-ttu-id="94031-106">Método</span><span class="sxs-lookup"><span data-stu-id="94031-106">Method</span></span>|<span data-ttu-id="94031-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="94031-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="94031-108">Método AddAssemblyReference</span><span class="sxs-lookup"><span data-stu-id="94031-108">AddAssemblyReference Method</span></span>](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)|<span data-ttu-id="94031-109">Informa al CLR de una referencia de ensamblado que el generador de perfiles tiene previsto agregar en la devolución de llamada [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="94031-109">Informs the CLR of an assembly reference that the profiler plans to add in the [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="94031-110">Notas</span><span class="sxs-lookup"><span data-stu-id="94031-110">Remarks</span></span>  
 <span data-ttu-id="94031-111">El CLR pasa el generador de perfiles a un objeto de interfaz de `ICorProfilerAssemblyReferenceProvider` en la devolución de llamada [ICorProfilerCallback6:: GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) .</span><span class="sxs-lookup"><span data-stu-id="94031-111">The CLR passes the profiler an `ICorProfilerAssemblyReferenceProvider` interface object in the [ICorProfilerCallback6::GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) callback.</span></span> <span data-ttu-id="94031-112">Esto permite al generador de perfiles informar a CLR de las referencias de ensamblado que el generador de perfiles planea agregar posteriormente en [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md).</span><span class="sxs-lookup"><span data-stu-id="94031-112">This enables the profiler to inform the CLR of assembly references that the profiler plans to add later in the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md).</span></span> <span data-ttu-id="94031-113">.</span><span class="sxs-lookup"><span data-stu-id="94031-113">callback.</span></span> <span data-ttu-id="94031-114">Mejora la precisión del rastreador de cierres de referencia de ensamblado de CLR y de sus algoritmos para determinar si los ensamblados se pueden compartir.</span><span class="sxs-lookup"><span data-stu-id="94031-114">This improves the accuracy of the CLR's assembly reference closure walker and its algorithms for determining whether assemblies may be shared.</span></span>  
  
 <span data-ttu-id="94031-115">Esta interfaz solo se puede usar en la devolución de llamada [ICorProfilerCallback6:: GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) que pasa este objeto de interfaz al generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="94031-115">This interface can be used only in the [ICorProfilerCallback6::GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) callback that passes this interface object to the profiler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94031-116">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="94031-116">Requirements</span></span>  
 <span data-ttu-id="94031-117">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94031-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94031-118">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="94031-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="94031-119">**.NET Framework versiones:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94031-119">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94031-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="94031-120">See also</span></span>

- [<span data-ttu-id="94031-121">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="94031-121">Profiling Interfaces</span></span>](profiling-interfaces.md)
