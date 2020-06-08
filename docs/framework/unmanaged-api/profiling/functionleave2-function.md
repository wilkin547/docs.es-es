---
title: FunctionLeave2 (Función)
ms.date: 03/30/2017
api_name:
- FunctionLeave2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionLeave2
helpviewer_keywords:
- FunctionLeave2 function [.NET Framework profiling]
ms.assetid: 8cdac941-8b94-4497-b874-4e571785f3fe
topic_type:
- apiref
ms.openlocfilehash: a2a3d58e0631fceab96c32f9d86fef25973fed84
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500668"
---
# <a name="functionleave2-function"></a>FunctionLeave2 (Función)
Notifica al generador de perfiles que una función está a punto de volver al autor de la llamada y proporciona información sobre el marco de pila y el valor devuelto de la función.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
void __stdcall FunctionLeave2 (  
    [in]  FunctionID                        funcId,  
    [in]  UINT_PTR                          clientData,  
    [in]  COR_PRF_FRAME_INFO                func,  
    [in]  COR_PRF_FUNCTION_ARGUMENT_RANGE  *retvalRange  
);  
```  
  
## <a name="parameters"></a>Parámetros

- `funcId`

  \[in] el identificador de la función que devuelve.

- `clientData`

  \[in] el identificador de la función reasignada, que el generador de perfiles especificó previamente a través de la función [FunctionIDMapper](functionidmapper-function.md) .

- `func`

  \[en] un `COR_PRF_FRAME_INFO` valor que señala a la información sobre el marco de pila.

  El generador de perfiles debe tratarlo como un identificador opaco que se puede devolver al motor de ejecución en el método [ICorProfilerInfo2:: getfunctioninfo2 (](icorprofilerinfo2-getfunctioninfo2-method.md) .  
  
- `retvalRange`

  \[in] un puntero a una estructura de [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) que especifica la ubicación de memoria del valor devuelto de la función.

  Para tener acceso a la información de los valores devueltos, `COR_PRF_ENABLE_FUNCTION_RETVAL` se debe establecer la marca. El generador de perfiles puede utilizar el método [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) para establecer las marcas de evento.

## <a name="remarks"></a>Comentarios  
 Los valores de los `func` `retvalRange` parámetros y no son válidos después de que la `FunctionLeave2` función devuelva, ya que los valores pueden cambiar o destruirse.  
  
 La `FunctionLeave2` función es una devolución de llamada; debe implementarla. La implementación debe usar el `__declspec` `naked` atributo de clase de almacenamiento ().  
  
 El motor de ejecución no guarda ningún registro antes de llamar a esta función.  
  
- En la entrada, debe guardar todos los registros que use, incluidos los de la unidad de punto flotante (FPU).  
  
- Al salir, debe restaurar la pila desactivando todos los parámetros insertados por el autor de la llamada.  
  
 La implementación de `FunctionLeave2` no debe bloquearse porque retrasará la recolección de elementos no utilizados. La implementación no debe intentar una recolección de elementos no utilizados porque es posible que la pila no esté en un estado reconocible para la recolección de elementos no utilizados. Si se intenta realizar una recolección de elementos no utilizados, el tiempo de ejecución se bloqueará hasta que se `FunctionLeave2` devuelva.  
  
 Además, la `FunctionLeave2` función no debe llamar a código administrado ni producir una asignación de memoria administrada.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Corprof. idl  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [FunctionEnter2 (Función)](functionenter2-function.md)
- [FunctionTailcall2 (Función)](functiontailcall2-function.md)
- [Método SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [Funciones estáticas globales para generación de perfiles](profiling-global-static-functions.md)
