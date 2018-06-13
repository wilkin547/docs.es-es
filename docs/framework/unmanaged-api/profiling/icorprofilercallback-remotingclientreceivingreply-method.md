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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 04956fb5519c66141f4bd7330367f6c78b4e7bc4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33453963"
---
# <a name="icorprofilercallbackremotingclientreceivingreply-method"></a>ICorProfilerCallback::RemotingClientReceivingReply (Método)
Notifica al generador de perfiles que se ha completado la parte de servidor de una llamada de comunicación remota y el cliente ahora está recibiendo y va a procesar la respuesta.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT RemotingClientReceivingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);   
```  
  
#### <a name="parameters"></a>Parámetros  
 `pCookie`  
 [in] Un valor que se corresponderá con el valor proporcionado en [ICorProfilerCallback:: RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md) en estas condiciones:  
  
-   Las cookies GUID de comunicación remota están activas.  
  
-   El canal consigue transmitir el mensaje.  
  
-   Las cookies de GUID están activas en el proceso de servidor.  
  
 Esto permite la fácil emparejamiento de las llamadas remotas.  
  
 `fIsAsync`  
 [in] Un valor que es `true` si la llamada es asincrónica; en caso contrario, `false`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorProfilerCallback (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
