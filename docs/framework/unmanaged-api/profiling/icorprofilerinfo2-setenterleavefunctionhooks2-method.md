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
ms.openlocfilehash: f71d0b5c77d4a514001bcbe6904ed912be388d18
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95681553"
---
# <a name="icorprofilerinfo2setenterleavefunctionhooks2-method"></a><span data-ttu-id="91557-102">ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 (Método)</span><span class="sxs-lookup"><span data-stu-id="91557-102">ICorProfilerInfo2::SetEnterLeaveFunctionHooks2 Method</span></span>

<span data-ttu-id="91557-103">Especifica las funciones implementadas por el generador de perfiles a las que se va a llamar en las versiones actualizadas de los enlaces "Enter", "Leave" y "llamada" de las funciones administradas.</span><span class="sxs-lookup"><span data-stu-id="91557-103">Specifies profiler-implemented functions to be called on the updated versions of the "enter", "leave", and "tailcall" hooks of managed functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91557-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="91557-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEnterLeaveFunctionHooks2(  
    [in] FunctionEnter2    *pFuncEnter,  
    [in] FunctionLeave2    *pFuncLeave,  
    [in] FunctionTailcall2 *pFuncTailcall);  
```  
  
## <a name="parameters"></a><span data-ttu-id="91557-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="91557-105">Parameters</span></span>  

 `pFuncEnter`  
 <span data-ttu-id="91557-106">de Puntero a la implementación de que se va a usar como devolución de llamada de [FunctionEnter2](functionenter2-function.md) .</span><span class="sxs-lookup"><span data-stu-id="91557-106">[in] A pointer to the implementation to be used as the [FunctionEnter2](functionenter2-function.md) callback.</span></span>  
  
 `pFuncLeave`  
 <span data-ttu-id="91557-107">de Un puntero a la implementación de que se va a usar como devolución de llamada de [FunctionLeave2](functionleave2-function.md) .</span><span class="sxs-lookup"><span data-stu-id="91557-107">[in] A pointer to the implementation to be used as the [FunctionLeave2](functionleave2-function.md) callback.</span></span>  
  
 `pFuncTailcall`  
 <span data-ttu-id="91557-108">de Puntero a la implementación de que se va a usar como devolución de llamada de [FunctionTailcall2](functiontailcall2-function.md) .</span><span class="sxs-lookup"><span data-stu-id="91557-108">[in] A pointer to the implementation to be used as the [FunctionTailcall2](functiontailcall2-function.md) callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="91557-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="91557-109">Remarks</span></span>  

 <span data-ttu-id="91557-110">El `SetEnterLeaveFunctionHooks2` método es similar al método [ICorProfilerInfo:: SetEnterLeaveFunctionHooks (](icorprofilerinfo-setenterleavefunctionhooks-method.md) .</span><span class="sxs-lookup"><span data-stu-id="91557-110">The `SetEnterLeaveFunctionHooks2` method is similar to the [ICorProfilerInfo::SetEnterLeaveFunctionHooks](icorprofilerinfo-setenterleavefunctionhooks-method.md) method.</span></span> <span data-ttu-id="91557-111">Use el primero para especificar las funciones que se van a usar como las versiones más recientes de las devoluciones de llamada Enter/Leave/llamada y la última para especificar las funciones que se van a usar como versiones anteriores de las devoluciones de llamada Enter/Leave/llamada.</span><span class="sxs-lookup"><span data-stu-id="91557-111">Use the former to specify functions to be used as the newer versions of the enter/leave/tailcall callbacks, and the latter to specify functions to be used as the older versions of the enter/leave/tailcall callbacks.</span></span>  
  
 <span data-ttu-id="91557-112">Solo un conjunto de devoluciones de llamada puede estar activo a la vez.</span><span class="sxs-lookup"><span data-stu-id="91557-112">Only one set of callbacks may be active at a time.</span></span> <span data-ttu-id="91557-113">Por lo tanto, si un generador de perfiles llama a `ICorProfilerInfo::SetEnterLeaveFunctionHooks` y `SetEnterLeaveFunctionHooks2` , `SetEnterLeaveFunctionHooks2` se utiliza.</span><span class="sxs-lookup"><span data-stu-id="91557-113">Thus, if a profiler calls both `ICorProfilerInfo::SetEnterLeaveFunctionHooks` and `SetEnterLeaveFunctionHooks2`, `SetEnterLeaveFunctionHooks2` is used.</span></span>  
  
 <span data-ttu-id="91557-114">`SetEnterLeaveFunctionHooks2`Solo se puede llamar al método desde la devolución de llamada [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="91557-114">The `SetEnterLeaveFunctionHooks2` method may be called only from the profiler's [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91557-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="91557-115">Requirements</span></span>  

 <span data-ttu-id="91557-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="91557-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91557-117">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="91557-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="91557-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="91557-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="91557-119">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91557-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91557-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="91557-120">See also</span></span>

- [<span data-ttu-id="91557-121">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="91557-121">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="91557-122">ICorProfilerInfo2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="91557-122">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
