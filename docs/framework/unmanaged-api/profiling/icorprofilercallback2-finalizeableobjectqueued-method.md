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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b99a942d5c5fb205a84dd3766c99cc1126998de8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59190408"
---
# <a name="icorprofilercallback2finalizeableobjectqueued-method"></a><span data-ttu-id="997cd-102">ICorProfilerCallback2::FinalizeableObjectQueued (Método)</span><span class="sxs-lookup"><span data-stu-id="997cd-102">ICorProfilerCallback2::FinalizeableObjectQueued Method</span></span>
<span data-ttu-id="997cd-103">Notifica al generador de perfiles de código que un objeto con un finalizador se ha puesto en cola para el subproceso del finalizador para la ejecución de su `Finalize` método.</span><span class="sxs-lookup"><span data-stu-id="997cd-103">Notifies the code profiler that an object with a finalizer has been queued to the finalizer thread for execution of its `Finalize` method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="997cd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="997cd-104">Syntax</span></span>  
  
```  
HRESULT FinalizeableObjectQueued(  
    [in] DWORD finalizerFlags,  
    [in] ObjectID objectID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="997cd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="997cd-105">Parameters</span></span>  
 `finalizerFlags`  
 <span data-ttu-id="997cd-106">[in] Un valor de la [COR_PRF_FINALIZER_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-finalizer-flags-enumeration.md) enumeración que describe aspectos del finalizador.</span><span class="sxs-lookup"><span data-stu-id="997cd-106">[in] A value of the [COR_PRF_FINALIZER_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-finalizer-flags-enumeration.md) enumeration that describes aspects of the finalizer.</span></span>  
  
 `objectID`  
 <span data-ttu-id="997cd-107">[in] El identificador del objeto que se ha puesto en cola.</span><span class="sxs-lookup"><span data-stu-id="997cd-107">[in] The ID of the object that has been queued.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="997cd-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="997cd-108">Requirements</span></span>  
 <span data-ttu-id="997cd-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="997cd-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="997cd-110">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="997cd-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="997cd-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="997cd-111">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="997cd-112">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="997cd-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="997cd-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="997cd-113">See also</span></span>

- [<span data-ttu-id="997cd-114">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="997cd-114">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="997cd-115">ICorProfilerCallback2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="997cd-115">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
