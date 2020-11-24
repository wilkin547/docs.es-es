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
ms.openlocfilehash: 81509db178b0ab1a524dcc4b00f39264e87a220d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95682788"
---
# <a name="icorprofilerinfo5geteventmask2-method"></a><span data-ttu-id="a6953-102">ICorProfilerInfo5::GetEventMask2 (Método)</span><span class="sxs-lookup"><span data-stu-id="a6953-102">ICorProfilerInfo5::GetEventMask2 Method</span></span>

<span data-ttu-id="a6953-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="a6953-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="a6953-104">Obtiene las categorías de eventos actuales para las que el generador de perfiles quiere recibir notificaciones de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="a6953-104">Gets the current event categories for which the profiler wants to receive notifications from the common language runtime (CLR).</span></span>  <span data-ttu-id="a6953-105">Proporciona funcionalidad no proporcionada por el método [ICorProfilerInfo:: GetEventMask (](icorprofilerinfo-geteventmask-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a6953-105">It provides functionality not provided by the [ICorProfilerInfo::GetEventMask](icorprofilerinfo-geteventmask-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6953-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a6953-106">Syntax</span></span>  
  
```cpp
HRESULT GetEventMask2(  
        [out] DWORD* pdwEventsLow,  
        [out] DWORD* pdwEventsHigh  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6953-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a6953-107">Parameters</span></span>  

 `pdwEventsLow`  
 <span data-ttu-id="a6953-108">[out] Puntero a un valor de 4 bytes que especifica las categorías de eventos.</span><span class="sxs-lookup"><span data-stu-id="a6953-108">[out] A pointer to a 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="a6953-109">Cada bit controla una funcionalidad, comportamiento o tipo de evento diferente.</span><span class="sxs-lookup"><span data-stu-id="a6953-109">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="a6953-110">Los bits se describen en la enumeración [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="a6953-110">The bits are described in the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 `pdwEventsHigh`  
 <span data-ttu-id="a6953-111">[out] Puntero a un valor de 4 bytes que especifica las categorías de eventos.</span><span class="sxs-lookup"><span data-stu-id="a6953-111">[out] A pointer to a 4-byte value that specifies the categories of events.</span></span>  <span data-ttu-id="a6953-112">Cada bit controla una funcionalidad, comportamiento o tipo de evento diferente.</span><span class="sxs-lookup"><span data-stu-id="a6953-112">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="a6953-113">Los bits se describen en la enumeración [COR_PRF_HIGH_MONITOR](cor-prf-high-monitor-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="a6953-113">The bits are described in the [COR_PRF_HIGH_MONITOR](cor-prf-high-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a6953-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a6953-114">Remarks</span></span>  

 <span data-ttu-id="a6953-115">El método `GetEventMask2` se usa para determinar a qué devoluciones de llamada se ha suscrito el generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="a6953-115">The `GetEventMask2` method is used to determine which callbacks the profiler has subscribed to.</span></span> <span data-ttu-id="a6953-116">Normalmente, se realiza una operación OR lógica de `pdwEventsLow` los `pdwEventsHigh` valores y y los bits nuevos que se desea establecer y, a continuación, se llama al método [SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a6953-116">Typically, you perform a logical OR of the `pdwEventsLow` and `pdwEventsHigh` values and any new bits you want to set, and then call the [SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) method.</span></span>  
  
 <span data-ttu-id="a6953-117">Este método es la alternativa recomendada para el método [GetEventMask (](icorprofilerinfo-geteventmask-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a6953-117">This method is the recommended alternative to the [GetEventMask](icorprofilerinfo-geteventmask-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6953-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a6953-118">Requirements</span></span>  

 <span data-ttu-id="a6953-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6953-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6953-120">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a6953-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a6953-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a6953-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a6953-122">**.NET Framework versiones:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6953-122">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6953-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a6953-123">See also</span></span>

- [<span data-ttu-id="a6953-124">ICorProfilerInfo5 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a6953-124">ICorProfilerInfo5 Interface</span></span>](icorprofilerinfo5-interface.md)
- [<span data-ttu-id="a6953-125">SetEventMask2 (método)</span><span class="sxs-lookup"><span data-stu-id="a6953-125">SetEventMask2 Method</span></span>](icorprofilerinfo5-seteventmask2-method.md)
