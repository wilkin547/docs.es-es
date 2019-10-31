---
title: ICorProfilerAssemblyReferenceProvider::AddAssemblyReference (Método)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorProfilerAssemblyReferenceProvider.AddAssemblyReference
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 3d5af8e7-c337-48f4-9fa6-97c83878b9b1
topic_type:
- apiref
ms.openlocfilehash: 2325e3034dbf00441e587017affa65b80821fbb1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128750"
---
# <a name="icorprofilerassemblyreferenceprovideraddassemblyreference-method"></a><span data-ttu-id="2408b-102">ICorProfilerAssemblyReferenceProvider::AddAssemblyReference (Método)</span><span class="sxs-lookup"><span data-stu-id="2408b-102">ICorProfilerAssemblyReferenceProvider::AddAssemblyReference Method</span></span>
<span data-ttu-id="2408b-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="2408b-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="2408b-104">Informa al Common Language Runtime (CLR) de una referencia de ensamblado que el generador de perfiles tiene previsto agregar en la devolución de llamada [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="2408b-104">Informs the common language runtime (CLR) of an assembly reference that the profiler plans to add in the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2408b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2408b-105">Syntax</span></span>  
  
```cpp
HRESULT AddAssemblyReference(  
        const COR_PRF_ASSEMBLY_REFERENCE_INFO* pAssemblyRefInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2408b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2408b-106">Parameters</span></span>  
 <span data-ttu-id="2408b-107">pAssemblyRefInfo</span><span class="sxs-lookup"><span data-stu-id="2408b-107">pAssemblyRefInfo</span></span>  
 <span data-ttu-id="2408b-108">Puntero a una estructura [COR_PRF_ASSEMBLY_REFERENCE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-assembly-reference-info-structure.md) que proporciona a CLR información sobre una referencia de ensamblado que debe tener en cuenta al realizar un recorrido de cierre de referencia de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="2408b-108">A pointer to a [COR_PRF_ASSEMBLY_REFERENCE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-assembly-reference-info-structure.md) structure that provides the CLR with information about an assembly reference that it should consider when performing an assembly reference closure walk.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2408b-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2408b-109">Remarks</span></span>  
 <span data-ttu-id="2408b-110">El generador de perfiles llama a este método para cada ensamblado de destino al que tiene previsto hacer referencia desde el ensamblado especificado en el argumento `wszAssemblyPath` de la devolución de llamada [ICorProfilerCallback6:: GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) .</span><span class="sxs-lookup"><span data-stu-id="2408b-110">The profiler calls this method for each target assembly it plans to reference from the assembly specified in the `wszAssemblyPath` argument of the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback.</span></span> <span data-ttu-id="2408b-111">El objeto de interfaz [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) se pasa a la devolución de llamada [ICorProfilerCallback6:: GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) del generador de perfiles, junto con la ruta de acceso y el nombre del ensamblado en el argumento `wszAssemblyPath`.</span><span class="sxs-lookup"><span data-stu-id="2408b-111">The [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) interface object is passed to the profiler's [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback, along with the assembly path and name in the `wszAssemblyPath` argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2408b-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2408b-112">Requirements</span></span>  
 <span data-ttu-id="2408b-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2408b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2408b-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2408b-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2408b-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2408b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2408b-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2408b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2408b-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="2408b-117">See also</span></span>

- [<span data-ttu-id="2408b-118">ICorProfilerAssemblyReferenceProvider (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2408b-118">ICorProfilerAssemblyReferenceProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md)
- [<span data-ttu-id="2408b-119">GetAssemblyReferences (método)</span><span class="sxs-lookup"><span data-stu-id="2408b-119">GetAssemblyReferences Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)
- [<span data-ttu-id="2408b-120">ModuleLoadFinished (método)</span><span class="sxs-lookup"><span data-stu-id="2408b-120">ModuleLoadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)
