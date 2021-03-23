---
description: 'Más información sobre: ICorProfilerInfo12:: EventPipeDefineEvent (método)'
title: 'ICorProfilerInfo12:: EventPipeDefineEvent (método)'
ms.date: 03/19/2021
api_name:
- ICorProfilerInfo12.EventPipeDefineEvent
api_location:
- coreclr.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 845f7f26dce7aa0f4b7d895b9f04cc89e7ac7192
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805758"
---
# <a name="icorprofilerinfo12eventpipedefineevent-method"></a><span data-ttu-id="0d0dc-103">ICorProfilerInfo12:: EventPipeDefineEvent (método)</span><span class="sxs-lookup"><span data-stu-id="0d0dc-103">ICorProfilerInfo12::EventPipeDefineEvent Method</span></span>

<span data-ttu-id="0d0dc-104">Define un evento EventPipe en un proveedor existente.</span><span class="sxs-lookup"><span data-stu-id="0d0dc-104">Defines an EventPipe event on an existing provider.</span></span> <span data-ttu-id="0d0dc-105">Este proveedor se puede utilizar para escribir eventos EventPipe que otros agentes de escucha pueden recibir.</span><span class="sxs-lookup"><span data-stu-id="0d0dc-105">This provider can be used to write EventPipe events that other listeners can receive.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="0d0dc-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0d0dc-106">Syntax</span></span>  
  
```cpp  
    HRESULT EventPipeDefineEvent(
                [in] EVENTPIPE_PROVIDER     provider,
                [in, string] const WCHAR   *eventName,
                [in] UINT32                 eventID,
                [in] UINT64                 keywords,
                [in] UINT32                 eventVersion,
                [in] UINT32                 level,
                [in] UINT8                  opcode,
                [in] BOOL                   needStack,
                [in] UINT32                 cParamDescs,
                [in, size_is(cParamDescs)]
                     COR_PRF_EVENTPIPE_PARAM_DESC pParamDescs[],
                [out] EVENTPIPE_EVENT      *pEvent);
```  
  
## <a name="parameters"></a><span data-ttu-id="0d0dc-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0d0dc-107">Parameters</span></span>

<span data-ttu-id="0d0dc-108">`provider` de IDENTIFICADOR del proveedor en el que se va a definir un evento.</span><span class="sxs-lookup"><span data-stu-id="0d0dc-108">`provider` [in] The ID of the provider to define an event on.</span></span>

<span data-ttu-id="0d0dc-109">`eventName` de Puntero a una cadena de caracteres anchos terminada en null que contiene el nombre del evento.</span><span class="sxs-lookup"><span data-stu-id="0d0dc-109">`eventName` [in] A pointer to a null terminated wide character string that contains the event name.</span></span>

<span data-ttu-id="0d0dc-110">`eventID` de IDENTIFICADOR del evento que se va a definir.</span><span class="sxs-lookup"><span data-stu-id="0d0dc-110">`eventID` [in] The ID of the event being defined.</span></span>

<span data-ttu-id="0d0dc-111">`keywords` de Palabras clave del evento que se está definiendo.</span><span class="sxs-lookup"><span data-stu-id="0d0dc-111">`keywords` [in] The keywords of the event being defined.</span></span>

<span data-ttu-id="0d0dc-112">`eventVersion` de Versión del evento que se va a definir.</span><span class="sxs-lookup"><span data-stu-id="0d0dc-112">`eventVersion` [in] The version of the event being defined.</span></span>

<span data-ttu-id="0d0dc-113">`level` de Nivel del evento que se va a definir.</span><span class="sxs-lookup"><span data-stu-id="0d0dc-113">`level` [in] The level of the event being defined.</span></span>

<span data-ttu-id="0d0dc-114">`opcode` de Código de operación del evento que se está definiendo.</span><span class="sxs-lookup"><span data-stu-id="0d0dc-114">`opcode` [in] The opcode of the event being defined.</span></span>

<span data-ttu-id="0d0dc-115">`needStack` de Un valor de tipo `BOOL` que indica si las pilas administradas deben recopilarse cada vez que se activa este evento.</span><span class="sxs-lookup"><span data-stu-id="0d0dc-115">`needStack` [in] A `BOOL` indicating whether managed stacks should be collected each time this event fires.</span></span>

<span data-ttu-id="0d0dc-116">`cParamDescs` de Recuento del número de parámetros en `pParamDescs` .</span><span class="sxs-lookup"><span data-stu-id="0d0dc-116">`cParamDescs` [in] The count of the number of parameters in `pParamDescs`.</span></span>

<span data-ttu-id="0d0dc-117">`pParamDescs` de Matriz de `COR_PRF_EVENTPIPE_PARAM_DESC` la definición de los tipos de parámetro para el evento que se está definiendo.</span><span class="sxs-lookup"><span data-stu-id="0d0dc-117">`pParamDescs` [in] An array of `COR_PRF_EVENTPIPE_PARAM_DESC` defining the parameter types to the event being defined.</span></span>

<span data-ttu-id="0d0dc-118">`pEvent` enuncia Un puntero proporcionado por el autor de la llamada que se rellenará con el identificador del evento que se va a definir cuando se devuelva la función.</span><span class="sxs-lookup"><span data-stu-id="0d0dc-118">`pEvent` [out] A caller provided pointer that will be filled with the ID of the event being defined when the function returns.</span></span>

## <a name="requirements"></a><span data-ttu-id="0d0dc-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0d0dc-119">Requirements</span></span>  

<span data-ttu-id="0d0dc-120">**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/windows.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="0d0dc-120">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>
<span data-ttu-id="0d0dc-121">**Encabezado:** **Versiones de .net** de Corprof. idl, Corprof. h: [!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d0dc-121">**Header:** CorProf.idl, CorProf.h **.NET Versions:** [!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0d0dc-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0d0dc-122">See also</span></span>

- [<span data-ttu-id="0d0dc-123">Información general sobre EventPipe</span><span class="sxs-lookup"><span data-stu-id="0d0dc-123">EventPipe Overview</span></span>](../../../core/diagnostics/eventpipe.md)
- [<span data-ttu-id="0d0dc-124">EventProviders conocidos</span><span class="sxs-lookup"><span data-stu-id="0d0dc-124">Well Known EventProviders</span></span>](../../../core/diagnostics/well-known-event-providers.md)
- [<span data-ttu-id="0d0dc-125">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="0d0dc-125">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="0d0dc-126">Interfaz ICorProfilerCallback10</span><span class="sxs-lookup"><span data-stu-id="0d0dc-126">ICorProfilerCallback10 Interface</span></span>](icorprofilercallback10-interface.md)
- [<span data-ttu-id="0d0dc-127">Interfaz ICorProfilerInfo12</span><span class="sxs-lookup"><span data-stu-id="0d0dc-127">ICorProfilerInfo12 Interface</span></span>](icorprofilerinfo12-interface.md)
- [<span data-ttu-id="0d0dc-128">Estructura de COR_PRF_EVENTPIPE_PARAM_DESC</span><span class="sxs-lookup"><span data-stu-id="0d0dc-128">COR_PRF_EVENTPIPE_PARAM_DESC Structure</span></span>](cor-prf-eventpipe-param-desc-structure.md)
