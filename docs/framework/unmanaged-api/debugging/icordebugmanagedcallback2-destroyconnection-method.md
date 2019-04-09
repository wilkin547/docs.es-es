---
title: ICorDebugManagedCallback2::DestroyConnection (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.DestroyConnection
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::DestroyConnection
helpviewer_keywords:
- DestroyConnection method [.NET Framework debugging]
- ICorDebugManagedCallback2::DestroyConnection method [.NET Framework debugging]
ms.assetid: cf7940e9-4558-4319-925c-09f6c98c8fcd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 35ae3a9761798ed9ea42b984f2c6c2cad4e42777
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59075930"
---
# <a name="icordebugmanagedcallback2destroyconnection-method"></a>ICorDebugManagedCallback2::DestroyConnection (Método)
Notifica al depurador que ha finalizado la conexión especificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT DestroyConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pProcess`  
 [in] Un puntero a un objeto ICorDebugProcess que representa el proceso que contiene la conexión que se ha destruido.  
  
 `dwConnectionId`  
 [in] El identificador de la conexión que se ha destruido.  
  
## <a name="remarks"></a>Comentarios  
 Un `DestroyConnection` devolución de llamada se activará cuando llama un host [ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md) en el [API de hospedaje](../../../../docs/framework/unmanaged-api/hosting/index.md).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugManagedCallback2 (Interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [ICorDebugManagedCallback (Interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
