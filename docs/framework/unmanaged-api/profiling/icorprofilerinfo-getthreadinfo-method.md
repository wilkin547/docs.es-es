---
title: "ICorProfilerInfo::GetThreadInfo (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetThreadInfo
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::GetThreadInfo
helpviewer_keywords:
- ICorProfilerInfo::GetThreadInfo method [.NET Framework profiling]
- GetThreadInfo method [.NET Framework profiling]
ms.assetid: fc994fef-65c9-432a-84cb-66c8141147e7
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 4c4657279e145dbb923c339ed0114723620e7aa7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfogetthreadinfo-method"></a><span data-ttu-id="3271c-102">ICorProfilerInfo::GetThreadInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="3271c-102">ICorProfilerInfo::GetThreadInfo Method</span></span>
<span data-ttu-id="3271c-103">Obtiene la identidad del subproceso de Win32 actual para el subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="3271c-103">Gets the current Win32 thread identity for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3271c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3271c-104">Syntax</span></span>  
  
```  
HRESULT GetThreadInfo(  
    [in]  ThreadID threadId,  
    [out] DWORD    *pdwWin32ThreadId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3271c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3271c-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="3271c-106">[in] El identificador del subproceso para el que se va a obtener el identificador de Win32 actual.</span><span class="sxs-lookup"><span data-stu-id="3271c-106">[in] The ID of the thread for which to get the current Win32 ID.</span></span>  
  
 `pdwWin32ThreadId`  
 <span data-ttu-id="3271c-107">[out] Identificador de un puntero al subproceso de Win32 actual del subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="3271c-107">[out] A pointer to the specified thread's current Win32 thread ID.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3271c-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3271c-108">Requirements</span></span>  
 <span data-ttu-id="3271c-109">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3271c-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3271c-110">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3271c-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3271c-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3271c-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3271c-112">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3271c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3271c-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="3271c-113">See Also</span></span>  
 [<span data-ttu-id="3271c-114">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3271c-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
