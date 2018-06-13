---
title: ICorProfilerCallback8::DynamicMethodJITCompilationStarted (método)
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
ms.openlocfilehash: ad74eeb4deeae73be40b3a0bc0f6a18ec2299780
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33454755"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationstarted-method"></a>ICorProfilerCallback8::DynamicMethodJITCompilationStarted (método)
[Compatible con .NET Framework 4.7 y versiones posteriores]  
  
Notifica al generador de perfiles cada vez que se ha iniciado la compilación JIT de un método dinámico.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT DynamicMethodJITCompilationStarted(  
     [in]  FunctionID  functionId,   
     [in]  BOOL        fIsSafeToBlock,   
     [in]  LPCBYTE     pILHeader,   
     [in]  LONG        cbILHeader   
);  
```  
  
#### <a name="parameters"></a>Parámetros  
[in] `functionId`  
El identificador de la función en memoria para qué JIT se inicia la compilación.   

[in] `fIsSafeToBlock`   
`true` para indicar que el bloqueo puede causar el tiempo de ejecución esperar el subproceso de llamada devolver desde esta devolución de llamada; `false` para indicar que el bloqueo no afectará al funcionamiento del tiempo de ejecución.  

[in] `pILHeader`    
Un puntero al primer byte del encabezado de IL del método.   

[in] `cbILHeader`    
El número de bytes en el encabezado de IL. 

## <a name="remarks"></a>Comentarios  

Esta devolución de llamada se desencadena cuando un método dinámico está compilado JIT. Esto incluye diversos métodos LCG y códigos auxiliares de IL. Su objetivo es proporcionar suficiente información para identificar el método compilado a los usuarios a escritores profiler.

> [!NOTE]
> `functionId` valores no se puede usar para resolver a sus tokens de metadatos, porque los métodos dinámicos no tienen metadatos.

El `pILHeader` puntero solo es válido durante la devolución de llamada.

## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  
  
## <a name="see-also"></a>Vea también  
 [DynamicMethodJITCompilationFinished (método)](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)  
 [Interfaz ICorProfilerCallback8](icorprofilercallback8-interface.md)
