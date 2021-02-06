---
description: 'Más información acerca de: ICorDebugType:: GetStaticFieldValue (método)'
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
ms.openlocfilehash: 378c72f24fedd76f40704ff684781bed124055bb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99658235"
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
 enuncia Un puntero a la dirección de un `ICorDebugValue` que contiene el valor del campo estático.  
  
## <a name="remarks"></a>Observaciones  

 El `GetStaticFieldValue` método solo se puede usar si el tipo es ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE, tal y como se indica en el método [ICorDebugType:: GetType](icordebugtype-gettype-method.md) .  
  
 En el caso de los tipos no genéricos, la operación realizada por `GetStaticFieldValue` es idéntica a llamar a [ICorDebugClass:: GetStaticFieldValue](icordebugclass-getstaticfieldvalue-method.md) en el objeto ICorDebugClass que devuelve [ICorDebugType:: GetClass](icordebugtype-getclass-method.md).  
  
 En el caso de los tipos genéricos, un valor de campo estático será relativo a una instancia determinada. Además, si el campo estático podría ser relacionado con un subproceso, un contexto o un dominio de aplicación, el marco de pila ayudará al depurador a determinar el valor adecuado.  
  
## <a name="remarks"></a>Observaciones  

 `GetStaticFieldValue` solo se puede usar cuando una llamada a `ICorDebugType::GetType` devuelve un valor de ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
