---
title: ICorProfilerInfo5::GetEventMask2 (Método)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorProfilerInfo5.GetEventMask2
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: f854b68f-009c-4ffb-89cd-ca874d1c0fb7
topic_type:
- apiref
ms.openlocfilehash: f3943eef969f777b40dc51c4900b190561f14887
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868400"
---
# <a name="icorprofilerinfo5geteventmask2-method"></a><span data-ttu-id="1d880-102">ICorProfilerInfo5::GetEventMask2 (Método)</span><span class="sxs-lookup"><span data-stu-id="1d880-102">ICorProfilerInfo5::GetEventMask2 Method</span></span>
<span data-ttu-id="1d880-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="1d880-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="1d880-104">Obtiene las categorías de eventos actuales para las que el generador de perfiles quiere recibir notificaciones de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="1d880-104">Gets the current event categories for which the profiler wants to receive notifications from the common language runtime (CLR).</span></span>  <span data-ttu-id="1d880-105">Proporciona funcionalidad no proporcionada por el método [ICorProfilerInfo:: GetEventMask (](icorprofilerinfo-geteventmask-method.md) .</span><span class="sxs-lookup"><span data-stu-id="1d880-105">It provides functionality not provided by the [ICorProfilerInfo::GetEventMask](icorprofilerinfo-geteventmask-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d880-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1d880-106">Syntax</span></span>  
  
```cpp
HRESULT GetEventMask2(  
        [out] DWORD* pdwEventsLow,  
        [out] DWORD* pdwEventsHigh  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1d880-107">Parameters</span><span class="sxs-lookup"><span data-stu-id="1d880-107">Parameters</span></span>  
 `pdwEventsLow`  
 <span data-ttu-id="1d880-108">[out] Puntero a un valor de 4 bytes que especifica las categorías de eventos.</span><span class="sxs-lookup"><span data-stu-id="1d880-108">[out] A pointer to a 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="1d880-109">Cada bit controla una funcionalidad, comportamiento o tipo de evento diferente.</span><span class="sxs-lookup"><span data-stu-id="1d880-109">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="1d880-110">Los bits se describen en la enumeración [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="1d880-110">The bits are described in the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 `pdwEventsHigh`  
 <span data-ttu-id="1d880-111">[out] Puntero a un valor de 4 bytes que especifica las categorías de eventos.</span><span class="sxs-lookup"><span data-stu-id="1d880-111">[out] A pointer to a 4-byte value that specifies the categories of events.</span></span>  <span data-ttu-id="1d880-112">Cada bit controla una funcionalidad, comportamiento o tipo de evento diferente.</span><span class="sxs-lookup"><span data-stu-id="1d880-112">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="1d880-113">Los bits se describen en la enumeración [COR_PRF_HIGH_MONITOR](cor-prf-high-monitor-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="1d880-113">The bits are described in the [COR_PRF_HIGH_MONITOR](cor-prf-high-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1d880-114">Notas</span><span class="sxs-lookup"><span data-stu-id="1d880-114">Remarks</span></span>  
 <span data-ttu-id="1d880-115">El método `GetEventMask2` se usa para determinar a qué devoluciones de llamada se ha suscrito el generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="1d880-115">The `GetEventMask2` method is used to determine which callbacks the profiler has subscribed to.</span></span> <span data-ttu-id="1d880-116">Normalmente, se realiza una operación OR lógica de los valores `pdwEventsLow` y `pdwEventsHigh` y los bits nuevos que se desea establecer y, después, se llama al método [SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="1d880-116">Typically, you perform a logical OR of the `pdwEventsLow` and `pdwEventsHigh` values and any new bits you want to set, and then call the [SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) method.</span></span>  
  
 <span data-ttu-id="1d880-117">Este método es la alternativa recomendada para el método [GetEventMask (](icorprofilerinfo-geteventmask-method.md) .</span><span class="sxs-lookup"><span data-stu-id="1d880-117">This method is the recommended alternative to the [GetEventMask](icorprofilerinfo-geteventmask-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d880-118">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="1d880-118">Requirements</span></span>  
 <span data-ttu-id="1d880-119">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d880-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d880-120">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1d880-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1d880-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1d880-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1d880-122">**.NET Framework versiones:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d880-122">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d880-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="1d880-123">See also</span></span>

- [<span data-ttu-id="1d880-124">ICorProfilerInfo5 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1d880-124">ICorProfilerInfo5 Interface</span></span>](icorprofilerinfo5-interface.md)
- [<span data-ttu-id="1d880-125">SetEventMask2 (método)</span><span class="sxs-lookup"><span data-stu-id="1d880-125">SetEventMask2 Method</span></span>](icorprofilerinfo5-seteventmask2-method.md)
