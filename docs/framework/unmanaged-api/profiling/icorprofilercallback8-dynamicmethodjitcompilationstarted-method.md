---
title: Método ICorProfilerCallback8::DynamicMethodJITCompilationStarted
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationStarted
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5a60f074ce0081df07a61d0b832d542c8873776f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67757984"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationstarted-method"></a>Método ICorProfilerCallback8::DynamicMethodJITCompilationStarted
[Se admite en .NET Framework 4.7 y versiones posteriores]  
  
Notifica al generador de perfiles cada vez que se ha iniciado la compilación JIT de un método dinámico.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT DynamicMethodJITCompilationStarted(  
     [in]  FunctionID  functionId,   
     [in]  BOOL        fIsSafeToBlock,   
     [in]  LPCBYTE     pILHeader,   
     [in]  LONG        cbILHeader   
);  
```  
  
## <a name="parameters"></a>Parámetros  
[in] `functionId`  
El identificador de la función en memoria para que JIT se inicia la compilación.   

[in] `fIsSafeToBlock`   
`true` para indicar que el bloqueo puede causar el tiempo de ejecución esperar el subproceso de llamada devolver desde esta devolución de llamada; `false` para indicar que la de bloqueo no afectará al funcionamiento del tiempo de ejecución.  

[in] `pILHeader`    
Un puntero al primer byte del encabezado de IL del método.   

[in] `cbILHeader`    
El número de bytes en el encabezado de IL. 

## <a name="remarks"></a>Comentarios  

Esta devolución de llamada se desencadena cada vez que un método dinámico está compilado JIT. Esto incluye diversos métodos LCG y código auxiliar de IL. Su objetivo es proporcionar los escritores del generador de perfiles con la suficiente información para identificar el método compilado a los usuarios.

> [!NOTE]
> `functionId` los valores no se puede usar para resolver a sus tokens de metadatos, porque los métodos dinámicos no tienen ningún metadato.

El `pILHeader` puntero solo es válido durante la devolución de llamada.

## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  
  
## <a name="see-also"></a>Vea también

- [DynamicMethodJITCompilationFinished (método)](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [ICorProfilerCallback8 (interfaz)](icorprofilercallback8-interface.md)
