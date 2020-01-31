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
ms.openlocfilehash: f2f365f3fe1568f2dd3bad677dd77a13946002e1
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792468"
---
# <a name="icordebugprocess3setenablecustomnotification-method"></a>ICorDebugProcess3::SetEnableCustomNotification (Método)
Habilita y deshabilita las notificaciones del depurador personalizado del tipo especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetEnableCustomNotification(ICorDebugClass * pClass,  
                                    BOOL fEnable);  
```  
  
## <a name="parameters"></a>Parameters  
 `pClass`  
 de Tipo que especifica las notificaciones del depurador personalizadas.  
  
 `fEnable`  
 [in] `true` para habilitar las notificaciones personalizadas del depurador; `false` para deshabilitar las notificaciones. El valor predeterminado es `false`.  
  
## <a name="remarks"></a>Notas  
 Cuando `fEnable` se establece en `true`, las llamadas al método <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> desencadenan una devolución de llamada [ICorDebugManagedCallback3 (:: customnotification (](icordebugmanagedcallback3-customnotification-method.md) . Las notificaciones están deshabilitadas de forma predeterminada; por consiguiente, el depurador debe especificar los tipos de notificación que conoce y desea controlar. Dado que el ámbito de la clase [ICorDebugClass](icordebug-interface.md) es el dominio de aplicación, el depurador debe llamar a `SetEnableCustomNotification` para cada dominio de aplicación en el proceso si desea recibir la notificación en todo el proceso.  
  
 A partir de la .NET Framework 4, la única notificación admitida es una notificación de dependencia entre subprocesos.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugProcess3 (interfaz)](icordebugprocess3-interface.md)
- [Interfaces de depuración](debugging-interfaces.md)
- [Depuración](index.md)
