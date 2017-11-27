---
title: "ICorProfilerCallback2::FinalizeableObjectQueued (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback2.FinalizeableObjectQueued
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback2::FinalizeableObjectQueued
helpviewer_keywords:
- FinalizeableObjectQueued method [.NET Framework profiling]
- ICorProfilerCallback2::FinalizeableObjectQueued method [.NET Framework profiling]
ms.assetid: 92d76893-683c-475d-9996-5bff03cdb10f
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7ff90fd6df337f7b92a73b43b6abc488da7ed6b7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallback2finalizeableobjectqueued-method"></a><span data-ttu-id="678d2-102">ICorProfilerCallback2::FinalizeableObjectQueued (Método)</span><span class="sxs-lookup"><span data-stu-id="678d2-102">ICorProfilerCallback2::FinalizeableObjectQueued Method</span></span>
<span data-ttu-id="678d2-103">Notifica al generador de perfiles de código que un objeto con un finalizador se ha puesto en cola en el subproceso finalizador para la ejecución de su `Finalize` método.</span><span class="sxs-lookup"><span data-stu-id="678d2-103">Notifies the code profiler that an object with a finalizer has been queued to the finalizer thread for execution of its `Finalize` method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="678d2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="678d2-104">Syntax</span></span>  
  
```  
HRESULT FinalizeableObjectQueued(  
    [in] DWORD finalizerFlags,  
    [in] ObjectID objectID);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="678d2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="678d2-105">Parameters</span></span>  
 `finalizerFlags`  
 <span data-ttu-id="678d2-106">[in] Un valor de la [COR_PRF_FINALIZER_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-finalizer-flags-enumeration.md) enumeración que describe aspectos del finalizador.</span><span class="sxs-lookup"><span data-stu-id="678d2-106">[in] A value of the [COR_PRF_FINALIZER_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-finalizer-flags-enumeration.md) enumeration that describes aspects of the finalizer.</span></span>  
  
 `objectID`  
 <span data-ttu-id="678d2-107">[in] El identificador del objeto que se ha puesto en cola.</span><span class="sxs-lookup"><span data-stu-id="678d2-107">[in] The ID of the object that has been queued.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="678d2-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="678d2-108">Requirements</span></span>  
 <span data-ttu-id="678d2-109">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="678d2-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="678d2-110">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="678d2-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="678d2-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="678d2-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="678d2-112">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="678d2-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="678d2-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="678d2-113">See Also</span></span>  
 [<span data-ttu-id="678d2-114">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="678d2-114">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="678d2-115">ICorProfilerCallback2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="678d2-115">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
