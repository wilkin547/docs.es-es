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
# <a name="icorprofilerinfo12eventpipedefineevent-method"></a>ICorProfilerInfo12:: EventPipeDefineEvent (método)

Define un evento EventPipe en un proveedor existente. Este proveedor se puede utilizar para escribir eventos EventPipe que otros agentes de escucha pueden recibir.
  
## <a name="syntax"></a>Sintaxis  
  
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
  
## <a name="parameters"></a>Parámetros

`provider` de IDENTIFICADOR del proveedor en el que se va a definir un evento.

`eventName` de Puntero a una cadena de caracteres anchos terminada en null que contiene el nombre del evento.

`eventID` de IDENTIFICADOR del evento que se va a definir.

`keywords` de Palabras clave del evento que se está definiendo.

`eventVersion` de Versión del evento que se va a definir.

`level` de Nivel del evento que se va a definir.

`opcode` de Código de operación del evento que se está definiendo.

`needStack` de Un valor de tipo `BOOL` que indica si las pilas administradas deben recopilarse cada vez que se activa este evento.

`cParamDescs` de Recuento del número de parámetros en `pParamDescs` .

`pParamDescs` de Matriz de `COR_PRF_EVENTPIPE_PARAM_DESC` la definición de los tipos de parámetro para el evento que se está definiendo.

`pEvent` enuncia Un puntero proporcionado por el autor de la llamada que se rellenará con el identificador del evento que se va a definir cuando se devuelva la función.

## <a name="requirements"></a>Requisitos  

**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/windows.md?pivots=os-windows).
**Encabezado:** **Versiones de .net** de Corprof. idl, Corprof. h: [!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]
  
## <a name="see-also"></a>Consulte también

- [Información general sobre EventPipe](../../../core/diagnostics/eventpipe.md)
- [EventProviders conocidos](../../../core/diagnostics/well-known-event-providers.md)
- [Interfaces para generación de perfiles](profiling-interfaces.md)
- [Interfaz ICorProfilerCallback10](icorprofilercallback10-interface.md)
- [Interfaz ICorProfilerInfo12](icorprofilerinfo12-interface.md)
- [Estructura de COR_PRF_EVENTPIPE_PARAM_DESC](cor-prf-eventpipe-param-desc-structure.md)
