---
title: "ICorDebugManagedCallback::DebuggerError (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.DebuggerError
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::DebuggerError
helpviewer_keywords:
- DebuggerError method [.NET Framework debugging]
- ICorDebugManagedCallback::DebuggerError method [.NET Framework debugging]
ms.assetid: 9e983d11-eaf3-4741-b936-29ec456384a3
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cc92bc6a1718d9d3505443e5b13786d1a359481f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbackdebuggererror-method"></a>ICorDebugManagedCallback::DebuggerError (Método)
Notifica al depurador que se ha producido un error al intentar controlar un evento de common language runtime (CLR).  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT DebuggerError (  
    [in] ICorDebugProcess *pProcess,  
    [in] HRESULT           errorHR,  
    [in] DWORD             errorCode  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pProcess`  
 [in] Un puntero a un objeto de "ICorDebugProcess" que representa el proceso en el que se produjo el evento.  
  
 `errorHR`  
 [in] El valor HRESULT que se devolvió desde el controlador de eventos.  
  
 `errorCode`  
 [in] Un entero que especifica el error CLR.  
  
## <a name="remarks"></a>Comentarios  
 El proceso se puede colocar en el modo de acceso directo, dependiendo de la naturaleza del error.  
  
 El `DebugError` devolución de llamada indica que los servicios de depuración se han deshabilitado debido a un error, por lo que los depuradores deben hacer que el mensaje de error disponible para el usuario. [ICorDebugProcess:: GetId](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md) sea segura para la llamada, pero todos los demás métodos, incluidos los [ICorDebug:: Terminate](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md), no debe llamarse. El depurador debe utilizar funciones del sistema operativo para finalizar los procesos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorDebugManagedCallback (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
