---
title: FunctionTailcall (Función)
ms.date: 03/30/2017
api_name:
- FunctionTailcall
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionTailcall
helpviewer_keywords:
- FunctionTailcall function [.NET Framework profiling]
ms.assetid: 66347e03-9a97-41e8-8f9d-89b80803f7b5
topic_type:
- apiref
ms.openlocfilehash: 42ea497bdcab71518bec08514b827d76f0317d57
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500603"
---
# <a name="functiontailcall-function"></a>FunctionTailcall (Función)
Notifica al generador de perfiles que la función que se está ejecutando actualmente está a punto de realizar una llamada de cola a otra función.  
  
> [!NOTE]
> La `FunctionTailcall` función está en desuso en la .NET Framework versión 2,0. Continuará funcionando, pero se producirá una reducción del rendimiento. En su lugar, use la función [FunctionTailcall2](functiontailcall2-function.md) .  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
void __stdcall FunctionTailcall (  
    [in] FunctionID funcID  
);  
```  
  
## <a name="parameters"></a>Parámetros

- `funcID`

  \[in] el identificador de la función que se ejecuta actualmente y que está a punto de realizar una llamada de cola.

## <a name="remarks"></a>Comentarios  
 La función de destino de la llamada de cola usará el marco de pila actual y devolverá directamente al llamador de la función que realizó la llamada de cola. Esto significa que no se emitirá una devolución de llamada de [FunctionLeave (](functionleave-function.md) para una función que sea el destino de una llamada de cola.  
  
 La `FunctionTailcall` función es una devolución de llamada; debe implementarla. La implementación debe usar el `__declspec` `naked` atributo de clase de almacenamiento ().  
  
 El motor de ejecución no guarda ningún registro antes de llamar a esta función.  
  
- En la entrada, debe guardar todos los registros que use, incluidos los de la unidad de punto flotante (FPU).  
  
- Al salir, debe restaurar la pila desactivando todos los parámetros insertados por el autor de la llamada.  
  
 La implementación de `FunctionTailcall` no debe bloquearse porque retrasará la recolección de elementos no utilizados. La implementación no debe intentar una recolección de elementos no utilizados porque es posible que la pila no esté en un estado reconocible para la recolección de elementos no utilizados. Si se intenta realizar una recolección de elementos no utilizados, el tiempo de ejecución se bloqueará hasta que se `FunctionTailcall` devuelva.  
  
 Además, la `FunctionTailcall` función no debe llamar a código administrado ni producir una asignación de memoria administrada.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Corprof. idl  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** 1,1, 1,0  
  
## <a name="see-also"></a>Consulte también:

- [FunctionEnter2 (Función)](functionenter2-function.md)
- [FunctionLeave2 (Función)](functionleave2-function.md)
- [Método SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [Funciones estáticas globales para generación de perfiles](profiling-global-static-functions.md)
