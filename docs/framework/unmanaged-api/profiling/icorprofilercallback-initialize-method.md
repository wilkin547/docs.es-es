---
title: "ICorProfilerCallback::Initialize (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.Initialize
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::Initialize
helpviewer_keywords:
- Initialize method, ICorProfilerCallback interface [.NET Framework profiling]
- ICorProfilerCallback::Initialize method [.NET Framework profiling]
ms.assetid: dc5fab2a-4b45-4b12-8727-b89c9915f23e
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2eebe596b3459d51afe66df4bb81f74e93f3526e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackinitialize-method"></a><span data-ttu-id="abe92-102">ICorProfilerCallback::Initialize (Método)</span><span class="sxs-lookup"><span data-stu-id="abe92-102">ICorProfilerCallback::Initialize Method</span></span>
<span data-ttu-id="abe92-103">Se llama para inicializar el generador de perfiles de código cada vez que se inicia una nueva aplicación de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="abe92-103">Called to initialize the code profiler whenever a new common language runtime (CLR) application is started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="abe92-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="abe92-104">Syntax</span></span>  
  
```  
HRESULT Initialize(  
    [in] IUnknown     *pICorProfilerInfoUnk);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="abe92-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="abe92-105">Parameters</span></span>  
 `pICorProfilerInfoUnk`  
 <span data-ttu-id="abe92-106">[en](/cpp/atl/iunknown) interfaz que el generador de perfiles debe consultar un [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) puntero de interfaz.</span><span class="sxs-lookup"><span data-stu-id="abe92-106">[in](/cpp/atl/iunknown) interface that the profiler must query for an [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) interface pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="abe92-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="abe92-107">Remarks</span></span>  
 <span data-ttu-id="abe92-108">El `Initialize` llamada es la única oportunidad para habilitar (o deshabilitar) devoluciones de llamada que son inmutables.</span><span class="sxs-lookup"><span data-stu-id="abe92-108">The `Initialize` call is the only opportunity to enable (or disable) callbacks that are immutable.</span></span> <span data-ttu-id="abe92-109">Una vez habilitada una devolución de llamada por el `Initialize` llamar a, no se puede deshabilitar posteriormente mediante [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md).</span><span class="sxs-lookup"><span data-stu-id="abe92-109">Once a callback is enabled by the `Initialize` call, it cannot be disabled later using [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md).</span></span> <span data-ttu-id="abe92-110">El valor COR_PRF_MONITOR_IMMUTABLE de la [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeración indica qué eventos son inmutables.</span><span class="sxs-lookup"><span data-stu-id="abe92-110">The COR_PRF_MONITOR_IMMUTABLE value of the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration indicates which events are immutable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="abe92-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="abe92-111">Requirements</span></span>  
 <span data-ttu-id="abe92-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="abe92-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="abe92-113">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="abe92-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="abe92-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="abe92-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="abe92-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="abe92-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abe92-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="abe92-116">See Also</span></span>  
 [<span data-ttu-id="abe92-117">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="abe92-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="abe92-118">Shutdown (método)</span><span class="sxs-lookup"><span data-stu-id="abe92-118">Shutdown Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-shutdown-method.md)
