---
title: ICorProfilerCallback::ExceptionUnwindFunctionLeave (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionUnwindFunctionLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionUnwindFunctionLeave
helpviewer_keywords:
- ICorProfilerCallback::ExceptionUnwindFunctionLeave method [.NET Framework profiling]
- ExceptionUnwindFunctionLeave method [.NET Framework profiling]
ms.assetid: ebaad1d5-ee0a-4cb0-96bc-8ba5d371b747
topic_type:
- apiref
ms.openlocfilehash: 9f88a3fde7d7cb5941e3a7f44a7d94056a959ab8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733924"
---
# <a name="icorprofilercallbackexceptionunwindfunctionleave-method"></a>ICorProfilerCallback::ExceptionUnwindFunctionLeave (Método)

Notifica al generador de perfiles que la fase de desenredado del control de excepciones ha terminado de desenredar una función.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ExceptionUnwindFunctionLeave();  
```  
  
## <a name="remarks"></a>Comentarios  

 Cuando `ExceptionUnwindFunctionLeave` se llama al método, la instancia de la función y sus datos de pila se quitan de la pila.  
  
 El generador de perfiles no debe bloquearse durante esta llamada porque es posible que la pila no esté en un estado que permita la recolección de elementos no utilizados y, por tanto, no se puede habilitar la recolección de elementos no utilizados preferente. Si el generador de perfiles se bloquea aquí y se intenta realizar una recolección de elementos no utilizados, el tiempo de ejecución se bloqueará hasta que esta devolución de llamada vuelva.  
  
 Además, durante esta llamada, el generador de perfiles no debe llamar a código administrado ni provocar una asignación de memoria administrada.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorProfilerCallback (Interfaz)](icorprofilercallback-interface.md)
- [Método ExceptionUnwindFunctionEnter](icorprofilercallback-exceptionunwindfunctionenter-method.md)
