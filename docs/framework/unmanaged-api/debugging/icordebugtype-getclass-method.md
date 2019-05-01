---
title: ICorDebugType::GetClass (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetClass
helpviewer_keywords:
- ICorDebugType::GetClass method [.NET Framework debugging]
- GetClass method, ICorDebugType interface [.NET Framework debugging]
ms.assetid: 2644f48b-db3c-429f-ae62-76f1c98a1af5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0915027ce6a3768ff854eafc5496c5057081cc4d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61946216"
---
# <a name="icordebugtypegetclass-method"></a>ICorDebugType::GetClass (Método)
Obtiene un puntero de interfaz a ICorDebugClass que representa el tipo genérico sin instancias.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetClass (  
    [out] ICorDebugClass   **ppClass  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `ppClass`  
 [out] Un puntero a la dirección de un `ICorDebugClass` interfaz que representa el tipo genérico sin instancias.  
  
## <a name="remarks"></a>Comentarios  
 `GetClass` se puede llamar sólo bajo ciertas condiciones. Llame a [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) antes de llamar a `GetClass`. Si `ICorDebugType::GetType` devuelve un valor CorElementType ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE, `GetClass` se puede llamar para obtener el tipo sin instancias de un tipo genérico.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
