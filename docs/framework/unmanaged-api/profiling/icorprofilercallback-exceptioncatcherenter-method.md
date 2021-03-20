---
description: 'Más información sobre: ICorProfilerCallback:: Exceptioncatcherenter ((método)'
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
ms.openlocfilehash: f9ea2b44e7a783f9b21f4aa385585dfebc48b1d4
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2021
ms.locfileid: "104760527"
---
# <a name="icorprofilercallbackexceptioncatcherenter-method"></a>ICorProfilerCallback::ExceptionCatcherEnter (Método)

Notifica al generador de perfiles que el control se está pasando al `catch` bloque adecuado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ExceptionCatcherEnter(  
    [in] FunctionID functionId,  
    [in] ObjectID   objectId);  
```  
  
## <a name="parameters"></a>Parámetros

`functionId` de Identificador de la función que contiene el `catch` bloque.
  
`objectId` de Identificador de la excepción que se está controlando.

## <a name="remarks"></a>Observaciones  

 `ExceptionCatcherEnter`Solo se llama al método si el punto de captura está en código compilado con el compilador Just-in-Time (JIT). Una excepción que se detecta en el código no administrado o en el código interno del tiempo de ejecución no llamará a esta notificación. El `objectId` valor se pasa de nuevo porque una recolección de elementos no utilizados podría haber trasladado el objeto desde la `ExceptionThrown` notificación.  
  
 El generador de perfiles no debe bloquear en su implementación de este método porque la pila puede no estar en un estado que permita la recolección de elementos no utilizados y, por tanto, no se puede habilitar la recolección de elementos no utilizados preferente. Si el generador de perfiles se bloquea aquí y se intenta la recolección de elementos no utilizados, el tiempo de ejecución se bloqueará hasta que esta devolución de llamada vuelva.  
  
 La implementación del generador de perfiles de este método no debe llamar a código administrado ni provocar una asignación de memoria administrada.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorProfilerCallback (Interfaz)](icorprofilercallback-interface.md)
- [Método ExceptionCatcherLeave](icorprofilercallback-exceptioncatcherleave-method.md)
