---
title: "ICorDebugEval2::CreateValueForType (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval2.CreateValueForType
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval2::CreateValueForType
helpviewer_keywords:
- CreateValueForType method [.NET Framework debugging]
- ICorDebugEval2::CreateValueForType method [.NET Framework debugging]
ms.assetid: ea38ae20-7e0a-427a-be77-d78fae719d82
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 18e7eb5fc30c27fd2c4865dc61e2f75dc9e96068
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugeval2createvaluefortype-method"></a>ICorDebugEval2::CreateValueForType (Método)
Obtiene un puntero a un nuevo objeto ICorDebugValue del tipo especificado, con un valor inicial de cero o null.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT CreateValueForType (  
    [in] ICorDebugType         *pType,  
    [out] ICorDebugValue       **ppValue  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pType`  
 [in] Puntero a un objeto ICorDebugType que representa el tipo.  
  
 `ppValue`  
 [out] Puntero a la dirección de un `ICorDebugValue` objeto que representa el valor.  
  
## <a name="remarks"></a>Comentarios  
 `CreateValueForType`generaliza [ICorDebugEval:: CreateValue](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-createvalue-method.md) por lo que permite especificar un tipo de objeto arbitrario, incluidos construyen tipos como `List<int>`. El único propósito de este método consiste en generar un valor que puede pasarse a una evaluación de función.  
  
 El tipo debe ser una clase o un tipo de valor. No se puede usar este método para crear valores de matriz o valores de cadena.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
