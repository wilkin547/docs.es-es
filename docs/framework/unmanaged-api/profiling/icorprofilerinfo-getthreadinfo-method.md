---
title: ICorProfilerInfo::GetThreadInfo (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetThreadInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetThreadInfo
helpviewer_keywords:
- ICorProfilerInfo::GetThreadInfo method [.NET Framework profiling]
- GetThreadInfo method [.NET Framework profiling]
ms.assetid: fc994fef-65c9-432a-84cb-66c8141147e7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 53bcc04c8d68a79217ebda5284efe7d8e18fdb91
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478783"
---
# <a name="icorprofilerinfogetthreadinfo-method"></a><span data-ttu-id="ac3ff-102">ICorProfilerInfo::GetThreadInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="ac3ff-102">ICorProfilerInfo::GetThreadInfo Method</span></span>
<span data-ttu-id="ac3ff-103">Obtiene la identidad del subproceso Win32 actual para el subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="ac3ff-103">Gets the current Win32 thread identity for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac3ff-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ac3ff-104">Syntax</span></span>  
  
```  
HRESULT GetThreadInfo(  
    [in]  ThreadID threadId,  
    [out] DWORD    *pdwWin32ThreadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ac3ff-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ac3ff-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="ac3ff-106">[in] El identificador del subproceso que se va a obtener el identificador de Win32 actual.</span><span class="sxs-lookup"><span data-stu-id="ac3ff-106">[in] The ID of the thread for which to get the current Win32 ID.</span></span>  
  
 `pdwWin32ThreadId`  
 <span data-ttu-id="ac3ff-107">[out] Identificador de un puntero al subproceso de Win32 actual del subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="ac3ff-107">[out] A pointer to the specified thread's current Win32 thread ID.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac3ff-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ac3ff-108">Requirements</span></span>  
 <span data-ttu-id="ac3ff-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac3ff-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac3ff-110">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ac3ff-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ac3ff-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ac3ff-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ac3ff-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac3ff-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac3ff-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="ac3ff-113">See also</span></span>
- [<span data-ttu-id="ac3ff-114">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ac3ff-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
