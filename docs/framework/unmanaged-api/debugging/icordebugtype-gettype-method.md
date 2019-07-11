---
title: ICorDebugType::GetType (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetType
helpviewer_keywords:
- ICorDebugType::GetType method [.NET Framework debugging]
- GetType method, ICorDebugType interface [.NET Framework debugging]
ms.assetid: d6e64534-4d47-4ad0-a340-7590e07e2b4a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 78f2733584e07433171c91d6a2674d3a67c8e283
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67772520"
---
# <a name="icordebugtypegettype-method"></a>ICorDebugType::GetType (Método)
Obtiene un valor de CorElementType que describe el tipo nativo de common language runtime (CLR) <xref:System.Type> representado por esta instancia de ICorDebugType.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetType (  
    [out] CorElementType   *ty  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `ty`  
 [out] Un puntero a un valor de la `CorElementType` enumeración que indica el CLR <xref:System.Type> que `ICorDebugType` representa.  
  
## <a name="remarks"></a>Comentarios  
 Si el valor de `ty` es ELEMENT_TYPE_CLASS o ELEMENT_TYPE_VALUETYPE, el [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getclass-method.md) método puede llamarse para obtener el tipo sin instancias de un tipo genérico; de lo contrario, no llame a `ICorDebugType::GetClass`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
