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
ms.openlocfilehash: 12d4e63480f03bfad613f30362ddaeaf12b57a88
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791049"
---
# <a name="icordebugvariablehomegetargumentindex-method"></a>ICorDebugVariableHome:: GetArgumentIndex (método)

Obtiene el índice de un argumento de función.

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT GetArgumentIndex(
    [out] ULONG32* pArgumentIndex
);
```

## <a name="parameters"></a>Parameters

`pArgumentIndex`\
enuncia Puntero al índice del argumento.

## <a name="return-value"></a>Valor devuelto

El método devuelve los valores siguientes.

|{2&gt;Value&lt;2}|Descripción|
|-----------|-----------------|
|`S_OK`|La llamada al método devolvió un índice de argumento válido.|
|`E_FAIL`|La instancia de [ICorDebugVariableHome](icordebugvariablehome-interface.md) actual representa una variable local.|

## <a name="remarks"></a>Notas

El índice de argumento se puede utilizar para recuperar los metadatos de este argumento.

## <a name="requirements"></a>Requisitos de

**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).

**Encabezado:** CorDebug.idl, CorDebug.h

**Biblioteca:** CorGuids.lib

**.NET Framework versiones:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]

## <a name="see-also"></a>Vea también

- [ICorDebugVariableHome (interfaz)](icordebugvariablehome-interface.md)
