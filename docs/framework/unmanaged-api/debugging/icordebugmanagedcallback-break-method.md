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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bab20301c5413f8bbe95d44b87e06d3b3870c9e7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988371"
---
# <a name="icordebugmanagedcallbackbreak-method"></a>ICorDebugManagedCallback::Break (Método)

Notifica al depurador cuando un <xref:System.Reflection.Emit.OpCodes.Break> se ejecuta la instrucción en la secuencia de código.

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT Break (
    [in] ICorDebugAppDomain *pAppDomain,
    [in] ICorDebugThread    *thread
);
```

## <a name="parameters"></a>Parámetros

`pAppDomain`\
[in] Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene la instrucción break.

`thread`\
[in] Un puntero a un objeto ICorDebugThread que representa el subproceso que contiene la instrucción break.

## <a name="requirements"></a>Requisitos

**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).

**Encabezado**: CorDebug.idl, CorDebug.h

**Biblioteca:** CorGuids.lib

**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>Vea también

- [ICorDebugManagedCallback (interfaz)](icordebugmanagedcallback-interface.md)