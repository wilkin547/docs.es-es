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
ms.openlocfilehash: 0cef868861155d553aba42fe28c3f1f1b86763b0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731974"
---
# <a name="icorprofilercallbackthreaddestroyed-method"></a><span data-ttu-id="4032a-102">ICorProfilerCallback::ThreadDestroyed (Método)</span><span class="sxs-lookup"><span data-stu-id="4032a-102">ICorProfilerCallback::ThreadDestroyed Method</span></span>

<span data-ttu-id="4032a-103">Notifica al generador de perfiles que se ha destruido un subproceso.</span><span class="sxs-lookup"><span data-stu-id="4032a-103">Notifies the profiler that a thread has been destroyed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4032a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4032a-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadDestroyed(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4032a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4032a-105">Parameters</span></span>  

 `threadId`  
 <span data-ttu-id="4032a-106">de IDENTIFICADOR del subproceso que se ha destruido.</span><span class="sxs-lookup"><span data-stu-id="4032a-106">[in] The ID of the thread that has been destroyed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4032a-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4032a-107">Remarks</span></span>  

 <span data-ttu-id="4032a-108">El `threadId` valor ya no es válido en el momento de esta llamada.</span><span class="sxs-lookup"><span data-stu-id="4032a-108">The `threadId` value is no longer valid at the time of this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4032a-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4032a-109">Requirements</span></span>  

 <span data-ttu-id="4032a-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4032a-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4032a-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4032a-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4032a-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4032a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4032a-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4032a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4032a-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4032a-114">See also</span></span>

- [<span data-ttu-id="4032a-115">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4032a-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="4032a-116">Método ThreadCreated</span><span class="sxs-lookup"><span data-stu-id="4032a-116">ThreadCreated Method</span></span>](icorprofilercallback-threadcreated-method.md)
