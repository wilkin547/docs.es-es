---
description: 'Más información acerca de: ICorProfilerCallback:: Initialize (método)'
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
ms.openlocfilehash: c7138a1a39a1d32c751c205a86c00e6070a236b3
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2021
ms.locfileid: "104760423"
---
# <a name="icorprofilercallbackinitialize-method"></a>ICorProfilerCallback::Initialize (Método)

Se llama para inicializar el generador de perfiles de código cada vez que se inicia una nueva aplicación de Common Language Runtime (CLR).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT Initialize(  
    [in] IUnknown     *pICorProfilerInfoUnk);  
```  
  
## <a name="parameters"></a>Parámetros

`pICorProfilerInfoUnk` de Puntero a una interfaz [IUnknown](/cpp/atl/iunknown) que el generador de perfiles debe consultar para un puntero de interfaz [ICorProfilerInfo](icorprofilerinfo-interface.md) .  

## <a name="remarks"></a>Observaciones  

 La `Initialize` llamada es la única oportunidad para habilitar (o deshabilitar) las devoluciones de llamada que son inmutables. Una vez que la llamada habilita una devolución de llamada `Initialize` , no se puede deshabilitar posteriormente mediante [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md). El valor COR_PRF_MONITOR_IMMUTABLE de la enumeración [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) indica qué eventos son inmutables.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorProfilerCallback (Interfaz)](icorprofilercallback-interface.md)
- [Método Shutdown](icorprofilercallback-shutdown-method.md)
