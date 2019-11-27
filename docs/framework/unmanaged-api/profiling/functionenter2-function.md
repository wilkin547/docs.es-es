---
title: FunctionEnter2 (Función)
ms.date: 03/30/2017
api_name:
- FunctionEnter2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionEnter2
helpviewer_keywords:
- FunctionEnter2 function [.NET Framework profiling]
ms.assetid: ce7a21f9-0ca3-4b92-bc4b-bb803cae3f51
topic_type:
- apiref
ms.openlocfilehash: f4deec3e2b49b5cd6a924af8024e775c5c549f97
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440851"
---
# <a name="functionenter2-function"></a>FunctionEnter2 (Función)
Notifica al generador de perfiles que el control se pasa a una función y proporciona información sobre el marco de pila y los argumentos de la función. Esta función reemplaza la función [FunctionEnter (](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md) .  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
void __stdcall FunctionEnter2 (  
    [in]  FunctionID                       funcId,   
    [in]  UINT_PTR                         clientData,   
    [in]  COR_PRF_FRAME_INFO               func,   
    [in]  COR_PRF_FUNCTION_ARGUMENT_INFO  *argumentInfo  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `funcId`  
 de Identificador de la función a la que se pasa el control.  
  
 `clientData`  
 de Identificador de la función reasignada, que el generador de perfiles especificó anteriormente mediante la función [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) .  
  
 `func`  
 de `COR_PRF_FRAME_INFO` valor que apunta a la información sobre el marco de pila.  
  
 El generador de perfiles debe tratarlo como un identificador opaco que se puede devolver al motor de ejecución en el método [ICorProfilerInfo2:: getfunctioninfo2 (](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) .  
  
 `argumentInfo`  
 de Puntero a una estructura de [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) que especifica las ubicaciones en memoria de los argumentos de la función.  
  
 Para tener acceso a la información de los argumentos, se debe establecer la marca `COR_PRF_ENABLE_FUNCTION_ARGS`. El generador de perfiles puede utilizar el método [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) para establecer las marcas de evento.  
  
## <a name="remarks"></a>Comentarios  
 Los valores de los parámetros `func` y `argumentInfo` no son válidos después de que se devuelva la función `FunctionEnter2` porque los valores pueden cambiar o ser destruidos.  
  
 La función `FunctionEnter2` es una devolución de llamada; debe implementarla. La implementación debe usar el atributo de clase de almacenamiento `__declspec`(`naked`).  
  
 El motor de ejecución no guarda ningún registro antes de llamar a esta función.  
  
- En la entrada, debe guardar todos los registros que use, incluidos los de la unidad de punto flotante (FPU).  
  
- Al salir, debe restaurar la pila desactivando todos los parámetros insertados por el autor de la llamada.  
  
 La implementación de `FunctionEnter2` no debe bloquearse porque retrasará la recolección de elementos no utilizados. La implementación no debe intentar una recolección de elementos no utilizados porque es posible que la pila no esté en un estado reconocible para la recolección de elementos no utilizados. Si se intenta realizar una recolección de elementos no utilizados, el tiempo de ejecución se bloqueará hasta que `FunctionEnter2` devuelva.  
  
 Además, la función `FunctionEnter2` no debe llamar a código administrado ni producir una asignación de memoria administrada.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Corprof. idl  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [FunctionLeave2 (Función)](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)
- [FunctionTailcall2 (Función)](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)
- [SetEnterLeaveFunctionHooks2 (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [Funciones estáticas globales para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
