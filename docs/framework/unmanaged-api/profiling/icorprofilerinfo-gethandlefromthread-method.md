---
title: "ICorProfilerInfo::GetHandleFromThread (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 465fb61d17269873b3a2aa2f323086f209cab946
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfogethandlefromthread-method"></a><span data-ttu-id="24f8c-102">ICorProfilerInfo::GetHandleFromThread (Método)</span><span class="sxs-lookup"><span data-stu-id="24f8c-102">ICorProfilerInfo::GetHandleFromThread Method</span></span>
<span data-ttu-id="24f8c-103">El identificador de un subproceso se asigna a un identificador de subproceso de Win32.</span><span class="sxs-lookup"><span data-stu-id="24f8c-103">Maps the ID of a thread to a Win32 thread handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24f8c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="24f8c-104">Syntax</span></span>  
  
```  
HRESULT GetHandleFromThread(  
    [in]  ThreadID threadId,  
    [out] HANDLE  *phThread);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="24f8c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="24f8c-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="24f8c-106">[in] El identificador del subproceso que debe asignarse.</span><span class="sxs-lookup"><span data-stu-id="24f8c-106">[in] The thread ID to be mapped.</span></span>  
  
 `phThread`  
 <span data-ttu-id="24f8c-107">[out] Un puntero a un identificador de subproceso de Win32.</span><span class="sxs-lookup"><span data-stu-id="24f8c-107">[out] A pointer to a Win32 thread handle.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="24f8c-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="24f8c-108">Remarks</span></span>  
 <span data-ttu-id="24f8c-109">El generador de perfiles debe llamar a Win32 `DuplicateHandle` función en el identificador antes de usarlo.</span><span class="sxs-lookup"><span data-stu-id="24f8c-109">The profiler must call the Win32 `DuplicateHandle` function on the handle before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24f8c-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="24f8c-110">Requirements</span></span>  
 <span data-ttu-id="24f8c-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24f8c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24f8c-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="24f8c-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="24f8c-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="24f8c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="24f8c-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24f8c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24f8c-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="24f8c-115">See Also</span></span>  
 [<span data-ttu-id="24f8c-116">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="24f8c-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
