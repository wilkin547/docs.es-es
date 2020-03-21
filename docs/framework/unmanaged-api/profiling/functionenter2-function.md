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
ms.openlocfilehash: 9aeb7a294beb10f9c2968e6161c72fdc362c4991
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177064"
---
# <a name="functionenter2-function"></a>FunctionEnter2 (Función)
Notifica al generador de perfiles que el control se pasa a una función y proporciona información sobre el marco de pila y los argumentos de función. Esta función sustituye a la función [FunctionEnter.](functionenter-function.md)  
  
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

- `funcId`

  \[en] El identificador de la función a la que se pasa el control.

- `clientData`

  \[en] El identificador de función reasignado, que el generador de perfiles especificó previamente mediante la función [FunctionIDMapper.](functionidmapper-function.md)
  
- `func`

  \[en] `COR_PRF_FRAME_INFO` Un valor que apunta a información sobre el marco de pila.
  
  El generador de perfiles debe tratar esto como un identificador opaco que se puede volver al motor de ejecución en el [ICorProfilerInfo2::GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) método.  
  
- `argumentInfo`

  \[en] Un puntero a una estructura [COR_PRF_FUNCTION_ARGUMENT_INFO](cor-prf-function-argument-info-structure.md) que especifica las ubicaciones en memoria de los argumentos de la función.

  Para acceder a la `COR_PRF_ENABLE_FUNCTION_ARGS` información del argumento, se debe establecer el indicador. El generador de perfiles puede utilizar el método [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) para establecer los indicadores de evento.

## <a name="remarks"></a>Observaciones  
 Los valores `func` de `argumentInfo` los parámetros `FunctionEnter2` y no son válidos después de que la función devuelve porque los valores pueden cambiar o destruirse.  
  
 La `FunctionEnter2` función es una devolución de llamada; debe implementarlo. La implementación `__declspec`debe`naked`usar el atributo de clase de almacenamiento ( ).  
  
 El motor de ejecución no guarda ningún registro antes de llamar a esta función.  
  
- En la entrada, debe guardar todos los registros que utilice, incluidos los de la unidad de punto flotante (FPU).  
  
- Al salir, debe restaurar la pila desprendendo todos los parámetros que fueron empujados por su llamador.  
  
 La implementación de no debe bloquearse porque retrasará la recolección de `FunctionEnter2` elementos no utilizados. La implementación no debe intentar una recolección de elementos no utilizados porque la pila puede no estar en un estado compatible con la recolección de elementos no utilizados. Si se intenta una recolección de `FunctionEnter2` elementos no utilizados, el tiempo de ejecución se bloqueará hasta que se devuelva.  
  
 Además, la `FunctionEnter2` función no debe llamar al código administrado ni de ninguna manera provocar una asignación de memoria administrada.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [FunctionLeave2 (Función)](functionleave2-function.md)
- [FunctionTailcall2 (Función)](functiontailcall2-function.md)
- [Método SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [Funciones estáticas globales para generación de perfiles](profiling-global-static-functions.md)
