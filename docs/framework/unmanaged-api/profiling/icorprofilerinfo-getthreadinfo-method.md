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
ms.openlocfilehash: 0631afe149c7a179a6cda4b5e491ad28653ddee9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59111922"
---
# <a name="icorprofilerinfogetthreadinfo-method"></a><span data-ttu-id="1f505-102">ICorProfilerInfo::GetThreadInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="1f505-102">ICorProfilerInfo::GetThreadInfo Method</span></span>
<span data-ttu-id="1f505-103">Obtiene la identidad del subproceso Win32 actual para el subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="1f505-103">Gets the current Win32 thread identity for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f505-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1f505-104">Syntax</span></span>  
  
```  
HRESULT GetThreadInfo(  
    [in]  ThreadID threadId,  
    [out] DWORD    *pdwWin32ThreadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1f505-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1f505-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="1f505-106">[in] El identificador del subproceso que se va a obtener el identificador de Win32 actual.</span><span class="sxs-lookup"><span data-stu-id="1f505-106">[in] The ID of the thread for which to get the current Win32 ID.</span></span>  
  
 `pdwWin32ThreadId`  
 <span data-ttu-id="1f505-107">[out] Identificador de un puntero al subproceso de Win32 actual del subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="1f505-107">[out] A pointer to the specified thread's current Win32 thread ID.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f505-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1f505-108">Requirements</span></span>  
 <span data-ttu-id="1f505-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1f505-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f505-110">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1f505-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1f505-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1f505-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1f505-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f505-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f505-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="1f505-113">See also</span></span>

- [<span data-ttu-id="1f505-114">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1f505-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
