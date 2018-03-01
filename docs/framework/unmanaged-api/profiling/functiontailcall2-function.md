---
title: "FunctionTailcall2 (Función)"
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
- FunctionTailcall2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionTailcall2
helpviewer_keywords:
- FunctionTailcall2 function [.NET Framework profiling]
ms.assetid: 249f9892-b5a9-41e1-b329-28a925904df6
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a9d6ccb08bc09bea2ec9e9a49333c92da8cb5695
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="functiontailcall2-function"></a><span data-ttu-id="ab387-102">FunctionTailcall2 (Función)</span><span class="sxs-lookup"><span data-stu-id="ab387-102">FunctionTailcall2 Function</span></span>
<span data-ttu-id="ab387-103">Notifica al generador de perfiles que la función en ejecución está a punto de realizar una llamada de cola a otra función y proporciona información sobre el marco de pila.</span><span class="sxs-lookup"><span data-stu-id="ab387-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function and provides information about the stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab387-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ab387-104">Syntax</span></span>  
  
```  
void __stdcall FunctionTailcall2 (  
    [in] FunctionID         funcId,   
    [in] UINT_PTR           clientData,   
    [in] COR_PRF_FRAME_INFO func  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ab387-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ab387-105">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="ab387-106">[in] El identificador de la función en ejecución que se va a realizar una cola llamada.</span><span class="sxs-lookup"><span data-stu-id="ab387-106">[in] The identifier of the currently executing function that is about to make a tail call.</span></span>  
  
 `clientData`  
 <span data-ttu-id="ab387-107">[in] El identificador de la función reasignada, que el generador de perfiles especificó previamente a través de [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md), de la función en ejecución que se va a realizar una cola llamada.</span><span class="sxs-lookup"><span data-stu-id="ab387-107">[in] The remapped function identifier, which the profiler previously specified via [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md), of the currently executing function that is about to make a tail call.</span></span>  
  
 `func`  
 <span data-ttu-id="ab387-108">[in] Un `COR_PRF_FRAME_INFO` valor que indica dónde obtener información sobre el marco de pila.</span><span class="sxs-lookup"><span data-stu-id="ab387-108">[in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>  
  
 <span data-ttu-id="ab387-109">El generador de perfiles debe tratar como un identificador opaco que puede pasarse al motor de ejecución en el [ICorProfilerInfo2:: Getfunctioninfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="ab387-109">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ab387-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ab387-110">Remarks</span></span>  
 <span data-ttu-id="ab387-111">La función de destino de la llamada de cola usará el marco de pila actual y devolverá directamente al autor de llamada de la función que realizó el final de la llamada.</span><span class="sxs-lookup"><span data-stu-id="ab387-111">The target function of the tail call will use the current stack frame, and will return directly to the caller of the function that made the tail call.</span></span> <span data-ttu-id="ab387-112">Esto significa que un [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) devolución de llamada no se emitirá para una función que es el destino de una llamada de cola.</span><span class="sxs-lookup"><span data-stu-id="ab387-112">This means that a [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) callback will not be issued for a function that is the target of a tail call.</span></span>  
  
 <span data-ttu-id="ab387-113">El valor de la `func` parámetro no es válido tras la `FunctionTailcall2` función devuelve porque el valor puede cambiar o se destruye.</span><span class="sxs-lookup"><span data-stu-id="ab387-113">The value of the `func` parameter is not valid after the `FunctionTailcall2` function returns because the value may change or be destroyed.</span></span>  
  
 <span data-ttu-id="ab387-114">El `FunctionTailcall2` función es una devolución de llamada; debe implementar.</span><span class="sxs-lookup"><span data-stu-id="ab387-114">The `FunctionTailcall2` function is a callback; you must implement it.</span></span> <span data-ttu-id="ab387-115">La implementación debe utilizar el `__declspec`(`naked`) el atributo de clase de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="ab387-115">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="ab387-116">El motor de ejecución no guardan los registros antes de llamar a esta función.</span><span class="sxs-lookup"><span data-stu-id="ab387-116">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="ab387-117">En la entrada, debe guardar todos los registros que utilice, incluidos los de la unidad de punto flotante (FPU).</span><span class="sxs-lookup"><span data-stu-id="ab387-117">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="ab387-118">Al salir, debe restablecer la pila desactivando todos los parámetros que se han insertados por el llamador.</span><span class="sxs-lookup"><span data-stu-id="ab387-118">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="ab387-119">La implementación de `FunctionTailcall2` no debe bloquearse porque retrasará la recolección de elementos.</span><span class="sxs-lookup"><span data-stu-id="ab387-119">The implementation of `FunctionTailcall2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="ab387-120">La implementación no debería intentar una recolección porque la pila no puede estar en un estado compatible con la colección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="ab387-120">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="ab387-121">Si se intenta realizar una recolección, el tiempo de ejecución se bloqueará hasta que `FunctionTailcall2` devuelve.</span><span class="sxs-lookup"><span data-stu-id="ab387-121">If a garbage collection is attempted, the runtime will block until `FunctionTailcall2` returns.</span></span>  
  
 <span data-ttu-id="ab387-122">Además, la `FunctionTailcall2` función no debe llamar a código administrado o en modo alguno provocar una asignación de memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="ab387-122">Also, the `FunctionTailcall2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab387-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ab387-123">Requirements</span></span>  
 <span data-ttu-id="ab387-124">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab387-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab387-125">**Encabezado:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="ab387-125">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="ab387-126">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ab387-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ab387-127">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab387-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab387-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="ab387-128">See Also</span></span>  
 [<span data-ttu-id="ab387-129">FunctionEnter2 (Función)</span><span class="sxs-lookup"><span data-stu-id="ab387-129">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 [<span data-ttu-id="ab387-130">FunctionLeave2 (Función)</span><span class="sxs-lookup"><span data-stu-id="ab387-130">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 [<span data-ttu-id="ab387-131">SetEnterLeaveFunctionHooks2 (método)</span><span class="sxs-lookup"><span data-stu-id="ab387-131">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)  
 [<span data-ttu-id="ab387-132">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="ab387-132">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
