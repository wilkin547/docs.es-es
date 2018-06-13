---
title: Método de ICorDebugAppDomain4::GetObjectForCCW
ms.date: 03/30/2017
ms.assetid: 2cacdb85-e7b8-42e7-b310-c3e8c22e5d33
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f1089668aa19747f5f694360ebb87098e2df9ad4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405556"
---
# <a name="icordebugappdomain4getobjectforccw-method"></a>Método de ICorDebugAppDomain4::GetObjectForCCW
Obtiene un objeto administrado de un puntero de contenedor CCW (COM callable wrapper).  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetObjectForCCW(  
   [in]CORDB_ADDRESS ccwPointer,   
   [out]ICorDebugValue **ppManagedObject  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `ccwPointer`  
 [in] Puntero de contenedor CCW (COM callable wrapper).  
  
 `ppManagedObject`  
 [out] Un puntero a la dirección de un objeto de "ICorDebugValue" que representa el objeto administrado que corresponde al puntero CCW especificado.  
  
## <a name="remarks"></a>Comentarios  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorDebugAppDomain4 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain4-interface.md)  
 [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
