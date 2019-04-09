---
title: ICorProfilerInfo4::EnumJITedFunctions2 (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.EnumJITedFunctions2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::EnumJITedFunctions2
helpviewer_keywords:
- EnumJITedFunctions2 method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::EnumJITedFunctions2 method [.NET Framework profiling]
ms.assetid: 40e9a1be-9bd2-4fad-9921-34a84b61c1e3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 92bc16091abd3e21ebd226fb13dd47b55b0c9cc4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59166834"
---
# <a name="icorprofilerinfo4enumjitedfunctions2-method"></a><span data-ttu-id="aa035-102">ICorProfilerInfo4::EnumJITedFunctions2 (Método)</span><span class="sxs-lookup"><span data-stu-id="aa035-102">ICorProfilerInfo4::EnumJITedFunctions2 Method</span></span>
<span data-ttu-id="aa035-103">Devuelve un enumerador para todas las funciones que antes estaban compilados JIT y recompilada con JIT.</span><span class="sxs-lookup"><span data-stu-id="aa035-103">Returns an enumerator for all functions that were previously JIT-compiled and JIT-recompiled.</span></span> <span data-ttu-id="aa035-104">Este método reemplaza el [ICorProfilerInfo3:: EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) método, que no enumera los identificadores de recompilada con JIT.</span><span class="sxs-lookup"><span data-stu-id="aa035-104">This method replaces the [ICorProfilerInfo3::EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) method, which does not enumerate JIT-recompiled IDs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa035-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aa035-105">Syntax</span></span>  
  
```  
HRESULT EnumJITedFunctions([out] ICorProfilerFunctionEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aa035-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="aa035-106">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="aa035-107">[out] Un puntero a la [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) enumerador.</span><span class="sxs-lookup"><span data-stu-id="aa035-107">[out] A pointer to the [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) enumerator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aa035-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="aa035-108">Remarks</span></span>  
 <span data-ttu-id="aa035-109">Este método se puede superponer con `JITCompilation` las devoluciones de llamada, como el [JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="aa035-109">This method may overlap with `JITCompilation` callbacks such as the [ICorProfilerCallback::JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) method.</span></span> <span data-ttu-id="aa035-110">La enumeración devuelta incluye los valores para el `COR_PRF_FUNCTION::reJitId` campo.</span><span class="sxs-lookup"><span data-stu-id="aa035-110">The returned enumeration includes values for the `COR_PRF_FUNCTION::reJitId` field.</span></span> <span data-ttu-id="aa035-111">El [ICorProfilerInfo3:: EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) método, que reemplaza este método, no enumerar identificadores recompilada con JIT, porque el `COR_PRF_FUNCTION::reJitId` campo siempre se establece en 0.</span><span class="sxs-lookup"><span data-stu-id="aa035-111">The [ICorProfilerInfo3::EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) method, which this method replaces, does not enumerate JIT-recompiled IDs, because the `COR_PRF_FUNCTION::reJitId` field is always set to 0.</span></span> <span data-ttu-id="aa035-112">El `ICorProfilerInfo4::EnumJITedFunctions` método enumerar identificadores recompilada con JIT, porque el `COR_PRF_FUNCTION::reJitId` campo se establece correctamente.</span><span class="sxs-lookup"><span data-stu-id="aa035-112">The `ICorProfilerInfo4::EnumJITedFunctions` method does enumerate JIT-recompiled IDs, because the `COR_PRF_FUNCTION::reJitId` field is set properly.</span></span> <span data-ttu-id="aa035-113">Tenga en cuenta que el [ICorProfilerInfo4::EnumJITedFunctions2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md) método puede desencadenar una recolección de elementos, mientras que [método ICorProfilerInfo3:: EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) no se iniciará.</span><span class="sxs-lookup"><span data-stu-id="aa035-113">Note that the [ICorProfilerInfo4::EnumJITedFunctions2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md) method can trigger a garbage collection, whereas [ICorProfilerInfo3::EnumJITedFunctions method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) will not.</span></span>  <span data-ttu-id="aa035-114">Para obtener más información, consulte [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md).</span><span class="sxs-lookup"><span data-stu-id="aa035-114">For more information, see [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa035-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="aa035-115">Requirements</span></span>  
 <span data-ttu-id="aa035-116">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa035-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa035-117">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="aa035-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="aa035-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aa035-118">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="aa035-119">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="aa035-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="aa035-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="aa035-120">See also</span></span>

- [<span data-ttu-id="aa035-121">Método EnumJITedFunctions</span><span class="sxs-lookup"><span data-stu-id="aa035-121">EnumJITedFunctions Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md)
- [<span data-ttu-id="aa035-122">ICorProfilerInfo4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="aa035-122">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [<span data-ttu-id="aa035-123">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="aa035-123">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="aa035-124">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="aa035-124">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
