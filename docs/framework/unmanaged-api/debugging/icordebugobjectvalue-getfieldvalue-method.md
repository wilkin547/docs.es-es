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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 72a504d23b7b15ad3de72995a632843874cc7c5f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54631776"
---
# <a name="icordebugobjectvaluegetfieldvalue-method"></a>ICorDebugObjectValue::GetFieldValue (Método)
Obtiene el valor del campo especificado de la clase especificada para el valor de este objeto.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetFieldValue (  
    [in]  ICorDebugClass     *pClass,  
    [in]  mdFieldDef         fieldDef,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pClass`  
 [in] Un puntero a un objeto "ICorDebugClass" que representa la clase que se va a obtener el valor del campo.  
  
 `fieldDef`  
 [in] Un `mdFieldDef` símbolo (token) que hace referencia a los metadatos que describen el campo.  
  
 `ppValue`  
 [out] Un puntero a un objeto "ICorDebugValue" que representa el valor del campo especificado.  
  
## <a name="remarks"></a>Comentarios  
 La clase, especificada en el `pClass` parámetro, debe estar en la jerarquía de clase del valor de objeto y el campo debe ser un campo de esa clase.  
  
 El `GetFieldValue` método todavía se realizará correctamente para los objetos genéricos y clases genéricas. Por ejemplo, si MyDictionary\<V > hereda de Dictionary\<string, V >, y el valor del objeto es de tipo MyDictionary\<int32 >, pasando el `ICorDebugClass` objeto de diccionario\<K, V > le obtener correctamente un campo de diccionario\<string, int32 >.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también


