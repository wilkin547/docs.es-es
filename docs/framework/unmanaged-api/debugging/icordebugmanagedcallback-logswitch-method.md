---
title: "ICorDebugManagedCallback::LogSwitch (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.LogSwitch
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::LogSwitch
helpviewer_keywords:
- LogSwitch method [.NET Framework debugging]
- ICorDebugManagedCallback::LogSwitch method [.NET Framework debugging]
ms.assetid: 0ac59d27-783f-4a87-b7a8-baa3ccc54582
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9480b3123abceb6a108e2e00c7304829188cd162
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmanagedcallbacklogswitch-method"></a>ICorDebugManagedCallback::LogSwitch (Método)
Notifica al depurador que un subproceso de common language runtime (CLR) administrado ha llamado a un método el <xref:System.Diagnostics.Switch> clase para crear, modificar o eliminar un modificador de depuración o traza.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT LogSwitch (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] LONG                 lLevel,  
    [in] ULONG                ulReason,  
    [in] WCHAR               *pLogSwitchName,  
    [in] WCHAR               *pParentName);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `PAppDomain`  
 [in] Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene el subproceso administrado que ha creado, modificado o eliminado un conmutador de depuración/seguimiento.  
  
 `pThread`  
 [in] Un puntero a un objeto ICorDebugThread que representa el subproceso administrado.  
  
 `lLevel`  
 [in] Un valor que indica el nivel de gravedad del mensaje descriptivo que se escribió en el registro de eventos.  
  
 `ulReason`  
 [in] Un valor de la [LogSwitchCallReason](../../../../docs/framework/unmanaged-api/debugging/logswitchcallreason-enumeration.md) enumeración que indica que la operación se realiza en el conmutador de depuración/seguimiento.  
  
 `pLogSwitchName`  
 [in] Un puntero al nombre del conmutador de depuración/seguimiento.  
  
 `pParentName`  
 [in] Un puntero al nombre del elemento primario del modificador de depuración o traza.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorDebugManagedCallback (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
