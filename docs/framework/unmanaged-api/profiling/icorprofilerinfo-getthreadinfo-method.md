---
description: 'Más información acerca de: ICorProfilerInfo:: GetThreadInfo ((método)'
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
ms.openlocfilehash: 5514b1c4860067a07bf922e9d9a8bfab8c05e218
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760555"
---
# <a name="icorprofilerinfogetthreadinfo-method"></a><span data-ttu-id="f68ec-103">ICorProfilerInfo::GetThreadInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="f68ec-103">ICorProfilerInfo::GetThreadInfo Method</span></span>

<span data-ttu-id="f68ec-104">Obtiene la identidad del subproceso de Win32 actual para el subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="f68ec-104">Gets the current Win32 thread identity for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f68ec-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f68ec-105">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadInfo(  
    [in]  ThreadID threadId,  
    [out] DWORD    *pdwWin32ThreadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f68ec-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f68ec-106">Parameters</span></span>  

 `threadId`  
 <span data-ttu-id="f68ec-107">de IDENTIFICADOR del subproceso para el que se va a obtener el ID. de Win32 actual.</span><span class="sxs-lookup"><span data-stu-id="f68ec-107">[in] The ID of the thread for which to get the current Win32 ID.</span></span>  
  
 `pdwWin32ThreadId`  
 <span data-ttu-id="f68ec-108">enuncia Puntero al identificador de subproceso actual de Win32 del subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="f68ec-108">[out] A pointer to the specified thread's current Win32 thread ID.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f68ec-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f68ec-109">Requirements</span></span>  

 <span data-ttu-id="f68ec-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f68ec-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f68ec-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f68ec-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f68ec-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f68ec-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f68ec-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f68ec-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f68ec-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="f68ec-114">See also</span></span>

- [<span data-ttu-id="f68ec-115">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f68ec-115">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
