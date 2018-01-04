---
title: "ICorProfilerCallback::ExceptionThrown (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ExceptionThrown
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ExceptionThrown
helpviewer_keywords:
- ExceptionThrown method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionThrown method [.NET Framework profiling]
ms.assetid: f1a23f3b-ac21-4905-8abf-8ea59f15af53
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 65fdd8f2912dc2854ba7801244ba489426d05e47
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackexceptionthrown-method"></a><span data-ttu-id="1229c-102">ICorProfilerCallback::ExceptionThrown (Método)</span><span class="sxs-lookup"><span data-stu-id="1229c-102">ICorProfilerCallback::ExceptionThrown Method</span></span>
<span data-ttu-id="1229c-103">Notifica al generador de perfiles que se ha producido una excepción.</span><span class="sxs-lookup"><span data-stu-id="1229c-103">Notifies the profiler that an exception has been thrown.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1229c-104">Esta función se invoca únicamente si la excepción alcanza el código administrado.</span><span class="sxs-lookup"><span data-stu-id="1229c-104">This function is called only if the exception reaches managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1229c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1229c-105">Syntax</span></span>  
  
```  
HRESULT ExceptionThrown(  
    [in] ObjectID thrownObjectId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1229c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1229c-106">Parameters</span></span>  
 `thrownObjectId`  
 <span data-ttu-id="1229c-107">[in] El identificador del objeto que provocó la excepción.</span><span class="sxs-lookup"><span data-stu-id="1229c-107">[in] The ID of the object that caused the exception to be thrown.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1229c-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1229c-108">Remarks</span></span>  
 <span data-ttu-id="1229c-109">El generador de perfiles no debe bloquearse en su implementación de este método porque la pila no puede estar en un estado que permita la recopilación de elementos no utilizados y, por lo tanto, no se puede habilitar la colección de elementos no utilizados preferente.</span><span class="sxs-lookup"><span data-stu-id="1229c-109">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="1229c-110">Si el generador de perfiles se bloquea aquí y se intenta realizar la recolección de elementos, el tiempo de ejecución se bloqueará hasta que devuelve esta devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="1229c-110">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="1229c-111">Implementación del generador de perfiles de este método no debe llamar a código administrado o en modo alguno provocar una asignación de memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="1229c-111">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1229c-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1229c-112">Requirements</span></span>  
 <span data-ttu-id="1229c-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1229c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1229c-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1229c-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1229c-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1229c-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1229c-116">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1229c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1229c-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="1229c-117">See Also</span></span>  
 [<span data-ttu-id="1229c-118">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1229c-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
