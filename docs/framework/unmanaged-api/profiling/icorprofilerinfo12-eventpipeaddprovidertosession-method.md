---
description: 'Más información sobre: ICorProfilerInfo12:: EventPipeAddProviderToSession (método)'
title: 'ICorProfilerInfo12:: EventPipeAddProviderToSession (método)'
ms.date: 03/19/2021
api_name:
- ICorProfilerInfo12.EventPipeAddProviderToSession
api_location:
- coreclr.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 70654660c496211c20459ef9ba37dfbd96b829b3
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805693"
---
# <a name="icorprofilerinfo12eventpipeaddprovidertosession-method"></a>ICorProfilerInfo12:: EventPipeAddProviderToSession (método)

Agrega un proveedor a una sesión de EventPipe existente.
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
    HRESULT EventPipeAddProviderToSession(
        [in] EVENTPIPE_SESSION                 session,
        [in] COR_PRF_EVENTPIPE_PROVIDER_CONFIG providerConfig);
```  
  
## <a name="parameters"></a>Parámetros

`session` de IDENTIFICADOR de la sesión a la que se va a agregar el proveedor.

`providerConfig` de `COR_PRF_EVENTPIPE_PROVIDER_CONFIG` Que describe el proveedor que se va a agregar a la sesión.

## <a name="requirements"></a>Requisitos  

**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/windows.md?pivots=os-windows).
**Encabezado:** **Versiones de .net** de Corprof. idl, Corprof. h: [!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]
  
## <a name="see-also"></a>Consulte también

- [Información general sobre EventPipe](../../../core/diagnostics/eventpipe.md)
- [EventProviders conocidos](../../../core/diagnostics/well-known-event-providers.md)
- [Interfaces para generación de perfiles](profiling-interfaces.md)
- [Interfaz ICorProfilerCallback10](icorprofilercallback10-interface.md)
- [Interfaz ICorProfilerInfo12](icorprofilerinfo12-interface.md)
- [Estructura de COR_PRF_EVENTPIPE_PROVIDER_CONFIG](cor-prf-eventpipe-provider-config-structure.md)
