---
title: ICorProfilerCallback::RemotingClientInvocationFinished (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingClientInvocationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingClientInvocationFinished
helpviewer_keywords:
- RemotingClientInvocationFinished method [.NET Framework profiling]
- ICorProfilerCallback::RemotingClientInvocationFinished method [.NET Framework profiling]
ms.assetid: ea4b283b-1210-4f41-a7a2-c398b1adde4e
topic_type:
- apiref
ms.openlocfilehash: c9a750b941b29047206c98410d4b4673d1101a01
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445838"
---
# <a name="icorprofilercallbackremotingclientinvocationfinished-method"></a>ICorProfilerCallback::RemotingClientInvocationFinished (Método)
Notifica al generador de perfiles que se ha ejecutado una llamada de comunicación remota para completarse en el cliente.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT RemotingClientInvocationFinished();  
```  
  
## <a name="remarks"></a>Comentarios  
 Si la llamada de comunicación remota fue sincrónica, también se ha ejecutado hasta completarse en el servidor. Si la llamada de comunicación remota es asincrónica, se podría esperar una respuesta cuando se controla la llamada. Si se espera una respuesta, se producirá como una llamada a [ICorProfilerCallback:: remotingclientreceivingreply (](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) y una llamada adicional a `RemotingClientInvocationFinished` para indicar el procesamiento secundario necesario de una llamada asincrónica.  
  
 Cada uno de los siguientes pares de devoluciones de llamada se producirá en el mismo subproceso:  
  
- `RemotingClientInvocationStarted` e [ICorProfilerCallback:: remotingclientsendingmessage (](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)  
  
- [ICorProfilerCallback:: remotingclientreceivingreply (](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) e [ICorProfilerCallback:: remotingclientinvocationfinished (](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)  
  
- [ICorProfilerCallback:: RemotingServerInvocationReturned (](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) e [ICorProfilerCallback:: RemotingServerSendingReply (](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)  
  
 Debe tener en cuenta los siguientes problemas con las devoluciones de llamada de comunicación remota:  
  
- La ejecución de una función de comunicación remota no se refleja en la API del generador de perfiles, por lo que las notificaciones para las funciones a las que se llama desde el cliente y que se ejecutan en el servidor no se reciben correctamente. La invocación real se produce a través de un objeto proxy. en el generador de perfiles, parece que ciertas funciones se compilan JIT pero nunca se usan.  
  
- El generador de perfiles no recibe notificaciones precisas para eventos de comunicación remota asincrónica.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerCallback (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
