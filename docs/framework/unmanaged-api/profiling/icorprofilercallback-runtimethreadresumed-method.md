---
title: ICorProfilerCallback::RuntimeThreadResumed (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeThreadResumed
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeThreadResumed
helpviewer_keywords:
- ICorProfilerCallback::RuntimeThreadResumed method [.NET Framework profiling]
- RuntimeThreadResumed method [.NET Framework profiling]
ms.assetid: da984f89-4f53-4ab0-ae6f-3e2ee6085994
topic_type:
- apiref
ms.openlocfilehash: d3949189a72583ebb50b67a270694a31f1eb23dc
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503216"
---
# <a name="icorprofilercallbackruntimethreadresumed-method"></a><span data-ttu-id="b2005-102">ICorProfilerCallback::RuntimeThreadResumed (Método)</span><span class="sxs-lookup"><span data-stu-id="b2005-102">ICorProfilerCallback::RuntimeThreadResumed Method</span></span>
<span data-ttu-id="b2005-103">Notifica al generador de perfiles que se ha reanudado el subproceso especificado tras su suspensión.</span><span class="sxs-lookup"><span data-stu-id="b2005-103">Notifies the profiler that the specified thread has resumed after being suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2005-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b2005-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeThreadResumed(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2005-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b2005-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="b2005-106">de IDENTIFICADOR del subproceso que se ha reanudado.</span><span class="sxs-lookup"><span data-stu-id="b2005-106">[in] The ID of the thread that has been resumed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2005-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b2005-107">Requirements</span></span>  
 <span data-ttu-id="b2005-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2005-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2005-109">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b2005-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b2005-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2005-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2005-111">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2005-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2005-112">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="b2005-112">See also</span></span>

- [<span data-ttu-id="b2005-113">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b2005-113">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="b2005-114">Método RuntimeThreadSuspended</span><span class="sxs-lookup"><span data-stu-id="b2005-114">RuntimeThreadSuspended Method</span></span>](icorprofilercallback-runtimethreadsuspended-method.md)
