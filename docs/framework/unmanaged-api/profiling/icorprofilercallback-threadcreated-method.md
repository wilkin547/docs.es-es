---
description: 'Más información sobre: ICorProfilerCallback:: ThreadCreated ((método)'
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
ms.openlocfilehash: 8b6208856b78298f643161cd6bb78773ac86bc3b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99657208"
---
# <a name="icorprofilercallbackthreadcreated-method"></a><span data-ttu-id="9dd71-103">ICorProfilerCallback::ThreadCreated (Método)</span><span class="sxs-lookup"><span data-stu-id="9dd71-103">ICorProfilerCallback::ThreadCreated Method</span></span>

<span data-ttu-id="9dd71-104">Notifica al generador de perfiles que se ha creado un subproceso.</span><span class="sxs-lookup"><span data-stu-id="9dd71-104">Notifies the profiler that a thread has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9dd71-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9dd71-105">Syntax</span></span>  
  
```cpp  
HRESULT ThreadCreated(  
    [in] ThreadID threadId);
```  
  
## <a name="parameters"></a><span data-ttu-id="9dd71-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9dd71-106">Parameters</span></span>  

 `threadId`  
 <span data-ttu-id="9dd71-107">de IDENTIFICADOR del subproceso que se ha creado.</span><span class="sxs-lookup"><span data-stu-id="9dd71-107">[in] The ID of the thread that has been created.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9dd71-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9dd71-108">Remarks</span></span>  

 <span data-ttu-id="9dd71-109">El `threadId` valor es válido inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="9dd71-109">The `threadId` value is immediately valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9dd71-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9dd71-110">Requirements</span></span>  

 <span data-ttu-id="9dd71-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9dd71-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9dd71-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9dd71-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9dd71-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9dd71-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9dd71-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9dd71-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9dd71-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="9dd71-115">See also</span></span>

- [<span data-ttu-id="9dd71-116">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9dd71-116">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="9dd71-117">Método ThreadDestroyed</span><span class="sxs-lookup"><span data-stu-id="9dd71-117">ThreadDestroyed Method</span></span>](icorprofilercallback-threaddestroyed-method.md)
