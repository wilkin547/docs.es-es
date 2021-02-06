---
description: 'Más información acerca de: ICorProfilerCallback:: Shutdown (método)'
title: ICorProfilerCallback::Shutdown (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.Shutdown
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::Shutdown
helpviewer_keywords:
- ICorProfilerCallback::Shutdown method [.NET Framework profiling]
- Shutdown method [.NET Framework profiling]
ms.assetid: 1ea194f0-a331-4855-a2ce-37393b8e5f84
topic_type:
- apiref
ms.openlocfilehash: 7afc274579f248ee190e379160f2709b5cb9881a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99657325"
---
# <a name="icorprofilercallbackshutdown-method"></a>ICorProfilerCallback::Shutdown (Método)

Notifica al generador de perfiles que la aplicación se está cerrando.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT Shutdown();  
```  
  
## <a name="remarks"></a>Observaciones  

 El código del generador de perfiles no puede llamar de forma segura a los métodos de la interfaz [ICorProfilerInfo](icorprofilerinfo-interface.md) después de `Shutdown` llamar al método. Cualquier llamada a `ICorProfilerInfo` métodos produce un comportamiento indefinido después de que el `Shutdown` método devuelva un resultado. Es posible que se sigan produciendo ciertos eventos inmutables después del apagado; el generador de perfiles debe tener cuidado de volver inmediatamente cuando esto suceda.  
  
 `Shutdown`Solo se llamará al método si la aplicación administrada en la que se va a crear el perfiles se inicia como código administrado (es decir, el marco inicial en la pila de procesos está administrado). Si la aplicación se inició como código no administrado, pero posteriormente se saltó a código administrado, con lo que se crea una instancia del Common Language Runtime (CLR), entonces `Shutdown` no se llamará a. En estos casos, el generador de perfiles debe incluir en su biblioteca una `DllMain` rutina que use el valor DLL_PROCESS_DETACH para liberar los recursos y realizar el procesamiento de limpieza de sus datos, como el vaciado de seguimientos en el disco, etc.  
  
 En general, el generador de perfiles debe hacer frente a apagados inesperados. Por ejemplo, un proceso podría detenerse mediante el `TerminateProcess` método Win32 (declarado en Winbase. h). En otros casos, CLR detendrá determinados subprocesos administrados (subprocesos en segundo plano) sin proporcionar mensajes de destrucción ordenada para ellos.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerCallback (Interfaz)](icorprofilercallback-interface.md)
- [Método Initialize](icorprofilercallback-initialize-method.md)
