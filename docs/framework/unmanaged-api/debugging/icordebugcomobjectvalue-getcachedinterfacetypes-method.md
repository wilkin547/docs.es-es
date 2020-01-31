---
title: ICorDebugComObjectValue::GetCachedInterfaceTypes (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugComObjectValue::GetCachedInterfaceTypes
api_location:
- mscordbi.dll
f1_keywords:
- ICorDebugComObjectValue::GetCachedInterfaceTypes
helpviewer_keywords:
- GetCachedInterface method, ICorDebugComObjectValue interface [.NET Framework debugging]
- ICorDebugComObjectValue::GetCachedInterface method [.NET Framework debugging]
ms.assetid: d492284f-d3c5-4614-adb8-d718d5042500
topic_type:
- apiref
ms.openlocfilehash: f720b06581ac60c8bd68dc5e85f15843fd9425f6
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788905"
---
# <a name="icordebugcomobjectvaluegetcachedinterfacetypes-method"></a>ICorDebugComObjectValue::GetCachedInterfaceTypes (Método)
Proporciona un enumerador para los tipos de interfaz en los que se ha convertido el objeto actual o se ha utilizado como.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetCachedInterfaceTypes(  
    [in] BOOL bIInspectableOnly,  
    [out] ICorDebugTypeEnum **ppInterfacesEnum);  
```  
  
## <a name="parameters"></a>Parameters  
 `bIInspectableOnly`  
 de Valor que indica si el método devuelve solo Windows Runtime interfaces (interfaces`IInspectable`) o todas las interfaces COM almacenadas en caché por el contenedor RCW (Runtime Callable wrapper).  
  
 `ppInterfacesEnum`  
 enuncia Puntero a la dirección de un enumerador ICorDebugTypeEnum que proporciona acceso a los objetos ICorDebugType que representan los tipos de interfaz almacenados en memoria caché filtrados según `bIInspectableOnly`.  
  
## <a name="remarks"></a>Notas  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugComObjectValue (interfaz)](icordebugcomobjectvalue-interface.md)
- [Interfaces de depuración](debugging-interfaces.md)
