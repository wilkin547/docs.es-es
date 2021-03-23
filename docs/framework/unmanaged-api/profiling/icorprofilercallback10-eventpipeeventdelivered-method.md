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
# <a name="icorprofilercallback10eventpipeeventdelivered-method"></a>ICorProfilerCallback10:: EventPipeEventDelivered (método)

Notifica al generador de perfiles cada vez que se ha entregado un evento EventPipe a la sesión activa del generador de perfiles.  
  
## <a name="syntax"></a>Sintaxis  
  
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
  
## <a name="parameters"></a>Parámetros

`provider` de Proveedor del que se originó este evento.

`eventId` de IDENTIFICADOR del evento que se va a entregar.

`eventVersion` de Versión del evento que se va a entregar.

`cbMetadataBlob` de Longitud, en bytes, de `metadataBlob` .

`metadataBlob` de Puntero al objeto binario de metadatos para el evento.

`cbEventData` de Longitud, en bytes, de `eventData` .

`eventData` de Carga del evento.

`pActivityId` de Puntero al GUID que representa el identificador de actividad del evento o NULL.

`pRelatedActivityId` de Puntero al GUID que representa el identificador de actividad relacionado del evento o NULL.

`eventThread` de IDENTIFICADOR del subproceso en el que se produjo el evento.

`numStackFrames` de Número de elementos de la `stackFrames` matriz.

`stackFrames` de Matriz de direcciones de código que representa la pila de llamadas administrada del evento.

## <a name="requirements"></a>Requisitos  

**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/windows.md?pivots=os-windows).  
**Encabezado:** CorProf.idl, CorProf.h  
**Versiones de .net:**[!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaces para generación de perfiles](profiling-interfaces.md)
- [Interfaz ICorProfilerCallback10](icorprofilercallback10-interface.md)
- [Interfaz ICorProfilerInfo12](icorprofilerinfo12-interface.md)
- [ICorProfilerInfo12. EventPipeStartSession, método](icorprofilerinfo12-eventpipestartsession-method.md)
