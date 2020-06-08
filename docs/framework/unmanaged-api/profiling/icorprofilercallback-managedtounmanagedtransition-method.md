---
title: ICorProfilerCallback::ManagedToUnmanagedTransition (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ManagedToUnmanagedTransition
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ManagedToUnmanagedTransition
helpviewer_keywords:
- ManagedToUnmanagedTransition method [.NET Framework profiling]
- ICorProfilerCallback::ManagedToUnmanagedTransition method [.NET Framework profiling]
ms.assetid: ef3cd619-912d-40c5-a449-03ba02a39ee7
topic_type:
- apiref
ms.openlocfilehash: 9b53030fe860e02b0afd0dce3055ac3cf29e3491
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500005"
---
# <a name="icorprofilercallbackmanagedtounmanagedtransition-method"></a><span data-ttu-id="4ddd9-102">ICorProfilerCallback::ManagedToUnmanagedTransition (Método)</span><span class="sxs-lookup"><span data-stu-id="4ddd9-102">ICorProfilerCallback::ManagedToUnmanagedTransition Method</span></span>
<span data-ttu-id="4ddd9-103">Notifica al generador de perfiles que se ha producido una transición de código administrado a código no administrado.</span><span class="sxs-lookup"><span data-stu-id="4ddd9-103">Notifies the profiler that a transition from managed code to unmanaged code has occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ddd9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4ddd9-104">Syntax</span></span>  
  
```cpp  
HRESULT ManagedToUnmanagedTransition(  
    [in] FunctionID functionId,  
    [in] COR_PRF_TRANSITION_REASON reason);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4ddd9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4ddd9-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="4ddd9-106">de IDENTIFICADOR de la función a la que se está llamando.</span><span class="sxs-lookup"><span data-stu-id="4ddd9-106">[in] The ID of the function that is being called.</span></span>  
  
 `reason`  
 <span data-ttu-id="4ddd9-107">de Un valor de la enumeración [COR_PRF_TRANSITION_REASON](cor-prf-transition-reason-enumeration.md) que indica si la transición se produjo debido a una llamada a código no administrado desde código administrado, o debido a una devolución de una función administrada a la que llama un no administrado.</span><span class="sxs-lookup"><span data-stu-id="4ddd9-107">[in] A value of the [COR_PRF_TRANSITION_REASON](cor-prf-transition-reason-enumeration.md) enumeration that indicates whether the transition occurred because of a call into unmanaged code from managed code, or because of a return from a managed function called by an unmanaged one.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4ddd9-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4ddd9-108">Remarks</span></span>  
 <span data-ttu-id="4ddd9-109">Si el valor de `reason` es COR_PRF_TRANSITION_CALL, el identificador de función es el de la función no administrada, que nunca se habrá compilado con el compilador Just-in-Time.</span><span class="sxs-lookup"><span data-stu-id="4ddd9-109">If the value of `reason` is COR_PRF_TRANSITION_CALL, the function ID is that of the unmanaged function, which will never have been compiled using the just-in-time compiler.</span></span> <span data-ttu-id="4ddd9-110">Las funciones no administradas tienen información básica asociada, como un nombre y algunos metadatos.</span><span class="sxs-lookup"><span data-stu-id="4ddd9-110">Unmanaged functions have basic information associated with them, such as a name and some metadata.</span></span> <span data-ttu-id="4ddd9-111">Si se llamó a la función no administrada mediante la invocación de plataforma implícita (PInvoke), el tiempo de ejecución no puede determinar el destino de la llamada y el valor de `functionId` será null.</span><span class="sxs-lookup"><span data-stu-id="4ddd9-111">If the unmanaged function was called by using implicit platform invoke (PInvoke), the runtime cannot determine the destination of the call and the value of `functionId` will be null.</span></span> <span data-ttu-id="4ddd9-112">Para obtener más información sobre PInvoke implícito, vea [usar la interoperabilidad de C++ (implicit PInvoke)](/cpp/dotnet/using-cpp-interop-implicit-pinvoke).</span><span class="sxs-lookup"><span data-stu-id="4ddd9-112">For more information on implicit PInvoke, see [Using C++ Interop (Implicit PInvoke)](/cpp/dotnet/using-cpp-interop-implicit-pinvoke).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ddd9-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4ddd9-113">Requirements</span></span>  
 <span data-ttu-id="4ddd9-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4ddd9-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ddd9-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4ddd9-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4ddd9-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4ddd9-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4ddd9-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ddd9-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ddd9-118">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="4ddd9-118">See also</span></span>

- [<span data-ttu-id="4ddd9-119">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4ddd9-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="4ddd9-120">Método UnmanagedToManagedTransition</span><span class="sxs-lookup"><span data-stu-id="4ddd9-120">UnmanagedToManagedTransition Method</span></span>](icorprofilercallback-unmanagedtomanagedtransition-method.md)
- [<span data-ttu-id="4ddd9-121">Usar PInvoke explícito en C++ (atributo DllImport)</span><span class="sxs-lookup"><span data-stu-id="4ddd9-121">Using Explicit PInvoke in C++ (DllImport Attribute)</span></span>](/cpp/dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute)
