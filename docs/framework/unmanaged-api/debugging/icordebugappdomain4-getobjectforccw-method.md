---
title: Método de ICorDebugAppDomain4::GetObjectForCCW
ms.date: 03/30/2017
ms.assetid: 2cacdb85-e7b8-42e7-b310-c3e8c22e5d33
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7ab4905c55a1395e9ae5cba8343e6b832622005d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737643"
---
# <a name="icordebugappdomain4getobjectforccw-method"></a>Método de ICorDebugAppDomain4::GetObjectForCCW
Obtiene un objeto administrado de un puntero de contenedor CCW (COM callable wrapper).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetObjectForCCW(  
   [in]CORDB_ADDRESS ccwPointer,   
   [out]ICorDebugValue **ppManagedObject  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `ccwPointer`  
 [in] Puntero de contenedor CCW (COM callable wrapper).  
  
 `ppManagedObject`  
 [out] Un puntero a la dirección de un objeto "ICorDebugValue" que representa el objeto administrado que corresponde al puntero CCW especificado.  
  
## <a name="remarks"></a>Comentarios  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugAppDomain4 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain4-interface.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
