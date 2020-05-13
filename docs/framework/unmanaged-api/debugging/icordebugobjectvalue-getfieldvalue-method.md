---
title: ICorDebugObjectValue::GetFieldValue (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue.GetFieldValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue::GetFieldValue
helpviewer_keywords:
- ICorDebugObjectValue::GetFieldValue method [.NET Framework debugging]
- GetFieldValue method [.NET Framework debugging]
ms.assetid: c96770b0-3e09-47bb-bd29-20353b043459
topic_type:
- apiref
ms.openlocfilehash: 660bc13e8109994f59444c0adebbc97f54de0b43
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207587"
---
# <a name="icordebugobjectvaluegetfieldvalue-method"></a>ICorDebugObjectValue::GetFieldValue (Método)
Obtiene el valor del campo especificado de la clase especificada para este valor de objeto.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetFieldValue (  
    [in]  ICorDebugClass     *pClass,  
    [in]  mdFieldDef         fieldDef,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pClass`  
 de Un puntero a un objeto "ICorDebugClass" que representa la clase para la que se va a obtener el valor del campo.  
  
 `fieldDef`  
 de `mdFieldDef`Token que hace referencia a los metadatos que describen el campo.  
  
 `ppValue`  
 enuncia Un puntero a un objeto "ICorDebugValue" que representa el valor del campo especificado.  
  
## <a name="remarks"></a>Observaciones  
 La clase, especificada en el `pClass` parámetro, debe estar en la jerarquía de la clase del valor del objeto y el campo debe ser un campo de esa clase.  
  
 El `GetFieldValue` método seguirá teniendo éxito para los objetos genéricos y las clases genéricas. Por ejemplo, si el diccionario \< v> hereda de la cadena del diccionario \< , V> y el valor del objeto es del tipo de Diccionario de \< Int32>, al pasar el `ICorDebugClass` objeto del diccionario \< K, V> obtendrá correctamente un campo de cadena de diccionario \< , Int32>.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también
