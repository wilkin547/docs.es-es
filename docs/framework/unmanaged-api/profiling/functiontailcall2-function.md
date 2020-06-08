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
ms.openlocfilehash: cb7e21e0c6aad5ebb328ae5d1a993716f96e8d47
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500577"
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

  \[in] el identificador de la función que se ejecuta actualmente y que está a punto de realizar una llamada de cola.

- `clientData`

  \[in] el identificador de la función reasignada, que el generador de perfiles especificó previamente a través de [FunctionIDMapper](functionidmapper-function.md), de la función que se ejecuta actualmente y que está a punto de realizar una llamada de cola.
  
- `func`

  \[en] un `COR_PRF_FRAME_INFO` valor que señala a la información sobre el marco de pila.

  El generador de perfiles debe tratarlo como un identificador opaco que se puede devolver al motor de ejecución en el método [ICorProfilerInfo2:: getfunctioninfo2 (](icorprofilerinfo2-getfunctioninfo2-method.md) .

## <a name="remarks"></a>Comentarios  
 La función de destino de la llamada de cola usará el marco de pila actual y devolverá directamente al llamador de la función que realizó la llamada de cola. Esto significa que no se emitirá una devolución de llamada de [FunctionLeave2](functionleave2-function.md) para una función que sea el destino de una llamada de cola.  
  
 El valor del `func` parámetro no es válido después de que la `FunctionTailcall2` función devuelva porque el valor puede cambiar o ser destruido.  
  
 La `FunctionTailcall2` función es una devolución de llamada; debe implementarla. La implementación debe usar el `__declspec` `naked` atributo de clase de almacenamiento ().  
  
 El motor de ejecución no guarda ningún registro antes de llamar a esta función.  
  
- En la entrada, debe guardar todos los registros que use, incluidos los de la unidad de punto flotante (FPU).  
  
- Al salir, debe restaurar la pila desactivando todos los parámetros insertados por el autor de la llamada.  
  
 La implementación de `FunctionTailcall2` no debe bloquearse porque retrasará la recolección de elementos no utilizados. La implementación no debe intentar una recolección de elementos no utilizados porque es posible que la pila no esté en un estado reconocible para la recolección de elementos no utilizados. Si se intenta realizar una recolección de elementos no utilizados, el tiempo de ejecución se bloqueará hasta que se `FunctionTailcall2` devuelva.  
  
 Además, la `FunctionTailcall2` función no debe llamar a código administrado ni producir una asignación de memoria administrada.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Corprof. idl  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [FunctionEnter2 (Función)](functionenter2-function.md)
- [FunctionLeave2 (Función)](functionleave2-function.md)
- [Método SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [Funciones estáticas globales para generación de perfiles](profiling-global-static-functions.md)
