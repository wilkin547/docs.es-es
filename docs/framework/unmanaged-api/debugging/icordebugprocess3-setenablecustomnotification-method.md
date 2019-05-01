---
title: ICorDebugProcess3::SetEnableCustomNotification (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess3.SetEnableCustomNotification Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess3::SetEnableCustomNotification
helpviewer_keywords:
- ICorDebugProcess3::SetEnableCustomNotification method [.NET Framework debugging]
- SetEnableCustomNotification method [.NET Framework debugging]
ms.assetid: afd88ee9-2589-4461-a75a-9b6fe55a2525
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e8c8725bf21aefa3abf5fc41366d8f983bd686b2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994362"
---
# <a name="icordebugprocess3setenablecustomnotification-method"></a>ICorDebugProcess3::SetEnableCustomNotification (Método)
Habilita y deshabilita las notificaciones del depurador personalizados del tipo especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT SetEnableCustomNotification(ICorDebugClass * pClass,  
                                    BOOL fEnable);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pClass`  
 [in] El tipo que especifica las notificaciones del depurador personalizados.  
  
 `fEnable`  
 [in] `true` para habilitar las notificaciones del depurador personalizados; `false` para deshabilitar las notificaciones. El valor predeterminado es `false`.  
  
## <a name="remarks"></a>Comentarios  
 Cuando `fEnable` está establecido en `true`, las llamadas a la <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> desencadenador método un [ICorDebugManagedCallback3:: CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) devolución de llamada. Las notificaciones están deshabilitadas de forma predeterminada; por lo tanto, el depurador debe especificar cualquier tipo de notificación que conozca y desea controlar. Dado que el [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) ámbito de clase por dominio de aplicación, el depurador debe llamar a `SetEnableCustomNotification` para cada dominio de aplicación en el proceso si desea recibir la notificación en todo el proceso.  
  
 A partir de la [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], el solo notificación compatible es una notificación de dependencia entre subprocesos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugProcess3 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
