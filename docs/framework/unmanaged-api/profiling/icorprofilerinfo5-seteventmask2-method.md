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
ms.openlocfilehash: 8027cdcde8281c363207e309bf65fcd90c03b626
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495637"
---
# <a name="icorprofilerinfo5seteventmask2-method"></a><span data-ttu-id="dc6b1-102">ICorProfilerInfo5::SetEventMask2 (Método)</span><span class="sxs-lookup"><span data-stu-id="dc6b1-102">ICorProfilerInfo5::SetEventMask2 Method</span></span>
<span data-ttu-id="dc6b1-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="dc6b1-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="dc6b1-104">Establece un valor que especifica los tipos de eventos para los que el generador de perfiles quiere recibir notificaciones de eventos desde Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="dc6b1-104">Sets a value that specifies the types of events for which the profiler wants to receive event notifications from the common language runtime (CLR).</span></span> <span data-ttu-id="dc6b1-105">Proporciona más funcionalidad que el método [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) .</span><span class="sxs-lookup"><span data-stu-id="dc6b1-105">It provides more functionality than the [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc6b1-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dc6b1-106">Syntax</span></span>  
  
```cpp
HRESULT SetEventMask2(        [in] DWORD dwEventsLow,        [in] DWORD dwEventsHigh  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dc6b1-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dc6b1-107">Parameters</span></span>  
 `dwEventsLow`  
 <span data-ttu-id="dc6b1-108">[in] Valor de 4 bytes que especifica las categorías de eventos.</span><span class="sxs-lookup"><span data-stu-id="dc6b1-108">[in] A 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="dc6b1-109">Cada bit controla una funcionalidad, comportamiento o tipo de evento diferente.</span><span class="sxs-lookup"><span data-stu-id="dc6b1-109">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="dc6b1-110">Los bits se describen en la enumeración [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="dc6b1-110">The bits are described in the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 `dwEventsHigh`  
 <span data-ttu-id="dc6b1-111">[in] Valor de 4 bytes que especifica las categorías de eventos.</span><span class="sxs-lookup"><span data-stu-id="dc6b1-111">[in] A 4-byte value that specifies the categories of events.</span></span>  <span data-ttu-id="dc6b1-112">Cada bit controla una funcionalidad, comportamiento o tipo de evento diferente.</span><span class="sxs-lookup"><span data-stu-id="dc6b1-112">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="dc6b1-113">Los bits se describen en la enumeración [COR_PRF_HIGH_MONITOR](cor-prf-high-monitor-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="dc6b1-113">The bits are described in the [COR_PRF_HIGH_MONITOR](cor-prf-high-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dc6b1-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dc6b1-114">Remarks</span></span>  
 <span data-ttu-id="dc6b1-115">El método `SetEventMask2` se usa para establecer las devoluciones de llamada a las que se suscribe el generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="dc6b1-115">The `SetEventMask2` method is used to set the callbacks to which the profiler subscribes.</span></span> <span data-ttu-id="dc6b1-116">Normalmente, se llama al método [GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) para determinar qué bits se establecen, se realiza una operación OR lógica de sus `pdwEventsLow` `pdwEventsHigh` valores y y los bits nuevos que se desea establecer y, después, se llama al `SetEventMask2` método.</span><span class="sxs-lookup"><span data-stu-id="dc6b1-116">Typically, you call the [GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) method to determine which bits are set, perform a logical OR of its `pdwEventsLow` and `pdwEventsHigh` values and any new bits you want to set, and then call the `SetEventMask2` method.</span></span>  
  
 <span data-ttu-id="dc6b1-117">Este método es la alternativa recomendada al método [SetEventMask](icorprofilerinfo-seteventmask-method.md) .</span><span class="sxs-lookup"><span data-stu-id="dc6b1-117">This method is the recommended alternative to the [SetEventMask](icorprofilerinfo-seteventmask-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc6b1-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dc6b1-118">Requirements</span></span>  
 <span data-ttu-id="dc6b1-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc6b1-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc6b1-120">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="dc6b1-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="dc6b1-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dc6b1-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dc6b1-122">**.NET Framework versiones:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc6b1-122">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc6b1-123">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="dc6b1-123">See also</span></span>

- [<span data-ttu-id="dc6b1-124">ICorProfilerInfo5 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="dc6b1-124">ICorProfilerInfo5 Interface</span></span>](icorprofilerinfo5-interface.md)
- [<span data-ttu-id="dc6b1-125">GetEventMask2 (método)</span><span class="sxs-lookup"><span data-stu-id="dc6b1-125">GetEventMask2 Method</span></span>](icorprofilerinfo5-geteventmask2-method.md)
