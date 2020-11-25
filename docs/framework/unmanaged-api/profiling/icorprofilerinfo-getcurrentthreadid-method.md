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
ms.openlocfilehash: 18298c4c726d7d850e67afbf82ca77b7511d8917
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722601"
---
# <a name="icorprofilerinfogetcurrentthreadid-method"></a><span data-ttu-id="314c6-102">ICorProfilerInfo::GetCurrentThreadID (Método)</span><span class="sxs-lookup"><span data-stu-id="314c6-102">ICorProfilerInfo::GetCurrentThreadID Method</span></span>

<span data-ttu-id="314c6-103">Obtiene el identificador del subproceso actual, si es un subproceso administrado.</span><span class="sxs-lookup"><span data-stu-id="314c6-103">Gets the ID of the current thread, if it is a managed thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="314c6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="314c6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentThreadID(  
    [out] ThreadID *pThreadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="314c6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="314c6-105">Parameters</span></span>  

 `pThreadId`  
 <span data-ttu-id="314c6-106">enuncia Puntero al identificador devuelto del subproceso administrado.</span><span class="sxs-lookup"><span data-stu-id="314c6-106">[out] A pointer to the returned ID of the managed thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="314c6-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="314c6-107">Remarks</span></span>  

 <span data-ttu-id="314c6-108">Si el subproceso actual es un subproceso en tiempo de ejecución interno u otro subproceso no administrado, `GetCurrentThreadID` devuelve CORPROF_E_NOT_MANAGED_THREAD como HRESULT y el valor devuelto del `pThreadId` parámetro será null.</span><span class="sxs-lookup"><span data-stu-id="314c6-108">If the current thread is an internal runtime thread or other unmanaged thread, `GetCurrentThreadID` returns CORPROF_E_NOT_MANAGED_THREAD as the HRESULT, and the returned value of the `pThreadId` parameter will be null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="314c6-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="314c6-109">Requirements</span></span>  

 <span data-ttu-id="314c6-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="314c6-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="314c6-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="314c6-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="314c6-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="314c6-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="314c6-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="314c6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="314c6-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="314c6-114">See also</span></span>

- [<span data-ttu-id="314c6-115">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="314c6-115">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
