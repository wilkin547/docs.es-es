---
title: ICorProfilerInfo5::SetEventMask2 (Método)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- IcorProfilerInfo5.SetEventMask2
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 05dbbe2b-049c-4a60-be69-2ad7a949405e
topic_type:
- apiref
ms.openlocfilehash: 1e1779c0f4f36b2d7b81832bc90cf5aee0b8a7df
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130392"
---
# <a name="icorprofilerinfo5seteventmask2-method"></a><span data-ttu-id="01be3-102">ICorProfilerInfo5::SetEventMask2 (Método)</span><span class="sxs-lookup"><span data-stu-id="01be3-102">ICorProfilerInfo5::SetEventMask2 Method</span></span>
<span data-ttu-id="01be3-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="01be3-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="01be3-104">Establece un valor que especifica los tipos de eventos para los que el generador de perfiles quiere recibir notificaciones de eventos desde Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="01be3-104">Sets a value that specifies the types of events for which the profiler wants to receive event notifications from the common language runtime (CLR).</span></span> <span data-ttu-id="01be3-105">Proporciona más funcionalidad que el método [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) .</span><span class="sxs-lookup"><span data-stu-id="01be3-105">It provides more functionality than the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01be3-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="01be3-106">Syntax</span></span>  
  
```cpp
HRESULT SetEventMask2(        [in] DWORD dwEventsLow,        [in] DWORD dwEventsHigh  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="01be3-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="01be3-107">Parameters</span></span>  
 `dwEventsLow`  
 <span data-ttu-id="01be3-108">[in] Valor de 4 bytes que especifica las categorías de eventos.</span><span class="sxs-lookup"><span data-stu-id="01be3-108">[in] A 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="01be3-109">Cada bit controla una funcionalidad, comportamiento o tipo de evento diferente.</span><span class="sxs-lookup"><span data-stu-id="01be3-109">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="01be3-110">Los bits se describen en la enumeración [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="01be3-110">The bits are described in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 `dwEventsHigh`  
 <span data-ttu-id="01be3-111">[in] Valor de 4 bytes que especifica las categorías de eventos.</span><span class="sxs-lookup"><span data-stu-id="01be3-111">[in] A 4-byte value that specifies the categories of events.</span></span>  <span data-ttu-id="01be3-112">Cada bit controla una funcionalidad, comportamiento o tipo de evento diferente.</span><span class="sxs-lookup"><span data-stu-id="01be3-112">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="01be3-113">Los bits se describen en la enumeración [COR_PRF_HIGH_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="01be3-113">The bits are described in the [COR_PRF_HIGH_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="01be3-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="01be3-114">Remarks</span></span>  
 <span data-ttu-id="01be3-115">El método `SetEventMask2` se usa para establecer las devoluciones de llamada a las que se suscribe el generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="01be3-115">The `SetEventMask2` method is used to set the callbacks to which the profiler subscribes.</span></span> <span data-ttu-id="01be3-116">Normalmente, se llama al método [GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) para determinar qué bits se establecen, se realiza una operación OR lógica de sus valores `pdwEventsLow` y `pdwEventsHigh` y los bits nuevos que se desea establecer y, después, se llama al método `SetEventMask2`.</span><span class="sxs-lookup"><span data-stu-id="01be3-116">Typically, you call the [GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) method to determine which bits are set, perform a logical OR of its `pdwEventsLow` and `pdwEventsHigh` values and any new bits you want to set, and then call the `SetEventMask2` method.</span></span>  
  
 <span data-ttu-id="01be3-117">Este método es la alternativa recomendada al método [SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) .</span><span class="sxs-lookup"><span data-stu-id="01be3-117">This method is the recommended alternative to the [SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01be3-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="01be3-118">Requirements</span></span>  
 <span data-ttu-id="01be3-119">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="01be3-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01be3-120">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="01be3-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="01be3-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="01be3-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="01be3-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01be3-122">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01be3-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="01be3-123">See also</span></span>

- [<span data-ttu-id="01be3-124">ICorProfilerInfo5 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="01be3-124">ICorProfilerInfo5 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)
- [<span data-ttu-id="01be3-125">GetEventMask2 (método)</span><span class="sxs-lookup"><span data-stu-id="01be3-125">GetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md)
