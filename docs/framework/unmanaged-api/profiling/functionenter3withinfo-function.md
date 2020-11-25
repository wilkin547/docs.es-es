---
title: FunctionEnter3WithInfo (Función)
ms.date: 03/30/2017
api_name:
- FunctionEnter3WithInfo
api_location:
- mscorwks.cll
api_type:
- COM
f1_keywords:
- FunctionEnter3WithInfo
helpviewer_keywords:
- FunctionEnter3WithInfo function [.NET Framework profiling]
ms.assetid: 277c3344-d0cb-431e-beae-eb1eeeba8eea
topic_type:
- apiref
ms.openlocfilehash: b511c5abe10ab6c0ec856a5686b082132ed4a5d9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722872"
---
# <a name="functionenter3withinfo-function"></a>FunctionEnter3WithInfo (Función)

Notifica al generador de perfiles que el control se pasa a una función y proporciona un identificador que se puede pasar al [método ICorProfilerInfo3:: GetFunctionEnter3Info (](icorprofilerinfo3-getfunctionenter3info-method.md) para recuperar el marco de pila y los argumentos de la función.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
void __stdcall FunctionEnter3WithInfo(  
               [in] FunctionIDOrClientID functionIDOrClientID,  
               [in] COR_PRF_ELT_INFO eltInfo);  
```  
  
## <a name="parameters"></a>Parámetros

- `functionIDOrClientID`

  \[in] el identificador de la función a la que se pasa el control.

- `eltInfo`

  \[in] un identificador opaco que representa información sobre un marco de pila determinado. Este identificador es válido solo durante la devolución de llamada a la que se pasa.

## <a name="remarks"></a>Comentarios  

 El `FunctionEnter3WithInfo` método de devolución de llamada notifica al generador de perfiles cuando se llama a las funciones y permite al generador de perfiles usar el [método ICorProfilerInfo3:: GetFunctionEnter3Info (](icorprofilerinfo3-getfunctionenter3info-method.md) para inspeccionar los valores de argumento. Para tener acceso a la información de los argumentos, se debe `COR_PRF_ENABLE_FUNCTION_ARGS` establecer la marca. El generador de perfiles puede utilizar el [método ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) para establecer las marcas de evento y, a continuación, usar el [método ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3WithInfo (](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) para registrar la implementación de esta función.  
  
 La `FunctionEnter3WithInfo` función es una devolución de llamada; debe implementarla. La implementación debe usar el `__declspec(naked)` atributo de clase de almacenamiento.  
  
 El motor de ejecución no guarda ningún registro antes de llamar a esta función.  
  
- En la entrada, debe guardar todos los registros que use, incluidos los de la unidad de punto flotante (FPU).  
  
- Al salir, debe restaurar la pila desactivando todos los parámetros insertados por el autor de la llamada.  
  
 La implementación de `FunctionEnter3WithInfo` no debe bloquearse porque retrasará la recolección de elementos no utilizados. La implementación no debe intentar una recolección de elementos no utilizados, porque es posible que la pila no esté en un estado reconocible para la recolección de elementos no utilizados. Si se intenta realizar una recolección de elementos no utilizados, el tiempo de ejecución se bloqueará hasta que se `FunctionEnter3WithInfo` devuelva.  
  
 La `FunctionEnter3WithInfo` función no debe llamar a código administrado ni producir una asignación de memoria administrada de ninguna manera.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Corprof. idl  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Getfunctionenter3info (](icorprofilerinfo3-getfunctionenter3info-method.md)
- [FunctionEnter3](functionenter3-function.md)
- [FunctionLeave3](functionleave3-function.md)
- [Funciones estáticas globales para generación de perfiles](profiling-global-static-functions.md)
