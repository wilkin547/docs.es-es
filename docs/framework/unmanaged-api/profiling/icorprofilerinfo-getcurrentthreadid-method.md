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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 89f7ff2c213dc510268f9e6c802813a48e870d99
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33453863"
---
# <a name="icorprofilerinfogetcurrentthreadid-method"></a><span data-ttu-id="5738e-102">ICorProfilerInfo::GetCurrentThreadID (Método)</span><span class="sxs-lookup"><span data-stu-id="5738e-102">ICorProfilerInfo::GetCurrentThreadID Method</span></span>
<span data-ttu-id="5738e-103">Obtiene el identificador del subproceso actual, si es un subproceso administrado.</span><span class="sxs-lookup"><span data-stu-id="5738e-103">Gets the ID of the current thread, if it is a managed thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5738e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5738e-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentThreadID(  
    [out] ThreadID *pThreadId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5738e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5738e-105">Parameters</span></span>  
 `pThreadId`  
 <span data-ttu-id="5738e-106">[out] Un puntero al identificador devuelto del subproceso administrado.</span><span class="sxs-lookup"><span data-stu-id="5738e-106">[out] A pointer to the returned ID of the managed thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5738e-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5738e-107">Remarks</span></span>  
 <span data-ttu-id="5738e-108">Si el subproceso actual es un subproceso en tiempo de ejecución interno u otro subproceso no administrado, `GetCurrentThreadID` devuelve CORPROF_E_NOT_MANAGED_THREAD como HRESULT y el valor devuelto de la `pThreadId` parámetro será nulo.</span><span class="sxs-lookup"><span data-stu-id="5738e-108">If the current thread is an internal runtime thread or other unmanaged thread, `GetCurrentThreadID` returns CORPROF_E_NOT_MANAGED_THREAD as the HRESULT, and the returned value of the `pThreadId` parameter will be null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5738e-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5738e-109">Requirements</span></span>  
 <span data-ttu-id="5738e-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5738e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5738e-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5738e-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5738e-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5738e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5738e-113">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5738e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5738e-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="5738e-114">See Also</span></span>  
 [<span data-ttu-id="5738e-115">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5738e-115">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
