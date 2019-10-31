---
title: ICorProfilerCallback8::D método ynamicMethodJITCompilationFinished
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationFinished
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 0e04459614ca697908fb9b71ecc3931ac305a838
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136585"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationfinished-method"></a>ICorProfilerCallback8::D método ynamicMethodJITCompilationFinished
[Se admite en el .NET Framework 4,7 y versiones posteriores]  
  
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

[in] `hrStatus`   
Valor que indica si la compilación JIT se realizó correctamente.

[in] `fIsSafeToBlock`   
`true` para indicar que el bloqueo puede hacer que el tiempo de ejecución espere a que el subproceso que realiza la llamada devuelva de esta devolución de llamada; `false` para indicar que el bloqueo no afectará al funcionamiento del tiempo de ejecución.  

## <a name="remarks"></a>Comentarios  

Esta devolución de llamada se desencadena cuando finaliza la compilación JIT de un método dinámico. Esto incluye varios códigos auxiliares de IL y métodos LCG. Su objetivo es proporcionar a los escritores de Profiler información suficiente para identificar el método compilado para los usuarios.

> [!NOTE]
> `functionId` valores no se pueden usar para resolver sus tokens de metadatos, porque los métodos dinámicos no tienen metadatos.

## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  
  
## <a name="see-also"></a>Vea también

- [DynamicMethodJITCompilationStarted (método)](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [ICorProfilerCallback8 (interfaz)](icorprofilercallback8-interface.md)
