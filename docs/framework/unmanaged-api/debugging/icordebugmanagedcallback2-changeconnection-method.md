---
title: ICorDebugManagedCallback2::ChangeConnection (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.ChangeConnection
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::ChangeConnection
helpviewer_keywords:
- ICorDebugManagedCallback2::ChangeConnection method [.NET Framework debugging]
- ChangeConnection method [.NET Framework debugging]
ms.assetid: 7263f9a9-4c0b-4d82-a181-288873fb2b18
topic_type:
- apiref
ms.openlocfilehash: 4558074bc23334bd697461a00ccb31db3e3fe397
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130600"
---
# <a name="icordebugmanagedcallback2changeconnection-method"></a>ICorDebugManagedCallback2::ChangeConnection (Método)
Notifica al depurador que ha cambiado el conjunto de tareas asociado a la conexión especificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ChangeConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pProcess`  
 de Un puntero a un objeto "ICorDebugProcess" que representa el proceso que contiene la conexión que cambió.  
  
 `dwConnectionId`  
 de IDENTIFICADOR de la conexión que cambió.  
  
## <a name="remarks"></a>Comentarios  
 Una devolución de llamada de `ChangeConnection` se desencadenará en cualquiera de los siguientes casos:  
  
- Cuando un depurador se asocia a un proceso que contiene conexiones. En este caso, el tiempo de ejecución generará y enviará un evento [ICorDebugManagedCallback2:: CreateConnection](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-createconnection-method.md) y un evento `ChangeConnection` para cada conexión del proceso. Se genera un evento `ChangeConnection` para cada conexión existente, independientemente de si el conjunto de tareas de la conexión se ha cambiado desde su creación.  
  
- Cuando un host llama a [ICLRDebugManager:: SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md) en la [API de hospedaje](../../../../docs/framework/unmanaged-api/hosting/index.md).  
  
 El depurador debe examinar todos los subprocesos del proceso para recopilar los cambios nuevos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugManagedCallback2 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [ICorDebugManagedCallback (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
