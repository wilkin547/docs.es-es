---
title: ICorDebugCode2::GetCodeChunks (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugCode2.GetCodeChunks
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode2::GetCodeChunks
helpviewer_keywords:
- GetCodeChunks method [.NET Framework debugging]
- ICorDebugCode2::GetCodeChunks method [.NET Framework debugging]
ms.assetid: 210a2f02-2678-4555-bc4a-78a0408764c8
topic_type:
- apiref
ms.openlocfilehash: e419ebb6ffd404368baf32e591e08c4a70645127
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121121"
---
# <a name="icordebugcode2getcodechunks-method"></a>ICorDebugCode2::GetCodeChunks (Método)

Obtiene los fragmentos de código de los que está compuesto este objeto de código.

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT GetCodeChunks (
    [in]  ULONG32     cbufSize,
    [out] ULONG32     *pcnumChunks,
    [out, size_is(cbufSize), length_is(*pcnumChunks)]
        CodeChunkInfo chunks[]
);
```

## <a name="parameters"></a>Parámetros

`cbufSize`  
de Tamaño de la matriz de `chunks`.

`pcnumChunks`  
enuncia El número de fragmentos devueltos en la matriz de `chunks`.

`chunks`  
enuncia Una matriz de estructuras "CodeChunkInfo (", cada una de las cuales representa un único fragmento de código. Si el valor de `cbufSize` es 0, este parámetro puede ser null.

## <a name="remarks"></a>Comentarios

Los fragmentos de código nunca se superpondrán y seguirán el orden en el que se habrían concatenado mediante [ICorDebugCode:: getCode](icordebugcode-getcode-method.md). Un objeto de código de lenguaje intermedio de Microsoft (MSIL) de la .NET Framework versión 2,0 incluirá un único fragmento de código.

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).

**Encabezado:** CorDebug.idl, CorDebug.h

**Biblioteca:** CorGuids.lib

**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
