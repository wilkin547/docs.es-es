---
description: 'Más información acerca de: ICorProfilerCallback8::D ynamicMethodJITCompilationStarted (método)'
title: ICorProfilerCallback8::D método ynamicMethodJITCompilationStarted
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationStarted
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: c03251ab3120fd93cbb8e6c2f1bb62a4527a92bb
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2021
ms.locfileid: "104759929"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationstarted-method"></a>ICorProfilerCallback8::D método ynamicMethodJITCompilationStarted

[Se admite en el .NET Framework 4,7 y versiones posteriores]  
  
Notifica al generador de perfiles cada vez que se inicia la compilación JIT de un método dinámico.  
  
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

`functionId`  
de Identificador de la función en memoria para la que se inicia la compilación JIT.

`fIsSafeToBlock` [in] `true` para indicar que el bloqueo puede hacer que el tiempo de ejecución espere a que el subproceso que realiza la llamada devuelva de esta devolución de llamada; `false` para indicar que el bloqueo no afectará al funcionamiento del tiempo de ejecución.  

`pILHeader` de Puntero al primer byte del encabezado IL del método.

`cbILHeader` de Número de bytes del encabezado IL.

## <a name="remarks"></a>Observaciones  

Esta devolución de llamada se desencadena cada vez que se compila un método dinámico. Esto incluye varios códigos auxiliares de IL y métodos LCG. Su objetivo es proporcionar a los escritores de Profiler información suficiente para identificar el método compilado para los usuarios.

> [!NOTE]
> `functionId` los valores no se pueden usar para resolver sus tokens de metadatos, porque los métodos dinámicos no tienen metadatos.

El `pILHeader` puntero solo es válido durante la devolución de llamada.

## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  
  
## <a name="see-also"></a>Consulte también

- [Método DynamicMethodJITCompilationFinished](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [Interfaz ICorProfilerCallback8](icorprofilercallback8-interface.md)
