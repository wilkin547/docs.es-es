---
title: ICorProfilerCallback::Initialize (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.Initialize
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::Initialize
helpviewer_keywords:
- Initialize method, ICorProfilerCallback interface [.NET Framework profiling]
- ICorProfilerCallback::Initialize method [.NET Framework profiling]
ms.assetid: dc5fab2a-4b45-4b12-8727-b89c9915f23e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 16001c4af2bcd8aa8d5fff6b06fa8c275bc24cb9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59191008"
---
# <a name="icorprofilercallbackinitialize-method"></a><span data-ttu-id="12b26-102">ICorProfilerCallback::Initialize (Método)</span><span class="sxs-lookup"><span data-stu-id="12b26-102">ICorProfilerCallback::Initialize Method</span></span>
<span data-ttu-id="12b26-103">Se llama para inicializar el generador de perfiles de código cuando se inicia una nueva aplicación de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="12b26-103">Called to initialize the code profiler whenever a new common language runtime (CLR) application is started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12b26-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="12b26-104">Syntax</span></span>  
  
```  
HRESULT Initialize(  
    [in] IUnknown     *pICorProfilerInfoUnk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="12b26-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="12b26-105">Parameters</span></span>  
 `pICorProfilerInfoUnk`  
 <span data-ttu-id="12b26-106">[en](/cpp/atl/iunknown) interfaz que el generador de perfiles debe consultar un [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) puntero de interfaz.</span><span class="sxs-lookup"><span data-stu-id="12b26-106">[in](/cpp/atl/iunknown) interface that the profiler must query for an [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) interface pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="12b26-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="12b26-107">Remarks</span></span>  
 <span data-ttu-id="12b26-108">El `Initialize` llamada es la única oportunidad de habilitar (o deshabilitar) las devoluciones de llamada que son inmutables.</span><span class="sxs-lookup"><span data-stu-id="12b26-108">The `Initialize` call is the only opportunity to enable (or disable) callbacks that are immutable.</span></span> <span data-ttu-id="12b26-109">Una vez que una devolución de llamada está habilitada de forma el `Initialize` llamar a, no puede deshabilitarse más adelante mediante [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md).</span><span class="sxs-lookup"><span data-stu-id="12b26-109">Once a callback is enabled by the `Initialize` call, it cannot be disabled later using [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md).</span></span> <span data-ttu-id="12b26-110">El valor COR_PRF_MONITOR_IMMUTABLE de la [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeración indica qué eventos son inmutables.</span><span class="sxs-lookup"><span data-stu-id="12b26-110">The COR_PRF_MONITOR_IMMUTABLE value of the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration indicates which events are immutable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12b26-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="12b26-111">Requirements</span></span>  
 <span data-ttu-id="12b26-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="12b26-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12b26-113">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="12b26-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="12b26-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="12b26-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="12b26-115">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="12b26-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="12b26-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="12b26-116">See also</span></span>

- [<span data-ttu-id="12b26-117">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="12b26-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="12b26-118">Método Shutdown</span><span class="sxs-lookup"><span data-stu-id="12b26-118">Shutdown Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-shutdown-method.md)
