---
title: ICorProfilerCallback4::ReJITCompilationFinished (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.ReJITCompilationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::ReJITCompilationFinished
helpviewer_keywords:
- ICorProfilerCallback4::ReJITCompilationFinished method [.NET Framework profiling]
- ReJITCompilationFinished method, ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 3b5cff02-2005-44eb-a2bc-50214c4b0e1d
topic_type:
- apiref
ms.openlocfilehash: e010a49dabd3b44602136e70b4c5524a68bdd9e2
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865212"
---
# <a name="icorprofilercallback4rejitcompilationfinished-method"></a>ICorProfilerCallback4::ReJITCompilationFinished (Método)
Notifica al generador de perfiles que el compilador Just-in-Time (JIT) ha terminado de volver a compilar una función.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ReJITCompilationFinished(  
    [in] FunctionID functionId,    [in] ReJITID rejitId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a>Parameters  
 `functionId`  
 de IDENTIFICADOR de la función que se volvió a compilar.  
  
 `rejitId`  
 [in] Identidad de la función recompilada con JIT.  
  
 `hrStatus`  
 de Valor que indica si la recompilación JIT se realizó correctamente.  
  
 `fIsSafeToBlock`  
 [in] `true` para indicar que el bloqueo puede hacer que el tiempo de ejecución espere a que el subproceso que realiza la llamada devuelva de esta devolución de llamada; `false` para indicar que el bloqueo no afectará al funcionamiento del tiempo de ejecución.  
  
 Un valor de `true` no perjudica al tiempo de ejecución, pero puede afectar a los resultados de la generación de perfiles.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerCallback (interfaz)](icorprofilercallback-interface.md)
- [ICorProfilerCallback4 (interfaz)](icorprofilercallback4-interface.md)
- [JITCompilationStarted (método)](icorprofilercallback-jitcompilationstarted-method.md)
- [ReJITCompilationStarted (método)](icorprofilercallback4-rejitcompilationstarted-method.md)
