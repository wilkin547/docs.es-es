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
ms.openlocfilehash: 37bf5abf66b613d8432af84c7d73aff60e9127cb
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791271"
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
  
## <a name="parameters"></a>Parameters  
 `fieldDef`  
 de Un `mdFieldDef` token que especifica el campo estático.  
  
 `pFrame`  
 de Un puntero a un ICorDebugFrame que representa el marco de pila.  
  
 `ppValue`  
 enuncia Puntero a la dirección de una `ICorDebugValue` que contiene el valor del campo estático.  
  
## <a name="remarks"></a>Notas  
 El método `GetStaticFieldValue` solo se puede usar si el tipo es ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE, como indica el método [ICorDebugType:: GetType](icordebugtype-gettype-method.md) .  
  
 En el caso de los tipos no genéricos, la operación realizada por `GetStaticFieldValue` es idéntica a llamar a [ICorDebugClass:: GetStaticFieldValue](icordebugclass-getstaticfieldvalue-method.md) en el objeto ICorDebugClass que devuelve [ICorDebugType:: GetClass](icordebugtype-getclass-method.md).  
  
 En el caso de los tipos genéricos, un valor de campo estático será relativo a una instancia determinada. Además, si el campo estático podría ser relacionado con un subproceso, un contexto o un dominio de aplicación, el marco de pila ayudará al depurador a determinar el valor adecuado.  
  
## <a name="remarks"></a>Notas  
 `GetStaticFieldValue` solo se puede usar cuando una llamada a `ICorDebugType::GetType` devuelve un valor de ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
