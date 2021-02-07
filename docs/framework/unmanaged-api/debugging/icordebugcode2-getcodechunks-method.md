---
description: 'Más información sobre: ICorDebugCode2:: Getcodechunks ((método)'
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
ms.openlocfilehash: 371d077466ff2390293d9d4e320d4c95a992fe54
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99764975"
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
de Tamaño de la `chunks` matriz.

`pcnumChunks`  
enuncia El número de fragmentos devueltos en la `chunks` matriz.

`chunks`  
enuncia Una matriz de estructuras "CodeChunkInfo (", cada una de las cuales representa un único fragmento de código. Si el valor de `cbufSize` es 0, este parámetro puede ser null.

## <a name="remarks"></a>Observaciones

Los fragmentos de código nunca se superpondrán y seguirán el orden en el que se habrían concatenado mediante [ICorDebugCode:: getCode](icordebugcode-getcode-method.md). Un objeto de código de lenguaje intermedio de Microsoft (MSIL) de la .NET Framework versión 2,0 incluirá un único fragmento de código.

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).

**Encabezado:** CorDebug.idl, CorDebug.h

**Biblioteca:** CorGuids.lib

**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
