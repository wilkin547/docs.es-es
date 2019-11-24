---
title: ICorProfilerCallback2::FinalizeableObjectQueued (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.FinalizeableObjectQueued
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::FinalizeableObjectQueued
helpviewer_keywords:
- FinalizeableObjectQueued method [.NET Framework profiling]
- ICorProfilerCallback2::FinalizeableObjectQueued method [.NET Framework profiling]
ms.assetid: 92d76893-683c-475d-9996-5bff03cdb10f
topic_type:
- apiref
ms.openlocfilehash: ade0ba0517e47e9500683836b87d7a8ac1dfcfdb
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439853"
---
# <a name="icorprofilercallback2finalizeableobjectqueued-method"></a><span data-ttu-id="2bee0-102">ICorProfilerCallback2::FinalizeableObjectQueued (Método)</span><span class="sxs-lookup"><span data-stu-id="2bee0-102">ICorProfilerCallback2::FinalizeableObjectQueued Method</span></span>
<span data-ttu-id="2bee0-103">Notifies the code profiler that an object with a finalizer has been queued to the finalizer thread for execution of its `Finalize` method.</span><span class="sxs-lookup"><span data-stu-id="2bee0-103">Notifies the code profiler that an object with a finalizer has been queued to the finalizer thread for execution of its `Finalize` method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bee0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2bee0-104">Syntax</span></span>  
  
```cpp  
HRESULT FinalizeableObjectQueued(  
    [in] DWORD finalizerFlags,  
    [in] ObjectID objectID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2bee0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2bee0-105">Parameters</span></span>  
 `finalizerFlags`  
 <span data-ttu-id="2bee0-106">[in] A value of the [COR_PRF_FINALIZER_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-finalizer-flags-enumeration.md) enumeration that describes aspects of the finalizer.</span><span class="sxs-lookup"><span data-stu-id="2bee0-106">[in] A value of the [COR_PRF_FINALIZER_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-finalizer-flags-enumeration.md) enumeration that describes aspects of the finalizer.</span></span>  
  
 `objectID`  
 <span data-ttu-id="2bee0-107">[in] The ID of the object that has been queued.</span><span class="sxs-lookup"><span data-stu-id="2bee0-107">[in] The ID of the object that has been queued.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2bee0-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2bee0-108">Requirements</span></span>  
 <span data-ttu-id="2bee0-109">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2bee0-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2bee0-110">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2bee0-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2bee0-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2bee0-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2bee0-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2bee0-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bee0-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="2bee0-113">See also</span></span>

- [<span data-ttu-id="2bee0-114">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2bee0-114">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="2bee0-115">ICorProfilerCallback2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2bee0-115">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
