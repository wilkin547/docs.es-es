---
description: 'Más información acerca de: FunctionLeave3WithInfo (función)'
title: FunctionLeave3WithInfo (Función)
ms.date: 03/30/2017
api_name:
- FunctionLeave3WithInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionLeave3WithInfo
helpviewer_keywords:
- FunctionLeave3WithInfo function [.NET Framework profiling]
ms.assetid: 5fa68a67-ced6-41c6-a2c0-467060fd0692
topic_type:
- apiref
ms.openlocfilehash: 617ca023f58a180c198751fea9752fe737249331
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2021
ms.locfileid: "104760085"
---
# <a name="functionleave3withinfo-function"></a>FunctionLeave3WithInfo (Función)

Notifica al generador de perfiles que el control se devuelve desde una función y proporciona un identificador que se puede pasar al [método ICorProfilerInfo3:: GetFunctionLeave3Info (](icorprofilerinfo3-getfunctionleave3info-method.md) para recuperar el marco de pila y el valor devuelto.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
void __stdcall FunctionLeave3WithInfo(  
               [in] FunctionIDOrClientID functionIDOrClientID,  
               [in] COR_PRF_ELT_INFO eltInfo);  
```  
  
## <a name="parameters"></a>Parámetros

`functionIDOrClientID` de Identificador de la función de la que se devuelve el control.

`eltInfo` de Un identificador opaco que representa información sobre un marco de pila determinado. Este identificador es válido solo durante la devolución de llamada a la que se pasa.

## <a name="remarks"></a>Observaciones  

 El `FunctionLeave3WithInfo` método de devolución de llamada notifica al generador de perfiles cuando se llama a las funciones y permite que el generador de perfiles use el [método ICorProfilerInfo3:: GetFunctionLeave3Info (](icorprofilerinfo3-getfunctionleave3info-method.md) para inspeccionar el valor devuelto. Para tener acceso a la información del valor devuelto, se debe `COR_PRF_ENABLE_FUNCTION_RETVAL` establecer la marca. El generador de perfiles puede utilizar el [método ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) para establecer las marcas de evento y, a continuación, usar el [método ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3WithInfo (](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) para registrar la implementación de esta función.  
  
 La `FunctionLeave3WithInfo` función es una devolución de llamada; debe implementarla. La implementación debe usar el `__declspec(naked)` atributo de clase de almacenamiento.  
  
 El motor de ejecución no guarda ningún registro antes de llamar a esta función.  
  
- En la entrada, debe guardar todos los registros que use, incluidos los de la unidad de punto flotante (FPU).  
  
- Al salir, debe restaurar la pila desactivando todos los parámetros insertados por el autor de la llamada.  
  
 La implementación de `FunctionLeave3WithInfo` no debe bloquearse porque retrasará la recolección de elementos no utilizados. La implementación no debe intentar una recolección de elementos no utilizados, porque es posible que la pila no esté en un estado reconocible para la recolección de elementos no utilizados. Si se intenta realizar una recolección de elementos no utilizados, el tiempo de ejecución se bloqueará hasta que se `FunctionLeave3WithInfo` devuelva.  
  
 La `FunctionLeave3WithInfo` función no debe llamar a código administrado ni producir una asignación de memoria administrada de ninguna manera.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Corprof. idl  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Getfunctionleave3info (](icorprofilerinfo3-getfunctionleave3info-method.md)
- [FunctionEnter3](functionenter3-function.md)
- [FunctionLeave3](functionleave3-function.md)
- [FunctionTailcall3](functiontailcall3-function.md)
- [FunctionEnter3WithInfo](functionenter3withinfo-function.md)
- [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md)
- [Setenterleavefunctionhooks3 (](icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [Setenterleavefunctionhooks3withinfo (](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [Setfunctionidmapper (](icorprofilerinfo-setfunctionidmapper-method.md)
- [Setfunctionidmapper2 (](icorprofilerinfo3-setfunctionidmapper2-method.md)
- [Funciones estáticas globales para generación de perfiles](profiling-global-static-functions.md)
