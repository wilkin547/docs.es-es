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
ms.openlocfilehash: 6514606290bf006443d7011c1a428bebb4cca0f6
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865836"
---
# <a name="icorprofilercallbackthreadcreated-method"></a><span data-ttu-id="49be7-102">ICorProfilerCallback::ThreadCreated (Método)</span><span class="sxs-lookup"><span data-stu-id="49be7-102">ICorProfilerCallback::ThreadCreated Method</span></span>
<span data-ttu-id="49be7-103">Notifica al generador de perfiles que se ha creado un subproceso.</span><span class="sxs-lookup"><span data-stu-id="49be7-103">Notifies the profiler that a thread has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49be7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="49be7-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadCreated(  
    [in] ThreadID threadId);   
```  
  
## <a name="parameters"></a><span data-ttu-id="49be7-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="49be7-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="49be7-106">de IDENTIFICADOR del subproceso que se ha creado.</span><span class="sxs-lookup"><span data-stu-id="49be7-106">[in] The ID of the thread that has been created.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="49be7-107">Notas</span><span class="sxs-lookup"><span data-stu-id="49be7-107">Remarks</span></span>  
 <span data-ttu-id="49be7-108">El valor `threadId` es válido de forma inmediata.</span><span class="sxs-lookup"><span data-stu-id="49be7-108">The `threadId` value is immediately valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49be7-109">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="49be7-109">Requirements</span></span>  
 <span data-ttu-id="49be7-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49be7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49be7-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="49be7-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="49be7-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="49be7-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="49be7-113">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49be7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49be7-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="49be7-114">See also</span></span>

- [<span data-ttu-id="49be7-115">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="49be7-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="49be7-116">ThreadDestroyed (método)</span><span class="sxs-lookup"><span data-stu-id="49be7-116">ThreadDestroyed Method</span></span>](icorprofilercallback-threaddestroyed-method.md)
