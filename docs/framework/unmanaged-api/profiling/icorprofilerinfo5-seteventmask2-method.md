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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 266219894ffefa0d4066c6ca68c7cadf6265e098
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62000485"
---
# <a name="icorprofilerinfo5seteventmask2-method"></a><span data-ttu-id="ca716-102">ICorProfilerInfo5::SetEventMask2 (Método)</span><span class="sxs-lookup"><span data-stu-id="ca716-102">ICorProfilerInfo5::SetEventMask2 Method</span></span>
<span data-ttu-id="ca716-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="ca716-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="ca716-104">Establece un valor que especifica los tipos de eventos para los que el generador de perfiles quiere recibir notificaciones de eventos desde Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="ca716-104">Sets a value that specifies the types of events for which the profiler wants to receive event notifications from the common language runtime (CLR).</span></span> <span data-ttu-id="ca716-105">Proporciona más funcionalidad que la [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="ca716-105">It provides more functionality than the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca716-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ca716-106">Syntax</span></span>  
  
```cpp
HRESULT SetEventMask2(        [in] DWORD dwEventsLow,        [in] DWORD dwEventsHigh  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ca716-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ca716-107">Parameters</span></span>  
 `dwEventsLow`  
 <span data-ttu-id="ca716-108">[in] Valor de 4 bytes que especifica las categorías de eventos.</span><span class="sxs-lookup"><span data-stu-id="ca716-108">[in] A 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="ca716-109">Cada bit controla una funcionalidad, comportamiento o tipo de evento diferente.</span><span class="sxs-lookup"><span data-stu-id="ca716-109">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="ca716-110">Los bits se describen en la [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeración.</span><span class="sxs-lookup"><span data-stu-id="ca716-110">The bits are described in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 `dwEventsHigh`  
 <span data-ttu-id="ca716-111">[in] Valor de 4 bytes que especifica las categorías de eventos.</span><span class="sxs-lookup"><span data-stu-id="ca716-111">[in] A 4-byte value that specifies the categories of events.</span></span>  <span data-ttu-id="ca716-112">Cada bit controla una funcionalidad, comportamiento o tipo de evento diferente.</span><span class="sxs-lookup"><span data-stu-id="ca716-112">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="ca716-113">Los bits se describen en la [COR_PRF_HIGH_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) enumeración.</span><span class="sxs-lookup"><span data-stu-id="ca716-113">The bits are described in the [COR_PRF_HIGH_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ca716-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ca716-114">Remarks</span></span>  
 <span data-ttu-id="ca716-115">El método `SetEventMask2` se usa para establecer las devoluciones de llamada a las que se suscribe el generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="ca716-115">The `SetEventMask2` method is used to set the callbacks to which the profiler subscribes.</span></span> <span data-ttu-id="ca716-116">Normalmente, se llama a la [GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) método para determinar qué bits se establecen, realizar una operación OR lógica de su `pdwEventsLow` y `pdwEventsHigh` valores y los nuevos bits que desea establecer y, a continuación, llame el `SetEventMask2` método.</span><span class="sxs-lookup"><span data-stu-id="ca716-116">Typically, you call the [GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) method to determine which bits are set, perform a logical OR of its `pdwEventsLow` and `pdwEventsHigh` values and any new bits you want to set, and then call the `SetEventMask2` method.</span></span>  
  
 <span data-ttu-id="ca716-117">Este método es la alternativa recomendada para el [SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="ca716-117">This method is the recommended alternative to the [SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca716-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ca716-118">Requirements</span></span>  
 <span data-ttu-id="ca716-119">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca716-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca716-120">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ca716-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ca716-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ca716-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ca716-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca716-122">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca716-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="ca716-123">See also</span></span>

- [<span data-ttu-id="ca716-124">ICorProfilerInfo5 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ca716-124">ICorProfilerInfo5 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)
- [<span data-ttu-id="ca716-125">GetEventMask2 (método)</span><span class="sxs-lookup"><span data-stu-id="ca716-125">GetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md)
