---
title: ICorDebugEval::CallFunction (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugEval.CallFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::CallFunction
helpviewer_keywords:
- ICorDebugEval::CallFunction method [.NET Framework debugging]
- CallFunction method [.NET Framework debugging]
ms.assetid: 7f470c5c-e1c0-4d8d-aad8-830f113ae751
topic_type:
- apiref
ms.openlocfilehash: 4ac26ef4449dc02230f26b1247616b4587d217b7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73085159"
---
# <a name="icordebugevalcallfunction-method"></a>ICorDebugEval::CallFunction (Método)

Configura una llamada a la función especificada.

Este método está obsoleto en la .NET Framework versión 2,0. Use [ICorDebugEval2:: CallParameterizedFunction (](icordebugeval2-callparameterizedfunction-method.md) en su lugar.

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT CallFunction (
    [in] ICorDebugFunction  *pFunction,
    [in] ULONG32            nArgs,
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]
);
```

## <a name="parameters"></a>Parámetros

`pFunction`\
de Puntero a un objeto ICorDebugFunction que especifica la función a la que se va a llamar.

`nArgs`\
de El número de argumentos de la función.

`ppArgs`\
de Matriz de punteros, cada uno de los cuales señala a un objeto ICorDebugValue que especifica un argumento que se va a pasar a la función.

## <a name="remarks"></a>Comentarios

Si la función es virtual, `CallFunction` realizará el envío virtual. Si la función está en un dominio de aplicación diferente, se producirá una transición siempre y cuando todos los argumentos estén también en ese dominio de aplicación.

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).

**Encabezado:** CorDebug.idl, CorDebug.h

**Biblioteca:** CorGuids.lib

**.NET Framework versiones:** 1,1, 1,0

## <a name="see-also"></a>Vea también

- [CallParameterizedFunction (método)](icordebugeval2-callparameterizedfunction-method.md)
