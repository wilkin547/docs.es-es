---
description: 'Más información sobre: ICorDebugCodeEnum (:: Next (método)'
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
ms.openlocfilehash: 51d46718891ce3df537c675175eacc4e33b92f79
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99764780"
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
de El número de `ICorDebugCode` instancias que se van a recuperar.

`values`  
enuncia Matriz de punteros, cada uno de los cuales señala a un `ICorDebugCode` objeto.

`pceltFetched`  
enuncia Puntero al número de `ICorDebugCode` instancias devueltas realmente. Este valor puede ser null si `celt` es uno.

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).

**Encabezado:** CorDebug.idl, CorDebug.h

**Biblioteca:** CorGuids.lib

**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
