---
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
ms.openlocfilehash: 63e41df8af85d94df068526ef69708687b341e78
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446947"
---
# <a name="icorprofilercallbackshutdown-method"></a>ICorProfilerCallback::Shutdown (Método)
Notifica al generador de perfiles que la aplicación se está cerrando.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT Shutdown();  
```  
  
## <a name="remarks"></a>Comentarios  
 El código del generador de perfiles no puede llamar a los métodos de la interfaz [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) de forma segura después de llamar al método `Shutdown`. Cualquier llamada a métodos `ICorProfilerInfo` produce un comportamiento indefinido después de que el método `Shutdown` devuelva. Es posible que se sigan produciendo ciertos eventos inmutables después del apagado; el generador de perfiles debe tener cuidado de volver inmediatamente cuando esto suceda.  
  
 Solo se llamará al método `Shutdown` si la aplicación administrada en la que se va a crear el perfiles se inicia como código administrado (es decir, el marco inicial en la pila de procesos se administra). Si la aplicación se inició como código no administrado, pero posteriormente salta a código administrado, con lo que se crea una instancia del Common Language Runtime (CLR), no se llamará a `Shutdown`. En estos casos, el generador de perfiles debe incluir en su biblioteca una rutina `DllMain` que use el valor DLL_PROCESS_DETACH para liberar los recursos y realizar el procesamiento de la limpieza de sus datos, como el vaciado de seguimientos en el disco, etc.  
  
 En general, el generador de perfiles debe hacer frente a apagados inesperados. Por ejemplo, un proceso podría detenerse mediante Win32 `TerminateProcess` método (declarado en Winbase. h). En otros casos, CLR detendrá determinados subprocesos administrados (subprocesos en segundo plano) sin proporcionar mensajes de destrucción ordenada para ellos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerCallback (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [Initialize (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)
