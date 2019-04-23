---
title: ICorProfilerInfo::SetEnterLeaveFunctionHooks (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetEnterLeaveFunctionHooks
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetEnterLeaveFunctionHooks
helpviewer_keywords:
- SetEnterLeaveFunctionHooks method [.NET Framework profiling]
- ICorProfilerInfo::SetEnterLeaveFunctionHooks method [.NET Framework profiling]
ms.assetid: 72399636-c219-4ffd-8ac8-39432c9d4641
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a2d45e98f3e7b71375b14c43c4bff4929bc79494
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59142537"
---
# <a name="icorprofilerinfosetenterleavefunctionhooks-method"></a><span data-ttu-id="dbbcd-102">ICorProfilerInfo::SetEnterLeaveFunctionHooks (Método)</span><span class="sxs-lookup"><span data-stu-id="dbbcd-102">ICorProfilerInfo::SetEnterLeaveFunctionHooks Method</span></span>
<span data-ttu-id="dbbcd-103">Especifica las funciones implementadas por el generador de perfiles que se llamará en "enter", "salir" y "llamada de cola" enlaces de funciones administradas.</span><span class="sxs-lookup"><span data-stu-id="dbbcd-103">Specifies profiler-implemented functions to be called on "enter", "leave", and "tailcall" hooks of managed functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbbcd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dbbcd-104">Syntax</span></span>  
  
```  
HRESULT SetEnterLeaveFunctionHooks(  
    [in] FunctionEnter    *pFuncEnter,  
    [in] FunctionLeave    *pFuncLeave,  
    [in] FunctionTailcall *pFuncTailcall);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dbbcd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dbbcd-105">Parameters</span></span>  
 `pFuncEnter`  
 <span data-ttu-id="dbbcd-106">[in] Un puntero a la implementación que se usará como el [FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md) devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="dbbcd-106">[in] A pointer to the implementation to be used as the [FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md) callback.</span></span>  
  
 `pFuncLeave`  
 <span data-ttu-id="dbbcd-107">[in] Un puntero a la implementación que se usará como el [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="dbbcd-107">[in] A pointer to the implementation to be used as the [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) callback.</span></span>  
  
 `pFuncTailcall`  
 <span data-ttu-id="dbbcd-108">[in] Un puntero a la implementación que se usará como el [FunctionTailcall](../../../../docs/framework/unmanaged-api/profiling/functiontailcall-function.md) devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="dbbcd-108">[in] A pointer to the implementation to be used as the [FunctionTailcall](../../../../docs/framework/unmanaged-api/profiling/functiontailcall-function.md) callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dbbcd-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dbbcd-109">Remarks</span></span>  
 <span data-ttu-id="dbbcd-110">En la versión 1.0 de .NET Framework, cada puntero de función puede ser null para deshabilitar esa devolución de llamada correspondiente.</span><span class="sxs-lookup"><span data-stu-id="dbbcd-110">In the .NET Framework version 1.0, each function pointer can be null to disable that corresponding callback.</span></span>  
  
 <span data-ttu-id="dbbcd-111">Puede activarse únicamente un conjunto de devoluciones de llamada a la vez.</span><span class="sxs-lookup"><span data-stu-id="dbbcd-111">Only one set of callbacks can be active at a time.</span></span> <span data-ttu-id="dbbcd-112">Por lo tanto, si un generador de perfiles llama a ambos `SetEnterLeaveFunctionHooks` y [ICorProfilerInfo2:: Setenterleavefunctionhooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md), a continuación, `SetEnterLeaveFunctionHooks2` tiene prioridad.</span><span class="sxs-lookup"><span data-stu-id="dbbcd-112">Thus, if a profiler calls both `SetEnterLeaveFunctionHooks` and [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md), then `SetEnterLeaveFunctionHooks2` takes precedence.</span></span>  
  
 <span data-ttu-id="dbbcd-113">El `SetEnterLeaveFunctionHooks` método se puede llamar solo desde el generador de perfiles [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="dbbcd-113">The `SetEnterLeaveFunctionHooks` method can be called only from the profiler's [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dbbcd-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dbbcd-114">Requirements</span></span>  
 <span data-ttu-id="dbbcd-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dbbcd-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dbbcd-116">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="dbbcd-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="dbbcd-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dbbcd-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dbbcd-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dbbcd-118">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbbcd-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="dbbcd-119">See also</span></span>

- [<span data-ttu-id="dbbcd-120">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="dbbcd-120">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
