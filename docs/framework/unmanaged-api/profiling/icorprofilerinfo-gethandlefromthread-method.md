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
ms.openlocfilehash: 038f922eaaeb7d660cfbdcc0facb89677bdd154e
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863548"
---
# <a name="icorprofilerinfogethandlefromthread-method"></a><span data-ttu-id="95d70-102">ICorProfilerInfo::GetHandleFromThread (Método)</span><span class="sxs-lookup"><span data-stu-id="95d70-102">ICorProfilerInfo::GetHandleFromThread Method</span></span>
<span data-ttu-id="95d70-103">Asigna el identificador de un subproceso a un identificador de subproceso de Win32.</span><span class="sxs-lookup"><span data-stu-id="95d70-103">Maps the ID of a thread to a Win32 thread handle.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95d70-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="95d70-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHandleFromThread(  
    [in]  ThreadID threadId,  
    [out] HANDLE  *phThread);  
```  
  
## <a name="parameters"></a><span data-ttu-id="95d70-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="95d70-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="95d70-106">de IDENTIFICADOR del subproceso que se va a asignar.</span><span class="sxs-lookup"><span data-stu-id="95d70-106">[in] The thread ID to be mapped.</span></span>  
  
 `phThread`  
 <span data-ttu-id="95d70-107">enuncia Puntero a un identificador de subproceso de Win32.</span><span class="sxs-lookup"><span data-stu-id="95d70-107">[out] A pointer to a Win32 thread handle.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="95d70-108">Notas</span><span class="sxs-lookup"><span data-stu-id="95d70-108">Remarks</span></span>  
 <span data-ttu-id="95d70-109">El generador de perfiles debe llamar a la función `DuplicateHandle` de Win32 en el identificador antes de usarlo.</span><span class="sxs-lookup"><span data-stu-id="95d70-109">The profiler must call the Win32 `DuplicateHandle` function on the handle before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95d70-110">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="95d70-110">Requirements</span></span>  
 <span data-ttu-id="95d70-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95d70-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95d70-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="95d70-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="95d70-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="95d70-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="95d70-114">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95d70-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95d70-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="95d70-115">See also</span></span>

- [<span data-ttu-id="95d70-116">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="95d70-116">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
