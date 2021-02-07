---
description: 'Más información acerca de: ICorDebugEval:: CallFunction (método)'
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
ms.openlocfilehash: c0978ab3bdffc83e3eb5e3a6553e7f374ab6d5da
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99694193"
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

## <a name="remarks"></a>Observaciones

Si la función es virtual, `CallFunction` realizará el envío virtual. Si la función está en un dominio de aplicación diferente, se producirá una transición siempre y cuando todos los argumentos estén también en ese dominio de aplicación.

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).

**Encabezado:** CorDebug.idl, CorDebug.h

**Biblioteca:** CorGuids.lib

**.NET Framework versiones:** 1,1, 1,0

## <a name="see-also"></a>Vea también

- [Método CallParameterizedFunction](icordebugeval2-callparameterizedfunction-method.md)
