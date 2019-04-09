---
title: ICorProfilerCallback::ExceptionUnwindFinallyLeave (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionUnwindFinallyLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionUnwindFinallyLeave
helpviewer_keywords:
- ICorProfilerCallback::ExceptionUnwindFinallyLeave method [.NET Framework profiling]
- ExceptionUnwindFinallyLeave method [.NET Framework profiling]
ms.assetid: 2350351e-f253-4c0c-a191-f952bc5700e6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7ba62ab2c4df73b570fb1c76adaee44a2a2ce8c3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59117811"
---
# <a name="icorprofilercallbackexceptionunwindfinallyleave-method"></a><span data-ttu-id="a726b-102">ICorProfilerCallback::ExceptionUnwindFinallyLeave (Método)</span><span class="sxs-lookup"><span data-stu-id="a726b-102">ICorProfilerCallback::ExceptionUnwindFinallyLeave Method</span></span>
<span data-ttu-id="a726b-103">Notifica al generador de perfiles que la fase de desenredo de excepción control ha dejado un `finally` cláusula.</span><span class="sxs-lookup"><span data-stu-id="a726b-103">Notifies the profiler that the unwind phase of exception handling has left a `finally` clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a726b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a726b-104">Syntax</span></span>  
  
```  
HRESULT ExceptionUnwindFinallyLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="a726b-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a726b-105">Remarks</span></span>  
 <span data-ttu-id="a726b-106">El generador de perfiles no debe bloquearse durante esta llamada porque la pila no puede estar en un estado que permita la recolección de elementos y, por lo tanto, no se puede habilitar la recolección preferente.</span><span class="sxs-lookup"><span data-stu-id="a726b-106">The profiler should not block during this call because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="a726b-107">Si se intenta aquí los bloques del generador de perfiles y una colección de elementos no utilizados, el tiempo de ejecución se bloqueará hasta que devuelve esta devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="a726b-107">If the profiler blocks here and a garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="a726b-108">Asimismo, durante esta llamada, el generador de perfiles no debe llamar a código administrado o en modo alguno provocar una asignación de memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="a726b-108">Also, during this call, the profiler must not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a726b-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a726b-109">Requirements</span></span>  
 <span data-ttu-id="a726b-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a726b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a726b-111">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a726b-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a726b-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a726b-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="a726b-113">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="a726b-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a726b-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="a726b-114">See also</span></span>

- [<span data-ttu-id="a726b-115">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a726b-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="a726b-116">Método ExceptionUnwindFinallyEnter</span><span class="sxs-lookup"><span data-stu-id="a726b-116">ExceptionUnwindFinallyEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)
