---
title: ICorDebugEval::CreateValue (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugEval.CreateValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::CreateValue
helpviewer_keywords:
- ICorDebugEval::CreateValue method [.NET Framework debugging]
- CreateValue method [.NET Framework debugging]
ms.assetid: 9a1c0b47-6f10-4fcb-844a-4ab2d7990140
topic_type:
- apiref
ms.openlocfilehash: 4bb04ba090be9cab551bc39d8d9f1be974c747d3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73085134"
---
# <a name="icordebugevalcreatevalue-method"></a>ICorDebugEval::CreateValue (Método)
Crea un valor del tipo especificado, con un valor inicial de cero o null.  
  
 Este método está obsoleto en la .NET Framework versión 2,0. Use [ICorDebugEval2:: createvaluefortype (](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md) en su lugar.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CreateValue (  
    [in] CorElementType     elementType,  
    [in] ICorDebugClass     *pElementClass,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `elementType`  
 de Un valor de la enumeración [CorElementType](../../../../docs/framework/unmanaged-api/metadata/corelementtype-enumeration.md) que especifica el tipo del valor.  
  
 `pElementClass`  
 de Puntero a un objeto [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md) que especifica la clase del valor, si el tipo no es un tipo primitivo.  
  
 `ppValue`  
 enuncia Puntero a la dirección de un objeto "ICorDebugValue" que representa el valor.  
  
## <a name="remarks"></a>Comentarios  
 `CreateValue` crea un objeto `ICorDebugValue` del tipo especificado con el único fin de utilizarlo en una evaluación de función. Este objeto de valor se puede usar para pasar constantes de usuario como parámetros.  
  
 Si el tipo del valor es un tipo primitivo, su valor inicial es cero o null. Use [ICorDebugGenericValue:: SetValue](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-setvalue-method.md) para establecer el valor de un tipo primitivo.  
  
 Si el valor de `elementType` es ELEMENT_TYPE_CLASS, obtendrá un "ICorDebugReferenceValue" (devuelto en `ppValue`) que representa la referencia de objeto null. Puede utilizar este objeto para pasar null a una evaluación de función que tenga parámetros de referencia de objeto. No se puede establecer el `ICorDebugValue` en nada; siempre sigue siendo null.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** 1,1, 1,0  
  
## <a name="see-also"></a>Vea también

- [CreateValueForType (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md)
- [ICorDebugEval (interfaz)](icordebugeval-interface.md)
