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
ms.openlocfilehash: b11c70fa7d423575b2dd1d2cc676908885a0fd4c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33457369"
---
# <a name="icorprofilerinfo4enumjitedfunctions2-method"></a><span data-ttu-id="890c8-102">ICorProfilerInfo4::EnumJITedFunctions2 (Método)</span><span class="sxs-lookup"><span data-stu-id="890c8-102">ICorProfilerInfo4::EnumJITedFunctions2 Method</span></span>
<span data-ttu-id="890c8-103">Devuelve un enumerador para todas las funciones que anteriormente estaban compilados JIT y recompilado con JIT.</span><span class="sxs-lookup"><span data-stu-id="890c8-103">Returns an enumerator for all functions that were previously JIT-compiled and JIT-recompiled.</span></span> <span data-ttu-id="890c8-104">Este método reemplaza el [ICorProfilerInfo3:: EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) método, que no enumerar identificadores recompilado con JIT.</span><span class="sxs-lookup"><span data-stu-id="890c8-104">This method replaces the [ICorProfilerInfo3::EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) method, which does not enumerate JIT-recompiled IDs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="890c8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="890c8-105">Syntax</span></span>  
  
```  
HRESULT EnumJITedFunctions([out] ICorProfilerFunctionEnum** ppEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="890c8-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="890c8-106">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="890c8-107">[out] Un puntero a la [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) enumerador.</span><span class="sxs-lookup"><span data-stu-id="890c8-107">[out] A pointer to the [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) enumerator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="890c8-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="890c8-108">Remarks</span></span>  
 <span data-ttu-id="890c8-109">Este método se puede superponer con `JITCompilation` las devoluciones de llamada, como el [ICorProfilerCallback:: JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="890c8-109">This method may overlap with `JITCompilation` callbacks such as the [ICorProfilerCallback::JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) method.</span></span> <span data-ttu-id="890c8-110">La enumeración devuelta incluye valores para el `COR_PRF_FUNCTION::reJitId` campo.</span><span class="sxs-lookup"><span data-stu-id="890c8-110">The returned enumeration includes values for the `COR_PRF_FUNCTION::reJitId` field.</span></span> <span data-ttu-id="890c8-111">El [ICorProfilerInfo3:: EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) método, que reemplaza este método, no enumerar identificadores recompilado con JIT, porque el `COR_PRF_FUNCTION::reJitId` campo siempre está establecido en 0.</span><span class="sxs-lookup"><span data-stu-id="890c8-111">The [ICorProfilerInfo3::EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) method, which this method replaces, does not enumerate JIT-recompiled IDs, because the `COR_PRF_FUNCTION::reJitId` field is always set to 0.</span></span> <span data-ttu-id="890c8-112">El `ICorProfilerInfo4::EnumJITedFunctions` método enumerar los identificadores recompilado con JIT, porque el `COR_PRF_FUNCTION::reJitId` campo está configurado correctamente.</span><span class="sxs-lookup"><span data-stu-id="890c8-112">The `ICorProfilerInfo4::EnumJITedFunctions` method does enumerate JIT-recompiled IDs, because the `COR_PRF_FUNCTION::reJitId` field is set properly.</span></span> <span data-ttu-id="890c8-113">Tenga en cuenta que la [icorprofilerinfo4:: Enumjitedfunctions2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md) método puede desencadenar una recolección, mientras que [ICorProfilerInfo3:: EnumJITedFunctions (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) no.</span><span class="sxs-lookup"><span data-stu-id="890c8-113">Note that the [ICorProfilerInfo4::EnumJITedFunctions2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md) method can trigger a garbage collection, whereas [ICorProfilerInfo3::EnumJITedFunctions method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) will not.</span></span>  <span data-ttu-id="890c8-114">Para obtener más información, consulte [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md).</span><span class="sxs-lookup"><span data-stu-id="890c8-114">For more information, see [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="890c8-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="890c8-115">Requirements</span></span>  
 <span data-ttu-id="890c8-116">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="890c8-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="890c8-117">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="890c8-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="890c8-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="890c8-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="890c8-119">**Versiones de .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="890c8-119">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="890c8-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="890c8-120">See Also</span></span>  
 [<span data-ttu-id="890c8-121">EnumJITedFunctions (método)</span><span class="sxs-lookup"><span data-stu-id="890c8-121">EnumJITedFunctions Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md)  
 [<span data-ttu-id="890c8-122">ICorProfilerInfo4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="890c8-122">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 [<span data-ttu-id="890c8-123">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="890c8-123">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="890c8-124">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="890c8-124">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
