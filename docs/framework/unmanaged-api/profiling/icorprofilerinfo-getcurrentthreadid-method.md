---
title: ICorProfilerInfo::GetCurrentThreadID (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetCurrentThreadID
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetCurrentThreadID
helpviewer_keywords:
- GetCurrentThreadID method, ICorProfilerInfo interface [.NET Framework profiling]
- ICorProfilerInfo::GetCurrentThreadID method [.NET Framework profiling]
ms.assetid: 39bbdb30-6a7a-4202-8da3-67ae9a0ab3a8
topic_type:
- apiref
ms.openlocfilehash: fa0fe827300a86a906a254292434e2a56ebb4a47
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84498406"
---
# <a name="icorprofilerinfogetcurrentthreadid-method"></a><span data-ttu-id="0c8fa-102">ICorProfilerInfo::GetCurrentThreadID (Método)</span><span class="sxs-lookup"><span data-stu-id="0c8fa-102">ICorProfilerInfo::GetCurrentThreadID Method</span></span>
<span data-ttu-id="0c8fa-103">Obtiene el identificador del subproceso actual, si es un subproceso administrado.</span><span class="sxs-lookup"><span data-stu-id="0c8fa-103">Gets the ID of the current thread, if it is a managed thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c8fa-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0c8fa-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentThreadID(  
    [out] ThreadID *pThreadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c8fa-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0c8fa-105">Parameters</span></span>  
 `pThreadId`  
 <span data-ttu-id="0c8fa-106">enuncia Puntero al identificador devuelto del subproceso administrado.</span><span class="sxs-lookup"><span data-stu-id="0c8fa-106">[out] A pointer to the returned ID of the managed thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c8fa-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0c8fa-107">Remarks</span></span>  
 <span data-ttu-id="0c8fa-108">Si el subproceso actual es un subproceso en tiempo de ejecución interno u otro subproceso no administrado, `GetCurrentThreadID` devuelve CORPROF_E_NOT_MANAGED_THREAD como HRESULT y el valor devuelto del `pThreadId` parámetro será null.</span><span class="sxs-lookup"><span data-stu-id="0c8fa-108">If the current thread is an internal runtime thread or other unmanaged thread, `GetCurrentThreadID` returns CORPROF_E_NOT_MANAGED_THREAD as the HRESULT, and the returned value of the `pThreadId` parameter will be null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c8fa-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0c8fa-109">Requirements</span></span>  
 <span data-ttu-id="0c8fa-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c8fa-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c8fa-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0c8fa-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0c8fa-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0c8fa-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0c8fa-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c8fa-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c8fa-114">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="0c8fa-114">See also</span></span>

- [<span data-ttu-id="0c8fa-115">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0c8fa-115">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
