---
title: ICorDebugProcess5::GetArrayLayout (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetArrayLayout
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetArrayLayout
helpviewer_keywords:
- ICorDebugProcess5::GetArrayLayout method [.NET Framework debugging]
- GetArrayLayout method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 9a7393b9-9735-43c6-8616-afb103c432fd
topic_type:
- apiref
ms.openlocfilehash: aac3d54d25b50d0e2ce3e93cdfba5a17679e1f76
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209674"
---
# <a name="icordebugprocess5getarraylayout-method"></a>ICorDebugProcess5::GetArrayLayout (Método)
Proporciona información sobre el diseño de los tipos de matriz.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetArrayLayout(    [in] COR_TYPEID id,     [out] COR_ARRAY_LAYOUT *pLayout);  
```  
  
## <a name="parameters"></a>Parámetros  
 `id`  
 de [COR_TYPEID](cor-typeid-structure.md) token que especifica la matriz cuyo diseño se desea.  
  
 `pLayout`  
 enuncia Puntero a una estructura de [COR_ARRAY_LAYOUT](cor-array-layout-structure.md) que contiene información sobre el diseño de la matriz en memoria.  
  
## <a name="remarks"></a>Observaciones  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorDebugProcess5 (Interfaz)](icordebugprocess5-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
