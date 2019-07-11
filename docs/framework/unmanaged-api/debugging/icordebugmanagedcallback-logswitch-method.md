---
title: ICorDebugManagedCallback::LogSwitch (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LogSwitch
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LogSwitch
helpviewer_keywords:
- LogSwitch method [.NET Framework debugging]
- ICorDebugManagedCallback::LogSwitch method [.NET Framework debugging]
ms.assetid: 0ac59d27-783f-4a87-b7a8-baa3ccc54582
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9d7432771a7d8eee9cea10f883dd3bd91f5ffb74
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67761390"
---
# <a name="icordebugmanagedcallbacklogswitch-method"></a>ICorDebugManagedCallback::LogSwitch (Método)
Notifica al depurador que un subproceso de common language runtime (CLR) administrado ha llamado a un método el <xref:System.Diagnostics.Switch> clase para crear, modificar o eliminar un conmutador de depuración y seguimiento.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT LogSwitch (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] LONG                 lLevel,  
    [in] ULONG                ulReason,  
    [in] WCHAR               *pLogSwitchName,  
    [in] WCHAR               *pParentName);  
```  
  
## <a name="parameters"></a>Parámetros  
 `PAppDomain`  
 [in] Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene el subproceso administrado que crea, modifica o elimina un conmutador de depuración y seguimiento.  
  
 `pThread`  
 [in] Un puntero a un objeto ICorDebugThread que representa el subproceso administrado.  
  
 `lLevel`  
 [in] Un valor que indica el nivel de gravedad del mensaje descriptivo que se escribió en el registro de eventos.  
  
 `ulReason`  
 [in] Un valor de la [LogSwitchCallReason](../../../../docs/framework/unmanaged-api/debugging/logswitchcallreason-enumeration.md) enumeración que indica la operación se realiza en el conmutador de depuración y seguimiento.  
  
 `pLogSwitchName`  
 [in] Un puntero al nombre del conmutador de depuración y seguimiento.  
  
 `pParentName`  
 [in] Un puntero al nombre del elemento primario del conmutador de depuración y seguimiento.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugManagedCallback (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
