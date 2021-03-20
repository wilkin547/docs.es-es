---
description: 'Más información acerca de: ICorProfilerCallback:: Initialize (método)'
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
ms.openlocfilehash: c7138a1a39a1d32c751c205a86c00e6070a236b3
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2021
ms.locfileid: "104760423"
---
# <a name="icorprofilercallbackinitialize-method"></a><span data-ttu-id="e14ed-103">ICorProfilerCallback::Initialize (Método)</span><span class="sxs-lookup"><span data-stu-id="e14ed-103">ICorProfilerCallback::Initialize Method</span></span>

<span data-ttu-id="e14ed-104">Se llama para inicializar el generador de perfiles de código cada vez que se inicia una nueva aplicación de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="e14ed-104">Called to initialize the code profiler whenever a new common language runtime (CLR) application is started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e14ed-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e14ed-105">Syntax</span></span>  
  
```cpp  
HRESULT Initialize(  
    [in] IUnknown     *pICorProfilerInfoUnk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e14ed-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e14ed-106">Parameters</span></span>

<span data-ttu-id="e14ed-107">`pICorProfilerInfoUnk` de Puntero a una interfaz [IUnknown](/cpp/atl/iunknown) que el generador de perfiles debe consultar para un puntero de interfaz [ICorProfilerInfo](icorprofilerinfo-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="e14ed-107">`pICorProfilerInfoUnk` [in] Pointer to an [IUnknown](/cpp/atl/iunknown) interface that the profiler must query for an [ICorProfilerInfo](icorprofilerinfo-interface.md) interface pointer.</span></span>  

## <a name="remarks"></a><span data-ttu-id="e14ed-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e14ed-108">Remarks</span></span>  

 <span data-ttu-id="e14ed-109">La `Initialize` llamada es la única oportunidad para habilitar (o deshabilitar) las devoluciones de llamada que son inmutables.</span><span class="sxs-lookup"><span data-stu-id="e14ed-109">The `Initialize` call is the only opportunity to enable (or disable) callbacks that are immutable.</span></span> <span data-ttu-id="e14ed-110">Una vez que la llamada habilita una devolución de llamada `Initialize` , no se puede deshabilitar posteriormente mediante [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md).</span><span class="sxs-lookup"><span data-stu-id="e14ed-110">Once a callback is enabled by the `Initialize` call, it cannot be disabled later using [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md).</span></span> <span data-ttu-id="e14ed-111">El valor COR_PRF_MONITOR_IMMUTABLE de la enumeración [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) indica qué eventos son inmutables.</span><span class="sxs-lookup"><span data-stu-id="e14ed-111">The COR_PRF_MONITOR_IMMUTABLE value of the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration indicates which events are immutable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e14ed-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e14ed-112">Requirements</span></span>  

 <span data-ttu-id="e14ed-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e14ed-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e14ed-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e14ed-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e14ed-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e14ed-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e14ed-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e14ed-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e14ed-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e14ed-117">See also</span></span>

- [<span data-ttu-id="e14ed-118">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e14ed-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="e14ed-119">Método Shutdown</span><span class="sxs-lookup"><span data-stu-id="e14ed-119">Shutdown Method</span></span>](icorprofilercallback-shutdown-method.md)
