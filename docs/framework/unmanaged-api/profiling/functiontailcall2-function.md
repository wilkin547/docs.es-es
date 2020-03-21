---
title: FunctionTailcall2 (Función)
ms.date: 03/30/2017
api_name:
- FunctionTailcall2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionTailcall2
helpviewer_keywords:
- FunctionTailcall2 function [.NET Framework profiling]
ms.assetid: 249f9892-b5a9-41e1-b329-28a925904df6
topic_type:
- apiref
ms.openlocfilehash: 60276327617ae24e9bdcebf958613c21d3808429
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175192"
---
# <a name="functiontailcall2-function"></a>FunctionTailcall2 (Función)
Notifica al generador de perfiles que la función que se está ejecutando actualmente está a punto de realizar una llamada de cola a otra función y proporciona información sobre el marco de pila.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
void __stdcall FunctionTailcall2 (  
    [in] FunctionID         funcId,
    [in] UINT_PTR           clientData,
    [in] COR_PRF_FRAME_INFO func  
);  
```  
  
## <a name="parameters"></a>Parámetros

- `funcId`

  \[en] El identificador de la función que se está ejecutando actualmente que está a punto de realizar una llamada de cola.

- `clientData`

  \[en] El identificador de función reasignado, que el generador de perfiles especificó previamente a través de [FunctionIDMapper](functionidmapper-function.md), de la función que se está ejecutando actualmente que está a punto de realizar una llamada de cola.
  
- `func`

  \[en] `COR_PRF_FRAME_INFO` Un valor que apunta a información sobre el marco de pila.

  El generador de perfiles debe tratar esto como un identificador opaco que se puede volver al motor de ejecución en el [ICorProfilerInfo2::GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md) método.

## <a name="remarks"></a>Observaciones  
 La función de destino de la llamada de cola utilizará el marco de pila actual y volverá directamente al llamador de la función que realizó la llamada de cola. Esto significa que no se emitirá una devolución de llamada [FunctionLeave2](functionleave2-function.md) para una función que sea el destino de una llamada de cola.  
  
 El valor `func` del parámetro no `FunctionTailcall2` es válido después de que la función devuelve porque el valor puede cambiar o destruirse.  
  
 La `FunctionTailcall2` función es una devolución de llamada; debe implementarlo. La implementación `__declspec`debe`naked`usar el atributo de clase de almacenamiento ( ).  
  
 El motor de ejecución no guarda ningún registro antes de llamar a esta función.  
  
- En la entrada, debe guardar todos los registros que utilice, incluidos los de la unidad de punto flotante (FPU).  
  
- Al salir, debe restaurar la pila desprendendo todos los parámetros que fueron empujados por su llamador.  
  
 La implementación de no debe bloquearse porque retrasará la recolección de `FunctionTailcall2` elementos no utilizados. La implementación no debe intentar una recolección de elementos no utilizados porque la pila puede no estar en un estado compatible con la recolección de elementos no utilizados. Si se intenta una recolección de `FunctionTailcall2` elementos no utilizados, el tiempo de ejecución se bloqueará hasta que se devuelva.  
  
 Además, la `FunctionTailcall2` función no debe llamar al código administrado ni de ninguna manera provocar una asignación de memoria administrada.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [FunctionEnter2 (Función)](functionenter2-function.md)
- [FunctionLeave2 (Función)](functionleave2-function.md)
- [Método SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [Funciones estáticas globales para generación de perfiles](profiling-global-static-functions.md)
