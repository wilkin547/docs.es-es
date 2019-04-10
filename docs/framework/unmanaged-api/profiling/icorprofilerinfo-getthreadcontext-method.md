---
title: ICorProfilerInfo::GetThreadContext (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetThreadContext
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetThreadContext
helpviewer_keywords:
- ICorProfilerInfo::GetThreadContext method [.NET Framework profiling]
- GetThreadContext method, ICorProfilerInfo interface [.NET Framework profiling]
ms.assetid: 79446216-4b8b-484c-8fe3-e87dbf9df2fd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f26fd93d42a709249936815d3c29ae572482f427
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59224629"
---
# <a name="icorprofilerinfogetthreadcontext-method"></a><span data-ttu-id="e2d16-102">ICorProfilerInfo::GetThreadContext (Método)</span><span class="sxs-lookup"><span data-stu-id="e2d16-102">ICorProfilerInfo::GetThreadContext Method</span></span>
<span data-ttu-id="e2d16-103">Obtiene la identidad de contexto actualmente asociada con el subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="e2d16-103">Gets the context identity currently associated with the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2d16-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e2d16-104">Syntax</span></span>  
  
```  
HRESULT GetThreadContext(  
    [in]  ThreadID  threadId,  
    [out] ContextID *pContextId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e2d16-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e2d16-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="e2d16-106">[in] El identificador del subproceso.</span><span class="sxs-lookup"><span data-stu-id="e2d16-106">[in] The ID of the thread.</span></span>  
  
 `pContextId`  
 <span data-ttu-id="e2d16-107">[out] Un puntero al identificador de contexto actualmente asociado con el subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="e2d16-107">[out] A pointer to the context ID currently associated with the specified thread.</span></span> <span data-ttu-id="e2d16-108">Si el subproceso no tiene ningún contexto asociado actualmente, esta función devolverá CORPROF_E_DATAINCOMPLETE.</span><span class="sxs-lookup"><span data-stu-id="e2d16-108">If the thread has no context currently associated with it, this function will return CORPROF_E_DATAINCOMPLETE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2d16-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e2d16-109">Requirements</span></span>  
 <span data-ttu-id="e2d16-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2d16-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2d16-111">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e2d16-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e2d16-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e2d16-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="e2d16-113">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="e2d16-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e2d16-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2d16-114">See also</span></span>

- [<span data-ttu-id="e2d16-115">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e2d16-115">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
