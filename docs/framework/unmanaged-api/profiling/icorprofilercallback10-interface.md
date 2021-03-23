---
description: 'Más información acerca de: interfaz ICorProfilerCallback10'
title: Interfaz ICorProfilerCallback10
ms.date: 03/19/2021
api_name:
- ICorProfilerCallback10
api_location:
- coreclr.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: d9091dc81307e2dcb83e74154a8217dffaa1e7a2
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805654"
---
# <a name="icorprofilercallback10-interface"></a>Interfaz ICorProfilerCallback10

 Una subclase de [ICorProfilerCallback9](icorprofilercallback9-interface.md) que proporciona métodos de devolución de llamada para notificar al generador de perfiles que se han entregado eventos EventPipe a la sesión activa del generador de perfiles.
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método EventPipeEventDelivered](icorprofilercallback10-eventpipeeventdelivered-method.md)|Notifica al generador de perfiles que se ha entregado un evento EventPipe a la sesión que el generador de perfiles tiene abierto.|
|[Método EventPipeProviderCreated](icorprofilercallback10-eventpipeprovidercreated-method.md)|Notifica al generador de perfiles que se ha creado un proveedor EventPipe, lo que permite al generador de perfiles agregar ese proveedor a su sesión.|  
  
## <a name="requirements"></a>Requisitos  

**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/windows.md?pivots=os-windows).  
**Encabezado:** CorProf.idl, CorProf.h  
**Versiones de .net:**[!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]  

## <a name="see-also"></a>Consulte también

- [Información general sobre EventPipe](../../../core/diagnostics/eventpipe.md)
- [EventProviders conocidos](../../../core/diagnostics/well-known-event-providers.md)
- [Interfaces para generación de perfiles](profiling-interfaces.md)
- [Interfaz ICorProfilerInfo12](ICorProfilerInfo12-interface.md)
- [ICorProfilerInfo12. EventPipeStartSession, método](ICorProfilerInfo12-eventpipestartsession-method.md)
- [ICorProfilerInfo12. EventPipeStopSession, método](ICorProfilerInfo12-eventpipestopsession-method.md)
