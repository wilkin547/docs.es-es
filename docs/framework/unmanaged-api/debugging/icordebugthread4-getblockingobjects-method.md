---
title: ICorDebugThread4::GetBlockingObjects (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThread4.GetBlockingObjects Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4::GetBlockingObjects
helpviewer_keywords:
- GetBlockingObjects method [.NET Framework debugging]
- ICorDebugThread4::GetBlockingObjects method [.NET Framework debugging]
ms.assetid: a7e6c54e-7be9-4e52-bbb4-95f52458e8e4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5095dc04b118e782b00bb385427ad23a2786343c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54740169"
---
# <a name="icordebugthread4getblockingobjects-method"></a>ICorDebugThread4::GetBlockingObjects (Método)
Proporciona una enumeración ordenada de [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) estructuras que proporcionen información de bloqueo de subprocesos.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
```  
  
#### <a name="parameters"></a>Parámetros  
 `ppBlockingObjectEnum`  
 [out] Un puntero a una enumeración ordenada de [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) estructuras.  
  
## <a name="remarks"></a>Comentarios  
 El primer elemento de la enumeración devuelta corresponde a la primera estructura que está bloqueando el subproceso. El segundo elemento corresponde a un elemento de bloqueo que se produjo al ejecutar una llamada a procedimientos asincrónicos (APC) cuando se bloquea en la primera y así sucesivamente.  
  
 La enumeración es válida solo durante el tiempo que dure el estado sincronizado actual.  
  
 Debe llamar a este método mientras el depurador está en un estado sincronizado.  
  
 Si `ppBlockingObjectEnum` no es un puntero válido, el resultado es indefinido.  
  
 Si un subproceso está bloqueado y no se puede determinar el error, el método devuelve un HRESULT que indica un error; en caso contrario, devuelve S_OK.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [ICorDebugThread4 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
