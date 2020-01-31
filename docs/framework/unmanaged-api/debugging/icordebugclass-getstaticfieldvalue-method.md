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
ms.openlocfilehash: 873dd5a1eb2c9356049d2d0c0cb495b963c2ae46
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784189"
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
  
## <a name="parameters"></a>Parameters  
 `fieldDef`  
 de Un campo `Def` token que hace referencia al campo que se va a recuperar.  
  
 `pFrame`  
 de Un puntero a un objeto ICorDebugFrame que representa el marco que se va a utilizar para eliminar la ambigüedad entre el subproceso, el contexto o los estáticos del dominio de aplicación.  
  
 Si el campo estático es relativo a un subproceso, un contexto o un dominio de aplicación, el marco determinará el valor adecuado.  
  
 `ppValue`  
 enuncia Puntero a la dirección de un objeto ICorDebugValue que representa el valor del campo estático.  
  
## <a name="remarks"></a>Notas  
 En el caso de los tipos parametrizados, el valor de un campo estático es relativo a la creación de instancias concreta. Por consiguiente, si el constructor de clase toma parámetros de tipo <xref:System.Type>, llame a [ICorDebugType:: GetStaticFieldValue](icordebugtype-getstaticfieldvalue-method.md) en lugar de a `ICorDebugClass::GetStaticFieldValue`.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
