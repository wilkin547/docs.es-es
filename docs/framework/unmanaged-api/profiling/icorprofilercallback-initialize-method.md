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
ms.openlocfilehash: 64df6a81eb23c20537238c702fd0c204d64d14bc
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434556"
---
# <a name="icorprofilercallbackinitialize-method"></a>ICorProfilerCallback::Initialize (Método)
Se llama para inicializar el generador de perfiles de código cada vez que se inicia una nueva aplicación de Common Language Runtime (CLR).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT Initialize(  
    [in] IUnknown     *pICorProfilerInfoUnk);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pICorProfilerInfoUnk`  
 [en](/cpp/atl/iunknown) la interfaz que el generador de perfiles debe consultar para un puntero de interfaz [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) .  
  
## <a name="remarks"></a>Comentarios  
 La llamada a `Initialize` es la única oportunidad para habilitar (o deshabilitar) las devoluciones de llamada inmutables. Una vez que la llamada a `Initialize` habilita una devolución de llamada, no se puede deshabilitar posteriormente mediante [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md). El valor COR_PRF_MONITOR_IMMUTABLE de la enumeración [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) indica qué eventos son inmutables.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerCallback (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [Shutdown (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-shutdown-method.md)
