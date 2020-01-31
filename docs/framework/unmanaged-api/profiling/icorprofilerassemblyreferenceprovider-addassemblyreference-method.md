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
ms.openlocfilehash: 2357e5348192db5d41adfe1176300359440aeee3
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866733"
---
# <a name="icorprofilerassemblyreferenceprovideraddassemblyreference-method"></a><span data-ttu-id="4c1b5-102">ICorProfilerAssemblyReferenceProvider::AddAssemblyReference (Método)</span><span class="sxs-lookup"><span data-stu-id="4c1b5-102">ICorProfilerAssemblyReferenceProvider::AddAssemblyReference Method</span></span>
<span data-ttu-id="4c1b5-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="4c1b5-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="4c1b5-104">Informa al Common Language Runtime (CLR) de una referencia de ensamblado que el generador de perfiles tiene previsto agregar en la devolución de llamada [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="4c1b5-104">Informs the common language runtime (CLR) of an assembly reference that the profiler plans to add in the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c1b5-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4c1b5-105">Syntax</span></span>  
  
```cpp
HRESULT AddAssemblyReference(  
        const COR_PRF_ASSEMBLY_REFERENCE_INFO* pAssemblyRefInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4c1b5-106">Parameters</span><span class="sxs-lookup"><span data-stu-id="4c1b5-106">Parameters</span></span>

- `pAssemblyRefInfo`

  <span data-ttu-id="4c1b5-107">Puntero a una estructura de [COR_PRF_ASSEMBLY_REFERENCE_INFO](cor-prf-assembly-reference-info-structure.md) que proporciona a CLR información sobre una referencia de ensamblado que debe tener en cuenta al realizar un recorrido de cierre de referencia de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="4c1b5-107">A pointer to a [COR_PRF_ASSEMBLY_REFERENCE_INFO](cor-prf-assembly-reference-info-structure.md) structure that provides the CLR with information about an assembly reference that it should consider when performing an assembly reference closure walk.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="4c1b5-108">Notas</span><span class="sxs-lookup"><span data-stu-id="4c1b5-108">Remarks</span></span>  
 <span data-ttu-id="4c1b5-109">El generador de perfiles llama a este método para cada ensamblado de destino al que tiene previsto hacer referencia desde el ensamblado especificado en el argumento `wszAssemblyPath` de la devolución de llamada [ICorProfilerCallback6:: GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) .</span><span class="sxs-lookup"><span data-stu-id="4c1b5-109">The profiler calls this method for each target assembly it plans to reference from the assembly specified in the `wszAssemblyPath` argument of the [ICorProfilerCallback6::GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) callback.</span></span> <span data-ttu-id="4c1b5-110">El objeto de interfaz [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) se pasa a la devolución de llamada [ICorProfilerCallback6:: GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) del generador de perfiles, junto con la ruta de acceso y el nombre del ensamblado en el argumento `wszAssemblyPath`.</span><span class="sxs-lookup"><span data-stu-id="4c1b5-110">The [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) interface object is passed to the profiler's [ICorProfilerCallback6::GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) callback, along with the assembly path and name in the `wszAssemblyPath` argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c1b5-111">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="4c1b5-111">Requirements</span></span>  
 <span data-ttu-id="4c1b5-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4c1b5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c1b5-113">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4c1b5-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4c1b5-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4c1b5-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4c1b5-115">**.NET Framework versiones:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c1b5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c1b5-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="4c1b5-116">See also</span></span>

- [<span data-ttu-id="4c1b5-117">ICorProfilerAssemblyReferenceProvider (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4c1b5-117">ICorProfilerAssemblyReferenceProvider Interface</span></span>](icorprofilerassemblyreferenceprovider-interface.md)
- [<span data-ttu-id="4c1b5-118">GetAssemblyReferences (método)</span><span class="sxs-lookup"><span data-stu-id="4c1b5-118">GetAssemblyReferences Method</span></span>](icorprofilercallback6-getassemblyreferences-method.md)
- [<span data-ttu-id="4c1b5-119">ModuleLoadFinished (método)</span><span class="sxs-lookup"><span data-stu-id="4c1b5-119">ModuleLoadFinished Method</span></span>](icorprofilercallback-moduleloadfinished-method.md)
