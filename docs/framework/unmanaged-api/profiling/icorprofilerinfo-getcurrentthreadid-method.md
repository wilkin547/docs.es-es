---
description: 'Más información sobre: ICorProfilerInfo:: GetCurrentThreadID (método)'
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
ms.openlocfilehash: 562c6cb61f13e9ab568d18c7d179872cbc7cdb06
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99647649"
---
# <a name="icorprofilerinfogetcurrentthreadid-method"></a><span data-ttu-id="e6fa6-103">ICorProfilerInfo::GetCurrentThreadID (Método)</span><span class="sxs-lookup"><span data-stu-id="e6fa6-103">ICorProfilerInfo::GetCurrentThreadID Method</span></span>

<span data-ttu-id="e6fa6-104">Obtiene el identificador del subproceso actual, si es un subproceso administrado.</span><span class="sxs-lookup"><span data-stu-id="e6fa6-104">Gets the ID of the current thread, if it is a managed thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6fa6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e6fa6-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentThreadID(  
    [out] ThreadID *pThreadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6fa6-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e6fa6-106">Parameters</span></span>  

 `pThreadId`  
 <span data-ttu-id="e6fa6-107">enuncia Puntero al identificador devuelto del subproceso administrado.</span><span class="sxs-lookup"><span data-stu-id="e6fa6-107">[out] A pointer to the returned ID of the managed thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e6fa6-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e6fa6-108">Remarks</span></span>  

 <span data-ttu-id="e6fa6-109">Si el subproceso actual es un subproceso en tiempo de ejecución interno u otro subproceso no administrado, `GetCurrentThreadID` devuelve CORPROF_E_NOT_MANAGED_THREAD como HRESULT y el valor devuelto del `pThreadId` parámetro será null.</span><span class="sxs-lookup"><span data-stu-id="e6fa6-109">If the current thread is an internal runtime thread or other unmanaged thread, `GetCurrentThreadID` returns CORPROF_E_NOT_MANAGED_THREAD as the HRESULT, and the returned value of the `pThreadId` parameter will be null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6fa6-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e6fa6-110">Requirements</span></span>  

 <span data-ttu-id="e6fa6-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6fa6-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6fa6-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e6fa6-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e6fa6-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e6fa6-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e6fa6-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6fa6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6fa6-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="e6fa6-115">See also</span></span>

- [<span data-ttu-id="e6fa6-116">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e6fa6-116">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
