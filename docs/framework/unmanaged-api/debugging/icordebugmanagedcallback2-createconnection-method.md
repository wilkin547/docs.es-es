---
title: ICorDebugManagedCallback2::CreateConnection (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.CreateConnection
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::CreateConnection
helpviewer_keywords:
- CreateConnection method [.NET Framework debugging]
- ICorDebugManagedCallback2::CreateConnection method [.NET Framework debugging]
ms.assetid: 49e647be-9d63-4250-9d11-704e2a400d1b
topic_type:
- apiref
ms.openlocfilehash: 5a4ebf65dfaaa487e87f3fd78e54c468c7e24a89
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697251"
---
# <a name="icordebugmanagedcallback2createconnection-method"></a>ICorDebugManagedCallback2::CreateConnection (Método)

Notifica al depurador que se ha creado una nueva conexión.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CreateConnection (  
    [in] ICorDebugProcess     *pProcess,  
    [in] CONNID               dwConnectionId,  
    [in] WCHAR                *pConnName  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pProcess`  
 de Un puntero a un objeto "ICorDebugProcess" que representa el proceso en el que se creó la conexión.  
  
 `dwConnectionId`  
 de IDENTIFICADOR de la nueva conexión.  
  
 `pConnName`  
 de Puntero al nombre de la nueva conexión.  
  
## <a name="remarks"></a>Comentarios  

 Una `CreateConnection` devolución de llamada se desencadenará en cualquiera de los siguientes casos:  
  
- Cuando un depurador se asocia a un proceso que contiene conexiones. En este caso, el tiempo de ejecución generará y enviará un `CreateConnection` evento y un evento [ICorDebugManagedCallback2:: ChangeConnection (](icordebugmanagedcallback2-changeconnection-method.md) para cada conexión del proceso.  
  
- Cuando un host llama a [ICLRDebugManager:: BeginConnection](../hosting/iclrdebugmanager-beginconnection-method.md) en la [API de hospedaje](../hosting/index.md).  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorDebugManagedCallback2 (Interfaz)](icordebugmanagedcallback2-interface.md)
- [ICorDebugManagedCallback (Interfaz)](icordebugmanagedcallback-interface.md)
