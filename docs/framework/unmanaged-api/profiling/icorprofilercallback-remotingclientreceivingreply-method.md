---
title: ICorProfilerCallback::RemotingClientReceivingReply (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingClientReceivingReply
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingClientReceivingReply
helpviewer_keywords:
- ICorProfilerCallback::RemotingClientReceivingReply method [.NET Framework profiling]
- RemotingClientReceivingReply method [.NET Framework profiling]
ms.assetid: 15cfc300-8231-4ecb-9a04-19851c3eb484
topic_type:
- apiref
ms.openlocfilehash: 62973a36e899b1a8c618888e5245bfc00d8ad777
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866077"
---
# <a name="icorprofilercallbackremotingclientreceivingreply-method"></a>ICorProfilerCallback::RemotingClientReceivingReply (Método)
Notifica al generador de perfiles que se ha completado la parte del servidor de una llamada de comunicación remota y que el cliente está recibiendo y procesando la respuesta.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT RemotingClientReceivingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);   
```  
  
## <a name="parameters"></a>Parameters  
 `pCookie`  
 de Un valor que se corresponderá con el valor proporcionado en [ICorProfilerCallback:: RemotingServerSendingReply (](icorprofilercallback-remotingserversendingreply-method.md) en estas condiciones:  
  
- Las cookies del GUID de comunicación remota están activas.  
  
- El canal realiza correctamente la transmisión del mensaje.  
  
- Las cookies de GUID están activas en el proceso del servidor.  
  
 Esto permite un fácil emparejamiento de llamadas remotas.  
  
 `fIsAsync`  
 de Valor que se `true` si la llamada es asincrónica; de lo contrario, `false`.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerCallback (interfaz)](icorprofilercallback-interface.md)
