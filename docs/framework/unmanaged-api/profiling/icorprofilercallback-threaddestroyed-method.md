---
description: 'Más información sobre: ICorProfilerCallback:: ThreadDestroyed ((método)'
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
ms.openlocfilehash: 63c8c4c523cb398bd7c766fc41bc669a2d74045e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99657198"
---
# <a name="icorprofilercallbackthreaddestroyed-method"></a><span data-ttu-id="fd608-103">ICorProfilerCallback::ThreadDestroyed (Método)</span><span class="sxs-lookup"><span data-stu-id="fd608-103">ICorProfilerCallback::ThreadDestroyed Method</span></span>

<span data-ttu-id="fd608-104">Notifica al generador de perfiles que se ha destruido un subproceso.</span><span class="sxs-lookup"><span data-stu-id="fd608-104">Notifies the profiler that a thread has been destroyed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd608-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fd608-105">Syntax</span></span>  
  
```cpp  
HRESULT ThreadDestroyed(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fd608-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fd608-106">Parameters</span></span>  

 `threadId`  
 <span data-ttu-id="fd608-107">de IDENTIFICADOR del subproceso que se ha destruido.</span><span class="sxs-lookup"><span data-stu-id="fd608-107">[in] The ID of the thread that has been destroyed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fd608-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="fd608-108">Remarks</span></span>  

 <span data-ttu-id="fd608-109">El `threadId` valor ya no es válido en el momento de esta llamada.</span><span class="sxs-lookup"><span data-stu-id="fd608-109">The `threadId` value is no longer valid at the time of this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd608-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fd608-110">Requirements</span></span>  

 <span data-ttu-id="fd608-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd608-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd608-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fd608-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fd608-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fd608-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fd608-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd608-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd608-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="fd608-115">See also</span></span>

- [<span data-ttu-id="fd608-116">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fd608-116">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="fd608-117">Método ThreadCreated</span><span class="sxs-lookup"><span data-stu-id="fd608-117">ThreadCreated Method</span></span>](icorprofilercallback-threadcreated-method.md)
