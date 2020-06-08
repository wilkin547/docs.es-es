---
title: FunctionEnter (Función)
ms.date: 03/30/2017
api_name:
- FunctionEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionEnter
helpviewer_keywords:
- FunctionEnter function [.NET Framework profiling]
ms.assetid: bf4ffa50-4506-4dd4-aa13-a0457b47ca74
topic_type:
- apiref
ms.openlocfilehash: 52870c7446987817ff00b90db26c3265bccdd096
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500733"
---
# <a name="functionenter-function"></a>FunctionEnter (Función)
Notifica al generador de perfiles que el control se pasa a una función.  
  
> [!NOTE]
> La `FunctionEnter` función está en desuso en la .NET Framework versión 2,0, y su uso implicará una penalización del rendimiento. En su lugar, use la función [FunctionEnter2](functionenter2-function.md) .  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
void __stdcall FunctionEnter (  
    [in]  FunctionID funcID  
);  
```  
  
## <a name="parameters"></a>Parámetros

- `funcID`

  \[in] el identificador de la función a la que se pasa el control.

## <a name="remarks"></a>Comentarios  
 La `FunctionEnter` función es una devolución de llamada; debe implementarla. La implementación debe usar el `__declspec` `naked` atributo de clase de almacenamiento ().  
  
 El motor de ejecución no guarda ningún registro antes de llamar a esta función.  
  
- En la entrada, debe guardar todos los registros que use, incluidos los de la unidad de punto flotante (FPU).  
  
- Al salir, debe restaurar la pila desactivando todos los parámetros insertados por el autor de la llamada.  
  
 La implementación de `FunctionEnter` no debe bloquearse porque retrasará la recolección de elementos no utilizados. La implementación no debe intentar una recolección de elementos no utilizados porque es posible que la pila no esté en un estado reconocible para la recolección de elementos no utilizados. Si se intenta realizar una recolección de elementos no utilizados, el tiempo de ejecución se bloqueará hasta que se `FunctionEnter` devuelva.  
  
 Además, la `FunctionEnter` función no debe llamar a código administrado ni producir una asignación de memoria administrada.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Corprof. idl  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** 1,1, 1,0  
  
## <a name="see-also"></a>Consulte también:

- [FunctionEnter2 (Función)](functionenter2-function.md)
- [FunctionLeave2 (Función)](functionleave2-function.md)
- [FunctionTailcall2 (Función)](functiontailcall2-function.md)
- [Método SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [Funciones estáticas globales para generación de perfiles](profiling-global-static-functions.md)
