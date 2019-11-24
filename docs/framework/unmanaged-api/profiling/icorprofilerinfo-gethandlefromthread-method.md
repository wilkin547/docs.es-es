---
title: ICorProfilerInfo::GetHandleFromThread (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetHandleFromThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetHandleFromThread
helpviewer_keywords:
- GetHandleFromThread method [.NET Framework profiling]
- ICorProfilerInfo::GetHandleFromThread method [.NET Framework profiling]
ms.assetid: 36cdc9f5-7579-4cd2-aa36-fc05c741584c
topic_type:
- apiref
ms.openlocfilehash: e508ccd81d25aa3d303456fa88554903ec71d633
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439066"
---
# <a name="icorprofilerinfogethandlefromthread-method"></a><span data-ttu-id="bb3ab-102">ICorProfilerInfo::GetHandleFromThread (Método)</span><span class="sxs-lookup"><span data-stu-id="bb3ab-102">ICorProfilerInfo::GetHandleFromThread Method</span></span>
<span data-ttu-id="bb3ab-103">Maps the ID of a thread to a Win32 thread handle.</span><span class="sxs-lookup"><span data-stu-id="bb3ab-103">Maps the ID of a thread to a Win32 thread handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb3ab-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bb3ab-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHandleFromThread(  
    [in]  ThreadID threadId,  
    [out] HANDLE  *phThread);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bb3ab-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bb3ab-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="bb3ab-106">[in] The thread ID to be mapped.</span><span class="sxs-lookup"><span data-stu-id="bb3ab-106">[in] The thread ID to be mapped.</span></span>  
  
 `phThread`  
 <span data-ttu-id="bb3ab-107">[out] A pointer to a Win32 thread handle.</span><span class="sxs-lookup"><span data-stu-id="bb3ab-107">[out] A pointer to a Win32 thread handle.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bb3ab-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bb3ab-108">Remarks</span></span>  
 <span data-ttu-id="bb3ab-109">The profiler must call the Win32 `DuplicateHandle` function on the handle before using it.</span><span class="sxs-lookup"><span data-stu-id="bb3ab-109">The profiler must call the Win32 `DuplicateHandle` function on the handle before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb3ab-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bb3ab-110">Requirements</span></span>  
 <span data-ttu-id="bb3ab-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb3ab-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb3ab-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bb3ab-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bb3ab-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bb3ab-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bb3ab-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb3ab-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb3ab-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="bb3ab-115">See also</span></span>

- [<span data-ttu-id="bb3ab-116">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bb3ab-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
