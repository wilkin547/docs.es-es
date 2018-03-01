---
title: "ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerInfo2.SetEnterLeaveFunctionHooks2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::SetEnterLeaveFunctionHooks2
helpviewer_keywords:
- ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 method [.NET Framework profiling]
- SetEnterLeaveFunctionHooks2 method [.NET Framework profiling]
ms.assetid: 3c26b3e7-f72b-48a5-bf8c-edc122523a4b
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0c460cfd24a83ca2a6c75e061b7a797c8f455bc1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo2setenterleavefunctionhooks2-method"></a><span data-ttu-id="f5edf-102">ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 (Método)</span><span class="sxs-lookup"><span data-stu-id="f5edf-102">ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 Method</span></span>
<span data-ttu-id="f5edf-103">Especifica las funciones implementadas por el generador de perfiles que se llame en las versiones actualizadas de los "Entrar", "leave" y "tailcall" enlaces de funciones administradas.</span><span class="sxs-lookup"><span data-stu-id="f5edf-103">Specifies profiler-implemented functions to be called on the updated versions of the "enter", "leave", and "tailcall" hooks of managed functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5edf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f5edf-104">Syntax</span></span>  
  
```  
HRESULT SetEnterLeaveFunctionHooks2(  
    [in] FunctionEnter2    *pFuncEnter,  
    [in] FunctionLeave2    *pFuncLeave,  
    [in] FunctionTailcall2 *pFuncTailcall);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f5edf-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f5edf-105">Parameters</span></span>  
 `pFuncEnter`  
 <span data-ttu-id="f5edf-106">[in] Un puntero a la implementación que se usará como el [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="f5edf-106">[in] A pointer to the implementation to be used as the [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) callback.</span></span>  
  
 `pFuncLeave`  
 <span data-ttu-id="f5edf-107">[in] Un puntero a la implementación que se usará como el [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="f5edf-107">[in] A pointer to the implementation to be used as the [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) callback.</span></span>  
  
 `pFuncTailcall`  
 <span data-ttu-id="f5edf-108">[in] Un puntero a la implementación que se usará como el [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="f5edf-108">[in] A pointer to the implementation to be used as the [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f5edf-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f5edf-109">Remarks</span></span>  
 <span data-ttu-id="f5edf-110">El `SetEnterLeaveFunctionHooks2` método es similar a la [ICorProfilerInfo:: SetEnterLeaveFunctionHooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="f5edf-110">The `SetEnterLeaveFunctionHooks2` method is similar to the [ICorProfilerInfo::SetEnterLeaveFunctionHooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md) method.</span></span> <span data-ttu-id="f5edf-111">Utilice el primero para especificar las funciones que se usará como las versiones más recientes de las devoluciones de llamada ENTRAR/leave/tailcall y el segundo para especificar las funciones que se usará como las versiones anteriores de las devoluciones de llamada ENTRAR/leave/tailcall.</span><span class="sxs-lookup"><span data-stu-id="f5edf-111">Use the former to specify functions to be used as the newer versions of the enter/leave/tailcall callbacks, and the latter to specify functions to be used as the older versions of the enter/leave/tailcall callbacks.</span></span>  
  
 <span data-ttu-id="f5edf-112">Un conjunto de devoluciones de llamada no se activa cada vez.</span><span class="sxs-lookup"><span data-stu-id="f5edf-112">Only one set of callbacks may be active at a time.</span></span> <span data-ttu-id="f5edf-113">Por lo tanto, si llama a un generador de perfiles las `ICorProfilerInfo::SetEnterLeaveFunctionHooks` y `SetEnterLeaveFunctionHooks2`, `SetEnterLeaveFunctionHooks2` se utiliza.</span><span class="sxs-lookup"><span data-stu-id="f5edf-113">Thus, if a profiler calls both `ICorProfilerInfo::SetEnterLeaveFunctionHooks` and `SetEnterLeaveFunctionHooks2`, `SetEnterLeaveFunctionHooks2` is used.</span></span>  
  
 <span data-ttu-id="f5edf-114">El `SetEnterLeaveFunctionHooks2` solo desde el generador de perfiles puede llamar al método [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="f5edf-114">The `SetEnterLeaveFunctionHooks2` method may be called only from the profiler's [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5edf-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f5edf-115">Requirements</span></span>  
 <span data-ttu-id="f5edf-116">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5edf-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5edf-117">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f5edf-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f5edf-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f5edf-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f5edf-119">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5edf-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5edf-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="f5edf-120">See Also</span></span>  
 [<span data-ttu-id="f5edf-121">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f5edf-121">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="f5edf-122">ICorProfilerInfo2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f5edf-122">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
