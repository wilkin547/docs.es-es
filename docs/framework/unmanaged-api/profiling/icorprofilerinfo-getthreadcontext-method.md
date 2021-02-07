---
description: 'Más información acerca de: ICorProfilerInfo:: GetThreadContext (método)'
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
ms.openlocfilehash: b2970da90250819cc68eee55b70188d4830113a6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99687279"
---
# <a name="icorprofilerinfogetthreadcontext-method"></a><span data-ttu-id="0a823-103">ICorProfilerInfo::GetThreadContext (Método)</span><span class="sxs-lookup"><span data-stu-id="0a823-103">ICorProfilerInfo::GetThreadContext Method</span></span>

<span data-ttu-id="0a823-104">Obtiene la identidad de contexto asociada actualmente al subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="0a823-104">Gets the context identity currently associated with the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a823-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0a823-105">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
    [in]  ThreadID  threadId,  
    [out] ContextID *pContextId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0a823-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0a823-106">Parameters</span></span>  

 `threadId`  
 <span data-ttu-id="0a823-107">de IDENTIFICADOR del subproceso.</span><span class="sxs-lookup"><span data-stu-id="0a823-107">[in] The ID of the thread.</span></span>  
  
 `pContextId`  
 <span data-ttu-id="0a823-108">enuncia Puntero al identificador de contexto asociado actualmente al subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="0a823-108">[out] A pointer to the context ID currently associated with the specified thread.</span></span> <span data-ttu-id="0a823-109">Si el subproceso no tiene ningún contexto asociado actualmente, esta función devolverá CORPROF_E_DATAINCOMPLETE.</span><span class="sxs-lookup"><span data-stu-id="0a823-109">If the thread has no context currently associated with it, this function will return CORPROF_E_DATAINCOMPLETE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a823-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0a823-110">Requirements</span></span>  

 <span data-ttu-id="0a823-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0a823-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a823-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0a823-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0a823-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0a823-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0a823-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a823-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a823-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="0a823-115">See also</span></span>

- [<span data-ttu-id="0a823-116">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0a823-116">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
