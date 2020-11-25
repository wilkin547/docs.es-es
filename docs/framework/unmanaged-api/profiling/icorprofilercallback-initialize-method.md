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
ms.openlocfilehash: 26df1599af247bd08d3702d4ef3c5aa2f648620c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720378"
---
# <a name="icorprofilercallbackinitialize-method"></a><span data-ttu-id="faf2a-102">ICorProfilerCallback::Initialize (Método)</span><span class="sxs-lookup"><span data-stu-id="faf2a-102">ICorProfilerCallback::Initialize Method</span></span>

<span data-ttu-id="faf2a-103">Se llama para inicializar el generador de perfiles de código cada vez que se inicia una nueva aplicación de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="faf2a-103">Called to initialize the code profiler whenever a new common language runtime (CLR) application is started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="faf2a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="faf2a-104">Syntax</span></span>  
  
```cpp  
HRESULT Initialize(  
    [in] IUnknown     *pICorProfilerInfoUnk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="faf2a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="faf2a-105">Parameters</span></span>

- `pICorProfilerInfoUnk`

  <span data-ttu-id="faf2a-106">\[in] puntero en una interfaz [IUnknown](/cpp/atl/iunknown) que el generador de perfiles debe consultar para un puntero de interfaz [ICorProfilerInfo](icorprofilerinfo-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="faf2a-106">\[in] Pointer to an [IUnknown](/cpp/atl/iunknown) interface that the profiler must query for an [ICorProfilerInfo](icorprofilerinfo-interface.md) interface pointer.</span></span>  

## <a name="remarks"></a><span data-ttu-id="faf2a-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="faf2a-107">Remarks</span></span>  

 <span data-ttu-id="faf2a-108">La `Initialize` llamada es la única oportunidad para habilitar (o deshabilitar) las devoluciones de llamada que son inmutables.</span><span class="sxs-lookup"><span data-stu-id="faf2a-108">The `Initialize` call is the only opportunity to enable (or disable) callbacks that are immutable.</span></span> <span data-ttu-id="faf2a-109">Una vez que la llamada habilita una devolución de llamada `Initialize` , no se puede deshabilitar posteriormente mediante [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md).</span><span class="sxs-lookup"><span data-stu-id="faf2a-109">Once a callback is enabled by the `Initialize` call, it cannot be disabled later using [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md).</span></span> <span data-ttu-id="faf2a-110">El valor COR_PRF_MONITOR_IMMUTABLE de la enumeración [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) indica qué eventos son inmutables.</span><span class="sxs-lookup"><span data-stu-id="faf2a-110">The COR_PRF_MONITOR_IMMUTABLE value of the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration indicates which events are immutable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="faf2a-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="faf2a-111">Requirements</span></span>  

 <span data-ttu-id="faf2a-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="faf2a-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="faf2a-113">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="faf2a-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="faf2a-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="faf2a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="faf2a-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="faf2a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="faf2a-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="faf2a-116">See also</span></span>

- [<span data-ttu-id="faf2a-117">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="faf2a-117">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="faf2a-118">Método Shutdown</span><span class="sxs-lookup"><span data-stu-id="faf2a-118">Shutdown Method</span></span>](icorprofilercallback-shutdown-method.md)
