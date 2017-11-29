---
title: "ICorProfilerCallback::RemotingServerReceivingMessage (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RemotingServerReceivingMessage
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RemotingServerReceivingMessage
helpviewer_keywords:
- ICorProfilerCallback::RemotingServerReceivingMessage method [.NET Framework profiling]
- RemotingServerReceivingMessage method [.NET Framework profiling]
ms.assetid: 5604d21f-e6b7-490e-b469-42122a7568e1
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5947541204edf7fd4359dfa3aca78ea62c8009c6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackremotingserverreceivingmessage-method"></a>ICorProfilerCallback::RemotingServerReceivingMessage (Método)
Notifica al generador de perfiles que el proceso ha recibido una solicitud de activación o la invocación de método remoto.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pCookie`  
 [in] Un valor que se corresponderá con el valor proporcionado en [ICorProfilerCallback:: RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md) en estas condiciones:  
  
-   Las cookies GUID de comunicación remota están activas.  
  
-   El canal consigue transmitir el mensaje.  
  
-   Las cookies de GUID están activas en el proceso de cliente.  
  
 Esto permite la fácil emparejamiento de las llamadas remotas y la creación de una pila de llamadas lógica.  
  
 `fIsAsync`  
 [in] Un valor que es `true` si la llamada es asincrónica; en caso contrario, `false`.  
  
## <a name="remarks"></a>Comentarios  
 Si la solicitud de mensaje es asincrónica, la solicitud puede ser atendida por cualquier subproceso arbitrario.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorProfilerCallback (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
