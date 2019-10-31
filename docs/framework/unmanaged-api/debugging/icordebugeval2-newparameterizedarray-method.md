---
title: ICorDebugEval2::NewParameterizedArray (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.NewParameterizedArray
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::NewParameterizedArray
helpviewer_keywords:
- ICorDebugEval2::NewParameterizedArray method [.NET Framework debugging]
- NewParameterizedArray method [.NET Framework debugging]
ms.assetid: 45efb8ba-c4de-4109-945f-e734d376b43c
topic_type:
- apiref
ms.openlocfilehash: 9476bcc9706e89fd3d7e0abc14031f70a0aa0ad0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73084833"
---
# <a name="icordebugeval2newparameterizedarray-method"></a>ICorDebugEval2::NewParameterizedArray (Método)
Asigna una nueva matriz del tipo de elemento y las dimensiones especificadas.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT NewParameterizedArray(  
    [in] ICorDebugType          *pElementType,  
    [in] ULONG32                rank,  
    [in, size_is(rank)] ULONG32 dims[],  
    [in, size_is(rank)] ULONG32 lowBounds[]  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pElementType`  
 de Un puntero a un objeto ICorDebugType que representa el tipo de elemento almacenado en la matriz.  
  
 `rank`  
 de Número de dimensiones de la matriz. En la .NET Framework versión 2,0, este valor debe ser 1.  
  
 `dims`  
 de Tamaño, en bytes, de cada dimensión de la matriz.  
  
 `lowBounds`  
 [in] Opcional. Límite inferior de cada dimensión de la matriz. Si se omite este valor, se supone un límite inferior de cero para cada dimensión.  
  
## <a name="remarks"></a>Comentarios  
 Los elementos de la matriz pueden ser instancias de un tipo genérico. La matriz siempre se crea en el dominio de aplicación en el que el subproceso se está ejecutando actualmente. En el .NET Framework 2,0, el valor de `rank` debe ser 1.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
