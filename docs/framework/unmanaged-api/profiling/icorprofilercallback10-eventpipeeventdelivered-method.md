---
description: 'Más información sobre: ICorProfilerCallback10:: EventPipeEventDelivered (método)'
title: 'ICorProfilerCallback10:: EventPipeEventDelivered (método)'
ms.date: 03/19/2021
api_name:
- ICorProfilerCallback10.EventPipeEventDelivered
api_location:
- coreclr.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 7b2ca813d610c2b41d97d8cd76dac22ca38802d7
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805641"
---
# <a name="icorprofilercallback10eventpipeeventdelivered-method"></a><span data-ttu-id="a1639-103">ICorProfilerCallback10:: EventPipeEventDelivered (método)</span><span class="sxs-lookup"><span data-stu-id="a1639-103">ICorProfilerCallback10::EventPipeEventDelivered Method</span></span>

<span data-ttu-id="a1639-104">Notifica al generador de perfiles cada vez que se ha entregado un evento EventPipe a la sesión activa del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="a1639-104">Notifies the profiler whenever an EventPipe event has been delivered to the profiler's currently active session.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1639-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a1639-105">Syntax</span></span>  
  
```cpp  
    HRESULT EventPipeEventDelivered(
        [in] EVENTPIPE_PROVIDER provider,
        [in] DWORD eventId,
        [in] DWORD eventVersion,
        [in] ULONG cbMetadataBlob,
        [in, size_is(cbMetadataBlob)] LPCBYTE metadataBlob,
        [in] ULONG cbEventData,
        [in, size_is(cbEventData)] LPCBYTE eventData,
        [in] LPCGUID pActivityId,
        [in] LPCGUID pRelatedActivityId,
        [in] ThreadID eventThread,
        [in] ULONG numStackFrames,
        [in, length_is(numStackFrames)] UINT_PTR stackFrames[]); 
```  
  
## <a name="parameters"></a><span data-ttu-id="a1639-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a1639-106">Parameters</span></span>

<span data-ttu-id="a1639-107">`provider` de Proveedor del que se originó este evento.</span><span class="sxs-lookup"><span data-stu-id="a1639-107">`provider` [in] The provider that this event originated from.</span></span>

<span data-ttu-id="a1639-108">`eventId` de IDENTIFICADOR del evento que se va a entregar.</span><span class="sxs-lookup"><span data-stu-id="a1639-108">`eventId` [in] The ID of the event being delivered.</span></span>

<span data-ttu-id="a1639-109">`eventVersion` de Versión del evento que se va a entregar.</span><span class="sxs-lookup"><span data-stu-id="a1639-109">`eventVersion` [in] The version of the event being delivered.</span></span>

<span data-ttu-id="a1639-110">`cbMetadataBlob` de Longitud, en bytes, de `metadataBlob` .</span><span class="sxs-lookup"><span data-stu-id="a1639-110">`cbMetadataBlob` [in] The length, in bytes, of `metadataBlob`.</span></span>

<span data-ttu-id="a1639-111">`metadataBlob` de Puntero al objeto binario de metadatos para el evento.</span><span class="sxs-lookup"><span data-stu-id="a1639-111">`metadataBlob` [in] A pointer to the metadata blob for the event.</span></span>

<span data-ttu-id="a1639-112">`cbEventData` de Longitud, en bytes, de `eventData` .</span><span class="sxs-lookup"><span data-stu-id="a1639-112">`cbEventData` [in] The length, in bytes, of `eventData`.</span></span>

<span data-ttu-id="a1639-113">`eventData` de Carga del evento.</span><span class="sxs-lookup"><span data-stu-id="a1639-113">`eventData` [in] The payload for the event.</span></span>

<span data-ttu-id="a1639-114">`pActivityId` de Puntero al GUID que representa el identificador de actividad del evento o NULL.</span><span class="sxs-lookup"><span data-stu-id="a1639-114">`pActivityId` [in] A pointer to the GUID that represents the event's activity ID, or NULL.</span></span>

<span data-ttu-id="a1639-115">`pRelatedActivityId` de Puntero al GUID que representa el identificador de actividad relacionado del evento o NULL.</span><span class="sxs-lookup"><span data-stu-id="a1639-115">`pRelatedActivityId` [in] A pointer to the GUID that represents the event's related activity ID, or NULL.</span></span>

<span data-ttu-id="a1639-116">`eventThread` de IDENTIFICADOR del subproceso en el que se produjo el evento.</span><span class="sxs-lookup"><span data-stu-id="a1639-116">`eventThread` [in] The ID of the thread the event occurred on.</span></span>

<span data-ttu-id="a1639-117">`numStackFrames` de Número de elementos de la `stackFrames` matriz.</span><span class="sxs-lookup"><span data-stu-id="a1639-117">`numStackFrames` [in] The number of elements in the `stackFrames` array.</span></span>

<span data-ttu-id="a1639-118">`stackFrames` de Matriz de direcciones de código que representa la pila de llamadas administrada del evento.</span><span class="sxs-lookup"><span data-stu-id="a1639-118">`stackFrames` [in] An array of code addresses representing the managed callstack of the event.</span></span>

## <a name="requirements"></a><span data-ttu-id="a1639-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a1639-119">Requirements</span></span>  

<span data-ttu-id="a1639-120">**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/windows.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="a1639-120">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>  
<span data-ttu-id="a1639-121">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a1639-121">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="a1639-122">**Versiones de .net:**[!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1639-122">**.NET Versions:** [!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1639-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a1639-123">See also</span></span>

- [<span data-ttu-id="a1639-124">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="a1639-124">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="a1639-125">Interfaz ICorProfilerCallback10</span><span class="sxs-lookup"><span data-stu-id="a1639-125">ICorProfilerCallback10 Interface</span></span>](icorprofilercallback10-interface.md)
- [<span data-ttu-id="a1639-126">Interfaz ICorProfilerInfo12</span><span class="sxs-lookup"><span data-stu-id="a1639-126">ICorProfilerInfo12 Interface</span></span>](icorprofilerinfo12-interface.md)
- [<span data-ttu-id="a1639-127">ICorProfilerInfo12. EventPipeStartSession, método</span><span class="sxs-lookup"><span data-stu-id="a1639-127">ICorProfilerInfo12.EventPipeStartSession Method</span></span>](icorprofilerinfo12-eventpipestartsession-method.md)
