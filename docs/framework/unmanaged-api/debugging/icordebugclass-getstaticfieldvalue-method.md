---
title: ICorDebugClass::GetStaticFieldValue (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugClass.GetStaticFieldValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass::GetStaticFieldValue
helpviewer_keywords:
- GetStaticFieldValue method, ICorDebugClass interface [.NET Framework debugging]
- ICorDebugClass::GetStaticFieldValue method [.NET Framework debugging]
ms.assetid: 56e718b4-fabd-418b-a5b3-3cc33c745683
topic_type:
- apiref
ms.openlocfilehash: 867db3325f9b18b31f66429d01ea02be3603c0f6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125762"
---
# <a name="icordebugclassgetstaticfieldvalue-method"></a>ICorDebugClass::GetStaticFieldValue (Método)
Obtiene el valor del campo estático especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef         fieldDef,  
    [in]  ICorDebugFrame     *pFrame,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `fieldDef`  
 de Un campo `Def` token que hace referencia al campo que se va a recuperar.  
  
 `pFrame`  
 de Un puntero a un objeto ICorDebugFrame que representa el marco que se va a utilizar para eliminar la ambigüedad entre el subproceso, el contexto o los estáticos del dominio de aplicación.  
  
 Si el campo estático es relativo a un subproceso, un contexto o un dominio de aplicación, el marco determinará el valor adecuado.  
  
 `ppValue`  
 enuncia Puntero a la dirección de un objeto ICorDebugValue que representa el valor del campo estático.  
  
## <a name="remarks"></a>Comentarios  
 En el caso de los tipos parametrizados, el valor de un campo estático es relativo a la creación de instancias concreta. Por consiguiente, si el constructor de clase toma parámetros de tipo <xref:System.Type>, llame a [ICorDebugType:: GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md) en lugar de a `ICorDebugClass::GetStaticFieldValue`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
