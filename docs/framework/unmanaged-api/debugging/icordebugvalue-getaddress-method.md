---
description: 'Más información acerca de: ICorDebugValue:: GetAddress (método)'
title: ICorDebugValue::GetAddress (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugValue.GetAddress
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetAddress
helpviewer_keywords:
- ICorDebugValue::GetAddress method [.NET Framework debugging]
- GetAddress method, ICorDebugValue interface [.NET Framework debugging]
ms.assetid: a247c792-45e1-4538-9e1f-b46acca4a463
topic_type:
- apiref
ms.openlocfilehash: c922388fbab820e50edffc140be94a2c0920099d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99690436"
---
# <a name="icordebugvaluegetaddress-method"></a>ICorDebugValue::GetAddress (Método)

Obtiene la dirección de este objeto "ICorDebugValue", que está en proceso de depuración.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS   *pAddress  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pAddress`  
 enuncia Puntero a un `CORDB_ADDRESS` objeto que especifica la dirección de este objeto de valor.  
  
## <a name="remarks"></a>Observaciones  

 Si el valor no está disponible, se devuelve 0 (cero). Esto puede ocurrir si el valor es, al menos, parcialmente en registros o almacenados en un identificador de recolector de elementos no utilizados ( `GCHandle` ).  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también
