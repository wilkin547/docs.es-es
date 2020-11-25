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
ms.openlocfilehash: d725cbe89e0631630affb6b0540a7d5f57ab6b89
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720118"
---
# <a name="icordebugmanagedcallback2destroyconnection-method"></a>ICorDebugManagedCallback2::DestroyConnection (Método)

Notifica al depurador que se ha terminado la conexión especificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT DestroyConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pProcess`  
 de Un puntero a un objeto ICorDebugProcess que representa el proceso que contiene la conexión que se ha destruido.  
  
 `dwConnectionId`  
 de IDENTIFICADOR de la conexión que se ha destruido.  
  
## <a name="remarks"></a>Comentarios  

 Se `DestroyConnection` activará una devolución de llamada cuando un host llame a [ICLRDebugManager:: EndConnection](../hosting/iclrdebugmanager-endconnection-method.md) en la [API de hospedaje](../hosting/index.md).  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorDebugManagedCallback2 (Interfaz)](icordebugmanagedcallback2-interface.md)
- [ICorDebugManagedCallback (Interfaz)](icordebugmanagedcallback-interface.md)
