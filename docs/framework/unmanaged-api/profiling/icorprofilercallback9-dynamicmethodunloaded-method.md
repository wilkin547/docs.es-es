---
description: 'Más información acerca de: ICorProfilerCallback9::D ynamicMethodUnloaded (método)'
title: ICorProfilerCallback9::D método ynamicMethodUnloaded
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback9.DynamicMethodUnloaded
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 243660d3159e3c8c1d052c08e9c7499e7065d301
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753333"
---
# <a name="icorprofilercallback9dynamicmethodunloaded-method"></a>ICorProfilerCallback9::D método ynamicMethodUnloaded

[Se admite en el .NET Framework 4.7.2 y versiones posteriores]  
  
Notifica al generador de perfiles cada vez que un método dinámico se recolecta como elemento no utilizado y, posteriormente, se descarga.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT DynamicMethodUnloaded(  
     [in]  FunctionID  functionId
);  
```  
  
## <a name="parameters"></a>Parámetros  

[in] `functionId`  
El identificador de la función en memoria que se ha recolectado y descargado.

## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerCallback8. DynamicMethodJITCompilationStarted, método](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [ICorProfilerCallback8. DynamicMethodJITCompilationFinished, método](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [Interfaz ICorProfilerCallback9](icorprofilercallback9-interface.md)
- [COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS](cor-prf-high-monitor-enumeration.md)
