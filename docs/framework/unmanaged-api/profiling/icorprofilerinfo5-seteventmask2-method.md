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
ms.openlocfilehash: 10e84b729c8af607165009a8591a69dbc1afcb1e
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868387"
---
# <a name="icorprofilerinfo5seteventmask2-method"></a><span data-ttu-id="51b30-102">ICorProfilerInfo5::SetEventMask2 (Método)</span><span class="sxs-lookup"><span data-stu-id="51b30-102">ICorProfilerInfo5::SetEventMask2 Method</span></span>
<span data-ttu-id="51b30-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="51b30-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="51b30-104">Establece un valor que especifica los tipos de eventos para los que el generador de perfiles quiere recibir notificaciones de eventos desde Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="51b30-104">Sets a value that specifies the types of events for which the profiler wants to receive event notifications from the common language runtime (CLR).</span></span> <span data-ttu-id="51b30-105">Proporciona más funcionalidad que el método [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) .</span><span class="sxs-lookup"><span data-stu-id="51b30-105">It provides more functionality than the [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51b30-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="51b30-106">Syntax</span></span>  
  
```cpp
HRESULT SetEventMask2(        [in] DWORD dwEventsLow,        [in] DWORD dwEventsHigh  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="51b30-107">Parameters</span><span class="sxs-lookup"><span data-stu-id="51b30-107">Parameters</span></span>  
 `dwEventsLow`  
 <span data-ttu-id="51b30-108">[in] Valor de 4 bytes que especifica las categorías de eventos.</span><span class="sxs-lookup"><span data-stu-id="51b30-108">[in] A 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="51b30-109">Cada bit controla una funcionalidad, comportamiento o tipo de evento diferente.</span><span class="sxs-lookup"><span data-stu-id="51b30-109">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="51b30-110">Los bits se describen en la enumeración [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="51b30-110">The bits are described in the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 `dwEventsHigh`  
 <span data-ttu-id="51b30-111">[in] Valor de 4 bytes que especifica las categorías de eventos.</span><span class="sxs-lookup"><span data-stu-id="51b30-111">[in] A 4-byte value that specifies the categories of events.</span></span>  <span data-ttu-id="51b30-112">Cada bit controla una funcionalidad, comportamiento o tipo de evento diferente.</span><span class="sxs-lookup"><span data-stu-id="51b30-112">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="51b30-113">Los bits se describen en la enumeración [COR_PRF_HIGH_MONITOR](cor-prf-high-monitor-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="51b30-113">The bits are described in the [COR_PRF_HIGH_MONITOR](cor-prf-high-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="51b30-114">Notas</span><span class="sxs-lookup"><span data-stu-id="51b30-114">Remarks</span></span>  
 <span data-ttu-id="51b30-115">El método `SetEventMask2` se usa para establecer las devoluciones de llamada a las que se suscribe el generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="51b30-115">The `SetEventMask2` method is used to set the callbacks to which the profiler subscribes.</span></span> <span data-ttu-id="51b30-116">Normalmente, se llama al método [GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) para determinar qué bits se establecen, se realiza una operación OR lógica de sus valores `pdwEventsLow` y `pdwEventsHigh` y los bits nuevos que se desea establecer y, después, se llama al método `SetEventMask2`.</span><span class="sxs-lookup"><span data-stu-id="51b30-116">Typically, you call the [GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) method to determine which bits are set, perform a logical OR of its `pdwEventsLow` and `pdwEventsHigh` values and any new bits you want to set, and then call the `SetEventMask2` method.</span></span>  
  
 <span data-ttu-id="51b30-117">Este método es la alternativa recomendada al método [SetEventMask](icorprofilerinfo-seteventmask-method.md) .</span><span class="sxs-lookup"><span data-stu-id="51b30-117">This method is the recommended alternative to the [SetEventMask](icorprofilerinfo-seteventmask-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51b30-118">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="51b30-118">Requirements</span></span>  
 <span data-ttu-id="51b30-119">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51b30-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51b30-120">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="51b30-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="51b30-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="51b30-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="51b30-122">**.NET Framework versiones:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51b30-122">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51b30-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="51b30-123">See also</span></span>

- [<span data-ttu-id="51b30-124">ICorProfilerInfo5 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="51b30-124">ICorProfilerInfo5 Interface</span></span>](icorprofilerinfo5-interface.md)
- [<span data-ttu-id="51b30-125">GetEventMask2 (método)</span><span class="sxs-lookup"><span data-stu-id="51b30-125">GetEventMask2 Method</span></span>](icorprofilerinfo5-geteventmask2-method.md)
