---
title: "ICorDebugType::GetStaticFieldValue (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugType.GetStaticFieldValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugType::GetStaticFieldValue
helpviewer_keywords:
- GetStaticFieldValue method, ICorDebugType interface [.NET Framework debugging]
- ICorDebugType::GetStaticFieldValue method [.NET Framework debugging]
ms.assetid: 62eb5d55-53ee-4fb3-8d47-7b6c96808f9e
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 34a37ef9a28dd0e6325db9bee61146f14d4638a6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugtypegetstaticfieldvalue-method"></a>ICorDebugType::GetStaticFieldValue (Método)
Obtiene un puntero de interfaz a un objeto ICorDebugValue que contiene el valor del campo estático al que hace referencia el campo especificado token en el marco de pila especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef        fieldDef,  
    [in]  ICorDebugFrame    *pFrame,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `fieldDef`  
 [in] Un `mdFieldDef` símbolo (token) que especifica el campo estático.  
  
 `pFrame`  
 [in] Un puntero a un ICorDebugFrame que representa el marco de pila.  
  
 `ppValue`  
 [out] Un puntero a la dirección de un `ICorDebugValue` que contiene el valor del campo estático.  
  
## <a name="remarks"></a>Comentarios  
 El `GetStaticFieldValue` método se puede usar sólo si el tipo es ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE, tal y como indica la [ICorDebugType:: GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) método.  
  
 Para los tipos no genéricos, la operación se realiza por `GetStaticFieldValue` equivale a llamar a [ICorDebugClass:: GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md) en el objeto ICorDebugClass devuelto por [ICorDebugType:: GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md).  
  
 Para los tipos genéricos, será un valor de campo estático con respecto a una instancia determinada. Además, si el campo estático posiblemente podría ser relativo a un subproceso, un contexto o un dominio de aplicación, a continuación, el marco de pila ayudará al depurador determinar el valor adecuado.  
  
## <a name="remarks"></a>Comentarios  
 `GetStaticFieldValue`puede usarse solo cuando una llamada a `ICorDebugType::GetType` devuelve un valor de ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
