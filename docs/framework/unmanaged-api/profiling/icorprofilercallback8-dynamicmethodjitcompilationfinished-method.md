---
title: Método ICorProfilerCallback8::DynamicMethodJITCompilationFinished
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationFinished
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ba9f9d4ee5f95def3dcd2d757517e225c826cb9e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67757994"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationfinished-method"></a>Método ICorProfilerCallback8::DynamicMethodJITCompilationFinished
[Se admite en .NET Framework 4.7 y versiones posteriores]  
  
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
El identificador de la función en memoria para que JIT se inicia la compilación.   

[in] `hrStatus`   
Un valor que indica si la compilación JIT fue correcta.

[in] `fIsSafeToBlock`   
`true` para indicar que el bloqueo puede causar el tiempo de ejecución esperar el subproceso de llamada devolver desde esta devolución de llamada; `false` para indicar que la de bloqueo no afectará al funcionamiento del tiempo de ejecución.  

## <a name="remarks"></a>Comentarios  

Esta devolución de llamada se desencadena cada vez que ha finalizado la compilación JIT de un método dinámico. Esto incluye diversos métodos LCG y código auxiliar de IL. Su objetivo es proporcionar los escritores del generador de perfiles con la suficiente información para identificar el método compilado a los usuarios.

> [!NOTE]
> `functionId` los valores no se puede usar para resolver a sus tokens de metadatos, porque los métodos dinámicos no tienen ningún metadato.

## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  
  
## <a name="see-also"></a>Vea también

- [DynamicMethodJITCompilationStarted (método)](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [ICorProfilerCallback8 (interfaz)](icorprofilercallback8-interface.md)
