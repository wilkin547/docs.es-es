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
ms.openlocfilehash: b3ff579dee384b331450aa54aace39890febfe30
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99705946"
---
# <a name="icorprofilercallbackinitialize-method"></a><span data-ttu-id="5a380-103">ICorProfilerCallback::Initialize (Método)</span><span class="sxs-lookup"><span data-stu-id="5a380-103">ICorProfilerCallback::Initialize Method</span></span>

<span data-ttu-id="5a380-104">Se llama para inicializar el generador de perfiles de código cada vez que se inicia una nueva aplicación de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="5a380-104">Called to initialize the code profiler whenever a new common language runtime (CLR) application is started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a380-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5a380-105">Syntax</span></span>  
  
```cpp  
HRESULT Initialize(  
    [in] IUnknown     *pICorProfilerInfoUnk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a380-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5a380-106">Parameters</span></span>

- `pICorProfilerInfoUnk`

  <span data-ttu-id="5a380-107">\[in] puntero en una interfaz [IUnknown](/cpp/atl/iunknown) que el generador de perfiles debe consultar para un puntero de interfaz [ICorProfilerInfo](icorprofilerinfo-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="5a380-107">\[in] Pointer to an [IUnknown](/cpp/atl/iunknown) interface that the profiler must query for an [ICorProfilerInfo](icorprofilerinfo-interface.md) interface pointer.</span></span>  

## <a name="remarks"></a><span data-ttu-id="5a380-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5a380-108">Remarks</span></span>  

 <span data-ttu-id="5a380-109">La `Initialize` llamada es la única oportunidad para habilitar (o deshabilitar) las devoluciones de llamada que son inmutables.</span><span class="sxs-lookup"><span data-stu-id="5a380-109">The `Initialize` call is the only opportunity to enable (or disable) callbacks that are immutable.</span></span> <span data-ttu-id="5a380-110">Una vez que la llamada habilita una devolución de llamada `Initialize` , no se puede deshabilitar posteriormente mediante [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md).</span><span class="sxs-lookup"><span data-stu-id="5a380-110">Once a callback is enabled by the `Initialize` call, it cannot be disabled later using [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md).</span></span> <span data-ttu-id="5a380-111">El valor COR_PRF_MONITOR_IMMUTABLE de la enumeración [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) indica qué eventos son inmutables.</span><span class="sxs-lookup"><span data-stu-id="5a380-111">The COR_PRF_MONITOR_IMMUTABLE value of the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration indicates which events are immutable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a380-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5a380-112">Requirements</span></span>  

 <span data-ttu-id="5a380-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a380-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a380-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5a380-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5a380-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5a380-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5a380-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a380-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a380-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="5a380-117">See also</span></span>

- [<span data-ttu-id="5a380-118">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5a380-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="5a380-119">Método Shutdown</span><span class="sxs-lookup"><span data-stu-id="5a380-119">Shutdown Method</span></span>](icorprofilercallback-shutdown-method.md)
