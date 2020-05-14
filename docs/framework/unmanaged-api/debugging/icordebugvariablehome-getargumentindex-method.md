---
title: 'ICorDebugVariableHome:: GetArgumentIndex (método)'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetArgumentIndex
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetArgumentIndex
helpviewer_keywords:
- ICorDebugVariableHome::GetArgumentIndex method [.NET Framework debugging]
- GetArgumentIndex method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: e86fcc72-388d-4009-ab21-8f9c3323e9a3
topic_type:
- apiref
ms.openlocfilehash: 27a676fd1d2d7903943e44f8a7201b88af4fba89
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396993"
---
# <a name="icordebugvariablehomegetargumentindex-method"></a>ICorDebugVariableHome:: GetArgumentIndex (método)

Obtiene el índice de un argumento de función.

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT GetArgumentIndex(
    [out] ULONG32* pArgumentIndex
);
```

## <a name="parameters"></a>Parámetros

`pArgumentIndex`\
enuncia Puntero al índice del argumento.

## <a name="return-value"></a>Valor devuelto

El método devuelve los valores siguientes.

|Valor|Descripción|
|-----------|-----------------|
|`S_OK`|La llamada al método devolvió un índice de argumento válido.|
|`E_FAIL`|La instancia de [ICorDebugVariableHome](icordebugvariablehome-interface.md) actual representa una variable local.|

## <a name="remarks"></a>Comentarios

El índice de argumento se puede utilizar para recuperar los metadatos de este argumento.

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).

**Encabezado:** CorDebug.idl, CorDebug.h

**Biblioteca:** CorGuids.lib

**.NET Framework versiones:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]

## <a name="see-also"></a>Vea también

- [Interfaz ICorDebugVariableHome](icordebugvariablehome-interface.md)
