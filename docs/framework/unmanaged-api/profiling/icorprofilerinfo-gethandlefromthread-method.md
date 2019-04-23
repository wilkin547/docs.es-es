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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8fc26ad9b25ad243bf868d6ef3155360509e6483
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59185749"
---
# <a name="icorprofilerinfogethandlefromthread-method"></a><span data-ttu-id="33ba5-102">ICorProfilerInfo::GetHandleFromThread (Método)</span><span class="sxs-lookup"><span data-stu-id="33ba5-102">ICorProfilerInfo::GetHandleFromThread Method</span></span>
<span data-ttu-id="33ba5-103">El identificador de un subproceso se asigna a un identificador de subproceso de Win32.</span><span class="sxs-lookup"><span data-stu-id="33ba5-103">Maps the ID of a thread to a Win32 thread handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33ba5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="33ba5-104">Syntax</span></span>  
  
```  
HRESULT GetHandleFromThread(  
    [in]  ThreadID threadId,  
    [out] HANDLE  *phThread);  
```  
  
## <a name="parameters"></a><span data-ttu-id="33ba5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="33ba5-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="33ba5-106">[in] El identificador de subproceso para asignarse.</span><span class="sxs-lookup"><span data-stu-id="33ba5-106">[in] The thread ID to be mapped.</span></span>  
  
 `phThread`  
 <span data-ttu-id="33ba5-107">[out] Un puntero a un identificador de subproceso de Win32.</span><span class="sxs-lookup"><span data-stu-id="33ba5-107">[out] A pointer to a Win32 thread handle.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="33ba5-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="33ba5-108">Remarks</span></span>  
 <span data-ttu-id="33ba5-109">El generador de perfiles debe llamar a Win32 `DuplicateHandle` función en el identificador antes de usarlo.</span><span class="sxs-lookup"><span data-stu-id="33ba5-109">The profiler must call the Win32 `DuplicateHandle` function on the handle before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33ba5-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="33ba5-110">Requirements</span></span>  
 <span data-ttu-id="33ba5-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33ba5-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33ba5-112">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="33ba5-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="33ba5-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="33ba5-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="33ba5-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33ba5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33ba5-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="33ba5-115">See also</span></span>

- [<span data-ttu-id="33ba5-116">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="33ba5-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
