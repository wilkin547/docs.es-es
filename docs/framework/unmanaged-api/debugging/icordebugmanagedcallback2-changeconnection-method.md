---
description: 'Más información sobre: ICorDebugManagedCallback2:: ChangeConnection ((método)'
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
ms.openlocfilehash: 854ea7f40cad9bce613b4034afe7688f4aaf4e52
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790924"
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
  
## <a name="remarks"></a>Observaciones  

 Una `ChangeConnection` devolución de llamada se desencadenará en cualquiera de los siguientes casos:  
  
- Cuando un depurador se asocia a un proceso que contiene conexiones. En este caso, el tiempo de ejecución generará y enviará un evento [ICorDebugManagedCallback2:: CreateConnection](icordebugmanagedcallback2-createconnection-method.md) y un `ChangeConnection` evento para cada conexión del proceso. `ChangeConnection`Se genera un evento para cada conexión existente, independientemente de si el conjunto de tareas de la conexión se ha cambiado desde su creación.  
  
- Cuando un host llama a [ICLRDebugManager:: SetConnectionTasks](../hosting/iclrdebugmanager-setconnectiontasks-method.md) en la [API de hospedaje](../hosting/index.md).  
  
 El depurador debe examinar todos los subprocesos del proceso para recopilar los cambios nuevos.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugManagedCallback2 (Interfaz)](icordebugmanagedcallback2-interface.md)
- [ICorDebugManagedCallback (Interfaz)](icordebugmanagedcallback-interface.md)
