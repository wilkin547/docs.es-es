---
title: ICorProfilerCallback::ExceptionCatcherEnter (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionCatcherEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionCatcherEnter
helpviewer_keywords:
- ICorProfilerCallback::ExceptionCatcherEnter method [.NET Framework profiling]
- ExceptionCatcherEnter method [.NET Framework profiling]
ms.assetid: 41462329-a648-46f0-ae6d-728b94c31aa9
topic_type:
- apiref
ms.openlocfilehash: 534e0672820cc2509f32765274ad970fda69ec5d
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866512"
---
# <a name="icorprofilercallbackexceptioncatcherenter-method"></a>ICorProfilerCallback::ExceptionCatcherEnter (Método)
Notifica al generador de perfiles que el control se pasa al bloque `catch` adecuado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ExceptionCatcherEnter(  
    [in] FunctionID functionId,  
    [in] ObjectID   objectId);  
```  
  
## <a name="parameters"></a>Parameters

- `functionId`

  \[en] el identificador de la función que contiene el bloque de `catch`.
  
- `objectId`

  \[en] el identificador de la excepción que se está controlando.

## <a name="remarks"></a>Notas  
 Solo se llama al método `ExceptionCatcherEnter` si el punto de captura está en código compilado con el compilador Just-in-Time (JIT). Una excepción que se detecta en el código no administrado o en el código interno del tiempo de ejecución no llamará a esta notificación. El valor `objectId` se pasa de nuevo porque una recolección de elementos no utilizados podría haber trasladado el objeto desde la notificación de `ExceptionThrown`.  
  
 El generador de perfiles no debe bloquear en su implementación de este método porque la pila puede no estar en un estado que permita la recolección de elementos no utilizados y, por tanto, no se puede habilitar la recolección de elementos no utilizados preferente. Si el generador de perfiles se bloquea aquí y se intenta la recolección de elementos no utilizados, el tiempo de ejecución se bloqueará hasta que esta devolución de llamada vuelva.  
  
 La implementación del generador de perfiles de este método no debe llamar a código administrado ni provocar una asignación de memoria administrada.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerCallback (interfaz)](icorprofilercallback-interface.md)
- [ExceptionCatcherLeave (método)](icorprofilercallback-exceptioncatcherleave-method.md)
