---
title: ICorProfilerCallback::ExceptionUnwindFinallyEnter (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionUnwindFinallyEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionUnwindFinallyEnter
helpviewer_keywords:
- ICorProfilerCallback::ExceptionUnwindFinallyEnter method [.NET Framework profiling]
- ExceptionUnwindFinallyEnter method [.NET Framework profiling]
ms.assetid: c7fab986-b69f-4ec8-b7b7-91dcfc239cd0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: aebfc0d763fa1ea14c55a0c61fbf63db65fefe02
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59137870"
---
# <a name="icorprofilercallbackexceptionunwindfinallyenter-method"></a><span data-ttu-id="bbd5b-102">ICorProfilerCallback::ExceptionUnwindFinallyEnter (Método)</span><span class="sxs-lookup"><span data-stu-id="bbd5b-102">ICorProfilerCallback::ExceptionUnwindFinallyEnter Method</span></span>
<span data-ttu-id="bbd5b-103">Notifica al generador de perfiles que la fase de desenredo de excepciones está entrando en control de un `finally` cláusula contenida en la función especificada.</span><span class="sxs-lookup"><span data-stu-id="bbd5b-103">Notifies the profiler that the unwind phase of exception handling is entering a `finally` clause contained in the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbd5b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bbd5b-104">Syntax</span></span>  
  
```  
HRESULT ExceptionUnwindFinallyEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bbd5b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bbd5b-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="bbd5b-106">[in] El identificador de la función que contiene el `finally` cláusula.</span><span class="sxs-lookup"><span data-stu-id="bbd5b-106">[in] The ID of the function that contains the `finally` clause.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bbd5b-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bbd5b-107">Remarks</span></span>  
 <span data-ttu-id="bbd5b-108">El generador de perfiles no debe bloquearse en su implementación de este método porque la pila no puede estar en un estado que permita la recolección de elementos y, por lo tanto, no se puede habilitar la recolección preferente.</span><span class="sxs-lookup"><span data-stu-id="bbd5b-108">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="bbd5b-109">Si el generador de perfiles se bloquea aquí y se intenta realizar la recolección de elementos, el tiempo de ejecución se bloqueará hasta que devuelve esta devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="bbd5b-109">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="bbd5b-110">Implementación del generador de perfiles de este método no debe llamar a código administrado o en modo alguno provocar una asignación de memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="bbd5b-110">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bbd5b-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bbd5b-111">Requirements</span></span>  
 <span data-ttu-id="bbd5b-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bbd5b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bbd5b-113">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bbd5b-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bbd5b-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bbd5b-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="bbd5b-115">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="bbd5b-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="bbd5b-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="bbd5b-116">See also</span></span>

- [<span data-ttu-id="bbd5b-117">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bbd5b-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="bbd5b-118">Método GetNotifiedExceptionClauseInfo</span><span class="sxs-lookup"><span data-stu-id="bbd5b-118">GetNotifiedExceptionClauseInfo Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md)
- [<span data-ttu-id="bbd5b-119">Método ExceptionUnwindFinallyLeave</span><span class="sxs-lookup"><span data-stu-id="bbd5b-119">ExceptionUnwindFinallyLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)
