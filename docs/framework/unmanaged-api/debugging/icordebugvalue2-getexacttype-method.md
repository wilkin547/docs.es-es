---
title: ICorDebugValue2::GetExactType (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugValue2.GetExactType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue2::GetExactType
helpviewer_keywords:
- ICorDebugValue2::GetExactType method [.NET Framework debugging]
- GetExactType method [.NET Framework debugging]
ms.assetid: 8e9aae1b-d1b7-4b6e-b577-6faf36dcec85
topic_type:
- apiref
ms.openlocfilehash: cb5bec66ab02de248109d8aaf444a93e67c2c6d2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720365"
---
# <a name="icordebugvalue2getexacttype-method"></a>ICorDebugValue2::GetExactType (Método)

Obtiene un puntero de interfaz a un objeto "ICorDebugType" que representa el <xref:System.Type> de este valor.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetExactType (  
    [out] ICorDebugType   **ppType  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `ppType`  
 enuncia Puntero a la dirección de un `ICorDebugType` objeto que representa el <xref:System.Type> del valor representado por este objeto "ICorDebugValue2".  
  
## <a name="remarks"></a>Comentarios  

 El método compatible con genéricos `GetExactType` sustituye a los métodos [ICorDebugObjectValue:: GetClass](icordebugobjectvalue-getclass-method.md) y [ICorDebugValue:: GetType](icordebugvalue-gettype-method.md) , cada uno de los cuales devuelve información sobre el tipo de un valor.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también
