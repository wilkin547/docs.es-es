---
title: ICorDebugType::GetStaticFieldValue (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetStaticFieldValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetStaticFieldValue
helpviewer_keywords:
- GetStaticFieldValue method, ICorDebugType interface [.NET Framework debugging]
- ICorDebugType::GetStaticFieldValue method [.NET Framework debugging]
ms.assetid: 62eb5d55-53ee-4fb3-8d47-7b6c96808f9e
topic_type:
- apiref
ms.openlocfilehash: 95183701987d3ddec3835a17c5d256c25c2c4c64
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132064"
---
# <a name="icordebugtypegetstaticfieldvalue-method"></a>ICorDebugType::GetStaticFieldValue (Método)
Obtiene un puntero de interfaz a un objeto ICorDebugValue que contiene el valor del campo estático al que hace referencia el token de campo especificado en el marco de pila especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef        fieldDef,  
    [in]  ICorDebugFrame    *pFrame,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `fieldDef`  
 de Un `mdFieldDef` token que especifica el campo estático.  
  
 `pFrame`  
 de Un puntero a un ICorDebugFrame que representa el marco de pila.  
  
 `ppValue`  
 enuncia Puntero a la dirección de una `ICorDebugValue` que contiene el valor del campo estático.  
  
## <a name="remarks"></a>Comentarios  
 El método `GetStaticFieldValue` solo se puede usar si el tipo es ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE, tal y como se indica en el método [ICorDebugType:: GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) .  
  
 En el caso de los tipos no genéricos, la operación realizada por `GetStaticFieldValue` es idéntica a llamar a [ICorDebugClass:: GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md) en el objeto ICorDebugClass que devuelve [ICorDebugType:: GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md).  
  
 En el caso de los tipos genéricos, un valor de campo estático será relativo a una instancia determinada. Además, si el campo estático podría ser relacionado con un subproceso, un contexto o un dominio de aplicación, el marco de pila ayudará al depurador a determinar el valor adecuado.  
  
## <a name="remarks"></a>Comentarios  
 `GetStaticFieldValue` solo se puede usar cuando una llamada a `ICorDebugType::GetType` devuelve un valor de ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
