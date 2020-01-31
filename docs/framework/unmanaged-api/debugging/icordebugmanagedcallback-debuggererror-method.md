---
title: ICorDebugManagedCallback::DebuggerError (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.DebuggerError
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::DebuggerError
helpviewer_keywords:
- DebuggerError method [.NET Framework debugging]
- ICorDebugManagedCallback::DebuggerError method [.NET Framework debugging]
ms.assetid: 9e983d11-eaf3-4741-b936-29ec456384a3
topic_type:
- apiref
ms.openlocfilehash: 9b96c0a2eca543b9e01ccf92b271b1aa7003c5c9
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76781946"
---
# <a name="icordebugmanagedcallbackdebuggererror-method"></a>ICorDebugManagedCallback::DebuggerError (Método)
Notifica al depurador que se ha producido un error al intentar controlar un evento desde el Common Language Runtime (CLR).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT DebuggerError (  
    [in] ICorDebugProcess *pProcess,  
    [in] HRESULT           errorHR,  
    [in] DWORD             errorCode  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `pProcess`  
 de Un puntero a un objeto "ICorDebugProcess" que representa el proceso en el que se produjo el evento.  
  
 `errorHR`  
 de Valor HRESULT devuelto por el controlador de eventos.  
  
 `errorCode`  
 de Un entero que especifica el error de CLR.  
  
## <a name="remarks"></a>Notas  
 El proceso se puede poner en modo de paso a través, dependiendo de la naturaleza del error.  
  
 La devolución de llamada `DebugError` indica que los servicios de depuración se han deshabilitado debido a un error, de modo que los depuradores deberían poner el mensaje de error a disposición del usuario. Se puede llamar a [ICorDebugProcess:: getId](icordebugprocess-getid-method.md) con seguridad, pero no se debe llamar a todos los demás métodos, incluido [ICorDebug:: Terminate](icordebug-terminate-method.md). El depurador debe usar las funciones del sistema operativo para finalizar los procesos.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugManagedCallback (interfaz)](icordebugmanagedcallback-interface.md)
