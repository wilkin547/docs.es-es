---
title: "ICorProfilerInfo::GetThreadContext (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetThreadContext
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::GetThreadContext
helpviewer_keywords:
- ICorProfilerInfo::GetThreadContext method [.NET Framework profiling]
- GetThreadContext method, ICorProfilerInfo interface [.NET Framework profiling]
ms.assetid: 79446216-4b8b-484c-8fe3-e87dbf9df2fd
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8f2802c89a72b6c6c9e268d9d35767ca5b6dadce
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfogetthreadcontext-method"></a><span data-ttu-id="a6ba0-102">ICorProfilerInfo::GetThreadContext (Método)</span><span class="sxs-lookup"><span data-stu-id="a6ba0-102">ICorProfilerInfo::GetThreadContext Method</span></span>
<span data-ttu-id="a6ba0-103">Obtiene la identidad del contexto asociada actualmente al subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="a6ba0-103">Gets the context identity currently associated with the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6ba0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a6ba0-104">Syntax</span></span>  
  
```  
HRESULT GetThreadContext(  
    [in]  ThreadID  threadId,  
    [out] ContextID *pContextId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a6ba0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a6ba0-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="a6ba0-106">[in] El identificador del subproceso.</span><span class="sxs-lookup"><span data-stu-id="a6ba0-106">[in] The ID of the thread.</span></span>  
  
 `pContextId`  
 <span data-ttu-id="a6ba0-107">[out] Un puntero al identificador del contexto asociado actualmente al subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="a6ba0-107">[out] A pointer to the context ID currently associated with the specified thread.</span></span> <span data-ttu-id="a6ba0-108">Si un subproceso no tiene ningún contexto asociado actualmente, esta función devolverá CORPROF_E_DATAINCOMPLETE.</span><span class="sxs-lookup"><span data-stu-id="a6ba0-108">If the thread has no context currently associated with it, this function will return CORPROF_E_DATAINCOMPLETE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6ba0-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a6ba0-109">Requirements</span></span>  
 <span data-ttu-id="a6ba0-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6ba0-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6ba0-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a6ba0-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a6ba0-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a6ba0-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a6ba0-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6ba0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6ba0-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="a6ba0-114">See Also</span></span>  
 [<span data-ttu-id="a6ba0-115">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a6ba0-115">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
