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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6d67784daee055106f104d74d098b9926c6de2ec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33417117"
---
# <a name="icordebugevalcreatevalue-method"></a>ICorDebugEval::CreateValue (Método)
Crea un valor del tipo especificado, con un valor inicial de cero o null.  
  
 Este método está obsoleto en la versión 2.0 de .NET Framework. Use [ICorDebugEval2:: CreateValueForType](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md) en su lugar.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT CreateValue (  
    [in] CorElementType     elementType,  
    [in] ICorDebugClass     *pElementClass,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `elementType`  
 [in] Un valor de la [CorElementType](../../../../docs/framework/unmanaged-api/metadata/corelementtype-enumeration.md) enumeración que especifica el tipo del valor.  
  
 `pElementClass`  
 [in] Puntero a un [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md) objeto que especifica la clase del valor, si el tipo no es un tipo primitivo.  
  
 `ppValue`  
 [out] Puntero a la dirección de un objeto de "ICorDebugValue" que representa el valor.  
  
## <a name="remarks"></a>Comentarios  
 `CreateValue` crea un `ICorDebugValue` objeto del tipo especificado con el único fin de utilizarlo en una evaluación de función. Este objeto de valor se puede usar para pasar constantes de usuario como parámetros.  
  
 Si el tipo del valor es un tipo primitivo, su valor inicial es cero o null. Use [ICorDebugGenericValue:: SetValue](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-setvalue-method.md) para establecer el valor de un tipo primitivo.  
  
 Si el valor de `elementType` es ELEMENT_TYPE_CLASS, obtendrá un "ICorDebugReferenceValue" (devuelto en `ppValue`) que representa la referencia de objeto null. Puede utilizar este objeto para pasar null para una evaluación de función que tiene parámetros de referencia de objeto. No se puede establecer el `ICorDebugValue` que hacer nada; siempre es null.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** 1.1, 1.0  
  
## <a name="see-also"></a>Vea también  
    
 [CreateValueForType (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-createvaluefortype-method.md)  
 ICorDebugValue
