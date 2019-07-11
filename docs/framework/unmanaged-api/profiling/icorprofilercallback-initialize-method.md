---
title: ICorProfilerCallback::Initialize (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.Initialize
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::Initialize
helpviewer_keywords:
- Initialize method, ICorProfilerCallback interface [.NET Framework profiling]
- ICorProfilerCallback::Initialize method [.NET Framework profiling]
ms.assetid: dc5fab2a-4b45-4b12-8727-b89c9915f23e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e50421dc15dd30f1811dbe5ebef2ff2f7a0a9483
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67755827"
---
# <a name="icorprofilercallbackinitialize-method"></a>ICorProfilerCallback::Initialize (Método)
Se llama para inicializar el generador de perfiles de código cuando se inicia una nueva aplicación de common language runtime (CLR).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT Initialize(  
    [in] IUnknown     *pICorProfilerInfoUnk);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pICorProfilerInfoUnk`  
 [en](/cpp/atl/iunknown) interfaz que el generador de perfiles debe consultar un [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) puntero de interfaz.  
  
## <a name="remarks"></a>Comentarios  
 El `Initialize` llamada es la única oportunidad de habilitar (o deshabilitar) las devoluciones de llamada que son inmutables. Una vez que una devolución de llamada está habilitada de forma el `Initialize` llamar a, no puede deshabilitarse más adelante mediante [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md). El valor COR_PRF_MONITOR_IMMUTABLE de la [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeración indica qué eventos son inmutables.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerCallback (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [Shutdown (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-shutdown-method.md)
