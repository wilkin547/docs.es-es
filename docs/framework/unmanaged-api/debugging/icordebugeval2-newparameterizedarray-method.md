---
description: 'Más información sobre: ICorDebugEval2:: NewParameterizedArray ((método)'
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
ms.openlocfilehash: 0ce8582328013ad02357361f05efb55ade8780e5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99693751"
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
  
## <a name="remarks"></a>Observaciones  

 Los elementos de la matriz pueden ser instancias de un tipo genérico. La matriz siempre se crea en el dominio de aplicación en el que el subproceso se está ejecutando actualmente. En el .NET Framework 2,0, el valor de `rank` debe ser 1.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
