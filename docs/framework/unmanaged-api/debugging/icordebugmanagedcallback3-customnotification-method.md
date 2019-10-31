---
title: ICorDebugManagedCallback3::CustomNotification (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback3.CustomNotification Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback3::CustomNotification
helpviewer_keywords:
- ICorDebugManagedCallback3::CustomNotification method [.NET Framework debugging]
- CustomNotification method [.NET Framework debugging]
ms.assetid: 5e5422ac-afa1-403d-a894-2d7348673e38
topic_type:
- apiref
ms.openlocfilehash: 83192fd2d24e740ab470988531db823b34df4494
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131438"
---
# <a name="icordebugmanagedcallback3customnotification-method"></a>ICorDebugManagedCallback3::CustomNotification (Método)
Indica que se ha generado una notificación del depurador personalizado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CustomNotification(ICorDebugThread *    pThread,  
                           ICorDebugAppDomain * pAppDomain);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pThread`  
 de Puntero al subproceso que provocó la notificación.  
  
 `pAppDomain`  
 de Puntero al dominio de aplicación que contiene el subproceso que provocó la notificación.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El método se completó correctamente.|  
  
## <a name="exceptions"></a>Excepciones  
  
## <a name="remarks"></a>Comentarios  
 Una llamada subsiguiente al método [ICorDebugThread4:: getcurrentcustomdebuggernotification (](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-getcurrentcustomdebuggernotification-method.md) recupera el objeto de subproceso que se pasó al método <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType>. El tipo del objeto de subproceso debe haberse habilitado previamente mediante una llamada al método [ICorDebugProcess3 (:: SetEnableCustomNotification (](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-setenablecustomnotification-method.md) . El depurador puede leer parámetros específicos del tipo de los campos del objeto de subproceso y puede almacenar las respuestas en los campos.  
  
 La interfaz [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) no impone ninguna directiva en los tipos de notificaciones ni su contenido, y la semántica de las notificaciones es estrictamente un contrato entre los depuradores, las aplicaciones y el .NET Framework.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugManagedCallback3 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-interface.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
