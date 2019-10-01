---
title: ICorDebugCodeEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugCodeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCodeEnum::Next
helpviewer_keywords:
- ICorDebugCodeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: 644ece86-384d-4c63-9fba-52c789616ff7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 076b5d628dfe83decdbbe2f5e74c50e08262c580
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700695"
---
# <a name="icordebugcodeenumnext-method"></a>ICorDebugCodeEnum::Next (Método)

Obtiene el número especificado de instancias de "ICorDebugCode" de la enumeración, comenzando en la posición actual.

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT Next (
    [in] ULONG  celt,
    [out, size_is(celt), length_is(*pceltFetched)]
        ICorDebugCode *values[],
    [out] ULONG *pceltFetched
);
```

## <a name="parameters"></a>Parámetros

 `celt`  
 de Número de instancias de @no__t 0 que se van a recuperar.

 `values`  
 enuncia Matriz de punteros, cada uno de los cuales señala a un objeto `ICorDebugCode`.

 `pceltFetched`  
 enuncia Un puntero al número de instancias `ICorDebugCode` devueltas realmente. Este valor puede ser null si `celt` es uno.

## <a name="requirements"></a>Requisitos

 **Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).

 **Encabezado**: Cordebug. idl, Cordebug. h

 **Biblioteca** CorGuids.lib

 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
 
