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
ms.openlocfilehash: f68565977551a54244f3caf6a0250f67005a6ecf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452887"
---
# <a name="icorprofilerinfogetthreadinfo-method"></a><span data-ttu-id="81e25-102">ICorProfilerInfo::GetThreadInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="81e25-102">ICorProfilerInfo::GetThreadInfo Method</span></span>
<span data-ttu-id="81e25-103">Obtiene la identidad del subproceso de Win32 actual para el subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="81e25-103">Gets the current Win32 thread identity for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81e25-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="81e25-104">Syntax</span></span>  
  
```  
HRESULT GetThreadInfo(  
    [in]  ThreadID threadId,  
    [out] DWORD    *pdwWin32ThreadId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="81e25-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="81e25-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="81e25-106">[in] El identificador del subproceso para el que se va a obtener el identificador de Win32 actual.</span><span class="sxs-lookup"><span data-stu-id="81e25-106">[in] The ID of the thread for which to get the current Win32 ID.</span></span>  
  
 `pdwWin32ThreadId`  
 <span data-ttu-id="81e25-107">[out] Identificador de un puntero al subproceso de Win32 actual del subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="81e25-107">[out] A pointer to the specified thread's current Win32 thread ID.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81e25-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="81e25-108">Requirements</span></span>  
 <span data-ttu-id="81e25-109">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81e25-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81e25-110">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="81e25-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="81e25-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="81e25-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="81e25-112">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81e25-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81e25-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="81e25-113">See Also</span></span>  
 [<span data-ttu-id="81e25-114">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="81e25-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
