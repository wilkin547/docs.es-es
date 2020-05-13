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
ms.openlocfilehash: 8a4620e591cc80efb5c0fd53b0edf3a35849c421
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209765"
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
  
## <a name="remarks"></a>Observaciones  
 Una llamada subsiguiente al método [ICorDebugThread4:: getcurrentcustomdebuggernotification (](icordebugthread4-getcurrentcustomdebuggernotification-method.md) recupera el objeto de subproceso que se pasó al <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> método. El tipo del objeto de subproceso debe haberse habilitado previamente mediante una llamada al método [ICorDebugProcess3 (:: SetEnableCustomNotification (](icordebugprocess3-setenablecustomnotification-method.md) . El depurador puede leer parámetros específicos del tipo de los campos del objeto de subproceso y puede almacenar las respuestas en los campos.  
  
 La interfaz [ICorDebug](icordebug-interface.md) no impone ninguna directiva en los tipos de notificaciones ni su contenido, y la semántica de las notificaciones es estrictamente un contrato entre los depuradores, las aplicaciones y el .NET Framework.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorDebugManagedCallback3 (Interfaz)](icordebugmanagedcallback3-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
- [Depuración](index.md)
