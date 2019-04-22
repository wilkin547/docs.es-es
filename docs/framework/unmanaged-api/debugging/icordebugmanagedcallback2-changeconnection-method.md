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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b4eeecc22db5786f66b3d484b521989e71817d8e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59185047"
---
# <a name="icordebugmanagedcallback2changeconnection-method"></a>ICorDebugManagedCallback2::ChangeConnection (Método)
Notifica al depurador que se ha cambiado el conjunto de tareas asociadas con la conexión especificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT ChangeConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pProcess`  
 [in] Un puntero a un objeto "ICorDebugProcess" que representa el proceso que contiene la conexión que ha cambiado.  
  
 `dwConnectionId`  
 [in] El identificador de la conexión que ha cambiado.  
  
## <a name="remarks"></a>Comentarios  
 Un `ChangeConnection` se desencadenará una devolución de llamada en cualquiera de los casos siguientes:  
  
-   Cuando se adjunta un depurador a un proceso que contiene las conexiones. En este caso, el tiempo de ejecución generará y enviar un [Icordebugmanagedcallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-createconnection-method.md) eventos y un `ChangeConnection` eventos para cada conexión en el proceso. Un `ChangeConnection` evento se genera para todas las conexiones existentes, independientemente de si el conjunto de la conexión de tareas ha cambiado desde su creación.  
  
-   Cuando llama un host [ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md) en el [API de hospedaje](../../../../docs/framework/unmanaged-api/hosting/index.md).  
  
 El depurador debe examinar todos los subprocesos del proceso para recoger los cambios nuevo.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugManagedCallback2 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [ICorDebugManagedCallback (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
