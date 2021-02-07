---
description: 'Más información sobre: ICorProfilerInfo4:: Enumjitedfunctions2 ((método)'
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
ms.openlocfilehash: 3740236cfe2bc7ecc6cd3bbeb3345c7510dd159f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99686952"
---
# <a name="icorprofilerinfo4enumjitedfunctions2-method"></a><span data-ttu-id="cf0f8-103">ICorProfilerInfo4::EnumJITedFunctions2 (Método)</span><span class="sxs-lookup"><span data-stu-id="cf0f8-103">ICorProfilerInfo4::EnumJITedFunctions2 Method</span></span>

<span data-ttu-id="cf0f8-104">Devuelve un enumerador para todas las funciones compiladas previamente y compiladas con JIT.</span><span class="sxs-lookup"><span data-stu-id="cf0f8-104">Returns an enumerator for all functions that were previously JIT-compiled and JIT-recompiled.</span></span> <span data-ttu-id="cf0f8-105">Este método reemplaza el método [ICorProfilerInfo3:: EnumJITedFunctions (](icorprofilerinfo3-enumjitedfunctions-method.md) , que no enumera los identificadores de recompilación JIT.</span><span class="sxs-lookup"><span data-stu-id="cf0f8-105">This method replaces the [ICorProfilerInfo3::EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md) method, which does not enumerate JIT-recompiled IDs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf0f8-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cf0f8-106">Syntax</span></span>  
  
```cpp  
HRESULT EnumJITedFunctions([out] ICorProfilerFunctionEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf0f8-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cf0f8-107">Parameters</span></span>  

 `ppEnum`  
 <span data-ttu-id="cf0f8-108">enuncia Puntero al enumerador [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="cf0f8-108">[out] A pointer to the [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) enumerator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf0f8-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="cf0f8-109">Remarks</span></span>  

 <span data-ttu-id="cf0f8-110">Este método se puede superponer con `JITCompilation` devoluciones de llamada como el método [ICorProfilerCallback:: JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) .</span><span class="sxs-lookup"><span data-stu-id="cf0f8-110">This method may overlap with `JITCompilation` callbacks such as the [ICorProfilerCallback::JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) method.</span></span> <span data-ttu-id="cf0f8-111">La enumeración devuelta incluye valores para el `COR_PRF_FUNCTION::reJitId` campo.</span><span class="sxs-lookup"><span data-stu-id="cf0f8-111">The returned enumeration includes values for the `COR_PRF_FUNCTION::reJitId` field.</span></span> <span data-ttu-id="cf0f8-112">El método [ICorProfilerInfo3:: EnumJITedFunctions (](icorprofilerinfo3-enumjitedfunctions-method.md) , que este método reemplaza, no enumera los identificadores compilados con JIT, ya que el `COR_PRF_FUNCTION::reJitId` campo siempre se establece en 0.</span><span class="sxs-lookup"><span data-stu-id="cf0f8-112">The [ICorProfilerInfo3::EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md) method, which this method replaces, does not enumerate JIT-recompiled IDs, because the `COR_PRF_FUNCTION::reJitId` field is always set to 0.</span></span> <span data-ttu-id="cf0f8-113">El `ICorProfilerInfo4::EnumJITedFunctions` método enumera los identificadores de recompilación JIT, ya que el `COR_PRF_FUNCTION::reJitId` campo se ha establecido correctamente.</span><span class="sxs-lookup"><span data-stu-id="cf0f8-113">The `ICorProfilerInfo4::EnumJITedFunctions` method does enumerate JIT-recompiled IDs, because the `COR_PRF_FUNCTION::reJitId` field is set properly.</span></span> <span data-ttu-id="cf0f8-114">Tenga en cuenta que el método [ICorProfilerInfo4:: enumjitedfunctions2 (](icorprofilerinfo4-enumjitedfunctions2-method.md) puede desencadenar una recolección de elementos no utilizados, mientras que el [método ICorProfilerInfo3:: EnumJITedFunctions (](icorprofilerinfo3-enumjitedfunctions-method.md) no lo hará.</span><span class="sxs-lookup"><span data-stu-id="cf0f8-114">Note that the [ICorProfilerInfo4::EnumJITedFunctions2](icorprofilerinfo4-enumjitedfunctions2-method.md) method can trigger a garbage collection, whereas [ICorProfilerInfo3::EnumJITedFunctions method](icorprofilerinfo3-enumjitedfunctions-method.md) will not.</span></span>  <span data-ttu-id="cf0f8-115">Para obtener más información, vea [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](corprof-e-unsupported-call-sequence-hresult.md).</span><span class="sxs-lookup"><span data-stu-id="cf0f8-115">For more information, see [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](corprof-e-unsupported-call-sequence-hresult.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf0f8-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cf0f8-116">Requirements</span></span>  

 <span data-ttu-id="cf0f8-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf0f8-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf0f8-118">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cf0f8-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cf0f8-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cf0f8-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cf0f8-120">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf0f8-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf0f8-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="cf0f8-121">See also</span></span>

- [<span data-ttu-id="cf0f8-122">Método EnumJITedFunctions</span><span class="sxs-lookup"><span data-stu-id="cf0f8-122">EnumJITedFunctions Method</span></span>](icorprofilerinfo3-enumjitedfunctions-method.md)
- [<span data-ttu-id="cf0f8-123">ICorProfilerInfo4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cf0f8-123">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
- [<span data-ttu-id="cf0f8-124">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="cf0f8-124">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="cf0f8-125">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="cf0f8-125">Profiling</span></span>](index.md)
