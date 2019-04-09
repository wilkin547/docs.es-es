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
ms.openlocfilehash: f7f1b2756dd180cb0a701429978a34ea80447a86
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59107645"
---
# <a name="icorprofilercallbackexceptioncatcherleave-method"></a><span data-ttu-id="5ad1d-102">ICorProfilerCallback::ExceptionCatcherLeave (Método)</span><span class="sxs-lookup"><span data-stu-id="5ad1d-102">ICorProfilerCallback::ExceptionCatcherLeave Method</span></span>
<span data-ttu-id="5ad1d-103">Notifica al generador de perfiles que se pasa el control fuera adecuado `catch` bloque.</span><span class="sxs-lookup"><span data-stu-id="5ad1d-103">Notifies the profiler that control is being passed out of the appropriate `catch` block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ad1d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5ad1d-104">Syntax</span></span>  
  
```  
HRESULT ExceptionCatcherLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="5ad1d-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5ad1d-105">Remarks</span></span>  
 <span data-ttu-id="5ad1d-106">El generador de perfiles no debe bloquearse en su implementación de este método porque la pila no puede estar en un estado que permita la recolección de elementos y, por lo tanto, no se puede habilitar la recolección preferente.</span><span class="sxs-lookup"><span data-stu-id="5ad1d-106">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="5ad1d-107">Si el generador de perfiles se bloquea aquí y se intenta realizar la recolección de elementos, el tiempo de ejecución se bloqueará hasta que devuelve esta devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="5ad1d-107">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="5ad1d-108">Implementación del generador de perfiles de este método no debe llamar a código administrado o en modo alguno provocar una asignación de memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="5ad1d-108">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ad1d-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5ad1d-109">Requirements</span></span>  
 <span data-ttu-id="5ad1d-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ad1d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ad1d-111">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5ad1d-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5ad1d-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5ad1d-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="5ad1d-113">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="5ad1d-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5ad1d-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="5ad1d-114">See also</span></span>

- [<span data-ttu-id="5ad1d-115">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5ad1d-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="5ad1d-116">Método ExceptionCatcherEnter</span><span class="sxs-lookup"><span data-stu-id="5ad1d-116">ExceptionCatcherEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)
