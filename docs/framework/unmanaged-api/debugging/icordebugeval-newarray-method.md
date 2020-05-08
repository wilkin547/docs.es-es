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
ms.openlocfilehash: 496a6a7e01dec8aa90ba4e849c431ccd499ef53d
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976205"
---
# <a name="icordebugevalnewarray-method"></a>ICorDebugEval::NewArray (Método)
Asigna una nueva matriz del tipo de elemento y las dimensiones especificadas.  
  
 Este método está obsoleto en la .NET Framework versión 2,0. Use [ICorDebugEval2:: NewParameterizedArray (](icordebugeval2-newparameterizedarray-method.md) en su lugar.  
  
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
  
## <a name="remarks"></a>Observaciones  
 La matriz siempre se crea en el dominio de aplicación en el que se está ejecutando el subproceso.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** 1,1, 1,0
