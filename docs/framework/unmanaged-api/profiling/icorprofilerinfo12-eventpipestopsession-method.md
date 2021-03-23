---
description: 'Más información sobre: ICorProfilerInfo12:: EventPipeStopSession (método)'
title: 'ICorProfilerInfo12:: EventPipeStopSession (método)'
ms.date: 03/19/2021
api_name:
- ICorProfilerInfo12.EventPipeStopSession
api_location:
- coreclr.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: c1b104f63755bcec52a113be7e2aa9af76ecd34e
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805719"
---
# <a name="icorprofilerinfo12eventpipestopsession-method"></a>ICorProfilerInfo12:: EventPipeStopSession (método)

Detiene una sesión de EventPipe, evitando que se escriban eventos futuros en la sesión.
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
    HRESULT EventPipeStopSession(
        [in] EVENTPIPE_SESSION session);
```  
  
## <a name="parameters"></a>Parámetros

`session` de IDENTIFICADOR de la sesión que se va a detener.

## <a name="requirements"></a>Requisitos  

**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/windows.md?pivots=os-windows).
**Encabezado:** **Versiones de .net** de Corprof. idl, Corprof. h: [!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]
  
## <a name="see-also"></a>Consulte también

- [Interfaces para generación de perfiles](profiling-interfaces.md)
- [Interfaz ICorProfilerCallback10](icorprofilercallback10-interface.md)
- [Interfaz ICorProfilerInfo12](icorprofilerinfo12-interface.md)
