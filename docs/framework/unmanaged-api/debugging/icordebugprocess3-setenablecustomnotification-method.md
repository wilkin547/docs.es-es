---
title: "ICorDebugProcess3::SetEnableCustomNotification (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess3.SetEnableCustomNotification Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess3::SetEnableCustomNotification
helpviewer_keywords:
- ICorDebugProcess3::SetEnableCustomNotification method [.NET Framework debugging]
- SetEnableCustomNotification method [.NET Framework debugging]
ms.assetid: afd88ee9-2589-4461-a75a-9b6fe55a2525
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6d4c6604d57b28cca33007b9d72d4b4c06e6d062
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess3setenablecustomnotification-method"></a>ICorDebugProcess3::SetEnableCustomNotification (Método)
Habilita y deshabilita notificaciones del depurador personalizadas del tipo especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT SetEnableCustomNotification(ICorDebugClass * pClass,  
                                    BOOL fEnable);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pClass`  
 [in] El tipo que especifica las notificaciones del depurador personalizadas.  
  
 `fEnable`  
 [in] `true` para habilitar las notificaciones del depurador personalizadas; `false` para deshabilitar las notificaciones. El valor predeterminado es `false`.  
  
## <a name="remarks"></a>Comentarios  
 Cuando `fEnable` está establecido en `true`, llama a la <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> desencadenador método un [ICorDebugManagedCallback3:: CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) devolución de llamada. Las notificaciones están deshabilitadas de forma predeterminada; por lo tanto, el depurador debe especificar cualquier tipo de notificación que conozca y desea controlar. Dado que la [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) clase tiene un ámbito de dominio de aplicación, el depurador debe llamar a `SetEnableCustomNotification` para cada dominio de aplicación en el proceso si desea recibir la notificación en todo el proceso.  
  
 A partir de la [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], el solo notificación compatible es una notificación de dependencia entre subprocesos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorDebugProcess3 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md)  
 [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
