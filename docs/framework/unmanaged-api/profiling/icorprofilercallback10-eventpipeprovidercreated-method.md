---
description: 'Más información sobre: ICorProfilerCallback10:: EventPipeProviderCreated (método)'
title: 'ICorProfilerCallback10:: EventPipeProviderCreated (método)'
ms.date: 03/19/2021
api_name:
- ICorProfilerCallback10.EventPipeProviderCreated
api_location:
- coreclr.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 4602438148a369f2a2321a2ec2e959cc375e37cf
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805589"
---
# <a name="icorprofilercallback10eventpipeprovidercreated-method"></a>ICorProfilerCallback10:: EventPipeProviderCreated (método)

Notifica al generador de perfiles cada vez que se crea un proveedor de EventPipe.
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
    HRESULT EventPipeProviderCreated([in] EVENTPIPE_PROVIDER provider); 
```  
  
## <a name="parameters"></a>Parámetros

`provider` de Proveedor que se ha creado.

## <a name="requirements"></a>Requisitos  

**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/windows.md?pivots=os-windows).  
**Encabezado:** CorProf.idl, CorProf.h  
**Versiones de .net:**[!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaces para generación de perfiles](profiling-interfaces.md)
- [Interfaz ICorProfilerCallback10](icorprofilercallback10-interface.md)
- [Interfaz ICorProfilerInfo12](icorprofilerinfo12-interface.md)
- [ICorProfilerInfo12. EventPipeAddProviderToSession, método](icorprofilerinfo12-eventpipeaddprovidertosession-method.md)
