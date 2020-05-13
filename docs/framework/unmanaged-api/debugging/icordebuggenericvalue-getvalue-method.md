---
title: ICorDebugGenericValue::GetValue (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugGenericValue.GetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGenericValue::GetValue
helpviewer_keywords:
- ICorDebugGenericValue::GetValue method [.NET Framework debugging]
- GetValue method, ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: 4e95d7cb-144d-4ccf-8a69-d605f4744be2
topic_type:
- apiref
ms.openlocfilehash: 646b2661148e38f3c918fc18fce5c9cd0b1134a1
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213028"
---
# <a name="icordebuggenericvaluegetvalue-method"></a>ICorDebugGenericValue::GetValue (Método)
Copia el valor de este genérico en el búfer especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetValue (  
    [out] void     *pTo  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pTo`  
 enuncia Puntero al valor representado por este objeto ICorDebugGenericValue. El valor puede ser un tipo simple o un tipo de referencia (es decir, un puntero).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
