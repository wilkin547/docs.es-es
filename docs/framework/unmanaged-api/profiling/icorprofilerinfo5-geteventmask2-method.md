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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f8ebddf9a16b2eddbbc58342f68b517064e8d794
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62041048"
---
# <a name="icorprofilerinfo5geteventmask2-method"></a><span data-ttu-id="dccbf-102">ICorProfilerInfo5::GetEventMask2 (Método)</span><span class="sxs-lookup"><span data-stu-id="dccbf-102">ICorProfilerInfo5::GetEventMask2 Method</span></span>
<span data-ttu-id="dccbf-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="dccbf-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="dccbf-104">Obtiene las categorías de eventos actuales para las que el generador de perfiles quiere recibir notificaciones de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="dccbf-104">Gets the current event categories for which the profiler wants to receive notifications from the common language runtime (CLR).</span></span>  <span data-ttu-id="dccbf-105">Proporciona funcionalidad que no proporcionada la [ICorProfilerInfo:: GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="dccbf-105">It provides functionality not provided by the [ICorProfilerInfo::GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dccbf-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dccbf-106">Syntax</span></span>  
  
```cpp
HRESULT GetEventMask2(  
        [out] DWORD* pdwEventsLow,  
        [out] DWORD* pdwEventsHigh  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dccbf-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dccbf-107">Parameters</span></span>  
 `pdwEventsLow`  
 <span data-ttu-id="dccbf-108">[out] Puntero a un valor de 4 bytes que especifica las categorías de eventos.</span><span class="sxs-lookup"><span data-stu-id="dccbf-108">[out] A pointer to a 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="dccbf-109">Cada bit controla una funcionalidad, comportamiento o tipo de evento diferente.</span><span class="sxs-lookup"><span data-stu-id="dccbf-109">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="dccbf-110">Los bits se describen en la [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeración.</span><span class="sxs-lookup"><span data-stu-id="dccbf-110">The bits are described in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 `pdwEventsHigh`  
 <span data-ttu-id="dccbf-111">[out] Puntero a un valor de 4 bytes que especifica las categorías de eventos.</span><span class="sxs-lookup"><span data-stu-id="dccbf-111">[out] A pointer to a 4-byte value that specifies the categories of events.</span></span>  <span data-ttu-id="dccbf-112">Cada bit controla una funcionalidad, comportamiento o tipo de evento diferente.</span><span class="sxs-lookup"><span data-stu-id="dccbf-112">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="dccbf-113">Los bits se describen en la [COR_PRF_HIGH_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) enumeración.</span><span class="sxs-lookup"><span data-stu-id="dccbf-113">The bits are described in the [COR_PRF_HIGH_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dccbf-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dccbf-114">Remarks</span></span>  
 <span data-ttu-id="dccbf-115">El método `GetEventMask2` se usa para determinar a qué devoluciones de llamada se ha suscrito el generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="dccbf-115">The `GetEventMask2` method is used to determine which callbacks the profiler has subscribed to.</span></span> <span data-ttu-id="dccbf-116">Normalmente, se realiza una operación OR lógica de la `pdwEventsLow` y `pdwEventsHigh` valores y los nuevos bits que desea establecer y, a continuación, llame el [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="dccbf-116">Typically, you perform a logical OR of the `pdwEventsLow` and `pdwEventsHigh` values and any new bits you want to set, and then call the [SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method.</span></span>  
  
 <span data-ttu-id="dccbf-117">Este método es la alternativa recomendada para el [GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="dccbf-117">This method is the recommended alternative to the [GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dccbf-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dccbf-118">Requirements</span></span>  
 <span data-ttu-id="dccbf-119">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dccbf-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dccbf-120">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="dccbf-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="dccbf-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dccbf-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dccbf-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dccbf-122">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dccbf-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="dccbf-123">See also</span></span>

- [<span data-ttu-id="dccbf-124">ICorProfilerInfo5 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="dccbf-124">ICorProfilerInfo5 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)
- [<span data-ttu-id="dccbf-125">SetEventMask2 (método)</span><span class="sxs-lookup"><span data-stu-id="dccbf-125">SetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)
