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
# <a name="icorprofilerinfo12eventpipewriteevent-method"></a>ICorProfilerInfo12:: EventPipeWriteEvent (método)

Escribe un evento EventPipe en los agentes de escucha que han habilitado este evento.
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
    HRESULT EventPipeWriteEvent(
                [in] EVENTPIPE_EVENT    event,
                [in] UINT32             cData,
                [in, size_is(cData)]
                     COR_PRF_EVENT_DATA data[],
                [in] LPCGUID            pActivityId,
                [in] LPCGUID            pRelatedActivityId);
```  
  
## <a name="parameters"></a>Parámetros

`event` de IDENTIFICADOR del evento que se va a escribir.

`cData` de Número de elementos de `data` .

`data` de Matriz de `COR_PRF_EVENT_DATA` que contiene los argumentos de evento.

`pActivityId` de Un puntero a un GUID que especifica el identificador de actividad del evento.

`pRelatedActivityId` de Un puntero a un GUID que especifica el identificador de actividad relacionado del evento.

## <a name="requirements"></a>Requisitos  

**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/windows.md?pivots=os-windows).
**Encabezado:** **Versiones de .net** de Corprof. idl, Corprof. h: [!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]
  
## <a name="see-also"></a>Consulte también

- [Interfaces para generación de perfiles](profiling-interfaces.md)
- [Interfaz ICorProfilerCallback10](icorprofilercallback10-interface.md)
- [Interfaz ICorProfilerInfo12](icorprofilerinfo12-interface.md)
- [Estructura de COR_PRF_EVENT_DATA](cor-prf-event-data-structure.md)
