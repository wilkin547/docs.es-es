---
title: ICorDebugProcess5::GetObject (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetObject
helpviewer_keywords:
- GetObject method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::GetObject method [.NET Framework debugging]
ms.assetid: c8111502-5a20-447f-9dc2-76e8acd7ed5a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 35fdcd4bc3c9dbf6408f501256ce0df0174f9374
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59135660"
---
# <a name="icordebugprocess5getobject-method"></a>ICorDebugProcess5::GetObject (Método)
Convierte una dirección de objeto a un objeto "ICorDebugObjectValue".  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetObject(  
    [in] CORDB_ADDRESS addr,   
    [out] ICorDebugObjectValue **ppObject  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `addr`  
 [in] La dirección del objeto.  
  
 `ppObject`  
 [out] Un puntero a la dirección de un objeto "ICorDebugObjectValue".  
  
## <a name="remarks"></a>Comentarios  
 Si `addr` no apunta a un objeto administrado válido, el `GetObject` devuelve del método `E_FAIL`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugProcess5 (Interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [Interfaces para depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
