---
title: ICorDebugComObjectValue::GetCachedInterfacePointers (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugComObjectValue::GetCachedInterfacePointers
api_location:
- mscordbi.dll
f1_keywords:
- ICorDebugComObjectValue::GetCachedInterfacePointers
helpviewer_keywords:
- ICorDebugComObjectValue::GetCachedInterfacePointers method [.NET Framework debugging]
- GetCachedInterfacePointers method, ICorDebugComObjectValue interface [.NET Framework debugging]
ms.assetid: 08dbd558-bd39-4263-94c2-71e70687aaf0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bdbec0101de269b3d5b09e750d552c993a0198ab
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67748482"
---
# <a name="icordebugcomobjectvaluegetcachedinterfacepointers-method"></a>ICorDebugComObjectValue::GetCachedInterfacePointers (Método)
Obtiene los punteros de interfaz sin formato almacenados en caché en el contenedor invocable en tiempo de ejecución actual (RCW).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetCachedInterfacePointers(  
    [in] BOOL bIInspectableOnly,  
    [in] ULONG32 celt,  
    [out] ULONG32 *pceltFetched,  
    [out, size_is(celt), length_is(*pceltFetched) CORDB_ADDRESS *ptrs);  
```  
  
## <a name="parameters"></a>Parámetros  
 `bIInspectableOnly`  
 [in] Un valor que indica si el método devolverá solo las interfaces de Windows en tiempo de ejecución (`IInspectable` interfaces) o todas las interfaces COM que se almacenan en caché por el contenedor invocable en tiempo de ejecución (RCW).  
  
 `celt`  
 [in] El número de objetos cuyas direcciones se van a recuperar.  
  
 `pceltFetched`  
 [out] Un puntero al número de `CORDB_ADDRESS` valores devueltos realmente en `ptrs`.  
  
 `ptrs`  
 Un puntero a la dirección inicial de una matriz de `CORDB_ADDRESS` valores que contienen las direcciones de almacenar en caché los objetos de interfaz.  
  
## <a name="remarks"></a>Comentarios  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugComObjectValue (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-interface.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
