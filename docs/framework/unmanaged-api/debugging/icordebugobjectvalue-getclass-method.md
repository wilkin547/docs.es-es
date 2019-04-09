---
title: ICorDebugObjectValue::GetClass (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue.GetClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue::GetClass
helpviewer_keywords:
- ICorDebugObjectValue::GetClass method [.NET Framework debugging]
- GetClass method, ICorDebugObjectValue interface [.NET Framework debugging]
ms.assetid: 5be25292-8357-445f-a09b-f997c0de761c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 06e9c7af1c4a769bfb45a8e9f805d97b3bad94aa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59174192"
---
# <a name="icordebugobjectvaluegetclass-method"></a>ICorDebugObjectValue::GetClass (Método)
Obtiene la clase de valor de este objeto.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetClass (  
    [out] ICorDebugClass     **ppClass  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `ppClass`  
 [out] Un puntero a la dirección de un objeto "ICorDebugClass" que representa la clase del valor del objeto representado por este objeto "ICorDebugObjectValue".  
  
## <a name="remarks"></a>Comentarios  
 El `GetClass` y [ICorDebugValue](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) métodos cada devuelven información sobre el tipo de valor; ambos son reemplazados por los con elementos genéricos [Icordebugvalue2](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también
