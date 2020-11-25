---
title: ICorProfilerCallback::ExceptionUnwindFinallyLeave (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionUnwindFinallyLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionUnwindFinallyLeave
helpviewer_keywords:
- ICorProfilerCallback::ExceptionUnwindFinallyLeave method [.NET Framework profiling]
- ExceptionUnwindFinallyLeave method [.NET Framework profiling]
ms.assetid: 2350351e-f253-4c0c-a191-f952bc5700e6
topic_type:
- apiref
ms.openlocfilehash: e02716350aa2bf32bdd7c4b2e01841405de6dc14
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720404"
---
# <a name="icorprofilercallbackexceptionunwindfinallyleave-method"></a>ICorProfilerCallback::ExceptionUnwindFinallyLeave (Método)

Notifica al generador de perfiles que la fase de desenredado del control de excepciones ha dejado una `finally` cláusula.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ExceptionUnwindFinallyLeave();  
```  
  
## <a name="remarks"></a>Comentarios  

 El generador de perfiles no debe bloquearse durante esta llamada porque es posible que la pila no esté en un estado que permita la recolección de elementos no utilizados y, por tanto, no se puede habilitar la recolección de elementos no utilizados preferente. Si el generador de perfiles se bloquea aquí y se intenta realizar una recolección de elementos no utilizados, el tiempo de ejecución se bloqueará hasta que esta devolución de llamada vuelva.  
  
 Además, durante esta llamada, el generador de perfiles no debe llamar a código administrado ni provocar una asignación de memoria administrada.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorProfilerCallback (Interfaz)](icorprofilercallback-interface.md)
- [Método ExceptionUnwindFinallyEnter](icorprofilercallback-exceptionunwindfinallyenter-method.md)
