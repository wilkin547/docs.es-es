---
description: 'Más información sobre: ICorProfilerCallback:: RuntimeThreadResumed ((método)'
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
ms.openlocfilehash: a01be057bb442c69890d3b1cb4ebe1f861d2518c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99657351"
---
# <a name="icorprofilercallbackruntimethreadresumed-method"></a><span data-ttu-id="e240c-103">ICorProfilerCallback::RuntimeThreadResumed (Método)</span><span class="sxs-lookup"><span data-stu-id="e240c-103">ICorProfilerCallback::RuntimeThreadResumed Method</span></span>

<span data-ttu-id="e240c-104">Notifica al generador de perfiles que se ha reanudado el subproceso especificado tras su suspensión.</span><span class="sxs-lookup"><span data-stu-id="e240c-104">Notifies the profiler that the specified thread has resumed after being suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e240c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e240c-105">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeThreadResumed(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e240c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e240c-106">Parameters</span></span>  

 `threadId`  
 <span data-ttu-id="e240c-107">de IDENTIFICADOR del subproceso que se ha reanudado.</span><span class="sxs-lookup"><span data-stu-id="e240c-107">[in] The ID of the thread that has been resumed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e240c-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e240c-108">Requirements</span></span>  

 <span data-ttu-id="e240c-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e240c-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e240c-110">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e240c-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e240c-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e240c-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e240c-112">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e240c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e240c-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="e240c-113">See also</span></span>

- [<span data-ttu-id="e240c-114">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e240c-114">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="e240c-115">Método RuntimeThreadSuspended</span><span class="sxs-lookup"><span data-stu-id="e240c-115">RuntimeThreadSuspended Method</span></span>](icorprofilercallback-runtimethreadsuspended-method.md)
