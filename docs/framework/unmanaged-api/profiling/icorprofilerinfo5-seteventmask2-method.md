---
description: 'Más información sobre: ICorProfilerInfo5:: SetEventMask2 (método)'
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
ms.openlocfilehash: 2928ec408f2fdeb363164530258a3bf5c9719e2b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799010"
---
# <a name="icorprofilerinfo5seteventmask2-method"></a><span data-ttu-id="8155d-103">ICorProfilerInfo5::SetEventMask2 (Método)</span><span class="sxs-lookup"><span data-stu-id="8155d-103">ICorProfilerInfo5::SetEventMask2 Method</span></span>

<span data-ttu-id="8155d-104">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="8155d-104">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="8155d-105">Establece un valor que especifica los tipos de eventos para los que el generador de perfiles quiere recibir notificaciones de eventos desde Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="8155d-105">Sets a value that specifies the types of events for which the profiler wants to receive event notifications from the common language runtime (CLR).</span></span> <span data-ttu-id="8155d-106">Proporciona más funcionalidad que el método [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) .</span><span class="sxs-lookup"><span data-stu-id="8155d-106">It provides more functionality than the [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8155d-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8155d-107">Syntax</span></span>  
  
```cpp
HRESULT SetEventMask2(        [in] DWORD dwEventsLow,        [in] DWORD dwEventsHigh  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8155d-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8155d-108">Parameters</span></span>  

 `dwEventsLow`  
 <span data-ttu-id="8155d-109">[in] Valor de 4 bytes que especifica las categorías de eventos.</span><span class="sxs-lookup"><span data-stu-id="8155d-109">[in] A 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="8155d-110">Cada bit controla una funcionalidad, comportamiento o tipo de evento diferente.</span><span class="sxs-lookup"><span data-stu-id="8155d-110">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="8155d-111">Los bits se describen en la enumeración [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="8155d-111">The bits are described in the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 `dwEventsHigh`  
 <span data-ttu-id="8155d-112">[in] Valor de 4 bytes que especifica las categorías de eventos.</span><span class="sxs-lookup"><span data-stu-id="8155d-112">[in] A 4-byte value that specifies the categories of events.</span></span>  <span data-ttu-id="8155d-113">Cada bit controla una funcionalidad, comportamiento o tipo de evento diferente.</span><span class="sxs-lookup"><span data-stu-id="8155d-113">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="8155d-114">Los bits se describen en la enumeración [COR_PRF_HIGH_MONITOR](cor-prf-high-monitor-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="8155d-114">The bits are described in the [COR_PRF_HIGH_MONITOR](cor-prf-high-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8155d-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8155d-115">Remarks</span></span>  

 <span data-ttu-id="8155d-116">El método `SetEventMask2` se usa para establecer las devoluciones de llamada a las que se suscribe el generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="8155d-116">The `SetEventMask2` method is used to set the callbacks to which the profiler subscribes.</span></span> <span data-ttu-id="8155d-117">Normalmente, se llama al método [GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) para determinar qué bits se establecen, se realiza una operación OR lógica de sus `pdwEventsLow` `pdwEventsHigh` valores y y los bits nuevos que se desea establecer y, después, se llama al `SetEventMask2` método.</span><span class="sxs-lookup"><span data-stu-id="8155d-117">Typically, you call the [GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) method to determine which bits are set, perform a logical OR of its `pdwEventsLow` and `pdwEventsHigh` values and any new bits you want to set, and then call the `SetEventMask2` method.</span></span>  
  
 <span data-ttu-id="8155d-118">Este método es la alternativa recomendada al método [SetEventMask](icorprofilerinfo-seteventmask-method.md) .</span><span class="sxs-lookup"><span data-stu-id="8155d-118">This method is the recommended alternative to the [SetEventMask](icorprofilerinfo-seteventmask-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8155d-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8155d-119">Requirements</span></span>  

 <span data-ttu-id="8155d-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8155d-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8155d-121">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8155d-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8155d-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8155d-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8155d-123">**.NET Framework versiones:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8155d-123">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8155d-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="8155d-124">See also</span></span>

- [<span data-ttu-id="8155d-125">ICorProfilerInfo5 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8155d-125">ICorProfilerInfo5 Interface</span></span>](icorprofilerinfo5-interface.md)
- [<span data-ttu-id="8155d-126">GetEventMask2 (método)</span><span class="sxs-lookup"><span data-stu-id="8155d-126">GetEventMask2 Method</span></span>](icorprofilerinfo5-geteventmask2-method.md)
