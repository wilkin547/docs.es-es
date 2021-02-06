---
description: 'Más información acerca de: interfaz ICorProfilerAssemblyReferenceProvider'
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
ms.openlocfilehash: 0f16bad95dba46452ce5cc8ad1bbe6ca1bfeb7c8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99648355"
---
# <a name="icorprofilerassemblyreferenceprovider-interface"></a><span data-ttu-id="73442-103">ICorProfilerAssemblyReferenceProvider (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="73442-103">ICorProfilerAssemblyReferenceProvider Interface</span></span>

<span data-ttu-id="73442-104">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="73442-104">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="73442-105">Permite al generador de perfiles informar al Common Language Runtime (CLR) de las referencias de ensamblado que el generador de perfiles agregará en la devolución de llamada [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="73442-105">Enables the profiler to inform the common language runtime (CLR) of assembly references that the profiler will add in the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="73442-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="73442-106">Methods</span></span>  
  
|<span data-ttu-id="73442-107">Método</span><span class="sxs-lookup"><span data-stu-id="73442-107">Method</span></span>|<span data-ttu-id="73442-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="73442-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="73442-109">Método AddAssemblyReference</span><span class="sxs-lookup"><span data-stu-id="73442-109">AddAssemblyReference Method</span></span>](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)|<span data-ttu-id="73442-110">Informa al CLR de una referencia de ensamblado que el generador de perfiles tiene previsto agregar en la devolución de llamada [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="73442-110">Informs the CLR of an assembly reference that the profiler plans to add in the [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73442-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="73442-111">Remarks</span></span>  

 <span data-ttu-id="73442-112">El CLR pasa el generador de perfiles a un `ICorProfilerAssemblyReferenceProvider` objeto de interfaz en la devolución de llamada [ICorProfilerCallback6:: GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) .</span><span class="sxs-lookup"><span data-stu-id="73442-112">The CLR passes the profiler an `ICorProfilerAssemblyReferenceProvider` interface object in the [ICorProfilerCallback6::GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) callback.</span></span> <span data-ttu-id="73442-113">Esto permite al generador de perfiles informar a CLR de las referencias de ensamblado que el generador de perfiles planea agregar posteriormente en [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md).</span><span class="sxs-lookup"><span data-stu-id="73442-113">This enables the profiler to inform the CLR of assembly references that the profiler plans to add later in the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md).</span></span> <span data-ttu-id="73442-114">.</span><span class="sxs-lookup"><span data-stu-id="73442-114">callback.</span></span> <span data-ttu-id="73442-115">Mejora la precisión del rastreador de cierres de referencia de ensamblado de CLR y de sus algoritmos para determinar si los ensamblados se pueden compartir.</span><span class="sxs-lookup"><span data-stu-id="73442-115">This improves the accuracy of the CLR's assembly reference closure walker and its algorithms for determining whether assemblies may be shared.</span></span>  
  
 <span data-ttu-id="73442-116">Esta interfaz solo se puede usar en la devolución de llamada [ICorProfilerCallback6:: GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) que pasa este objeto de interfaz al generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="73442-116">This interface can be used only in the [ICorProfilerCallback6::GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) callback that passes this interface object to the profiler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73442-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="73442-117">Requirements</span></span>  

 <span data-ttu-id="73442-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="73442-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73442-119">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="73442-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="73442-120">**.NET Framework versiones:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73442-120">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73442-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="73442-121">See also</span></span>

- [<span data-ttu-id="73442-122">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="73442-122">Profiling Interfaces</span></span>](profiling-interfaces.md)
