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
ms.openlocfilehash: 002c6cccb3ddf29b831ba5e14baa5e51f1b82433
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73095879"
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
 de `mdFieldDef` token que hace referencia a los metadatos que describen el campo.  
  
 `ppValue`  
 enuncia Un puntero a un objeto "ICorDebugValue" que representa el valor del campo especificado.  
  
## <a name="remarks"></a>Comentarios  
 La clase, especificada en el parámetro `pClass`, debe estar en la jerarquía de la clase del valor del objeto y el campo debe ser un campo de esa clase.  
  
 El método `GetFieldValue` seguirá teniendo éxito para los objetos genéricos y las clases genéricas. Por ejemplo, si el Diccionario\<V > hereda del diccionario\<cadena, V >, y el valor del objeto es de tipo Dictionary\<Int32 >, pasando el objeto `ICorDebugClass` para el Diccionario\<K, V > obtendrá correctamente un campo de Dictionary\<String, Int32 >.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también
