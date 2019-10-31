---
title: ICorDebugEval::NewArray (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewArray
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewArray
helpviewer_keywords:
- NewArray method [.NET Framework debugging]
- ICorDebugEval::NewArray method [.NET Framework debugging]
ms.assetid: cc79a67d-5368-434d-a943-209db90491b9
topic_type:
- apiref
ms.openlocfilehash: ca0844e4d2b1cad65266d58c6cda74de203d1758
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137658"
---
# <a name="icordebugevalnewarray-method"></a>ICorDebugEval::NewArray (Método)
Asigna una nueva matriz del tipo de elemento y las dimensiones especificadas.  
  
 Este método está obsoleto en la .NET Framework versión 2,0. Use [ICorDebugEval2:: NewParameterizedArray (](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md) en su lugar.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT NewArray (  
    [in] CorElementType     elementType,  
    [in] ICorDebugClass     *pElementClass,  
    [in] ULONG32            rank,  
    [in, size_is(rank)] ULONG32 dims[],  
    [in, size_is(rank)] ULONG32 lowBounds[]  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `elementType`  
 de Un valor de la enumeración CorElementType que especifica el tipo de elemento de la matriz.  
  
 `pElementClass`  
 de Un puntero a un objeto ICorDebugClass que especifica la clase del elemento. Este valor puede ser null si el tipo de elemento es un tipo primitivo.  
  
 `rank`  
 de Número de dimensiones de la matriz. En el .NET Framework 2,0, este valor debe ser 1.  
  
 `dims`  
 de Tamaño, en bytes, de cada dimensión de la matriz.  
  
 `lowBounds`  
 [in] Opcional. Límite inferior de cada dimensión de la matriz. Si se omite este valor, se supone un límite inferior de cero para cada dimensión.  
  
## <a name="remarks"></a>Comentarios  
 La matriz siempre se crea en el dominio de aplicación en el que se está ejecutando el subproceso.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** 1,1, 1,0
