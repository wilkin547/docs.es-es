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
ms.openlocfilehash: be8f4e396171f3e56b5b93969d3960b7aaea142e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780648"
---
# <a name="icorprofilerinfogethandlefromthread-method"></a><span data-ttu-id="b884d-102">ICorProfilerInfo::GetHandleFromThread (Método)</span><span class="sxs-lookup"><span data-stu-id="b884d-102">ICorProfilerInfo::GetHandleFromThread Method</span></span>
<span data-ttu-id="b884d-103">El identificador de un subproceso se asigna a un identificador de subproceso de Win32.</span><span class="sxs-lookup"><span data-stu-id="b884d-103">Maps the ID of a thread to a Win32 thread handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b884d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b884d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHandleFromThread(  
    [in]  ThreadID threadId,  
    [out] HANDLE  *phThread);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b884d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b884d-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="b884d-106">[in] El identificador de subproceso para asignarse.</span><span class="sxs-lookup"><span data-stu-id="b884d-106">[in] The thread ID to be mapped.</span></span>  
  
 `phThread`  
 <span data-ttu-id="b884d-107">[out] Un puntero a un identificador de subproceso de Win32.</span><span class="sxs-lookup"><span data-stu-id="b884d-107">[out] A pointer to a Win32 thread handle.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b884d-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b884d-108">Remarks</span></span>  
 <span data-ttu-id="b884d-109">El generador de perfiles debe llamar a Win32 `DuplicateHandle` función en el identificador antes de usarlo.</span><span class="sxs-lookup"><span data-stu-id="b884d-109">The profiler must call the Win32 `DuplicateHandle` function on the handle before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b884d-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b884d-110">Requirements</span></span>  
 <span data-ttu-id="b884d-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b884d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b884d-112">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b884d-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b884d-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b884d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b884d-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b884d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b884d-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="b884d-115">See also</span></span>

- [<span data-ttu-id="b884d-116">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b884d-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
