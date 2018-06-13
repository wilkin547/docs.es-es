---
title: ICorProfilerCallback2::ThreadNameChanged (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.ThreadNameChanged
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::ThreadNameChanged
helpviewer_keywords:
- ThreadNameChanged method [.NET Framework profiling]
- ICorProfilerCallback2::ThreadNameChanged method [.NET Framework profiling]
ms.assetid: c8bbd76d-a9ff-44f2-87a6-be052819da36
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6bf11d71b90f11a5d9a3844ed59a8574b7b76699
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452577"
---
# <a name="icorprofilercallback2threadnamechanged-method"></a><span data-ttu-id="da885-102">ICorProfilerCallback2::ThreadNameChanged (Método)</span><span class="sxs-lookup"><span data-stu-id="da885-102">ICorProfilerCallback2::ThreadNameChanged Method</span></span>
<span data-ttu-id="da885-103">Notifica al analizador de código que ha cambiado el nombre de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="da885-103">Notifies the code profiler that the name of a thread has changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da885-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="da885-104">Syntax</span></span>  
  
```  
HRESULT ThreadNameChanged(  
    [in] ThreadID threadId,  
    [in] ULONG cchName,  
    [in] WCHAR name[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="da885-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="da885-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="da885-106">[in] El identificador del subproceso.</span><span class="sxs-lookup"><span data-stu-id="da885-106">[in] The ID of the thread.</span></span>  
  
 `cchName`  
 <span data-ttu-id="da885-107">[in] La longitud del nuevo nombre del subproceso.</span><span class="sxs-lookup"><span data-stu-id="da885-107">[in] The length of the new name of the thread.</span></span>  
  
 `name`  
 <span data-ttu-id="da885-108">[in] El nuevo nombre del subproceso.</span><span class="sxs-lookup"><span data-stu-id="da885-108">[in] The new name of the thread.</span></span> <span data-ttu-id="da885-109">El nombre no está terminada en null.</span><span class="sxs-lookup"><span data-stu-id="da885-109">The name is not null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da885-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="da885-110">Requirements</span></span>  
 <span data-ttu-id="da885-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da885-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da885-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="da885-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="da885-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="da885-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="da885-114">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da885-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da885-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="da885-115">See Also</span></span>  
 [<span data-ttu-id="da885-116">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="da885-116">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="da885-117">ICorProfilerCallback2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="da885-117">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
