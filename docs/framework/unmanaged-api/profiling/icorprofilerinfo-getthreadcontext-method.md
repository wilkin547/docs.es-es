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
ms.openlocfilehash: 2e24d72c8be1ace10b2feb15101ed8f83db386c2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724096"
---
# <a name="icorprofilerinfogetthreadcontext-method"></a><span data-ttu-id="aab9f-102">ICorProfilerInfo::GetThreadContext (Método)</span><span class="sxs-lookup"><span data-stu-id="aab9f-102">ICorProfilerInfo::GetThreadContext Method</span></span>

<span data-ttu-id="aab9f-103">Obtiene la identidad de contexto asociada actualmente al subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="aab9f-103">Gets the context identity currently associated with the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aab9f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aab9f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
    [in]  ThreadID  threadId,  
    [out] ContextID *pContextId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aab9f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="aab9f-105">Parameters</span></span>  

 `threadId`  
 <span data-ttu-id="aab9f-106">de IDENTIFICADOR del subproceso.</span><span class="sxs-lookup"><span data-stu-id="aab9f-106">[in] The ID of the thread.</span></span>  
  
 `pContextId`  
 <span data-ttu-id="aab9f-107">enuncia Puntero al identificador de contexto asociado actualmente al subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="aab9f-107">[out] A pointer to the context ID currently associated with the specified thread.</span></span> <span data-ttu-id="aab9f-108">Si el subproceso no tiene ningún contexto asociado actualmente, esta función devolverá CORPROF_E_DATAINCOMPLETE.</span><span class="sxs-lookup"><span data-stu-id="aab9f-108">If the thread has no context currently associated with it, this function will return CORPROF_E_DATAINCOMPLETE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aab9f-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="aab9f-109">Requirements</span></span>  

 <span data-ttu-id="aab9f-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aab9f-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aab9f-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="aab9f-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="aab9f-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aab9f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aab9f-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aab9f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aab9f-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="aab9f-114">See also</span></span>

- [<span data-ttu-id="aab9f-115">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="aab9f-115">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
