---
title: ICorDebugManagedCallback2::ExceptionUnwind (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.ExceptionUnwind
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::ExceptionUnwind
helpviewer_keywords:
- ICorDebugManagedCallback2::ExceptionUnwind method [.NET Framework debugging]
- ExceptionUnwind method [.NET Framework debugging]
ms.assetid: aaf5938d-179c-4eaa-8d35-8523a4fadded
topic_type:
- apiref
ms.openlocfilehash: fa317e1217ac0a9ca46bfeb312446534b1fca63a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131565"
---
# <a name="icordebugmanagedcallback2exceptionunwind-method"></a>ICorDebugManagedCallback2::ExceptionUnwind (Método)
Proporciona una notificación de estado durante el proceso de desenredo de excepciones.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ExceptionUnwind (  
    [in] ICorDebugAppDomain                  *pAppDomain,  
    [in] ICorDebugThread                     *pThread,  
    [in] CorDebugExceptionUnwindCallbackType  dwEventType,  
    [in] DWORD                                dwFlags  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pAppDomain`  
 de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene el subproceso en el que se produjo la excepción.  
  
 `pThread`  
 de Un puntero a un objeto ICorDebugThread que representa el subproceso en el que se produjo la excepción.  
  
 `dwEventType`  
 de Un valor de la enumeración CorDebugExceptionUnwindCallbackType (que especifica el evento que la devolución de llamada señala durante la fase de desenredado.  
  
 `dwFlags`  
 de Un valor de la enumeración [cordebugexceptionflags (](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) que especifica información adicional sobre la excepción.  
  
## <a name="remarks"></a>Comentarios  
 se llama a `ExceptionUnwind` en varios puntos durante la fase de desenredado del proceso de control de excepciones. `ExceptionUnwind` se puede llamar más de una vez al desenredar una sola excepción.  
  
 Si `dwEventType` = DEBUG_EXCEPTION_INTERCEPTED, el puntero de instrucción estará en el marco hoja del subproceso, en el punto de secuencia antes (puede haber varias instrucciones antes) de la instrucción que condujo a la excepción.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugManagedCallback2 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [ICorDebugManagedCallback (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
