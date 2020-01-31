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
ms.openlocfilehash: e4a003b30c495852a3a68d44d92bef35c3ed7812
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866304"
---
# <a name="icorprofilercallbackinitialize-method"></a><span data-ttu-id="5e6a9-102">ICorProfilerCallback::Initialize (Método)</span><span class="sxs-lookup"><span data-stu-id="5e6a9-102">ICorProfilerCallback::Initialize Method</span></span>
<span data-ttu-id="5e6a9-103">Se llama para inicializar el generador de perfiles de código cada vez que se inicia una nueva aplicación de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="5e6a9-103">Called to initialize the code profiler whenever a new common language runtime (CLR) application is started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e6a9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5e6a9-104">Syntax</span></span>  
  
```cpp  
HRESULT Initialize(  
    [in] IUnknown     *pICorProfilerInfoUnk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5e6a9-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="5e6a9-105">Parameters</span></span>

- `pICorProfilerInfoUnk`

  <span data-ttu-id="5e6a9-106">\[in] puntero en una interfaz [IUnknown](/cpp/atl/iunknown) que el generador de perfiles debe consultar para un puntero de interfaz [ICorProfilerInfo](icorprofilerinfo-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="5e6a9-106">\[in] Pointer to an [IUnknown](/cpp/atl/iunknown) interface that the profiler must query for an [ICorProfilerInfo](icorprofilerinfo-interface.md) interface pointer.</span></span>  

## <a name="remarks"></a><span data-ttu-id="5e6a9-107">Notas</span><span class="sxs-lookup"><span data-stu-id="5e6a9-107">Remarks</span></span>  
 <span data-ttu-id="5e6a9-108">La llamada a `Initialize` es la única oportunidad para habilitar (o deshabilitar) las devoluciones de llamada inmutables.</span><span class="sxs-lookup"><span data-stu-id="5e6a9-108">The `Initialize` call is the only opportunity to enable (or disable) callbacks that are immutable.</span></span> <span data-ttu-id="5e6a9-109">Una vez que la llamada a `Initialize` habilita una devolución de llamada, no se puede deshabilitar posteriormente mediante [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md).</span><span class="sxs-lookup"><span data-stu-id="5e6a9-109">Once a callback is enabled by the `Initialize` call, it cannot be disabled later using [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md).</span></span> <span data-ttu-id="5e6a9-110">El valor COR_PRF_MONITOR_IMMUTABLE de la enumeración [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) indica qué eventos son inmutables.</span><span class="sxs-lookup"><span data-stu-id="5e6a9-110">The COR_PRF_MONITOR_IMMUTABLE value of the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration indicates which events are immutable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e6a9-111">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="5e6a9-111">Requirements</span></span>  
 <span data-ttu-id="5e6a9-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e6a9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e6a9-113">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5e6a9-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5e6a9-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5e6a9-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5e6a9-115">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e6a9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e6a9-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e6a9-116">See also</span></span>

- [<span data-ttu-id="5e6a9-117">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5e6a9-117">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="5e6a9-118">Shutdown (método)</span><span class="sxs-lookup"><span data-stu-id="5e6a9-118">Shutdown Method</span></span>](icorprofilercallback-shutdown-method.md)
