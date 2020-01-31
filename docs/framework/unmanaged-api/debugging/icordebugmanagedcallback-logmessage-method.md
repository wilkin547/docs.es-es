---
title: ICorDebugManagedCallback::LogMessage (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LogMessage
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LogMessage
helpviewer_keywords:
- ICorDebugManagedCallback::LogMessage method [.NET Framework debugging]
- LogMessage method [.NET Framework debugging]
ms.assetid: d218554a-bf42-4d88-833d-ede30de67a53
topic_type:
- apiref
ms.openlocfilehash: 4306c4ae44b0ae1ade2bf374981492fa1a4df76f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788366"
---
# <a name="icordebugmanagedcallbacklogmessage-method"></a>ICorDebugManagedCallback::LogMessage (Método)
Notifica al depurador que un subproceso administrado Common Language Runtime (CLR) ha llamado a un método en la clase <xref:System.Diagnostics.EventLog> para registrar un evento.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT LogMessage (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] LONG                 lLevel,  
    [in] WCHAR               *pLogSwitchName,  
    [in] WCHAR               *pMessage  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `pAppDomain`  
 de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene el subproceso administrado que registró el evento.  
  
 `pThread`  
 de Un puntero a un objeto ICorDebugThread que representa el subproceso administrado.  
  
 `lLevel`  
 de Un valor de la enumeración [LoggingLevelEnum (](logginglevelenum-enumeration.md) que indica el nivel de gravedad del mensaje descriptivo que se escribió en el registro de eventos.  
  
 `pLogSwitchName`  
 de Puntero al nombre del modificador de seguimiento.  
  
 `pMessage`  
 de Un puntero al mensaje que se escribió en el registro de eventos.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugManagedCallback (interfaz)](icordebugmanagedcallback-interface.md)
