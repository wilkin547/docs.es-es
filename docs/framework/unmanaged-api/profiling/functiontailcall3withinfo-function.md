---
description: 'Más información acerca de: FunctionTailcall3WithInfo (función)'
title: FunctionTailcall3WithInfo (Función)
ms.date: 03/30/2017
api_name:
- FunctionTailcall3WithInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionTailcall3WithInfo
helpviewer_keywords:
- FunctionTailcall3WithInfo function [.NET Framework profiling]
ms.assetid: 46380fcc-0198-43ae-a1f5-2d4939425886
topic_type:
- apiref
ms.openlocfilehash: d84cac19acb8a1d696030fe372d29c655c5f97a6
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2021
ms.locfileid: "104760800"
---
# <a name="functiontailcall3withinfo-function"></a>FunctionTailcall3WithInfo (Función)

Notifica al generador de perfiles que la función que se está ejecutando actualmente está a punto de realizar una llamada de cola a otra función y proporciona un identificador que se puede pasar al [método ICorProfilerInfo3:: GetFunctionTailcall3Info (](icorprofilerinfo3-getfunctiontailcall3info-method.md) para recuperar el marco de pila.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
void __stdcall FunctionTailcall3WithInfo(  
               [in] FunctionIDOrClientID functionIDOrClientID,  
               [in] COR_PRF_ELT_INFO eltInfo);  
```  
  
## <a name="parameters"></a>Parámetros  

`functionIDOrClientID` de Identificador de la función que se ejecuta actualmente y que está a punto de realizar una llamada de cola.

`eltInfo` de Un identificador opaco que representa información sobre un marco de pila determinado. Este identificador es válido solo durante la devolución de llamada a la que se pasa.

## <a name="remarks"></a>Observaciones  

 El `FunctionTailcall3WithInfo` método de devolución de llamada notifica al generador de perfiles cuando se llama a las funciones y permite que el generador de perfiles use el [método ICorProfilerInfo3:: GetFunctionTailcall3Info (](icorprofilerinfo3-getfunctiontailcall3info-method.md) para inspeccionar el marco de pila. Para obtener acceso a la información del marco de pila, se debe `COR_PRF_ENABLE_FRAME_INFO` establecer la marca. El generador de perfiles puede utilizar el [método ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) para establecer las marcas de evento y, a continuación, usar el [método ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3WithInfo (](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) para registrar la implementación de esta función.  
  
 La `FunctionTailcall3WithInfo` función es una devolución de llamada; debe implementarla. La implementación debe usar el `__declspec(naked)` atributo de clase de almacenamiento.  
  
 El motor de ejecución no guarda ningún registro antes de llamar a esta función.  
  
- En la entrada, debe guardar todos los registros que use, incluidos los de la unidad de punto flotante (FPU).  
  
- Al salir, debe restaurar la pila desactivando todos los parámetros insertados por el autor de la llamada.  
  
 La implementación de `FunctionTailcall3WithInfo` no debe bloquearse porque retrasará la recolección de elementos no utilizados. La implementación no debe intentar una recolección de elementos no utilizados, porque es posible que la pila no esté en un estado reconocible para la recolección de elementos no utilizados. Si se intenta realizar una recolección de elementos no utilizados, el tiempo de ejecución se bloqueará hasta que se `FunctionTailcall3WithInfo` devuelva.  
  
 Además, la función FunctionTailcall3WithInfo no debe llamar a código administrado ni producir una asignación de memoria administrada de ninguna manera.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Corprof. idl  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [FunctionEnter3](functionenter3-function.md)
- [FunctionLeave3](functionleave3-function.md)
- [FunctionTailcall3](functiontailcall3-function.md)
- [FunctionEnter3WithInfo](functiontailcall3-function.md)
- [FunctionLeave3WithInfo](functionleave3withinfo-function.md)
- [Setenterleavefunctionhooks3 (](icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [Setenterleavefunctionhooks3withinfo (](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [Setfunctionidmapper (](icorprofilerinfo-setfunctionidmapper-method.md)
- [Setfunctionidmapper2 (](icorprofilerinfo3-setfunctionidmapper2-method.md)
- [Funciones estáticas globales para generación de perfiles](profiling-global-static-functions.md)
