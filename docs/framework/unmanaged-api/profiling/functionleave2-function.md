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
ms.openlocfilehash: 0b1ecd1266528f8a08ef114de2f111dd0f71ca8b
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866936"
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
  
## <a name="parameters"></a>Parameters

- `funcId`

  \[en] el identificador de la función que devuelve.

- `clientData`

  \[in] identificador de la función reasignada, que el generador de perfiles especificó previamente a través de la función [FunctionIDMapper](functionidmapper-function.md) .

- `func`

  \[en] un valor `COR_PRF_FRAME_INFO` que apunta a la información sobre el marco de pila.

  El generador de perfiles debe tratarlo como un identificador opaco que se puede devolver al motor de ejecución en el método [ICorProfilerInfo2:: getfunctioninfo2 (](icorprofilerinfo2-getfunctioninfo2-method.md) .  
  
- `retvalRange`

  \[in] un puntero a una estructura de [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) que especifica la ubicación de memoria del valor devuelto de la función.

  Para tener acceso a la información de los valores devueltos, se debe establecer la marca `COR_PRF_ENABLE_FUNCTION_RETVAL`. El generador de perfiles puede utilizar el método [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) para establecer las marcas de evento.

## <a name="remarks"></a>Notas  
 Los valores de los parámetros `func` y `retvalRange` no son válidos después de que se devuelva la función `FunctionLeave2` porque los valores pueden cambiar o ser destruidos.  
  
 La función `FunctionLeave2` es una devolución de llamada; debe implementarla. La implementación debe usar el atributo de clase de almacenamiento `__declspec`(`naked`).  
  
 El motor de ejecución no guarda ningún registro antes de llamar a esta función.  
  
- En la entrada, debe guardar todos los registros que use, incluidos los de la unidad de punto flotante (FPU).  
  
- Al salir, debe restaurar la pila desactivando todos los parámetros insertados por el autor de la llamada.  
  
 La implementación de `FunctionLeave2` no debe bloquearse porque retrasará la recolección de elementos no utilizados. La implementación no debe intentar una recolección de elementos no utilizados porque es posible que la pila no esté en un estado reconocible para la recolección de elementos no utilizados. Si se intenta realizar una recolección de elementos no utilizados, el tiempo de ejecución se bloqueará hasta que `FunctionLeave2` devuelva.  
  
 Además, la función `FunctionLeave2` no debe llamar a código administrado ni producir una asignación de memoria administrada.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Corprof. idl  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [FunctionEnter2 (Función)](functionenter2-function.md)
- [FunctionTailcall2 (Función)](functiontailcall2-function.md)
- [SetEnterLeaveFunctionHooks2 (método)](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [Funciones estáticas globales para generación de perfiles](profiling-global-static-functions.md)
