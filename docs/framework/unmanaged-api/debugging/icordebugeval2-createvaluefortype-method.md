---
title: ICorDebugEval2::CreateValueForType (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.CreateValueForType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::CreateValueForType
helpviewer_keywords:
- CreateValueForType method [.NET Framework debugging]
- ICorDebugEval2::CreateValueForType method [.NET Framework debugging]
ms.assetid: ea38ae20-7e0a-427a-be77-d78fae719d82
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9ffddb8242b6627239a99bd9223b98762910b831
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67753237"
---
# <a name="icordebugeval2createvaluefortype-method"></a>ICorDebugEval2::CreateValueForType (Método)
Obtiene un puntero a un nuevo objeto ICorDebugValue del tipo especificado, con un valor inicial de cero o null.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CreateValueForType (  
    [in] ICorDebugType         *pType,  
    [out] ICorDebugValue       **ppValue  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pType`  
 [in] Puntero a un objeto ICorDebugType que representa el tipo.  
  
 `ppValue`  
 [out] Puntero a la dirección de un `ICorDebugValue` objeto que representa el valor.  
  
## <a name="remarks"></a>Comentarios  
 `CreateValueForType` generaliza [ICorDebugEval](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-createvalue-method.md) , ya que permite especificar un tipo de objeto arbitrario, incluidos construyen tipos como `List<int>`. Es el único propósito de este método generar un valor que se puede pasar a una evaluación de función.  
  
 El tipo debe ser una clase o un tipo de valor. No se puede usar este método para crear valores de la matriz o los valores de cadena.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
