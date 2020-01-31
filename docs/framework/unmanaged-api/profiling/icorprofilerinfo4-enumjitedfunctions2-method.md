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
ms.openlocfilehash: 3903ebf1ad35bd7eb1ba49b4f1acda9024678423
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862209"
---
# <a name="icorprofilerinfo4enumjitedfunctions2-method"></a><span data-ttu-id="20d16-102">ICorProfilerInfo4::EnumJITedFunctions2 (Método)</span><span class="sxs-lookup"><span data-stu-id="20d16-102">ICorProfilerInfo4::EnumJITedFunctions2 Method</span></span>
<span data-ttu-id="20d16-103">Devuelve un enumerador para todas las funciones compiladas previamente y compiladas con JIT.</span><span class="sxs-lookup"><span data-stu-id="20d16-103">Returns an enumerator for all functions that were previously JIT-compiled and JIT-recompiled.</span></span> <span data-ttu-id="20d16-104">Este método reemplaza el método [ICorProfilerInfo3:: EnumJITedFunctions (](icorprofilerinfo3-enumjitedfunctions-method.md) , que no enumera los identificadores de recompilación JIT.</span><span class="sxs-lookup"><span data-stu-id="20d16-104">This method replaces the [ICorProfilerInfo3::EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md) method, which does not enumerate JIT-recompiled IDs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20d16-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="20d16-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumJITedFunctions([out] ICorProfilerFunctionEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="20d16-106">Parameters</span><span class="sxs-lookup"><span data-stu-id="20d16-106">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="20d16-107">enuncia Puntero al enumerador [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="20d16-107">[out] A pointer to the [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) enumerator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="20d16-108">Notas</span><span class="sxs-lookup"><span data-stu-id="20d16-108">Remarks</span></span>  
 <span data-ttu-id="20d16-109">Este método se puede superponer con `JITCompilation` devoluciones de llamada como el método [ICorProfilerCallback:: JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) .</span><span class="sxs-lookup"><span data-stu-id="20d16-109">This method may overlap with `JITCompilation` callbacks such as the [ICorProfilerCallback::JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) method.</span></span> <span data-ttu-id="20d16-110">La enumeración devuelta incluye valores para el campo `COR_PRF_FUNCTION::reJitId`.</span><span class="sxs-lookup"><span data-stu-id="20d16-110">The returned enumeration includes values for the `COR_PRF_FUNCTION::reJitId` field.</span></span> <span data-ttu-id="20d16-111">El método [ICorProfilerInfo3:: EnumJITedFunctions (](icorprofilerinfo3-enumjitedfunctions-method.md) , que este método reemplaza, no enumera los identificadores compilados con JIT, ya que el campo de `COR_PRF_FUNCTION::reJitId` siempre se establece en 0.</span><span class="sxs-lookup"><span data-stu-id="20d16-111">The [ICorProfilerInfo3::EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md) method, which this method replaces, does not enumerate JIT-recompiled IDs, because the `COR_PRF_FUNCTION::reJitId` field is always set to 0.</span></span> <span data-ttu-id="20d16-112">El método `ICorProfilerInfo4::EnumJITedFunctions` enumera los identificadores compilados con JIT, ya que el campo de `COR_PRF_FUNCTION::reJitId` está configurado correctamente.</span><span class="sxs-lookup"><span data-stu-id="20d16-112">The `ICorProfilerInfo4::EnumJITedFunctions` method does enumerate JIT-recompiled IDs, because the `COR_PRF_FUNCTION::reJitId` field is set properly.</span></span> <span data-ttu-id="20d16-113">Tenga en cuenta que el método [ICorProfilerInfo4:: enumjitedfunctions2 (](icorprofilerinfo4-enumjitedfunctions2-method.md) puede desencadenar una recolección de elementos no utilizados, mientras que el [método ICorProfilerInfo3:: EnumJITedFunctions (](icorprofilerinfo3-enumjitedfunctions-method.md) no lo hará.</span><span class="sxs-lookup"><span data-stu-id="20d16-113">Note that the [ICorProfilerInfo4::EnumJITedFunctions2](icorprofilerinfo4-enumjitedfunctions2-method.md) method can trigger a garbage collection, whereas [ICorProfilerInfo3::EnumJITedFunctions method](icorprofilerinfo3-enumjitedfunctions-method.md) will not.</span></span>  <span data-ttu-id="20d16-114">Para obtener más información, vea [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](corprof-e-unsupported-call-sequence-hresult.md).</span><span class="sxs-lookup"><span data-stu-id="20d16-114">For more information, see [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](corprof-e-unsupported-call-sequence-hresult.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20d16-115">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="20d16-115">Requirements</span></span>  
 <span data-ttu-id="20d16-116">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20d16-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20d16-117">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="20d16-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="20d16-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="20d16-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="20d16-119">**.NET Framework versiones:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20d16-119">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20d16-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="20d16-120">See also</span></span>

- [<span data-ttu-id="20d16-121">EnumJITedFunctions (método)</span><span class="sxs-lookup"><span data-stu-id="20d16-121">EnumJITedFunctions Method</span></span>](icorprofilerinfo3-enumjitedfunctions-method.md)
- [<span data-ttu-id="20d16-122">ICorProfilerInfo4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="20d16-122">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
- [<span data-ttu-id="20d16-123">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="20d16-123">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="20d16-124">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="20d16-124">Profiling</span></span>](index.md)
