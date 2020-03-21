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
ms.openlocfilehash: 7fb58c0eb2446253bd658434fc9d68bb857fe0e6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175127"
---
# <a name="icorprofilercallbackthreadcreated-method"></a><span data-ttu-id="1a563-102">ICorProfilerCallback::ThreadCreated (Método)</span><span class="sxs-lookup"><span data-stu-id="1a563-102">ICorProfilerCallback::ThreadCreated Method</span></span>
<span data-ttu-id="1a563-103">Notifica al generador de perfiles que se ha creado un subproceso.</span><span class="sxs-lookup"><span data-stu-id="1a563-103">Notifies the profiler that a thread has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a563-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1a563-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadCreated(  
    [in] ThreadID threadId);
```  
  
## <a name="parameters"></a><span data-ttu-id="1a563-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1a563-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="1a563-106">[en] El identificador del subproceso que se ha creado.</span><span class="sxs-lookup"><span data-stu-id="1a563-106">[in] The ID of the thread that has been created.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1a563-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1a563-107">Remarks</span></span>  
 <span data-ttu-id="1a563-108">El `threadId` valor es inmediatamente válido.</span><span class="sxs-lookup"><span data-stu-id="1a563-108">The `threadId` value is immediately valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a563-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1a563-109">Requirements</span></span>  
 <span data-ttu-id="1a563-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1a563-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a563-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1a563-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1a563-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1a563-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1a563-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a563-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a563-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1a563-114">See also</span></span>

- [<span data-ttu-id="1a563-115">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1a563-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="1a563-116">ThreadDestroyed (método)</span><span class="sxs-lookup"><span data-stu-id="1a563-116">ThreadDestroyed Method</span></span>](icorprofilercallback-threaddestroyed-method.md)
