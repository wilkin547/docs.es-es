---
title: ICorProfilerCallback::ThreadDestroyed (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ThreadDestroyed
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ThreadDestroyed
helpviewer_keywords:
- ThreadDestroyed method [.NET Framework profiling]
- ICorProfilerCallback::ThreadDestroyed method [.NET Framework profiling]
ms.assetid: 4c2b66fd-0595-40a3-8931-f9c4fff97ac8
topic_type:
- apiref
ms.openlocfilehash: 07041d06668d474a3d30968fb623854a24ebf0eb
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865829"
---
# <a name="icorprofilercallbackthreaddestroyed-method"></a><span data-ttu-id="f8f74-102">ICorProfilerCallback::ThreadDestroyed (Método)</span><span class="sxs-lookup"><span data-stu-id="f8f74-102">ICorProfilerCallback::ThreadDestroyed Method</span></span>
<span data-ttu-id="f8f74-103">Notifica al generador de perfiles que se ha destruido un subproceso.</span><span class="sxs-lookup"><span data-stu-id="f8f74-103">Notifies the profiler that a thread has been destroyed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8f74-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f8f74-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadDestroyed(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f8f74-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="f8f74-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="f8f74-106">de IDENTIFICADOR del subproceso que se ha destruido.</span><span class="sxs-lookup"><span data-stu-id="f8f74-106">[in] The ID of the thread that has been destroyed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8f74-107">Notas</span><span class="sxs-lookup"><span data-stu-id="f8f74-107">Remarks</span></span>  
 <span data-ttu-id="f8f74-108">El valor `threadId` ya no es válido en el momento de esta llamada.</span><span class="sxs-lookup"><span data-stu-id="f8f74-108">The `threadId` value is no longer valid at the time of this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8f74-109">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="f8f74-109">Requirements</span></span>  
 <span data-ttu-id="f8f74-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8f74-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8f74-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f8f74-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f8f74-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f8f74-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f8f74-113">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8f74-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8f74-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="f8f74-114">See also</span></span>

- [<span data-ttu-id="f8f74-115">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f8f74-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="f8f74-116">ThreadCreated (método)</span><span class="sxs-lookup"><span data-stu-id="f8f74-116">ThreadCreated Method</span></span>](icorprofilercallback-threadcreated-method.md)
