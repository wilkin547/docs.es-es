---
title: ICorProfilerCallback::ThreadCreated (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ThreadCreated
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ThreadCreated
helpviewer_keywords:
- ICorProfilerCallback::ThreadCreated method [.NET Framework profiling]
- ThreadCreated method [.NET Framework profiling]
ms.assetid: cca0f799-09b8-4689-a33c-6d6537943a9b
topic_type:
- apiref
ms.openlocfilehash: 72b074d1794a6039060cbd84aabb0bc0155c154e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717297"
---
# <a name="icorprofilercallbackthreadcreated-method"></a><span data-ttu-id="322c3-102">ICorProfilerCallback::ThreadCreated (Método)</span><span class="sxs-lookup"><span data-stu-id="322c3-102">ICorProfilerCallback::ThreadCreated Method</span></span>

<span data-ttu-id="322c3-103">Notifica al generador de perfiles que se ha creado un subproceso.</span><span class="sxs-lookup"><span data-stu-id="322c3-103">Notifies the profiler that a thread has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="322c3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="322c3-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadCreated(  
    [in] ThreadID threadId);
```  
  
## <a name="parameters"></a><span data-ttu-id="322c3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="322c3-105">Parameters</span></span>  

 `threadId`  
 <span data-ttu-id="322c3-106">de IDENTIFICADOR del subproceso que se ha creado.</span><span class="sxs-lookup"><span data-stu-id="322c3-106">[in] The ID of the thread that has been created.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="322c3-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="322c3-107">Remarks</span></span>  

 <span data-ttu-id="322c3-108">El `threadId` valor es válido inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="322c3-108">The `threadId` value is immediately valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="322c3-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="322c3-109">Requirements</span></span>  

 <span data-ttu-id="322c3-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="322c3-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="322c3-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="322c3-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="322c3-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="322c3-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="322c3-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="322c3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="322c3-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="322c3-114">See also</span></span>

- [<span data-ttu-id="322c3-115">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="322c3-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="322c3-116">Método ThreadDestroyed</span><span class="sxs-lookup"><span data-stu-id="322c3-116">ThreadDestroyed Method</span></span>](icorprofilercallback-threaddestroyed-method.md)
