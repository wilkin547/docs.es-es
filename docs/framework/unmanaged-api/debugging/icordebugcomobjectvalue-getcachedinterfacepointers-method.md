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
ms.openlocfilehash: 9d1d6d2f506086dd3204053b0b635da2e7cdc87e
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783961"
---
# <a name="icordebugcomobjectvaluegetcachedinterfacepointers-method"></a>ICorDebugComObjectValue::GetCachedInterfacePointers (Método)
Obtiene los punteros de interfaz sin formato almacenados en memoria caché en el contenedor RCW (Runtime Callable wrapper) actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetCachedInterfacePointers(  
    [in] BOOL bIInspectableOnly,  
    [in] ULONG32 celt,  
    [out] ULONG32 *pceltFetched,  
    [out, size_is(celt), length_is(*pceltFetched) CORDB_ADDRESS *ptrs);  
```  
  
## <a name="parameters"></a>Parameters  
 `bIInspectableOnly`  
 de Valor que indica si el método devolverá solo Windows Runtime interfaces (interfaces`IInspectable`) o todas las interfaces COM almacenadas en caché por el contenedor RCW (Runtime Callable wrapper).  
  
 `celt`  
 de El número de objetos cuyas direcciones se van a recuperar.  
  
 `pceltFetched`  
 enuncia Puntero al número de valores `CORDB_ADDRESS` realmente devueltos en `ptrs`.  
  
 `ptrs`  
 Puntero a la dirección de inicio de una matriz de valores de `CORDB_ADDRESS` que contienen las direcciones de los objetos de interfaz almacenados en memoria caché.  
  
## <a name="remarks"></a>Notas  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugComObjectValue (interfaz)](icordebugcomobjectvalue-interface.md)
- [Interfaces de depuración](debugging-interfaces.md)
