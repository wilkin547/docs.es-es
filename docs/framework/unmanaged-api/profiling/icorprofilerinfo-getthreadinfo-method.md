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
ms.openlocfilehash: 7318d7d1494b0cf4db54b92ff09775be5500bdb1
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76869587"
---
# <a name="icorprofilerinfogetthreadinfo-method"></a><span data-ttu-id="f0913-102">ICorProfilerInfo::GetThreadInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="f0913-102">ICorProfilerInfo::GetThreadInfo Method</span></span>
<span data-ttu-id="f0913-103">Obtiene la identidad del subproceso de Win32 actual para el subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="f0913-103">Gets the current Win32 thread identity for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0913-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f0913-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadInfo(  
    [in]  ThreadID threadId,  
    [out] DWORD    *pdwWin32ThreadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0913-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="f0913-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="f0913-106">de IDENTIFICADOR del subproceso para el que se va a obtener el ID. de Win32 actual.</span><span class="sxs-lookup"><span data-stu-id="f0913-106">[in] The ID of the thread for which to get the current Win32 ID.</span></span>  
  
 `pdwWin32ThreadId`  
 <span data-ttu-id="f0913-107">enuncia Puntero al identificador de subproceso actual de Win32 del subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="f0913-107">[out] A pointer to the specified thread's current Win32 thread ID.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0913-108">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="f0913-108">Requirements</span></span>  
 <span data-ttu-id="f0913-109">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0913-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0913-110">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f0913-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f0913-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0913-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f0913-112">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0913-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0913-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="f0913-113">See also</span></span>

- [<span data-ttu-id="f0913-114">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f0913-114">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
