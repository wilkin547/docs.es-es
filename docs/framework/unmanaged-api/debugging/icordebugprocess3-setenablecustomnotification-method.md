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
ms.openlocfilehash: 523d9665ffd2637a0e856d74d4d3b3838cb5e83c
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212131"
---
# <a name="icordebugprocess3setenablecustomnotification-method"></a>ICorDebugProcess3::SetEnableCustomNotification (Método)
Habilita y deshabilita las notificaciones del depurador personalizado del tipo especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetEnableCustomNotification(ICorDebugClass * pClass,  
                                    BOOL fEnable);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pClass`  
 de Tipo que especifica las notificaciones del depurador personalizadas.  
  
 `fEnable`  
 [in] `true` para habilitar las notificaciones del depurador personalizadas; `false`para deshabilitar las notificaciones. El valor predeterminado es `false`.  
  
## <a name="remarks"></a>Observaciones  
 Cuando `fEnable` se establece en `true` , las llamadas al <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> método desencadenan una devolución de llamada [ICorDebugManagedCallback3 (:: customnotification (](icordebugmanagedcallback3-customnotification-method.md) . Las notificaciones están deshabilitadas de forma predeterminada; por consiguiente, el depurador debe especificar los tipos de notificación que conoce y desea controlar. Dado que el ámbito de la clase [ICorDebugClass](icordebug-interface.md) es el dominio de aplicación, el depurador debe llamar a `SetEnableCustomNotification` para cada dominio de aplicación en el proceso si desea recibir la notificación en todo el proceso.  
  
 A partir de la .NET Framework 4, la única notificación admitida es una notificación de dependencia entre subprocesos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorDebugProcess3 (Interfaz)](icordebugprocess3-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
- [Depuración](index.md)
