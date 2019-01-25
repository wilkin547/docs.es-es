---
title: ICorDebugObjectValue::IsValueClass (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue.IsValueClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue::IsValueClass
helpviewer_keywords:
- ICorDebugObjectValue::IsValueClass method [.NET Framework debugging]
- IsValueClass method [.NET Framework debugging]
ms.assetid: 13d89a4a-5d9d-4a79-9600-5e2a98c3d166
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 932d4ecbf34a636d37a60af0ba11f3fc149ffcea
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54649653"
---
# <a name="icordebugobjectvalueisvalueclass-method"></a>ICorDebugObjectValue::IsValueClass (Método)
Obtiene un valor que indica si el valor de este objeto es un tipo de valor.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT IsValueClass (  
    [out] BOOL               *pbIsValueClass  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pbIsValueClass`  
 [out] Un puntero a un valor booleano que es `true` si el valor de objeto, representado por "ICorDebugObjectValue", es un tipo de valor en lugar de un tipo de referencia; de lo contrario, `pbIsValueClass` es `false`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también


