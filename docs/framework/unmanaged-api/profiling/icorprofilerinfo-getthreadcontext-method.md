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
ms.openlocfilehash: 45ae164e79f077549a1d685aa060484240546a10
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84497964"
---
# <a name="icorprofilerinfogetthreadcontext-method"></a><span data-ttu-id="accf9-102">ICorProfilerInfo::GetThreadContext (Método)</span><span class="sxs-lookup"><span data-stu-id="accf9-102">ICorProfilerInfo::GetThreadContext Method</span></span>
<span data-ttu-id="accf9-103">Obtiene la identidad de contexto asociada actualmente al subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="accf9-103">Gets the context identity currently associated with the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="accf9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="accf9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
    [in]  ThreadID  threadId,  
    [out] ContextID *pContextId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="accf9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="accf9-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="accf9-106">de IDENTIFICADOR del subproceso.</span><span class="sxs-lookup"><span data-stu-id="accf9-106">[in] The ID of the thread.</span></span>  
  
 `pContextId`  
 <span data-ttu-id="accf9-107">enuncia Puntero al identificador de contexto asociado actualmente al subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="accf9-107">[out] A pointer to the context ID currently associated with the specified thread.</span></span> <span data-ttu-id="accf9-108">Si el subproceso no tiene ningún contexto asociado actualmente, esta función devolverá CORPROF_E_DATAINCOMPLETE.</span><span class="sxs-lookup"><span data-stu-id="accf9-108">If the thread has no context currently associated with it, this function will return CORPROF_E_DATAINCOMPLETE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="accf9-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="accf9-109">Requirements</span></span>  
 <span data-ttu-id="accf9-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="accf9-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="accf9-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="accf9-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="accf9-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="accf9-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="accf9-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="accf9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="accf9-114">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="accf9-114">See also</span></span>

- [<span data-ttu-id="accf9-115">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="accf9-115">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
