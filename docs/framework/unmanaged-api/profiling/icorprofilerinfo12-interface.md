---
description: 'Más información acerca de: interfaz ICorProfilerInfo12'
title: Interfaz ICorProfilerInfo12
ms.date: 03/19/2021
api_name:
- ICorProfilerInfo12
api_location:
- coreclr.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: a8b91eba686478c3e825ae15d6ae95bd0ffad944
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805732"
---
# <a name="icorprofilerinfo12-interface"></a>Interfaz ICorProfilerInfo12

 Una subclase de [ICorProfilerInfo11](icorprofilerinfo11-interface.md) que proporciona métodos para crear sesiones, eventos y proveedores de EventPipe.
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método EventPipeStartSession](icorprofilerinfo12-eventpipestartsession-method.md)|Inicia una sesión de EventPipe del generador de perfiles.|
|[Método EventPipeAddProviderToSession](icorprofilerinfo12-eventpipeaddprovidertosession-method.md)|Agrega un proveedor a una sesión de EventPipe existente.|
|[Método EventPipeStopSession](icorprofilerinfo12-eventpipestopsession-method.md)|Detiene una sesión de EventPipe.|
|[Método EventPipeCreateProvider](icorprofilerinfo12-eventpipecreateprovider-method.md)|Crea un proveedor de EventPipe.|  
|[Método EventPipeGetProviderInfo](icorprofilerinfo12-eventpipegetproviderinfo-method.md)|Obtiene el nombre de un proveedor EventPipe de su identificador.|
|[Método EventPipeDefineEvent](icorprofilerinfo12-eventpipedefineevent-method.md)|Define un evento en un proveedor de EventPipe existente.|  
|[Método EventPipeWriteEvent](icorprofilerinfo12-eventpipewriteevent-method.md)|Escribe un evento EventPipe.|
  
## <a name="requirements"></a>Requisitos  

**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/windows.md?pivots=os-windows).  
**Encabezado:** CorProf.idl, CorProf.h  
**Versiones de .net:**[!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]  

## <a name="see-also"></a>Consulte también

- [Información general sobre EventPipe](../../../core/diagnostics/eventpipe.md)
- [EventProviders conocidos](../../../core/diagnostics/well-known-event-providers.md)
- [Interfaces para generación de perfiles](profiling-interfaces.md)
- [Interfaz ICorProfilerCallback10](icorprofilercallback10-interface.md)
