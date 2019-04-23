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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 09ce4f3a293e7870ddadf4ad6ee2c15de10f4594
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59200576"
---
# <a name="icorprofilerassemblyreferenceprovideraddassemblyreference-method"></a><span data-ttu-id="f88ed-102">ICorProfilerAssemblyReferenceProvider::AddAssemblyReference (Método)</span><span class="sxs-lookup"><span data-stu-id="f88ed-102">ICorProfilerAssemblyReferenceProvider::AddAssemblyReference Method</span></span>
<span data-ttu-id="f88ed-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="f88ed-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="f88ed-104">Informa a common language runtime (CLR) de una referencia de ensamblado que el generador de perfiles planea agregar en el [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="f88ed-104">Informs the common language runtime (CLR) of an assembly reference that the profiler plans to add in the [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f88ed-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f88ed-105">Syntax</span></span>  
  
```cpp
HRESULT AddAssemblyReference(  
        const COR_PRF_ASSEMBLY_REFERENCE_INFO* pAssemblyRefInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f88ed-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f88ed-106">Parameters</span></span>  
 <span data-ttu-id="f88ed-107">pAssemblyRefInfo</span><span class="sxs-lookup"><span data-stu-id="f88ed-107">pAssemblyRefInfo</span></span>  
 <span data-ttu-id="f88ed-108">Un puntero a un [COR_PRF_ASSEMBLY_REFERENCE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-assembly-reference-info-structure.md) estructura que proporciona información sobre una referencia de ensamblado que debe tener en cuenta al realizar un rastreo de cierre de referencias de ensamblado CLR.</span><span class="sxs-lookup"><span data-stu-id="f88ed-108">A pointer to a [COR_PRF_ASSEMBLY_REFERENCE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-assembly-reference-info-structure.md) structure that provides the CLR with information about an assembly reference that it should consider when performing an assembly reference closure walk.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f88ed-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f88ed-109">Remarks</span></span>  
 <span data-ttu-id="f88ed-110">El generador de perfiles llama a este método para cada ensamblado de destino tiene previsto hacer referencia desde el ensamblado especificado en el `wszAssemblyPath` argumento de la [icorprofilercallback6:: Getassemblyreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="f88ed-110">The profiler calls this method for each target assembly it plans to reference from the assembly specified in the `wszAssemblyPath` argument of the [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback.</span></span> <span data-ttu-id="f88ed-111">El [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) objeto de interfaz se pasa al generador de perfiles [icorprofilercallback6:: Getassemblyreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) devolución de llamada, junto con la ruta de acceso de ensamblado y el nombre en el `wszAssemblyPath` argumento.</span><span class="sxs-lookup"><span data-stu-id="f88ed-111">The [ICorProfilerAssemblyReferenceProvider](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md) interface object is passed to the profiler's [ICorProfilerCallback6::GetAssemblyReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback, along with the assembly path and name in the `wszAssemblyPath` argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f88ed-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f88ed-112">Requirements</span></span>  
 <span data-ttu-id="f88ed-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f88ed-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f88ed-114">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f88ed-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f88ed-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f88ed-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f88ed-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f88ed-116">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f88ed-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="f88ed-117">See also</span></span>

- [<span data-ttu-id="f88ed-118">ICorProfilerAssemblyReferenceProvider (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f88ed-118">ICorProfilerAssemblyReferenceProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md)
- [<span data-ttu-id="f88ed-119">GetAssemblyReferences (método)</span><span class="sxs-lookup"><span data-stu-id="f88ed-119">GetAssemblyReferences Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)
- [<span data-ttu-id="f88ed-120">ModuleLoadFinished (método)</span><span class="sxs-lookup"><span data-stu-id="f88ed-120">ModuleLoadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)
