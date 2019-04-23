---
title: ICorProfilerInfo4::GetReJITIDs (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetReJITIDs
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetReJITIDs
helpviewer_keywords:
- GetReJITIDs method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::GetReJITIDs method [.NET Framework profiling]
ms.assetid: 634ac28c-a5b7-4fc3-af84-256c24ca8177
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9d2d48e5fb070ec0334de579d2e28146177a87b1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59121620"
---
# <a name="icorprofilerinfo4getrejitids-method"></a><span data-ttu-id="17a9d-102">ICorProfilerInfo4::GetReJITIDs (Método)</span><span class="sxs-lookup"><span data-stu-id="17a9d-102">ICorProfilerInfo4::GetReJITIDs Method</span></span>
<span data-ttu-id="17a9d-103">Devuelve una matriz de identificadores que identifican todas recompilada con JIT las versiones de la función especificada que todavía se asignan.</span><span class="sxs-lookup"><span data-stu-id="17a9d-103">Returns an array of IDs that identify all JIT-recompiled versions of the specified function that are still allocated.</span></span> <span data-ttu-id="17a9d-104">Esto incluye versiones recompilada con JIT de funciones que se han revertido posteriormente, pero aún no se ha liberado (por ejemplo, cuando el dominio de aplicación que contiene la función revertida todavía está en uso).</span><span class="sxs-lookup"><span data-stu-id="17a9d-104">This includes JIT-recompiled versions of functions that have been subsequently reverted but not yet freed (for example, when the application domain that contains the reverted function is still in use).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17a9d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="17a9d-105">Syntax</span></span>  
  
```  
HRESULT GetReJITIDs (  
     [in]  FunctionID          functionId,  
     [in]  ULONG               cReJitIds,  
     [out] ULONG *             pcReJitIds,  
     [out, size_is(cReJitIds), length_is(*pcReJitIds)]   ReJITID        reJitIds[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="17a9d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="17a9d-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="17a9d-107">[in] El `FunctionID` de la instancia de la función para que se enumeran las versiones.</span><span class="sxs-lookup"><span data-stu-id="17a9d-107">[in] The `FunctionID` of the function instance for which to enumerate versions.</span></span>  
  
 `cReJitIds`  
 <span data-ttu-id="17a9d-108">[in] El número de identificadores recompilada con JIT asignada en el `reJitIds` matriz.</span><span class="sxs-lookup"><span data-stu-id="17a9d-108">[in] The number of JIT-recompiled IDs allocated in the `reJitIds` array.</span></span>  
  
 `pcReJitIds`  
 <span data-ttu-id="17a9d-109">[out] El número real de los identificadores de recompilada con JIT.</span><span class="sxs-lookup"><span data-stu-id="17a9d-109">[out] The actual number of JIT-recompiled IDs.</span></span>  
  
 `reJitIds`  
 <span data-ttu-id="17a9d-110">[out] Una matriz asignada por el llamador que contendrá los identificadores recompilada con JIT para la función especificada.</span><span class="sxs-lookup"><span data-stu-id="17a9d-110">[out] A caller-allocated array that will contain the JIT-recompiled IDs for the specified function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="17a9d-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="17a9d-111">Remarks</span></span>  
 <span data-ttu-id="17a9d-112">`GetReJITIDs` Enumera los identificadores de recompilada con JIT activos para una instancia de la función especificada.</span><span class="sxs-lookup"><span data-stu-id="17a9d-112">`GetReJITIDs` enumerates the active JIT-recompiled IDs for a given function instance.</span></span> <span data-ttu-id="17a9d-113">Sigue el mismo patrón de uso como otro `ICorProfilerInfo` funciones que aceptan los búferes asignados por el llamador.</span><span class="sxs-lookup"><span data-stu-id="17a9d-113">It follows the same usage pattern as other `ICorProfilerInfo` functions that accept caller-allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17a9d-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="17a9d-114">Requirements</span></span>  
 <span data-ttu-id="17a9d-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17a9d-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17a9d-116">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="17a9d-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="17a9d-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="17a9d-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="17a9d-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17a9d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17a9d-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="17a9d-119">See also</span></span>

- [<span data-ttu-id="17a9d-120">ICorProfilerInfo4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="17a9d-120">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [<span data-ttu-id="17a9d-121">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="17a9d-121">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="17a9d-122">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="17a9d-122">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
