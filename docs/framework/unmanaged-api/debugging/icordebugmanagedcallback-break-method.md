---
title: ICorDebugManagedCallback::Break (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.Break
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::Break
helpviewer_keywords:
- Break method [.NET Framework debugging]
- ICorDebugManagedCallback::Break method [.NET Framework debugging]
ms.assetid: 7d78a301-82b3-43b2-9d65-3cda3285ae97
topic_type:
- apiref
ms.openlocfilehash: f70a88df00d15729a6bde06b49417b6439f7c0ec
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212482"
---
# <a name="icordebugmanagedcallbackbreak-method"></a>ICorDebugManagedCallback::Break (Método)

Notifica al depurador cuando <xref:System.Reflection.Emit.OpCodes.Break> se ejecuta una instrucción en la secuencia de código.

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT Break (
    [in] ICorDebugAppDomain *pAppDomain,
    [in] ICorDebugThread    *thread
);
```

## <a name="parameters"></a>Parámetros

`pAppDomain`\
de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene la instrucción break.

`thread`\
de Un puntero a un objeto ICorDebugThread que representa el subproceso que contiene la instrucción break.

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).

**Encabezado:** CorDebug.idl, CorDebug.h

**Biblioteca:** CorGuids.lib

**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>Consulte también

- [ICorDebugManagedCallback (Interfaz)](icordebugmanagedcallback-interface.md)
