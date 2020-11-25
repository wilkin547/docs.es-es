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
ms.openlocfilehash: 2ac645cbaaa45554568874653be016e4691bbd2f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707482"
---
# <a name="icorprofilerinfo4getrejitids-method"></a><span data-ttu-id="b92dc-102">ICorProfilerInfo4::GetReJITIDs (Método)</span><span class="sxs-lookup"><span data-stu-id="b92dc-102">ICorProfilerInfo4::GetReJITIDs Method</span></span>

<span data-ttu-id="b92dc-103">Devuelve una matriz de identificadores que identifican todas las versiones compiladas con JIT de la función especificada que se siguen asignando.</span><span class="sxs-lookup"><span data-stu-id="b92dc-103">Returns an array of IDs that identify all JIT-recompiled versions of the specified function that are still allocated.</span></span> <span data-ttu-id="b92dc-104">Esto incluye las versiones de funciones compiladas con JIT que se han revertido posteriormente pero que todavía no se han liberado (por ejemplo, cuando el dominio de aplicación que contiene la función revertida todavía está en uso).</span><span class="sxs-lookup"><span data-stu-id="b92dc-104">This includes JIT-recompiled versions of functions that have been subsequently reverted but not yet freed (for example, when the application domain that contains the reverted function is still in use).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b92dc-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b92dc-105">Syntax</span></span>  
  
```cpp
HRESULT GetReJITIDs (  
     [in]  FunctionID          functionId,  
     [in]  ULONG               cReJitIds,  
     [out] ULONG *             pcReJitIds,  
     [out, size_is(cReJitIds), length_is(*pcReJitIds)]   ReJITID        reJitIds[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b92dc-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b92dc-106">Parameters</span></span>  

 `functionId`  
 <span data-ttu-id="b92dc-107">de `FunctionID` De la instancia de la función para la que se van a enumerar las versiones.</span><span class="sxs-lookup"><span data-stu-id="b92dc-107">[in] The `FunctionID` of the function instance for which to enumerate versions.</span></span>  
  
 `cReJitIds`  
 <span data-ttu-id="b92dc-108">de Número de identificadores de recompilación JIT asignados en la `reJitIds` matriz.</span><span class="sxs-lookup"><span data-stu-id="b92dc-108">[in] The number of JIT-recompiled IDs allocated in the `reJitIds` array.</span></span>  
  
 `pcReJitIds`  
 <span data-ttu-id="b92dc-109">enuncia Número real de identificadores recompilados con JIT.</span><span class="sxs-lookup"><span data-stu-id="b92dc-109">[out] The actual number of JIT-recompiled IDs.</span></span>  
  
 `reJitIds`  
 <span data-ttu-id="b92dc-110">enuncia Matriz asignada por el llamador que contendrá los identificadores de recompilación JIT de la función especificada.</span><span class="sxs-lookup"><span data-stu-id="b92dc-110">[out] A caller-allocated array that will contain the JIT-recompiled IDs for the specified function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b92dc-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b92dc-111">Remarks</span></span>  

 <span data-ttu-id="b92dc-112">`GetReJITIDs` enumera los identificadores de compilación JIT activos para una instancia de función determinada.</span><span class="sxs-lookup"><span data-stu-id="b92dc-112">`GetReJITIDs` enumerates the active JIT-recompiled IDs for a given function instance.</span></span> <span data-ttu-id="b92dc-113">Sigue el mismo patrón de uso que otras `ICorProfilerInfo` funciones que aceptan búferes asignados por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="b92dc-113">It follows the same usage pattern as other `ICorProfilerInfo` functions that accept caller-allocated buffers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b92dc-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b92dc-114">Requirements</span></span>  

 <span data-ttu-id="b92dc-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b92dc-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b92dc-116">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b92dc-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b92dc-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b92dc-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b92dc-118">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b92dc-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b92dc-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b92dc-119">See also</span></span>

- [<span data-ttu-id="b92dc-120">ICorProfilerInfo4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b92dc-120">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
- [<span data-ttu-id="b92dc-121">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="b92dc-121">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="b92dc-122">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="b92dc-122">Profiling</span></span>](index.md)
