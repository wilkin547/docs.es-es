---
title: ICorProfilerCallback4::GetReJITParameters (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.GetReJITParameters
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::GetReJITParameters
helpviewer_keywords:
- ICorProfilerCallback4::GetReJITParameters method [.NET Framework profiling]
- GetReJITParameters method, ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 0e9bfe07-9f20-498c-b568-9017c8f6056c
topic_type:
- apiref
ms.openlocfilehash: d81d7275d197de1dfc99b135377459f509c2651f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439439"
---
# <a name="icorprofilercallback4getrejitparameters-method"></a><span data-ttu-id="380de-102">ICorProfilerCallback4::GetReJITParameters (Método)</span><span class="sxs-lookup"><span data-stu-id="380de-102">ICorProfilerCallback4::GetReJITParameters Method</span></span>
<span data-ttu-id="380de-103">Allows the code profiler to set alternate code generation flags for a new recompiled method body.</span><span class="sxs-lookup"><span data-stu-id="380de-103">Allows the code profiler to set alternate code generation flags for a new recompiled method body.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="380de-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="380de-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReJITParameters(     [in] ModuleID moduleId,     [in] mdMethodDef methodId,     [in] ICorProfilerFunctionControl *pFunctionControl);  
```  
  
## <a name="parameters"></a><span data-ttu-id="380de-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="380de-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="380de-106">[in] The module that contains the method for which the CLR needs JIT recompilation parameters.</span><span class="sxs-lookup"><span data-stu-id="380de-106">[in] The module that contains the method for which the CLR needs JIT recompilation parameters.</span></span>  
  
 `methodId`  
 <span data-ttu-id="380de-107">[in] The `MethodDef` of the method for which the CLR needs JIT recompilation parameters.</span><span class="sxs-lookup"><span data-stu-id="380de-107">[in] The `MethodDef` of the method for which the CLR needs JIT recompilation parameters.</span></span>  
  
 `pFunctionControl`  
 <span data-ttu-id="380de-108">[in] A pointer to an [ICorProfilerFunctionControl](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md) interface that the profiler can use to provide JIT recompilation information for the method being recompiled.</span><span class="sxs-lookup"><span data-stu-id="380de-108">[in] A pointer to an [ICorProfilerFunctionControl](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md) interface that the profiler can use to provide JIT recompilation information for the method being recompiled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="380de-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="380de-109">Remarks</span></span>  
 <span data-ttu-id="380de-110">The CLR issues a `GetReJITParameters` callback so that the profiler can specify the parameters for recompiling a given method.</span><span class="sxs-lookup"><span data-stu-id="380de-110">The CLR issues a `GetReJITParameters` callback so that the profiler can specify the parameters for recompiling a given method.</span></span> <span data-ttu-id="380de-111">The `GetReJITParameters` callback is issued only once per function; the parameters supplied by the profiler apply to all instances of that function.</span><span class="sxs-lookup"><span data-stu-id="380de-111">The `GetReJITParameters` callback is issued only once per function; the parameters supplied by the profiler apply to all instances of that function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="380de-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="380de-112">Requirements</span></span>  
 <span data-ttu-id="380de-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="380de-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="380de-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="380de-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="380de-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="380de-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="380de-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="380de-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="380de-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="380de-117">See also</span></span>

- [<span data-ttu-id="380de-118">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="380de-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="380de-119">ICorProfilerCallback4 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="380de-119">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
- [<span data-ttu-id="380de-120">JITCompilationStarted (método)</span><span class="sxs-lookup"><span data-stu-id="380de-120">JITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)
- [<span data-ttu-id="380de-121">ReJITCompilationStarted (método)</span><span class="sxs-lookup"><span data-stu-id="380de-121">ReJITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationstarted-method.md)
