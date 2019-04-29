---
title: ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 (Método)
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b9f95a404ce7124a76ee527cdc70ccccf103838b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763183"
---
# <a name="icorprofilerinfo2setenterleavefunctionhooks2-method"></a><span data-ttu-id="218e2-102">ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 (Método)</span><span class="sxs-lookup"><span data-stu-id="218e2-102">ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 Method</span></span>
<span data-ttu-id="218e2-103">Especifica las funciones implementadas por el generador de perfiles que se llamará en las versiones actualizadas de los "enter", "salir" y "llamada de cola" enlaces de funciones administradas.</span><span class="sxs-lookup"><span data-stu-id="218e2-103">Specifies profiler-implemented functions to be called on the updated versions of the "enter", "leave", and "tailcall" hooks of managed functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="218e2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="218e2-104">Syntax</span></span>  
  
```  
HRESULT SetEnterLeaveFunctionHooks2(  
    [in] FunctionEnter2    *pFuncEnter,  
    [in] FunctionLeave2    *pFuncLeave,  
    [in] FunctionTailcall2 *pFuncTailcall);  
```  
  
## <a name="parameters"></a><span data-ttu-id="218e2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="218e2-105">Parameters</span></span>  
 `pFuncEnter`  
 <span data-ttu-id="218e2-106">[in] Un puntero a la implementación que se usará como el [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="218e2-106">[in] A pointer to the implementation to be used as the [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) callback.</span></span>  
  
 `pFuncLeave`  
 <span data-ttu-id="218e2-107">[in] Un puntero a la implementación que se usará como el [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="218e2-107">[in] A pointer to the implementation to be used as the [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) callback.</span></span>  
  
 `pFuncTailcall`  
 <span data-ttu-id="218e2-108">[in] Un puntero a la implementación que se usará como el [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="218e2-108">[in] A pointer to the implementation to be used as the [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="218e2-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="218e2-109">Remarks</span></span>  
 <span data-ttu-id="218e2-110">El `SetEnterLeaveFunctionHooks2` método es similar a la [SetEnterLeaveFunctionHooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="218e2-110">The `SetEnterLeaveFunctionHooks2` method is similar to the [ICorProfilerInfo::SetEnterLeaveFunctionHooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md) method.</span></span> <span data-ttu-id="218e2-111">Utilice el primero para especificar las funciones que se usará como las versiones más recientes de las devoluciones de llamada ENTRAR/leave/llamada de cola y este último para especificar las funciones que se usará como las versiones anteriores de las devoluciones de llamada ENTRAR/leave/llamada de cola.</span><span class="sxs-lookup"><span data-stu-id="218e2-111">Use the former to specify functions to be used as the newer versions of the enter/leave/tailcall callbacks, and the latter to specify functions to be used as the older versions of the enter/leave/tailcall callbacks.</span></span>  
  
 <span data-ttu-id="218e2-112">Solo un conjunto de devoluciones de llamada puede ser activo a la vez.</span><span class="sxs-lookup"><span data-stu-id="218e2-112">Only one set of callbacks may be active at a time.</span></span> <span data-ttu-id="218e2-113">Por lo tanto, si un generador de perfiles llama a ambos `ICorProfilerInfo::SetEnterLeaveFunctionHooks` y `SetEnterLeaveFunctionHooks2`, `SetEnterLeaveFunctionHooks2` se utiliza.</span><span class="sxs-lookup"><span data-stu-id="218e2-113">Thus, if a profiler calls both `ICorProfilerInfo::SetEnterLeaveFunctionHooks` and `SetEnterLeaveFunctionHooks2`, `SetEnterLeaveFunctionHooks2` is used.</span></span>  
  
 <span data-ttu-id="218e2-114">El `SetEnterLeaveFunctionHooks2` método puede llamarse solo desde el generador de perfiles [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="218e2-114">The `SetEnterLeaveFunctionHooks2` method may be called only from the profiler's [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="218e2-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="218e2-115">Requirements</span></span>  
 <span data-ttu-id="218e2-116">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="218e2-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="218e2-117">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="218e2-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="218e2-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="218e2-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="218e2-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="218e2-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="218e2-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="218e2-120">See also</span></span>

- [<span data-ttu-id="218e2-121">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="218e2-121">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="218e2-122">ICorProfilerInfo2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="218e2-122">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
