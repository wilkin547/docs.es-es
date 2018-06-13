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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 83e32b2b69d53772f8a4ebaabe1c025b95d1da47
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33453732"
---
# <a name="icorprofilercallbackshutdown-method"></a>ICorProfilerCallback::Shutdown (Método)
Notifica al generador de perfiles que se está cerrando la aplicación.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT Shutdown();  
```  
  
## <a name="remarks"></a>Comentarios  
 El código del generador de perfiles con seguridad no puede llamar a métodos de la [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) interfaz después de la `Shutdown` se llama al método. Las llamadas a `ICorProfilerInfo` métodos como resultado un comportamiento indefinido después el `Shutdown` devuelve del método. Algunos eventos inmutables todavía pueden producirse después de cerrarse la aplicación; el generador de perfiles debe tener cuidado para devolver inmediatamente cuando esto ocurre.  
  
 El `Shutdown` se llamará al método únicamente si ha iniciado la aplicación administrada que se está perfilando como código administrado (es decir, se administra el marco inicial en la pila de proceso). Si la aplicación se inicia como código no administrado pero posteriormente pasa a código administrado, con lo que se crea una instancia de common language runtime (CLR), a continuación, `Shutdown` no se llamará. Para estos casos, el generador de perfiles debe incluir en su biblioteca un `DllMain` rutina que use el DLL_PROCESS_DETACH valor que se debe liberar todos los recursos y realizar el procesamiento de limpieza de los datos, como el vaciado de seguimientos en el disco y así sucesivamente.  
  
 En general, el generador de perfiles debe sobrellevar apagados inesperados. Por ejemplo, podría detener un proceso de Win32 `TerminateProcess` método (declarado en Winbase.h). En otros casos, CLR detendrá determinados subprocesos administrados (subprocesos en segundo plano) sin entregar los mensajes de destrucción ordenada para ellos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorProfilerCallback (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [Initialize (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)
