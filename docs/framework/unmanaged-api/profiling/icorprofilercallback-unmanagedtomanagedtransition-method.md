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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 421b729468cad365c48bccdae3b31132dd1ed894
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54496028"
---
# <a name="icorprofilercallbackunmanagedtomanagedtransition-method"></a><span data-ttu-id="7d653-102">ICorProfilerCallback::UnmanagedToManagedTransition (Método)</span><span class="sxs-lookup"><span data-stu-id="7d653-102">ICorProfilerCallback::UnmanagedToManagedTransition Method</span></span>
<span data-ttu-id="7d653-103">Notifica al generador de perfiles que se ha producido una transición desde código no administrado a código administrado.</span><span class="sxs-lookup"><span data-stu-id="7d653-103">Notifies the profiler that a transition from unmanaged code to managed code has occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d653-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7d653-104">Syntax</span></span>  
  
```  
HRESULT UnmanagedToManagedTransition(  
    [in] FunctionID functionId,  
    [in] COR_PRF_TRANSITION_REASON reason);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7d653-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7d653-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="7d653-106">[in] El identificador de la función que se llama.</span><span class="sxs-lookup"><span data-stu-id="7d653-106">[in] The ID of the function that is being called.</span></span>  
  
 `reason`  
 <span data-ttu-id="7d653-107">[in] Un valor de la [COR_PRF_TRANSITION_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md) enumeración que indica si la transición se produjo debido a una llamada a código administrado desde código no administrado, o debido a una devolución de una función no administrada que se llama a uno administrada.</span><span class="sxs-lookup"><span data-stu-id="7d653-107">[in] A value of the [COR_PRF_TRANSITION_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md) enumeration that indicates whether the transition occurred because of a call into managed code from unmanaged code, or because of a return from an unmanaged function called by a managed one.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7d653-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7d653-108">Remarks</span></span>  
 <span data-ttu-id="7d653-109">Si el valor de `reason` es COR_PRF_TRANSITION_RETURN y `functionId` es no nulo, la función ID es el de la función no administrada y nunca habrá sido compilado mediante el compilador just-in-time (JIT).</span><span class="sxs-lookup"><span data-stu-id="7d653-109">If the value of `reason` is COR_PRF_TRANSITION_RETURN and `functionId` is not null, the function ID is that of the unmanaged function, and will never have been compiled using the just-in-time (JIT) compiler.</span></span> <span data-ttu-id="7d653-110">Funciones no administradas tengan cierta información básica asociado con ellos, como el nombre y algunos metadatos.</span><span class="sxs-lookup"><span data-stu-id="7d653-110">Unmanaged functions have some basic information associated with them, such as a name and some metadata.</span></span>  
  
 <span data-ttu-id="7d653-111">Si el valor de `reason` es COR_PRF_TRANSITION_CALL, puede que sea posible que la función llamada (es decir, la función administrada) no se ha recibido la compilación JIT.</span><span class="sxs-lookup"><span data-stu-id="7d653-111">If the value of `reason` is COR_PRF_TRANSITION_CALL, it may be possible that the called function (that is, the managed function) has not yet been JIT-compiled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d653-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7d653-112">Requirements</span></span>  
 <span data-ttu-id="7d653-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d653-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d653-114">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7d653-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7d653-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7d653-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7d653-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d653-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d653-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="7d653-117">See also</span></span>
- [<span data-ttu-id="7d653-118">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7d653-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="7d653-119">ManagedToUnmanagedTransition (método)</span><span class="sxs-lookup"><span data-stu-id="7d653-119">ManagedToUnmanagedTransition Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md)
- [<span data-ttu-id="7d653-120">Usar un elemento PInvoke explícito en C++ (Atributo DllImport)</span><span class="sxs-lookup"><span data-stu-id="7d653-120">Using Explicit PInvoke in C++ (DllImport Attribute)</span></span>](/cpp/dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute)
- [<span data-ttu-id="7d653-121">Usar la interoperabilidad de C++ (PInvoke implícito)</span><span class="sxs-lookup"><span data-stu-id="7d653-121">Using C++ Interop (Implicit PInvoke)</span></span>](/cpp/dotnet/using-cpp-interop-implicit-pinvoke)
