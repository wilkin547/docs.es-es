---
title: ICorProfilerCallback9::DynamicMethodUnloaded (método)
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
ms.openlocfilehash: 16b3334647922f845645e6eb58db3146f4c9b936
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452408"
---
# <a name="icorprofilercallback9dynamicmethodunloaded-method"></a>ICorProfilerCallback9::DynamicMethodUnloaded (método)
[Compatible con .NET Framework 4.7.2 y versiones posteriores]  
  
Notifica al generador de perfiles siempre que un método dinámico es recolectado y posteriormente se descargan.  
  
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
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vea también  
[ICorProfilerCallback8.DynamicMethodJITCompilationStarted (método)](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)  
[ICorProfilerCallback8.DynamicMethodJITCompilationFinished (método)](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)  
[Interfaz ICorProfilerCallback9](icorprofilercallback9-interface.md)   
[COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS](cor-prf-high-monitor-enumeration.md)
