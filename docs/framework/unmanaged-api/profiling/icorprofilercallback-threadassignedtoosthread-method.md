---
title: ICorProfilerCallback::ThreadAssignedToOSThread (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ThreadAssignedToOSThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ThreadAssignedToOSThread
helpviewer_keywords:
- ThreadAssignedToOSThread method [.NET Framework profiling]
- ICorProfilerCallback::ThreadAssignedToOSThread method [.NET Framework profiling]
ms.assetid: f9671e5a-7b14-4f5b-8404-58136422c8b2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: eefcd4436a28fdf52cbe55da5d4bb7eea4449463
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59158462"
---
# <a name="icorprofilercallbackthreadassignedtoosthread-method"></a><span data-ttu-id="b62c1-102">ICorProfilerCallback::ThreadAssignedToOSThread (Método)</span><span class="sxs-lookup"><span data-stu-id="b62c1-102">ICorProfilerCallback::ThreadAssignedToOSThread Method</span></span>
<span data-ttu-id="b62c1-103">Notifica al generador de perfiles que se está implementando un subproceso administrado mediante un subproceso concreto del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="b62c1-103">Notifies the profiler that a managed thread is being implemented using a particular operating system thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b62c1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b62c1-104">Syntax</span></span>  
  
```  
HRESULT ThreadAssignedToOSThread(  
    [in] ThreadID managedThreadId,  
    [in] DWORD    osThreadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b62c1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b62c1-105">Parameters</span></span>  
 `managedThreadId`  
 <span data-ttu-id="b62c1-106">[in] El identificador del subproceso administrado.</span><span class="sxs-lookup"><span data-stu-id="b62c1-106">[in] The identifier of the managed thread.</span></span>  
  
 `osThreadId`  
 <span data-ttu-id="b62c1-107">[in] El identificador de subproceso del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="b62c1-107">[in] The identifier of the operating system thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b62c1-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b62c1-108">Remarks</span></span>  
 <span data-ttu-id="b62c1-109">El `ThreadAssignedToOSThread` devolución de llamada existe para que el generador de perfiles puede mantener una asignación precisa en fibras de subprocesos del sistema operativo para los subprocesos administrados.</span><span class="sxs-lookup"><span data-stu-id="b62c1-109">The `ThreadAssignedToOSThread` callback exists so that the profiler can maintain an accurate mapping across fibers of operating system threads to managed threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b62c1-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b62c1-110">Requirements</span></span>  
 <span data-ttu-id="b62c1-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b62c1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b62c1-112">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b62c1-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b62c1-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b62c1-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="b62c1-114">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="b62c1-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b62c1-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="b62c1-115">See also</span></span>

- [<span data-ttu-id="b62c1-116">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b62c1-116">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
