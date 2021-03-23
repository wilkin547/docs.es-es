---
description: 'Más información sobre: ICorProfilerInfo12:: EventPipeWriteEvent (método)'
title: 'ICorProfilerInfo12:: EventPipeWriteEvent (método)'
ms.date: 03/19/2021
api_name:
- ICorProfilerInfo12.EventPipeWriteEvent
api_location:
- coreclr.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: a0a06ff0fa1c936518586834f4dfc73810ef0e44
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805745"
---
# <a name="icorprofilerinfo12eventpipewriteevent-method"></a><span data-ttu-id="efc84-103">ICorProfilerInfo12:: EventPipeWriteEvent (método)</span><span class="sxs-lookup"><span data-stu-id="efc84-103">ICorProfilerInfo12::EventPipeWriteEvent Method</span></span>

<span data-ttu-id="efc84-104">Escribe un evento EventPipe en los agentes de escucha que han habilitado este evento.</span><span class="sxs-lookup"><span data-stu-id="efc84-104">Writes an EventPipe event to any listeners who have enabled this event.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="efc84-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="efc84-105">Syntax</span></span>  
  
```cpp  
    HRESULT EventPipeWriteEvent(
                [in] EVENTPIPE_EVENT    event,
                [in] UINT32             cData,
                [in, size_is(cData)]
                     COR_PRF_EVENT_DATA data[],
                [in] LPCGUID            pActivityId,
                [in] LPCGUID            pRelatedActivityId);
```  
  
## <a name="parameters"></a><span data-ttu-id="efc84-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="efc84-106">Parameters</span></span>

<span data-ttu-id="efc84-107">`event` de IDENTIFICADOR del evento que se va a escribir.</span><span class="sxs-lookup"><span data-stu-id="efc84-107">`event` [in] The ID of the event being written.</span></span>

<span data-ttu-id="efc84-108">`cData` de Número de elementos de `data` .</span><span class="sxs-lookup"><span data-stu-id="efc84-108">`cData` [in] The number of elements in `data`.</span></span>

<span data-ttu-id="efc84-109">`data` de Matriz de `COR_PRF_EVENT_DATA` que contiene los argumentos de evento.</span><span class="sxs-lookup"><span data-stu-id="efc84-109">`data` [in] An array of `COR_PRF_EVENT_DATA` containing the event arguments.</span></span>

<span data-ttu-id="efc84-110">`pActivityId` de Un puntero a un GUID que especifica el identificador de actividad del evento.</span><span class="sxs-lookup"><span data-stu-id="efc84-110">`pActivityId` [in] A pointer to a GUID specifying the event's activity ID.</span></span>

<span data-ttu-id="efc84-111">`pRelatedActivityId` de Un puntero a un GUID que especifica el identificador de actividad relacionado del evento.</span><span class="sxs-lookup"><span data-stu-id="efc84-111">`pRelatedActivityId` [in] A pointer to a GUID specifying the event's related activity ID.</span></span>

## <a name="requirements"></a><span data-ttu-id="efc84-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="efc84-112">Requirements</span></span>  

<span data-ttu-id="efc84-113">**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/windows.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="efc84-113">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>
<span data-ttu-id="efc84-114">**Encabezado:** **Versiones de .net** de Corprof. idl, Corprof. h: [!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]</span><span class="sxs-lookup"><span data-stu-id="efc84-114">**Header:** CorProf.idl, CorProf.h **.NET Versions:** [!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]</span></span>
  
## <a name="see-also"></a><span data-ttu-id="efc84-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="efc84-115">See also</span></span>

- [<span data-ttu-id="efc84-116">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="efc84-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="efc84-117">Interfaz ICorProfilerCallback10</span><span class="sxs-lookup"><span data-stu-id="efc84-117">ICorProfilerCallback10 Interface</span></span>](icorprofilercallback10-interface.md)
- [<span data-ttu-id="efc84-118">Interfaz ICorProfilerInfo12</span><span class="sxs-lookup"><span data-stu-id="efc84-118">ICorProfilerInfo12 Interface</span></span>](icorprofilerinfo12-interface.md)
- [<span data-ttu-id="efc84-119">Estructura de COR_PRF_EVENT_DATA</span><span class="sxs-lookup"><span data-stu-id="efc84-119">COR_PRF_EVENT_DATA Structure</span></span>](cor-prf-event-data-structure.md)
