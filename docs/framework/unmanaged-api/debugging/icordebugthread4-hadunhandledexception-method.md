---
description: 'Más información sobre: ICorDebugThread4:: HadUnhandledException ((método)'
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
ms.openlocfilehash: cd0ccdbdd68c37b5fbdbd705da7136e5d36baa60
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800934"
---
# <a name="icordebugthread4hadunhandledexception-method"></a>ICorDebugThread4::HadUnhandledException (Método)

Indica si el subproceso ha tenido alguna vez una excepción no controlada.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
    );  
```  
  
## <a name="parameters"></a>Parámetros  

 `ppBlockingObjectEnum`  
 enuncia Puntero a la dirección de una enumeración ordenada de estructuras [CorDebugBlockingObject](cordebugblockingobject-structure.md) .  
  
## <a name="return-value"></a>Valor devuelto  

 Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El subproceso ha tenido una excepción no controlada desde su creación.|  
|S_FALSE|El subproceso nunca ha tenido una excepción no controlada.|  
  
## <a name="remarks"></a>Observaciones  

 Este método indica si el subproceso ha tenido alguna vez una excepción no controlada. En el momento en que se desencadena la devolución de llamada de excepción no controlada o se inicia la Asociación JIT nativa, se garantiza que este método devuelve S_OK. No hay ninguna garantía de que el método [ICorDebugThread. GetCurrentException (](icordebugthread-getcurrentexception-method.md) devuelva la excepción no controlada. sin embargo, si el proceso aún no se ha continuado después de obtener la devolución de llamada de excepción no controlada o después de la Asociación JIT nativa. Además, es posible (aunque improbable) tener más de un subproceso con una excepción no controlada en el momento en que se desencadena la Asociación JIT nativa. En tal caso, no hay ninguna manera de determinar qué excepción desencadenó la Asociación JIT.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugThread4 (Interfaz)](icordebugthread4-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
- [Depuración](index.md)
