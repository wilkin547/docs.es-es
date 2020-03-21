---
title: ICorProfilerCallback8::DynamicMethodJITCompilationFinished Método
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationFinished
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: c2e9489654a0fe5fa65ec638ed0f991a6c01415a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175114"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationfinished-method"></a>ICorProfilerCallback8::DynamicMethodJITCompilationFinished Método
[Soportado en .NET Framework 4.7 y versiones posteriores]  
  
Notifica al generador de perfiles cada vez que se ha completado la compilación JIT de un método dinámico.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT DynamicMethodJITCompilationFinished(  
     [in]  FunctionID  functionId,
     [in]  BOOL        hrStatus,
     [in]  BOOL        fIsSafeToBlock
);  
```  
  
## <a name="parameters"></a>Parámetros  
[in] `functionId`  
Identificador de la función en memoria para la que se inicia la compilación JIT.

[en] `hrStatus` Valor que indica si la compilación JIT se realizó correctamente.

[en] `fIsSafeToBlock` para indicar que el bloqueo puede hacer que el tiempo de ejecución espere a que el subproceso que realiza la llamada vuelva de esta devolución de 
 `true` llamada; `false` para indicar que el bloqueo no afectará al funcionamiento del tiempo de ejecución.  

## <a name="remarks"></a>Observaciones  

Esta devolución de llamada se desencadena cada vez que la compilación JIT de un método dinámico ha finalizado. Esto incluye varios talones de IL y métodos LCG. Su objetivo es proporcionar a los escritores de generadores de perfiles suficiente información para identificar el método compilado a los usuarios.

> [!NOTE]
> `functionId`los valores no se pueden usar para resolver en sus tokens de metadatos, porque los métodos dinámicos no tienen metadatos.

## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  
  
## <a name="see-also"></a>Consulte también

- [DynamicMethodJITCompilationStarted (método)](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [ICorProfilerCallback8 (interfaz)](icorprofilercallback8-interface.md)
