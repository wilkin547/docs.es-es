---
title: ICorProfilerCallback::UnmanagedToManagedTransition (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.UnmanagedToManagedTransition
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::UnmanagedToManagedTransition
helpviewer_keywords:
- ICorProfilerCallback::UnmanagedToManagedTransition method [.NET Framework profiling]
- UnmanagedToManagedTransition method [.NET Framework profiling]
ms.assetid: ade2cc01-9b81-4e09-a5f9-b3b9dda27e96
topic_type:
- apiref
ms.openlocfilehash: c381d4a85a1e836f1972060c8182dd698bb27550
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76870557"
---
# <a name="icorprofilercallbackunmanagedtomanagedtransition-method"></a><span data-ttu-id="69cf5-102">ICorProfilerCallback::UnmanagedToManagedTransition (Método)</span><span class="sxs-lookup"><span data-stu-id="69cf5-102">ICorProfilerCallback::UnmanagedToManagedTransition Method</span></span>
<span data-ttu-id="69cf5-103">Notifica al generador de perfiles que se ha producido una transición de código no administrado a código administrado.</span><span class="sxs-lookup"><span data-stu-id="69cf5-103">Notifies the profiler that a transition from unmanaged code to managed code has occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69cf5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="69cf5-104">Syntax</span></span>  
  
```cpp  
HRESULT UnmanagedToManagedTransition(  
    [in] FunctionID functionId,  
    [in] COR_PRF_TRANSITION_REASON reason);  
```  
  
## <a name="parameters"></a><span data-ttu-id="69cf5-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="69cf5-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="69cf5-106">de IDENTIFICADOR de la función a la que se está llamando.</span><span class="sxs-lookup"><span data-stu-id="69cf5-106">[in] The ID of the function that is being called.</span></span>  
  
 `reason`  
 <span data-ttu-id="69cf5-107">de Un valor de la enumeración [COR_PRF_TRANSITION_REASON](cor-prf-transition-reason-enumeration.md) que indica si la transición se produjo debido a una llamada a código administrado desde código no administrado o debido a una devolución de una función no administrada a la que llama una administrada.</span><span class="sxs-lookup"><span data-stu-id="69cf5-107">[in] A value of the [COR_PRF_TRANSITION_REASON](cor-prf-transition-reason-enumeration.md) enumeration that indicates whether the transition occurred because of a call into managed code from unmanaged code, or because of a return from an unmanaged function called by a managed one.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="69cf5-108">Notas</span><span class="sxs-lookup"><span data-stu-id="69cf5-108">Remarks</span></span>  
 <span data-ttu-id="69cf5-109">Si el valor de `reason` es COR_PRF_TRANSITION_RETURN y `functionId` no es null, el identificador de función es el de la función no administrada y nunca se habrá compilado con el compilador Just-in-Time (JIT).</span><span class="sxs-lookup"><span data-stu-id="69cf5-109">If the value of `reason` is COR_PRF_TRANSITION_RETURN and `functionId` is not null, the function ID is that of the unmanaged function, and will never have been compiled using the just-in-time (JIT) compiler.</span></span> <span data-ttu-id="69cf5-110">Las funciones no administradas tienen asociada cierta información básica, como un nombre y algunos metadatos.</span><span class="sxs-lookup"><span data-stu-id="69cf5-110">Unmanaged functions have some basic information associated with them, such as a name and some metadata.</span></span>  
  
 <span data-ttu-id="69cf5-111">Si el valor de `reason` es COR_PRF_TRANSITION_CALL, es posible que la función a la que se llama (es decir, la función administrada) todavía no se haya compilado JIT.</span><span class="sxs-lookup"><span data-stu-id="69cf5-111">If the value of `reason` is COR_PRF_TRANSITION_CALL, it may be possible that the called function (that is, the managed function) has not yet been JIT-compiled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69cf5-112">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="69cf5-112">Requirements</span></span>  
 <span data-ttu-id="69cf5-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="69cf5-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69cf5-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="69cf5-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="69cf5-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="69cf5-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="69cf5-116">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69cf5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69cf5-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="69cf5-117">See also</span></span>

- [<span data-ttu-id="69cf5-118">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="69cf5-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="69cf5-119">ManagedToUnmanagedTransition (método)</span><span class="sxs-lookup"><span data-stu-id="69cf5-119">ManagedToUnmanagedTransition Method</span></span>](icorprofilercallback-managedtounmanagedtransition-method.md)
- [<span data-ttu-id="69cf5-120">Usar un elemento PInvoke explícito en C++ (Atributo DllImport)</span><span class="sxs-lookup"><span data-stu-id="69cf5-120">Using Explicit PInvoke in C++ (DllImport Attribute)</span></span>](/cpp/dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute)
- [<span data-ttu-id="69cf5-121">Usar la interoperabilidad de C++ (PInvoke implícito)</span><span class="sxs-lookup"><span data-stu-id="69cf5-121">Using C++ Interop (Implicit PInvoke)</span></span>](/cpp/dotnet/using-cpp-interop-implicit-pinvoke)
