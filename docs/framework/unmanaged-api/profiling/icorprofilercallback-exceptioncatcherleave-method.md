---
title: ICorProfilerCallback::ExceptionCatcherLeave (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionCatcherLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionCatcherLeave
helpviewer_keywords:
- ExceptionCatcherLeave method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionCatcherLeave method [.NET Framework profiling]
ms.assetid: 1f3dbdf5-db0c-4b07-bbb7-375de2a63673
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d0fef75a1d47ba0c16569d3955ee447c2e7332d4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776129"
---
# <a name="icorprofilercallbackexceptioncatcherleave-method"></a><span data-ttu-id="3a5c1-102">ICorProfilerCallback::ExceptionCatcherLeave (Método)</span><span class="sxs-lookup"><span data-stu-id="3a5c1-102">ICorProfilerCallback::ExceptionCatcherLeave Method</span></span>
<span data-ttu-id="3a5c1-103">Notifica al generador de perfiles que se pasa el control fuera adecuado `catch` bloque.</span><span class="sxs-lookup"><span data-stu-id="3a5c1-103">Notifies the profiler that control is being passed out of the appropriate `catch` block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a5c1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3a5c1-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCatcherLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="3a5c1-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3a5c1-105">Remarks</span></span>  
 <span data-ttu-id="3a5c1-106">El generador de perfiles no debe bloquearse en su implementación de este método porque la pila no puede estar en un estado que permita la recolección de elementos y, por lo tanto, no se puede habilitar la recolección preferente.</span><span class="sxs-lookup"><span data-stu-id="3a5c1-106">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="3a5c1-107">Si el generador de perfiles se bloquea aquí y se intenta realizar la recolección de elementos, el tiempo de ejecución se bloqueará hasta que devuelve esta devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="3a5c1-107">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="3a5c1-108">Implementación del generador de perfiles de este método no debe llamar a código administrado o en modo alguno provocar una asignación de memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="3a5c1-108">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a5c1-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3a5c1-109">Requirements</span></span>  
 <span data-ttu-id="3a5c1-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a5c1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a5c1-111">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3a5c1-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3a5c1-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3a5c1-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3a5c1-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a5c1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a5c1-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="3a5c1-114">See also</span></span>

- [<span data-ttu-id="3a5c1-115">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3a5c1-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="3a5c1-116">ExceptionCatcherEnter (método)</span><span class="sxs-lookup"><span data-stu-id="3a5c1-116">ExceptionCatcherEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)
