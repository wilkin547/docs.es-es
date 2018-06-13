---
title: ICorDebugThread4::HadUnhandledException (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThread4.HadUnhandledException Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4::HadUnhandledException
helpviewer_keywords:
- ICorDebugThread4::HadUnhandledException method [.NET Framework debugging]
- HadUnhandledException method [.NET Framework debugging]
ms.assetid: 05558daa-39e2-4c38-aeaf-e2aec4a09468
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8215ddfd0f59f835d0b0dcd278b8cae9c12027d2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422115"
---
# <a name="icordebugthread4hadunhandledexception-method"></a>ICorDebugThread4::HadUnhandledException (Método)
Indica si el subproceso nunca ha tenido una excepción no controlada.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
    );  
```  
  
#### <a name="parameters"></a>Parámetros  
 `ppBlockingObjectEnum`  
 [out] Un puntero a la dirección de una enumeración ordenada de [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) estructuras.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El subproceso ha tenido una excepción no controlada desde su creación.|  
|S_FALSE|El subproceso nunca ha tenido una excepción no controlada.|  
  
## <a name="remarks"></a>Comentarios  
 Este método indica si el subproceso nunca ha tenido una excepción no controlada. Cuando se desencadena la devolución de llamada de excepción no controlada o se inicia la operación de adjuntar de JIT nativa, se garantiza que este método devuelve S_OK. No hay ninguna garantía de que el [ICorDebugThread.GetCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md) método devolverá la excepción no controlada; sin embargo, hará lo siguiente si el proceso no se ha continuado después de obtener la devolución de llamada de excepción no controlada o en adjuntar de JIT nativa. Además, es posible (aunque improbable) que haya más de un subproceso con una excepción no controlada en el momento en que se desencadene la operación de adjuntar de JIT nativa. En tal caso, no hay ninguna manera de determinar qué excepción desencadenó la de adjuntos JIT.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorDebugThread4 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)  
 [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
