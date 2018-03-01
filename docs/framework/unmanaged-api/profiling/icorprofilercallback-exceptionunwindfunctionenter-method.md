---
title: "ICorProfilerCallback::ExceptionUnwindFunctionEnter (Método)"
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
- ICorProfilerCallback.ExceptionUnwindFunctionEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionUnwindFunctionEnter
helpviewer_keywords:
- ICorProfilerCallback::ExceptionUnwindFunctionEnter method [.NET Framework profiling]
- ExceptionUnwindFunctionEnter method [.NET Framework profiling]
ms.assetid: ea3dc625-5650-4bf4-8e67-01e42be065b1
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: bae438413ad81d556d8aeb0ca4a3526bcd968d67
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackexceptionunwindfunctionenter-method"></a><span data-ttu-id="c172e-102">ICorProfilerCallback::ExceptionUnwindFunctionEnter (Método)</span><span class="sxs-lookup"><span data-stu-id="c172e-102">ICorProfilerCallback::ExceptionUnwindFunctionEnter Method</span></span>
<span data-ttu-id="c172e-103">Notifica al generador de perfiles que la fase de desenredo del control de excepciones ha empezado a desenredar una función.</span><span class="sxs-lookup"><span data-stu-id="c172e-103">Notifies the profiler that the unwind phase of exception handling has begun to unwind a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c172e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c172e-104">Syntax</span></span>  
  
```  
HRESULT ExceptionUnwindFunctionEnter(  
    [in] FunctionID functionId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c172e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c172e-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="c172e-106">[in] El identificador de la función que se va a desenredar.</span><span class="sxs-lookup"><span data-stu-id="c172e-106">[in] The ID of the function that is being unwound.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c172e-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c172e-107">Remarks</span></span>  
 <span data-ttu-id="c172e-108">El generador de perfiles no debe bloquearse en su implementación de este método porque la pila no puede estar en un estado que permita la recopilación de elementos no utilizados y, por lo tanto, no se puede habilitar la colección de elementos no utilizados preferente.</span><span class="sxs-lookup"><span data-stu-id="c172e-108">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="c172e-109">Si el generador de perfiles se bloquea aquí y se intenta realizar la recolección de elementos, el tiempo de ejecución se bloqueará hasta que devuelve esta devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="c172e-109">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="c172e-110">Implementación del generador de perfiles de este método no debe llamar a código administrado o en modo alguno provocar una asignación de memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="c172e-110">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c172e-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c172e-111">Requirements</span></span>  
 <span data-ttu-id="c172e-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c172e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c172e-113">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c172e-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c172e-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c172e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c172e-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c172e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c172e-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="c172e-116">See Also</span></span>  
 [<span data-ttu-id="c172e-117">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c172e-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="c172e-118">ExceptionUnwindFunctionLeave (método)</span><span class="sxs-lookup"><span data-stu-id="c172e-118">ExceptionUnwindFunctionLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionleave-method.md)
