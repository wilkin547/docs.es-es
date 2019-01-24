---
title: Método ICorProfilerCallback9::DynamicMethodUnloaded
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback9.DynamicMethodUnloaded
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 27e68c82a04b78a18f51f0a2c9ec712036521368
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54513547"
---
# <a name="icorprofilercallback9dynamicmethodunloaded-method"></a>Método ICorProfilerCallback9::DynamicMethodUnloaded
[Compatible con .NET Framework 4.7.2 y versiones posteriores]  
  
Notifica al generador de perfiles cada vez que un método dinámico es recolectado y posteriormente descargan.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT DynamicMethodUnloaded(  
     [in]  FunctionID  functionId
);  
```  
  
#### <a name="parameters"></a>Parámetros  
[in] `functionId`  
El identificador de la función en memoria que se ha recolectado y descarga.   

## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vea también
- [Método ICorProfilerCallback8.DynamicMethodJITCompilationStarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [Método ICorProfilerCallback8.DynamicMethodJITCompilationFinished](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [ICorProfilerCallback9 (interfaz)](icorprofilercallback9-interface.md)
- [COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS](cor-prf-high-monitor-enumeration.md)
