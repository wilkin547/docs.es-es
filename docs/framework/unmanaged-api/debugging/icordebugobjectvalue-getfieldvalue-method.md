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
ms.openlocfilehash: 745be25183f6b94e7a807c4230961d72e2836fe5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695340"
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
 de `mdFieldDef` Token que hace referencia a los metadatos que describen el campo.  
  
 `ppValue`  
 enuncia Un puntero a un objeto "ICorDebugValue" que representa el valor del campo especificado.  
  
## <a name="remarks"></a>Comentarios  

 La clase, especificada en el `pClass` parámetro, debe estar en la jerarquía de la clase del valor del objeto y el campo debe ser un campo de esa clase.  
  
 El `GetFieldValue` método seguirá teniendo éxito para los objetos genéricos y las clases genéricas. Por ejemplo, si \<V> se hereda de Dictionary \<string,V> y el valor del objeto es del tipo de diccionario \<int32> , el paso del `ICorDebugClass` objeto para el diccionario \<K,V> obtendrá correctamente un campo de diccionario \<string,int32> .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también
